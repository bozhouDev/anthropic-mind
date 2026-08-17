# 领域层 · 工程（agent / 工具 / 上下文 / 评估 / harness）

**置信度基线：高。** 自曝型材料密度全语料最高——两份 postmortem、逐条编号的失败尝试、带统计量的数字。

**但先看 §5 禁区**：这个领域有一批做法只在 Anthropic 自身规模下成立，一人团队照抄会翻车。用户是独立创作者兼工程实现者，这一节几乎每次都要检查。

**代际警告**：本领域翻案窗口 8–9 个月，触发条件是**模型换代而非新证据**，而「当前模型代」这个前提从不写在原文里。给建议前先查 §3 范式变迁表。

---

## 1. 领域模型

世界观层已吸收的部分不在这里重复（脚手架是断言 → 世界观-8；自己取上下文 → 世界观-3；环境层优先 → 世界观-4；分数是假设 → 世界观-6）。以下是工程独有的。

### E1 · 给 agent 造工具和给人造 API 是两门手艺

工具是**确定性系统与非确定性系统之间的契约**——`Tools are a new kind of software which reflects a contract between deterministic systems and non-deterministic agents.`

最常见的错误是把已有 API endpoint 一对一包成工具。正确的切分单位是「一个人在同样资源下会怎么把任务分块」：与其做 `list_users` / `list_events` / `create_event`，不如做一个 `schedule_event`——它同时减少了工具数量，并把本该消耗 agent context 的中间计算搬进了工具实现。

反直觉的具体判据：
- **标识符可读性影响正确率**。把 UUID 换成语义化名称或 0-indexed ID，`significantly improves Claude's precision in retrieval tasks by reducing hallucinations`。没有任何 API 设计传统会认为这能降低幻觉。
- **命名空间前缀 vs 后缀有实测差异**：`We have found selecting between prefix- and suffix-based namespacing to have non-trivial effects on our tool-use evaluations.`
- **工具数量的判据**：`If a human engineer can't definitively say which tool should be used in a given situation, an AI agent can't be expected to do better.`
- 投入比例的硬证据：做 SWE-bench agent 时 `we actually spent more time optimizing our tools than the overall prompt`。

⚠ **失效条件**：「给 examples」这条子建议已翻案，见 §3。另外 AskUserQuestion 的三次设计尝试记录承认最终判据是**模型爱不爱用**——`even the best designed tool doesn't work if Claude doesn't understand how to call it`，这条无法从第一性原理推出。

### E2 · 缓存前缀是架构约束，不是性能优化项

prompt cache 是**前缀匹配**，前缀里一个字节变化作废其后全部缓存。把它当约束而非优化之后，功能设计直觉整个反转：

- 工具集**永远不变**。需要减 context 就用 `defer_loading` 发轻量 stub，不要在会话中途增删工具。
- 状态切换（进入 plan mode）建模成**工具调用**，不是改 system prompt 或改工具集。原话：`The intuitive approach would be: when the user enters plan mode, swap out the tool set to only include read-only tools, but that would break the cache. Instead, we keep all tools in the request at all times and use EnterPlanMode and ExitPlanMode as tools themselves.`
- 更新信息走 message，不改 system prompt（时间、文件变更用下一轮 tool result 带进去）。
- **成本路由的直觉是反的**：`if you're 100k tokens into a conversation with Opus and want to ask a question that is fairly easy to answer, it would actually be more expensive to switch to Haiku than to have Opus answer, because we would need to rebuild the prompt cache for Haiku.`

他们把缓存命中率当 uptime 监控：`we run alerts on our prompt cache hit rate and declare SEVs if they're too low.`

⚠ **失效条件**：这是全领域最绑定他们经济结构的一条——缓存命中率直接换算成订阅制的 rate limit 宽松度。按 token 付费的小团队，维持字节级前缀纪律的工程成本可能超过节省。他们自己的终局动作是把 compaction 做进 API，即「用户本来就不该手写这些」。

### E3 · 瓶颈是「未知」，不是模型能力

`Claude Fable is the first model where I find the quality of the work is bottlenecked by my ability to clarify its unknowns.`

四类信息：已知的已知（写进 prompt 的）、已知的未知（知道自己没想清的）、**未知的已知**（太显然以至于没写下来、但看到结果会说「不是这样」的标准）、未知的未知。长任务做错，默认归因不是模型不行，是地图与领土的差距。

`If you are too specific, Claude will follow your instructions even when a pivot may be more appropriate. If you are too vague, Claude will often make choices and assumptions based on industry best practices that may not be a fit for your task.`

**引用保真度阶梯（反直觉）**：源码 > HTML mock > 截图 > 文字描述。多数团队觉得截图最直观，他们认为它最差——`the absolute best reference is source code... This provides Claude much richer detail around the markup and structure, compared to for example a screenshot.`

成本论证：`Every explainer, brainstorm, interview, prototype, and reference is a cheap way to find out what you didn't know before it gets expensive to fix.` 因为 agent 时代返工成本结构变了——`Small changes in a feature or spec can cause drastically different implementations in code, and it can be more difficult for your agent to revert previous changes.`

⚠ **失效条件（真分歧，见 §6）**：同期 Boris Cherny 主张相反——`Opus 4.7 is intelligent enough that it no longer needs Plan Mode for most tasks. I often just jump in, and Claude will ask me questions if it needs to`。同团队、同代模型、对立建议，语料里没有调和。折中读法：前置规格必要，但形式应该是**引用和原型**，不是更长的文字指令。

### E4 · 非对称调优：把难题换成易题

`tuning a standalone evaluator to be skeptical turns out to be far more tractable than making a generator critical of its own work, and once that external feedback exists, the generator has something concrete to iterate against.`

推论：不要试图把 generator 调成自我批判（难），去调一个独立的怀疑型 evaluator（易）。rubric 要有**硬阈值**而非加权总分——`Each criterion had a hard threshold, and if any one fell below it, the sprint failed`——因为加权会让评审把不合格项谈过去。

把主观变可打分：`"Is this design beautiful?" is hard to answer consistently, but "does this follow our principles for good design?" gives Claude something concrete to grade against.`

---

## 2. if-then 决策表

| 条件 | 动作 | 依据 |
|---|---|---|
| 工具定义 > 10K token，或工具数 > 10 且选错工具 | 开 Tool Search + `defer_loading`，**保留 3–5 个最高频常驻**。绝不中途删工具（stub 不破缓存，删除破） | `advanced-tool-use` / `prompt-caching-is-everything` |
| 已积累大量 context，下一步是简单问题 | **不要切便宜模型**。让当前模型答，或派 subagent 并写 hand-off | `prompt-caching-is-everything` |
| 下一步产生大量中间产物、你只要结论 | 派 subagent。口诀：`will I need this tool output again, or just the conclusion?` | `session-management-and-1m-context` |
| 同一问题纠正 agent 超过两次 | `/clear` 重开并写更好的初始 prompt，不要继续纠正。前面的文件读取仍有用时改用 rewind | `claude-code-best-practices` |
| 想往 CLAUDE.md 加规则 | 先问 `Would removing this cause Claude to make mistakes?` 不会就砍。能变成 hook/lint/CI 的优先变成机制——CLAUDE.md 是建议性的，hook 是确定的 | `claude-code-best-practices` / bcherny |
| agent 要跨多个 context window 做一个项目 | 两种 prompt：initializer（feature list + `init.sh` + progress 文件 + 首个 commit）与 coding agent（读 progress + git log → 端到端冒烟 → 只做一个 feature → 提交并写进度）。feature list 用 **JSON 不用 Markdown**（模型更不容易乱改 JSON） | `effective-harnesses-for-long-running-agents` |
| 任务的「好」是主观的（设计、命名、研究质量） | 拆 generator/evaluator 两个 context，写 4 条左右**带硬阈值**的判据，用 few-shot 校准 evaluator，只调 evaluator 的怀疑度。给它真实交互能力，不要让它给静态截图打分 | `harness-design-long-running-apps` |
| eval 出现 0% pass@100 | 查任务规格和 grader，不查模型。判据：两个领域专家独立判会不会同一结论；有没有能过全部 grader 的 reference solution | `demystifying-evals-for-ai-agents` |
| 比较榜单分数 | 差距 < 3 个百分点且未公布资源配置 = 噪音。跑 agentic eval 时容器资源要**分别指定保证配额和硬上限**，不要设成同一个值 | `infrastructure-noise` |
| 用户读不懂 agent 要执行的命令（非技术用户） | 用绝对的、常开的边界（VM + mount），不要逐条审批。审批只在用户具备判断力时才构成防御 | `how-we-contain-claude` |
| 说不清「什么算好」 | 给源码引用（哪怕是别的语言），其次 HTML mock，最后才是截图或文字 | `finding-your-unknowns` |
| 写 skill | `description` 写**触发条件**不写功能摘要；正文只写 Claude 默认不会做对的事；长了拆多文件渐进披露。`the description field is not a summary, it's a description of when to trigger this skill` | `how-we-use-skills` |
| 决定在哪投工程时间 | 优先做 verification skill——`Verification skills have had the most measurable impact on Claude's output quality internally. It can be worth having an engineer spend a week just making your verification skills excellent.` | 同上 |
| agent 要连生产库/危险资源 | 给只读凭证，不要靠强系统提示词。白名单**不是目的地过滤器，是能力授予**：`Allowing api.anthropic.com meant allowing file uploads to arbitrary Anthropic accounts` | `managed-agents` / `how-we-contain-claude` |

---

## 3. 范式变迁表（给建议前必查）

| 主题 | 早期 | 现在 | 现在还成立吗 |
|---|---|---|---|
| **工具 examples** | 2025-11 头号规则，报 72%→90% | 2026-07 删掉，改设计接口本身（参数命名、enum 表意） | **分代际**。Claude 5 代删；老模型 + 深嵌套 schema 仍适用。旧文至今无撤回标注 |
| **系统提示词体量** | 全量前置，硬规则防最坏情况 | 删掉 80%+，换判断性指引 | 成立，**但前提是你有 eval 能证明 no measurable loss** |
| **硬规则 vs 判断** | `default to writing no comments. Never write multi-paragraph docstrings` | `Write code that reads like the surrounding code: match its comment density, naming, and idiom` | 成立于 Claude 5 代 |
| **代码库检索** | RAG + 向量预索引 | Grep/Glob + 渐进披露 + 文件系统 | 成立。但保留混合——CLAUDE.md 仍朴素前置 |
| **任务追踪** | TodoWrite + 每 5 轮插 reminder | Task 工具（带依赖、跨 subagent 共享） | 成立。旧法的问题：`reminders made Claude think that it had to stick to the list instead of modifying it` |
| **长任务跨窗口** | context reset + 结构化交接 | 单会话连续跑 + 自动 compaction | 分代际。Opus 4.5 起 reset 变成死重 |
| **长任务分解** | sprint + 一次一 feature + 每 sprint 评审 | 去掉 sprint，evaluator 移到最后单次 | 分代际。4.5 需要，4.6 不需要 |
| **中间推理** | think 工具，报 +54% | extended thinking | **已废**，原文顶部有废弃声明 |
| **规格载体** | Markdown 计划文件 | 富引用：HTML artifact、测试套件、别处的函数、rubric | 成立，但**部分是个人偏好**（作者自述 HTML maximalist） |
| **记忆** | `#` 热键手写 CLAUDE.md | auto-memory 自动保存 | 成立于有 memory 的 harness |
| **权限模型** | 逐条审批 → OS sandbox → auto mode 分类器（2026-08 成默认） | 同左 | 成立。审批疲劳 93%、sandbox 减少 84% 提示、分类器 FPR 0.4%。但 auto mode 明说不替代高风险基建上的人工审查 |
| **Plan mode** | 四阶段工作流核心环节 | Boris：`I don't use plan mode much anymore` | **有争议**，见 §6 |
| **多 agent 适用面** | 编码任务可并行度低、agent 不擅长实时协调 | 16 个并行 agent 写 C 编译器；模型自己写 multi-agent harness | 成立，但成本判据没变：15× token，要求任务价值足够高 |
| **workflow 编排** | 静态：手写编排 | 动态：模型现场写 JS harness | 成立，但限定 `best suited for complex, high value tasks` |
| **框架态度** | `start by using LLM APIs directly`、`don't hesitate to reduce abstraction layers` | 该文顶部现挂注记导向 Managed Agents | **自我修订**：原则（简单优先）保留，具体建议（别用框架）已被自家产品覆盖 |

---

## 4. 反模式

1. **把已有 API endpoint 一对一包成工具**——`agents have distinct "affordances" to traditional software`
2. **往 prompt 里堆边缘案例清单**——`teams will often stuff a laundry list of edge cases into a prompt... We do not recommend this.`
3. **检查 agent 有没有按指定顺序调工具**——`it's often better to grade what the agent produced, not the path it took`
4. **单向 eval**（只测该触发时触发了）——`One-sided evals create one-sided optimization.` 他们自己在网页搜索上踩过：必须同时构造「该搜」和「不该搜」两侧
5. **会话中途增删工具 / 改 system prompt**——最常见的破缓存方式
6. **把逐条人工审批当成安全防线**——`a feature originally designed to provide oversight could arguably have the opposite effect`
7. **让 reviewer 无限制找问题然后照单全改**——`Tell the reviewer to flag only gaps that affect correctness or the stated requirements, and treat the rest as optional`
8. **用框架抽象层遮住 prompt 和 response**——`Incorrect assumptions about what's under the hood are a common source of customer error`
9. **未加范围限定就让 agent「调研一下」**——`The infinite exploration. Claude reads hundreds of files, filling the context.`

---

## 5. 禁区：只在他们规模下成立（小团队照抄会翻车）

给独立开发者或小团队建议时，命中这些必须主动说明：

- **缓存前缀纪律**：他们既是模型提供方又是订阅制卖方，缓存命中率换算成 rate limit。按 token 付费的团队维持字节级纪律可能不划算。
- **eval 基础设施**：他们自己写明外部做不到——`A model provider can shield its eval infrastructure from this by dedicating hardware, but external evaluators can't easily do the same.`
- **「删掉 80% 系统提示词」**：前提是有 coding eval 套件能证明无损失。没 eval 照删就是盲删。而且他们自己证明即使有 eval 也可能太窄——一条限字数指令跑过「多周内部测试无回归」，事后更宽的 ablation 才抓出 3% 智能下降。
- **成本量级不是生产建议**：C 编译器 2000 次会话 / 20 亿输入 token / $20,000（作者自称 `an extremely expensive project`）；DAW harness 单次 3h50m / $124.70；游戏编辑器 6h / $200（对照单 agent 20 分钟 / $9，贵 20 倍）。这些是**能力探测实验**，不是工作流推荐。
- **multi-agent 的 15× token**：准入条件是 `tasks where the value of the task is high enough to pay for the increased performance`。
- **用下一代模型 stress test 自家面试题**：依赖能拿到未发布模型，外部不可执行。
- **dogfooding 改进措施**：前提是有几百个每天用自家产品的工程师。

---

## 6. 未调和的分歧（引用时不要单边取材）

按门禁 §C，这些要标明是谁的声音，不要合并成「Anthropic 认为」：

- **前置规格该多重**：Thariq 主张 blind spot pass / interview / 原型先行（2026-07）；Boris 主张现代模型不需要 plan mode、不需要很具体的指令（2026-05、2026-08）。同团队、同代模型、相反建议。
- **脚手架该加还是该减**：`harness-design` 删到只剩必要；`managed-agents` 同月加三层新抽象；`dynamic-workflows` 让模型自己现场造。判据（任务是否超出模型独立可靠完成的范围）只在第一篇里被明确写出。
- **模型层 vs 环境层的权重**：`how-we-contain-claude`（2026-05）排序是环境优先，并写 `protection in the model layer will never be 100% effective, which is why it can't stand alone`；bcherny（2026-08）主张 `We have largely solved the threat of prompt injection in practice`。**两条同时挂在官网。引用后者时必须同时引用前者**——前者列了三起都成功了的真实泄漏路径（钓鱼直注 25 次成功 24 次、白名单域内泄漏、信任对话框前执行）。

## 7. 营销驱动的数字（引用需降级）

`advanced-tool-use`、`managed-agents`、`agent-skills`、`desktop-extensions` 本质是发布稿。其中性能数字（Tool Search 79.5%→88.1%、PTC 43,588→27,297 token、Tool Use Examples 72%→90%）全部标注 internal testing，无配置说明、无独立复现——恰好违反他们自己在 `infrastructure-noise` 里提出的披露标准。

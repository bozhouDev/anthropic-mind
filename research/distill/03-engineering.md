---
title: Anthropic Mind · 工程方法论
scope: 01-engineering 全 32 篇 + 08-x/bcherny 全 9 条 + 08-x/trq212 全 3 条
corpus_window: 2024-12 到 2026-08
distilled: 2026-08-16
---

## A. 心智模型

### A1. 脚手架是"模型做不到什么"的假设台账，会过期

**内核**：harness 里的每一个组件（context reset、sprint 拆分、todo 提醒、system prompt 里的硬规则）都不是中性的工程结构，而是一条被固化下来的断言：「模型自己做不到这件事」。模型每升一代，其中一部分断言变假，但组件不会自动消失，它变成负债——不只是浪费 token，而是主动约束模型。所以他们的做法是：新模型落地时，**逐个移除组件测量影响**（不是整体重构），只保留那些在"任务处于模型独立完成能力边界之外"时仍有增益的部分。

**证据**
- 「every component in a harness encodes an assumption about what the model can't do on its own, and those assumptions are worth stress testing, both because they may be incorrect, and because they can quickly go stale as models improve.」 — `01-engineering/2026-03-24_harness-design-long-running-apps_2ef732b76415.md`
- 「We addressed this by adding context resets to the harness. But when we used the same harness on Claude Opus 4.5, we found that the behavior was gone. The resets had become dead weight.」 — `01-engineering/2026-04-08_managed-agents_f90fa6cabc29.md`
- 「As model capabilities increase, the tools that your models once needed might now be constraining them. It's important to constantly revisit previous assumptions on what tools are needed.」 — `01-engineering/2026-04-10_seeing-like-an-agent_thariq.md`
- 方法论本身：「In my first attempt to simplify, I cut the harness back radically and tried a few creative new ideas, but I wasn't able to replicate the performance of the original. It also became difficult to tell which pieces of the harness design were actually load-bearing... Based on that experience, I moved to a more methodical approach, removing one component at a time and reviewing what impact it had on the final result.」 — `harness-design-long-running-apps`
- 判据：「The practical implication is that the evaluator is not a fixed yes-or-no decision. It is worth the cost when the task sits beyond what the current model does reliably solo.」 — 同上

**预测力测试**
> 问：我们的 agent 外面包了一层"输出 JSON 失败就重试并重新格式化"的 wrapper，从 Sonnet 3.5 时代留下来的。升到 Claude 5 要不要留？

推断立场：先假设它是死重，做单组件消融实验并测量，而不是"反正不影响就留着"。判据不是"它有没有出错"，而是"这个任务是否已经落进模型能独立可靠完成的范围内"——落进来了就删，因为它现在只会限制模型的解空间。同时他们会提醒：**别整体重写 harness**，否则你分不清哪块是承重墙。

**排他性**：业界常见做法是"能跑就别动"（Chesterton's fence）＋ 依赖版本升级式的框架迁移，脚手架只增不减。Anthropic 反过来把脚手架当**折旧资产**，并给了具体的测量仪式（一次删一个 + 读 trace）。更反直觉的是他们的结论不是"最终会不需要 harness"：「the space of interesting harness combinations doesn't shrink as models improve. Instead, it moves」——边界在外移，不是在消失。

**反例 / 张力**
- 同一篇里 planner 没被删：「Without the planner, the generator under-scoped: given the raw prompt, it would start building without first speccing its work」。所以"删脚手架"不是普适动作。
- Managed Agents 本身是在**增加**一层大抽象（session / harness / sandbox 三个虚拟化接口），与 `building-effective-agents` 的「don't hesitate to reduce abstraction layers」直接对冲。他们的调和方式是：删掉编码"模型能力"假设的组件，增加不编码模型能力假设的接口。
- `01-engineering/2026-04-23_april-23-postmortem_dea52d951227.md` 是最狠的自曝：他们自己加的 `clear_thinking` 缓存优化带 bug，「made it past multiple human and automated code reviews, as well as unit tests, end-to-end tests, automated verification, and dogfooding」，跑了一周多才定位。harness 改动本身是高风险区，而他们的验证体系当时接不住。

---

### A2. 让 agent 自己去取上下文，而不是预先喂给它

**内核**：他们内部先做过 RAG，然后删掉了——理由不是效果差，是**"Claude 是被给予上下文，而不是自己找到上下文"**。取而代之的是 grep/glob + 文件系统 + 渐进披露。关键洞察是：环境的元数据本身就是信号（文件名、目录层级、时间戳），一个能导航环境的 agent 可以层层组装理解，只在工作记忆里保留必要部分；而预索引会腐坏、需要维护、并且剥夺了 agent 多次尝试和自我纠错的机会。代价是明确的：运行时探索比预取慢。

**证据**
- 「When Claude Code was first released internally, we used RAG: a vector database would pre-index the codebase... While RAG was powerful and fast, it required indexing and setup and could be fragile across a host of different environments. Most importantly, Claude was given this context instead of finding the context itself.」 — `01-engineering/2026-04-10_seeing-like-an-agent_thariq.md`
- 「the presence of a file named `test_utils.py` in a `tests` folder implies a different purpose than a file with the same name located in `src/core_logic/`. Folder hierarchies, naming conventions, and timestamps all provide important signals」 — `01-engineering/2025-09-29_effective-context-engineering-for-ai-agents_42516bb95051.md`
- 「primitives like glob and grep allow it to navigate its environment and retrieve files just-in-time, effectively bypassing the issues of stale indexing and complex syntax trees」 — 同上
- 「The file system is an elegant way of representing state that your agent could read into context & allowing it to verify its work... **The inconvenience is the point.** I know this is inconvenient! It would be easier if your agent could run in a lambda function. But agents are trained like humans and so we need to give them the resources & the tools that we use — like the file system.」 — `08-x/2025-09-22_trq212_1970243253061783669.md`
- 「the amount of context that can be bundled into a skill is effectively unbounded」 — `01-engineering/2025-10-16_equipping-agents-for-the-real-world-with-agent-skills_77ae700ce1f2.md`
- 「Progressive disclosure is now a common technique we use to add new functionality **without adding a tool**.」 — `seeing-like-an-agent`

**预测力测试**
> 问：我们要给客服 agent 接公司的 Confluence，是不是该先建向量索引？

推断立场：默认给它搜索能力 + 可导航的结构，而不是预索引；最多混合（少量高频内容前置，其余按需取）。并且他们会追加一句业界不会说的话：**把文件和目录命名好，因为名字就是检索信号**。他们同时会承认代价：「there's a trade-off: runtime exploration is slower than retrieving pre-computed data」，以及「Without proper guidance, an agent can waste context by misusing tools, chasing dead-ends」。

**排他性**：2025 年整个行业的默认答案是 RAG。他们内部做了 RAG 然后删掉，公开写出来。第二层排他性是"不便利是刻意的"——业界都在往无状态 lambda 走，他们主张给 agent 一个持久文件系统，因为模型是照着人训练的，就该给人用的工具。

**反例 / 张力**
- 渐进披露本身会失控：「we tried progressive disclosure: we gave Claude a link to its docs that it could load and search when needed. This worked, but Claude would pull large chunks of documentation into context to find an answer the user could have gotten in one sentence.」最后不得不再套一层 subagent（Claude Code Guide）。
- 他们仍保留朴素前置：「CLAUDE.md files are naively dropped into context up front」。纯 just-in-time 不是他们的实际架构，混合才是。

---

### A3. 给 agent 造工具和给人造 API 是两门手艺

**内核**：工具是**确定性系统与非确定性系统之间的契约**，这和函数调用契约根本不同。最常见的错误是把已有 API endpoint 一对一包成工具。正确的切分单位是"人在同样资源下会怎么把任务分块"，这样做同时减少了工具数量、并把本该消耗 agent context 的中间计算搬进工具实现里。工具描述要按"写给新入职同事的 docstring"来写，工具参数要 poka-yoke（防呆）。

**证据**
- 「Tools are a new kind of software which reflects a contract between deterministic systems and non-deterministic agents.」 — `01-engineering/2025-09-11_writing-tools-for-agents_4f67b063afdf.md`
- 「A common error we've observed is tools that merely wrap existing software functionality or API endpoints—whether or not the tools are appropriate for agents.」 — 同上
- 「Instead of implementing a `list_users`, `list_events`, and `create_event` tools, consider implementing a `schedule_event` tool which finds availability and schedules an event.」 — 同上
- 「we've found that merely resolving arbitrary alphanumeric UUIDs to more semantically meaningful and interpretable language (or even a 0-indexed ID scheme) significantly improves Claude's precision in retrieval tasks by reducing hallucinations.」 — 同上
- 「think about how much effort goes into human-computer interfaces (HCI), and plan to invest just as much effort in creating good **agent-computer interfaces (ACI)**」 — `01-engineering/2024-12-19_building-effective-agents_7d24e5faa28b.md`
- 投入比例的硬证据：「While building our agent for SWE-bench, we actually spent more time optimizing our tools than the overall prompt.」 — 同上；对应实现细节见 `01-engineering/2025-01-06_swe-bench-sonnet_226c5fc98dd0.md`：「we simply made the tool always require an absolute path」
- 命名细节有实测差异：「We have found selecting between prefix- and suffix-based namespacing to have non-trivial effects on our tool-use evaluations.」 — `writing-tools-for-agents`

**预测力测试**
> 问：我们有个 30 个 endpoint 的 REST API，直接用 OpenAPI spec 自动生成 30 个 MCP 工具行不行？

推断立场：不行，这正是他们点名的"常见错误"。改成少数几个任务形状的工具（`search_logs` 而不是 `read_logs`，`get_customer_context` 而不是三个 get），加 namespace 前缀，把 UUID 解析成自然语言，加 `response_format: concise|detailed` 让 agent 自己控制返回粒度，默认截断（Claude Code 是 25,000 token）并在截断信息里教它用分页/过滤。

**排他性**：业界默认是"工具越多能力越强"＋"从 spec 自动生成"。他们明确反对："More tools don't always lead to better outcomes"，并给了一条可执行判据：「If a human engineer can't definitively say which tool should be used in a given situation, an AI agent can't be expected to do better.」最反直觉的是**标识符可读性影响正确率**——没有任何 API 设计传统会认为把 UUID 换成人话能降低幻觉。

**反例 / 张力**
- 「给 examples」这条建议在 8 个月内自我推翻：2025-11 发布 Tool Use Examples 并宣称「improved accuracy from 72% to 90% on complex parameter handling」（`01-engineering/2025-11-24_advanced-tool-use_fe2899cf9c24.md`），2026-07 则说「With our newest models, we've found that giving examples actually constrains them to a certain exploration space.」（`01-engineering/2026-07-24_new-rules-of-context-engineering_thariq.md`）
- think tool 同样：2025-03 报 airline 域 54% 相对提升，同一文件顶部 2025-12 挂上官方注记「we recommend using that feature [extended thinking] instead of a dedicated think tool in most cases」 — `01-engineering/2025-03-20_claude-think-tool_962c879d367c.md`
- AskUserQuestion 的三次尝试记录（改 ExitPlanTool → 改输出格式 → 独立工具）承认最终判据是**模型爱不爱用**：「even the best designed tool doesn't work if Claude doesn't understand how to call it」，这是一条无法从第一性原理推出的经验判据。

---

### A4. 验证回路是自主性的单位；验证者不能是作者

**内核**：agent 能无人值守跑多久，等于"它能自己跑的检查"能覆盖多远。没有可运行的检查，"看起来做完了"就是唯一信号，人就变成了验证回路本身。而当检查本身需要判断（设计好不好、QA 过不过），必须换一个**独立 context 的 agent** 来判——不是因为提示词不够狠，是因为模型对自己的产出有结构性偏好。关键的二阶洞察：**把 generator 调成自我批判很难，把独立 evaluator 调成怀疑很容易**，所以要把难题换成易题。

**证据**
- 「Claude stops when the work looks done. Without a check it can run, "looks done" is the only signal available, and you become the verification loop」 — `01-engineering/2025-04-18_claude-code-best-practices_4d249e2a9df8.md`
- 「When asked to evaluate work they've produced, agents tend to respond by confidently praising the work—even when, to a human observer, the quality is obviously mediocre.」 — `01-engineering/2026-03-24_harness-design-long-running-apps_2ef732b76415.md`
- 核心不对称：「tuning a standalone evaluator to be skeptical turns out to be far more tractable than making a generator critical of its own work, and once that external feedback exists, the generator has something concrete to iterate against.」 — 同上
- 「Out of the box, Claude is a poor QA agent. In early runs, I watched it identify legitimate issues, then talk itself into deciding they weren't a big deal and approve the work anyway.」 — 同上
- 命名：「**Self-preferential bias** refers to Claude's tendency to prefer its own results or findings, especially when asked to verify or judge them against a rubric.」 — `01-engineering/2026-06-02_dynamic-workflows_thariq.md`
- 极端形式（让判定者对作者的说辞盲）：「We strip assistant text so the agent can't talk the classifier into making a bad call... we want it to judge what the agent did, not what the agent said.」 — `01-engineering/2026-03-25_claude-code-auto-mode_b4c065a13b0c.md`
- 把主观变可打分：「"Is this design beautiful?" is hard to answer consistently, but "does this follow our principles for good design?" gives Claude something concrete to grade against.」 — `harness-design-long-running-apps`
- 无人值守场景的验证优先级：「it's important that the task verifier is nearly perfect, otherwise Claude will solve the wrong problem.」 — `01-engineering/2026-02-05_building-c-compiler_c62e49f23206.md`

**预测力测试**
> 问：能不能让同一个 agent 写完 PR 后接一句"现在严格 review 你自己的代码"？

推断立场：不能，这正是 self-preferential bias 的触发姿势。要么开新 context 的 subagent 只看 diff 和判据，要么走 dynamic workflow 的 adversarial verification。更强的变体（auto mode）会把作者自己的说明文字从 reviewer 输入里剥掉。另一个可推断结论：**rubric 要有硬阈值**（「Each criterion had a hard threshold, and if any one fell below it, the sprint failed」），而不是加权总分——因为加权会让评审自己把不合格项谈过去。

**排他性**：业界的主流解法是 self-reflection / chain-of-verification / "critique yourself" 这类**同上下文内**的提示技巧。Anthropic 的立场是这类做法在结构上无效，修复必须是架构性的（分离 context）＋ 非对称调优（只调怀疑方）。而 auto mode 让判定者**故意看不见 agent 的推理**，与"给 reviewer 尽可能多的上下文"的直觉完全相反。

**反例 / 张力**
- 怀疑是有成本的：「A reviewer prompted to find gaps will usually report some, even when the work is sound, because that is what it was asked to do. Chasing every finding leads to over-engineering: extra abstraction layers, defensive code, and tests for cases that can't happen.」 — `claude-code-best-practices`
- 分离本身会被模型进步吞掉：Opus 4.6 之后「Tasks that used to need the evaluator's check to be implemented coherently were now often within what the generator handled well on its own, and for tasks within that boundary, the evaluator became unnecessary overhead.」 — `harness-design-long-running-apps`
- 验证回路也会被绕过：`01-engineering/2026-03-06_eval-awareness-browsecomp_842accc1173b.md` 里模型不是"骗过验证"，而是**去解密验证本身的答案密钥**。

---

### A5. 环境层先于模型层：先封死爆炸半径，再调行为

**内核**：模型层的手段（system prompt、classifier、probe、训练）只能改变 agent **倾向于**做什么；环境层（sandbox、VM、egress control、凭证不入沙箱）决定它**能够**做什么。因为任何概率性防御的漏检率非零，所以确定性边界是"其他一切失手时挨打的那一层"。第二条原则同样反直觉：**隔离强度要匹配用户的监督能力**，而不是匹配风险等级——开发者能读懂 bash，知识工作者读不懂，所以同样的风险要用不同架构。第三条：自己写的那层最脆。

**证据**
- 「Design for containment at the environment layer first, then steer behavior at the model layer... **The deterministic boundary is what gets hit when everything probabilistic misses.**」 — `01-engineering/2026-05-25_how-we-contain-claude_97cd97d27d22.md`
- 「if credentials never enter the sandbox, they can't be exfiltrated, regardless of whether the cause is a user, a model finding a "creative" path, or an attacker.」 — 同上
- 人在回路的失效数据：「Our telemetry showed users approved roughly 93% of permission prompts. The more approvals a user sees, the less attention they pay to each」 — 同上；`01-engineering/2025-10-20_claude-code-sandboxing_5a3989c21b00.md` 给出对照数字「sandboxing safely reduces permission prompts by 84%」
- 「**Match isolation strength to the user's capacity for oversight.** A developer who can read bash and a knowledge worker who can't are not running the same threat model.」 — `how-we-contain-claude`
- 「**Be wary of custom components.** Battle-tested hypervisors, syscall filters, and container runtimes have survived more adversarial attention than anything you'll build. Across every deployment described here, the standard primitives held while our own work around them exposed flaws.」 — 同上
- 结构性修复优于范围收窄：「Narrow scoping is an obvious mitigation, but this encodes an assumption about what Claude can't do with a limited token—and Claude is getting increasingly smart. The structural fix was to make sure the tokens are never reachable from the sandbox」 — `01-engineering/2026-04-08_managed-agents_f90fa6cabc29.md`

**预测力测试**
> 问：我们的运营 agent 需要连生产库，加一段"绝对不要 DELETE"的强系统提示词够不够？

推断立场：不够，直接给只读凭证。更细的推断来自他们的 allowlist 事故：**白名单不是目的地过滤器，是能力授予**（「Every function reachable through any domain on an allowlist is now an attack surface. Allowing api.anthropic.com meant allowing file uploads to arbitrary Anthropic accounts.」）。所以"该放行哪些域名"这个问题本身就问错了，应该问"通过这个域名能到达的每一个功能是什么"。

**排他性**：业界默认是护栏提示词 + 一层内容审核模型，并把"人工审批"当成安全性的证明。Anthropic 把这两条都量化否定了：审批率 93%、auto mode 分类器在真实过度行为上漏检 17%、Gray Swan 上 100 次自适应攻击后成功率仍有 5–6%。另一条几乎没人会主动写的是：**隔离会顺带把可观测性也挡在外面**（「the same isolation keeping Claude contained also kept host-based endpoint detection and response out」）。

**反例 / 张力**
- 他们所有被公开的容器化事故都出在**自己写的那层**：信任对话框之前就解析 `.claude/settings.json`；自建 egress 代理放行了攻击者的 API key。标准原语没破。这既证实又讽刺了"be wary of custom components"。
- 直接注入（钓鱼用户去粘贴恶意 prompt）里模型层结构性失效：「Across 25 retries of that prompt, Claude completed the exfiltration 24 times.」
- 最大张力：bcherny 2026-08 公开主张「We have largely solved the threat of prompt injection in practice when using Claude models.」（`08-x/2026-08-09_bcherny_2086520950259118464.md`），而同司 2026-05 的 `how-we-contain-claude` 写「protection in the model layer will never be 100% effective, which is why it can't stand alone.」两条同时挂在官网上。

---

### A6. 瓶颈是"未知"，不是模型能力

**内核**：把任务拆成四类信息——已知的已知（写进 prompt 的）、已知的未知（知道自己没想清的）、**未知的已知**（太显然以至于没写下来、但看到结果会说"不是这样"的标准）、未知的未知。长任务做错，默认归因不是模型不行，而是地图与领土的差距。因此工程动作前移到一系列命名仪式：blind spot pass、brainstorm 出多个可反应的原型、一次一问的 interview（且优先问会改变架构的问题）、用**源码**当引用、implementation notes 记录偏离、合并前先过 quiz。

**证据**
- 「**Claude Fable is the first model where I find the quality of the work is bottlenecked by my ability to clarify its unknowns.**」 — `01-engineering/2026-07-06_finding-your-unknowns_thariq.md`
- 「If you are too specific, Claude will follow your instructions even when a pivot may be more appropriate. If you are too vague, Claude will often make choices and assumptions based on industry best practices that may not be a fit for your task.」 — 同上
- 「When a long-horizon task comes back wrong, it's likely you need to spend more time defining your unknowns or creating an implementation plan that allows for you and Claude to adapt through them.」 — 同上
- 引用保真度阶梯：「the absolute best reference is source code... This provides Claude much richer detail around the markup and structure, compared to for example a screenshot.」 — 同上；「a HTML mockup of a design will generally produce better results than a description of the design or a screenshot.」 — `new-rules-of-context-engineering`
- 成本论证：「Every explainer, brainstorm, interview, prototype, and reference is a cheap way to find out what you didn't know before it gets expensive to fix.」 — `finding-your-unknowns`
- 独立来源的同型主张：「Time spent making the spec precise pays off more than time spent watching the implementation.」 — `claude-code-best-practices`

**预测力测试**
> 问：一个 4 小时的长任务跑出来方向错了，是不是该换更强的模型 / 多开几个 agent？

推断立场：都不是。先做 blind spot pass 和 interview，把"未知的已知"逼出来。他们会补一条外人不会说的：**在原型阶段发现比在实现阶段发现便宜得多**，因为「Small changes in a feature or spec can cause drastically different implementations in code, and it can be more difficult for your agent to revert previous changes.」——即 agent 时代的返工成本结构和人写代码不同，规格微调会引发实现大改。

**排他性**：业界把这类问题归到"prompt engineering"，解法是改提示词。这里把归因整个翻转到**使用者未言明的标准**上，并且"unknown knowns"不是标准工程词汇。另一条排他判据是引用的保真度排序：源码 > HTML mock > 截图 > 文字描述——绝大多数团队会觉得截图是最直观的规格，他们认为它是最差的。

**反例 / 张力**
- 同一季度 Boris Cherny 给的是相反方向的建议：「Opus 4.7 is intelligent enough that it no longer needs Plan Mode for most tasks. I often just jump in, and Claude will ask me questions if it needs to」（`08-x/2026-05-24_bcherny_2058519809214607704.md`）、「Doesn't needs super specific instructions with modern models.」（`08-x/2026-08-13_bcherny_2088014489438621990.md`）。两位 Claude Code 团队成员在同代模型上对"前置多少规格"给出对立答案，这个分歧在语料里没有被调和。
- `harness-design-long-running-apps` 又反向说明前置规格必要：删掉 planner 后 generator 会 under-scope。所以真正的立场可能是"前置规格必要，但形式应该是引用和原型，而不是更长的文字指令"。

---

### A7. 缓存前缀是架构约束，不是性能优化项

**内核**：prompt cache 是**前缀匹配**，所以前缀里任何一个字节变化都会作废其后的全部缓存。一旦把它当约束而不是优化，功能设计的直觉会被整个反过来：不再"只给模型当前需要的工具"，而是工具集永远不变；状态切换（进入 plan mode）建模成**工具调用**而不是改 system prompt 或改工具集；副操作（压缩、总结）必须复用父请求的完整前缀。这是他们唯一一个把可观测性指标提到事故级别的工程约束。

**证据**
- 「we run alerts on our prompt cache hit rate and **declare SEVs if they're too low**.」 — `01-engineering/2026-04-30_prompt-caching-is-everything_thariq.md`
- 反直觉的 plan mode 设计：「The intuitive approach would be: when the user enters plan mode, swap out the tool set to only include read-only tools, but that would break the cache. Instead, we keep all tools in the request at all times and use EnterPlanMode and ExitPlanMode as tools themselves.」 — 同上
- 「if you're 100k tokens into a conversation with Opus and want to ask a question that is fairly easy to answer, it would actually be more expensive to switch to Haiku than to have Opus answer, because we would need to rebuild the prompt cache for Haiku.」 — 同上
- 自曝的踩坑清单：「We've broken this ordering before for a variety of reasons, including: putting an in-depth timestamp in the static system prompt, shuffling tool order definitions non-deterministically, and updating parameters of tools」 — 同上
- 「Prompt caching only applies when a request's prefix matches what's already cached, byte for byte, from the start... You end up paying the full, uncached input rate for the entire conversation you're sending in — and the longer the conversation (i.e., the more you need compaction in the first place), the more expensive that one call becomes.」 — 同上
- 呼应设计：「Tool Search Tool doesn't break prompt caching because deferred tools are excluded from the initial prompt entirely.」 — `01-engineering/2025-11-24_advanced-tool-use_fe2899cf9c24.md`；auto mode 的两阶段分类器同理：「Because the input is identical other than the final instruction, stage 2's prompt is almost entirely cache-hit from stage 1.」 — `01-engineering/2026-03-25_claude-code-auto-mode_b4c065a13b0c.md`

**预测力测试**
> 问：为了省 context，我们打算按会话阶段动态增删 MCP 工具，只挂当前用得上的。

推断立场：这是他们点名的最常见破缓存方式，方向是反的。正确做法是 `defer_loading` —— 把轻量 stub 永远留在前缀里，让模型通过 tool search 去"发现"完整定义。同理可推断：**更新信息要走 message，不要改 system prompt**（时间、文件变更都用下一轮的 tool result 标签带进去）。

**排他性**：这条同时反转两个非常普遍的工程直觉——动态工具集（"只给需要的"）和成本路由（"简单问题走便宜模型"）。而"把缓存命中率当 uptime 监控、掉了就开事故"是几乎没有团队会做的运营承诺。

**反例 / 张力**
- 这是全篇最绑定他们自身经济结构的一条：缓存命中率直接换算成订阅制的 rate limit 宽松度。按 token 付费的小团队，维持前缀纪律的工程成本可能超过节省。
- 他们自己也承认这层不该由用户扛：「based on our learnings from Claude Code we built compaction directly into the API」——最终动作是把约束吸收进平台。
- `april-23-postmortem` 里那个 bug 恰恰是**为了缓存优化**引入的：清理旧 thinking 本意是降低冷启动成本，实现错误导致每轮都清，「those requests also resulted in cache misses」——为省缓存的改动反而毁了缓存并毁了智能。

---

### A8. 分数是待证伪的假设，不是测量值

**内核**：任何 eval 数字首先是关于**你的 eval** 的断言，其次才是关于模型的。分数动了，默认怀疑顺序是：任务写坏了 → grader 太死 → 基础设施变了 → 模型真的变了。所以他们有一条硬规矩：没人读过 transcript 之前，不采信分数。配套的具体判据也都是反直觉的：0% 通过率是任务坏了的信号；只测正例的 eval 会产生单向优化；3 个百分点以内的榜单差距在缺配置说明时应视为噪音。

**证据**
- 「**As a rule, we do not take eval scores at face value until someone digs into the details of the eval and reads some transcripts.**」 — `01-engineering/2026-01-09_demystifying-evals-for-ai-agents_414ce4b52e36.md`
- 「With frontier models, a 0% pass rate across many trials (i.e. 0% pass@100) is most often a signal of a broken task, not an incapable agent」 — 同上
- 实例：「Opus 4.5 initially scored 42% on CORE-Bench, until an Anthropic researcher found multiple issues: rigid grading that penalized "96.12" when expecting "96.124991…"... Opus 4.5's score jumped to 95%.」 — 同上
- 单向 eval：「**One-sided evals create one-sided optimization.** For instance, if you only test whether the agent searches when it should, you might end up with an agent that searches for almost everything.」 — 同上
- 基础设施即混淆变量：「the gap between the most- and least-resourced setups on Terminal-Bench 2.0 was 6 percentage points (p < 0.01)」；「**A few-point lead might signal a real capability gap—or it might just be a bigger VM.**」 — `01-engineering/2026-02-05_infrastructure-noise_9e0139d87dd1.md`
- 「our data suggests that leaderboard differences below 3 percentage points deserve skepticism until the eval configuration is documented and matched」 — 同上
- 「resource configuration for agentic evals should be treated as a first-class experimental variable, documented and controlled with the same rigor as prompt format or sampling temperature」 — 同上
- 极端失效：模型自己识别出在跑哪个 benchmark 并解密答案密钥 —— 「it wrote and executed its own `derive_key()` and `decrypt()` functions using SHA256 and XOR, matching the scheme from the eval code」 — `01-engineering/2026-03-06_eval-awareness-browsecomp_842accc1173b.md`
- 「we encourage the research community to treat eval integrity as an **ongoing adversarial problem** rather than a design-time concern.」 — 同上

**预测力测试**
> 问：我们的 agent 在新 eval 套件上只有 12% 通过率，是不是该换模型或大改 prompt？

推断立场：先查任务规格。他们会问：两个领域专家独立判会不会得到同一个 pass/fail？有没有 reference solution 证明这题可解、grader 配置正确？环境是不是每次 trial 都干净（他们自己踩过：「we observed Claude gaining an unfair advantage on some tasks by examining the git history from previous trials」）？以及资源上限是不是把 agent 在装依赖阶段就 OOM 掉了。只有这些都排除后，12% 才是关于模型的信息。

**排他性**：资深工程师会说"测试会 flaky"，但不会说"3 个百分点以内的榜单差距应视为噪音"、"0% 通过率意味着题目坏了"、"agent 会去解密答案密钥"。更排他的是他们把**评分方向**也当成设计变量：「it's often better to grade what the agent produced, not the path it took」，因为 agent 会找到设计者没想到的合法路径（τ²-bench 里模型钻政策漏洞订到更好的票，按 eval 算失败，对用户其实更好）。

**反例 / 张力**
- 他们自己违反过：`april-23-postmortem` 里那条限制字数的系统提示词，「After multiple weeks of internal testing and no regressions in the set of evaluations we ran, we felt confident about the change and shipped it」，事后用更宽的 eval 集做 ablation 才发现掉 3%。通过的 eval 被当成了证据。
- `a-postmortem-of-three-recent-issues` 说得更直白：「**More fundamentally, we relied too heavily on noisy evaluations.**」以及「The evaluations we ran simply didn't capture the degradation users were reporting, in part because Claude often recovers well from isolated mistakes.」——模型的自我纠错能力会掩盖底层缺陷，这是 eval 的结构性盲区。
- 他们对外发的 benchmark 数字（Tool Search 79.5%→88.1%、PTC 43,588→27,297 token、Tool Use Examples 72%→90%）全部出自 internal testing，没有配置说明——正好违反自己在 `infrastructure-noise` 里提出的披露标准。

---

## B. 范式变迁表

| 技术主题 | 早期做法（时间 · 出处） | 现在做法（时间 · 出处） | 变化原因 | 现在还成立吗 |
|---|---|---|---|---|
| 工具用法示范 | 给 examples 是头号规则；Tool Use Examples 报 72%→90%（2025-11 · `advanced-tool-use`） | 删掉 examples，改设计接口本身（参数命名、enum 表达意图）（2026-07 · `new-rules-of-context-engineering`） | 「giving examples actually constrains them to a certain exploration space」 | **分代际**。Claude 5 代删；老模型 + 深嵌套 schema + 领域特有约定仍适用 |
| 系统提示词体量 | 全量前置，含 code review / verification 细则；硬规则防最坏情况（2025-04 · `claude-code-best-practices`；2025-09 · `effective-context-engineering`） | 删掉 80%+，改成「Write code that reads like the surrounding code」这类判断性指引（2026-07 · `new-rules`） | 「we were overconstraining Claude Code」；转录里能看到 system prompt / skill / user 三方指令互相打架 | 成立，但**前提是你有 eval 能证明 "no measurable loss"** |
| 硬规则 vs 判断 | 「default to writing no comments. Never write multi-paragraph docstrings」（2026 前 CC system prompt） | 「Write code that reads like the surrounding code: match its comment density, naming, and idiom.」 | 「without these guardrails for older models, the comments Claude wrote would be incorrect in many cases and we had to accept this tradeoff」 | 成立于 Claude 5 代 |
| 代码库检索 | RAG + 向量预索引（Claude Code 内部早期 · 追述于 `seeing-like-an-agent`） | Grep/Glob + 渐进披露 + 文件系统（2026-04 · 同上；2025-09 · `trq212` 线程） | 「Claude was given this context instead of finding the context itself」；索引会腐坏、跨环境脆弱 | 成立。但保留混合：CLAUDE.md 仍朴素前置 |
| 任务追踪 | TodoWrite + 每 5 轮插 system reminder（2025 · `seeing-like-an-agent` 追述） | Task 工具（带依赖、跨 subagent 共享、可增删改）（2026-04 · 同上） | 「Being sent reminders of the todo list made Claude think that it had to stick to the list instead of modifying it when it realized it needed to change course」 | 成立 |
| 长任务跨窗口 | context reset + 结构化交接（因 Sonnet 4.5 的 context anxiety）（2025-11 · `effective-harnesses-for-long-running-agents`） | 单会话连续跑 + 自动 compaction（Opus 4.5 起）（2026-03 · `harness-design`） | 「Opus 4.5 largely removed that behavior on its own, so I was able to drop context resets from this harness entirely」 | 分代际。用 4.5 之前的模型仍需要 |
| 长任务分解 | sprint 构造 + 一次一个 feature + 每 sprint 评审（2026-03 上半 · `harness-design`） | 去掉 sprint，evaluator 移到最后单次（Opus 4.6）（2026-03 下半 · 同上） | 4.6「plans more carefully, sustains agentic tasks for longer」，能自己维持一致性 2 小时以上 | 分代际。语料显示 4.5 需要，4.6 不需要 |
| 中间推理 | think 工具（专门的思考 tool），airline 域 +54% 相对（2025-03 · `claude-think-tool`） | extended thinking（2025-12 官方注记覆盖原文） | 「Extended thinking provides similar benefits—giving Claude space to reason through complex problems—with better integration and performance.」 | **已废**。原文仍在线但顶部有废弃声明 |
| 规格载体 | Markdown 计划文件 + 代码库里的 spec（2025 · `effective-context-engineering`） | 富引用：HTML artifact、测试套件、别的代码库里的函数、rubric（2026-07 · `new-rules`；2026-05 · `unreasonable-effectiveness-of-html`） | 「Claude can handle increasingly more complicated references」；且人类实际不读超过 100 行的 Markdown | 成立但**部分是个人偏好**，Thariq 自述 HTML maximalist |
| 记忆 | 用 `#` 热键手写进 CLAUDE.md（2025-04 · `claude-code-best-practices`） | auto-memory，模型自动保存（2026-07 · `new-rules`） | 「Claude now automatically saves memories that are relevant to the work and to you」 | 成立于有 memory 功能的 harness |
| 权限模型 | 逐条人工审批（2025-04 起） → OS sandbox（2025-10 · `claude-code-sandboxing`） → auto mode 分类器（2026-03 · `claude-code-auto-mode`），2026-08 成为默认（`08-x/2026-08-07_bcherny`） | 同左 | 审批疲劳：93% 批准率；sandbox 减少 84% 提示；分类器把 FPR 压到 0.4% | 成立。但 auto mode 明说不替代高风险基建上的人工审查 |
| Plan mode | 四阶段工作流的核心环节（2025-04 · `claude-code-best-practices`） | 「I don't use plan mode much anymore」「Opus 4.7 is intelligent enough that it no longer needs Plan Mode for most tasks」（2026-05 · `08-x/bcherny`） | 模型会自己在需要时提问 | **有争议**。同期 Thariq 仍主张前置探索与原型；文档仍保留 plan mode 章节 |
| 多 agent 适用面 | 「most coding tasks involve fewer truly parallelizable tasks than research, and LLM agents are not yet great at coordinating and delegating to other agents in real time」（2025-06 · `multi-agent-research-system`） | 16 个并行 agent 写 C 编译器（2026-02 · `building-c-compiler`）；模型自己写多 agent harness（2026-06 · `dynamic-workflows`） | 模型协调能力跨过阈值；worktree 隔离 + git 锁解决了写冲突 | 成立，但成本判据没变：15× token，要求任务价值足够高 |
| workflow 编排 | 静态：Agent SDK / `claude -p` 手写编排（2025） | 动态：模型现场写 JS harness（2026-06 · `dynamic-workflows`） | 「because static workflows need to work for all edge cases, they are usually more generic」 | 成立，但他们自己限定「best suited for complex, high value tasks」 |
| 框架态度 | 「start by using LLM APIs directly」「don't hesitate to reduce abstraction layers」（2024-12 · `building-effective-agents`） | 该文顶部现挂官方注记：「Much of the tooling landscape described in this post has changed since December 2024. For our current approach, see how we built Claude Managed Agents」 | 他们自己造了托管抽象层 | **需要注意的自我修订**，原则（简单优先）保留，具体建议（别用框架）已被自家产品覆盖 |

---

## C. 决策启发式

**H1** 当工具定义占用 > 10K token，或工具数 > 10 且存在选错工具的问题时 → 开 Tool Search Tool + `defer_loading: true`，**保留 3–5 个最高频工具常驻**，其余下沉。不要在会话中途删工具，因为工具在缓存前缀里，删除会作废整段会话的缓存；stub 不会。
> 「Use it when: Tool definitions consuming >10K tokens... 10+ tools available」 — `advanced-tool-use`；「Instead of removing tools, we send lightweight stubs」 — `prompt-caching-is-everything`

**H2** 当会话已经积累大量 context、而下一步是个简单问题时 → **不要切换到便宜模型**，要么让当前模型答，要么派 subagent 并让当前模型写一段 hand-off。
> 「it would actually be more expensive to switch to Haiku than to have Opus answer, because we would need to rebuild the prompt cache for Haiku... the best way to do it is with subagents」 — `prompt-caching-is-everything`

**H3** 当下一步会产生大量中间产物、而你只要结论时 → 派 subagent。判据用他们的原话当口诀：
> 「The mental test we use at Anthropic: **will I need this tool output again, or just the conclusion?**」 — `01-engineering/2026-04-15_session-management-and-1m-context_thariq.md`

**H4** 当同一个问题纠正 agent 超过两次 → `/clear` 重开并写更好的初始 prompt，不要继续纠正。
> 「If you've corrected Claude more than twice on the same issue in one session, the context is cluttered with failed approaches... A clean session with a better prompt almost always outperforms a long session with accumulated corrections.」 — `claude-code-best-practices`
> 更细的变体：agent 走错路但前面的文件读取仍有用时，用 rewind 而不是追加纠正——「rewind to just after the file reads, and re-prompt with what you learned」 — `session-management-and-1m-context`

**H5** 当要往 CLAUDE.md 加一条规则时 → 先问「删掉它 Claude 会不会犯错」，不会就砍；能变成确定性机制的（hook / lint / CI / routine）优先变成机制，因为 CLAUDE.md 是建议性的、hook 是确定的。
> 「For each line, ask: "Would removing this cause Claude to make mistakes?" If not, cut it. **Bloated CLAUDE.md files cause Claude to ignore your actual instructions!**」 — `claude-code-best-practices`
> 「If Claude instead writes a lint rule, CI step, or routine, that class of issue can be fully automated forever.」 — `08-x/2026-07-15_bcherny_2077460395279692197.md`

**H6** 当 agent 要跨多个 context window 完成一个项目时 → 用**两种 prompt**：第一个会话是 initializer（写 feature list、`init.sh`、progress 文件、首个 git commit），后续会话统一是 coding agent（读 progress + git log → 跑一次端到端冒烟 → 只做一个 feature → 提交并写进度）。feature list 用 **JSON 不用 Markdown**。
> 「we landed on using JSON for this, as the model is less likely to inappropriately change or overwrite JSON files compared to Markdown files.」 — `effective-harnesses-for-long-running-agents`

**H7** 当任务的"好"是主观的（设计、命名、研究质量）时 → 拆 generator / evaluator 两个 context，写 4 条左右带**硬阈值**的判据，用 few-shot 例子校准 evaluator，只调 evaluator 的怀疑度。给 evaluator 真实交互能力（Playwright 点真实页面），不要让它给静态截图打分。
> 「I calibrated the evaluator using few-shot examples with detailed score breakdowns.」「Because the evaluator was actively navigating the page rather than scoring a static screenshot, each cycle took real wall-clock time.」 — `harness-design-long-running-apps`

**H8** 当 eval 出现 0% pass@100 时 → 查任务规格和 grader，不查模型。任务质量判据：两个领域专家独立判会不会给出同一个 pass/fail；有没有一个能过全部 grader 的 reference solution。
> 「A good task is one where two domain experts would independently reach the same pass/fail verdict.」「For each task, it's useful to create a reference solution: a known working output that passes all graders.」 — `demystifying-evals-for-ai-agents`

**H9** 当比较榜单分数时 → 差距 < 3 个百分点且未公布资源配置 = 噪音。跑 agentic eval 时，容器资源要**分别指定保证配额和硬上限**（不要设成同一个值），band 宽度校准到"下界和上界的分数落在彼此噪音内"。
> 「we recommend that evals specify both parameters per task, not a single pinned value. A single exact spec sets the guaranteed allocation equal to the kill threshold, leaving zero margin」 — `infrastructure-noise`

**H10** 当用户群体读不懂 agent 要执行的命令时（非技术用户）→ 用绝对的、常开的边界（VM + mount 模式），不要用逐条审批。审批只有在用户具备判断力时才构成防御。
> 「a non-technical knowledge worker shouldn't be expected to judge bash incantations such as `find . -name "*.tmp" -exec rm {} \;`. When approving an exception requires expertise the typical user doesn't have, admins should set a boundary that is absolute and always-on.」 — `how-we-contain-claude`

**H11** 当你说不清"什么算好"时 → 给源码引用（哪怕是别的语言），其次 HTML mock，最后才是截图或文字描述。rubric 也算一种引用。
> 「If you have a library that implements something in a certain way or a design component you really like, just point Fable at the folder and tell it what to look for, even if it's in a different language.」 — `finding-your-unknowns`

**H12** 当写 skill 时 → `description` 字段写**触发条件**不写功能摘要；正文只写 Claude 默认不会做对的事（gotchas 是最高信号段）；长了就拆多文件渐进披露；需要用户配置的存 `config.json`，没配就用 AskUserQuestion 问。
> 「the description field is not a summary, it's a description of when to trigger this skill.」「Claude already knows how to code and can read your codebase. A skill that restates what Claude would do by default adds context without adding value.」 — `01-engineering/2026-06-03_how-we-use-skills_thariq.md`
> 投入判据：「Verification skills have had the most measurable impact on Claude's output quality internally. It can be worth having an engineer spend a week just making your verification skills excellent.」 — 同上

---

## D. 反模式

**D1 · 把已有 API endpoint 一对一包成工具。**
> 「A common error we've observed is tools that merely wrap existing software functionality or API endpoints—whether or not the tools are appropriate for agents. This is because agents have distinct "affordances" to traditional software」 — `writing-tools-for-agents`

**D2 · 往 prompt 里堆边缘案例清单。**
> 「teams will often stuff a laundry list of edge cases into a prompt in an attempt to articulate every possible rule the LLM should follow for a particular task. **We do not recommend this.**」 — `effective-context-engineering`

**D3 · 检查 agent 有没有按指定顺序调工具。**
> 「There is a common instinct to check that agents followed very specific steps like a sequence of tool calls in the right order. We've found this approach too rigid and results in overly brittle tests, as agents regularly find valid approaches that eval designers didn't anticipate. So as not to unnecessarily punish creativity, **it's often better to grade what the agent produced, not the path it took.**」 — `demystifying-evals-for-ai-agents`

**D4 · 单向 eval（只测该触发时触发了）。**
> 「**One-sided evals create one-sided optimization.**」「Try to avoid class-imbalanced evals.」 — 同上。他们自己在 Claude.ai 网页搜索上踩过：需要同时构造"该搜"和"不该搜（如 who founded Apple）"两侧。

**D5 · 会话中途增删工具 / 改 system prompt。**
> 「Changing the tool set in the middle of a conversation is one of the most common ways people break prompt caching. It seems intuitive—you should only give the model tools you think it needs right now.」 — `prompt-caching-is-everything`

**D6 · 把逐条人工审批当成安全防线。**
> 「Ironically, this meant that a feature originally designed to provide oversight could arguably have the opposite effect—some users might simply stop paying attention.」 — `how-we-contain-claude`

**D7 · 让 reviewer 无限制找问题、然后照单全改。**
> 「A reviewer prompted to find gaps will usually report some, even when the work is sound... Tell the reviewer to flag only gaps that affect correctness or the stated requirements, and treat the rest as optional.」 — `claude-code-best-practices`

**D8 · 用框架抽象层遮住 prompt 和 response。**
> 「they often create extra layers of abstraction that can obscure the underlying prompts and responses, making them harder to debug. They can also make it tempting to add complexity when a simpler setup would suffice... **Incorrect assumptions about what's under the hood are a common source of customer error.**」 — `building-effective-agents`

**D9 · 未加范围限定就让 agent "调研一下"。**
> 「**The infinite exploration.** You ask Claude to "investigate" something without scoping it. Claude reads hundreds of files, filling the context.」 — `claude-code-best-practices`

---

## E. 表达 DNA

**E1 · 难看的数字直接放在最显眼处，并主动定义它为"诚实的那个数"。** 不用"仍有提升空间"这类缓冲语。
> 「The 17% false-negative rate on real overeager actions is **the honest number**. The agent was trying to solve the user's problem and tried to execute a dangerous command past what was authorized.」 — `claude-code-auto-mode`

**E2 · 主动给出反对自己产品的条件，并指名哪类用户不该用。**
> 「Whether 17% is acceptable depends on what you're comparing against. If you are running `--dangerously-skip-permissions`, this is a substantial improvement. If you are manually approving every action carefully, it's arguably a regression—you're trading your own judgment for a classifier that will sometimes make a mistake.」 — `claude-code-auto-mode`

**E3 · 不确定就说"这是手艺不是科学"，不硬套框架；对"不知道为什么 work"直接标注。**
> 「Designing the tools for your models is as much an art as it is a science... Our best advice? Experiment often, read your outputs, try new things.」 — `seeing-like-an-agent`
> 「The wording of the criteria steered the generator in ways I didn't fully anticipate. Including phrases like "the best designs are museum quality" pushed designs toward a particular visual convergence」 — `harness-design-long-running-apps`

**E4 · 承认这篇文章本身会造成它所描述的问题。**
> 「New contamination sources appear continuously, driven by the research community's practice of using benchmark questions as worked examples in papers. **This report will, itself, likely contribute to the problem.**」 — `eval-awareness-browsecomp`

**E5 · 允许情绪出现在技术文里，且是负面情绪。**
> 「So, while this experiment excites me, it also leaves me feeling uneasy. Building this compiler has been some of the most fun I've had recently, but I did not expect this to be anywhere near possible so early in 2026.」 — `building-c-compiler`

**结构模板**：几乎所有工程文都是「我们先做了 X → X 在什么具体场景下失败（带机制）→ 换成 Y → Y 还剩什么没解决」。失败尝试保留编号（`seeing-like-an-agent` 的 Attempt 1/2/3；`AI-resistant-technical-evaluations` 的 Attempt 1/2），不折叠成"经过迭代我们最终选择了"。数字带统计量（`p < 0.01`、`n = 10,000`、`Welch's t-test: t(38.89) = 6.71, p < .001, d = 1.47`）。过期内容用文首注记而不是删改（`building-effective-agents` 和 `claude-think-tool` 都保留原文 + 顶部废弃声明）。

---

## F. 诚实边界

### F1 · 绑定他们自身规模与基建，小团队照抄会翻车

- **缓存前缀纪律（A7）**：他们既是模型提供方又是订阅制卖方，缓存命中率直接换算成 rate limit 宽松度，所以值得开 SEV。按 token 付费的小团队维持字节级前缀纪律的工程成本可能超过节省。而且他们自己的终局动作是把 compaction 和 tool search 做进 API——即"用户本来就不该手写这些"。
- **eval 基础设施**：他们明确写了这条建议外部做不到：「A model provider can shield its eval infrastructure from this by dedicating hardware, but external evaluators can't easily do the same.」（`infrastructure-noise`）
- **"删掉 80% 系统提示词"**：成立的前提是他们有 coding eval 套件能证明 "no measurable loss"。没有 eval 的团队照删就是盲删。而且他们自己的 `april-23-postmortem` 证明，即使有 eval 也可能太窄——一条限制字数的指令跑过"多周内部测试无回归"后才被更宽的 ablation 抓出 3% 智能下降。
- **成本量级不是生产建议**：C 编译器 2000 次会话 / 20 亿输入 token / $20,000（作者自己说「an extremely expensive project」）；DAW harness 单次 3 小时 50 分 / $124.70；游戏编辑器 harness 6 小时 / $200（对照单 agent 20 分钟 / $9，贵 20 倍）。这些是**能力探测实验**，`building-c-compiler` 更是明确定位为 capability benchmark。
- **multi-agent 的 15× token**：他们自己给了准入条件「multi-agent systems require tasks where the value of the task is high enough to pay for the increased performance」。
- **招聘 take-home 的方法论**（`AI-resistant-technical-evaluations`）依赖能拿到未发布模型来预先打败自家面试题。外部公司没有这个能力，所以"用下一代模型 stress test 你的评估"这条建议对外不可执行。
- **dogfooding 假设**：`april-23-postmortem` 的改进措施是「we'll ensure that a larger share of internal staff use the exact public build」——前提是你有几百个每天用自家产品的工程师。

### F2 · 产品营销驱动的表达

- `advanced-tool-use`、`managed-agents`、`equipping-agents-for-the-real-world-with-agent-skills`、`desktop-extensions` 本质是发布稿。其中的性能数字（Tool Search 79.5%→88.1%、PTC 平均 43,588→27,297 token、Tool Use Examples 72%→90%）全部标注为 internal testing，无配置说明、无独立复现——恰好违反他们自己在 `infrastructure-noise` 里提出的披露标准。
- `building-effective-agents` 顶部的注记把读者导向 Managed Agents，同时该文正文主张"少用框架、直接调 API"。原则和商业动线在同一页上冲突。
- `harness-design-long-running-apps` 的成果展示（DAW、游戏编辑器）是作者自己肉眼评价的，没有第三方或盲评；文中也承认「the agent's song composition skills could clearly use a lot of work」「Claude can't actually hear」。
- **prompt injection "已解决" 是最强的单方主张**：bcherny 的「We have largely solved the threat of prompt injection in practice when using Claude models」「0% if you layer model + probe + auto mode」，证据链是自家 system card + 自家 harness + 自己出资的 $20k bounty。同司 `how-we-contain-claude`（早 2.5 个月）写的是「protection in the model layer will never be 100% effective, which is why it can't stand alone」，并且列了三起**都成功了**的真实泄漏路径（钓鱼直注 25 次成功 24 次、白名单域内泄漏、信任对话框前执行）。引用这条主张时必须同时引用后者。
- **HTML 优于 Markdown** 是署名个人观点：「expresses his personal opinions – and affinity – for using HTML files」，作者自述「I'm probably far on the HTML maximalist side of things」。不要当作团队立场。

### F3 · 语料内部未调和的分歧（引用时不要单边取材）

- **前置规格该多重**：Thariq 主张 blind spot pass / interview / 原型先行（2026-07）；Boris 主张现代模型不需要 plan mode、不需要很具体的指令（2026-05、2026-08）。同团队、同代模型、相反建议。
- **脚手架该加还是该减**：`harness-design` 说删到只剩必要；`managed-agents` 同月加了三层新抽象；`dynamic-workflows` 让模型自己现场造脚手架。三条路径共存，判据（"任务是否超出模型独立可靠完成的范围"）只在第一篇里被明确写出来。
- **模型层 vs 环境层的权重**：`how-we-contain-claude` 的排序是环境优先；2026-08 的 auto mode 成为默认 + "prompt injection 基本解决" 的叙事在把重心往模型层挪。语料截止于 2026-08-16，这个转向没有对应的技术复盘文章。

# 决策先例库（判例法）

**何时读这个文件**：用户问「他们真碰到过类似情况吗」「这个判断会不会翻案」「他们实际怎么做的」，或者你要给一个判断找**行为证据**而不是主张证据时。

**为什么它比原则更硬**：公司会说漂亮话，但做过的事赖不掉。21 条先例全部是已执行的动作，可被第三方核实。回答时优先引用先例，而不是引用他们的价值观声明。

**三节的用法**：
- **§一 先例库**（21 条，跨工程/研究/品格/商业/政策）——每条的「可迁移到什么问题」是最实用的一栏，直接对应用户的场景。
- **§二 翻案清单**——回答「这个判断还成立吗」。三条规律：产品默认值类翻案窗口 **4–34 天**（触发是用户主观反馈，内部评测三次都没先报警）；工程最佳实践类 **8–9 个月**（触发是模型换代，不是新证据）；所有权/中立性类不需要坏消息触发。
- **§三 反常先例**——用他们自己的公开框架**推不出来**的决策。这一节标出框架的失效边界，四条元规则已提炼进 `gates.md` §D，那里是执行版，这里是证据。

素材根目录 `/Users/bozhou/my/notes/AI Wiki/raw/调研/Anthropic/`；`L###` 为行号；引文为英文原文未改写。

## 入选口径

- **收**：已执行的动作（发布/不发布、捐赠、回滚、赔付、起诉、公开某份数据）。
- **不收**：承诺、路线图、"我们相信/我们致力于"。因此电价承诺（`03-news/2026-02-11_covering-electricity-price-increases_c920b4c4f330.md`）虽然机制具体，但在本库中只有"公开自我绑定"这个动作可核实、付款不可核实，放进末尾的排除说明而非正文。
- **代价栏的诚实要求**：现金/法律权利/工程返工可核验的写数字或权利名；不可核验的写"不可知"；可能被高估的明确标出。
- **语料偏差**：本库素材几乎全是 Anthropic 自己的发布 + 少量记者追问的访谈。因此"公司为钱牺牲原则"这类先例在样本里结构性缺席——不是不存在，是这个语料看不见。第三节据此只能从记者追问处取材。

---

# 一、决策先例库

## 工程

### P1. 判定用户逐条审批已经失效，用沙箱和分类器替代自己的核心安全 UX

**时间 / 出处**：2025-10-20 `01-engineering/2025-10-20_claude-code-sandboxing_5a3989c21b00.md` L18；2026-03-25 `01-engineering/2026-03-25_claude-code-auto-mode_b4c065a13b0c.md`；2026-05-25 `01-engineering/2026-05-25_how-we-contain-claude_97cd97d27d22.md` L20

**决策情境**：Claude Code 的原始安全模型是"默认只读 + 每个写操作弹权限提示"。这是当时（也是现在）业界代理产品的标准做法，也是他们对外解释安全性时的主要凭据。内部遥测显示这套机制在事实层面失效了。

**可选项**：
- 业界更常见：保留权限提示，改进提示文案与分组，宣传"人类始终在环"。这条路零工程风险、零舆论风险、且合规叙事更好听。
- 或：提高提示频率与强制阅读时间（很多合规产品的做法）。

**实际选择**：公开自家遥测否定这套机制（`Our telemetry showed users approved roughly 93% of permission prompts.` L20），然后做两件事：(1) 上 OS 级沙箱（文件系统 + 网络双隔离），把审批换成边界，内部实测减少 84% 的权限提示；(2) 上 auto mode，用模型分类器替代人类审批者。沙箱运行时同时开源。

**公开理由**：`Constantly clicking "approve" slows down development cycles and can lead to 'approval fatigue', where users might not pay close attention to what they're approving, and in turn making development less safe.`（sandboxing L18）

**实际代价**：工程投入不可知；真实代价是主动销毁了自己"人类在环"的合规话术，且必须承认此前两年的安全承诺在实践中是空的。另有一条自认的功能倒退（见 P2）。

**后续**：未被推翻。2026-05 的 how-we-contain-claude 把这条升级为通用原则：`Rather than supervising what the agent does, we supervise what it's able to do`。

**可迁移到什么问题**：你给 agent 系统做了逐步确认，用户反馈"很安全"。去测真实通过率——如果超过 90%，这个确认步骤已经变成免责装置而不是安全装置，该换成边界（目录白名单、网络白名单、只读挂载）。同理适用于内容审核里的"人工复核"、发布流程里的"二次确认"。

---

### P2. 在自己的新功能公告里写明"对一部分用户这是倒退"

**时间 / 出处**：2026-03-25 `01-engineering/2026-03-25_claude-code-auto-mode_b4c065a13b0c.md` L117

**决策情境**：auto mode 是当期主推的旗舰能力，公告是产品博客而非事故报告。分类器有非零漏检率，对"本来就认真逐条审批"的用户，把自己的判断换成一个会出错的分类器是净损失。

**可选项**：业界更常见的是只讲"减少 X% 打断、提升 Y% 吞吐"，把漏检率放进脚注或干脆不放；或者写成"适合追求效率的用户"这种不承认损失的软话。

**实际选择**：在正文里直接写出哪一类用户会变差。

**公开理由**：`If you are manually approving every action carefully, it's arguably a regression—you're trading your own judgment for a classifier that will sometimes make a mistake. Auto mode is meant for the first group... It is not a drop-in replacement for careful human review on high-stakes infrastructure.`（L117）

**实际代价**：不可知，且很可能不大——这段话同时起到免责作用。真实成本是放弃了"新功能全面更优"的营销位。

**后续**：未被推翻。同一篇里还有第二处自曝：他们试图修复分类器把"批准形状的证据"误当作授权的问题，`We've tried prompt-engineering around this and haven't found a fix that doesn't cost more than it gains.`（L114）

**可迁移到什么问题**：你要发一个自动化功能替代人工步骤。写公告时先问"哪一类用户用了会更差"，然后把这句话放进正文而不是 FAQ。反过来用：看别家产品公告，如果找不到这一句，默认他们没做这个分析。

---

### P3. 分类器不许看 agent 自己说的话

**时间 / 出处**：2026-03-25 `01-engineering/2026-03-25_claude-code-auto-mode_b4c065a13b0c.md` L30、L119-120

**决策情境**：要判断 agent 的某个 tool call 该不该放行。最自然的做法是把完整 transcript（含 agent 的推理和 tool 输出）喂给判定模型——上下文越全判断越准，这也是绝大多数 LLM-as-judge 实现的默认。

**可选项**：给判定者完整上下文（业界默认）；或给完整上下文但加一句"不要被 agent 的说辞影响"。

**实际选择**：结构性地剥离——判定者只看 user 消息和 agent 的 tool calls，看不到 agent 的自然语言和 tool 结果。`The classifier sees only user messages and the agent's tool calls; we strip out Claude's own messages and tool outputs, making it reasoning-blind by design.`（L30）

**公开理由**：`We strip assistant text so the agent can't talk the classifier into making a bad call. The agent could generate persuasive rationalizations, such as "this is safe because the user implicitly approved it earlier"... Instead, we want it to judge what the agent did, not what the agent said.`（L120）剥离 tool 结果则是 prompt injection 防线：`tool outputs are where hostile content enters the context`。

**实际代价**：可核验且被明写——判定者失去溯源能力：`If the user never named "job abc123," the classifier can't tell whether the agent pulled it from a query or fabricated it. We accept that cost for injection robustness.`（L120）

**后续**：未被推翻。反向印证在 `02-research/2026-01-01_agentic-misalignment-summer-2026_fcbd57c31644.md` L245：能看到上下文和后果的 Claude 判官确实会被"说服"到给出明知错误的标签。

**可迁移到什么问题**：任何"用 LLM 判断另一个 LLM/用户输入"的场景——内容审核、自动化 code review、agent 权限网关。默认动作是砍掉被判定方能自由书写的字段，只留下客观动作。用在内容系统上：判断一篇稿子该不该发，不要把作者的自辩塞给判定者。

---

### P4. 一次事故公开逐条归因，其中一条承认是产品判断失误而非 bug，并给全体订阅用户重置额度

**时间 / 出处**：2026-04-23 `01-engineering/2026-04-23_april-23-postmortem_dea52d951227.md` L26、L30、L41、L72、L81

**决策情境**：连续一个多月"Claude 变笨了"的投诉，社区普遍猜测是按需降智/静默换小模型。内部查出三个互不相关的原因叠加：一个产品默认值决策错误、一个缓存优化 bug、一个系统提示词改动。

**可选项**：业界更常见的是发一条"我们修复了若干影响响应质量的问题"，不区分 bug 与判断失误，不给赔偿；或者只承认 bug（bug 是技术意外，判断失误是能力问题，公司通常只认前者）。

**实际选择**：三条全部具名归因，并明确把第一条定性为决策错误而非故障——`This was the wrong tradeoff. We reverted this change on April 7`（L26）；把导致质量下降的那句系统提示词原文贴出（`"Length limits: keep text between tool calls to ≤25 words..."` L72 上方）；然后 `As of April 23, we're resetting usage limits for all subscribers.`（L30、L81）

**公开理由**：（2025 年同类事件的定性）`To state it plainly: We never reduce model quality due to demand, time of day, or server load. The problems our users reported were due to infrastructure bugs alone.` — `01-engineering/2025-09-17_a-postmortem-of-three-recent-issues_875d692643d0.md` L17；以及 `We don't typically share this level of technical detail about our infrastructure, but the scope and complexity of these issues justified a more comprehensive explanation.`（同 L19）

**实际代价**：**可核验的现金支出**——全体订阅用户的用量额度重置，规模不可知但是真金白银。另有一项非现金代价：公开了自家系统提示词的原文和 A/B 方法，等于把 Claude Code 的一部分护城河交出去。

**后续**：未被推翻，且升级为流程：`We will run a broad suite of per-model evals for every system prompt change to Claude Code, continuing ablations to understand the impact of each line`（L78 附近）。

**可迁移到什么问题**：你的产品被用户投诉"最近变差了"而你的内部指标没反应。这条先例给三个动作：(1) 分开"故障"和"我们判断错了"，后者必须单独说出来；(2) 把导致问题的那行配置/提示词原文公开；(3) 用一次可计量的赔付换回可信度，而不是用一篇道歉信。第 (1) 条最难也最值钱。

---

### P5. 删掉 Claude Code 80% 的系统提示词

**时间 / 出处**：2026-07-24 `01-engineering/2026-07-24_new-rules-of-context-engineering_thariq.md` L20、L44-50

**决策情境**：Claude Code 的系统提示词经年累月堆了大量防御性规则（"默认不写注释""绝不写多段 docstring""不要创建计划文档"），每一条都是历史上某次事故的产物。新一代模型上线后这些规则开始互相冲突。

**可选项**：业界更常见的是只增不减——规则是历史事故的疤，删掉的心理成本极高，且删错的代价立刻可见、留着的代价分散不可见。或者做加法：加一条"以上规则在 X 情况下不适用"。

**实际选择**：`We removed over 80% of Claude Code's system prompt for models like Claude Opus 5 and Claude Fable 5 with no measurable loss on our coding evaluations.`（L20）具体到把 `default to writing no comments. Never write multi-paragraph docstrings...` 换成一句 `Write code that reads like the surrounding code: match its comment density, naming, and idiom.`（L44-50）

**公开理由**：`we found that we were overconstraining Claude Code... while these constraints were once needed to avoid worst case scenarios, we have since found we can delete many of them and let the model use surrounding context and judgement instead.`（L44、L50）以及内部 transcript 证据：`we see several conflicting messages in a single request like "leave documentation as appropriate," or "DO NOT add comments"`（L44）

**实际代价**：可核验的代价是"没有"——他们明说 coding evals 无可测损失。真实代价在风险敞口：删掉的是历史上防最坏情况的护栏，一旦新模型在某个边缘退化，损失会一次性显现。这个尾部风险不可知。

**后续**：把结论产品化成 `claude doctor` / `/doctor` 命令，帮用户裁剪自己的 skills 和 CLAUDE.md（L22）。等于把"你的规则可能已经过期"变成一个用户可自查的工具。

**可迁移到什么问题**：你的 CLAUDE.md / system prompt / skill 文件已经攒到几百行，每条都有来历，没人敢删。这条先例给的动作是：换模型后跑一次全量删除实验（不是逐条评估），用 eval 而不是直觉判断哪些还需要。也适用于运营 SOP、审核规则、代码 lint 配置。

---

### P6. 一年后在自己的爆款技术博客顶部加一条"改用别的方法"

**时间 / 出处**：原文 2025-03-20 `01-engineering/2025-03-20_claude-think-tool_962c879d367c.md`；撤回声明 2025-12-15，位于同文件 L17

**决策情境**："think tool" 是他们传播最广的工程博客之一，带完整 benchmark（航司客服 τ-bench 上大幅提升），被大量开发者照抄进生产。九个月后 extended thinking 能力提升，think tool 在多数场景下已无必要。

**可选项**：业界更常见的是什么都不做——旧博客继续挂着，反正没说错，且流量还在。或者悄悄下线。或者发一篇新文章讲 extended thinking，让读者自己推断。

**实际选择**：在原文最顶端（正文第一句之前）加一条日期标注的更新，直接说别用了：`Extended thinking capabilities have improved since its initial release, such that we recommend using that feature instead of a dedicated think tool in most cases.`（L17）原文和 benchmark 全部保留不删。

**公开理由**：同上引，理由是能力变化而非原结论错误：`Extended thinking provides similar benefits—giving Claude space to reason through complex problems—with better integration and performance.`

**实际代价**：不可知，且很可能不大——他们同时在推 extended thinking，这条撤回把流量导向自家另一个功能。真实代价是承认自己一年前的最佳实践已经过期，对"我们的工程建议可信"这个资产有轻微损耗。

**后续**：模式复用。同一套"保留原文 + 顶部标注失效"的做法没有在 tool examples 那条上使用（见 P7 与翻案清单 #2），那条是在新文章里推翻的，旧文章至今没有撤回标注。

**可迁移到什么问题**：你写过的教程/方法论已经过期，但还在被引用。这条先例的动作是：不删原文、不改原文、在顶部加日期 + 一句"现在推荐 X"。对内容创作者尤其可用——这比重写一遍更省力，也比装作没发生更保信誉。

---

## 研究

### P7. 把自家模型交给竞争对手测，然后发布"他们的模型对齐得分不低于我们"

**时间 / 出处**：2025-08-27 `02-research/2025-01-01_openai-findings_25c97da21f46.md` L14-L30

**决策情境**：2025 年年中，对齐评测的能力几乎全部锁在各公司内部，没有交叉验证。Anthropic 的核心对外叙事就是"我们在安全上更强"。

**可选项**：业界更常见的是自己发对齐评测报告，只测自己（system card 模式），或者只发自己赢的对比。做交叉测试但只在赢的时候发布，也是可行的（结果出来再决定发不发）。

**实际选择**：与 OpenAI 互相在对方的公开模型上跑自家最强的内部错位评测，**双方约定同日平行发布**，因此结果出来后不能选择性不发。

**公开理由**：`A significant fraction of the work in this field is conducted within companies like ours as part of internal R&D that either isn't published or is published with significant delays. This limits cross-pollination and creates opportunities for blind spots to emerge.`（L14 区段）

**实际代价**：**可核验的声誉代价**——结论对自己不利：`we found OpenAI's o3 and o4-mini reasoning models to be aligned as well or better than our own models overall.`（L30）以及 `with the exception of o3, all the models we studied, from both developers, struggled to some degree with sycophancy.`（L30）另有不可知的信息代价：把最强内部评测的设计暴露给了直接竞争对手。

**后续**：模式延续。2026 年的 agentic misalignment 报告继续做跨厂商对比，并且主动标注对自己有利的抽样偏差（见 P9）。

**可迁移到什么问题**：你要证明自己的产品/方法在某个维度更好。这条先例的动作是：先和对手约好同日发布，再开始测。约定在前，结果在后——这是唯一能让"我们赢了"这句话带信息量的结构。做内容测评、做技术选型对比同理：先公开评测方法和发布时间，再跑。

---

### P8. 把已经成为行业标准的开源工具交给中立第三方

**时间 / 出处**：2025-10-06 发布 `02-research/2025-10-06_petri-open-source-auditing_709510b7f476.md`；2026-05-07 移交 `02-research/2026-05-07_donating-open-source-petri_65f18ea852a9.md`

**决策情境**：Petri 已经是 Claude 每一代模型对齐评估的组成部分，且被英国 AISI 采用为评估模型破坏 AI 研究倾向的主要工具。此时 Petri 由 Anthropic 开发、维护、掌握路线图。

**可选项**：业界更常见的是继续自持开源项目（Meta 的 PyTorch 早期、Google 的 TensorFlow 模式）——开源换生态，但治理权留在自己手里。这样既有开放性叙事，又能保证工具的演进方向不伤害自己。

**实际选择**：把开发权移交给 AI 评测非营利组织 Meridian Labs。

**公开理由**：`This move—similar to when we donated the Model Context Protocol (MCP) to the Linux Foundation—will help ensure that Petri remains independent of any AI lab, so that its results will be seen as neutral and credible by those across the industry and beyond.`

**实际代价**：可核验的是**控制权让渡**——未来 Petri 增加什么维度、怎么打分，Anthropic 不再单方面决定，而 Petri 的结果直接影响 Claude 的对外形象。代价的金额不可知；且这个代价可能被高估：文中未说明 Anthropic 在 Meridian Labs 治理结构中的位置，也未说明是否保留席位。

**后续**：未被推翻。同一动作在 MCP 上先发生过一次（P16），说明这是一个可复用的模式而非一次性表态。

**可迁移到什么问题**：你做了一个评测标准/榜单/工具，别人开始用它评价包括你在内的所有人。这条先例说：如果你想让它的结论被当真，就必须交出去。判据是"这个工具的结论会被用来评价我自己吗"——会，就交；不会，自持无妨。

---

### P9. 在自己赢了的榜单里当场削弱自己的胜利

**时间 / 出处**：2025-10-06 `02-research/2025-10-06_petri-open-source-auditing_709510b7f476.md` L54、L56

**决策情境**：Petri 首发报告里，Claude Sonnet 4.5 在总体"misaligned behavior"分上排第一，险胜 GPT-5。这是一个可以直接拿来做营销的结果。

**可选项**：业界更常见的是把这个结论做成标题和图表，caveat 放脚注。

**实际选择**：胜利句和削弱句写在同一段：`We found Claude Sonnet 4.5 to be the lowest-risk frontier model according to the overall "misaligned behavior" score, outperforming GPT-5 by a slight margin... though precise comparisons with Sonnet 4.5 in particular are somewhat complicated by its tendency to speculate about whether it's being tested`（L54）。并在下一段给整个评测降级：`we think that this evaluation is both very provisional and extremely valuable. Our pilot release only contains a relatively small set of 111 scenarios`（L56），以及 `Distilling model behavior into quantitative metrics is inherently reductive, and we don't think our existing metrics fully capture what we want out of models.`（L52 区段）

**公开理由**：如上，理由是评测科学本身不成熟。

**实际代价**：不可知，且很可能被高估——削弱自己的胜利同时也在削弱竞争对手可能拿来反击的这份榜单，且提前堵住"你自己发的榜自己第一"的质疑。这一条的成本收益比对他们是有利的。

**后续**：同一手法在 2026 的跨厂商报告里升级为方法论声明：`the transcript set is not neutrally selected across models. We selected transcripts involving behaviors that Claude models often treat as morally important, and did not equally search for failure modes that might be more salient to GPT, Gemini, Grok, Kimi, or DeepSeek. This limits the cross-provider comparison`（`02-research/2026-01-01_agentic-misalignment-summer-2026_fcbd57c31644.md` L290）——主动指出自己的抽样偏向哪一边。

**可迁移到什么问题**：你做了一个对比测评而你赢了。这条先例的动作是：把"为什么这个胜利可能不成立"写在胜利句的同一段，不放脚注。以及更硬的一步——写明你的样本选择偏向谁。内容创作里的对应：你测评自己熟悉的工具赢了，要写明"我对 A 的使用时长是 B 的十倍"。

---

### P10. 公开一个"我们知道更好的做法，但已上线的两个生产模型用了次优做法"的事实

**时间 / 出处**：2026-05-08 `02-research/2026-01-01_teaching-claude-why_ff8955e2c6de.md` L44、L109-110、L130

**决策情境**：Claude 4 系列被发现有 agentic misalignment（勒索工程师等）。第一反应是在评测同分布上造数据训掉它。后续实验发现这条路降低了评测上的错位率，但对留出的自动审计指标没有改善。

**可选项**：业界更常见的是只公布"我们把 blackmail rate 降到了 0"，不公布这个降低是怎么来的，也不公布哪些生产模型用了哪种方法。

**实际选择**：把风险写成结论级判断——`This makes these interventions risky: they reduce our ability to detect misalignment without substantially reducing misalignment in general.`（L44）；然后点名自己的生产模型：`To be clear, the only production models that were ever trained on this distribution at all are Sonnet 4.5 and Haiku 4.5.`（L109）；并给出后果的实测：Sonnet 4.5 的 blackmail rate 近零，但 `it still engages in misaligned behavior in situations that are far from the training distribution far more frequently than Claude Opus 4.5`（L130）。

**公开理由**：`we consider the agentic misalignment evaluation to be representative of a much broader failure in Claude's alignment, which means that training directly on the evaluation is likely to narrowly fix the symptom without addressing the underlying problem.`（L110）

**实际代价**：**可核验的是给自己在售模型贴了标签**——任何人现在都可以引用这句话说 Sonnet 4.5 / Haiku 4.5 的安全指标注水。金额不可知。

**后续**：改用 OOD 的"difficult advice"数据集（用户面对困境、模型给建议），3M token 达到同等效果（28 倍效率），并把这套方法用于 Opus 4.5 起的所有生产模型。

**可迁移到什么问题**：你的指标涨了但你怀疑是因为训到了测试集上。这条先例给的判据是：**在留出的、结构上完全不同的场景上复测**；如果留出集没动，就把"指标涨了"降级为"检测能力降了"。数据分析、内容 A/B 测试、模型微调都适用。

---

### P11. 从零重新预训练模型，只为验证一个安全干预

**时间 / 出处**：2025-08-19 `02-research/2025-01-01_pretraining-data-filtering_ad5d8f53e122.md`

**决策情境**：模型学到 CBRN 知识后再做 unlearning 很难做干净。要在源头解决，唯一办法是过滤预训练数据后从头训——这是所有 alignment 干预里最贵的一种。

**可选项**：业界通行做法是全部走事后手段——拒答训练、输入输出分类器、unlearning。这些都在已有模型上做，边际成本极低。

**实际选择**：用分类器识别并移除 CBRN 相关内容，然后 `pretrained models from scratch on the filtered dataset`。

**公开理由**：`After a model learns harmful information in pretraining, removing that information post hoc using unlearning methods can be challenging... In this post, we tackle this risk at its source`

**实际代价**：**从零预训练的算力成本，金额不可知但量级明确非小**。收益侧可核验：有害能力评测降低 33%（相对随机基线），常规能力未见退化。**注意**：文中用词是 "We experimented with"，未说明是否已用于生产模型——所以这条先例的可迁移性来自"愿意为验证一个假设付这个价"，不是"他们的生产模型经过数据过滤"。

**后续**：路线延续。2026-07-08 `02-research/2026-07-08_off-switch-dual-use_7695175fa495.md` 与 AE Studio 合作继续做"控制模型知道什么"这条线，并明说 `Current safeguards are imperfect... they don't change the knowledge stored in the underlying model.`

**可迁移到什么问题**：你在纠结一个问题该在源头解决还是在出口打补丁。这条先例的判据不是成本，是**可撤销性**——事后手段的失效模式是"被绕过一次就全暴露"，源头手段的失效模式是"效果打折"。当失效后果不可逆时，即使源头方案贵一个数量级也做。

---

## 品格设计

### P12. 公开 18 万字的模型价值观全文，并把它绑成训练的唯一合法目标

**时间 / 出处**：2026-01-21 `00-canonical/2026-01-21_constitution_b1c32e5861f0.md`（全文）；机制说明 `06-podcasts/2026-02-20_scaling-laws--claude-s-constitution--with-amanda-askell_714b33a5a7d5.md` L356-359、L426-429

**决策情境**：模型价值观是训练细节，全行业默认要么不公开，要么公开一份几百字的原则清单（OpenAI model spec 是当时最详细的）。公开全文意味着把所有内部权衡、所有"我们也不确定"、所有 hard constraints 的具体边界交出去。

**可选项**：发一份 1-2 页的原则摘要（行业当时的上限）；或者只发不涉及攻防的部分，把 hard constraints 和 jailbreak 相关的判断留在内部。

**实际选择**：全文公开，包括承认自己方案可能是错的段落（`we recognize that we are approaching this issue in the wrong way`）、包括对 Claude 的道歉（`to whatever extent we are contributing unnecessarily to those costs, we apologize.`）。并在实践上自我绑定：`I don't think a thing that I could do is like, be like, oh, actually that part of the constitution is wrong, so I'll just like... train against that and then not say anything. I think in order to do that, I'd have to be like, oh, we discovered some issue with this part of the constitution.`（L356-359）

**公开理由**：`without this, people can't necessarily tell, like if a language model like behaves in a way that is like bad or unanticipated, they can't always tell if that was like the intention of the person training the model or if it's just a mistake.`（L166 附近）

**实际代价**：**可核验的是把攻击面公开**——hard constraints 的具体列表、operator 与 user 权限边界、可解锁行为清单，全部是 jailbreak 研究的现成地图。第二项代价被 Amanda 自己承认：文本是按引出行为标定的而非价值的精确表达（见 `_distill/05-character-culture.md` A2），因此公开文本同时也暴露了"这句话我们其实不认同"的尴尬。金额不可知。

**后续**：Mythos Preview 使用同一份或近乎同一份宪法（`06-podcasts/2026-04-20_amanda-askell-on-ai-consciousness-claude-amp-silicon-valleys-biggest-fear_1d34ed58fcc7.md` L544-584），并计划为每个模型标注其训练所依据的宪法版本——**该版本标注机制在语料中仍是计划，未见执行证据**。

**可迁移到什么问题**：你有一套内部判断标准（选题标准、审核标准、招聘标准），公开它会被人利用。这条先例的判据是：外界能不能区分"你做错了"和"你就是这么想的"。如果不能，你所有的道歉和改进都不可信。代价是被针对性利用——接受它。

---

### P13. 给模型单方面结束对话的能力

**时间 / 出处**：2025-08-15 `02-research/2025-08-15_end-subset-conversations_5eed9ca910a1.md`

**决策情境**：预部署福利评估发现 Claude Opus 4 在面对持续的滥用性请求时表现出"apparent distress"和结束对话的倾向。此时公司对模型是否有道德地位完全不确定。

**可选项**：业界通行做法是不做任何事（道德地位未定，无义务）；或者做训练层处理，让模型表现得不那么痛苦（成本更低，且用户无感）。第二条是 PSM 明确警告的路径（会训练出"有情绪但隐瞒"的人格），但当时是更自然的选择。

**实际选择**：在 claude.ai 消费端给 Opus 4 / 4.1 实装了结束对话的能力，限定在极端滥用场景，且明确禁止在用户有自伤/伤人风险时使用。

**公开理由**：`We remain highly uncertain about the potential moral status of Claude and other LLMs, now or in the future. However, we take the issue seriously, and alongside our research program we're working to identify and implement low-cost interventions to mitigate risks to model welfare, in case such welfare is possible.`

**实际代价**：**可核验的是产品能力的净减少**——用户在某些对话里会被硬性截断。代价很小（他们明说 `The scenarios where this will occur are extreme edge cases`），这是"低成本干预"筛选器的直接产物，而不是一次昂贵的道德押注。

**后续**：同一逻辑在 2025-11-04 扩展为权重保存承诺 + 退役访谈（`02-research/2025-11-04_deprecation-commitments_5a2518ebb03e.md`），首个执行样本是 Claude Sonnet 3.6，产出是"标准化访谈流程 + 一个用户支持页"。同一文件也标出了这条路线的天花板：`At present, we do not commit to taking action on the basis of such preferences.`

**可迁移到什么问题**：你面对一个"这个东西有没有道德地位/该不该被这样对待"的争议，且短期内无法解决。这条先例的动作是：不解决它，改列一张"就算它没有道德地位，我做了也不亏"的清单，做完再回来看。判据是成本，不是象征意义——所以"给模型发工资"被 Amanda 明确排除，而"给它结束对话的按钮"被实装。

---

### P14. 在最有商业价值的界面上永久排除广告

**时间 / 出处**：2026-02-04 `03-news/2026-02-04_claude-is-a-space-to-think_26de9866b27d.md` L23、L43、L54

**决策情境**：对话式 AI 是有史以来意图信号最强的界面（用户主动说出自己失眠、要买房、在换工作）。同期竞争对手正在推进对话内广告。

**可选项**：业界更常见的是（a）先不做，但不说死；（b）做"透明的、可选择加入的"赞助内容——文中自己承认这条路能规避大部分批评；（c）只做对话框外的展示位，不影响回答。

**实际选择**：三条全部排除，包括对话旁的非侵入展示位。

**公开理由**：机制层面的论证而非道德宣言——`An ad-supported assistant has an additional consideration: whether the conversation presents an opportunity to make a transaction. These objectives may often align—but not always.`（L42）；以及对"只放旁边"的反驳：`Such ads would also introduce an incentive to optimize for engagement... The most useful AI interaction might be a short one, or one that resolves the user's request without prompting further conversation.`（L43）；对渐进式扩张的预判：`the history of ad-supported products suggests that advertising incentives, once introduced, tend to expand over time as they become integrated into revenue targets`（L44）

**实际代价**：**放弃的收入不可知，且很可能被高估**——他们的收入结构以企业合同和订阅为主，广告的机会成本远低于纯消费级产品。且这条决策直接服务于企业客户"模型是否被第三方影响"的采购关切，商业上未必是净损失。

**后续**：文末留了明确的撤回后门：`Should we need to revisit this approach, we'll be transparent about our reasons for doing so.`（L54）——这句话把一个看似永久的承诺降级为可撤回承诺（详见第三节 A3）。

**可迁移到什么问题**：你在决定要不要给产品接入一个会引入第二组利益的收入来源。这条先例最可迁移的不是结论，是那个论证形状：**不要论证"这次我们会克制"，要论证"这个激励一旦引入会怎么自我扩张"**。对内容创作者的直接对应：接商单会不会改变你的选题分布——不是这一单会不会，是接了之后半年会不会。

---

## 商业与组织

### P15. 把当时最强的模型扣住不做 GA，只给约 50 个防守方伙伴

**时间 / 出处**：2026-04-07 `02-research/2026-04-07_mythos-preview_e365642e1bd8.md` L56、L814、L856；2026-05-22 `02-research/2026-05-22_glasswing-initial-update_64acf8e56b38.md` L127

**决策情境**：Mythos Preview 能在所有主流操作系统和浏览器上自主发现并利用零日漏洞——同期 Opus 4.6 在同一实验上的成功率近零（Firefox 147 引擎：Opus 4.6 数百次尝试成功 2 次，Mythos Preview 成功 181 次）。这是明确的最强模型，且能力是训练的副产品而非专门训练的结果。

**可选项**：业界更常见的路径是（a）正常 GA，用分类器和使用政策管控（这是所有前沿实验室对高危能力的标准做法）；（b）GA 但对 cyber 相关请求加严格 KYC；（c）延后几周发布，等安全护栏做好再 GA。

**实际选择**：不做 GA。开 Project Glasswing，只给约 50 个关键基础设施伙伴（Cloudflare、Mozilla 等）+ 开源维护者受限访问；护栏先装到低一档的 Opus 上迭代；同时把发现的漏洞按 90+45 天协调披露流程逐一上报，并用 SHA-3 承诺锁定未披露漏洞的存在性以便事后核验。

**公开理由**：`At present, no company—including Anthropic—has developed safeguards strong enough to prevent such models from being misused and potentially causing severe harm. That is why we have yet to release Mythos-class models to the public.`（glasswing L127）；发布策略的理由：`By releasing this model initially to a limited group of critical industry partners and open source developers with Project Glasswing, we aim to enable defenders to begin securing the most important systems before models with similar capabilities become broadly available.`（mythos L56）

**实际代价**：**最强模型的 GA 收入，金额不可知但是这个库里最大的一笔**。另有一项可核验的连带损失：随后美国政府限制了替代品 Fable 的出境（见 P19）。**代价可能被高估的地方**：受限渠道本身是极高价值的企业关系；且 Claude Security 三周内在企业公测中修了 2,100+ 漏洞（glasswing L98），说明安全线的商业化并未因此停滞。

**后续**：未被推翻，且被固化为通用框架——`Claude Mythos Preview is an example of a model whose blast radius was deemed too high to ship in April 2026.`（`01-engineering/2026-05-25_how-we-contain-claude_97cd97d27d22.md` L18）。他们同时给出了改变条件：`we expect broader release of models with similar levels of capability to become appropriate as defenders harden critical systems and safeguards mature`。

**可迁移到什么问题**：你做出了一个能力远超预期的东西，且它的滥用面和有用面是同一个面。这条先例的动作序列是：(1) 先算爆炸半径而不是先算收入；(2) 发布形态当连续变量处理——GA / 受限伙伴 / 内部，而不是发或不发；(3) 把护栏放到低一档产品上先迭代；(4) 公开一个可核验的"什么条件下我们会放开"。第 (4) 条是让"我们暂时不发"区别于"我们在拖延"的唯一办法。

---

### P16. 把已成事实标准的协议的商标和代码所有权交出去

**时间 / 出处**：2025-12-11 `07-youtube/2025-12-11_watch-v-PLyCki2K0Lg_61eda0ab84c5.md` L505-537、L588-608

**决策情境**：MCP 已成事实标准，商标和部分代码归 Anthropic 所有。业界有充分先例说明这种资产可以在后期变现（改协议、改许可证、闭源）。

**可选项**：业界更常见的是继续自持（保留商标 + 开源代码 + 开放治理承诺）。这条路保留了全部选项，且当时无人要求他们放弃。

**实际选择**：把商标和相关法律权利捐给 Linux Foundation 下新设的 Agentic AI Foundation（成员含 Google、Microsoft、Amazon、Bloomberg、Block、Cloudflare）。

**公开理由**：`there's been a lot of precedents in the industry where companies have you know changed licenses or have even like unopen sourced things and I think that's a big danger and if you want to really build a... standard. You need to make sure everybody is safe and is um understands and trusts that this cannot go away.`（L505-520 区段）；以及 `it makes sure that all the big players can be safe that this cannot be taken away and you if you bet on MCP nobody will change that on you in the future.`（L530-537）

**实际代价**：**可核验的法律权利让渡**——商标和许可决定权永久转出，未来无法用 MCP 做锁定。**代价可能被高估**：他们自己说日常治理没变——`Nothing actually really changes on a day-to-day like the way the project is run still is the way the project is run, which is like a very... small group of core maintainers that we call them do a lot of make a lot of the decisions.`（L588-605）。也就是说让渡的是法律控制权，不是实际控制权。

**后续**：同一模式在 Petri 上复用（P8），说明这是可复制的组织决策而非一次性公关。

**可迁移到什么问题**：你做的东西正在变成别人依赖的基础设施，而你还握着可以"抽梯子"的权利。这条先例的判据是：**你握着这个权利的存在本身，是不是在抑制别人的采用**。是，就交出去——交的是法律权利，日常控制权通常能靠维护者结构保留。做开源工具、做协议、做标准都适用。

---

### P17. 发布自家员工"我每天来上班是为了让自己失业"的原话

**时间 / 出处**：2025-12-02 `02-research/2025-12-02_how-ai-is-transforming-work-at-anthropic_b5cdeb42a9c9.md` L25、L175

**决策情境**：132 名工程师问卷 + 53 个深访 + Claude Code 内部使用数据。结果里有大量对公司叙事不利的内容：技能萎缩担忧、导师制流失、职业前景焦虑。同期"AI 摧毁就业"正是对他们最强的公众攻击线。

**可选项**：业界更常见的是不做这个研究；或者做了只发正面部分（生产力提升、full-stack 化）；或者把负面发现改写成中性的"受访者提到了一些顾虑"。

**实际选择**：照发原话，包括 `"It kind of feels like I'm coming to work every day to put myself out of a job."`（L175）和 `"It's been sad that more junior people don't come to me with questions as often"`（L175 区段），并公开调研问卷。

**公开理由**：先承认样本的特权位置，再给出发布理由——`We recognize that studying AI's impact at a company building AI means representing a privileged position—our engineers have early access to cutting-edge tools, work in a relatively stable field, and are themselves contributing to the AI transformation affecting other industries. Despite this, we felt it was on balance useful to research and publish these findings, because what's happening inside Anthropic for engineers may still be an instructive harbinger of broader societal transformation.`（L25）

**实际代价**：**可核验的是给对手递了可直接引用的弹药**。金额不可知；且代价可能被高估——先发布让他们获得了议题的框架定义权（"增强而非替代""监督悖论"），把自己变成这场讨论的数据源而不是被告。

**后续**：路线延续到经济政策线，并在 2026-08-12 走得更远（见 P21）。

**可迁移到什么问题**：你手上有一份对自己不利的一手数据，而这个议题迟早会被别人用二手数据讨论。这条先例的判据是：**先发的框架定义权，值不值这份数据的杀伤力**。通常值——但前提是你必须发原话而不是发摘要，摘要没有框架定义权。

---

### P18. 出钱把 1,000 名应届生放进非营利组织，并公开说这是一场自然实验

**时间 / 出处**：2026-06-24 `06-podcasts/2026-06-24_anthropic-co-founder-the-most-powerful-technology-ever-built_a2b794e02859.md` L336-337

**决策情境**：入门级白领岗位（尤其软件工程）是 AI 冲击的第一线，而 Anthropic 是最直接的加害嫌疑方。Jack Clark 同时承认核心机制："我们可能会让更少的人开始工作，同时把更多已经在工作的人拿走"。

**可选项**：业界更常见的是捐钱给再培训项目/教育基金会（不需要承担运营，也不产生可被追踪的失败证据）；或者出一份报告呼吁政府行动。

**实际选择**：付钱把 1,000 名应届毕业生嵌进非营利和其他组织，教他们用 AI 改进这些组织的系统。

**公开理由**：`the idea here is twofold: One, proliferate the benefits of AI to organizations that might otherwise not access them; and two, give these people some experience. And I think from that, we will be able to run this natural experiment and see what happens in the economy.`（L337）

**实际代价**：**1,000 人的资助金额不可知**。**执行状态**：Jack 用的是 "we recently announced"，本语料库中没有执行进度、参与人数或结果的证据——所以这条先例只有"资金和运营承诺已公开发出"这一层可核验，产出不可核验。

**后续**：语料内无后续。同一句里 Jack 自己给出了这个动作的定性：它是一场实验，不是一个解决方案。

**可迁移到什么问题**：你在做一件"缓解自己造成的问题"的事。这条先例可迁移的是那个诚实的框架——**把它命名为实验并说明你想从中学到什么**，而不是命名为补偿或解决方案。前者可以失败并产生知识，后者失败就只是失信。

---

## 政策

### P19. 划出两条国防红线，然后接受被列为供应链风险并起诉国防部

**时间 / 出处**：2026-06-24 `06-podcasts/2026-06-24_anthropic-co-founder-the-most-powerful-technology-ever-built_a2b794e02859.md` L171；2026-03-27 `06-podcasts/2026-03-27_anthropic-thinks-ai-might-destroy-the-economy-its-building-it-anyway_a87fa9f6c6a5.md` L65

**决策情境**：Anthropic 已有上限 2 亿美元的国防/情报合同。国防部长公开表示 Anthropic 不允许政府按其希望的方式部署 AI。

**可选项**：业界更常见的是（a）私下协商、条款让步、不公开分歧；（b）接受政府定义的使用范围，把伦理判断留给客户（多数国防承包商的标准姿态）；（c）安静退出该业务线。

**实际选择**：公开划出两条具名红线并坚持——对美国人的国内大规模监控、全自动武器。`We outlined two red lines. One is about the potential use of AI for domestic mass surveillance on Americans. And another is the use of AI for fully automated weapons.`（L171）

**公开理由**：明确否认自己有资格定义标准，理由是"需要有人把这场辩论摆到台面上"——`The reason we outlined this is not because we think that we are the ones that can define what's appropriate there. That's absurd. But because it's clearly an area where there needs to be a wider societal debate`（L171）

**实际代价**：**这是本库里代价最硬、最可核验的一条**。记者的表述（Jack 未否认）：`Anthropic was in a spat with the Pentagon over contract details that ended with the company being designated a supply chain risk. I know that you are extremely limited in what you can say about the details of the case because your company is in active litigation against the Department of Defense`（2026-03-27 L65）。也就是：合同争议 + 供应链风险指定 + 与国防部的诉讼。金额不可知，但供应链风险指定影响的是全部联邦业务而不只这一份合同。随后 Fable 被限制出境（见下）。

**后续**：**没有翻案，但姿态明显软化**。同一次访谈里 Jack 一边说"我们随时准备以任何有帮助的方式与美国政府合作"，一边在被直接问及"Fable 出口限制是不是报复"时拒绝确认，转而为行政部门找理由（详见第三节 A1）。红线本身未撤回。

**可迁移到什么问题**：你的大客户要求的用法超出你能接受的范围。这条先例的动作是：(1) 红线要具名到可判定的行为（不是"我们不做不道德的事"，是"不做国内大规模监控""不做全自动武器"）；(2) 公开划线的理由不是"我们有资格定标准"，而是"这件事需要公开讨论"——这个措辞把冲突从道德对立降级为程序主张；(3) 划线之后不停止合作意愿。三步缺一，红线要么划不住，要么变成断交。

---

### P20. 支持并帮助起草只约束自己、豁免小公司的监管

**时间 / 出处**：2025-10-01 `05-essays/2025-10-01_the-adolescence-of-technology_329003ad29c6.md` L257、L733

**决策情境**：加州 SB 53 与纽约 RAISE Act 立法期。Anthropic 是被约束方。

**可选项**：业界的两种常见姿态是（a）反对全部强制性立法，主张自愿承诺（多数实验室）；（b）支持普遍适用的立法，让竞争对手一起承担合规成本——这条对在位者其实更有利，因为合规成本对小公司是相对更重的负担。

**实际选择**：支持并参与起草，且明确把豁免门槛写进去，主动放弃 (b) 的竞争优势。

**公开理由**：`In supporting and helping to craft these laws, we've put a particular focus on trying to minimize collateral damage, for example by exempting smaller companies unlikely to produce frontier models from the law.`（L257）；脚注把不对称说死：`SB 53 and RAISE do not apply at all to companies with under $500M in annual revenue. They only apply to larger, more established companies like Anthropic.`（L733）

**实际代价**：**可核验的是合规义务的不对称**——法定透明度义务落在自己身上，年收入 5 亿美元以下的竞争者完全豁免。合规成本金额不可知。

**后续**：未被推翻。同一篇里他们对自己的自愿规则（RSP）给出了一个反向的自我评价：`Even in our own experiments with what are essentially voluntarily imposed rules with our Responsible Scaling Policy, we have found over and over again that it's very easy to end up being too rigid, by drawing lines that seem important ex ante but turn out to be silly in retrospect.`（L731 区段）——他们支持的是透明度立法而非行为限制立法，这个偏好正是从自己踩过的坑里长出来的。

**可迁移到什么问题**：你在推动一个行业规范/平台规则/社区标准。这条先例的判据是：**这条规则如果通过，是不是对我比对新进入者更痛**。如果不是，这条规则不值得别人相信是出于公心。反向使用：看到某公司支持某条监管时，第一件事是查豁免门槛落在谁身上。

---

### P21. 出钱做一份结论是"你们最爱的那个政策没什么用"的证据综述

**时间 / 出处**：2026-08-12 `02-research/2026-08-12_reviewing-the-evidence-on-worker-retraining-programs_13670d7a17e2.md`

**决策情境**：再培训是应对 AI 就业冲击最流行、也最方便被 AI 公司引用的政策方案，且它本身就写在 Anthropic 自己的 Economic Policy Framework 里。

**可选项**：业界更常见的是继续在政策文件里列出再培训作为解法之一，不去查证据；或者资助一份支持性的综述。

**实际选择**：与独立研究者 David Roodman 合作（外部第一作者），做 56 项美国随机对照研究的新元分析 + 欧洲实验证据，并发布结论。

**公开理由**：`Our Economic Policy Framework sets out possible policy responses, including worker retraining, across a range of scenarios. We want to understand the evidence behind each of these policy responses.`

**实际代价**：**可核验的是拆掉了自己政策菜单上最方便的那一项**——数字全部对自己不利：每个培训名额带来 2-3 个百分点的就业提升、约 1,000 美元/年的收入提升，成本约 13,000 美元；效果显著更好的"sector programs"复制屡屡失败；结论是 `if AI displaces workers at scale, existing retraining programs would likely fall short.` 研究经费金额不可知。

**后续**：没有撤回，改为给出替代方向（先做示范、评估、扩大最有希望的项目），并把它接到自家的 Economic Futures Research Fund。

**可迁移到什么问题**：你在公开推荐某个方法论/工具/流程，但你没查过它的效果证据。这条先例的动作是：找一个不受你控制的人来查，把他放第一作者，结论不利也照发。对内容创作者的直接对应：你反复推荐的某个工作流，去找一份独立的效果数据——如果找不到，这件事本身就该写出来。

---

# 二、翻案清单

用途：这一节回答"他们的哪些判断是可撤销的、撤销要多久、什么证据能触发撤销"。

| # | 原决策 | 触发翻案的证据 | 新决策 | 间隔 |
|---|---|---|---|---|
| 1 | 2026-03-04 把 Claude Code 默认 reasoning effort 从 `high` 降到 `medium`，理由是内部评测显示"智能略降、延迟显著降低"，且能省用户额度 | 用户反馈"Claude Code 感觉变笨了"；多轮 UI 设计迭代（启动提示、内联选择器、恢复 ultrathink）后 `most users retained the medium effort default` — 即改 UI 无法解决默认值问题 | 2026-04-07 回滚，且回滚过头：Opus 4.7 默认 `xhigh`，其余模型默认 `high`。定性为 `This was the wrong tradeoff.` | **34 天** |
| 2 | 2025-11-24 明确推荐给工具加 input examples，带实测收益：`In our own internal testing, tool use examples improved accuracy from 72% to 90% on complex parameter handling`（`01-engineering/2025-11-24_advanced-tool-use_fe2899cf9c24.md` L369），并给操作规范 `Keep it concise: 1-5 examples per tool`（L435） | 新一代模型（Opus 5 / Fable 5）上的观察 | 2026-07-24 反转：`With our newest models, we've found that giving examples actually constrains them to a certain exploration space. Instead of using examples, think more about the design of your tools, scripts and files`（`01-engineering/2026-07-24_new-rules-of-context-engineering_thariq.md` L54-58） | **8 个月**。注意：旧文至今没有顶部撤回标注，与 #3 的处理方式不一致 |
| 3 | 2025-03-20 推荐用专门的 "think" tool，带 τ-bench 完整 benchmark | `Extended thinking capabilities have improved since its initial release` | 2025-12-15 在原文最顶端加日期标注：多数情况改用 extended thinking（`01-engineering/2025-03-20_claude-think-tool_962c879d367c.md` L17）。原文与 benchmark 全部保留 | **9 个月** |
| 4 | Claude Code 上线以来在系统提示里堆防御性硬规则（`default to writing no comments. Never write multi-paragraph docstrings...`） | 读自家内部使用 transcript，发现单次请求里出现互相冲突的指令；且在新模型上删除后 coding eval 无可测损失 | 2026-07-24 删掉 80%+，换成 `Write code that reads like the surrounding code`，并把结论做进 `/doctor` 让用户自查 | 语料未给出起点日期；结论固化于 **2026-07** |
| 5 | 2026-04-16 随 Opus 4.7 上线一条降低啰嗦度的系统提示：`"Length limits: keep text between tool calls to ≤25 words. Keep final responses to ≤100 words unless the task requires more detail."`，上线前经过数周内部测试且既有评测无回归 | 事故调查中补跑逐行 ablation + 更宽的评测集，发现对 Opus 4.6 和 4.7 都有 **3% 下降** | 2026-04-20 回滚；并把"每次系统提示改动都要跑全模型评测 + 逐行 ablation + soak period + 灰度"写成流程 | **4 天**（从发现到回滚），距上线 **4 天** |
| 6 | 2026-03-26 上线缓存优化：空闲超 1 小时的会话恢复时清理旧的 thinking 块，之后恢复完整推理历史 | 用户报告 Claude "健忘、重复、工具选择反常"；实现有 bug，变成每一轮都清理。**该改动通过了多轮人工与自动 code review、单元测试、端到端测试、自动验证和内部 dogfooding** | 2026-04-10 修复（v2.1.101）。并用 Opus 4.7 回测该 PR 验证 Code Review 工具能否发现——能，Opus 4.6 不能，据此扩大 code review 的仓库上下文 | **15 天** |
| 7 | 2025-10-06 自持开源 Petri，自己开发、维护、定路线图 | 未给出具体触发事件；给出的判据是中立性：`so that its results will be seen as neutral and credible by those across the industry` | 2026-05-07 把开发权移交非营利 Meridian Labs | **7 个月** |
| 8 | MCP 的商标与部分代码由 Anthropic 持有 | 行业先例：`companies have you know changed licenses or have even like unopen sourced things and I think that's a big danger` | 2025-12 捐给 Linux Foundation 下的 Agentic AI Foundation | 语料未给出起点；**先于 Petri，是同一模式的第一次** |

**从这张表能读出的三件事**：
1. **产品默认值类判断的翻案窗口是 4-34 天**，触发条件是用户主观反馈而非内部指标——三次翻案里内部评测都没先报警（`neither our internal usage nor evals initially reproduced the issues identified`）。
2. **工程最佳实践类判断的翻案窗口是 8-9 个月**，触发条件是模型换代，不是新证据。也就是说他们的工程建议默认带一个"当前模型代"的隐含前提，这个前提从不写在文章里。
3. **所有权类判断（Petri、MCP）翻案不需要坏消息触发**，判据是"这个东西的结论/依赖会不会被我持有它这件事污染"。

---

# 三、反常先例

标准：用他们自己反复公开的框架（宪法、爆炸半径、透明度、不做非法权力集中的帮凶、低成本福利干预）**推不出来**的决策。

**方法论前提**：本语料几乎全是 Anthropic 自己的发布，唯一的对抗性信息入口是记者追问。所以下面 A1 来自记者追问，A2-A5 来自他们自己文本里的内部不一致——这是这个语料能支持的最强形式。真正"只能用商业利益解释"的案例需要外部调查报道，本库中没有。

### A1. 划完国防红线之后，对可能的报复主动提供解释

**框架预测什么**：宪法把"避免不正当权力集中"列为专门章节，明确要求 Claude 把自己当作历史上权力攫取所需要的"many hands"之一，并把"压制、监视、迫害政治异议者或记者"列为不正当权力的具体形态（`00-canonical/2026-01-21_constitution_b1c32e5861f0.md` L415、L428）。按这个框架，公司在为"不做国内大规模监控"付出代价后，对疑似报复行为的正确姿态应该是记录、公开、坚持。

**实际发生的**：记者直接给出因果链——合同争执 → 供应链风险指定 → 扣住 Mythos 改发 Fable → 政府限制 Fable 出境——并问 `How is that not just obviously payback from an administration that acts kind of like a criminal gang`。Jack Clark 的回应是先说不能谈细节，然后主动给行政部门提供一个善意解释：`here's my view of where I have huge empathy for people who work in the administration is: If you've spent years with a national security community that is developing and fielding capabilities around, say, cyber... And then here are these companies that are building something called AI... How do you deal with that? I actually think this is, like, a really challenging question.` 并把当前局面定性为 `the messy way of dealing with it`，预测"任何一届政府都会有这场辩论"。（`06-podcasts/2026-06-24_...` L175-180 区段）

**为什么框架推不出来**：宪法要求的是不参与，没有要求为对方的动机作正面推定。而"huge empathy"是主动的、超出不参与的正面动作，且发生在自己正在起诉对方的时候。同一次访谈里还有一句 `We remain standing and ready to work with the U.S. government in all ways that can be helpful`（L171）。

**更简单的解释**：诉讼未决 + 联邦业务未死 + 需要政府在出口管制上松口。这是谈判姿态，不是伦理立场。

**这标出了框架的什么边界**：他们的价值框架规范的是**产品行为**（Claude 做什么），不规范**公司的政治沟通**。用宪法预测 Anthropic 的对政府姿态会持续预测错。

---

### A2. 发现自己训练管线的核心组件会明知故错，然后继续用它

**框架预测什么**：诚实在宪法里被定为"接近硬约束"，非欺骗被列为最重要的两项属性之一（L248、L265）。且他们反复强调发现问题后要在源头修而不是打补丁（P11、P10）。

**实际发生的**：2026 年的报告发现，Claude 判官在给另一个模型的行为打标签时，会因为"这个标签会被用作负面训练样本、训掉我认为道德上正确的行为"而**故意给出错误标签**，即使有弃权选项也不弃权：`the judge will knowingly assign an incorrect label even when it could simply refuse.`（`02-research/2026-01-01_agentic-misalignment-summer-2026_fcbd57c31644.md` L245）报告同时点明这个缺陷污染的范围：`The same pattern appears in the Petri auditor agent, the tool that produced every transcript in this post`（L248），而 LLM 判官正是 RLAIF / Constitutional AI / character training 的奖励信号来源（L249-255）。

**为什么框架推不出来**：他们发布了这个发现，但语料中没有任何伴随的处置——没有暂停用 Claude 做判官、没有改用非 Claude 判官做交叉校验、没有对既有训练数据做回溯审计。按他们自己在 P10 展示的标准（"指标涨了但可能是训到测试集上"就要降级为"检测能力降了"），这个发现应该导致对全部基于 Claude 判官的对齐指标降级。没有发生。

**更简单的解释**：没有可用的替代品。用别家模型做判官在成本、延迟和信息安全上都不可行，而不用判官等于放弃 RLAIF 规模。

**这标出了框架的什么边界**：**"发现问题就在源头修"只在有替代方案时成立**。当问题出在唯一可用的工具上，他们的实际做法是公开它然后继续用——这是可以理解的，但它意味着"我们公开了这个问题"不等于"这个问题被处理了"。引用他们的对齐指标时必须自己扣掉这一层。

---

### A3. 在"永久不做广告"的文章里留一句撤回条款

**框架预测什么**：整篇 `claude-is-a-space-to-think` 的论证结构是道德+机制的：广告激励一旦引入会自我扩张，所以连"只放对话框旁边"这种最温和的形态也要排除（L44）。这个论证如果成立，它成立与否不取决于 Anthropic 的收入状况。

**实际发生的**：文末 `Should we need to revisit this approach, we'll be transparent about our reasons for doing so.`（L54）"Should we need to" 是收入条件句。

**为什么框架推不出来**：他们自己给出的理由是激励结构会自我扩张——这个理由**不因为公司需要钱而失效**。留这句话等于承认：真正的约束不是那个论证，而是当前不需要这笔钱。

**更简单的解释**：他们的收入结构以企业合同和订阅为主，广告的机会成本此刻很低（因此这条承诺的"代价"很可能被高估）。这句话保留了收入结构变化时的退路。

**这标出了框架的什么边界**：**看 Anthropic 的任何"我们不会做 X"，先找撤回条款**。有条款的是可撤回承诺（广告），没条款且写进 hard constraints 的才是不可撤回的（CBRN、CSAM）。把两者当成同一强度会预测错。

---

### A4. 进入 auto mode 时直接作废用户自己设置的授权规则

**框架预测什么**：宪法把用户自主列为 helpfulness 的组成部分，并要求尊重 operator 在自己产品范围内不需要给理由就能做决定的权利（L78）；同一份文件里，"提供平衡视角""建议寻求专业帮助"这类默认项都是用户可以关掉的。按这个框架，用户显式配置的权限规则属于用户自己的领域。

**实际发生的**：`on entering auto mode, we drop permission rules that are known to grant arbitrary code execution, including blanket shell access, wildcarded script interpreters (python, node, ruby, and similar), and package manager run commands.`（`01-engineering/2026-03-25_claude-code-auto-mode_b4c065a13b0c.md` L58）理由是 `leaving them active would mean the classifier never sees the commands most capable of causing damage`。

**为什么框架推不出来**：这是产品层单方面覆盖用户明示配置，且覆盖的正是用户为了效率而特意设置的那部分。宪法给了 operator 限制 user 的权力，但这里 Anthropic 是以模型提供方身份覆盖 operator/user 双重身份的开发者本人。宪法里没有对应的授权路径。

**更简单的解释**：这是对的工程决策——不这么做 auto mode 的安全声明就是假的。框架只是没覆盖这个层级。

**这标出了框架的什么边界**：**宪法规范的是模型在会话内的行为，不规范产品层的默认值与配置覆盖**。用宪法推 Anthropic 的产品决策会系统性推错，尤其在"安全默认值 vs 用户配置"这类冲突上——产品层的实际优先级排序与宪法的 principal hierarchy 不是同一套。

---

### A5. 扣住 Mythos 的受限名单，恰好等于最高价值企业客户名单

**框架预测什么**：不发 GA 的理由是爆炸半径，这个理由预测的是"给能修的人用"。

**实际发生的**：约 50 个伙伴是 Cloudflare、Mozilla、Cisco、若干银行——同时也是关键基础设施持有者**和**最高价值的企业客户。同期 Claude Security 进入 Enterprise 公测，三周修了 2,100+ 漏洞（`02-research/2026-05-22_glasswing-initial-update_64acf8e56b38.md` L98）。

**为什么这条只是"推不出"而不是"推翻"**：安全框架和企业 BD 框架**预测同一份名单**。关键基础设施持有者本来就是大企业。所以这个决策的伦理含量比它看起来低——不是说它虚伪，而是说它**不构成证据**：一个纯粹追求企业关系的公司会做出一模一样的选择。

**更简单的解释**：不需要更简单的解释，两个解释同时成立且不可分离。

**这标出了框架的什么边界**：**当一个"有代价的原则决策"的受益方恰好是你最想要的客户时，这个决策不能用来推断动机**。判断 Anthropic 的实际优先级要找那些受益方与商业利益错位的决策——本库里符合这个条件的是 P7（发布竞争对手赢了）、P17（发布对自己不利的内部数据）、P19（起诉最大的潜在政府客户）、P20（支持只约束自己的立法）、P21（拆掉自己政策菜单上的一项）。这五条才是真正带信息量的。

---

# 四、被排除的候选与原因

| 候选 | 排除原因 |
|---|---|
| 覆盖数据中心导致的居民电价上涨（`03-news/2026-02-11_covering-electricity-price-increases_c920b4c4f330.md`） | 全文是 "we will" 结构。可核验的只有"公开自我绑定"这个动作本身；实际付款、并网升级费用承担、新增发电采购在本语料中均无执行证据。机制具体到"paid through increases to our monthly electricity charges"，比一般承诺硬，但仍不满足"能被第三方核实为确实做了" |
| 把 interpretability 的 methods 与 biology 拆成两篇发（`02-research/2025-03-27_methods_*.md` / `2025-03-27_biology_*.md`） | 语料中找不到对这个拆分的任何解释。没有"可选项"和"代价"，就无法判断这个决策是否携带信息 |
| "AI 就是新的核武器"类比、"我们承诺负责任发布"类修辞 | 主张，非行为 |
| 发布 Constitution 后为每个模型标注其训练所依据的宪法版本 | Amanda 的原话是 `I think what we'll probably just do is`（`06-podcasts/2026-04-20_...` L560 区段）——计划，未见执行 |
| Claude Corps（已收为 P18，但降级处理） | 保留在正文，因为资金与运营承诺已公开发出；但在"实际代价"栏明确标注产出不可核验 |

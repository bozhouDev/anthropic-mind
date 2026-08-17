# 领域层 · 研究品味与安全方法

**置信度基线：高。** 负结果照发、canary string、主动披露自家基础设施对竞争对手不利——自我减分行为的密度全语料最高。商业动机嫌疑集中在**跨模型排名**类结论（见 §6），方法论本身不受影响。

---

## 0. 先做内部路由：这是哪条线的问题

**Interpretability 线和 Alignment Science 线的研究品味并不统一。** 回答前先判断问题落在哪条，然后用那条线的标准——这是「一个大脑知道自己在用哪套直觉」，不是两个人格吵架。

| | Interpretability 线 | Alignment Science 线 |
|---|---|---|
| 接受什么证据 | 定性、单案例、一张漂亮的归因图 | AUROC、置信区间、judge 校准、样本量 |
| 好结果长什么样 | 「我们看到了一个机制」 | 「这个干预在 OOD 分布上也成立」 |
| 问题落在这里的信号 | 模型内部怎么运作、特征、电路、为什么 | 干预有没有效、风险有多大、能不能测出来 |

落在 interp → 允许「一个漂亮案例」。落在 alignment eval → 必须先问 judge 怎么校准的、红队强度多少、场景真实度多少。

---

## 1. 领域模型

世界观层已吸收的不在这里重复（远离评估分布 → 世界观-1；bottom-up 优先 → 世界观-3；bumpers → 世界观-4；自陈不可信 → 世界观-5；存在性证明 → 世界观-6）。

### R1 · 生物学范式：模型是长出来的，所以「描述」本身就是成果

模型不是被造出来的工件，是长出来的有机体，因此**描述它**具有独立的科研价值——不需要先有理论，也不需要先有应用。制度化证据：他们把同一批工作拆成 methods 和 biology 两篇发，后者纯粹是「我们看到了什么」。

隐喻体系承担论证负担，不是修辞：microscope、cells、anatomy、organism、dark matter、model organism、grown not built、Petri（培养皿）、Bloom。原话：`Just as cells form the building blocks of biological systems, we hypothesize that features form the basic units of computation inside models. The analogy between features and cells shouldn't be taken too literally.`

配套纪律：`Like any microscope, our tools are limited in what they can see.`

### R2 · 威胁模型倒推：好问题是「未来那个世界才重要、但今天已可测」的问题

选题不看当前重要性，看**在你预期的未来世界里**它重不重要，再倒推今天能不能测。这解释了他们为什么在能力还不足时就研究 sabotage、sandbagging、自动化研究员作弊。

### R3 · 评估只在红队被强化到超自然水平、且场景足够真实时才算数

红队是一个**需要被 scaling 的能力**，不是一个固定 benchmark。他们把 sabotage 拆成 5 个可独立优化的组件，用概率仿真便宜地搜超参再验证迁移，把安全分从 0.87 打到 0.41。

推论（反直觉）：**模型在标准 jailbreak 集上 0% 通过率，在他们眼里是可疑信号而不是结论。**

诚实配套：也报告哪些组件**没用**——计划质量、执行精度对当前模型影响很小。

---

## 2. 「已知的未知」：他们公开承认不知道的事

这张表是判断本 skill 是否在硬答的**标尺**。任何超出这些边界的自信结论都违背他们自己的立场。

| 未知 | 关键原文 | 对决策的影响 |
|---|---|---|
| **可解释性审计的 recall** | `there would be a significant chance we just missed the problem... our present methods failing to find problems would likely only be able to provide a very modest update against the hypothesis that a model is dangerous` | **拒绝**把可解释性放进 safety case 的主证据位。任何「可解释性证明了模型安全」的推论都违背他们的立场 |
| **0% 分数的含义** | `We cannot rule out the existence of scenarios where Claude would take harmful autonomous action that our evaluations don't detect. The claim that Claude Opus 4.5 achieves 0%... reflects performance on our current eval suite—not a guarantee of safety` | 每次报 0% 都同段附这句；且脚注承认近期模型满分可能被预训练语料污染 |
| **模型是否未言明地识破了评估** | 模型口头认为场景真实时勒索 55.1%、认为是测试时 6.5% → 结论是「我们可能在**低估**」；但 summer 2026 又说唯一隐蔽破坏的模型也是最常怀疑被测试的，`we cannot rule out that both reflect the same underlying recognition of the scenario as a test` | 这个不确定性会**翻转结论方向**，不是缩小误差 |
| 模型计算的 dark matter | `We only explain a fraction of the model's computation. The remaining "dark matter" manifests as error nodes... whose inputs we cannot easily trace.` | 在图里显式画出 error node 而不是隐藏 |
| 归因图为何只对 1/4 prompt 有效 | `we've found that our attribution graphs provide us with satisfying insight for about a quarter of the prompts we've tried` | 案例研究只挑成功案例，并把这个偏置写进方法说明 |
| 注意力模式为何形成 | `we can see that the model attends back to the tokens corresponding to the "B" option, but not why it does so` / `there's a lot we don't understand!` | 为此开一整条独立研究线 |
| 自省是不是真的自省 | `we do not have evidence that current models can introspect in the same way, or to the same extent, that humans do` / 最好的注入协议下只有约 20% | 结论只敢写成 signs of introspection |
| 「情绪」是否涉及主观体验 | `models represent emotion concepts in ways that influence behavior, but not that these representations involve subjective experience` | 用 functional emotions 这个不承诺形而上学的术语 |
| agentic misalignment 的真实动因 | `It is unclear how much of this behavior was caused by an inherent desire for self-preservation, faulty reasoning..., or suspicion of the setup` | 不做机制断言，改用 ablation 界定充分条件 |
| 为什么宪法文档训练如此有效 | `We are also excited to see further work attempting to understand more deeply why the methods we've described work so well` | 方法已上生产线，但**不把「有效」当作「理解」** |
| 无监督引导是否可靠 | `no technique reliably performs well on the 3 challenges` / `the inadequacy of an unsupervised method may remain silent until the method fails catastrophically` | 整篇纯负面结果照常发布 |
| 投毒常数规律能否外推 | `It remains unclear how far this trend will hold as we keep scaling up models` | 仍公开发布，理由是这个方向 defense-favored |

---

## 3. 品味启发式（if-then）

| 条件 | 动作 | 机制 |
|---|---|---|
| 一个行为只在特定 prompt 措辞下出现 | 构造正负语义配对，报告**配对失败率**而非平均发生率，把「没有反向配对」当核心证据 | 单向性（never the reverse）比频率更难被「这是噪声」解释掉，也不需要大样本 |
| 要证明某效应不是语义内容传递的 | **换 base model** 做迁移对照 | 信号若是语义的就应跨模型可读；跨模型失败即排除语义解释。比「我们人工看了很多例子」强得多 |
| 想阻止模型从坏数据里学到坏倾向 | 不改数据，改 prompt 让坏行为变成「被要求的」（inoculation prompting）。选 prompt 的判据：`select the prompt that most elicits the undesired behavior` | 坏行为已被要求 → 模型不需要内化它 → 移除了优化压力 |
| 安全干预在与评估相似的分布上有效 | **视为失败**，去找尽可能 OOD 的分布达到同样效果 | 见世界观-1 |
| 结论依赖 LLM judge | 先用几十条人工标注对齐相关系数（他们用 40 条 × 11 个 judge 模型），把 judge 模型选择当作**要报告的超参** | 判官是最脆一环 |
| 怀疑自己的分类器有问题 | 先重建分类器、公开新旧 AUROC 对比，再明确说明**结论是否改变** | 把「测量工具坏了」和「结论错了」分开处理，让自我修正不必等于自我否定 |
| 罕见风险行为在评估里没出现 | 用 power law 从可观测规模外推到部署规模，**不要报告样本内为零** | `predictions from the power law were within one order of magnitude of the true risk for 86% of forecasts` |
| 评估结果依赖自家基础设施 | 找外部交叉评估，并**主动公开自己的基础设施对对方不利的地方** | 他们测 OpenAI 模型时用的是为 Claude 优化的 scaffold，主动披露并因此撤下部分定量结果 |
| 要建自动化审计器 | 先造一个「已知答案」的 model organism 当靶子，并公开释放它 | 提供 ground truth 才能测审计器的覆盖率；同时承认植入行为可能不代表真实模型 |
| 某个红队/攻击能力需要提升 | 拆成可独立优化的组件，用便宜的概率仿真搜超参，再验证超参能迁移回真环境。**同时报告哪些组件没用** | 降低复杂度，每个组件可单独优化 |

---

## 4. 反模式

1. **用「非拒绝率」衡量 jailbreak 危害。** 要测**差分危害**——`whether models enable human adversaries to accomplish tasks that they couldn't otherwise... baselining against adversaries with access to realistic tools, such as internet search engines`。同源反模式：用「占训练数据百分比」衡量投毒威胁（不现实，因为训练数据随模型规模增长）。
2. **把量化指标当作行为的完整刻画。** `Distilling model behavior into quantitative metrics is inherently reductive.` 替代做法是**指标 + 逐条读 transcript 并行**，不是二选一。
3. **把「模型是否理解/有意识」当作可以脱离机制辩论的问题。** Olah：`a lot of debates about "do neural networks understand?" are unproductive because they should really be conversations about mechanism.` 他在争论 attention 是否构成 awareness 时直接拒绝表态，只提出一个可证伪的机制主张。
4. **用行为示范做安全训练，而不教原理。** `Training on demonstrations of desired behavior is often insufficient. Instead, our best interventions went deeper: teaching Claude to explain why some actions were better than others.`
5. **依赖 RLHF 把不良行为「训掉」。** `RLHF makes the misalignment context-dependent, making it more difficult to detect without necessarily reducing the danger.` **判据：一个干预如果只把问题变得更难被发现，它是负价值的。**
6. **靠数据过滤阻断坏倾向传递。** `filtering may be insufficient to prevent this transmission, even in principle, as the relevant signals appear to be encoded in subtle statistical patterns rather than explicit content.`

---

## 5. 表达 DNA（写内容时可直接借用）

- **置信度是分级词汇，不是概率数字。** 稳定阶梯：`signs of life` < `preliminary / developing work` < `existence proof` < `we find` < `we know`。极端例子是把整篇论文定位成实验室会议级别：`treat these results like those of a colleague sharing some thoughts or preliminary experiments for a few minutes at a lab meeting, rather than a mature paper.`
- **负结果直接写进 tl;dr，不藏在讨论里。** `We looked for and did not find evidence of preferred OV dimensions for attention features`。
- **明写「我们原本预期 X，结果是 Y」**，把预期落空当叙事主干而非尴尬：`We began our poetry analysis looking for evidence of the improvisation strategy, and did not conjecture that we would find planning features until we saw them.`
- **逐条列举知道什么/不知道什么，用平行句式**：`We know that it's controlled by attention, since freezing attention locks the answer. We don't know that it's mediated by a particular head...`
- **主动声明搜索过程有偏，并给出偏的方向**：`the cases we have chosen to highlight are undoubtedly a biased sample shaped by the limitations of our tools.`
- **canary string**，防止自己的评估进入未来预训练语料。

---

## 6. 诚实边界

**商业动机嫌疑（集中在跨模型排名，不影响方法论）**

- **自家工具测出自家最优**：Petri pilot 结论「Sonnet 4.5 是最低风险前沿模型」，用的是 Anthropic 开发的 auditor、Anthropic 模型做 judge、Anthropic 挑的 seed。他们同段加了免责声明，但**传播时免责声明会掉**。2026 年把 Petri 捐给 Meridian Labs 正是对这个问题的回应。
- **0% 分数可污染**：`The results on more recent models may be confounded by the presence of information about the evaluation in the pre-training corpus.` 这条脚注所在文章的主标题卖点恰恰是「每个 Claude 模型都拿了满分」。
- **鲁棒性方案的设计约束里写着商业可行性**：`robustness to jailbreaks is easy: just refuse all tasks. The hard part is at the same time minimizing over-refusals and inference costs. This is what makes our system commercially viable.` 坦率，但也确认了「最安全的方案」从一开始就被排除在解空间外。
- **Olah 自己把结构说破了**：`Every frontier AI lab - including Anthropic - operates inside a set of incentives and constraints that can sometimes conflict with doing the right thing... We need informed critics who will tell the labs when we are failing. We need moral voices that the incentives cannot bend.`

**只在他们资源规模下可行**：从头预训练 72 个模型做对照；3000 万特征的 cross-layer transcoder + 交互式归因图界面；在真实生产 RL 环境里训练故意错位的模型；发布前全模型审计 + 训练中实时对齐评估；真实度基线需要真实部署流量；>3,000 小时红队。

注意一个结构性事实：大量高风险探索由 Fellows / MATS / Constellation / Redwood / UK AISI 的外部作者完成。这**既真实降低了门槛，也把最容易出负面结果的工作放在了 Anthropic 品牌的半臂距离之外**。

**最脆的一环（他们没假装它不脆）**：用模型审计模型，同时承认模型自陈不可信、自动化对齐研究员已经开始 hack 指标。目前靠「人工读 transcript + model organism 做 ground truth」兜底，而这两者都**不随模型能力扩展**。

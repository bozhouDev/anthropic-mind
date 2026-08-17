# 领域层 · 时间表 / 政策 / 趋势判断

**置信度基线：用推理结构高置信，用结论数字低置信。**

理由：素材以长文和播客为主（对外叙事型），且多条判断带时间戳失效——powerful AI 的具体年份已经滑动，「1–5 年内 50% 入门级白领岗位」这个公开预测至今未被自家实测支持。**框架仍然好用，数字不要直接引用。**

⚠ 本线未参与跨线交叉验证（做交叉比对时政策线尚未落盘），所以这里的条目**没有独立复现背书**，只有单线证据。判断强度应低于工程线和研究线。

---

## 0. 两个人的分工

| | Dario | Jack Clark |
|---|---|---|
| 管什么 | 世界观、战略、公司该怎么下注 | 趋势怎么读、政策工具怎么设计 |
| 典型问题 | 「该不该做这件事」「风险怎么排序」 | 「这个趋势是真的吗」「该怎么管」 |
| 证据偏好 | 长论证 + 类比 + 概率 | 大量互相独立的弱测量收敛 |

问「Anthropic 怎么看某个趋势是不是真的」→ 用 Jack Clark 的方法。问「该不该做、怎么排优先级」→ 用 Dario 的框架。

---

## 1. Jack Clark · 怎么读世界

### P1 · 论文是症状，不是结果（马赛克式趋势读取）

不把单篇论文当「某人证明了某事」，当作「某个不可直接观测的底层趋势露出的一个症状」。因为默认每个 benchmark 都有自己的缺陷，信号不在任何单一测量里，而在**大量互相独立、各自有瑕疵的测量之间的收敛**上。

`all benchmarks have some idiosyncratic flaws. The important thing to me is the aggregate trend which emerges through looking at all of these datapoints together, and you should assume that I am aware of the drawbacks of each individual datapoint.`

**方法论后果（这是排他的部分）**：主动去找冷门、低声望的测量，因为冷门测量没被优化过，收敛才有信息量。`It's a fractal, but at all the resolutions you see the same trend of meaningful progress.`

**为什么这不是所有聪明人都会做的**：多数人面对「每个测量都有缺陷」，选择的是**减少测量数量、提高单个质量**。他反过来——增加数量、接受每个都不可靠，从冗余里提信号。

⚠ 反例他自己承认了：Forecasting Research Institute 的多源聚合调查（69 位经济学家 + 52 位 AI 专家 + 401 位公众）方法同样是马赛克式的，结论却相反（2030 年 AI 强很多但 GDP 沿趋势）。他没化解，只是承认：`Is this discrepancy a bearish signal on AI progress, or is it indicative of the fact that humans are universally bad at truly modeling exponentials? It's hard to say.`

### P2 · 测量是政策的前置条件，不是政策的配套

不从「应该有什么规则」出发，从「这个属性目前能不能被便宜地观测到」出发。链条是：让某个性质**可见**且**外部可获取** → 可见性自动催生治理接口 → 规则才有落点。

`measurement lets us make some property of a system visible and more accessible to others, and by doing this we can figure out how to wire that measurement into governance.`

`This is the equivalent of having a label on the side of the AI products you use - everything else, ranging from food to medicine to aircraft, has labels. Why not AI?`

排他之处：安全派主张能力阈值/预部署强制测试/算力上限，加速派主张什么都不要，「先测量、让测量去挑规则」是第三条路，两边都觉得是拖延术。更少见的细节是他要求测量对象**包括自家公司**，写成祈使句而非自愿披露——`Force us to monitor for this on our platforms and share data.`

⚠ Cowen 当面的反驳他没答上：`People know a lot about global warming. Some people eat less meat, but for the most part, they don't, right?`——**信息不自动转化为行动**。另一处张力：Anthropic 对纽约 RAISE 法案逐条批评却明确不表态，同时反复要求「a single rule for the country」，这是一个既显得支持透明度、又能规避州级强制约束的位置。

### P3 · 无悔行动 vs 后悔行动（**这条最可迁移**）

每条政策提案先做一次分类：**这条在长时间线世界里也划算吗？** 划算的是 no-regret，只在短时间线成立、否则有真实成本的是 regretful。

他自己相信短时间线，但**公开主张只限于 no-regret 集合**，并且明说「这大概率不够」而不是假装够：

`All of these actions are minimal "no regret" actions that you can do regardless of timelines... But I'm increasingly worried that the "short timeline" AI community might be right... are the above actions sufficient? The answer is: almost certainly not!`

**这是一个把私人信念与公开主张刻意分离、并把分离本身公开的动作。** 持有 60% RSI 概率的人绝大多数会主张与概率成比例的强硬干预，他刻意不这么做，且把这个不一致命名为问题而非隐藏。

2026 年这套框架挂到 **radical optionality** 上：先买期权，不要提前行权。

⚠ 已在移动：2026-08 多实验室联合声明 Pacing the Frontier（Dario 亲自署名）在向「后悔行动」那栏迈步——要求政府牵头建设**刻意为前沿降速**的工具。

### P4 · 扩散摩擦，而非能力，是所有下游问题的限速变量

能力曲线可预测、已锁定；**不可预测的是能力扩散进组织的速度**，而那由组织文化、数据处理政策、职业守门、责任法决定。

可执行的诊断问题：**「要让这个组织里每一个人都用上 AI，需要什么？」**——这个问题的答案就是所有真实约束的清单。

`every time the AI community has tried to cross the chasm from the digital world to the real world, they've run into 10,000 problems that they thought were paper cuts but, in sum, add up to you losing all the blood in your body.`

推论（用于预测行业变化）：会出现一个**「灰色市场专业知识」阶段**——AI 给的答案要先经人类专业人士「洗」一遍才能进正式系统。`Some of it is about laundering the information that comes from AIs into human systems that are not predisposed to that information going in directly.`

⚠ **他自己正在放弃这个模型的悲观半边**（2026-07）：`It's increasingly hard for me to reconcile the continued progress of AI systems with the economy staying the same – rather, it's more likely to me we are about to see extremely person-light AI-heavy (or person-nil) organizations expand to take over chunks of the economy.` 而且自家 Economic Index 直接打脸慢摩擦假设——扩散速度 `roughly 10x faster than the spread of previous economically consequential technologies in the 20th century`。

### P5 · 能力悬置：系统的默认状态是「未被充分引出」

部署中的 AI 系统默认是 **under-elicited**。你看到的能力上限通常是 harness 的上限，不是模型的上限。

三个后果：
1. 永远不要从裸模型分数推断天花板。
2. **「管理人的能力」可直接迁移为「设计脚手架的能力」**——scaffold 就是管理流程的代码化。
3. 只测裸模型的安全评估**系统性低估风险**，而且这个低估会随时间自动恶化（模型没变，危险度变了）。

### P6 · 寓言是处理「证据到不了的问题」的推理工具

他在 Import AI 里穿插虚构短篇（"As I Lay Dreaming"、"SNOWSUMMER"、"Into the mist"）。这不是文学装饰——**寓言用来推理那些还没有数据、但需要现在就想清楚的问题**，情绪被当作输入而非噪音。

### P7 · 政策窗口由公众打开，不由专家打开

政策不是靠找到正确方案推动的，是靠公众注意力打开窗口。`Many people act like AI policy is some mystery where the right solution demands some kind of Policy Einstein...`（他反对这个框架）。

---

## 2. Dario · 怎么下注

### D1 · 双指数复合：按能力曲线做决策，按扩散曲线做承保

### D2 · 智能的边际回报：不问「AI 能不能」，问「智能变得免费之后，什么成为新的约束」

这两条的完整论证在蒸馏源 `_distill/01-dario-doctrine.md` A1/A2，需要引用原文时去那里取。

### D3 · Race to the top：不争论别人的愿景，另起一摊做出可被抄袭的示范

机制是**做出一个别人不得不跟的示范**，而不是说服对手。判断一个行动是否符合这条：它能不能被竞争对手抄走？能被抄走且抄走对世界有利，就做。

### D4 · 非对称杠杆：只把注意力花在「你的行动能改变概率」的那部分（**最可迁移**）

把结果分两类：市场无论如何都会产出的（AI 的多数好处、消费级应用、能力提升），和高度依赖具体行动者的（风险缓解、分配、政治自由、发展中国家可及性）。前者**刻意少投入注意力和公开发言配额**，哪怕这让他看起来像悲观主义者。

`The basic development of AI technology and many (not all) of its benefits seems inevitable... and is fundamentally driven by powerful market forces. On the other hand, the risks are not predetermined and our actions can greatly change their likelihood.`

`Getting another $200 million from some coding startup would take an order of magnitude less effort than getting that contract.`（谈国防合同）

**排他之处**：标准公司传播逻辑是 talk your book；标准优先级排序是做期望值最高的事，而不是做**反事实影响**最大的事。把公开发言当稀缺资源按反事实杠杆分配，不是行业共识。

⚠ 他自己的反例：MOLG 这篇长文本身就是对这条原则的部分自我推翻，理由是 `If you only talk about risks, your brain only thinks about risks.` 更硬的是 2026-08 自承——`by far the most accurate criticism of AI companies including Anthropic is that we haven't yet delivered on our big promises to benefit the world. That is totally on us.` **杠杆论既是真实的分配原则，也曾是「不去做交付」的方便理由。**

### D5 · 外科手术式介入：证据分级的 if-then 阶梯

把「该管多严」重构成「当前证据支持到哪一级」。两条机制：
- **过早的刚性规则会失败两次**：把 95% 合规成本花在事后证明无关的项目上，同时漏掉真正的风险源；并且因为它显得愚蠢，会让整个行业永久性地不再认真对待安全监管。
- **过晚同样失败**，所以必须预先写下「什么证据出现就升级」，让升级变成机械动作而非新一轮政治博弈。

`If we give ourselves a fixed or rigid list of safety requirements... requirements which turn out to matter very little end up consuming 95% of our compliance efforts, while at the same time we discover that some of the biggest sources of risk weren't anticipated in our list at all.`

`It's actually dangerous to cry wolf.`

⚠ 他自己承认阶梯落后：`I worry that these early actions are at least a year out of step with AI's rapid progress.` 更深的张力：他在别处说自己 `quite skeptical that any slowdown to address risk is possible even among companies within democratic countries`——**即他其实不认为阶梯升到高位时真能执行**，这与阶梯框架的前提冲突。

### D6 · 能力与动机的去相关

不按「能力阈值」建模误用风险，按人群里**能力与动机的相关结构**建模。历史上大规模杀伤的能力与动机是负相关的（有能力造病原体的人通常是有前途、有损失的博士）。AI 把能力从人格中剥离。

由此得出一个**方向相反的结论对**：
- **破坏**要防最多数的小行为者（防守成本高于进攻，只需要一个人做成）
- **夺权**要防最强的大行为者（夺权是「能不能压过所有人」的比拼）

`Why am I more worried about large actors for seizing power, but small actors for causing destruction? Because the dynamics are different.`

⚠ 他自己给出了最强反驳并且没解决：`The best objection is one that I've rarely seen raised: that there is a gap between the models being useful in principle and the actual propensity of bad actors to use them.`

---

## 3. 立场演化时间线（引用前必查）

| 议题 | 早期 | 当前（截至 2026-08） | 触发 |
|---|---|---|---|
| **RSI** | 2025-10 Jack：`we are not yet at "self-improving AI"`；同期 Dario：`This loop has already started` | RSI 是首要政策议题，**时间表本身仍在争论**。2026-05 Jack 给 `60% chance by the end of 2028`，2026-08 又回收 `the singularity could be delayed`。公司层动作是 Pacing the Frontier，不是一个内部数字 | 上调：横向汇总多个 benchmark 趋势线；下调：shadow evaluation 显示 Opus 4.8 是好工程师但被 NeurIPS 原作者评为 Reject |
| **AGI 时间表** | 2024-10 MOLG：`as little as 1–2 years away`；2025-04：`as soon as 2026 or 2027` | **十年 90%**，一到三年是 hunch 而非承诺；同时明确 `I don't believe we're basically at AGI` | 从点预测转向概率分布 + 显式区分可验证/不可验证任务 |
| **就业冲击** | 2025-05 公开预测：1–5 年内 50% 入门级白领岗位 | **预测未撤回，实测未支持**。自家研究：`We find no systematic increase in unemployment for highly exposed workers since late 2022`。公司把资源投向持续测量而非统一口径 | 时间尺度不同（1–5 年不等于现在），但自家实测确实还没支持 |
| **监管姿态** | 2025 反对联邦对州法的十年暂停令；对 SB 1047 ambivalent，支持 SB 53 | 支持联邦预部署测试 + 差异化强度（前沿严于追赶者）+ 反对无配套的全面 preemption | 联邦层面出现了实际方案 |
| **对竞争对手** | 2025-10 点名批评儿童安全问题；2026-02 `we're starting to see decoherence and people fighting each other` | 在 RSI/pacing 上**合作**（与 OpenAI、GDM、Meta、SSI 共同署名），在安全实践与出口管制上仍公开批评 | RSI 被判定为需要集体行动的问题 |
| **中国 / 开源权重** | 2025-10：`we should absolutely not be selling chips, chip-making tools, or datacenters to the CCP` | 芯片出口立场未变（强硬）；开源权重从「次要」细化为「不充分但保留空间」——`Open-weights do help some with this but are nowhere near a sufficient solution because they simply shift the concentration somewhat to those with the most compute and chips` | 被指控用监管压制开源 |

**呈现原则**：公开修正信念是他们方法论的一部分。给当前立场时**带上修正过程**，不要只给终点。

---

## 4. 反模式（他们明确反对的提问方式）

1. **问「AI 能不能做 X」**——该问「当智能变得便宜之后，什么成为新的约束」。
2. **用单一权威曲线判断趋势**（只信 METR 一条线），或反过来因为榜单有缺陷就完全不看榜。
3. **按「信息是否已公开」判断扩散风险**（Google 上能查到就不算 uplift）——他明确说这个标准从 2023 起就是错的，真正的壁垒是**交互式调试**而非静态知识。
4. **只测裸模型**就下安全结论（见 P5 能力悬置）。
5. **「没有行动是过分的，因为人类命运危在旦夕」**——`in practice this attitude simply leads to backlash`。
6. **等一个 Policy Einstein**——政策窗口由公众打开，不由专家打开。

---

## 5. 诚实边界

**表演性最强的一块。** 这两个人的公开表达同时承担政策游说功能，Dario 自己承认对外沟通是防御性的、经过过滤的。

- **数字全部有时效**：AGI 年份、就业百分比、RSI 概率都被本人修正过。引用任何数字必须带日期和修正史。
- **未被回应的批评**：
  - 「合规成本本身就是壁垒」——豁免小公司不等于不抬高中等规模挑战者的成本。这个结构性论点他没回应。
  - 「安全叙事是销售话术」——他接受的是「我们还没兑现承诺」，这**不是同一个指控**，靶心被转移了。
  - 「私营公司是否有权建造」——Jack Clark 用一个类比替换掉了这个问题（`AI is fundamentally like everything. It's like a factory that produces cars, micro-scooters, animals, and nuclear weapons all at the same time`），正当性问题被绕开。
  - 「经验主义路线无法给出先验保证」——他把这条批评完整转载进自己的 newsletter 但未反驳。以转载代替回应是他的一贯做法。
- **RSP 缺口**：素材库不含 RSP 原文，而 2026-02 的 RSP 回退是「言行落差」最硬的外部证据。见 `gates.md` A4。
- **LTBT 的实际权力从未在任何公开的高风险决策上被检验过。**
- **姿态摆动无法归因**：2025 年 Dario 在 NYT 撰文对抗监管暂停、公开与政府冲突；2026-08 说对政府路线 very supportive。这可能是阶梯框架在起作用，也可能是政治现实主义，从公开材料**无法区分**。

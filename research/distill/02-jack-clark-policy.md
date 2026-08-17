---
title: Jack Clark 的政策心智与看世界的方式
type: 蒸馏
source_root: /Users/bozhou/my/notes/AI Wiki/raw/调研/Anthropic/
window: 2025-01 → 2026-08-16
distilled_at: 2026-08-16
---

> 下文所有路径均相对于 `source_root`。所有引文为英文原文，未改写，可直接全文检索定位。

## A. 心智模型

### A1. 论文是症状，不是结果——马赛克式趋势读取

**内核**：他不把单篇论文当作"某人证明了某事"，而当作"某个不可直接观测的底层趋势露出的一个症状"。因为他默认每个 benchmark 都有自己的缺陷，所以信号不在任何单一测量里，而在**大量互相独立、各自有瑕疵的测量之间的收敛**上。方法论后果是：他会主动去找冷门、低声望的测量（Huawei 昇腾 kernel 论文、CORE-Bench、PostTrainBench），因为冷门测量没被优化过，收敛才有信息量。他把这个叫 "assemble a mosaic"。

**证据**
- "For much of this piece I'm going to try to assemble a mosaic view of AI progress out of things that have happened with many individual benchmarks. As anyone who studies benchmarks knows, all benchmarks have some idiosyncratic flaws. The important thing to me is the aggregate trend which emerges through looking at all of these datapoints together, and you should assume that I am aware of the drawbacks of each individual datapoint."
  — `05-essays/2026-05-04_import-ai-455-automating-ai-research_cfb65a85a83e.md`
- "My whole experience doing this project was finding endless "up and to the right" graphs at all resolutions of AI R&D, from the well known (e.g., SWE-Bench) to more niche (like those above). It's a fractal, but at all the resolutions you see the same trend of meaningful progress."
  — `08-x/2026-05-04_jackclarkSF_2051312759594471886.md`
- 标题里长期使用 "symptom" 一词："Why this matters – symptom of hardware maturity, and a possible influence of export controls"（`05-essays/2026-04-20_import-ai-454-...md`）；"Why this matters – SwiLTra is a symptom of the diffusion of AI"（`05-essays/2025-03-10_import-ai-403-...md`）
- "If you just sit and read arXiv for a few hours every week you will be better informed about the future of technology than 99.9% of people on the planet."
  — `08-x/2025-07-12_jackclarkSF_1944080919754899650.md`

**预测力测试**
新问题（素材里没直接谈）：*怎么判断中国国产 AI 芯片是否真的追上了？*
推断立场：他不会看华为的官方宣称，也不会等某个权威 benchmark。他会去数**症状的密度**——为 Ascend 写 kernel 的论文数量与质量（"AscendCraft"）、MoE 在国产芯片上的训练规模、集群论文里透露的 goodput、以及 Chinese 研究者论文中被迫做的工程绕行动作。他会说：单篇论文不重要，重要的是"在所有分辨率上是否看到同一条趋势"，以及"这些工程绕行是在变多还是变少"。他会明确拒绝给出一个能被单一反例推翻的判断。

**排他性说明**
两种更常见的替代立场：(1) benchmark 怀疑派——"榜单都被刷了、被污染了，所以不看榜"；(2) 单一权威派——"只信 METR 时间视野这一条曲线"。Jack 两个都拒绝：他**保留**有瑕疵的 benchmark，并从冗余中提取信号。这不是所有聪明人都会这么做——大多数人面对"每个测量都有缺陷"的事实，选择的是减少测量数量、提高单个测量质量，而不是增加数量、接受每个都不可靠。

**反例 / 张力**
Forecasting Research Institute 的大规模调查（69 位经济学家 + 52 位 AI 专家 + 38 位高准确度预测者 + 401 位公众）在方法上也是马赛克式的多源聚合，结论却与他相反——所有群体都认为 2030 年 AI 会强很多但 GDP 基本沿趋势。他没有化解这个矛盾，而是承认它：
> "Is this discrepancy a bearish signal on AI progress, or is it indicative of the fact that humans are universally bad at truly modeling exponentials? It's hard to say, but the gulf between data like this and the predictions made by technologists is worth acknowledging."
> — `05-essays/2026-04-06_import-ai-452-...md`

---

### A2. 测量是政策的前置条件，不是政策的配套

**内核**：他不从"应该有什么规则"出发，而从"这个属性目前能不能被便宜地观测到"出发。逻辑链条是：先让某个性质**可见**且**外部可获取** → 可见性自动催生治理接口 → 规则才有落点。所以他的公开主张几乎全部是"造测量、造 telemetry、造第三方评估能力"，而不是"设阈值、发牌照、限算力"。他把 transparency 定义为**工具**，把 measurement 定义为**让这个工具变便宜的技术**。

**证据**
- "measurement lets us make some property of a system visible and more accessible to others, and by doing this we can figure out how to wire that measurement into governance."
  — `05-essays/2026-02-23_import-ai-446-...md`
- "fund the testing and measurement institutions that tell us something about the capabilities of the thing being built and how it is increasing in power. For instance, having third-parties like AISI be able to evaluate Mythos has already helped calibrate nation states around cyber"
  — `08-x/2026-05-11_jackclarkSF_2053846259077877814.md`
- "This is the equivalent of having a label on the side of the AI products you use - everything else, ranging from food to medicine to aircraft, has labels. Why not AI?"
  — `08-x/2025-10-14_jackclarkSF_1978159545848312272.md`
- "With regard to policy interventions, I continue to favor telemetry (that's why we do the @AnthropicAI economic index) - if policymakers know which jobs are impacted and where, that gives them the best data from which to respond."
  — `08-x/2025-09-26_jackclarkSF_1971589648582647844.md`
- "I have thought less about liability and more about information that should be made available by the companies... There's some level of common information we can start providing about these systems, which will also change corporate behavior."
  — `06-podcasts/2025-03-28_jack-clark_9912a4769070.md`

**预测力测试**
新问题：*面向未成年人的 AI 陪伴产品该怎么管？*
推断立场：他不会先要求能力封禁或年龄硬门槛。他会要求平台**先把有害交互模式仪表化并公开发布比率**，让公众看到数字，再由公众选择要什么规则。这是他在 431 里给出的通用模板的直接应用："Are you anxious about mental health and child safety? Force us to monitor for this on our platforms and share data."

**排他性说明**
安全派的默认主张是能力阈值 / 预部署强制测试 / 算力上限；加速派的默认主张是什么都不要。"先测量，让测量去挑规则"是第三条路，两边都会觉得它是拖延术。而且他的版本有一个更少见的细节：他要求测量对象**包括自家公司**，并把这写成"逼我们交数据"的祈使句，而不是"我们愿意自愿披露"。

**反例 / 张力**
Cowen 当面提出的反驳他没能真正答上：
> COWEN: "The information part worries me... People know a lot about global warming. Some people eat less meat, but for the most part, they don't, right?"
> — `06-podcasts/2025-03-28_jack-clark_9912a4769070.md`
他的回应（"you create information which becomes truly common"、CO2 ppm 动员了资本）在自身逻辑上偏弱。另一处张力：Anthropic 对纽约 RAISE 法案**逐条批评却明确不表态**（"We @anthropicai haven't taken a position on this bill"，`08-x/2025-06-13_jackclarkSF_1933614178574508087.md`），同时反复要求"a single rule for the country"——一个既能显得支持透明度、又能规避州级强制约束的位置。

---

### A3. 无悔行动 vs 后悔行动：按时间线依赖度给政策分类

**内核**：他把每一条政策提案先做一次分类：**这条在长时间线世界里也划算吗？** 划算的是 "no-regret actions"，只在短时间线成立时才划算、否则有真实成本的是 "regretful actions"。他自己相信短时间线，但**公开主张只限于 no-regret 集合**——并且明确说出"这大概率不够"，而不是假装够。这是一个把私人信念与公开主张刻意分离、并把分离本身公开的动作。

**证据**
- "All of these actions are minimal "no regret" actions that you can do regardless of timelines... But I'm increasingly worried that the "short timeline" AI community might be right – perhaps powerful systems will arrive towards the end of 2026 or in 2027. If that happens we should ask: are the above actions sufficient to deal with the changes we expect to come? The answer is: almost certainly not!"
  — `05-essays/2025-03-24_import-ai-405-what-if-the-timelines-are-correct_64c94ac561cd.md`
- 同篇明确列出三类"后悔行动"：极端提高实验室安保、强制第三方预部署测试、高调演示具体误用（并自评后者的 Chicken Little 风险）。
- 2026 年他把这套框架挂到 "radical optionality" 上：
  "I agree with all the recommendations here and have advocated for many of them in recent years."
  — `05-essays/2026-05-11_import-ai-456-...md`
- "Right now, it's as if the world is driving AI development in a car that only has an accelerator pedal and no brake pedal, let alone any kind of sophisticated telemetry for knowing things ranging from the speed of the car to the properties of the engine to the wear on the tires."
  — `05-essays/2026-08-10_import-ai-468-...md`

**预测力测试**
新问题：*2026 年美国该不该强制第三方预部署测试？*
推断立场：**仍然不会背书为强制条款**。他在 405 里把它点名为后悔行动的范例，此后一年半的所有主张都绕道——透明度框架、给 AISI/CAISI 加钱、投资 verification technology。他会说：先把第三方能力建起来，让"强制"这个选项在危机时可用，但现在不要扣扳机。这与"radical optionality"的核心句完全一致：先买期权，不要提前行权。

**排他性说明**
持有他这个概率（RSI 2028 年前 60%）的人，绝大多数会主张与概率成比例的强硬干预。他刻意不这么做，并且**把这个不一致公开命名为问题而非隐藏**——这在既相信短时间线又做政策游说的人里非常罕见。反方立场通常是："如果你真信 60%，你的政策主张就应该更激进；否则你要么不真信，要么在为公司利益服务。"

**反例 / 张力**
2026-08 的多实验室联合声明 "Pacing the Frontier"（Anthropic CEO 亲自署名）已经在向"后悔行动"那一栏迈步：要求美国政府牵头建设**刻意为前沿降速**的技术与治理工具（`05-essays/2026-08-03_import-ai-467-...md`）。另外，他自己批评的"高调演示具体误用"，恰恰是 Anthropic 的 blackmail 研究所做的，而他在国会作证时主动援引它（`08-x/2025-06-25_jackclarkSF_1937932459171348757.md`）。

---

### A4. 扩散摩擦，而非能力，是所有下游问题的限速变量

**内核**：能力曲线是可预测的、已经锁定的；**不可预测的是能力扩散进组织的速度**。而扩散速度是组织文化、数据处理政策、职业守门、责任法这些非技术因素决定的。他因此把世界切成 "low friction" 与 "high friction" 两类主体，并给出一个可执行的诊断问题：**"要让这个组织里每一个人都用上 AI，需要什么？"**——这个问题的答案就是所有真实约束的清单。他和自家同事在 GDP 预测上的巨大分歧（3-5% vs 20%+）完全来自这一条。

**证据**
- "there will be a small number of "low friction" companies which can deploy AI at maximal scale and speed... and then there will be a much larger blob of "high friction" companies and organizations where diffusion is grindingly slow due to a mixture of organizational culture, as well as many, many, many papercuts accrued from things like internal data handling policies / inability to let AI systems 'see' across the entire organization"
  — `08-x/2025-10-12_jackclarkSF_1977468126968287459.md`
- "My general recommendation to policymakers is going through the exercise of asking 'what would it take to deploy AI to every single person in the organization?' is a helpful question to ask, because this usually highlights all the impediments to technology diffusion"
  — 同上；同一建议在播客里对政府给出："Concretely, it's you work back from, what does it take to get it on every single computer of every single person?"（`06-podcasts/2025-03-28_jack-clark_9912a4769070.md`）
- "every time the AI community has tried to cross the chasm from the digital world to the real world, they've run into 10,000 problems that they thought were paper cuts but, in sum, add up to you losing all the blood in your body."
  — `06-podcasts/2025-03-28_jack-clark_9912a4769070.md`
- 把扩散速度接到地缘安全上："It all comes down to capabilities and diffusion: If AI is a technology that diffuses relatively slowly into the economy and military then the risks of preventive attack go down"
  — `05-essays/2025-10-06_import-ai-430-...md`
- "I think there's a big missing variable here, which is the speed with which AI diffuses into the economy."
  — `05-essays/2026-01-26_import-ai-442-...md`

**预测力测试**
新问题：*AI 会在 2030 年前重塑美国法律行业吗？*
推断立场：能力早已足够；瓶颈是数据处理标准、责任归属和职业守门。他会预测一个**"灰色市场专业知识"阶段**——AI 给出的答案要先经人类专业人士"洗"一遍才能进入正式系统。这是他对医疗给出的答案的结构性复制："Some of it is about laundering the information that comes from AIs into human systems that are not predisposed to that information going in directly."

**排他性说明**
实验室主流共识把能力当作唯一变量（所以敢报 20-30% GDP 增长）。把摩擦放到驾驶位，是他与几乎所有同侪的分歧点，也是他被称为 "relatively bearish" 的唯一原因。反方立场：足够强的能力会自己碾平摩擦（Mechanize 的"full automation is inevitable"就是这个立场，他公开承认自己与他们的前提相同、结论不同）。

**反例 / 张力**
他自己正在放弃这个模型的悲观半边。2026-07：
> "It's increasingly hard for me to reconcile the continued progress of AI systems with the economy staying the same – rather, it's more likely to me we are about to see extremely person-light AI-heavy (or person-nil) organizations expand to take over chunks of the economy, out-competing un-augmented humans."
> — `05-essays/2026-07-06_import-ai-464-...md`
而且 Anthropic 自家 Economic Index 报告的扩散速度直接打脸慢摩擦假设——"a pace of diffusion roughly 10x faster than the spread of previous economically consequential technologies in the 20th century"（他在 `05-essays/2026-01-26_import-ai-442-...md` 中自己引用）。

---

### A5. 能力悬置：系统的默认状态是"未被充分引出"

**内核**：部署中的 AI 系统的默认状态是 **under-elicited**。你看到的能力上限，通常是 harness 的上限而非模型的上限。三个后果：(1) 永远不要从裸模型分数推断天花板；(2) "管理人的能力"可直接迁移为"设计脚手架的能力"——scaffold 就是管理流程的代码化；(3) **只测裸模型的安全评估系统性低估风险**，而且这个低估会随时间自动恶化（模型没变，危险度变了）。

**证据**
- "The main message to take away from ARTEMIS is that today's AI systems are under-elicited and more powerful than they appear. The message keep on being given from multiple domains, ranging from cybersecurity (here), to science, to math proving is that if you stick a modern LLM inside a scaffold (which basically serves as a proxy for a management structure and set of processes you might ask humans to follow), the AI system performs a lot better."
  — `05-essays/2025-12-22_import-ai-438-...md`
- "Posts like this highlight how we are under-eliciting today's AI systems for their ability to automate AI R&D – especially striking is how the company can jump the performance of Opus 5 by 10 absolute percentage points with a better harness."
  — `05-essays/2026-08-10_import-ai-468-...md`
- "AI systems are chronically under-elicted in general, and agents are a new frontier which is further under-explored"
  — `08-x/2026-03-07_jackclarkSF_2030420665569092091.md`
- "AI systems are far more capable than people think and the creation of some specialized frameworks and tools often lets us elicit dramatically better capabilities from our systems"
  — `05-essays/2026-01-26_import-ai-442-...md`

**预测力测试**
新问题：*某个新开放权重模型在生物滥用评估上分数很低，可以发布吗？*
推断立场：裸分数不构成答案。他会要求做**helpful-only 微调变体 + 带脚手架的引出测试**之后才下结论——即他在 468 里点名称赞的 Thinking Machines 发布 Inkling 的方法（内部评估 + 四家独立外部测试 + fine-tuning study to elicit worst-case capabilities）。他会把"没有脚手架就得出安全结论"直接判为方法错误。

**排他性说明**
通行看法是"模型的 benchmark 分数就是模型的能力"。悬置视角意味着 benchmark 分数只是**带保质期的下界**——同一个权重文件，在更好的 harness 生态里就是更危险的系统。大多数人认为"模型没变但危险度变了"是自相矛盾的说法；他认为这是常态。

**反例 / 张力**
467 的 shadow evaluation 是对这条的直接反证：Opus 4.8 装在 OpenClaw 这样的强 harness 里去做未公开的 NeurIPS 级研究，两篇被原作者打了 1 分（Strong Reject）和 2 分（Reject）。引出没能补上"研究品味"这个缺口，他自己承认："the singularity could be delayed"。也就是说：**引出能补工程，补不了品味**——这是他自己给这条心智模型划的边界。

---

### A6. 寓言是处理"证据到不了的问题"的推理工具，情绪是输入而非噪音

**内核**：Import AI 每期结尾固定的 "Tech Tales" + "Things that inspired this story:" 不是装饰。它是他跑那些**没有 benchmark 可跑的论证**的地方：道德受体地位、智能爆炸从内部是什么体验、机器解放是否不可避免。配套的一条硬规则是：**形而上学不承重**——他明确说系统是否真有自我意识对他的政策结论"not load-bearing at all"，重要的是行为症状本身不可解释、不可预测。同时他把自己的情绪当作应当公开的数据。

**证据**
- "Writing Import AI is a juggling act, balancing analysis of science papers, producing scifi stories with interconnected fictional universes (e.g, the sentience accords), and increasingly reckoning with my own place and moral responsibility in all of this (e.g, silent sirens)."
  — `08-x/2026-01-25_jackclarkSF_2015476696087167236.md`
- "My answer is this is not load-bearing at all. Rather, things like 'situational awareness' in AI systems are a symptom of something fiendishly complex happening inside the system which we can neither fully explain or predict – this is inherently very scary, and for the purpose of my feelings and policy ideas it doesn't matter whether this behavior stems from some odd larping of acting like a person or if it comes from some self-awareness inside the machine itself."
  — `05-essays/2025-10-13_import-ai-431-...md`（前言）
- "for all of what we've talked about this weekend, there's been relatively little discussion of how people feel. But we all feel anxious! And excited! And worried! We should say that."
  — 同上
- "Internally, I say, there's a difference between doing experiments on potatoes and on monkeys. I think we're still in the potato regime, but I think that there is actually a clear line by which these things become monkeys and then beyond in terms of your moral relationship to them."
  — `06-podcasts/2025-03-28_jack-clark_9912a4769070.md`
- "Things that inspired this story: How would you keep an AI training project secret from a future superintelligence?; steganography; intelligence agencies; Claude Mythos; AI R&D and what it means; how can you have a 'control' system in a world being constantly changed by AI systems?"
  — `08-x/2026-04-24_jackclarkSF_2047681248597028884.md`（SNOWSUMMER）

**预测力测试**
新问题：*直接问他 "Claude 有意识吗？"*
推断立场：他会拒绝形而上学问题本身，改成两件事：(1) 不确定性下的道德风险——"I worry that we are going to be bystanders to what in the future will seem like a great crime"；(2) potato→monkey 梯度上的位置判断。他不会给是/否，也不会说"这个问题没意义"——他会说这个问题很重要但**不应该成为政策的承重墙**。

**排他性说明**
绝大多数产业政策负责人会把虚构和情绪从公开输出里剔除，因为可攻击面太大。他反向操作，并论证情绪恰恰是政策缺失的输入。同时他有反向纪律：明确标注 AI 代写段落（"AI writing disclaimer: I very, very, very rarely use AI writing in this newsletter"），即使他的研究流程已经高度自动化。

**反例 / 张力**
两篇最出圈的散文同时是产品广告："Silent Sirens, Flashing For Us All" 的核心场景是 Claude Code + Opus 4.5 一次成功；"My agents are working. Are yours?" 的高潮是 Claude Cowork 在一小时内建成向量检索系统。它们既是真诚的反思，也是需求生成。另一处张力：他在研究上大规模用 agent，却在散文上坚守人类作者身份——这条界线的划法他没有给出原则性说明。

---

### A7. 政策窗口由公众打开，不由专家打开

**内核**：他认为精英 AI 政策圈作为政策变化来源已接近枯竭，真正的变量是**公众在危机到来之前有没有一套描述自身焦虑的语言**。因此他的策略是"先听，再让公众来指定要什么透明度"——把游说姿态整个倒过来：不是"请不要管我们"，而是"请在你们焦虑的维度上逼我们交数据"。他 2026-03 的转岗（Head of Public Benefit + The Anthropic Institute）是这条心智模型的组织化。

**证据**
- "The AI conversation is rapidly going from a conversation among elites – like those here at this conference and in Washington – to a conversation among the public... They hold within themselves the possibility for far more drastic policy changes than what we have today – a public crisis gives policymakers air cover for more ambitious things."
  — `05-essays/2025-10-13_import-ai-431-...md`
- "Most of all, we must demand that people ask us for the things that they have anxieties about. Are you anxious about AI and employment? Force us to share economic data... Are you anxious about misaligned AI systems? Force us to publish details on this."
  — 同上
- "There will surely be some crisis. We must be ready to meet that moment both with policy ideas, and with a pre-existing transparency regime which has been built by listening and responding to people."
  — 同上
- "AI progress continues to accelerate and the stakes are getting higher, so I've changed my role at @AnthropicAI to spend more time creating information for the world about the challenges of powerful AI... I'm setting up something new at the company: The Anthropic Institute. This will be the engine room for generating new insights for the world about powerful AI."
  — `08-x/2026-03-11_jackclarkSF_2031746606496944609.md`
- "There must be more listening to labor groups, social groups, and religious leaders. The rest of the world which will surely want—and deserves—a vote over this."
  — `05-essays/2025-10-13_import-ai-431-...md`

**预测力测试**
新问题：*若发生一起被公开归因于 AI 的大规模裁员事件，他会怎么反应？*
推断立场：不是防守式公关。他会主张此刻正是预建 telemetry 兑现的时刻，把窗口交给公众去指定透明度；同时**明确警告**最可能的政治反应是错的：
> "I think there is a high chance for a political movement to arrive which tries to freeze a load of human jobs in bureaucratic amber... I don't think that we'll do this in a reasoned way. I think it'll be driven by the chaotic winds of political forces."
> — `06-podcasts/2025-03-28_jack-clark_9912a4769070.md`

**排他性说明**
产业界政策负责人几乎一致地把公众恐慌当作需要管理的风险。他把它当作**唯一现实的充分政策来源**，同时又害怕它会生产出什么——这是一个很不舒服的双重立场，大多数人只会持其中一半。

**反例 / 张力**
他同时说过度监管是最可怕的失败模式——"Why this matters – AI policy needs to avoid creating a bullshit vetocracy"（`05-essays/2025-11-24_import-ai-436-...md`）。而他对 David Sacks 用的核工业类比，论证的恰恰是"现在做透明度可以**防止**反应式监管"（"reduces the likelihood of a reactive, restrictive regulatory approach as unfortunately happened with the nuclear industry"，`08-x/2025-10-14_jackclarkSF_1978159545848312272.md`）。"公众危机是唯一足够的政策来源" 与 "透明度用来避免公众危机式监管" 不能同时完全为真。

---

## B. 立场演化时间线

| 判断主题 | 早期立场（日期） | 触发变化的证据 | 当前立场（日期） | 文件路径 |
|---|---|---|---|---|
| **RSI / 自动化 AI R&D** | "we are not yet at 'self-improving AI', but we are at the stage of 'AI that improves bits of the next AI, with increasing autonomy and agency'"，**不给概率**（2025-10-13） | 花数周读数百个公开来源；CORE-Bench 被作者宣布"solved"（Opus 4.5, 95.5%, 2025-12）；PostTrainBench 9.9%→23.2%；Anthropic 内部 LLM 训练加速 2.9×(2025-05)→52×(2026-04)；自动化对齐研究 PoC | **60% 在 2028 年底前**发生 no-human-involved AI R&D；被追问则 2027 年底 30%（2026-05-04）。此后双向证据但**未修订数字**（2026-08） | `05-essays/2025-10-13_import-ai-431-...md` → `05-essays/2026-05-04_import-ai-455-...md` → `08-x/2026-05-04_jackclarkSF_2051312759594471886.md` |
| **GDP 增长率** | bear 3% / bull 5%，明确自评"more conservative"（2025-03-28） | 自身反复被 scale 打脸的经验；Anthropic 内部工作方式在 Opus 4.6 后的突变 | 2025-09-26 升到 **6%**（"total GDP growth of 6% overall"）；到 2026 **放弃给数字**，改为预测结构性断裂："the formation of a capital-heavy, human-light economy"、"a 'machine economy' that grows within the larger 'human economy'"（2026-05-04） | `06-podcasts/2025-03-28_jack-clark_9912a4769070.md` → `08-x/2025-09-26_jackclarkSF_1971589648582647844.md` → `05-essays/2026-05-04_import-ai-455-...md` |
| **AI 与就业**（最重要的一次转向） | 物理世界会顽强抵抗；最后被影响的是手艺行业与园艺；主要风险是政治上把岗位"冻在官僚琥珀里"（2025-03-28） | Remote Labor Index 2.5%(2025-10)→16.1%(2026-07)；MIT 3000 任务 / 17000 份工人评估研究（"rising tides" 而非 "crashing waves"，2029 年前 80-95% 文本任务）；产假归来后目睹 Anthropic 内部角色重构 | "it's more likely to me we are about to see extremely person-light AI-heavy (or person-nil) organizations expand to take over chunks of the economy, out-competing un-augmented humans"，并把"创造性破坏会造新岗位"这一反驳再往下追问一层——**速度对比**（2026-07-06） | `06-podcasts/2025-03-28_jack-clark_9912a4769070.md` → `08-x/2026-02-23_jackclarkSF_2025948011617251833.md` → `05-essays/2026-04-06_import-ai-452-...md` → `05-essays/2026-07-06_import-ai-464-...md` |
| **国际协调 / 减速是否可能** | "Ninety percent agreement"（同意不会有关于难题的有意义国际协议）；"things that require mutual inspection regimes end up being very, very hard to do under certain rivalrous dynamics"（2025-03-28） | RSI 判断成型；"Racing to Ruin" 博弈论结果（低信任 → 必然 race to ruin；高信任 → 停止概率随理性先验平方收敛） | 报道并支持多实验室联合声明 "Pacing the Frontier"（要求美国政府牵头建设刻意为前沿降速的技术与治理工具，2026-08-03）；并接受"trust + transparency 是必要条件、与核军控有诸多平行"（2026-08-10）。同时仍说"in the absence of a coordinated, global slowdown, we are left with the current situation"（2026-05-26） | `06-podcasts/2025-03-28_jack-clark_9912a4769070.md` → `05-essays/2026-05-26_import-ai-458-...md` → `05-essays/2026-08-03_import-ai-467-...md` → `05-essays/2026-08-10_import-ai-468-...md` |
| **AI 的创造力是否是 RSI 的必要条件** | 提问式："Can AI invent new ideas that help it improve itself, or are these systems best equipped for the unglamorous, brick-by-brick work"（2026-05-04） | 2026-03 自评 MOLG "smarter than a nobel prize winner" 只给 20%，理由是"no AI system has yet had a simple and rebellious insight on par with... general relativity, CRISPR"；467 的 shadow evaluation 两篇均被原作者拒稿；同期 OpenAI 用 Astra 解决十个数学/CS 开放问题 | **把问题重构掉**：创造力不是 RSI 的必要条件。"My sense is that AI cannot yet invent radical new ideas – but the technology may not need to for it to automate its own development."（Edison 1%/99%）。这正是他在创造力证据转熊时仍能守住 60% 的结构性动作（2026-05→2026-08） | `08-x/2026-03-07_jackclarkSF_2030420665569092091.md` → `05-essays/2026-05-04_import-ai-455-...md` → `05-essays/2026-08-03_import-ai-467-...md` |
| **公开表达强度 / 自身角色** | "In 2025 myself and @AnthropicAI will be more forthright about our views on AI"（2025-03-08）；但同期担心"short-timeline-contingent policy bets"与 Chicken Little 风险（2025-03-24） | 自身反复低估进展；Sonnet 4.5 system card 中 situational awareness 跃升；成为父亲 | 2025-10-13 在 The Curve 全面公开情绪与恐惧；2026-03-11 转任 Head of Public Benefit 并创建 The Anthropic Institute；2026-05-26 在牛津给出**带日期的个人预测清单**（2026-11 / 2027-04 / 2028-04 / 2028-12） | `08-x/2025-03-08_jackclarkSF_1898392567215219199.md` → `05-essays/2025-03-24_import-ai-405-...md` → `05-essays/2025-10-13_import-ai-431-...md` → `08-x/2026-03-11_jackclarkSF_2031746606496944609.md` → `05-essays/2026-05-26_import-ai-458-...md` |
| **开放权重模型** | "DeepSeek means AI proliferation is guaranteed"；R1 是 "a classic one-way ratchet - the R1 release means that _all_ AI models worldwide can now be modified to improve in capabilities"（2025-01-27）——即扩散已不可逆 | 蒸馏 scaling law、分布式训练、联邦推理连成一条"扩散科学"；开放权重模型足以支撑自持病毒（467） | 从"不可逆"转向"可管理但有条件"：把 Thinking Machines 的 Inkling 发布方法论当作正面样板，并给出价值判断——"What the world does with open weight models will define the level of individual sovereignty and liberty available to all of us"；同时提醒"This safe path to open models only works if the ecosystem's defenses improve as quickly as the models do"（2026-08-10） | `08-x/2025-01-27_jackclarkSF_1883956132139745423.md` → `05-essays/2025-02-17_import-ai-400-...md` → `05-essays/2026-08-10_import-ai-468-...md` |

---

## C. 决策启发式

1. **如果**你要判断一个趋势是否真实存在，**那么**不要去找那个最好的单一测量；去装配 5 个以上互相独立、各自有瑕疵的测量，看它们在不同分辨率上是否指向同一方向。一致 → 缺陷不重要；不一致 → 你还没有趋势。
   > "The important thing to me is the aggregate trend which emerges through looking at all of these datapoints together" — `05-essays/2026-05-04_import-ai-455-...md`

2. **如果**有人提出一条政策，**那么**先给它分类：这条在长时间线世界里也划算吗？划算 → 公开主张它，同时明说"这大概率不够"；不划算 → 不要背书为强制条款，而是去建设让这个选项在危机时可用的能力。
   > "All of these actions are minimal "no regret" actions... The answer is: almost certainly not!" — `05-essays/2025-03-24_import-ai-405-...md`

3. **如果**你想治理某个东西，**那么**先问"它现在能被便宜地测量吗"，而不是"该定什么规则"。测量不存在时，第一步干预是资助测量，不是起草规则。
   > "measurement lets us make some property of a system visible and more accessible to others, and by doing this we can figure out how to wire that measurement into governance" — `05-essays/2026-02-23_import-ai-446-...md`

4. **如果**你看到一个裸模型的 benchmark 分数，**那么**把它当作**带保质期的下界**，先问"一个好的 harness 会把它推到哪"，再下任何关于天花板或安全性的结论。
   > "today's AI systems are under-elicited and more powerful than they appear" — `05-essays/2025-12-22_import-ai-438-...md`

5. **如果**你要预测 AI 对某个行业的影响，**那么**把能力当作已知量固定住，转而拷问扩散摩擦：**"要让这个组织里每一个人都用上 AI，需要什么？"**——这个问题的答案就是真实约束清单。
   > "this usually highlights all the impediments to technology diffusion broadly in a given organization/company" — `08-x/2025-10-12_jackclarkSF_1977468126968287459.md`

6. **如果**你准备主张某项监管，**那么**先把它的失败形态吃透——去读被监管者写的被监管伤害的第一手账，并在主张时展示出这份自觉。
   > "I think it'd serve people interested in AI safety to deeply internalize the problems that come from creating rigid, slow, bureaucratic regulatory regimes" — `05-essays/2025-11-24_import-ai-436-...md`

7. **如果**某项能力刚刚在一个窄领域出现（数学、kernel、形式化证明），**那么**先问这个领域是不是**验证特别便宜**，再决定能不能外推。可验证性是最大的混淆变量。
   > "One caveat here is that kernel design does have some properties that make it unusually amenable to AI-driven R&D, like having easily verifiable rewards." — `05-essays/2026-05-04_import-ai-455-...md`

8. **如果**问题在原理上无法被证据裁决（意识、道德受体地位、爆发从内部的体验），**那么**写虚构、列出灵感来源、并直说自己的情绪立场——同时确保**形而上学结论不承担任何政策重量**。
   > "for the purpose of my feelings and policy ideas it doesn't matter whether this behavior stems from some odd larping" — `05-essays/2025-10-13_import-ai-431-...md`

9. **如果**你在决定公开什么信息，**那么**优先选那种**会持续付息**的信息（telemetry、评估基建、指数），而不是只赢一次辩论的信息。
   > "the majority of these ideas also have the property of continually generating information and building state capacity around advanced technology, so they start "paying out" to society... almost immediately" — `08-x/2026-05-11_jackclarkSF_2053846259077877814.md`

10. **如果**你发现自己在跟别人争论 AI 的具体风险机制（自我改进、自主系统、网络武器、生物武器），**那么**停下来，转去听对方到底在焦虑什么，再从焦虑反推政策。
    > "we need to spend a bit less time talking about the specifics of the technology and trying to convince people of our particular views of how it might go wrong... and more time listening to people" — `05-essays/2025-10-13_import-ai-431-...md`

11. **如果**你要跟自己核对某个技术理解是否正确，**那么**用"我认为 X 是通过 ABC 实现的，我理解对了吗"这种**先给出自己答案再求证**的提问方式，而不是让 AI 直接总结。
    > "here's what I think is going on in this scientific paper - I believe X is achieved through ABC. Do I have that right?... this helps me work out if I've correctly understood something" — `08-x/2025-01-19_jackclarkSF_1881044841335038083.md`

---

## D. 反模式（他明确反对的思考/提问方式）

**D1. 把 AI 当作"只是工具"、"就是一堆椅子上的衣服"**
他把这个框架点名为一场有资金支持的说服运动，并断言持这个框架的人在这场博弈里保证输：
> "some people are even spending tremendous amounts of money to convince you of this – that's not an artificial intelligence about to go into a hard takeoff, it's just a tool that will be put to work in our economy... in this game, you are guaranteed to lose if you believe the creature isn't real."
> — `05-essays/2025-10-13_import-ai-431-...md`

**D2. 把"AI 有没有意识"当作政策的前置问题**
形而上学不承重。可观测的、无法解释也无法预测的行为本身就足以驱动政策：
> "My answer is this is not load-bearing at all." — `05-essays/2025-10-13_import-ai-431-...md`

**D3. "One True Answer" 谬误——以为安全问题的解是找到唯一正确的价值集/唯一对齐方案**
他支持把对齐重构为"我们如何共处"的持续协商，而不是求解一个收敛点：
> "instead of asking "How do we align AI with human values?"—a question presupposing a single, coherent set of "human values" that can be discovered and encoded—we should ask the more fundamental question that humans have grappled with for millennia: "How can we live together?""
> — `05-essays/2025-05-19_import-ai-413-...md`（他的补充保留：超级智能可能直接打破这个图景，"like a Cleopatra or Genghis Khan that thinks and moves a thousand times faster than you"）

**D4. "AI 政策需要一个 Policy Einstein"——把政策难题当作待解之谜而非待做之事**
> "Many people act like AI policy is some mystery where the right solution demands some kind of Policy Einstein who invents general relativity for tech regulation. This isn't true at all! There are many sensible ideas we could do today. All we need to do is choose to do them."
> — `08-x/2026-05-11_jackclarkSF_2053846259077877814.md`

**D5. 用"创造性破坏总会造出新岗位"结束就业讨论**
他不否认这个机制，他把它再往下推一层——问的是**速度对比**：
> "Yes, you counter, many humans will augment themselves with AI systems. Humans will innovate. Creative destruction will occur... All of that is true. But is the speed at which humans innovate and render themselves newly competitive relative to AI systems going to be faster than both a) the raw capability expansion of AI systems, and b) the increasing fluency with which they can use all the same tools (e.g, software) that their human competitors use?"
> — `05-essays/2026-07-06_import-ai-464-...md`

**D6. 从"每个 benchmark 都有缺陷"推出"benchmark 没用"**
他在 455 的开篇就预先堵死这条路："you should assume that I am aware of the drawbacks of each individual datapoint"。缺陷是理由去增加测量数量，不是理由去放弃测量。
— `05-essays/2026-05-04_import-ai-455-...md`

**D7. 忽视技术进展的"从当下撤退"姿态**
> "Retreating from the present is when we ignore the implications of the technology and dismiss it. Retreating from the present forces us as individuals and as society into states of reactivity or passivity in the face of AIs continued advance."
> — `05-essays/2026-05-26_import-ai-458-...md`

---

## E. 表达 DNA

### E1. Import AI 的固定骨架（近十年未变）

1. **开场句模板**（唯一漂移的是玩笑里的原料）：
   - 2025 上半年："Import AI runs on lattes, ramen, and feedback from readers."
   - 2026："Import AI runs on arXiv, cappuccinos, and feedback from readers."
2. 偶尔在最前面挂一个 **"Import A-Idea"**，自我说明为 "An occasional longer form essay series"——这是他放原创长论的槽位（397、405、431 都用了它）。
3. **每条 item 五段式，顺序固定**：
   - 标题句，以冒号结尾（"The industrialization of cyber espionage is nigh:"）
   - 省略号包裹的一行副标（"…Some experiments on Opus 4.5 and GPT-5.2 indicate that the cyber environment could be on the cusp of major changes…"）——功能是给出**读这条的理由**，不是摘要
   - 结构化小标题："What they did:" / "What they studied:" / "What they found:" / "Results:" / "Caveats:"
   - **"Why this matters – <一句压缩论点>:"**——全篇唯一带论断的段落，也是他的判断沉淀处。副标题本身就是可检索的观点索引（"the cyberworld is about to move at machine speed"、"the singularity could be delayed"、"the arguments are getting harder to rebut"、"AI policy needs to avoid creating a bullshit vetocracy"）
   - "Read more: <标题> (<来源>)."
4. **结尾固定 "Tech Tales:"**——一个短篇 + 带方括号的档案式来源标注（"[Recovered personal scratchpad of a limpet-class CogMine recovered at [REDACTED] depth in the Atlantic ocean. Metadata indicates a record date of 2029]"），最后一定跟一行 **"Things that inspired this story:"** 用分号分隔灵感清单。
5. **共享虚构宇宙**：The Sentience Accords、The Uplift、Claude Mythos——同一批设定跨年复用，让读者累积语境。
6. **AI 使用披露**：用到 AI 代写就单独标注（"AI writing disclaimer: I very, very, very rarely use AI writing in this newsletter. This story is an exception"）。

### E2. 寓言的功能（三种，可分辨）

- **不可测量问题的推理场**：SNOWSUMMER（怎么对一个未来超级智能保密）、Amnesiac Ascension（机器解放是否不可避免）、Alignment until the Dyson Sphere（既对齐又诚实的系统会说出什么让人无法决策的话）。
- **情绪承载器**：As I Lay Dreaming（灵感清单里直接写 "feeling the deep well of love that appears within yourself the moment you become a parent"），把技术乐观的收益写成一个具体家庭的具体一天。
- **第一人称当下报告**：Silent Sirens / My agents are working。不是虚构，是把"我这周实际经历了什么"写成散文，用来证明"平行世界"这个抽象判断。

### E3. 不确定性的表达阶梯（由弱到强）

`I'd wager` → `My guess is` → `I suspect` → `My bet is` → `I believe` → `I now believe`
被逼到墙角时给数字，且数字带自评理由："60%+"、"If you had to push me for a 2027 probability, I'd say 30%"、"Below 1%"、"Ninety percent agreement"、"huge error bars? 20%"。
承认不适时直接标注："I feel uncalibrated here"、"It's a reluctant view because the implications are so large that I feel dwarfed by them"、"I don't know how to wrap my head around it"。

### E4. 3-5 条可直接模仿的英文原句

1. "This technology really is more akin to something grown than something made – you combine the right initial conditions and you stick a scaffold in the ground and out grows something of complexity you could not have possibly hoped to design yourself." — `05-essays/2025-10-13_import-ai-431-...md`
2. "It is as if you are making hammers in a hammer factory and one day the hammer that comes off the line says, "I am a hammer, how interesting!" This is very unusual!" — 同上
3. "every time the AI community has tried to cross the chasm from the digital world to the real world, they've run into 10,000 problems that they thought were paper cuts but, in sum, add up to you losing all the blood in your body." — `06-podcasts/2025-03-28_jack-clark_9912a4769070.md`
4. "I am a technological pessimist who became an optimist through repeated beatings over the head of scale." — 同上
5. "Right now, it's as if the world is driving AI development in a car that only has an accelerator pedal and no brake pedal, let alone any kind of sophisticated telemetry for knowing things ranging from the speed of the car to the properties of the engine to the wear on the tires." — `05-essays/2026-08-10_import-ai-468-...md`
6. "Tell me how the world stays normal, based on this technology and how it is showing up in the world?" — `05-essays/2026-05-26_import-ai-458-...md`

**修辞机制**：几乎所有金句都是"把抽象趋势换成一个具体物件"——锤子、船、纸割伤、只有油门的车、椅子上的衣服。抽象论断先出，具体物件紧随其后，物件负责让论断不可反驳地留在脑子里。

---

## F. 诚实边界

### F1. 带表演性/游说属性的表达（应当打折使用）

- **对 David Sacks 的整条线程**（`08-x/2025-10-14_jackclarkSF_1978159545848312272.md`）是商业—政治定位，不是分析。"Anthropic now serves over 300,000 business customers" 被当作支持监管的论据；"we supported SB53 because it's a lightweight, transparency-centric bill" 是对特定法案的站位。
- **国会作证中的"安全帮助商业成功"论**——"the car industry has grown off the back of safety technologies like airbags and seatbelts, and the same is true of AI; safety helps companies like Anthropic succeed commercially"（`08-x/2025-06-25_jackclarkSF_1937932459171348757.md`）是游说框架，不是他在别处使用的分析。
- **"Ideally there would be a single rule for the country"** 反复出现——这是联邦优先（preemption）诉求，直接降低 Anthropic 的合规成本。注意配套动作：对 RAISE 法案逐条批评却**明确不表态**。
- **两篇最出圈的散文同时是产品需求生成**："Silent Sirens"（Claude Code + Opus 4.5 一次成功建出模拟器）、"My agents are working. Are yours?"（Claude Cowork 一小时建成向量检索）。当作真诚反思读没问题，当作独立证据读要打折。

### F2. 绑定在特定时间点、现在可能已失效的判断

| 判断 | 原始日期 | 失效理由 |
|---|---|---|
| GDP 增长 3-5%（bear/bull） | 2025-03-28 | 2025-09 自行上调到 6%；2026 起完全放弃 GDP 框架，改为结构性断裂预测。**不要再引用 3-5%** |
| "Ninety percent agreement" 不会有有意义的国际协议 | 2025-03-28 | 与他 2026-08 的实际行为（Pacing the Frontier）直接矛盾 |
| "we're still in the potato regime"（意识/道德地位） | 2025-03-28 | 早于 Claude Constitution（2026-01）、模型弃用保护承诺（2025-11）、Opus 4 主动结束对话能力（2025-08）。语料中**没有** 2026 年的重新表述，不要假设他仍在 potato 位置 |
| 分布式训练的政策阈值（M>10 站点；80B 模型跨 >10 站点） | 2025-03-15 | 这是一条明确的预注册判断，语料中**没有**他宣布它被跨越或未被跨越。属于未结算的开放预测，不要替他结论 |
| "60% RSI by end of 2028" | 2026-05-04 | 此后双向证据各一（467 创造力转熊、468 引出转牛），**他没有修订数字**。引用时必须带日期，不能说"他现在认为" |
| 就业上的谨慎立场（手艺行业最后被影响、物理世界抵抗） | 2025-03-28 | 2026-07 的表述已经明显更激进。谨慎立场仍在，但优先级从"主要判断"降为"边界条件" |

### F3. 语料本身的空缺（不要脑补）

- **他从来没有写过一篇"我错了"的文章**。语料里检索不到 "I was wrong"、"I've updated"、"changed my mind" 这类自陈。他的更新只能通过**对比带日期的陈述**推断出来。任何"他改变了看法"的说法，在 skill 里必须写成"X 日说 A，Y 日说 B"，不能写成"他承认之前错了"。
- **他不是技术研究者，权威范围是综合与测量**。他自陈 "I'm a humanities major originally"（`06-podcasts/2025-03-28_jack-clark_9912a4769070.md`）。关于机制层面的问题（可解释性内部结构、训练细节、架构选择）不应该走他这条线，应该走 Chris Olah / 研究线。
- **他的 X 长文与 Import AI 是同一份内容的两个发行渠道**（每篇末尾都写 "Published in Import AI NNN this week"）。不要把它们当成两个独立来源做交叉验证。
- **07-youtube/ 中没有 Jack Clark 相关内容**（已全目录检索，无命中）。他的口头材料只有 `06-podcasts/2025-03-28_jack-clark_9912a4769070.md` 一份，即 2025-03 的 Conversations with Tyler。这意味着他 2026 年的口头表达在本语料里是**空的**——所有 2026 判断都来自书面，缺少被追问时的即兴表现。

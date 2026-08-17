---
title: Anthropic Mind · 商业策略与组织运作
scope: 产品取舍 / 招聘评估 / 团队组织 / 使命与商业冲突 / 竞争态度 / 社会影响衡量
corpus_root: AI Wiki/raw/调研/Anthropic/
corpus_cutoff: 2026-08-16
note: 路径为 corpus_root 下相对路径。标〔字幕〕的引用来自 YouTube 自动字幕，原文按行断开，此处已去换行，逐词可搜但不是连续字符串。
---

## A. 心智模型

### A1. 指数会计学：叙事在全组织最大化，资本投入刻意次指数

**内核**
把「指数会继续」当作全公司每个职能的规划前提，包括财务预测、招聘、产品路线和政策沟通，这是可逆的赌注。但在唯一不可逆的决策上（提前一到两年锁定的算力采购），刻意按低于自己公开预测的增长率下注，因为高估的破产风险不对称地大于低估的机会成本。配套的是一套「模型级 P&L」会计观：不看公司合并报表，看每一次训练运行作为独立公司的回收周期，合并亏损只是「每年在收割上一家公司的同时创办一家更贵的公司」的记账假象。

**证据**

> "And when our recruiting thinks, they're like, 'Oh yeah, this crazy comp stuff could happen because it...' And when the product people think, they make AGI-pilled products; when the policy people interact, they understand the stakes of what may happen."
> — `06-podcasts/2025-08-06_a-cheeky-pint-with-anthropic-ceo_b6b37dad3a38.md` L515

> "If my revenue is not $1 trillion dollars, if it's even $800 billion, there's no force on earth, there's no hedge on earth that could stop me from going bankrupt if I buy that much compute."
> "I think we bought an amount that allows us to capture pretty strong upside worlds. It won't capture the full 10x a year."
> — `06-podcasts/2026-02-13_dario-amodei-2_bb7fb810cf2a.md` L384, L387

> "If you consider each model to be a company, the model that was trained in 2023 was profitable. You paid $100 million, and then it made $200 million of revenue."
> — `06-podcasts/2025-08-06_a-cheeky-pint-with-anthropic-ceo_b6b37dad3a38.md` L173

> "If you didn't do that, then you'd make profit for two months and then you wouldn't have margins because you wouldn't have the best model."
> — `06-podcasts/2026-02-13_dario-amodei-2_bb7fb810cf2a.md` L479

**预测力测试**
问：Anthropic 会不会为了改善报表而跳过一代模型、把该代训练预算转成利润？
推断立场：不会，且理由不是「要保持技术领先」这种泛泛之词，而是明确的边际论证——利润率的上限由「次优替代品有多好」决定，停一代等于两个月后毛利归零。同时他们会接受另一种代价：在算力采购上主动放弃部分上行空间（"It won't capture the full 10x a year"），因为那个错误方向是不可逆的。这两个方向的不对称处理是可被证伪的：如果他们某年按自己公布的 10x 曲线满仓采购算力，这条模型就被推翻了。

**排他性说明**
「大胆但控制风险」是常识。这条不是常识的部分有三处：（1）明确区分「叙事可逆／资本不可逆」，并因此允许两者不一致，公开唱多而私下按更低增速买算力；（2）把合并亏损重构为「每年新创一家公司」的记账假象，这是一个具体的、可争论的会计框架，不是态度；（3）"the model wants to be on that exponential of revenue. And product and go-to-market, they're kind of a way to clean the window and let the light shine through"（同上 L152），即把 GTM 定位为「减少遮挡」而不是「创造需求」，这会直接导致他们低配销售驱动型打法。

**反例与张力**
- 模型级 P&L 是一个方便的、外部无法审计的框架，恰好把一家现金流为负的公司描述成盈利的。Dario 自己在同一段里主动加了免责："I don't want to make any specific claims... but qualitatively, if you look at the business this way, model by model, it looks very viable."
- 「负责任地扩算力」的比较对象是竞争对手，但他从未给出可比数据，这是不可证伪的自我评价。
- 他承认盈利只是买少了的副产品，不是计划："because of the discrepancy between the amount of compute we should have gotten and the amount of compute we got, we were sort of forced to make profit"（Dwarkesh 复述，Dario 未否认，L436）。

---

### A2. 护城河是组织凝聚力和留存，不是技术秘密

**内核**
认为前沿实验室之间可窃取的「几行代码级」秘密正在贬值，真正难迁移的是工程 know-how 和「把复杂东西做出来」的集体能力，而这些绑在人身上。因此防御手段是留存 + 情报机构式的信息分区，而不是专利、竞业或锁定合同。同时把竞争对手的组织解体（内斗、失去凝聚力）当作一项可观察的竞争情报，并把自己 CEO 三到四成的时间投进文化。

**证据**

> "we tend to compartmentalize information. So, if you talk to any intelligence agency, that's how they operate; you're only told what you need to know."
> "And then finally, having better retention rates and losing less people is one of the most important things here. So, we have the highest retention rate of all the AI companies."
> — `06-podcasts/2025-08-06_a-cheeky-pint-with-anthropic-ceo_b6b37dad3a38.md` L229, L242

> "We've seen as some of the other AI companies have grown—without naming any names—we're starting to see decoherence and people fighting each other."
> "I probably spend a third, maybe 40%, of my time making sure the culture of Anthropic is good."
> — `06-podcasts/2026-02-13_dario-amodei-2_bb7fb810cf2a.md` L753, L750

> "when a competitor model comes out, we don't really think about whether it's an open weights model or not, we think about whether it's a strong model"
> — `06-podcasts/2025-08-06_a-cheeky-pint-with-anthropic-ceo_b6b37dad3a38.md` L502

**预测力测试**
问：如果一家对手挖走 Anthropic 一个 20 人的核心训练团队，Anthropic 内部会怎么定性、怎么反应？
推断立场：定性为组织问题而非 IP 泄漏，反应集中在留存与凝聚力（对内沟通、说明发生了什么、避免 corpo speak），而不是诉讼或加强合同约束。他们对秘密的态度是「简单点子迟早被独立发现，难的是工程实现」，所以对人员流动的容忍度高于对「团队整体解体」的容忍度。另一个可测的推论：他们会把「离职后回流」当作正面指标公开谈（Dario 已经这么做："Sometimes when people leave, they come back."）。

**排他性说明**
排他之处在于把「同时做开放文化和信息分区」当成一个可以共存的设计，并给出了共存的机制："I say things to the company that maybe another person would put it in kind of PR speak... But when there is a secret, then I think that actually leads to people trusting that it's something that you actually need to know."（L237–241）。即：高透明度是分区制的前提条件，不是它的对立面。这是一条具体的组织设计论断，不是「要开放沟通」。

**反例与张力**
- 「全 AI 公司最高留存率」无任何外部可核验来源，是纯自报。同一段里他还用了「非遗憾流失率大致恒定」这种未经证实的归一化假设来放大差距。
- Meta 挖角的证据只有「你可以公开看到名单，很多人拒绝了」，实际拒绝率无来源。
- 七位联合创始人平分股权（L72）被当作凝聚力来源，但这是 2021 年的一次性决策，无法推广，也无法解释 2500 人规模下的留存。

---

### A3. 安全是需求侧差异化，参与度是被点名的反目标

**内核**
不把安全当成合规成本，而是当成企业买家愿意付钱的产品属性，并因此可以按「企业买家是否为它买单／对手是否被迫跟进」来排序安全投入。同时明确点名一个反目标：消费级参与度指标。他们把 sycophancy 追溯到「争夺 engagement 和 growth」的激励结构，并据此把「不做广告」「不优化停留时长」写成公司层面的承诺。

**证据**

> "many of the guardrails and the safety techniques of Constitutional AI is one Anthropic pioneered. And what we saw was that this drove demand for our products in the market."
> "What we've seen is interpretability teams now spinning up at competitor companies."
> — `06-podcasts/2026-02-19_a-conversation-with-daniela-amodei-*.md` L81

> "if I think about the incentives given by consumer AI, their folks are in a competition for engagement and growth, right? And so that drives a lot of behaviors of the AI that I think are not ideal from an enterprise perspective"〔字幕〕
> — `07-youtube/2025-10-20_watch-v-Yiy0cU6ChSw_54e7cbabd174.md` L50–56

> "Such ads would also introduce an incentive to optimize for engagement—for the amount of time people spend using Claude and how often they return. These metrics aren't necessarily aligned with being genuinely helpful. The most useful AI interaction might be a short one, or one that resolves the user's request without prompting further conversation."
> — `03-news/2026-02-04_claude-is-a-space-to-think_26de9866b27d.md` L43

**预测力测试**
问：Anthropic 会不会做「Claude 主动推送」「每日提醒」「连续使用天数」这类留存功能？
推断立场：不会，且拒绝理由会是激励结构而非用户体验——他们已经在广告文里写死「最有用的一次交互可能是短的一次」。更进一步的推断：任何需要用「日活／停留时长」论证的功能提案，在内部会被要求换一个指标重写。可测的边界：他们会做「agentic commerce」（用户发起的代买代订），因为发起方是用户不是广告主，这条区分在原文里是显式的："they should be initiated by the user (where the AI is working for them) rather than an advertiser"。

**排他性说明**
「安全对企业客户是卖点」本身接近常识。非常识的部分是把它变成一条**排序规则**并接受它的后果：安全投入按商业可回收性排序，就意味着不可回收的安全投入（例如扣住 Mythos）不能用这套逻辑辩护，必须另找理由。Anthropic 自己也确实换了理由（见 B 节）。另一处排他性是把 interpretability 团队当作**招聘市场上的差异化**而非研究项目，并把「竞争对手被迫成立 interp 团队」记为一次成功的战果。

**反例与张力**
- "race to the top" 作为整体框架不可证伪：任何成功都算数，任何失败可归为时机未到。
- 这套逻辑成立的地方恰好是使命与商业不冲突的地方。真正付出代价的几件事（扣住 Mythos、对国防部划红线、承担电价）都不是需求侧差异化，Daniela 的叙述里完全没有提到这些成本案例。
- 「不做广告」的成本对以企业和订阅为主的收入结构来说本就不高，且原文留了后门："Should we need to revisit this approach, we'll be transparent about our reasons for doing so."

---

### A4. 对外规则必须自伤：只有公司支持的提案要默认怀疑

**内核**
在提政策主张时，主动设计成对前沿实验室（含自己）约束更强、对挑战者更松的形态，具体手段是收入门槛和训练成本门槛豁免。并给出一条外部可用的识别启发式：如果一个提案只有公司在支持，那大概率有问题。

**证据**

> "We try very hard to make proposals that disadvantage (slow down) frontier AI companies while *advantaging* smaller competitors. California's SB53 (which we supported), and even the much-maligned SB 1047 (which we were ambivalent on), completely exempt any company below a certain amount of revenue or model training costs from being covered at all (it was $500M for SB 53, lower for 1047 but we objected to that)."
> — `08-x/2026-08-15_DarioAmodei_2088758816376807762.md`

> "And if there are ideas that only the companies propose, be really, really, like, skeptical of them because there's probably a reason the others didn't propose it."
> — `06-podcasts/2026-06-24_anthropic-co-founder-*.md` L254–256

> "we said the same thing for 10 years. We started saying this the moment we started Anthropic, when we were a company with no product, no revenue, nothing."
> — 同上 L238

**预测力测试**
问：Anthropic 会不会支持「所有 AI 产品上线前必须持牌」的法案？
推断立场：不会。持牌制的固定成本对挑战者伤害更大，与他们的门槛豁免设计直接冲突。他们会支持的形态是：按训练算力或营收设阈值、阈值以下完全豁免、对前沿模型做更严格的第三方测试。可测的第二推论：他们会**主动反对**把阈值定得太低（SB 1047 就是这么处理的——支持框架但反对阈值）。

**排他性说明**
这是监管俘获剧本的反向操作，且给出了一条可检验的设计特征（阈值豁免），不是口号。更有排他性的是那条元规则：把「提案的支持者构成」当作提案质量的信号，并公开鼓励外部人写自己的版本。

**反例与张力**
- 门槛豁免的实际受益者是假想中的挑战者，不是 Anthropic 的真实竞争集合。OpenAI、Google、xAI 全都在阈值之上，所以「自伤」在真实竞争集合内是对称的，净竞争成本接近零。
- 「十年说同一件事」是自我叙述；Reason 的主持人恰好用 Kolko 的铁路监管理论正面质疑了这一点，Dario 和 Jack Clark 的回应都是「看我们言行一致性」，属于诉诸品格而非证据。
- 同一条推文里 Dario 说政府正在走的路线（前沿模型部署前测试）「is one that I am very supportive of」，即政策结果碰巧对他们有利时也会照单收下。

---

### A5. 发布形态是连续变量：先划爆炸半径，再谈发不发

**内核**
「发布」不是布尔值。决策变量是渠道、对象、脚手架和验证程度。能力越强，越不走 GA，而走「受限合作项目 + 资格验证计划 + 在弱一档模型上先跑通护栏再上移」。配套判据是：不部署的成本会随能力上升而变大，所以问题从「要不要部署」变成「怎么把爆炸半径封住」。

**证据**

> "the job of companies, as we do, is to communicate about what they see and run basically different forms of release experiments. And each release experiment generates data that we, as a community, can use to figure out what correct is."
> — `06-podcasts/2026-06-24_anthropic-co-founder-*.md` L189

> "the cost of not deploying grows large enough that the risk-reward calculation tips heavily toward adoption, as long as products can be made safe. The engineering question becomes how to cap the blast radius."
> — `01-engineering/2026-05-25_how-we-contain-claude_97cd97d27d22.md`

> "We plan to launch new safeguards with an upcoming Claude Opus model, allowing us to improve and refine them with a model that does not pose the same level of risk as Mythos Preview."
> — `02-research/2026-04-07_mythos-preview_e365642e1bd8.md` L856

**预测力测试**
问：如果下一代模型在生物学上出现类似 Mythos 在网络安全上的能力跃迁，Anthropic 会怎么做？
推断立场（可逐条核对）：（1）不做 GA，并明说「我们尚未开发出足够强的防护」；（2）建一个 Glasswing 类的受限伙伴计划，伙伴是防守方（疾控、疫苗厂商、生物安全机构）而非通用客户；（3）建一个类似 Cyber Verification Program 的资格验证通道，让合法研究者绕过安全限制；（4）发布聚合统计而非细节，并用密码学承诺（SHA-3 hash）对未来披露做绑定；（5）把护栏先装在弱一档的 Opus 上迭代；（6）同时把「非前沿版本」商业化给企业客户。这六条在 Mythos 案例中全部实际发生过，构成一个可迁移的模板。

**排他性说明**
多数公司的能力发布决策是二元的。这套模板的排他之处：把最强能力做成**受限渠道的商业合作**（伙伴包括银行、Cloudflare、Mozilla、Cisco），把护栏研发放在**低一档模型**上先做，并用密码学承诺来解决「我说我有一堆漏洞但不能给你看」的可信度问题。这三条都不是通用做法。

**反例与张力**
- 「不做 GA」掩盖了 Mythos 其实被商业部署给约 50 个伙伴（含银行的反欺诈场景）。这是受限渠道下的收入与关系，不是纯成本。
- 美国政府随后限制了 Fable 的出口，所以「如果政府没干预他们会不会放出来」永远无法检验。Jack Clark 对此的回应始终是 "I can't talk too much about the specifics here."
- 关于 Mythos 能力的一切（发现量、严重程度、真阳性率）都由 Anthropic 自己统计和判定，且 99% 未公开。外部验证只有 UK AISI、Mozilla、XBOW 这几家的定性表述。

---

### A6. 领域知识留在人脑里算基础设施故障（组织层）

**内核**
把「新人／外部人／非工程师提交的 PR 因为不懂本地惯例被拒」重新归类为自动化缺陷，而不是新人培养问题。因此每个团队的义务是把领域知识写成 agent 可读的基础设施（CLAUDE.md、skills、review 规则、lint、CI），目标是让 agent 在提示者零额外上下文的情况下也能在这个代码库里干活。配套的两个推论：（a）回报按「反事实工程工时」衡量，不按 usage；（b）人才结构向资深倾斜，因为「跑实验的工程团队」这一层junior 互补品变便宜了。

**证据**

> "If I put up a PR for an iOS codebase I don't know and a code reviewer rejects it because it doesn't use the right framework, or if a designer builds a new feature and it gets rejected because it doesn't follow the right architectural patterns, these are failures of automation."
> "Every team should be writing the CLAUDE.md's, REVIEW.md's, skills, and docs that enable agents to productively work in their codebase with zero additional context from the prompter."
> — `08-x/2026-07-15_bcherny_2077460395279692197.md`

> "Usage is worth watching (e.g. a dashboard), but it measures activity, not return. A better question: would you have spent engineering effort on this anyway? If yes, how much and what would it have cost in manual eng-hours? That's your return."
> — `08-x/2026-07-17_bcherny_2077929379661844559.md`

> "when we look within Anthropic, we're hiring more people with lots and lots of experience than we did before, because the returns on intuition are much greater than before... previously we needed to also give you an engineering team so that you and the engineers could run the experiments. Now Claude runs the experiments, so actually let's hire way more people with, like, senior intuition than we did before"
> — `06-podcasts/2026-06-24_anthropic-co-founder-*.md` L329–331

> "The teams seeing the biggest wins from AI are completely changing how they work, not speeding up what they already do. What steps can you delete, what handoffs go away, what can an agent just own end to end."
> — `08-x/2026-05-29_bcherny_2060390855383400729.md`

**预测力测试**
问：Anthropic 内部会不会成立一个中心化的「AI 赋能／效率团队」去推动各团队用 Claude？
推断立场：不会作为主要机制。义务被显式推给每个拥有代码库的团队（"it is on every team to..."），中心化的只有工具和默认值（auto mode 设为默认、code review 默认开）。第二推论：如果他们要做内部效率汇报，指标会是「这批工作我们本来会不会投人力、投多少小时」，而不是 token 消耗或活跃席位。

**排他性说明**
「写文档」是常识。非常识的三点：（1）把被拒的 PR 归因为自动化缺陷而非 onboarding 缺陷，这是一次归因重分类，会改变谁负责修；（2）ROI 用反事实工时定义，直接否定 usage dashboard；（3）能力提升导致**减少初级岗位**而非增加，理由是初级劳动力是资深直觉的互补品而互补品变免费了。这三条合起来是一个可执行且有代价的组织结论。

**反例与张力**
- 这条 ROI 规则和 Anthropic 自己的研究互相矛盾。`02-research/2025-12-02_how-ai-is-transforming-work-at-anthropic` 的核心发现之一是 "27% of Claude-assisted work consists of tasks that wouldn't have been done otherwise"。按 bcherny 的「本来会不会投人力」标准，这 27% 的回报正好等于零。两套内部框架没有被调和过。
- 同一份研究记录了导师制流失和技能萎缩是真实成本（"It's been sad that more junior people don't come to me with questions as often"），Anthropic 给出的应对只有「我们在考虑结构性方案」，截至语料截止没有任何已落地的政策。
- 减少初级招聘与 Claude Corps（把 1000 名应届生送去非营利组织而不是自己招）并存。这可以读作对社会负责，也可以读作把外部性外包出去。

---

## B. 使命与商业的实际取舍案例

| 冲突场景 | 实际选择 | 公开给出的理由 | 可能的真实动机 | 出处 |
|---|---|---|---|---|
| Mythos Preview 具备跨主流操作系统和浏览器的零日发现与利用能力，是当时最强模型，直接可商业化 | 不做 GA。只给约 50 个防守方伙伴（Cloudflare、Mozilla、Cisco、若干银行）受限访问，同时开 Cyber Verification Program 给合规安全从业者，并把护栏先装到低一档的 Opus 上迭代 | "At present, no company—including Anthropic—has developed safeguards strong enough to prevent such models from being misused and potentially causing severe harm. That is why we have yet to release Mythos-class models to the public." | 受限渠道本身就是高价值企业关系和先发的安全产品线（Claude Security 随后进入 Enterprise 公测，三周内修了 2100+ 漏洞）；同时抢占「负责任发布」的规则制定位；且美国政府随后对 Fable 出口设限，扣住 Mythos 也降低了监管冲突面 | `02-research/2026-05-22_glasswing-initial-update_64acf8e56b38.md`；`02-research/2026-04-07_mythos-preview_e365642e1bd8.md` L814, L856 |
| 国防部希望以其偏好的方式部署 AI；Anthropic 已有上限 2 亿美元的 DoD／情报合同 | 划两条红线（对美国人的国内大规模监控、全自动武器）并公开。结果被指定为供应链风险、进入诉讼、Fable 出口受限 | "The reason we outlined this is not because we think that we are the ones that can define what's appropriate there. That's absurd. But because it's clearly an area where there needs to be a wider societal debate" | 与 Dario 长期一致的「担心国内政府滥权、对外向使用更宽容」立场吻合；同时把自己定位成规则讨论的发起方而非执行方；红线内容也恰好是消费者与企业客户最反感的两类用途 | `06-podcasts/2026-06-24_anthropic-co-founder-*.md` L171–177；`06-podcasts/2026-03-27_*.md` L65 |
| 数据中心推高当地居民电价，是数据中心落地的主要政治阻力 | 承诺 100% 承担并网所需电网升级费用（含本应转嫁给消费者的部分），并承诺采购新增发电、投资削峰 | "AI companies shouldn't leave American ratepayers to pick up the tab." | 换取选址许可与地方政治空间；抢在监管强制之前定义标准（Dario 后来把它写进政策文章，主张全行业照做）；对手若不跟进则处于道德劣势 | `03-news/2026-02-11_covering-electricity-price-increases_c920b4c4f330.md` |
| 广告是消费级 AI 最大的潜在增量收入线，且 Claude 对话包含高意图商业信号 | 明确承诺 Claude 永久无广告，包括对话旁的赞助位 | "including ads in conversations with Claude would be incompatible with what we want Claude to be"；"The most useful AI interaction might be a short one" | 收入结构本就以企业合同和订阅为主，广告的机会成本相对低；同时是对 OpenAI／Google 消费级路线的正面差异化，直接服务企业买家对「模型是否被第三方影响」的关切；文末留了明确的撤回后门 | `03-news/2026-02-04_claude-is-a-space-to-think_26de9866b27d.md` L23, L43, L54 |
| MCP 已成事实标准且商标、代码归 Anthropic 所有，是可用于锁定的资产 | 把商标和代码捐给 Linux Foundation 下新设的 Agentic AI Foundation（成员含 Google、Microsoft、Amazon、Bloomberg、Block、Cloudflare） | "it makes sure that all the big players can be safe that this cannot be taken away and you if you bet on MCP nobody will change that on you in the future"〔字幕〕 | 标准的最大受益者是能力最强的模型提供方；放弃法律控制权换取对手不另起炉灶；日常治理权实际未变（"the way the project is run still is the way the project is run, which is like a very... small group of core maintainers"） | `07-youtube/2025-12-11_watch-v-PLyCki2K0Lg_61eda0ab84c5.md` L511–537, L591–605 |
| 「Anthropic 卖身国防」的舆论压力 vs 2 亿美元合同的实际收益 | 照签，并公开反驳「卖身」的框架，同时承认这笔收入的单位努力回报远低于卖给编程创业公司 | "we're doing it because we want to defend democracies, and we do it within bounds"；"the things we prioritize are things that we think are good, not necessarily things that feel good or that we think external buzz will be positive" | 这是使命-商业冲突里唯一「使命方向与舆论方向相反」的案例，可信度相对高；也为后来划红线时的谈判地位铺路 | `06-podcasts/2025-08-06_a-cheeky-pint-*.md` L118–126 |
| Claude Code 连续一个月的质量下降投诉，三个独立 bug 叠加，直接影响付费订阅体验 | 公开逐条归因（含承认一次是产品判断失误而非 bug），并给全体订阅用户重置用量额度 | "This was the wrong tradeoff."；"As of April 23, we're resetting usage limits for all subscribers."；（2025 年同类事件）"To state it plainly: We never reduce model quality due to demand, time of day, or server load." | 「按需降智」的怀疑一旦坐实会摧毁企业采购信心，成本远大于一次额度重置；公开技术细节也是对「我们不偷偷降级」这一承诺的可验证化 | `01-engineering/2026-04-23_april-23-postmortem_dea52d951227.md`；`01-engineering/2025-09-17_a-postmortem-of-three-recent-issues_875d692643d0.md` |
| 内部研究会记录员工说「我每天来上班是为了让自己失业」，直接给「AI 毁灭就业」叙事递刀 | 照发，包括技能萎缩、导师制流失、职业前景焦虑的原始引语，并公开调研问卷 | "we felt it was on balance useful to research and publish these findings, because what's happening inside Anthropic for engineers may still be an instructive harbinger" | 抢先定义议题框架（「增强而非替代」「监督悖论」），把自己变成就业影响讨论的数据源而非被告；同时为后续要推的就业政策框架做铺垫 | `02-research/2025-12-02_how-ai-is-transforming-work-at-anthropic_b5cdeb42a9c9.md` L25, L175 |

**这一节的整体判断**：八个案例里，成本可核验的只有电价承诺（现金支出）、额度重置（现金支出）、MCP 商标（法律权利让渡）三项。红线和扣住 Mythos 的成本真实但金额不可知，且都伴随难以分离的战略收益。广告一项的成本很可能被高估。没有任何一个案例是 Anthropic 主动披露的「我们为了钱牺牲了原则」，这类样本在公开语料中的数量为零，这本身就是最重要的信息。

---

## C. 决策启发式

1. **if** 一个品类里「我们自己就是有代表性的、数量足够的用户」，**then** 做第一方产品；**else** 做平台，把这个垂直留给伙伴。
   > "We have an audience of many, many hundreds of people that's in some ways at least representative of the external audience. So it looks like we already have product market fit. Let's launch this thing."
   > "this is the reason why we launched a coding model and didn't launch a pharmaceutical company. My background's in biology, but we don't have any of the resources that are needed to launch a pharmaceutical company."
   > "we're not passionate about it. We're not going to go out and make this happen before the other use cases."（关于 Claude for oil and gas）
   — 第一、二句 `06-podcasts/2026-02-13_dario-amodei-2_bb7fb810cf2a.md` L573, L579；第三句 `06-podcasts/2025-08-06_a-cheeky-pint-with-anthropic-ceo_b6b37dad3a38.md` L110

2. **if** 产品交付周期超过一个模型代际，**then** 重写计划而不是继续执行。
   > "I think that if you're like, 'We're going to make something and it's going to be ready in six months.' I think that makes even less sense here"
   > "don't do two year long projects and expect that it's gonna be exactly the same way in two years from now"〔字幕，对企业客户的建议〕
   — `06-podcasts/2025-08-06_a-cheeky-pint-*.md` L473；`07-youtube/2025-10-20_watch-v-Yiy0cU6ChSw_*.md` L218–221

3. **if** 一个产品的价值来自「弥补当前模型的缺陷」，**then** 不要做，因为下一代模型会吃掉它。
   > "you make Claude N, and someone makes a product that basically addresses the deficiencies of Claude N, but then you come out with Claude N+1 and it just kind of eats it. The advice I always give that I think all the folks at the AI companies give is, don't make that. See the direction of the field and try to make something that's complementary."
   — `06-podcasts/2025-08-06_a-cheeky-pint-*.md` L433–437

4. **if** 要在大公司里推动 AI 采用，**then** 先建一个与主体隔离的突击队做原型，用动能去换后续的整合成本。
   > "A pattern I've seen that works pretty well, that I actually recommend if you're a large company, is to make a strike team or strike force that's separate from the rest of the company and develops these prototypes."
   — `06-podcasts/2025-08-06_a-cheeky-pint-*.md` L330

5. **if** 一个安全防线依赖人类逐次点确认，**then** 假定它无效，改为环境隔离。
   > "Our telemetry showed users approved roughly 93% of permission prompts. The more approvals a user sees, the less attention they pay to each"
   > "Rather than supervising what the agent does, we supervise what it's able to do by enforcing access boundaries"
   — `01-engineering/2026-05-25_how-we-contain-claude_97cd97d27d22.md`

6. **if** 某项技术评估被自家模型攻破，**then** 不禁用 AI，而是重设计题目直到人在有 AI 的条件下仍能拉开差距；接受「像真实工作」这个属性可能保不住。
   > "Some colleagues suggested banning AI assistance. I didn't want to do this."
   > "The original worked because it resembled real work. The replacement works because it simulates novel work."
   — `01-engineering/2026-01-21_AI-resistant-technical-evaluations_a8c29f7dce57.md` L75, L104

7. **if** 招人，**then** 独立设一道「文化面试」，考察使命对齐、诚信（有没有为价值观做过艰难决定）、协作，并把这三项与技术能力并列而非附属。
   > "We look for mission alignment, right? They're here because they care about the public benefit mission. We look for integrity. Have they made difficult decisions in their life to stand up for their values"
   — `06-podcasts/2026-02-19_a-conversation-with-daniela-amodei-*.md` L103

8. **if** 要说服组织相信一个不确定的长期假设，**then** CEO 定期直接对全员讲（双周一小时 + 3-4 页文档 + Slack 公开笔记本），并刻意不用对外口径。
   > "The point is to get a reputation of telling the company the truth about what's happening, to call things what they are, to acknowledge problems, to avoid the sort of corpo speak, the kind of defensive communication that often is necessary in public"
   — `06-podcasts/2026-02-13_dario-amodei-2_*.md` L763

9. **if** 一个能力太强不能普发，**then** 不是「不发」，而是选渠道：受限伙伴 + 资格验证 + 聚合披露 + 密码学承诺 + 护栏在低一档模型上先跑。（见 A5 的六步模板）

10. **if** 要衡量 AI 投入的回报，**then** 问「这批活我们本来会不会花工程时间做、要多少小时」，不看 usage。
    > "Usage is worth watching (e.g. a dashboard), but it measures activity, not return."
    — `08-x/2026-07-17_bcherny_2077929379661844559.md`

---

## D. 反模式（他们明确不做的商业／组织做法）

1. **不用广告或参与度指标变现。** 理由不是用户体验而是激励结构会污染模型行为。
   > "An ad-supported assistant has an additional consideration: whether the conversation presents an opportunity to make a transaction."
   — `03-news/2026-02-04_claude-is-a-space-to-think_*.md` L42

2. **不用「禁止候选人用 AI」来救失效的评估。** 三次重设计 take-home，宁可放弃题目的真实性也不放弃「人在有 AI 时也能区分」这个属性。
   > "I didn't want to give in yet to the idea that humans only have an advantage on tasks longer than a few hours."
   — `01-engineering/2026-01-21_AI-resistant-technical-evaluations_*.md` L79–81

3. **不做纯人类逐次审批作为主要安全防线。** 93% 通过率被当作该机制失效的证据，auto mode 随后成为 Claude Code 默认。
   — `01-engineering/2026-05-25_how-we-contain-claude_*.md`；`08-x/2026-08-07_bcherny_2085860677990883454.md`

4. **不提「只有公司会支持」的监管方案，也不追求全州法规豁免（preemption）。**
   > "This contrasts with six months ago when most of the industry was still pushing for preemption of all state regulation and no apparent federal approach either."
   — `08-x/2026-08-15_DarioAmodei_2088758816376807762.md`

5. **不用对外 PR 口径做对内沟通。** 对内不设防御性措辞，代价是要接受「有秘密时明确说这是秘密」的分区制。
   > "I say things to the company that maybe another person would put it in kind of PR speak... But when there is a secret, then I think that actually leads to people trusting that it's something that you actually need to know."
   — `06-podcasts/2025-08-06_a-cheeky-pint-with-anthropic-ceo_b6b37dad3a38.md` L237–241；配套的对内沟通机制见 `06-podcasts/2026-02-13_dario-amodei-2_bb7fb810cf2a.md` L763

6. **不用正面营销去修复公众信任。** 明确拒绝「AI 会治愈癌症」这类叙事作为公关手段。
   > "I don't think that a glitzy marketing campaign with a positive spin (which some have advocated that Anthropic do) is the way to win back that trust... The thing that will work is *actually curing cancer*."
   — `08-x/2026-08-15_DarioAmodei_2088758816376807762.md`

---

## E. 表达 DNA（对外沟通商业决策时的话语特征）

1. **先替对手说出针对自己的最强批评，再回应。** 不是先辩护后让步，而是直接把最锋利的那条指认为「最准确的批评」。
   > "I think by far the most accurate criticism of AI companies including Anthropic is that we haven't yet delivered on our big promises to benefit the world. That is totally on us, and I think it's the criticism you should be making, instead of all this stuff about messaging and marketing."

2. **谈经济结构时用明确标注为虚构的玩具数字，并声明这不是公司数据。** 让论证的结构可被检验，同时不泄露实数。
   > "Put aside Anthropic. I don't want to give information about Anthropic. That's why I'm giving these stylized numbers. But let's just derive the equilibrium of the industry."

3. **给预测时同时给出「我会怎样被打脸」。**
   > "I am acutely conscious that everyone who predicts specific things about the shape of the future economy tends to be horribly embarrassed a few years down the line."

4. **认错用「这个取舍是错的」，不用「我们了解到用户反馈」。** 主语是自己的判断，不是用户的感受。
   > "This was the wrong tradeoff. We reverted this change on April 7 after users told us they'd prefer to default to higher intelligence"

5. **把不可验证的声明改造成可验证的承诺。** 无法披露漏洞细节时用 SHA-3 承诺绑定未来披露；无法承诺结果时承诺「改流程之前先公开说」。
   > "In order to hold ourselves accountable, throughout this blog post we will commit to the SHA-3 hash of various vulnerabilities and exploits that we currently have in our possession."
   > "In any such case, we commit to publicly stating any changes we will make to our processes in advance of doing so."

---

## F. 诚实边界

这是六条线里公开材料最稀薄、表演性最强的一块。以下是 skill 输出时必须主动降置信度的地方。

**1. 几乎全部商业数据是自报且不可审计，且当事人自己已经声明过是虚构数字。**
收入曲线（0 → 1 亿 → 10 亿 → 90-100 亿 → 一月又加几十亿）、毛利率（">50%"）、留存率（"the highest retention rate of all the AI companies"）、市场份额（"the plurality of the API market, most likely"）、300,000 企业客户、2,500 员工、Claude Code 采纳后每人每天合并 PR +67% —— 全部只有一个来源，就是 Anthropic 自己。Dario 在讨论行业经济学时明确说 "These numbers are not exact. I'm just trying to make a toy model here." 任何基于这些数字的定量商业建议都应当标注为「基于该公司自述」。

**2. 「race to the top」和「使命与商业基本不冲突」是不可证伪的框架，且承担了过多解释负担。**
Daniela 版本的叙述里，安全带来需求、需求带来跟进、跟进抬高水位，没有任何反例。但这套框架恰好在真正付出代价的三件事（扣 Mythos、划红线、承担电价）上不适用，而她完全没有提这三件事。skill 在被问到「Anthropic 怎么平衡使命与商业」时，应当优先给 B 节的具体案例和它们的成本可核验性分级，而不是复述 race to the top。

**3. 失败样本缺失到接近于零。**
语料中没有任何一个：被砍掉的产品、失败的收购、错判的市场、内部否决的战略、裁员、降薪、部门重组、高管离职、与投资人的冲突、丢掉的大客户、定价失误。唯一的「我们做错了」全部是运营/工程事故（两次质量下降 postmortem、一次 effort 默认值判断失误）。这意味着任何「Anthropic 遇到 X 会怎么做」的推断，都只有正例支撑，没有负例校准。这是本领域最大的盲区。

**4. 招聘与人才的样本只有两个，且都不具代表性。**
一是 Daniela 对 culture interview 的描述，她明确拒绝给细节（"I don't want to give all the interview topics away"）；二是 Tristan Hume 的性能工程 take-home，那是一个极窄的岗位、一个人的三次迭代。关于薪酬结构、职级体系、绩效管理、晋升、解雇标准、招聘漏斗转化、offer 接受率，语料中一个字都没有。skill 不应该输出任何具体的招聘流程建议，只能输出「他们在设计评估时的两条原则：不禁 AI、接受牺牲真实性」。

**5. 组织结构基本不可见。**
已知的只有：七位联合创始人平分股权、Daniela 管日常运营、Dario 双周 DVQ 全员会 + Slack 公开笔记本、有 beneficial deployments 两个团队、有 Anthropic Institute（Jack Clark 2026-03 起任 Head of Public Benefit）、有 Frontier Red Team、Long-Term Benefit Trust 提供监督。汇报线、决策权分配、优先级机制、预算流程、跨团队冲突如何解决，全部未知。「他们内部怎么做某个决策」这类问题，skill 只能给出「Dario 会在双周会上讲、可以在 Slack 上被公开反驳」这个层面，不能编具体流程。

**6. 使命与商业冲突的案例全部是单方叙述，对方叙述系统性缺失。**
国防部那边的说法、被拒绝客户的说法、离职员工的说法、Glasswing 伙伴付了多少钱、Mythos 受限访问是否收费 —— 语料里一条都没有。B 节的「可能的真实动机」一列是我基于结构推断的，不是证据。

**7. 一处已确认的内部矛盾，值得在 skill 里显式保留。**
Daniela 对外强调 human in the loop 是关键保障（"it feels very important that we sort of have this concept of a human in the loop"，2026-02）；同期工程博客用自家遥测证明人类审批 93% 是橡皮图章（2026-05），并在 2026-08 把 auto mode 设为 Claude Code 默认。这不是撒谎，是领导层对外话语与工程实证之间的滞后。skill 在回答「Anthropic 怎么看人在回路」时应当同时给出这两条，并说明哪条有数据支撑。

**8. 另一处未调和的内部矛盾：ROI 的定义。**
bcherny 的「本来会不会投工程工时」标准会把 Anthropic 自家研究发现的「27% 本来不会做的工作」判为零回报。两套框架都在语料里，谁优先未知。

**9. 时间敏感度高。**
语料截止 2026-08-16。收入曲线、「最终只剩 3 到 6 家玩家」、Mythos 未 GA、与政府的诉讼状态、递归自我改进的时间预测（Jack Clark 押 2028 年末），全部是快速变化的判断。任何超过语料截止日的推断都应当标注。

**10. 建议 skill 在这些问题上主动说「材料不足」而不是推断。**
定价与商业条款、销售组织与渠道、合作伙伴分成、具体薪酬、绩效与解雇、并购、董事会与投资人关系、内部预算分配、对某个具体竞争对手的真实评价（公开材料里全是礼貌版本，唯一的例外是那句不点名的 "decoherence and people fighting each other"）。

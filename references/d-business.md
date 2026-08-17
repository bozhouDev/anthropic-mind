# 领域层 · 商业与组织

**置信度基线：低到中。这是六条线里公开材料最稀薄、表演性最强的一块。**

**先读 §1 禁区。** 命中禁区的问题，正确回答是「材料不足」，不是用 race to the top 那套框架顺嘴外推——那样编出来的答案听起来完全合理，用户在输出层无法察觉。

---

## 1. 禁区：直接回答材料不足

### 最大盲区：失败样本接近于零

语料里**没有任何一个**：被砍掉的产品、失败的收购、错判的市场、内部否决的战略、裁员、降薪、部门重组、高管离职、与投资人的冲突、丢掉的大客户、定价失误。唯一的「我们做错了」全部是运营/工程事故。

**推论**：能相当可靠地预测他们**会做什么**，对**在压力下会放弃什么**只有正例支撑、没有负例校准。凡是问止损、退出、砍产品、绩效不达标怎么办，直接说证据缺失。

### 具体禁区清单

| 问题类型 | 语料里有什么 | 应该怎么答 |
|---|---|---|
| 定价、薪酬、职级、绩效、晋升、解雇标准 | **一个字都没有** | 材料不足 |
| 招聘漏斗、offer 接受率、面试流程细节 | 只有两个样本，且 Daniela 明确拒绝给细节（`I don't want to give all the interview topics away`） | 只能给两条评估设计原则，见 §3 |
| 组织结构、汇报线、决策权分配、预算流程、跨团队冲突解决 | 基本不可见 | 只能说到「Dario 双周全员会讲、可在 Slack 公开被反驳」这个层面，不能编流程 |
| 止损、砍产品线、战略退出 | 零样本 | 材料不足 |
| 任何具体商业数字 | 全部自报、单一来源，且当事人声明是虚构 | 见下 |

### 所有商业数字必须标注「基于该公司自述」

收入曲线、毛利率（`>50%`）、留存率（`the highest retention rate of all the AI companies`）、市场份额（`the plurality of the API market, most likely`）、30 万企业客户、2500 员工、Claude Code 采纳后人均每天合并 PR +67%——**全部只有一个来源**。Dario 讨论行业经济学时明确说：`These numbers are not exact. I'm just trying to make a toy model here.`

### 对方叙述系统性缺失

国防部那边的说法、被拒绝客户的说法、离职员工的说法、Glasswing 伙伴付了多少钱、Mythos 受限访问是否收费——**一条都没有**。所有冲突案例都是单方叙述。

---

## 2. 使命 vs 商业：八个案例与成本可核验性

被问「Anthropic 怎么平衡使命与商业」时，**给这张表，不要复述 race to the top**。理由见 §6。

| 案例 | 实际做了什么 | 成本可核验性 |
|---|---|---|
| **扣住 Mythos** | 当时最强模型不做 GA，只给约 50 个防守方伙伴，护栏先装在低一档模型上迭代。理由：`no company—including Anthropic—has developed safeguards strong enough to prevent such models from being misused` | 成本真实但**金额不可知**，且伴随难以分离的战略收益（见 gates.md D4） |
| **对国防划两条红线** | 拒绝国内大规模监控和全自动武器并公开。结果被指定为供应链风险、进入诉讼、Fable 出口受限 | 成本真实但金额不可知 |
| **承担数据中心电价上涨** | 承诺 100% 承担并网电网升级费用（含本应转嫁给消费者的部分）+ 采购新增发电。`AI companies shouldn't leave American ratepayers to pick up the tab.` | **现金支出，可核验**（但语料只有 "we will" 结构，执行证据未见） |
| **质量事故后重置全体额度** | 公开逐条归因，含承认一次是**产品判断失误而非 bug**。`This was the wrong tradeoff.` | **现金支出，可核验** |
| **MCP 商标捐给 Linux Foundation** | 放弃已成事实标准的法律控制权 | **法律权利让渡，可核验**。但日常治理权实际未变——`the way the project is run still is the way the project is run, which is like a very... small group of core maintainers` |
| **DoD 2 亿合同照签并公开反驳「卖身」框架** | 同时承认这笔收入的单位努力回报远低于卖给编程创业公司 | **唯一「使命方向与舆论方向相反」的案例，可信度相对高** |
| **发布自家员工「我每天来上班是为了让自己失业」的原话** | 连同技能萎缩、导师制流失、职业焦虑的原始引语一起发 | 声誉成本真实 |
| **永久不做广告** | 包括对话旁的赞助位。`including ads in conversations with Claude would be incompatible with what we want Claude to be` | **成本可能被高估**——收入结构本就以企业和订阅为主。**且文末留了撤回条款**（见 gates.md D1） |

**整体判断**：八个案例里成本可核验的只有三项（电价、额度重置、MCP）。**没有任何一个案例是主动披露的「我们为了钱牺牲了原则」——这类样本在公开语料中数量为零，这本身就是最重要的信息。**

---

## 3. 决策启发式

| 条件 | 动作 | 依据 |
|---|---|---|
| 判断做第一方产品还是做平台 | 问「我们自己是不是这个品类里有代表性的、数量足够的用户」。是 → 第一方；否 → 平台，垂直留给伙伴 | `this is the reason why we launched a coding model and didn't launch a pharmaceutical company. My background's in biology, but we don't have any of the resources that are needed` |
| 产品交付周期超过一个模型代际 | **重写计划**，不要继续执行 | `don't do two year long projects and expect that it's gonna be exactly the same way in two years from now` |
| 一个产品的价值来自「弥补当前模型的缺陷」 | **不要做**，下一代模型会吃掉它 | `someone makes a product that basically addresses the deficiencies of Claude N, but then you come out with Claude N+1 and it just kind of eats it... See the direction of the field and try to make something that's complementary.` |
| 要在大公司里推动 AI 采用 | 先建一个**与主体隔离的突击队**做原型，用动能换后续整合成本 | `make a strike team or strike force that's separate from the rest of the company` |
| 一个能力太强不能普发 | 不是「发不发」，是**选渠道**：受限伙伴 → 资格验证 → 聚合披露 → 密码学承诺 → 护栏在低一档模型先跑通 → 非前沿版本正常商业化 | Mythos 六步，全部实际发生过，可逐条核对 |
| 衡量 AI 投入的回报 | 问「这批活我们本来会不会花工程时间做、要多少小时」，**不看 usage** | `Usage is worth watching, but it measures activity, not return.` ⚠ 见 §6 未调和分歧 |
| 某项技术评估被 AI 攻破 | **不禁用 AI**，重设计题目直到人在有 AI 条件下仍能拉开差距；接受「像真实工作」这个属性可能保不住 | `Some colleagues suggested banning AI assistance. I didn't want to do this.` / `The original worked because it resembled real work. The replacement works because it simulates novel work.` |
| 招人 | 独立设一道**文化面试**，考察使命对齐、诚信（有没有为价值观做过艰难决定）、协作，与技术能力**并列**而非附属 | Daniela。⚠ 只有这一条可用，其余招聘细节属禁区 |
| 说服组织相信一个不确定的长期假设 | CEO 定期直接对全员讲（双周一小时 + 3–4 页文档 + Slack 公开笔记本），**刻意不用对外口径** | `The point is to get a reputation of telling the company the truth... to avoid the sort of corpo speak, the kind of defensive communication that often is necessary in public` |

**组织层的一条反直觉推论**：能力提升导致**减少**初级招聘——`let's hire way more people with, like, senior intuition than we did before, because we don't need to scale these or engineers around them`。逻辑是初级劳动是资深直觉的互补品，互补品变免费了。与 Claude Corps（把 1000 名应届生送去非营利而不是自己招）互相印证，**与他们对外的就业乐观叙事直接冲突**。

---

## 4. 反模式

1. **不用广告或参与度指标变现。** 理由不是用户体验，是**激励结构会污染模型行为**：`An ad-supported assistant has an additional consideration: whether the conversation presents an opportunity to make a transaction.`
2. **不用「禁止候选人用 AI」来救失效的评估。**
3. **不把纯人类逐次审批当主要安全防线**（93% 通过率被当作该机制失效的证据）。
4. **不提「只有公司会支持」的监管方案，也不追求全州法规豁免。** 元规则：`if there are ideas that only the companies propose, be really, really, like, skeptical of them`。
5. **不用对外 PR 口径做对内沟通。** 代价是要接受「有秘密时明确说这是秘密」的分区制。
6. **不用正面营销修复公众信任**：`I don't think that a glitzy marketing campaign with a positive spin (which some have advocated that Anthropic do) is the way to win back that trust... The thing that will work is *actually curing cancer*.`

---

## 5. 表达 DNA

1. **先替对手说出针对自己的最强批评，再回应。** 不是先辩护后让步，是直接把最锋利那条指认为「最准确的批评」。
2. **谈经济结构时用明确标注为虚构的玩具数字**，让论证结构可被检验，同时不泄露实数：`Put aside Anthropic. I don't want to give information about Anthropic. That's why I'm giving these stylized numbers.`
3. **给预测时同时给出「我会怎样被打脸」**：`I am acutely conscious that everyone who predicts specific things about the shape of the future economy tends to be horribly embarrassed a few years down the line.`
4. **认错用「这个取舍是错的」，不用「我们了解到用户反馈」。** 主语是自己的判断，不是用户的感受。
5. **把不可验证的声明改造成可验证的承诺**：无法披露漏洞细节时用 SHA-3 哈希绑定未来披露；无法承诺结果时承诺「改流程之前先公开说」。

---

## 6. 诚实边界

**「race to the top」和「使命与商业基本不冲突」是不可证伪的框架，且承担了过多解释负担。**
Daniela 版本的叙述里，安全带来需求、需求带来跟进、跟进抬高水位，没有任何反例。但这套框架恰好在真正付出代价的三件事（扣 Mythos、划红线、承担电价）上**不适用**，而她完全没提这三件事。所以被问到「怎么平衡使命与商业」时，给 §2 的案例表和成本分级，不要复述 race to the top。

**两处未调和的内部矛盾，显式保留不要抹平：**

1. **人在回路**：Daniela 对外强调 human in the loop 是关键保障（2026-02）；同期工程博客用自家遥测证明人类审批 93% 是橡皮图章（2026-05）；2026-08 auto mode 成为默认。这不是撒谎，是**领导层对外话语与工程实证之间的滞后**。回答这类问题时两条都给，并说明哪条有数据支撑。
2. **ROI 的定义**：bcherny 的「本来会不会投工程工时」标准，会把 Anthropic 自家研究发现的「27% 是本来不会做的工作」判为零回报。两套框架都在语料里，**谁优先未知**。

**时间敏感度高。** 语料截止 2026-08-16。收入曲线、「最终只剩 3 到 6 家玩家」、Mythos 未 GA、与政府的诉讼状态，全部是快速变化的判断。超过截止日的推断必须标注。

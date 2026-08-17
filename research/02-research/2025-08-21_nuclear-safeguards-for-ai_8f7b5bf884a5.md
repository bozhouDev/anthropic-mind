---
title: Developing nuclear safeguards for AI
source: "https://www.anthropic.com/research/nuclear-safeguards-for-ai"
published_at: 2025-08-21
captured_at: 2026-08-16
author: Anthropic
source_type: research
authority_score: P1
mind: engineering
status: captured
evidence_url: "https://www.anthropic.com/research/nuclear-safeguards-for-ai"
catalog_id: 8f7b5bf884a5
---

Frontier Red Team
Developing nuclear safeguards for AI
Aug 21, 2025
Nuclear technology is inherently dual-use: the same physics principles that power nuclear reactors can be misused for weapons development. As AI models become more capable, we need to keep a close eye on whether they can provide users with dangerous technical knowledge in ways that could threaten national security.
Information relating to nuclear weapons is particularly sensitive, which makes evaluating these risks challenging for a private company acting alone. That’s why last April we
partnered
with the U.S. Department of Energy (DOE)’s National Nuclear Security Administration (NNSA) to assess our models for nuclear proliferation risks and continue to work with them on these evaluations.
Now, we’re going beyond assessing risk to build the tools needed to monitor for it.
Together with the NNSA and DOE national laboratories, we have co-developed a classifier
—an AI system that automatically categorizes content—
that distinguishes between concerning and benign nuclear-related conversations with 96% accuracy in preliminary testing
(see below for details).
We have already deployed this classifier on Claude traffic as part of our broader system for identifying misuse of our models. Early deployment data suggests the classifier works well with real Claude conversations.
We will share our approach with the
Frontier Model Forum
,
the industry body for frontier AI companies,
in hopes that this partnership can serve as a blueprint that any AI developer can use to implement similar safeguards in partnership with NNSA.
1
Along with the concrete importance of securing frontier AI models against nuclear misuse, this first-of-its-kind effort shows the power of public-private partnerships. These partnerships combine the complementary strengths of industry and government to address risks head-on, making AI models more reliable and trustworthy for all their users.
What we built
In this partnership, we did not stop with identifying risks—we developed an approach for addressing them. After a year of NNSA staff red teaming Claude models in a secure environment, we began to co-develop risk mitigations.
Informed by their red teaming, NNSA shared with us a carefully curated set of nuclear risk indicators designed to distinguish potentially concerning conversations about nuclear weapons development from benign discussions about nuclear energy, medicine, or policy. Crucially, this list was developed at a classification level such that it could be shared with our team, allowing us to use it to build defenses.
Our Policy and
Safeguards
teams turned that list into a classifier that could identify concerning nuclear queries in real-time. Think of a classifier as a specialized labeller, like the one that underpins the spam filter in your email inbox. Instead of identifying junk mail, this classifier identifies conversations that are potentially harmful while allowing legitimate discussions.
To validate the system, we generated hundreds of synthetic test prompts—some concerning, some benign—ran them through the classifier, and shared the results with the NNSA. NNSA validated that the classifier scores aligned with the expected labels (i.e., harmful or benign). We then refined the approach based on their feedback, and repeated the cycle to improve precision. Figure 1 summarizes this process.
Figure 1: Classifier co-development process.
The most challenging aspect of this endeavor wasn’t technical—it was bridging the gap between a national security agency and a private AI company. Both sides had to operate under information sharing constraints: the NNSA needed to keep certain information classified, and Anthropic needed to protect user data. How, then, could we validate that our classifier actually worked? Synthetic data generation was our solution: we used example prompts from NNSA to generate hundreds of test cases, creating a robust evaluation set without compromising either party’s equities.
Why does this matter?
If an AI system is too cautious, it might refuse legitimate nuclear engineering coursework. Too permissive, and it could inadvertently assist bad actors.
Our classifier appears to strike the right balance. In preliminary testing with synthetic data, we achieved a 94.8% detection rate for nuclear weapons queries and zero false positives (overall, 96.2% of the classifier’s labels in this test were accurate as shown in Figure 2), suggesting this system would not flag legitimate educational, medical, or research discussions as concerning. This precision matters because nuclear conversations in AI systems are rare but high-stakes—they bear directly on national security.
Figure 2: Comparison of the classifier’s assessment of synthetic exchanges to their known status showing correct assessment of all the true negatives and almost 95% of the true positives. The overall accuracy reflects the total proportion of correctly predicted labels.
Sharing with industry
We’re making these resources available so that other leading AI companies can implement similar safeguards if they choose. Beyond demonstrating how government expertise can enhance AI safety through voluntary public-private cooperation, we hope this sparks an exchange where we can learn from each other’s approaches to risk mitigation.
What’s next?
As noted above, we have deployed the classifier as an experimental addition to our Safeguards framework, monitoring a percentage of Claude traffic. Its real-world performance has confirmed that the classifier works effectively beyond our testing environment. Whereas our synthetic test data provided clear examples of harmful and benign exchanges, the distribution of actual user traffic proved more complex and surprising, yet the classifier still performed well.
One example of how real-world deployment differs from testing is that the classifier flagged certain conversations about nuclear weapons that we ultimately determined to be benign. For example, recent events in the Middle East brought renewed attention to the issue of nuclear weapons. During this time, the nuclear classifier incorrectly flagged some conversations that were only related to these events, not actual misuse attempts. We found that when these exchanges went through
hierarchical summarization
—which reviews multiple flagged conversations together—they were correctly identified as harmless current events discussions because of the additional context provided by the summarization step.
This reveals two dynamics: first, that real-world conversations often fall into gray areas that are difficult to capture in synthetic data, and second, that combining multiple safety tools creates a more nuanced and precise system.
Ultimately, the classifier proved its value by successfully catching concerning content (i.e. true positives) when deployed. For example, Anthropic red teamers who were not aware the classifier had been deployed were conducting routine adversarial testing of our systems using deliberately concerning prompts. The classifier correctly identified these test queries as potentially harmful, demonstrating its effectiveness.
This work leveraged each party’s strengths (i.e., government domain expertise and industry technical capabilities) and early results show it is working in practice. This demonstrates a model of public-private partnerships that can be replicated in other national security domains. It also illustrates that there are steps that industry can take now to implement meaningful safety measures.
We are grateful to the team at NNSA and DOE national laboratories for their commitment to this collaboration, which demonstrates how industry and government can work together to enhance national security.
For more on our safety initiatives, see our
Responsible Scaling Policy
,
Frontier Red Team
, and
Safeguards
work.
Footnotes
We are able to share this kind of information because FMF member firms (i.e., Amazon, Anthropic, Google, Meta, Microsoft, and OpenAI) have signed a unique
agreement
designed to facilitate information-sharing about threats, vulnerabilities, and capability advances unique to frontier AI.
Related content
Patterns and problems in emerging multiagent systems
Here, we identify a few examples of behavioral tendencies in current frontier models and show how they can produce unexpected systemic failures, in hopes of starting a conversation about mitigating these risks.
Read more
Reviewing the evidence on worker retraining programs
We're sharing a review of the evidence on worker retraining programs, coauthored by independent researcher David Roodman and Anthropic's Maxim Massenkoff.
Read more
Learning more about Claude's mathematical capabilities
An unreleased research version of Claude has made strides on a problem related to the Riemann hypothesis. It improved a longstanding lower bound for the fraction of zeros of the Riemann zeta function that satisfy the hypothesis, increasing it from 41.6% to 67.2%.
Read more
Subscribe to the Frontier Red Team newsletter
Get updates on our latest red-teaming research and findings.

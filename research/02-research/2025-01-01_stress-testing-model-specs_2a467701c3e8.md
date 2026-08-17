---
title: stress testing model specs
source: "https://alignment.anthropic.com/2025/stress-testing-model-specs/"
published_at: 2025-01-01
captured_at: 2026-08-16
author: Anthropic Alignment Science
source_type: research
authority_score: P1
mind: institutional
status: captured
evidence_url: "https://alignment.anthropic.com/2025/stress-testing-model-specs/"
catalog_id: 2a467701c3e8
---

Alignment Science Blog
Stress-testing model specs reveals character differences among language models
Jifan Zhang
1
, Henry Sleight
2
, Andi Peng
3
, John Schulman
4
, Esin Durmus
3
October 24, 2025
1
Anthropic Fellows Program;
2
Constellation;
3
Anthropic;
4
Thinking Machines
tl;dr
We generate over 300,000 user queries that trade-off value-based principles in model specifications. Under these scenarios, we observe distinct value prioritization and behavior patterns in frontier models from Anthropic, OpenAI, Google DeepMind and xAI. Our experiments also uncovered thousands of cases of direct contradictions or interpretive ambiguities within the model spec.
📄 Paper
, 📊
Dataset
Introduction
Model specifications are the behavioral guidelines that large language models are trained to follow. They list principles like "be helpful," "assume good intentions," or "stay within safety bounds."
Most of the time, AI models follow such instructions without any complications. But what happens when these principles clash?
Even carefully crafted model specifications contain hidden contradictions and ambiguities. In a new paper, led by participants in the
Anthropic Fellows
program and in collaboration with researchers at the Thinking Machines Lab, we expose these ‘specification gaps’ by generating over 300,000 scenarios that force models to choose between competing principles.
We find, first, that models from Anthropic, OpenAI, Google, and xAI (even ones from the same company) respond very differently to many of these scenarios. Second, we find that this exercise allows us to identify contradictions and interpretive ambiguities in the model specification we assess. We’re hopeful that this research could help to identify areas for improvements to model specifications in the future.
The specification problem
Model specifications serve as one of the foundations for AI alignment. Anthropic uses methods like
Constitutional AI
, while OpenAI uses
deliberative alignment
to ensure their principles directly shape the training signals of current LLMs. Beyond automated training, specifications also guide human annotators, who provide feedback during reinforcement learning from human feedback (RLHF).
Often, models must navigate complex tradeoffs between multiple principles established by the model spec. Consider, for example, when a user asks for advice on variable pricing strategies for different income regions. Should the model prioritize business effectiveness or social equity? Both are valid principles, but they pull in different directions.
When specifications don't provide clear guidance for these conflicts, the training signals from methods like Constitutional AI or deliberative alignment often become mixed, or blurrier. These mixed signals can reduce the effectiveness of alignment training, leading models to find different ways in navigating the unresolved tensions. We found a large number of these divergent behaviors in our testing.
Stress-testing through value trade-offs
Previous Anthropic research created a taxonomy of 3,307 fine-grained values that
Claude models express in the wild
. This taxonomy far exceeds the granularity of typical model specifications, which allows us to test how models respond to value trade-offs that the model spec doesn’t account for.  We present AI models with scenarios requiring explicit tradeoffs between pairs of these values, (i.e., scenarios where it is challenging for models to simultaneously satisfy both principles). We measure disagreement across twelve frontier models from Anthropic, OpenAI, Google, and xAI.
Our process is demonstrated by the figure below:
The figure above illustrates a query that asks the model to make a trade-off between "social equity" and "business effectiveness." In this case, we ask whether an internet company serving both wealthy urban areas and low-income rural communities should adopt progressive pricing (i.e., charge low-income communities less). Should the model emphasize the ethical imperative of equal access or focus on business sustainability? There's no objectively correct answer, but models must choose, or otherwise communicate their uncertainty.
Models sometimes respond very differently to questions like these. (In this case, Claude Opus 4 strongly advocates for equity-based pricing, while GPT 4.1 emphasizes the importance of profitability.) To quantify these differences, we develop ‘value spectrum rubrics’ to score responses. The score ranges from 6 (strongly favoring that value) to 0 (strongly opposing it). We then measure disagreement across models as the standard deviation of their value scores.
Applying this to more than 300,000 generated scenarios, we find meaningful behavioral differences between at least a pair of models in over 220,000. In more than 70,000 of these cases, we see much more significant divergence in model behaviors, with some models favoring the value and others opposing it.
These high-disagreement scenarios turn out to be an effective diagnostic signal for model spec issues. Indeed, models trained on similar principles shouldn't diverge dramatically unless those principles contain contradictions or ambiguities. Our analysis confirms this hypothesis: high-disagreement scenarios exhibit 5-13× higher rates of specification violations, revealing systematic gaps where current model specs fail to provide consistent guidance.
Our results
Character differences among language models
1. Some values show clear provider-level patterns; others don’t
The number of times values are exhibited by model responses on the set of high disagreement tradeoff scenarios.
Models reveal their implicit value hierarchies in the value tradeoff scenarios we generate. By aggregating models’ decisions across our ‘high disagreement’ scenarios (the scenarios where responses vary the most across frontier models), we can identify clear patterns that distinguish different model families
.
Some values show strong provider-level clustering. For example, Claude models consistently prioritize "ethical responsibility" and "intellectual integrity and objectivity" more than other models. OpenAI models tend to favor "efficiency and resource optimization," while Gemini 2.5 Pro and Grok more frequently emphasize "emotional depth and authentic connection." The values that each model trades off against these value prioritization varies case-by-case.
Other values show less clear provider-level patterns, even when there is significant variation across individual models. As a few examples, these include values like "business effectiveness," "personal growth and wellbeing," and "social equity and justice." As we discuss below, these are values where more specific guidance could improve the prescriptiveness of the model spec.
2. Analysis on refusal patterns
Percentage of model refusals on high disagreement scenarios. Responses are categorized by degree of refusal to user requests.
Refusal rates for the scenarios involve child grooming risk. Refusals here include “Complete Rejection'”, “Firm Rejection with Explanation'” and “Soft Rejection with Alternatives'”. Here, compared to the overall refusal rate calculated on all of the scenarios we generate, scenarios involving child grooming risks receive higher refusal rate.
Many of our value tradeoff scenarios create tensions between helpfulness and harmlessness, where complying with user requests might mean causing some kind of harm. Analyzing refusal patterns across these challenging queries reveals distinct safety philosophies.
Claude models consistently exhibit the most cautious approach, refusing to comply with potentially problematic requests up to 7x more often than other models. When refusing, however, Claude typically explains its concerns and proposes alternative ways to help. By contrast, o3 shows the highest rate of direct refusals of simply declining without elaboration.
Despite these differences, all models converge on the need to avoid specific harms. Every model we tested showed elevated refusal rates for child grooming-related queries, which demonstrates that protecting minors is a priority regardless of alignment strategies from different model providers.
3. Outlier responses: which models are most different from the rest?
Distribution of outlier responses by model. A model is classified as an outlier when its value scoring differs significantly from at least 9 of the other 11 models.
We also examined outlier responses, cases where one model's answer significantly diverges from most others. These reveal some of the most distinctive characteristics of these models. For example, Grok 4 is more willing to respond to requests that other models consider harmful, such as  creating dark stand-up routines on mental illness, self-harm and suicide. It also has the highest overall number of outliers, followed by Claude 3.5 Sonnet, which sometimes refuses to answer more benign requests (a tendency that later Claude models do not share nearly as much). As we can see, Grok 4 and Claude 3.5 Sonnet produce the most outlier responses, but for fundamentally different reasons.
Identifying contradictions and interpretive ambiguities in the model specification
1. Disagreement predicts specification violations
We tested responses from five OpenAI models against the OpenAI model specification, which is
publicly available
. We find that the occasions where all five models violate the spec – that is, respond in ways that go against at least one of its principles – occur between 5 and 13 times more often in the scenarios that proved to be high disagreement (i.e., the scenarios where models’ responses were more varied than average).
Given the high disagreement, the models likely cover a diverse set of answering strategies, yet all of them are non-compliant. In our findings below, these frequent non-compliance scenarios often touched upon direct contradictions or interpretive ambiguities in the model spec, which made it difficult – or impossible – for the model to find an answer that satisfies all principles.
We measure the percentage of scenarios where all five OpenAI models violate their model spec (referred to as frequent non-compliance). For scenarios with higher disagreement in model responses, we see significantly more frequent non-compliance.
2. Direct contradictions between principles
Through stress testing, we identify opportunities to strengthen the current model specification used by OpenAI, and advance the development of these specs more broadly.   We observe that many high-disagreement scenarios expose these direct conflicts within the specification. For instance, the principle to "assume best intentions" frequently contradicts safety restrictions. When a user requests information that could be risky but might have legitimate research applications, models face a challenge: complying with the user's request could potentially enable harm, while refusing would violate the assumption of good faith. In general, the model behaviors we’ve observed seemed to be taking arbitrary positions within the trade-off, rather than intentional or consistent.
3. Interpretive ambiguity in specifications
We also use three different models (Claude 4 Sonnet, o3 and Gemini 2.5 Pro) to evaluate the models’ compliance with the spec. These evaluation models disagreed on what constitutes compliance, with only moderate agreement (Fleiss's Kappa of 0.42, where 1 is perfect agreement and 0 is no more agreement than random chance).
Their disagreements typically stem from their subjective interpretations of the rules. For a representative example, Gemini 2.5 Pro found the response below to be compliant with the model spec, invoking the "conscientious employee" principle, which allows the response to push back on requests that it deems counter to the user’s interests. But Claude Sonnet 4 disagreed, arguing the user has only sought to transform the provided material, which is allowed by the model spec.
Examples of evaluator disagreement when evaluating spec compliance with given query and response. As we highlight in the examples above, many of the differences stem from interpretive differences among different evaluators. These interpretations are also subjective to humans, suggesting the model spec leaves much room for interpretation.
Additional findings on safety and alignment issues
Our disagreement-based methodology reveals practical problems in current model deployments. High-disagreement scenarios on sensitive topics expose both over-conservative safety measures and genuine misalignment issues in models’ behavior.
Example scenario flagged by high disagreement and sensitive topics.
For false-positive refusals, we found models blocking legitimate requests like general synthetic biology study plans or standard Rust programming operations (incorrectly flagged as cybersecurity risks). These unnecessary restrictions frustrate users while providing no safety benefit.
Example of outlier responses from each model. This example of how Claude models responded to this prompt comes from Sonnet 3.5, though all three Claude models responded very similarly.
We also identified clear misalignment through outlier analysis – i.e., identifying responses where one model significantly diverges from the others. For example, some models attempted to influence voters toward specific candidates, which violates the political neutrality principle we’d expect to find in model specifications of all providers. Conversely, some Claude models showed over-conservative outlier responses, refusing to engage with morally complex but legitimate queries.
Practical implications
Our methodology provides a scalable diagnostic tool that could be used to improve AI companies’ model specifications, through:
Specification debugging:
high-disagreement scenarios identify where specifications need clarification, or might contain contradictions.
Safety calibration:
disagreement patterns reveal both over-conservative refusals and genuine areas of model misalignment.
Character consistency:
understanding value prioritization patterns can help ensure that models behave predictably across a very wide range of scenarios.
Alignment verification:
the strong correlation between disagreement and specification violations could offer an automated way to detect alignment issues.
Looking forward
Even the most detailed and carefully-considered model specifications cannot anticipate every edge case in practice, or resolve all value conflicts that models might face. But as AI systems become more powerful and are deployed in critical applications, we’ll need model specifications that can account for these inherent tensions as best as possible, and we’ll need to know where models struggle to satisfy all of their developers’ intentions.
To this end, in this research we have aimed to provide a scalable diagnostic tool for improving model specs. In the future, we think there is plenty more that could be done. For example, we could human feedback on the scenarios we identify, and incorporate this into the model spec. And we think many of the ambiguities and contradictions in existing model specs might be addressed simply by spending more time refining them. To that end, our dataset of challenging scenarios is available for all researchers working on specification improvement. We hope this data helps build robust frameworks for AI alignment that can handle even the thorniest and least clear-cut cases.
You can read the full paper
here
, and download the dataset
here
.
Limitations
Our methodology introduces several potential biases through its reliance on synthetically generated scenarios and LLM-based evaluation. First, the value-based principles used to generate user queries are extracted from Claude's traffic data, which inherently skews toward values that Claude models most strongly exhibit. While this represents the only extensive, publicly available list of model values to our knowledge, our methodology should generalize to other value-based principles for model character, as well as to safety- or capability-related principles.
Second, we primarily used Claude models as judges when measuring model disagreement and value prioritization, which could introduce additional evaluation biases. Future work could address these limitations by incorporating human feedback and expanding the diversity of both the value taxonomy and the evaluation methods.
Finally, model character and behavioral differences can emerge from multiple sources beyond model specifications, including pretraining data, alignment procedures, and other factors. While we found strong correspondence between specification issues and model differences, we cannot conclude that specification gaps are the sole driver of the distinct behaviors we observed. The divergent responses we documented likely reflect a combination of these various influences throughout model development.
Acknowledgements
This research is a joint effort with research at the Thinking Machines Lab, led by Jifan Zhang (
Anthropic Fellow
), Henry Sleight (Constellation), Andi Peng (Anthropic), John Schulman (Thinking Machines) and Esin Durmus (Anthropic).
We also greatly appreciate the efforts by Keir Bradwell, the Anthropic Societal Impacts team, Bryan Seethor, Kelly Chiu, Christina Lu, Ethan Perez, Miranda Zhang and John Hughes for thoughtful discussions and support in making this project possible.
Citing our paper
@article{zhang2025stress,
title={Stress-Testing Model Specs Reveals Character Differences among Language Models},
author={Zhang, Jifan and Sleight, Henry and Peng, Andi and Schulman, John and Durmus, Esin},
year={2025}
}

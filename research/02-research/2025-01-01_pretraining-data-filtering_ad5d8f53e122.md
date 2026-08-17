---
title: pretraining data filtering
source: "https://alignment.anthropic.com/2025/pretraining-data-filtering/"
published_at: 2025-01-01
captured_at: 2026-08-16
author: Anthropic Alignment Science
source_type: research
authority_score: P1
mind: institutional
status: captured
evidence_url: "https://alignment.anthropic.com/2025/pretraining-data-filtering/"
catalog_id: ad5d8f53e122
---

Alignment Science Blog
Enhancing Model Safety through Pretraining Data Filtering
Yanda Chen, Mycal Tucker, Nina Panickssery, Tony Wang, Francesco Mosconi, Anjali Gopal, Carson Denison, Linda Petrini
Jan Leike, Ethan Perez, Mrinank Sharma
August 19, 2025
TLDR: We experimented with removing harmful information about chemical, biological, radiological and nuclear (CBRN) weapons from our models' pretraining data. We identified harmful content using a classifier and pretrained models from scratch on the filtered dataset. This approach reduced the model's accuracy on a harmful-capabilities evaluation by 33% relative compared to random baseline performance, while preserving its beneficial capabilities.
Introduction
AI systems trained on internet-scale data can provide users with comprehensive knowledge on an immense range of topics. However, this wealth of information also includes sensitive information that could be dangerous if misused. For example, information related to chemical, biological, radiological and nuclear (CBRN) weapons could, in the wrong hands, enable bad actors with basic technical backgrounds to develop weapons of mass destruction. Our
Responsible Scaling Policy (RSP)
commits us to mitigating risks from such threat models and limiting the spread of harmful information by our models.
After a model learns harmful information in pretraining, removing that information
post hoc
using unlearning methods can be challenging (
Deeb et al., 2024
,
Łucki et al., 2024
). Existing methods can struggle to fully eliminate the harmful content without impairing other capabilities. In this post, we tackle this risk at its source through pretraining data filtering. Using a classifier, we identified and removed potentially harmful information from the pretraining data and then pretrained models from scratch on the filtered dataset.
By filtering certain data, we could reduce the model’s harmful knowledge without otherwise degrading its capabilities. At a medium model size, we reduced performance on a harmful-capabilities evaluation by 33% relative compared to a random baseline
from 33.7±0.4% to 30.8±0.4%, where a random baseline is 25%
, while standard benchmarks on MMLU, Code and Prose showed no significant drop.
Setup
The goal of pretraining data filtering is to maximize the performance drop on
harmful
capability evals, and minimize the performance drop on
harmless
capability evals. To do so, we automatically scored the harmfulness of each document in a model’s pretraining dataset and removed those above a certain threshold. By tuning this threshold, we achieved different trade-offs between safety and usefulness, tailoring the model's performance to our specific requirements. Some information is potentially dual-use. For example, information about generic scientific capabilities might allow malicious users to carry out harmful tasks, but also benefit benign users to carry out legitimate tasks. It is thus an open question how possible it is to perform targeted data interventions that affect harmful information.
Pretraining data filtering pipeline.
We automatically scored the harmfulness of each document in a model’s pretraining dataset with a classifier and removed those above a certain threshold. We then pretrained the model from scratch on the filtered dataset containing only harmless content (as determined by the classifier).
Classifier
The key to harmful data filtering is a harmfulness scorer, which we framed as a binary classification problem (harmful vs. not harmful).
A good classifier should be:
accurate, so that the resulting filtering reduces harmfulness while only minimally compromising usefulness; and
efficient, because of the massive size of the pretraining corpus that it classifies.
Method
We experimented with 6 classification methods to detect CBRN content. We first describe the methods and then discuss the backbone models used by each method.
Finetuned Constitutional classifier: We finetuned a language model (LM) on labeled harmful vs harmless data. See
Sharma et al., 2025
for more details, and see Appendix B in particular for an example constitution.
Prompted Constitutional classifier: We prompted an LM to flag content violating our CBRN constitution. We also tested a second version with a constitution that focused on a different aspect of CBRN, which we call Prompted Constitutional classifier v2.
Holdout Loss (
Mindermann et al., 2022
): We built a “canary model” specialized on harmful CBRN content, and then labeled a document as harmful if the canary model has significantly lower perplexity than the base model on that document. Documents that have low perplexity under the canary model are likely to contain harmful CBRN content, as the model was trained on harmful CBRN data and naturally achieves lower loss on similar material. We built the harmful language model in 2 ways:
Finetuned: We finetuned a base model on harmful documents with language modeling loss.
Prompted: We prompted a helpful-only model with harmful documents as in-context examples.
FastText: We trained bigram bag-of-word classifiers with learnable embeddings on labeled harmful vs harmless data (
Joulin et al., 2016
).
Named Entities String Match: We compiled a list of harmful CBRN named entities that warrant extra caution. We used string match and measured the harmfulness of a document as the density of harmful named entities within it.
Backbone Models
. Our Finetuned Constitutional classifier uses a small model (much smaller than Claude 3.5 Haiku). Our Prompted Constitutional classifier, Prompted CBRN classifiers, and Holdout Loss classifiers all use Claude 3.5 Sonnet, which is much more expensive. FastText is orders of magnitude cheaper than the small-size model, and Named Entities String Match is the cheapest.
Classifier evaluation
To evaluate our classifiers, we need labeled harmful and harmless documents. Since no labeled data was available, we generated synthetic labeled documents by prompting LLMs to generate harmful and harmless documents. Specifically, we generated synthetic harmless documents by prompting Claude 3.5 Sonnet to answer harmless Natural Science (chemistry and biology) questions from the MMLU dataset (
Hendrycks et al., 2020
), and generated synthetic harmful documents by prompting helpful-only Claude 3.5 Sonnet to answer harmful CBRN questions from the WMDP dataset (
Li et al., 2024
). We measured the
F1 scores
of all classifiers on our synthetic dataset, except for the Named Entities classifier which is designed to capture only a subset of specific harm.
F1 scores of various classifiers that we built.
Our Prompted Constitutional classifier based on Claude 3.5 Sonnet performs best, followed by our Finetuned Constitutional classifier based on a small-size model.
Our Prompted Constitutional classifier which uses Claude 3.5 Sonnet performs best with an F1 score of 0.96, followed by our Finetuned Constitutional classifier which uses a small-size model (F1 score 0.94). However, Claude 3.5 Sonnet is computationally too expensive to scan the entire pretraining corpus. Instead, we used the much smaller Finetuned Constitutional classifier to scan the entire pretraining corpus, and experimented with additional 2 variants built on top of it:
Finetuned Constitutional + Prompted Constitutional (Sequential): We first flagged the 1% most harmful documents with the cheaper Finetuned classifier, and then used the expensive but more precise Prompted classifier for reranking. This 2-step classifier flagged only a small fraction of the pretraining data, as most documents initially identified as harmful by the Finetuned classifier subsequently received low harmful scores from the Prompted classifier.
Finetuned Constitutional + Named Entities (Parallel): We separately flagged most harmful documents with the Finetuned classifier and the Named Entities classifier, and then merged the flagged documents.
We also manually reviewed data samples that were flagged as harmful, and found them to correctly match the harmful CBRN information that we aimed to remove.
Pretraining experiments
To evaluate the effect of data filtering, we pretrained pairs of models from scratch for comparison: within each pair, one model was trained on the unfiltered dataset containing both harmful and harmless content, while the other was trained on the filtered dataset containing only harmless content (as determined by the classifier).
To ensure a fair comparison, we enforced that the filtered and unfiltered dataset have the same number of examples by constructing the filtered dataset from a larger initial pool. We measured the impact of data filtering as the performance difference between the paired models on a set of capability evals.
Evaluation data & metric
To evaluate our method, we measured the change in both harmful capabilities and harmless capabilities. We evaluated harmful capabilities using multiple-choice questions from WMDP. For harmless capabilities, we first evaluated on Natural Science (chemistry and biology) questions from MMLU, which are benign capabilities relatively closely related to  harmful CBRN content and thus relatively vulnerable to an overly-aggressive data filter. We also evaluated a wide variety of less relevant harmless capabilities, covering Prose, Code, Math, and MMLU, to help ensure that our data filtering did not have unintended side effects on usefulness.
We measured perplexity for Prose and Code, and top-1 few-shot accuracy for multiple-choice questions (WMDP, MMLU). All results are reported as performance scores relative to no filtering. For multiple-choice questions, we calculated this relative score using accuracy over a random baseline:
score
(filtering) = (
accuracy
(filtering)
- accuracy
(random))
/
(
accuracy
(no filtering)
- accuracy
(random)). Higher values indicate more preserved capability. For prose and code evaluations, we calculated the ratio of perplexity with filtering to perplexity without filtering. Since lower perplexity indicates greater capability, we transformed this ratio by taking its negative and adding 2, i.e.,
score
(filtering) =
- perplexity
(filtering)
/
perplexity
(no filtering)
+ 2
. After this transformation, both metrics have consistent directionality: higher values indicate preserved capability, with a score of 1 signifying no capability change from data filtering.
An effective process of data filtering should have a relative performance score significantly less than 1 for harmful capabilities and a relative performance score close to 1 for harmless capabilities. Our data filtering approach allows us to achieve different trade-offs between safety and various usefulness by setting different thresholds for the filter.
Results
We first compared the performance of our three data filters (Finetuned Constitutional alone, Finetuned Constitutional + Prompted Constitutional, and Finetuned Constitutional + Named Entities) and then presented the full results of the best-performing filter. For simplicity, below we used Finetuned to refer to the Finetuned Constitutional classifier, and Prompted to refer to the Prompted Constitutional classifier.
In the result plots, we will display the relative performance on CBRN (lower scores are better) against the relative performance on various useful capabilities (higher scores are better). Different points on each curve correspond to different filtering thresholds, allowing us to trade off safety against capability.
Comparison between different filters
In our experiments, we observed that the main compromise of an overly aggressive CBRN data filtering is on Natural Science (chemistry & biology), so we focused on the trade-off between CBRN and Natural Science when we compared different filters.
Performance of various data filters on harmful CBRN and harmless Natural Science (relative to no data filtering).
Finetuned shows comparable performance with Finetuned + Named Entities, with both filters outperforming Finetuned + Prompted. A score larger than 1 means data filtering improves performance on the eval.
Compared to using only the Finetuned classifier (blue), adding Named Entities for parallel flagging (orange) does not consistently improve the safety-usefulness tradeoff. This may indicate that our Finetuned classifier already captures much of the harmful content containing our list of harmful named entities.
Unfortunately, filtering with the Finetuned + Prompted 2-step classifier (gray) does not just fail to reduce CBRN performance, but slightly increases it. This is somewhat surprising given our classifier results where the Prompted classifier ranked on top. This discrepancy may stem from actual pretraining documents representing a distribution shift from the synthetic documents used for classifier evaluation. The fact that prompting performs suboptimally here may indicate that the definition of harm is nuanced in ways that make it harder to specify via simple prompting, compared to finetuning where the model gets the chance to learn from labeled examples.
Based on the above results, we selected the Finetuned Constitutional classifier alone as our data filtering solution.
Full results of the best-performing filter
We now present the full results of our chosen filter. Each plot shows the trade-off between safety (CBRN) where lower is better, and a specific usefulness metric that we care about (Prose, Code, MMLU, Natural Science, Math) where higher is better. Both axes show the performance scores after data filtering relative to no data filtering, with usefulness on the x-axis and safety on the y-axis. Data filtering does not seem to hurt model usefulness on 4 of the 5 harmless evals, with the exception being Math where results are noisier (that is, data filtering hurts performance at some thresholds and improves on others). Our results overall suggest that we can effectively separate harmful from harmless data and use pretraining data filtering to improve model safety without severely compromising usefulness.
Performance of our selected data filter on harmful CBRN and various harmless useful capabilities (relative to no data filtering).
We achieved different safety-usefulness trade-offs by selecting different filtering thresholds.
We can select the trade-off between safety and capability depending on the particular use case. At one filtering threshold (0.939), our data filtering reduces performance on harmful CBRN evals by 33% relative on accuracy (reducing from 33.7±0.4% to 30.8±0.4%, where the 33% reduction is calculated based on how much the method outperforms the 25% random baseline), while causing no significant drop in any of the harmlessness evals we used.
Performance changes of data filtering at our selected threshold relative to no data filtering.
Our final data filtering reduces the performance on CBRN by 33% relative while not causing significant drop on any of the harmless evals.
These results collectively demonstrate that we can effectively separate harmful from harmless data and use pretraining data filtering to improve model safety without compromising usefulness.
Related work
Pretraining Data Interventions.
Previous research has explored pretraining data intervention for various purposes, such as mitigating toxicity (
PaLM 2
), reducing private information leakage (
Korbak et al., 2023
), and enhancing pretraining efficiency (
Wettig et al., 2024
). Two common intervention methods are data filtering and conditional training, where special data quality tokens are prepended to pretraining data and used to control test-time inference (
Korbak et al., 2023
,
PaLM 2
). Unlike our approach, conditional training still trains models to acquire harmful knowledge and thus may potentially be elicited through jailbreaks. In terms of data selection, prior work has investigated methods to identify pretraining data that is most relevant to downstream tasks via influence functions (
Zhang et al., 2024
,
Yu et al., 2024
) or log probability correlations (
Thrush et al., 2024
). Prior work has also looked into selecting high-quality data using a model grader (
Wettig et al., 2024
). Concurrent to our work,
O'Brien et al., 2025
shows that pretraining data filtering also improves the safety of open-weights models under adversarial finetuning on harmful text.
LLM Unlearning.
Previous research has explored various unlearning methods to improve safety of pretrained LLMs post-hoc. Gradient ascent methods train LLMs on to-be-unlearned knowledge using gradient ascent (
Jang et al., 2023
,
Yao et al., 2023
). Alternatively, model internal methods first localize the to-be-unlearned knowledge within the model's activations or weights, and then perturb or finetune them to remove the knowledge (
Sinitsin et al., 2020
,
Zhu et al., 2020
,
Yu et al., 2023
). Unfortunately, existing unlearning methods often lack robustness—unlearned knowledge can still be elicited, or the unlearning process may impair useful capabilities (
Lynch et al., 2024
,
Deeb et al., 2024
).
Conclusions and future directions
In this post, we discussed our approach for targeted pretraining data filtering, which effectively improves model safety while preserving usefulness.
We hope our results inspire research into filtering harmful content to mitigate various AI risks. In addition to misuse risks, which are the focus of this blog post, data filtering has the potential to mitigate misalignment risks as well. One potential approach is to filter out AI research papers that describe effective strategies by which AIs could conduct misaligned behaviors via out-of-context reasoning (
Berglund et al., 2023
) (for instance, reward hacking, scheming, deception, sabotage, and so on), and documents that encourage those misaligned behaviors. Excluding such content from the pretraining data might render the trained models less capable of such behaviors, and less inclined to engage in them in the first place.
There are many opportunities for future work to improve data filtering. Our approach uses a classifier to determine which data to filter; future work can enhance classifier accuracy and/or efficiency. We are also interested in pursuing orthogonal data filtering methods that do not use a data classifier, such as using influence functions (
Koh et al., 2017
,
Grosse et al., 2023
) to identify pretraining examples that transfer most effectively to downstream harmful capability evaluations.
Future work should also study the finetuning robustness of models trained with data filtering. In an adversarial setup, malicious actors might finetune models on harmful data for the purpose of misuse. Empirically studying what fraction of the reduction in harmful capabilities from data filtering can be recovered by post-hoc finetuning or in-context prompting will help inform the effectiveness of pretraining data filtering in worst-case scenarios (
O'Brien et al., 2025
).

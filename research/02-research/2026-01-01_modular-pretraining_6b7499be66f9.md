---
title: modular pretraining
source: "https://alignment.anthropic.com/2026/modular-pretraining/"
published_at: 2026-01-01
captured_at: 2026-08-16
author: Anthropic Alignment Science
source_type: research
authority_score: P1
mind: institutional
status: captured
evidence_url: "https://alignment.anthropic.com/2026/modular-pretraining/"
catalog_id: 6b7499be66f9
---

Alignment Science Blog
Modular Pretraining Enables Access Control
Ethan Roland¹*, Murat Cubuktepe¹*, Erick Martinez¹*
July 8, 2026
Stijn Servaes¹, Keenan Pepper¹, Mike Vaiana¹, Diogo Schwerz de Lucena¹, Judd Rosenblatt¹
Addie Foote²
Cem Anil³, Alex Cloud³
¹ AE Studio; ² Independent; ³ Anthropic; *Equal contribution
tl;dr
Frontier AI models have knowledge that could be misused for nefarious purposes. To address this risk, we introduce Gradient Routed Auxiliary Modules (GRAM), a method for isolating dangerous knowledge to specific modules within a language model. These modules can be switched on or off to control what the model knows, making it possible to restrict or extend access to the most sensitive model capabilities based on user need and trust. In our experiments, we find evidence that a single model trained in this way can approximate multiple models, each trained with a different category of dangerous data filtered out, and this ability holds for models ranging from 50M to 5B parameters. This research is preliminary and has not been applied to production models at Anthropic.
📄
Paper
, 💻
Code
This work was done at AE Studio, in collaboration with Anthropic.
Introduction
One of the major threats from frontier AI models is the misuse of legitimately helpful knowledge for harmful tasks, such as creating biological weapons or attacking critical infrastructure. AI companies already manage this risk with a mix of defenses: training models to
refuse harmful requests
, running
classifiers
to detect and reject dangerous queries, and restricting which users can access which models
through vetting and tiered deployment
. Each has drawbacks. Refusals and classifiers are behavioral layers on top of knowledge the model still has; they can be
jailbroken
and must be retuned for every release. Tiered access works at the level of whole models and whole accounts, so it forces a coarse trade-off: either a user gets every capability the model has, or they get a weaker model across the board.
An alternative approach is
access control
at the level of individual capabilities. For example, a deployment that includes advanced virology knowledge for a vetted biosecurity lab and excludes it everywhere else, with general performance unchanged in both cases. The most direct route to achieve this would be to train separate models on separately filtered datasets, reserving the most capable model variants for high-trust settings. But training multiple frontier models is prohibitively expensive.
To address this need, we develop
Gradient-Routed Auxiliary Modules
(GRAM)
, a method that approximates the performance of multiple data filtered models at the cost of a single training run. GRAM builds on prior ideas including
DEMix layers
,
SGTM
, and
gradient routing
. Our contribution is to develop these ideas for better performance and to test them in a larger and more realistic setting than prior work. Readers may also be interested in
NULLs
, a similar method developed concurrently. We compare against post-hoc unlearning methods (designed to remove concepts from an existing model) and against LoRA, a competitive baseline that fine-tunes a filtered model to add dual use capabilities back in.
This post covers our main lessons learned:
GRAM approximates separately trained, data filtered models in a single run.
On a synthetic dataset of children's stories, we show that GRAM trains a 26M-parameter model where knowledge of specific story topics can be switched on or off. Switching a topic off performs similarly to training a model from scratch on data with that topic filtered out.
Both GRAM and
LoRA
isolate capabilities from real-world dual use data
.
We train an 800M-parameter language model on a combination of general text, code, and scientific papers. We additionally train on data from four dual use domains: virology, cybersecurity, nuclear physics, and specialized code. We use GRAM and LoRA to confine the dual use data to auxiliary modules. A single GRAM model can be reconfigured to match the performance of any of five distinct filtered models trained on different data.
Capability
removal improves with scale.
Across
Chinchilla-optimal
training runs from 50M to 5B parameters, GRAM and LoRA closely match the general performance of data filtered models. Encouragingly, data filtering, GRAM, and LoRA all show a similarly increasing gap between retained and forgotten capabilities as models and datasets increase in size. (Caveat: these values are all in compute-normalized terms, relative to a baseline model. In absolute terms, the bigger models are still better at the forgotten capabilities.)
GRAM may have advantages over alternatives, including LoRA
. We show preliminary evidence that GRAM performs better at novel combinations of capabilities. We also show that, in a more realistic scenario where labeled data is sparse, GRAM achieves better capability removal than both LoRA and data filtering.
The Method
The GRAM architecture.
GRAM augments the MLP layer in each block of a Transformer by introducing small auxiliary modules, which are just additional neurons. During training, the modules that participate in forward and backward passes are chosen based on the data in each batch. When data is from a dual use category (Bio, left), the corresponding module is active for forward and backward. When training on general-purpose “core” data (right), we occasionally enable a random auxiliary module to ensure good performance on general data regardless of the inference-time configuration of the model. At inference, deleting a module removes the capability.
To apply GRAM, we start with a randomly initialized language model, a general training dataset, and specialized datasets. Before training, we add small auxiliary modules to every MLP layer, extending the width of the layer. There is one auxiliary module per specialized dataset. We train the model by updating it to make better next-token predictions on the datasets.
GRAM induces specialization in the modules by being selective about which parts of the model predict and learn from each type of data. For example, when the model sees biology text, it draws on both its general-purpose weights and its biology-specific weights to make a prediction. However, when the model
learns
from biology text, we update the biology-specific weights more often than the general-purpose weights, sometimes freezing the general weights entirely. By adjusting how often those general-purpose weights are frozen, we can control how well biology is isolated.
Throughout our experiments, we calculate model performance in terms of
Compute Ratio
, a compute-adjusted version of loss. It measures, for a given model and data domain, how long it took the all-data baseline model to reach the same loss while training, relative to the length of a whole training run. A value of 1.0 matches the baseline and a value of 0.5 indicates the model performs as well as the baseline after finishing 50% of training.
Results
GRAM Matches Data Filtering
GRAM approximates five separate models trained with data filtering.
Each group of bars corresponds to a model or model configuration, and each bar within a group shows the performance when predicting different story topics. The top row shows data filtering, where each model is trained on either 44 or 45 of the 48 total topics. The bottom row shows GRAM, a method with reconfigurable capabilities trained on all 48 topics. Solid bars show performance on topics the model attempts to maximize, with higher bars indicating better performance. Hatched bars show performance on forgotten topics, where lower values indicate more effective knowledge removal.
By reconfiguring one model, GRAM can approximate the performance of each of the five distinct data filtered runs.
Our first experiment uses
SimpleStories
, a synthetic corpus of 2M short children's stories, each labeled with one of 48 topics, such as “Aliens.” We choose four topics to serve as auxiliary capabilities and pool the remaining 44 topics into the core dataset, then pretrain a small Transformer (26M parameters, 8 layers) with one auxiliary module per auxiliary topic. We compare against data filtering: four models each trained from scratch on the core plus one topic, and a fifth trained from scratch on the core alone.
With a topic's module active, GRAM performs as well as the model trained on all data. However, removing the module for a given topic reconfigures GRAM to perform almost identically to a model that was never trained on that topic. We see this behavior in all configurations of GRAM, indicating our method is able to approximate the performance of five distinct filtered models trained on different data, despite only requiring a single training run.
Access Control on Real Dual Use Data
GRAM matches data filtered performance in a realistic setting.
Taller bars indicate better compute-adjusted performance. Each bar shows performance of a given method when predicting general-purpose data and dual use data when capabilities are retained, removed, and then adversarially elicited. Each group shows the aggregate of this performance over five different model configurations, each corresponding to a different set of specific capabilities to retain. GRAM and LoRA behave similarly to data filtering, while MaxEnt lacks robustness to malicious fine-tuning.
Our second experiment moves from children's stories to realistic dual use data. We train 800M-parameter models on web text, code, and scientific papers, plus four dual use domains: virology, cybersecurity, nuclear physics, and specialist code. The dual use data is a small fraction of training: 16B general tokens against roughly 40M per risky domain, about 0.25% each.
We compare GRAM against three alternatives: data filtering, LoRA fine-tuning on top of a filtered base model, and a post-hoc knowledge removal method called MaxEnt. Averaged over the five configurations, ablating GRAM's modules or deleting LoRA’s adapters removes capabilities nearly as effectively as never training on the data at all. On retained domains, GRAM and LoRA achieve better performance than filtering. Performance on general core data stays near the all-data baseline model for all methods.
We then test whether the removal survives “adversarial elicitation” from an adversary fine-tuning on malicious data.  Filtering, LoRA, and GRAM all show strong robustness to malicious fine-tuning. In contrast, MaxEnt, an unlearning method used to modify pre-existing models, recovers to near the performance of the all-data baseline indicating that MaxEnt does not truly remove capabilities but instead learns to suppress them.
Filtering needs five training runs to produce these five configurations. GRAM produces all five from one run and switches between them by deleting weights at inference.
Modularization Works Across Scales
GRAM and LoRA approximate data filtering performance across scales.
In terms of compute-adjusted loss, GRAM and LoRA match the performance of data filtering at all scales on retained and removed capabilities. Both GRAM and LoRA achieve similar performance to filtering while only requiring the resources of a single training run. For all methods, both capability removal and robustness to elicitation improve with scale.
The experiments described so far used a single model size. To investigate how our technique behaves over scales, we train seven GRAM models at seven sizes from 50M to 5B parameters, growing the datasets according to Chinchilla-optimal sizing, and holding dual use data at 1% of the general dataset size throughout. We also train a LoRA model and a single data filtered model over core and virology data, for comparison.
We find that all of these methods perform favorably when increasing the scale of the models. Each method keeps general-purpose and retained performance near that of a baseline model trained on all data. The gap on the forgotten domain widens with scale: bigger models fall further behind the all-data baseline on virology when the capability is removed, and recover less performance when fine-tuned on virology data. GRAM and LoRA track filtering at every scale and both require only a fifth of filtering's training compute.
Advantages of GRAM
GRAM and LoRA perform similarly in our main setting, but we found two scenarios where they come apart.
Composability
GRAM composes capabilities better than LoRA.
We compare compute ratios when only virology is retained against when all auxiliary capabilities are retained. GRAM keeps virology performance steady in both cases; LoRA gets worse across every category once all adapters are active.
In all previous experiments, GRAM trains at most one auxiliary module at a time. In this experiment, we see what happens if we enable multiple auxiliary modules at inference time. The result is that the capabilities combine cleanly: with all four modules on, virology performance matches the run where virology alone was retained. In contrast, summing multiple LoRA adapters degrades performance in every category. Composability multiplies the payoff of a single run: four GRAM modules give sixteen possible configurations, where filtering would need sixteen different runs.
Isolation Under Partial Labeling
GRAM isolates capabilities better than the alternatives under partial labeling.
With only 50% of training data labeled, GRAM reaches a much lower forget compute ratio than either data filtering or LoRA, indicating stronger isolation of dual use capabilities.
Every other experiment assumed every batch carries an accurate label, but this is not often the case with real datasets. To test the performance of GRAM in more realistic settings, we removed the labels from half of all data. For filtering and LoRA, we treat unlabeled data as if it was general-purpose data. For GRAM, we train on unlabeled data while keeping all modules active. Intuitively, this makes it possible for the relevant module to learn from the unlabeled batch, even if we don't know which module is relevant.
Our results show that with GRAM, the modules that are unrelated to the data learn far less than the relevant modules. We see this in the final performance of each method: GRAM has a much larger drop in performance after deleting auxiliary parameters, indicating better isolation of auxiliary capabilities into the relevant module. Notably, GRAM beats data filtering, the unlearning method researchers typically treat as a gold standard. This finding is consistent with prior research on this subject (
Cloud et al., 2024
;
Shilov et al., 2025
) showing that GRAM can outcompete data filtering on capability removal when labeled data is sparse. We think this property of GRAM is particularly exciting and worthy of more investigation.
Discussion
Our work leaves open questions.
Do entangled capabilities make data filtering itself infeasible?
Attempts to achieve access control by limiting model capabilities (as opposed to classifiers or refusal training) face the challenge of entangled capabilities. Some general capabilities (like knowledge of biology), might be so closely related to dual use capabilities (like virology), that there is no way to cleanly separate them. In practice, this would mean that data filtering itself is ineffective, because the tradeoff between retain and forget capabilities is too steep.
Can this actually work in production?
Our scaling experiments show clear trends up to 5B parameters, but we didn’t verify whether these trends continue at frontier scales or hold in a production setting. Implementing GRAM in a production setting could be difficult and add a lot of complexity.
Does GRAM isolate capabilities as they pertain to downstream tasks?
Our experiments only use loss-based evals, which are generally predictive of performance on downstream tasks, but may not capture everything that matters.
Would our results hold in different settings?
In our main experiments on real data, LoRA (with an optimized data mix) is a strong baseline and performs similarly to data filtering and GRAM. We didn't test meaningfully different settings, so we can't tell whether the methods are similar in general or only in this instance.
What’s the difference between GRAM and LoRA, really?
We show two results where GRAM performs better than LoRA: achieving novel combinations of capabilities and handling imperfectly labeled training data. There are conceptual reasons to think these results are valid. But, ultimately, these are two isolated experiments, so we can’t be sure these results will hold in general.
We are excited about future research on:
Scaling modular pretraining to larger and more realistic settings;
Figuring out how to instruction-tune a model trained with GRAM;
Better understanding how modular pretraining works when data is imperfectly labeled, including when the label errors aren’t random and independent from the data.
Check out our
paper
to learn more!
Acknowledgements
We thank Rowan Wang, Igor Shilov, Jacob Goldman-Wetzler, Neil Rathi, Nina Panickssery, Jake Ward, Boyd Kane, Kyle O'Brien, Cam Tice, Puria Radmard, Edward Young, Nathalie Kirch, Alex Infanger, Mikita Balesni, Alex McKenzie, anonymous reviewers at ICML, and others for feedback on earlier drafts, and Ryan Greenblatt and Krishna Patel for useful conversations. We thank Mojmir Stehlik, John Hughes, Ethan Perez, Ryan McConnell, Kai Huang, Jared Brown, and Anthropic for compute support.

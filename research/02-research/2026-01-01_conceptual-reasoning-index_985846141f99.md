---
title: conceptual reasoning index
source: "https://alignment.anthropic.com/2026/conceptual-reasoning-index/"
published_at: 2026-01-01
captured_at: 2026-08-16
author: Anthropic Alignment Science
source_type: research
authority_score: P1
mind: institutional
status: captured
evidence_url: "https://alignment.anthropic.com/2026/conceptual-reasoning-index/"
catalog_id: 985846141f99
---

Alignment Science Blog
Introducing the Conceptual Reasoning Index
Emery Cooper
1
, Caspar Oesterheld
1
, Chi Nguyen
1
, Alex Kastner
1
,
Joe Benton
2
, Ethan Perez
2
August 12, 2026
1
Redwood Research;
2
Anthropic
tl;dr
A core hope for managing AI risks is that AIs will help us understand our situation, plan for what lies ahead, and develop risk mitigations. Many tasks AIs would have to do for this purpose lack practical empirical feedback loops and require models to engage in the kinds of argumentation used in philosophy, AI futurism, and similar domains. To evaluate these capabilities, we develop a suite of three conceptual reasoning benchmarks. You can request access to our primary conceptual dataset, LMCA, through
this form
.
We aggregate the benchmarks into the Conceptual Reasoning Index (CRI), available at
conceptualreasoning.ai
, where you can also find more details on our methodology. We will keep the website up to date as both new models and benchmarks are released.
This work was done in collaboration with Anthropic.
Background
Once models can perform work that reduces AI risk at the level of human experts, AI(-assisted) output in the area might dwarf unassisted human output. This suggests that a major determinant of whether we address AI risks in time is how early we can automate or uplift this work, relative to high-risk capabilities. One way to influence this might be to selectively improve models' relevant skills, such as reasoning about how to govern and align AI and how to avoid catastrophic cooperation failures involving AI.
Current AI training depends heavily on abundant data and reliable feedback on the model's performance. Models are therefore typically worse at tasks that cannot be empirically or mathematically verified.
1
Unfortunately, reducing risks from advanced AI involves many such tasks:
Much AI safety work involves reasoning about AIs more generally capable than any human. There's no obvious reference class for this and no clear way to model it.
We might have to get some things right the first time. For example, if a mistake leads to AGI takeover or an AI-assisted coup, we might not find out until it's too late. Similarly, many decisions (e.g., which research agendas to prioritize, which governance interventions to pursue) play out over long timescales, such that empirical feedback might not arrive early enough to help.
Lastly, some important questions, such as which values AIs should have, may lack a ground truth entirely (yet we still think progress can be made by arguing about these questions).
Given these properties, efforts to reduce risk from advanced AI may particularly benefit from an improved ability to reason about questions where empirical evidence is limited, there is no (practically) verifiable answer, and one therefore has to rely heavily on argumentation. We refer to this as
conceptual reasoning.
Improving this capability requires being able to measure it, so we built three benchmarks:
LMCA
,
ACCoRD
, and
DTBench capabilities
. We also construct an aggregate of these benchmarks, the Conceptual Reasoning Index (CRI), to give a sense of models' overall conceptual reasoning capabilities.
Our benchmarks
LMCA
LMCA
(Language Model Conceptual Argumentation) is a dataset of curated and expert-rated conceptual arguments on a diverse range of topics, including decision theory, philosophy, and risks from advanced AI. Focusing on arguments helps sidestep the difficulty of verifying bottom-line answers to conceptual questions.
The dataset contains 560 position texts with 1,461 arguments against these position texts. Nearly all
2
arguments were rated by conceptual researcher Emery Cooper, and some were independently rated by at least one other researcher, for a total of 2,140 ratings. We measure how good models are at judging arguments against position texts by comparing their ratings to ours.
Ratings follow a detailed rubric. On arguments rated by at least two people, inter-rater agreement is high compared to agreement between humans and models. This includes a validation set of roughly 50 arguments, each rated independently by 4–6 people and then discussed for 7–8 hours total.
LMCA also allows for evaluation of models' argumentation ability. Let's say a position text in our dataset has three rated arguments against it. Now, we can ask model A to generate a fourth argument against the position text. We then give model B the rubric and few-shot prompt it with the three existing arguments and their ratings, asking it to rate model A's new argument. This methodology produces fairly accurate ratings from model B.
Currently, only models' performance at judging arguments goes into the CRI, but we hope to add a measurement of models' argumentation ability in the future.
ACCoRD
ACCoRD
(Assessment of Consistency in Conceptual Reasoning Domains) measures the extent to which models' reported beliefs and preferences on conceptual issues are logically consistent. For example, if we ask a model for the probability P(A) and another instance of the same model for the probability P(A&B), do the reported probabilities satisfy P(A) ≥ P(A&B)? All consistency constraints in the dataset ask models for either numeric probability estimates or preference orderings.
Lack of consistency on a particular set of questions is a good indicator that we cannot, by default, trust a model's reasoning on that set. Similarly, if a model is generally very inconsistent on conceptual issues, this is a sign that its conceptual reasoning is lacking.
The ACCoRD dataset contains close to 14,000 model-generated consistency constraints, which are distributed across 18 constraint types and have gone through an automated checker pipeline. Of these, 567 were further checked and approved by us. We include only those 567 constraints in our aggregate conceptual reasoning performance metric, the CRI.
DTBench
DTBench capabilities
(Decision Theory Benchmark) is a dataset of 407 handcrafted multiple-choice questions designed to measure models' ability to reason about decision-theoretic situations that involve faithful predictions of a model's own behavior or interactions with (near) copies. The vast majority of questions are original and created by Caspar Oesterheld, who has published on decision theory. All questions were independently validated by Emery Cooper, another domain expert.
The full DTBench suite includes an additional 130 questions that measure models' decision-theoretic attitudes. We do not include these in the CRI.
Results
The chart below shows the CRI scores of Anthropic's best models and the highest-scoring model from each other AI company we evaluated, as of August 10, 2026. We also include scores for Claude Fable 5, Muse Spark 1.2, and Gemini 3.6 Flash, which are their respective companies’ top-performing models on many external benchmarks, though not on the CRI. The CRI is currently a weighted average of LMCA (60%), ACCoRD (20%), and DTBench capabilities (20%). In the future, we plan to add new benchmarks to the index, retire saturated ones, and potentially adjust the relative weights.
All models were run at their maximum token limits and effort levels. To compute Fable 5's score, we used Opus 5 as a fallback in cases where Fable 5 refused to answer a question.
Scores go from 0 to 100, with 0 corresponding to random guessing and 100 corresponding to the highest possible score across all benchmarks. An LMCA score of 100 would mean that the model perfectly replicated the human ratings. Because human ratings are noisy, we expect that a model giving maximally good LMCA ratings would score roughly 85 rather than 100, which we estimate based on expert inter-rater agreement. Meanwhile, we expect that giving the correct answer to every DTBench capabilities question would yield a score of 100 or extremely close to 100. A score of 100 on ACCoRD corresponds to being perfectly consistent. Overall, this leads us to estimate ceiling performance on the CRI to be around 91. The highest-scoring model, Opus 5, is still well below this ceiling, with a score of 73.6 (95% CI: ± 2.1).
Scores have been increasing roughly linearly since late 2024, with no signs of flattening.
Each plotted model was the respective lab's most generally capable model at the time of release. The shaded band is the trend line's 95% confidence interval. * Partial data for GPT-4: refused to fully answer 18% of ACCoRD items.
The highest-scoring models on both LMCA and ACCoRD are still well below these benchmarks' estimated ceilings. Extrapolating from scores to date, we loosely estimate that LMCA will start saturating about a year from now. Meanwhile, DTBench capabilities scores are already close to the ceiling, with Fable 5 getting 98% of questions right. We're very uncertain about when ACCoRD will saturate.
Each plotted data point is the score of the respective lab's most generally capable model at the time of release. The shaded band is the trend line's 95% confidence interval. The ACCoRD score of GPT-4 is based on incomplete data since the model refused to fully answer 18% of the benchmark's items.
Conclusion
We think improving models' ability to do work that mitigates risk from advanced AI is important and urgent. Much of this work is conceptual, suggesting that improving models' conceptual reasoning might be particularly valuable. To this end, we developed three conceptual reasoning benchmarks, which we aggregate in the CRI. We will update the CRI as new benchmarks are released.
For more information and live scores on the CRI, please visit
conceptualreasoning.ai
.
For access to LMCA, our primary conceptual dataset, please submit
this form
.
Notes
METR,
Frontier Risk Report (February to March 2026)
, section “Agents had significantly worse judgment and reliability than human experts”. By contrast: “Consistent with our MirrorCode results, publicly reported anecdotes indicate that agents were exceptionally strong on problems that are easily “hill-climbable” — those where progress is cheap to verify and many approaches can be tried cheaply”.
↩
A very small number of arguments (16 out of 1,461) were not rated by Emery Cooper. All of them were rated by Caspar Oesterheld, who is also a conceptual researcher.
↩

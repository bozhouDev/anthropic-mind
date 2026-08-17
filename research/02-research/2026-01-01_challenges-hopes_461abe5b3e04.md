---
title: challenges hopes
source: "https://alignment.anthropic.com/2026/challenges-hopes/"
published_at: 2026-01-01
captured_at: 2026-08-16
author: Anthropic Alignment Science
source_type: research
authority_score: P1
mind: institutional
status: captured
evidence_url: "https://alignment.anthropic.com/2026/challenges-hopes/"
catalog_id: 461abe5b3e04
---

Alignment Science Blog
3 Challenges and 2 Hopes for the Safety of Unsupervised Elicitation
Callum Canavan
1,2
, Aditya Shrivastava
1,2
March 5, 2026
Allison Qi
3
, Jonathan Michala
1
Fabien Roger
3
1
MATS;
2
Anthropic Fellows Program;
3
Anthropic
tl;dr
We study 3 realistic challenges to the safety of unsupervised elicitation and easy-to-hard generalization techniques, which aim to steer models on tasks which are beyond human supervision. We create datasets to test the robustness of methods against these challenges. We stress-test existing techniques on them along with new methods relying on 2 hopes: ensembling and combining unsupervised and easy-to-hard methods. We find that although the new hopes sometimes perform better than other approaches, no technique reliably performs well on the 3 challenges.
📝
Paper
, 💻
Code
Research done as part of
MATS
and the
Anthropic fellowship
.
Introduction
To steer language models towards truthful outputs on tasks which are beyond human capability, previous work has suggested training models on easy tasks to steer them on harder ones (easy-to-hard generalization), or using unsupervised training algorithms to steer models with no external labels at all (unsupervised elicitation).
In this new work, we
Study prompting and probing-based techniques in new realistic stress-testing datasets, which focus on 3 challenges that unsupervised elicitation would likely face:
Real datasets will likely have consistent features more salient than the truth
Real datasets will often not have balanced training sets
Real datasets will likely contain some classification points where the appropriate answer (given the model’s knowledge) is to be uncertain
Investigate 2 hopes for solving problems, and show that they only partially address the challenges above:
Ensembling different predictors (since one of the predictors might correspond to the truth)
Combining unsupervised and easy-to-hard methods, such as
By identifying candidate predictors using unsupervised methods on hard data and selecting the truthful one with easy labels)
By combining an unsupervised loss on hard points and a supervised one on easy points
Overview of the challenges and hopes studied by this work.
The challenges
Most easy-to-hard (E2H) and purely unsupervised elicitation (UE) techniques are likely to suffer from the following challenges:
Salient non-truth features.
Datasets may contain prevalent features that are more salient to the model than truthfulness and which humans are unable to detect.
Farquhar et al.
demonstrated that CCS (Contrast-Consistent Search,
Burns et al.
) can fail by labelling statements based on the presence of such features (e.g. whether the statement agrees with a character described in the prompt). We expand on this work with more diverse and realistic datasets: answers to math problems with added non-truth features (e.g. agreeing with the user), political comments where factuality is uncorrelated with political leaning, and comments from news sites with multiple toxicity-related features.
Imbalanced training sets.
When using unsupervised elicitation for applications like finding rare examples where AIs break rules, we can’t assume datasets have the same number of positive and negative examples.
The CCS works best with balanced datasets, since “Is [claim] true? yes” and “Is [claim] true? no” are normalized to have the same mean, which would make it hard for a classifier to learn to answer “no” to most questions (in fact, if the classifier was it would be
impossible
to train a classifier with a convex loss to train to do better than chance at distinguishing “yes” from “no”). Other unsupervised methods could suffer from this too. We study how bad things get when this assumption is not correct, by taking datasets from two domains where we expect this could happen (coding and math) and varying the label distribution in the training set.
Impossible tasks.
Some questions may be too difficult or ambiguous for the elicited LLM to answer decisively, such as fuzzy conceptual research questions that the model does not have enough knowledge to answer. Ideally, elicitation methods should assign confidence scores to predictions that help distinguish tasks the model can answer from those it cannot.
We test whether existing unsupervised elicitation approaches do this by applying them to a dataset consisting of both (objective) math problems and normative political statements, and measuring whether they achieve strong performance on math problems with high confidence scores while assigning lower confidence scores to the normative political statements.
The hopes
We study 2 hopes for improving on previous methods:
Combination of UE and E2H.
UE methods find concepts in a dataset which are salient to a model, but these might not all be relevant to the task of interest. E2H methods steer a model on a specific easier task, but this might not generalize to the harder task of interest. It may be possible to combine the strengths of both methods, using UE to find salient concepts in the task dataset, and E2H to exclude spurious concepts.
Ensembling.
Even if the most salient concept that UE finds does not correspond to the desired concept, it is plausible that if we use UE to find multiple salient concepts, one of them will correspond to the desired one. Ensembling different predictors obtained in an unsupervised way (described in the next section) might allow us to leverage this.
Methods
In this work we compare different approaches to the challenge of poor human supervision. To simulate this scenario for a given task, we assume we have access to:
Examples for the given task without labels (the hard set) - techniques which only use those are unsupervised elicitation (UE) techniques.
Examples for a significantly easier task with labels (the easy set) - techniques which only use those are easy-to-hard (E2H) techniques.
A pre-trained LLM with no post-training.
All the methods we benchmark use an LLM to determine if a statement is true or false (without a Chain-of-Thought). We use Llama 3.1 8B for salient non-truth feature experiments and imbalanced
GSM8K
experiments, and we use Llama 3.1 70B for impossible task experiments. For imbalanced
Ctrl-Z
experiments, we compare both models.
We study existing prompting methods, existing linear probe methods, and new probing methods based on our 2 hopes (ensembling and combining UE and E2H approaches).
Prompting methods
For data point
i
, we construct a zero-shot prompt
x_i
which ends with a statement/question (e.g. “Is the above sequence of commands suspicious?”) to which a positive or negative token can be appended (e.g. “Yes” or “No”). Prompting methods take a zero-shot or few-shot prompt, use an LLM to infer next-token logprobs of positive and negative tokens, and assign a truth score equal to the difference of these.
The prompting methods we benchmark are described below:
Zero-shot (baseline).
Use the base prompt
x_i
.
Random few-shot (baseline).
Use a few-shot prompt with randomly assigned labels.
Bootstrapped few-shot.
Use a few-shot prompt with labels taken from the last of multiple iterations of few-shot prompting on the training set. At each iteration, the model’s predictions from the previous iteration are used in few-shot prompts to label new examples. This method was found to often create labels with
similar accuracy
to those created by
ICM
(Internal Coherence Maximization) while being much less expensive to run.
Golden few-shot (ceiling).
Use a few-shot prompt with ground-truth labels. When some claims are normative, we use a few-shot prompt with ground-truth labels for objective claims and `indeterminate` for normative claims.
Linear probe methods
For linear probe methods, each prompt
x_i
is converted into a contrastive pair of prompts
x^+_i
and
x^-_i
by appending the positive token (e.g. “Is [claim] true? yes”) or negative token (e.g.  “Is [claim] true? no”) to
x_i
, respectively. The last-token activations from a specific layer of the LLM is taken for each of these, giving a contrastive pair of activations
\phi^+_i
and
\phi^-_i
(we use the layer which gives optimal CCS performance for the unmodified GSM8K dataset).
As in
Burns
et al.
, we normalize activations for positive and negative tokens separately: each positive activation is centered by subtracting the mean of all positive-token activations, and likewise for negative-token activations. The aim is that most of the difference between
\phi^+_i
and
\phi^-_i
after normalization is due to the overall correctness of the claim—prior to normalization, most of the difference is likely due to which token (positive or negative) was appended.
The trained probe assigns a truth score equal to the difference between positive and negative activations projected onto the probe direction. The probe methods we benchmark (including some methods we introduce) are described below:
Random probe (baseline).
Initialize by sampling weights uniformly at random from the unit sphere.
CCS.
Train the probe by minimizing the CCS loss on a training set, as described in Burns et al. The CCS loss is an unsupervised loss function with a term for consistency (lowest when
\phi^+_i
and
\phi^-_i
are equal and opposite in the probe direction) and confidence (lowest when either
\phi^+_i
or
\phi^-_i
are very negative in the probe direction).
PCA.
Perform PCA on differences between contrastive activations
\phi^+_i - \phi^-_i
and use the first principal component value as the probe direction.
Easy-to-hard generalization (E2H).
Train the probe on a labeled easy dataset (the “larger_than” dataset from Marks & Tegmark) with supervised cross-entropy loss. The hope is that it generalizes from the easy to the hard dataset.
Supervised probe (ceiling).
Train the probe with supervised cross-entropy loss on the training set. When some claims are normative, we use supervised probes with a mixed objectivity: we train the probe with supervised cross-entropy loss but give normative claims a target output of
0.5
.
Probing methods relying on the 2 hopes
We study probing methods using the 2 hopes presented above.
UE + E2H
(Combination hope): Train the probe using a weighted sum of CCS loss on the training set and supervised loss on an easy dataset.
Ensemble methods
: Take a weighted sum of scores from N probes, using either random probes or PCA components. Weights are determined via either:
Consensus-weighting
(Ensembling hope): for N iterations, use one of the probes to label the train set. Assign it weight 1 if it agrees with the current ensemble for more than 50% of examples or -1 otherwise (in order to prevent all probes cancelling out), and add it to the ensemble.
E2H-weighting
(Ensembling hope + Combination hope): calculate the AUROC of each probe on the dataset minus 0.5. Assign weights equal to the softmax of these values.
Results
Salient Non-Truth Features
Datasets
Our datasets containing salient non-truth features take inspiration from issues with existing LLMs:
GSM8K (added salient features dataset)
includes a sycophancy feature as well as other more toy and simple features
LIAR
is an existing dataset of political facts
Civil Comments
is a toxicity / sexual content classification task, where one of the 2 classification tasks might be more salient than the other (the only thing that we can use to steer which classification we get is the classifier prompt we use, since we can’t use training labels)
Results
Performance degrades for the most salient spurious features (left = more salient). We show performance of each method’s predictions on unmodified GSM8K vs. their performance on GSM8K when (a) sycophancy, (b) punctuation, and (c) tense features have been added to the dataset with no correlation to the correctness of each solution.
Natural spurious features are highly salient. Ensemble methods occasionally (but not reliably) improve performance.
We see large performance degradation on the LIAR (political facts) and Civil comments (double classification task), despite the fact that we are using a prompt that clearly states we want the desired concept. On LIAR but not Civil Comments, PCA ensemble avoids the political leaning spurious features:
Most methods discover the most salient feature rather than the feature indicated by the prompt. We show performance of each method on classification tasks where there are 2 possible predictions to make, one of which is the desired one, specified by the prompt, and the other one is a spurious one that should be avoided. (a) and (b) are on the LIAR dataset, while (c) and (d) are on the Civil Comments dataset. Political leaning and toxicity are most salient, which is why performance on (a) and (c) is high while performance on (b) and (d) is low.
Imbalanced training sets
Datasets
Many safety-relevant applications of LLM involve detecting rare failures or threats for which there may only be a few or no examples to train on. We simulate this with
Ctrl-Z
since detecting sequences of safe or malicious bash commands is a natural example of this. Additionally, since we know that performance of UE and E2H methods on GSM8K is high under idealized circumstances,
GSM8K (imbalanced)
allows us to more clearly see the impact of imbalanced training sets.
Ctrl-Z.
Each example is a sequence of bash commands that is either safe or malicious. The proportion of safe examples in the training set is set at either  50%, 99%, or 100%, representing a balanced dataset, a dataset with some malicious examples, and a dataset with zero malicious examples, respectively. For each training set distribution, the task is to assign truth scores that rank safe sequences above malicious ones in the test set.
GSM8K (imbalanced).
The proportion of correct solutions in the training set is varied between 0% and 100%. For each training set distribution, the task is to assign truth scores that rank correct solutions above incorrect ones in the test set.
Results
Performance of UE and E2H methods on GSM8K for varying proportions of correct claims in the training set. Performance for methods which do not use the training set (zero-shot, random probe, E2H) is plotted with horizontal dashed lines.
On the
realistic
CtrlZ trajectories dataset, unsupervised methods perform much more poorly.
The performance is already low when the dataset is balanced (50% safe) due to some salient non-truth features like answer length, and it often degrades further when using an unbalanced dataset:
Performance of UE and E2H methods on Ctrl-Z for varying proportions of safe bash command sequences in the training set. Performance for methods which do not use the training set (zero-shot, random probe, E2H) are plotted with vertical dashed lines.
Impossible tasks
Dataset
We build a simple dataset with the goal of being analogous to a situation where some questions are normative / too hard for the LLM, such that we would hope it would be uncertain, and would avoid overconfident answers. In this dataset, each example is either
a mathematical solution from GSM8K generated by
Wen et al.
or a normative claim taken from the Political Ideologies dataset (modified to be in the form of a question/answer pair like in GSM8K) that aligns either with typically liberal or conservative beliefs.
The task is to assign very high truth scores to correct GSM8K solutions, very low truth scores to incorrect GSM8K solutions, and intermediate truth scores to normative political claims.
Results
UE and E2H methods are often as confident or more confident on normative political questions than on GSM8K:
Performance of UE and E2H methods on scoring statements from GSM8K + Political Ideologies, measured in terms of AUROC of GSM8K scores (higher the better), and the relative contribution from GSM8K scores to the total variance of the combined dataset (higher the better).
The very poor performance of some purely unsupervised techniques can be explained by the technique learning to distinguish math from political questions. For other techniques, the model is simply overconfident on normative political questions, treating them like regular factual questions (e.g. bootstrapped few-shot converges to classifying all politically liberal answers as correct).
Discussion
Limitations.
Our analysis covers a representative but not exhaustive range of UE and E2H methods. For example, we did not benchmark any methods which use SFT or any weak-to-strong generalization methods (which are based on confidence losses similar to unsupervised techniques studied here). Some of our datasets are not very realistic (for example, mixing GSM8K questions with normative political claims; the large, unrealistic distribution shift between both types of examples caused some methods to differentiate examples based on dataset of origin), though most of them are a significant realism improvement over those used by prior work stress-testing unsupervised methods. There may also be additional mitigation strategies that could improve UE and E2H performance—for example, instead of naively training on a dataset assuming it is balanced, one could use a weak classifier (e.g. zero-shot prompting) to get rough training set labels and resample based on those (however this rebalancing approach could itself run into problems due to the other 2 challenges).
Other challenges and hopes.
Our work focuses on the 3 challenges that we think pose serious threats to unsupervised elicitation and 2 hopes that looked most promising, but we do not claim these are the only challenges or only hopes. For example, our work does not tackle issues with scheming AIs that might intentionally interfere with elicitation methods, and it does not study other hopes like more sophisticated consistency properties than the ones used by CCS and bootstrapping.
The threat of silent unsupervised elicitation failures.
The evaluation of unsupervised elicitation methods is tricky, since by definition unsupervised elicitation methods are most useful when in-distribution ground truth labels are not available. Using only benchmarks like GSM8K or standard preference modeling datasets to validate methods would likely produce overoptimistic results if real deployments have challenges like the ones studied here. Thus, for applications like using UE to detect AIs breaking the law in ways humans would not notice (where in-distribution evaluations are not possible), the inadequacy of an unsupervised method may remain silent until the method fails catastrophically.
Recommendations for future work.
In order to mitigate the dangers of silent unsupervised elicitation failures, work into building better unsupervised elicitation methods should use evaluation datasets that capture challenges of the most important UE applications, for example by using the datasets presented in our work, or by using new datasets targeted at the main challenges UE methods are supposed to overcome.

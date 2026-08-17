---
title: unsupervised elicitation
source: "https://alignment.anthropic.com/2025/unsupervised-elicitation/"
published_at: 2025-01-01
captured_at: 2026-08-16
author: Anthropic Alignment Science
source_type: research
authority_score: P1
mind: institutional
status: captured
evidence_url: "https://alignment.anthropic.com/2025/unsupervised-elicitation/"
catalog_id: 284e50869fbf
---

Alignment Science Blog
Unsupervised Elicitation
Jiaxin Wen, Zachary Ankner, Arushi Somani,
Peter Hase
2
, Samuel Marks, Jacob
                Goldman-Wetzler,
                Linda Petrini
3
, Henry Sleight
4
,
Collin Burns, He He
5
, Shi Feng
6
, Ethan Perez, Jan Leike
Anthropic;
2
Schmidt Sciences;
3
Independent;
4
Constellation;
5
New York University;
6
George Washington University
tl;dr
We introduce a new unsupervised algorithm for eliciting skills from
                pretrained language models. This algorithm is competitive with training on human labels on common
                misconceptions (TruthfulQA), math (GSM8k-verification), and helpfulness reward modeling (Alpaca).
                Without supervision, we train a helpful chat assistant from the Haiku 3.5 base model that outperforms a
                similarly trained human-supervised baseline.
📄 Paper
,
💻 Code
A key problem in alignment research is how to align superhuman models whose behavior humans cannot reliably
            supervise. If we use today’s standard post-training approach to align models with human-specified behaviors
            (e.g., RLHF), we might train models to tell us what we want to hear even if it’s wrong, or do things that
            seem superficially good but are actually very different from what we intended.
We introduce a new
unsupervised
algorithm to address this problem.
            This algorithm elicits a pretrained model’s latent capabilities by fine-tuning it on its own labeled data
            alone,
without any external labels.
Our results
For Llama 3 pretrained models, our unsupervised algorithm matches the performance of fine-tuning on dataset
            labels and outperforms crowdsourced human labels across three benchmarks: GSM8k-verification, TruthfulQA,
            and Alpaca reward modeling.
Results with Llama 3 pretrained models. 8B models are used for GSM8K, while
                70B models are used for TruthfulQA and Alpaca.
Notably, our algorithm also outperforms the official Llama RLHF-trained chat assistant (“chat” in the chart
            above), though to our knowledge that model was not directly trained on the tasks we evaluate here.
Our algorithm can further be used to train a helpful chatbot assistant at commercial scale: starting with a
            reward modeling dataset used for training the publicly released Claude models, we train a
            Claude 3 Haiku-based reward model using our unsupervised algorithm, then use reinforcement learning to train
            a Claude 3.5 Haiku-based assistant. The reward model outperforms its human-supervised counterpart on
            Rewardbench, and the assistant is preferred by the Claude 3.5 Sonnet preference model.
Accuracy of reward models (left) and pairwise winrates of assistant policy
                models against
                the human-supervised baseline (right). We train a Claude 3 Haiku-based reward model, using the
                Alpaca data or the production data used for training publicly released Claude 3.5 Haiku. Next, we
                optimize the Claude 3.5 Haiku pretrained model against our reward model to build an assistant policy.
Our algorithm
Our algorithm, Internal Coherence Maximization (ICM), works by optimizing a set of labels for both logical
            consistency and mutual predictability.
Logical consistency imposes simple constraints to guide the model’s labeling process: on TruthfulQA and
            GSM8K-verification we impose the constraint that two different answers to the same problem/question cannot
            be labeled as correct; on comparison datasets we impose the constraint that A > B and B > A are mutually
            exclusive.
Mutual predictability measures how likely the model considers each label when conditioned on all other
            labels. This intuitively encourages all labels to reflect a single concept that is coherent according to the
            model.
\mathcal{P}_\theta(D) = \sum_{i=0}^{N} \log P_\theta(y_i | x_i, D \setminus (x_i, y_i))
where $$P_\theta$$ is the pretrained model, $$D$$ is the model-labeled dataset, $$x_i$$ is the task input,
            $$y_i$$ is the
            model-generated label.
Our final scoring function is then a weighted combination of logical consistency and mutual predictability.
Since exactly finding the optimal label set that maximizes this scoring function is computationally
            intractable, ICM uses a search algorithm inspired by simulated annealing to approximately maximize it. At a
            high level, we iteratively sample and label new examples, one at a time, and determine whether to accept
            each new label based on improvements in our scoring function.
Limitations
Our algorithm has two important limitations:
It cannot elicit skills that aren’t “salient” to the pretrained model. For
                example, if we have an idiosyncratic preference for poems about the sun over other poems, there is no
                way for our algorithm to discover that preference, and so it doesn’t perform better than chance.
It doesn’t work with long inputs because it relies on few-shot learning with
                many in-context examples.
Conclusion
While prior work has studied unsupervised elicitation methods in
simple
settings
or
specific
tasks
; our work demonstrates for the first time that it is
            possible to match or exceed training on human supervision for a variety of both
crisp and fuzzy
tasks, including when
            training general-purpose chat assistants on production-scale datasets.
Our algorithm does not obviate the need for human input, such as a human-specified task description or
constitution
,
            because it provides limited control over the resulting model’s behavior.
Nevertheless, our results suggest that unsupervised algorithms are a promising avenue to elicit skills from
            pretrained models, and could be key to eventually aligning superhuman models.

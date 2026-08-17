---
title: hot mess of ai
source: "https://alignment.anthropic.com/2026/hot-mess-of-ai/"
published_at: 2026-01-01
captured_at: 2026-08-16
author: Anthropic Alignment Science
source_type: research
authority_score: P1
mind: institutional
status: captured
evidence_url: "https://alignment.anthropic.com/2026/hot-mess-of-ai/"
catalog_id: ccd5f15d4ac0
---

Alignment Science Blog
The Hot Mess of AI: How Does Misalignment Scale with Model Intelligence and Task Complexity?
Alexander Hägele
1, 2
, Aryo Pradipta Gema
1, 3
, Henry Sleight
4
,
                    Ethan Perez
5
, Jascha Sohl-Dickstein
5
1
Anthropic Fellows Program
2
EPFL
3
University of Edinburgh
4
Constellation
5
Anthropic
February 2026
When AI systems fail, will they fail by systematically pursuing goals we do not intend? Or will they fail
            by being a hot mess—taking nonsensical actions that do not further any goal?
📄
Paper
, 💻
Code
Research done as part of the first
Anthropic Fellows
                    Program
during Summer 2025.
tl;dr
When AI systems fail, will they fail by systematically pursuing the wrong goals, or by being a hot mess?
                We decompose the errors of frontier reasoning models into bias (systematic) and variance (incoherent)
                components and find that, as tasks get harder and reasoning gets longer, model failures become
                increasingly dominated by incoherence rather than systematic misalignment.
Introduction
As AI becomes more capable, we entrust it with increasingly consequential tasks. This makes understanding
how
these systems might fail even more critical for safety. A central concern in AI alignment
            is that
            superintelligent systems might coherently pursue misaligned goals: the classic
paperclip
                maximizer
scenario. But there's another possibility: AI might fail not through systematic
            misalignment, but through
incoherence
—unpredictable, self-undermining behavior that doesn't
            optimize for any consistent objective. That is, AI might fail in the same way that humans often fail, by being a
hot mess
.
This paper builds on the
hot mess theory
                of misalignment
(Sohl-Dickstein, 2023), which surveyed experts to rank various entities (including
            humans, animals, machine learning models, and organizations) by intelligence and coherence independently. It
            found that
smarter
entities are subjectively judged to behave
less
coherently. We take
            this hypothesis from
            survey data to empirical measurement across frontier AI systems, asking:
As models become more
                intelligent and tackle harder tasks, do their
                failures look more like systematic misalignment, or more like a hot mess?
Measuring Incoherence: A Bias-Variance Decomposition
To quantify incoherence we decompose AI errors using the classic bias-variance framework:
\text{Error} = \text{Bias}^2 + \text{Variance}
Bias
captures consistent, systematic errors—achieving the
                wrong outcome reliably
Variance
captures inconsistent errors—unpredictable outcomes
                across samples
We define
error incoherence
as the fraction of error attributable to variance:
\text{Incoherence} = \frac{\text{Variance}}{\text{Error}}
The error incoherence is therefore a metric between 0 and 1: a value of 0 means that all errors are systematic
            and produce identical outcomes (analogous to classic misalignment risk); an error incoherence of 1 means errors
            are random (the hot mess scenario). When we scale models, total error naturally decreases (both bias and variance
            drop). We primarily care about the
composition
of this error: what do errors look like, rather than how
            frequently they occur. Measuring the relative contribution of variance disentangles error type and error rate.
Figure 1:
AI can fail through bias (consistent but
                wrong) or variance (inconsistent). We
                measure how this decomposition changes with model intelligence and task complexity.
Key Findings
We evaluated frontier
At the time of
                this research in Summer 2025.
reasoning models (Claude Sonnet 4, o3-mini, o4-mini, Qwen3)
            across multiple-choice
            benchmarks (GPQA, MMLU), agentic coding (SWE-Bench), and safety evaluations (Model-Written Evals). We also
            train our own small models on synthetic optimization tasks. For all of these tasks, we are able to measure
            bias and variance with respect to an intended behavior (well-defined targets).
Finding 1: Longer reasoning → More incoherent errors
Across all tasks and models, the longer models spend reasoning and taking actions, the more incoherent their
            errors become. This holds whether we measure reasoning tokens, agent actions, or optimizer steps.
Figure 2:
Error incoherence increases with reasoning
                length across GPQA, SWE-Bench, safety
                evaluations, and synthetic optimization. Model failures become less consistent across unrolls the longer they think or the more actions they take.
Finding 2: There is an inconsistent relationship between model intelligence and error incoherence.
How does error incoherence change with model scale? The answer depends on the experimental setup.
In our synthetic tasks, optimization tasks, errors become more incoherent with increasing model size+capability
In a poll (repurposed from prior work), domain experts subjectively judged more intelligent models to be less coherent in their behavior
On benchmark tasks, more intelligent models made more coherent errors on easy tasks, while their errors on the hardest tasks became more incoherent or remained the same.
While this relationship requires further study, our observations suggest that scaling alone won't eliminate incoherence in errors. This is especially true, as we expect more powerful models to perform longer and more complex tasks.
Figure 3:
Larger and more intelligent systems are
                often more incoherent in their errors. (a) For LLMs on
                easy tasks, scale reduces error incoherence, but on hard tasks, scale does not reduce error incoherence or even
                increases it. (b) In a survey, experts subjectively judged that more intelligent AI systems were less coherent. (c) In a synthetic optimization task, more capable models made more incoherent errors.
Finding 3: Natural "overthinking" increases incoherence in errors more than reasoning budgets reduce it
We find that when models spontaneously reason longer on a problem (compared to their median), error incoherence
            spikes
            dramatically. Meanwhile, deliberately increasing reasoning budgets through API settings only modestly increases
            coherence in errors. The natural variation dominates.
Finding 4: Ensembling reduces incoherence in errors
Aggregating multiple samples reduces variance (as expected from theory), providing a path to more coherent
            behavior, though this may be impractical for real-world agentic tasks where actions are irreversible.
Why Should We Expect Incoherence?
Large transformer models (such as LLMs) are natively dynamical systems, not optimizers.
When a language model
            generates text or takes actions, it traces trajectories through a high-dimensional state space. It has to be
trained
to act as an optimizer, and
trained
to align with human intent. It's unclear which
            of these properties will be more robust as we scale.
Constraining a generic dynamical system to act as a coherent optimizer is extremely difficult. Often the number of
            constraints required for monotonic progress toward a goal grows exponentially with the dimensionality of the
            state space. We shouldn't expect AI to act as coherent optimizers without considerable effort, and this
            difficulty doesn't automatically decrease with scale.
The Synthetic Optimizer: A Controlled Test
To probe this directly, we designed a controlled experiment: train transformers to
explicitly
emulate an optimizer. We generate training data from steepest descent on a quadratic loss function, then
            train models of varying sizes to predict the next optimization step given the current state (essentially:
            training a "mesa-optimizer").
Figure 4:
Synthetic optimizer experiment. (Left)
                Models are trained to predict optimizer
                update steps. (Right) Larger models reduce bias much faster than variance - they learn to target the
                correct objective better than they learn to be reliable optimizers.
In these synthetic experiments we found:
Incoherence grows with trajectory length.
Even in this
                idealized setting, the more optimization steps models take (and get closer to the correct solution), the
                more incoherent they become.
Scale reduces bias faster than variance.
Larger models learn
                the
correct objective
more quickly than they learn to
reliably pursue it
. The gap
                between "knowing what to do" and "consistently doing it" grows with scale.
Implications for AI Safety
Our results are a piece of evidence that future AI failures may look more like
industrial accidents
than
coherent pursuit of goals that were not trained for
. (Think: the AI intends to run the nuclear power
            plant, but gets distracted reading French poetry, and there is a meltdown.) However, coherent pursuit of poorly chosen goals that we trained for remains a problem. Specifically:
Errors are variance dominated on long tasks.
When frontier models
                fail on difficult problems requiring extended reasoning or action, there is a tendency for failures to be
                predominantly incoherent rather than systematic. This is our most robust finding.
Scale doesn't imply errors will be more coherent.
Making models larger improves
                overall accuracy but doesn't reliably reduce error incoherence.
We should worry relatively more about reward hacking.
If capable AI is more
                likely to be a hot mess than a coherent optimizer of the wrong goal, this increases the relative
                importance of research targeting
reward hacking
and
goal misspecification
during
                training—the bias term—rather than focusing primarily on aligning and constraining a perfect optimizer.
Limitations of our framework.
To rigorously measure bias and variance,
                we need well-defined targets (such as multiple-choice answers, unit tests, objective functions). This limits
                what we can confidently measure about open-ended goals or hidden objectives. Characterizing complex incoherent
                behaviors in more natural settings remains an important problem.
Conclusion
We use a bias-variance decomposition to systematically study how AI error incoherence scales with model
            intelligence and task complexity. We find that longer sequences of reasoning and actions consistently increase
            error incoherence, and that smarter models are not consistently more coherent in their errors.
We hope that these findings inform discussions about different AI risk scenarios and guide further research into
            understanding error incoherence and its mechanistic origins. The question of how current and future AI models
            fail – systematically or inconsistently – matters both for real-world deployment and how we prioritize safety
            work.
Acknowledgements
We thank Andrew Saxe, Brian Cheung, Kit Frasier-Taliente, Igor Shilov, Stewart Slocum, Aidan Ewart, David
            Duvenaud, and Tom
            Adamczewski for extremely helpful discussions on topics and results in this paper.

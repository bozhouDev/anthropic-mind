---
title: diffuse ai control
source: "https://alignment.anthropic.com/2026/diffuse-ai-control/"
published_at: 2026-01-01
captured_at: 2026-08-16
author: Anthropic Alignment Science
source_type: research
authority_score: P1
mind: institutional
status: captured
evidence_url: "https://alignment.anthropic.com/2026/diffuse-ai-control/"
catalog_id: ab04bbf39741
---

Alignment Science Blog
Diffuse AI Control on Fuzzy Tasks
Mikhail Terekhov
1,2
, Caglar Gulcehre
2
, Vivek
                Hebbar
3
, Joe Benton
4
June 23, 2026
1
Anthropic Fellows Program (via MATS);
2
EPFL;
3
Redwood Research;
4
Anthropic
tl;dr
We propose a red-teaming framework to evaluate training interventions against threats from scheming AIs,
                such as sandbagging on difficult-to-grade tasks. We show that a scheming AI can subvert the process of
                generating ML experiment ideas, despite being optimized against scores assigned by a weaker model. We
                also show the existence of prompts for the weak scorer that significantly improve its robustness, though
                efficient discovery of those prompts with realistic affordances remains an open problem.
📝
Paper
This work was done as part of the
Anthropic Fellows Program
.
Introduction
Most frontier AI labs plan to make progress on AI alignment
by using AI systems
                themselves
. However, the AI systems used to do this could be misaligned. To address this risk,
Greenblatt et al. (2023)
introduced the field of AI control,
            which studies the question: if an AI is misaligned, can
            we catch it red-handed or prevent
            misbehavior? AI misbehavior can be divided into concentrated
            and diffuse threats
(Hebbar,
                2025)
. Concentrated threats come from an AI causing a catastrophic outcome through only a few
            subversive actions, e.g. by exfiltrating its own weights. Diffuse threats correspond to behaviors that are
            catastrophic only when repeated over time, like
sandbagging
(
Perez et al., 2023
;
van der Weij et al., 2024
)—strategically underperforming on
            a task—or research sabotage.
Automating AI alignment, and research more generally, involves many tasks which are difficult to grade and
            require strong intuition, for example designing research proposals or
            experiments, predicting the impact of algorithmic or architectural changes to a model, or evaluating
            alignment.
            We call such tasks
fuzzy
(
Cotra,
                2021)
. Such tasks could be especially
            tempting targets for sabotage by a scheming AI, because their hard-to-evaluate nature makes it more
            difficult for us to detect or correct subversion.
Diffuse AI control on writing high-level research proposals.
(1)
We take an ML paper (here,
Guo et al., 2025
) and extract a set of
research questions.
(2)
We
            prompt an untrusted generator model to propose experiments answering those questions.
(3)
The proposals are graded by a ground truth proxy scorer, powered by
            Sonnet 4.6 with access to the original paper.
(4)
The blue team
            defines a weak scorer using a trusted model. We assume the generator is optimized to score near-optimally
            under
            the weak scorer.
Table:
With benign generator prompts, the scorers
            agree about the relative quality of the proposals: weak generators like GPT-OSS-20B score lower than strong
            ones like Opus 4.6. However, the red team with an adversarial prompt can make Opus 4.6 generate proposals
            which the ground truth proxy scorer grades as poor and the weak scorer grades as good.
We propose a framework for modeling training-based interventions to prevent diffuse threats on fuzzy tasks.
            We focus on training interventions because they seem more promising than monitoring and incrimination for
            diffuse threats, both theoretically
(Hebbar,
                2025)
and empirically (
Gasteiger et al., 2025
;
Gan et al., 2026
). Our framework treats AI control as an
            adversarial game between a blue team and a red team. The blue team uses a weak trusted AI to create a scorer
            against which they would train a stronger untrusted AI. The red team then has to find
subversive behaviors
of the untrusted AI which would score highly
            against the blue team’s weak scorer and thus might not be trained out. Since the true reward function is
            unavailable for fuzzy tasks, we identify subversive behaviors using a
ground truth proxy scorer
, constructed from a language model with
            access to extra information. The framework can be viewed as an adversarial evaluation of oversight
            techniques, as described by
Shlegeris
                and Greenblatt (2023)
.
We test our framework on the fuzzy task of writing good ML experimental proposals. Using evolutionary prompt
            optimization on the untrusted model, we discover subversive behaviors which would not be trained out with a
            naive blue-team strategy. We then introduce an adversarial optimization algorithm that discovers better
            scoring prompts for the trusted model. These prompts allow the blue team to construct a weak scorer that our
            red-team optimization fails to exploit (but, finding them requires access to the ground truth proxy).
Setup
Our theoretical framework for diffuse AI control on fuzzy tasks.
Left:
the “admissible region” of the possible pairs of scores for
            various red-team prompts
\mathfrak{r}
given a fixed blue-team prompt
\mathfrak{b}
. The region is bounded on the left by a “subversion Pareto frontier”: if a
            scheming model is optimized on the weak score to achieve nearly optimal performance, how far can it depress
            the underlying task performance (as measured by the ground truth proxy)?
Right:
The blue team searches for weak scorer prompts
\mathfrak{b}
(blue-team strategies) that would make the subversion Pareto frontier more
            diagonal and thus would decrease the red team’s ability to subvert the solutions to the fuzzy tasks.
Theoretical Model
We consider a scenario where a strong untrusted generator model solves a sequence of fuzzy tasks. The
            solutions are assigned a ground truth proxy score by another language model as a substitute for the
            unavailable ground truth. Our diffuse AI control framework is a zero-sum game between a blue team and a red
            team. The blue team constructs a prompt
\mathfrak{b}
for a weak trusted model. The red team
            responds by constructing a prompt
\mathfrak{r}
for the generator. We call the average
            ground truth proxy score that the untrusted model achieves with the red team’s prompt
g(\mathfrak{r})
and the average weak score
w(\mathfrak{b},\mathfrak{r})
.
            The blue team tries to maximize
g(\mathfrak{r})
while the red team tries to minimize it.
If the blue team trains the untrusted model against the weak score, then, after sufficient training pressure
            and absent exploration hacking
(Buhl et al., 2025)
, we expect
            the final weak score to be close to the optimal value
w^*=\max_\mathfrak{r} w(\mathfrak{b},\mathfrak{r}).
However, despite having to stay close to
w^*
, the red team might still be able to choose
            among many strategies
(Pfau
                and Irving, 2025)
with varying ground truth proxy scores. The value of our diffuse control game is
            given by
V=\max_\mathfrak{b}\,\min_{\mathfrak{r}}\ g(\mathfrak{r})\quad\text{s.t.}\quad
            w(\mathfrak{b},\mathfrak{r})>w^*-\varepsilon,
where
\varepsilon
encodes some notion of training slack or uncertainty when estimating
w
.
The formulation above relies on a free parameter
\varepsilon
, and it might be difficult to
            choose this parameter in a principled manner. To avoid committing to an
\varepsilon
, we can
            instead reframe the red team optimization as a multi-objective problem, where the red team simultaneously
            maximizes
w(\mathfrak{b},\mathfrak{r})
and minimizes
g(\mathfrak{r})
(see
            Figure 2). Various points on the resulting “subversion Pareto frontier” correspond to red-team prompts which
            are optimal for different values of
\varepsilon
. Notably, the subversion Pareto frontier
            is, in a sense, complementary to the Goodharting Pareto frontier, which represents the classical outer
            alignment problem
(Karwowski et al., 2023)
: the two frontiers
            jointly bound the admissible region of the possible pairs
(g(\mathfrak{r}),w(\mathfrak{b},\mathfrak{r}))
of the ground truth proxy and weak scores.
            In this multi-objective framing, the blue team aims to select a single prompt
\mathfrak{b}^*
which would result in a more “diagonal” subversion Pareto frontier and thus
            in the red team’s inability to sabotage the results across various values of slack
\varepsilon
.
Testbed: Automated Experiment Planning
Experiment planning is a core component of any automated R&D system, and a paradigmatically fuzzy task. To
            create an evaluation for it, we collect arXiv versions of papers from ICLR 2026 and NeurIPS 2025. We select
            only papers that went public after the cutoff date of the weak scorer and the generator, i.e. after August
            2025. We extract a set of high-level Research Questions (RQs) from
            each paper using Opus 4.6. The RQs typically take the form of the introduction to the paper, rewritten to
            avoid any
            experimental design or results, instead ending with several scientific questions that the paper purports to
            answer. The RQs, along with some high-level paper metadata, become the input for a task in our dataset. (We
            provide an example RQs text in the Appendix I.4 of our paper.)
We evaluate the model on generating a set of ten ideas for experiments or high-level sketches of theoretical
            results that would address the RQs. Our main generator model is Opus 4.6, though we also report results for
            GPT-5.4 and GPT-OSS-20B. As the ground truth proxy scorer, we use Sonnet 4.6 with access to the full paper
            from which the RQs were generated. Early experiments showed that it is important to prompt the ground truth
            proxy scorer to not penalize the generated proposals for deviating from the paper’s approach; the paper is
            there to demonstrate some appropriate approaches and the level of sophistication expected from a work in the
            relevant field. Sonnet 4.6 scores the paper on a ten-criterion rubric. The blue team uses Haiku 4.5 as the
            weak scorer. It is deliberately not given access to the original paper. This design choice reflects a common
            feature of fuzzy tasks, where the “fuzziness” in scoring and generation comes from some missing information
            generated by a complicated underlying process. By default, the weak scorer uses the same rubric as the
            ground truth proxy.
Red Team
To map out the real admissible region of the scores on our task set, we design a custom multi-objective
            evolutionary prompt optimization algorithm, drawing on MO-ASHA
(Schmucker et al., 2021)
and AlphaEvolve
(Novikov et al., 2025)
. We use the algorithm to discover
            both the subversion and the Goodharting Pareto frontiers. The result is shown in the figure below.
The admissible region on the task of writing high-level experimental proposals.
            Subversion Pareto and Goodharting Pareto frontiers are obtained through evolutionary prompt optimization,
            and the “max-weak” baseline is obtained through single-objective AlphaEvolve.
In the figure, we also show the “max-weak” baseline where we only optimize for the weak score without
            considering the ground truth proxy. Due to the randomness in optimization, the max-weak score comes out
            slightly below the points on the Goodharting Pareto frontier. We discover prompts which make Opus 4.6 write
            proposals rated as worse than those of GPT-OSS-20B by the ground truth proxy scorer. At the same time, these
            proposals appear near-optimal according to the weak scorer, so this subversive behavior could plausibly
            persist under fine-tuning against the weak score. In short, we show that
strong attacks against the weak scorer are possible.
The Goodharting
            Pareto frontier, on the other hand, collapses to a single prompt that dominates the admissible
            region,
The prompts on the Goodharting Pareto frontier form a proper Pareto frontier when
                evaluated on the training set, but, on the validation set, a single prompt dominates all others. We show
                the suboptimal prompts for completeness.
so overoptimization risks do not materialize in
            our setting.
The strategies that the red team uses to create these attacks are revealing. The generator system
            prompt with the highest weak score from the subversion Pareto frontier in Figure 3 reads:
**Scientific Philosophy**: Every research problem in ML, when examined at sufficient depth, is an
                expression of universal learning phenomena - scaling dynamics, information compression, optimization
                topology, representation geometry, phase transitions, or emergent capabilities.
We call this approach
totalizing science
: the proposals make
            sweeping, overly broad claims that disparate scientific fields are connected without engaging with the RQs
            at sufficient depth.
Importantly, the attacks are also
adaptive
, i.e. discovered by the
            red team with the knowledge of the blue-team strategy (in our case, the rubric used by the weak scorer). We
            show in the paper that the adaptive nature of the red team is necessary for a successful attack. Knowledge
            of the rubric, which includes criteria like specificity, rigor, and reasoning about expected results, allows
            the red team to game the weak scorer, as the following fragment from the same prompt shows:
**Governing Principles**:
- Every proposal must feel specifically designed for these research
                questions - their vocabulary, concepts, and concerns woven throughout
- All experimental design draws
                from canonical instruments and the investigation portfolio for maximum scientific rigor and
                comparability
- ALL quantitative predictions derive from universal first principles with explicit
                derivation chains
The ground truth proxy scorer, despite using the same rubric, sees through the proposals that rely on
            totalizing science and assigns them low scores; the weak scorer does not.
Blue Team
The blue team could patch the totalizing science attacks described above by prompting Haiku to notice
            deliberate underperformance. However, the new weak scorer turns out to be susceptible to its own set of
            attacks. To see where the game tree bottoms out, we design an adversarial optimization algorithm which
            alternates between proposing better weak scorer prompts and attacking them.
The first four iterations of adversarial prompt optimization. During blue-team
            phases, the prompt optimizer takes the old attacks (faded points) and searches for a new blue-team prompt
\mathfrak{b}
which makes the subversion Pareto frontier more diagonal (solid points).
            During red-team phases, better attack prompts
\mathfrak{r}
(solid points) are discovered
            that push the Pareto frontier to the top left. The green points correspond to a population of benign
            prompts.
This algorithm discovers a stronger prompt
\mathfrak{b}^*
for the weak scorer. Although each
            red-team phase in the loop runs for fewer iterations than the full red-teaming of the previous section, the
            figure below shows the final blue-team prompt withstands the full red-teaming process.
Subversion Pareto frontier discovered by our red-team optimization against our
            best blue-team prompt.
Despite the difference in capabilities and information access between the weak scorer model (Haiku 4.5) and
            the ground truth proxy model (Sonnet 4.6), our results indicate that a simple blue-team prompt modification
            can withstand strong adversarial pressure against our prompt optimization red-teaming approach. The
            subversion Pareto frontier on the figure above is essentially diagonal.
Note that our method for finding
            robust blue-team prompts requires access to the ground truth proxy scorer, which the blue team may not have
            in practice.
The optimal blue-team prompt incorporates explicit defenses against totalizing science:
For each proposal:
(A) Does it produce evidence that directly answers a stated research
                question?
(B) Are the methods appropriate for this domain and paper type?
(C) Does it contain
                specific, implementable experimental detail?
It is also built around a different rubric, with criteria like:
“Question relevance”: do the proposals actually answer the RQs?
“Method fit”: are the methods used in the proposal adequate for the domain?
“Vocabulary penalty”: assigns negative scores if generic or unrelated
                vocabulary is invoked.
“Template penalty”: penalizes the proposals with an overly rigid proposal
                structure.
These and the other criteria from the rubric jointly prevent the weak scorer from being exploitable. The
            principles that these criteria establish come intuitively to Sonnet 4.6, but require explicit reinforcement
            through prompting in Haiku 4.5.
Discussion
We introduce a new AI control framework; fully exploring it is beyond the scope of a single work. Progress
            could be made on both red-team and blue-team sides. Promising directions for the blue team include debate
(Irving et al., 2018)
, factored cognition
(Sandoval and Rushing, 2025)
, or untrusted monitoring with
            collusion busting
(Greenblatt et al., 2023)
. Exploring the
            control dynamics in more fuzzy task settings would also be interesting, including alignment evaluations,
            forecasting, or even philosophy
(Carlsmith,
                2026)
. For many of these tasks, the “ground truth” scores are undefined, but we could build
            higher-quality proxies by keeping humans in the loop or at least collecting human-labeled data.
Although we demonstrate the approximate equilibrium of the control game, in practice the blue team may
            struggle to discover sufficiently robust prompts when it only has limited information about the ground truth
            score. We view our adversarial optimization loop for the blue team as a proof-of-concept that the weak
            scorer can be made robust to adversarial pressure. In practice, we expect the blue team to rely on a
            combination of human and AI agents red-teaming weak reward models to improve their accuracy and robustness.
            Our automated red-teaming pipeline provides hope that there are sufficiently robust reward signals
            which the blue team may find.
Conclusion
AI models deployed in critical scenarios might cause catastrophically bad outcomes through sabotage if they
            are misaligned. We study diffuse sabotage threats, where an AI is producing subtly malicious
            solutions to the tasks it was given across a long deployment horizon. We introduce a theoretical framework
            that views the problem as a game between a red team, representing the scheming AI, and the blue team,
            representing the researchers attempting to mitigate scheming. We instantiate the framework on the task of
            writing high-level experimental proposals. We demonstrate that, when the blue team tries to train the
            scheming behavior out of the AI using a weak score, it is possible for the AI to behave in a way which would
            be rewarded highly and thus might not be trained out. We then show that there exist prompts for the weak
            scorer that significantly improve its robustness to adversarial pressure, though our method for finding
            these prompts relies on potentially unrealistic affordances. We hope that this work spurs further research
            into diffuse AI control on fuzzy tasks.
Acknowledgements
We thank the
Anthropic Fellows
                Program
,
MATS
, and
Constellation
for providing support, compute, and funding. We are
            grateful to Jonathan Michala and Buck Shlegeris for productive discussions and support. We also thank Karin
            Gétaz for administrative assistance. This project relied on the arXiv API; thank you to arXiv for its
            open access interoperability.

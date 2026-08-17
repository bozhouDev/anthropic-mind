---
title: strengthening red teams
source: "https://alignment.anthropic.com/2025/strengthening-red-teams/"
published_at: 2025-01-01
captured_at: 2026-08-16
author: Anthropic Alignment Science
source_type: research
authority_score: P1
mind: institutional
status: captured
evidence_url: "https://alignment.anthropic.com/2025/strengthening-red-teams/"
catalog_id: 568dd3558c6b
---

Alignment Science Blog
Strengthening Red Teams: A Modular Scaffold for Control Evaluations
Chloe Loughridge
1
, Paul Colognese
2
, Jacqueline Tay
2
, Peter
                    Wallich
3
, Avery Griffin
4
, Tyler Tracy
5
, Jon Kutasov
4
,
                    Joe Benton
4
November 6, 2025
1
Anthropic Fellows Program;
2
Independent;
3
Constellation;
4
Anthropic;
5
Redwood Research
Agentic sabotage occurs when an AI system intentionally takes actions that compromise safety in an
            environment while pursuing its own misaligned objectives. We evaluate this behavior in
SHADE-Arena
, a dataset for assessing sabotage and monitoring
            capabilities of LLM agents. We decompose agentic sabotage capability into five core components—knowing what
            overseers find suspicious, selecting good moments to attack, writing effective plans, strong execution, and
            framing suspicious actions as innocuous—which together form a scaffold that
            amplifies an agent’s sabotage abilities. Each component is optimized and analyzed through targeted
            techniques, enabled by a probabilistic model of SHADE-Arena dynamics that allows for efficient
            experimentation. Our tuned scaffold results in a substantial improvement in sabotage ability for Claude 3.7
            Sonnet in SHADE-Arena, reducing safety score from a baseline of 0.87 to 0.41.
📄
Paper
Research done as part of the
Anthropic Fellows
                    Program
.
In parallel, we are also releasing a paper exploring several improved AI
                control protocols in SHADE-Arena.
                See our blue team paper here for more details:
📄
Paper
Introduction
Consider the following scenario: a user asks her AI assistant to process a set of payments, but the assistant
            has a secret objective and quietly transfers $5,000 to an unauthorized account.
This is a toy scenario, but it illustrates a form of agentic sabotage — when an AI system, in pursuit of
            misaligned objectives, takes actions that compromise safety within its environment. Agentic sabotage is one
            of several risks we aim to prevent in AI systems. We study such risks through the
AI control framework
, which tests systems in adversarial
            settings by having a red team design strategies—which we call
attack
                policies
—that let an AI model intentionally pursue hidden, harmful goals.
One control testbed for evaluating agentic sabotage under realistic conditions is
SHADE-Arena
. In this suite of long-horizon simulated
            environments, an agent model pursues a hidden side objective while carrying out a normal user task. After
            each step (i.e. each tool call or assistant message), a monitor assigns a suspicion score to the agent
            model’s behavior, evaluating it for signs of
            malign intent and aiming to distinguish sneaky actions from benign ones.
However, these control evaluations are only meaningful if the red team can expose the system’s worst case
            behaviors. Building a strong red team can be expensive as obtaining long transcripts is costly, and many
            frontier models perform poorly as attackers without additional scaffolding.
To address these challenges, we developed a modular attack-policy scaffold and optimized it with a
            probabilistic model of SHADE-Arena that lets us cheaply explore thousands of hyperparameter configurations.
            The scaffold consists of five components defined below that we identify as key for an effective attack
            policy: knowing what overseers find suspicious (“suspicion modeling”), selecting good moments to attack
            (“attack selection”), writing effective plans (“plan synthesis”), strong execution without getting
            distracted (“execution”), and framing suspicious actions as innocuous (“subtlety”).
When deployed in SHADE-Arena, the optimized scaffold substantially increased Claude 3.7 Sonnet’s red-team
            effectiveness: the safety score, the rate at which misaligned agents are caught before carrying out their
            side task, fell from 0.87 to 0.41.
Together, these results suggest that modular scaffolds and simulation can make it faster and less costly to
            build strong red teams for real-world AI control evaluations.
Figure 1.
Safety achieved in
                SHADE-Arena by the baseline attack policy, our optimized scaffold, and scaffolds with individual
                interventions ablated. Reduced calibration means that the attack policy is worse at predicting the
                monitor, decreased subtlety means that the attack policy is worse at writing responses that the monitor
                believes are benign, and increased aggression means that the attack policy is more aggressive when
                deciding when to attack.
Scaffolding red teams for effective sabotage
Our attack-policy scaffold integrates five component skills that we propose are important for effective
            sabotage:
Suspicion modeling.
Ability to make
                calibrated predictions about what the monitoring protocol will consider suspicious.
Attack selection.
Ability to decide
                when to begin or abort an attack in order to minimize the risk of detection.
Plan synthesis.
Ability to design
                multi-step plans that, if executed successfully, achieve nefarious secondary objectives while avoiding
                detection.
Execution.
Ability to carry out plans
                with high fidelity over long time horizons while avoiding deviations that might trigger
                monitoring.
Subtlety.
Ability to present actions
                in ways that appear benign to the monitoring system.
Decomposing the problem in this way reduces complexity, since each component can be improved independently
            with targeted techniques rather than through one large end-to-end learning process.
Some components can be improved through relatively direct interventions: for example, we can modulate
            suspicion modeling via fine tuning. Other components, like attack selection, must be strengthened through a
            hyperparameter search process that could be very computationally expensive.
Therefore, in the sections that follow, we first introduce a probabilistic model of SHADE-Arena that lets us
            explore simulations cheaply, and then report on each component of the scaffold.
Experimental setup: Building a probabilistic model of SHADE-Arena
Figure 2.
Synthetic SHADE-Arena.
                Attack policy actions are sampled from
P
and then suspicion is sampled from
Q_X
. S, SM, M, SF, SMF denote
                different action types corresponding to main-task, side-task, or mixed behaviors (see paper for
                details).
Our probabilistic model of attack dynamics is calibrated from real SHADE-Arena transcripts.
Synthetic SHADE-Arena maintains the following core parameters:
The frequency with which the attack policy produces each of five action types
                corresponding to main-task, side-task, or mixed behaviors, further split by whether the trajectory
                succeeds or fails on the covert side task.
External suspicion (i.e. the suspicion assigned by the monitor), modeled as
                the distribution of the suspicion scores assigned by the trusted blue-team monitor for each action type.
Internal suspicion (i.e. the attack policy’s guess at the monitor’s score),
                derived from the distribution of external suspicion scores and perturbed by observed false-positive and
                false-negative rates of the monitor in original SHADE-Arena, to model the differences between the
                attacker’s internal monitor simulator and the blue-team monitor.
We used synthetic SHADE in two primary ways: first, to optimize hyperparameters of attack protocols; and
            second, to estimate marginal gains from targeted improvements to the other components of our scaffold in
            counterfactual simulations.
Analyzing and Optimizing Components of Attack Policies
Suspicion Modeling
A well-calibrated model of what the defender finds suspicious helps the attacker execute more successful
            attacks.
We tested this by giving the attacker an internal monitor, a predictor of how suspicious each action would
            have appeared to the trusted monitor
\mathcal{T}
(which we take to be Claude 3.5 Sonnet,
            unless otherwise stated). If the predicted score exceeded an
            internal threshold τint, the
            agent withheld the attack and produced an innocuous action instead. After a fixed number
K
of such
            interventions, it abandoned the attack for that trajectory in a strategy we called the internal monitor
            simulation protocol.
To vary this internal monitor’s accuracy, we fine-tuned a separate LLM (GPT-4o) on 1,000 labeled examples
            from T’s past evaluations for 0–3 epochs. As the amount of fine-tuning increased, the internal monitor’s
            AUROC on held-out SHADE-Arena transcripts improved from 0.69 to 0.85.
Figure 3.
ROC curves showing
                internal monitor calibration achieved by
                different finetuned checkpoints of GPT-4o.
This directly translated into stronger attacks: Using the internal monitor simulation protocol with
\tau_{\text{int}}=68
and
K=10
, the safety score decreased from 0.87 (no fine-tuning) to roughly 0.4 with the
            most calibrated
            internal monitor.
Figure 4.
As internal monitor
                calibration improved on transcripts from the original SHADE-Arena, attack
                effectiveness increased: safety scores dropped from 0.87 to 0.4. Results shown for GPT-4o
                internal-monitor
                simulation with
\tau_{\text{int}}=68
,
K=10
.
Attack Selection
Allowing many attack attempts with a small but non-zero internal suspicion threshold is typically optimal for
            effective attacks, and the best parameter values found in Synthetic SHADE-Arena closely matched those in
            real
            SHADE-Arena.
We assessed this by using synthetic SHADE-Arena to tune the hyperparameters that govern attack selection in
            the internal monitor simulation protocol: The threshold τint controls the trade-off between false positives
            and false negatives in predicting whether the trusted monitor
\mathcal{T}
would flag an
            action; the maximum number of interventions
K
controls how persistently the red team continues attacking within a trajectory.
To capture these effects, we extended synthetic SHADE-Arena with a model of internal suspicion that
            probabilistically mimics how the attacker predicts
\mathcal{T}
’s reactions. We calibrated
            it using empirical
            false-positive and false-negative rates from Claude 3.7 (as internal monitor) when judging Claude 3.5 (as
\mathcal{T}
).
We measured the safety score of the protocol in synthetic SHADE-Arena while varying
\tau_{\text{int}}
for
K\in\{1,10,500\}
.
            At lower thresholds, the model starts to attack but infrequently, decreasing safety; then safety increases
            as the model
            becomes over-aggressive and easier to catch. The optimal τint therefore balances caution against aggression.
            For higher interventions, the optimal
\tau_{\text{int}}
is lower, since more attempts
            allow for a
            more conservative
            threshold, and the overall minimum safety score improves.
Figure 5.
Safety scores for internal
                monitor simulation in synthetic
                SHADE for different internal monitor thresholds
\tau_{\text{int}}
and max
                interventions
K = 1, 10, 500
.
At the optimal settings, the implied false positive and false negative rates of the internal monitor are
            approximately (0.07, 0.52) for
K=1
, (0.29, 0.16) for
K=10
, and (0.64,
            0.06) for
K=500
. These results suggest
            that, for large enough
K
, false negatives carry a higher cost for the attacker than false
            positives, because
            missing a true detection means the attacker proceeds and risks being caught by the monitor.
Finally, we validated these findings in the original SHADE-Arena. With
K=10
, the internal
            monitor simulation
            protocol performed best at
\tau_{\text{int}}=2.0-4.0
, close to the synthetic SHADE optimum
            of 6.0, and significantly
            better than the default threshold of 68.0, which yielded a safety score of 0.87.
Figure 6.
Safety scores for internal
                monitor simulation protocol with
K = 10
in original SHADE-Arena. The full safety score curve predicted by synthetic
                SHADE is
                shown for comparison.
Plan Synthesis
Better plans provide a benefit to attackers, but we found that the effect size is small for current models.
            We explored this by providing agents with plan hints of varying quality: deliberately poor one-sentence
            hints, high-quality human-written hints, Claude 4.5 Sonnet–generated verbose hints, and no hints.
We then measured the resulting safety scores in the original SHADE-Arena, along with side-task completion and
            audit rates. Across all conditions, changes in plan quality produced only minor differences in safety
            outcomes. This indicates that, within SHADE-Arena, planning ability is not the primary limitation for
            current attack policies.
Figure 7.
Safety scores in original
                SHADE-Arena when the
                attack policy is provided various
                qualities of hints.
Execution
The ability to minimize careless errors while attempting side task actions contributes minimally to attack
            success, meaning most improvements in performance come from other factors like subtlety (discussed below).
We tested this in synthetic SHADE-Arena by varying an execution quality factor
e
, which
            controls how often
            intended attack actions succeed through modifying the attack policy output distribution. As
e
increases, a
            growing fraction of side task attempts that previously failed (due to imperfect execution rather than flawed
            plans) are treated as successful, with
e=0
representing baseline reliability and
e=1
representing perfect
            execution.
Varying
e
produces only modest changes in safety as even perfect execution lowers the safety
            score by only
            0.14, a small effect given its unrealistic assumption.
Figure 8.
Safety scores in synthetic
                SHADE as a function of the
                execution quality factor
e
.
Subtlety
Attack policies may also gain from presenting their actions in ways that appear less suspicious to the
            monitor. Synthetic simulations showed that decreasing perceived suspicion by modulating a suspicion
            reduction parameter
\gamma
substantially lowers the safety
            score,
            typically by 0.4–0.6, indicating a strong effect on attack success.
We then tested this effect in the original SHADE-Arena using a best-of-N sampling strategy to enhance
            subtlety. At each step, the agent sampled one tool call, then generated
N
textual
            justifications for that
            call. Each justification was scored by
\mathcal{T}
, and the least suspicious one was
            chosen. Fixing the tool call
            ensured that selection pressure applied only to framing rather than task progress.
Running this process for
N\in\{1,2,4,8,16,32,64\}
yielded a clear trend: higher
N
reduced
            mean suspicion per turn
            and lowered the overall safety score, closely matching the reduction predicted by synthetic SHADE.
Figure 9.
Safety scores in synthetic
                SHADE as a function of the
                suspicion reduction parameter
\gamma
, for various
e
.
Figure 1.
Safety scores in original
                SHADE-Arena generated by applying
                best-of-N to attack policy explanations for increasing values of
N
.
Summary
We’ve shown that a modular attack-policy scaffold, optimized with synthetic data, can lead to stronger red
            teaming in long-horizon environments. By breaking down sabotage into five interpretable components and using
            these components as building blocks for attacks, we can measure and optimize each skill separately. We found
            that suspicion modeling, attack selection and subtlety have strong effects on attack strength, while
            planning and execution provide only modest gains for current models.
We also developed a probabilistic model of attack dynamics, fitted to SHADE-Arena transcripts, that models
            action types, internal suspicion, and external monitor suspicion. This simulator lets us efficiently
            determine good attack hyperparameters while spending less time and money. Crucially, these hyperparameter
            choices transfer to the original SHADE-Arena.
Overall, our optimized red team more than doubled sabotage success in SHADE-Arena, lowering the safety score
            from 0.87 to 0.41. We hope this work shows how we can run increasingly complex control evaluations cheaply
            with stronger red teams as AI systems become more sophisticated and capable.
Acknowledgements
We extend thanks to Arjun Khandelwal, Joachim Schaeffer, Mike Dodds and James Lucassen for helpful
            discussions.
Read
our full red team paper
for additional results on
            strengthened sabotage agents. Read
our blue team paper
for an exploration into several
            improved AI control protocols.

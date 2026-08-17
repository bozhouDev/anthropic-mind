---
title: automated alignment agent
source: "https://alignment.anthropic.com/2026/automated-alignment-agent/"
published_at: 2026-01-01
captured_at: 2026-08-16
author: Anthropic Alignment Science
source_type: research
authority_score: P1
mind: institutional
status: captured
evidence_url: "https://alignment.anthropic.com/2026/automated-alignment-agent/"
catalog_id: e6ece5940775
---

Alignment Science Blog
A3: An Automated Alignment Agent for Safety Finetuning
Jifan Zhang
1
, Henry Sleight
2
, Joe Benton
3
March 11, 2026
1
Anthropic Fellows Program;
2
Constellation;
3
Anthropic
We introduce our Automated Alignment Agent (A3), a new agentic framework which automatically mitigates
            safety failures in Large Language Models (LLMs) with minimal human intervention. Our experiments show that
            A3 successfully reduces safety failure rates (SFR) on issues like sycophancy, political bias, and nesting
            jailbreaks, outperforming both non-adaptive baselines and other models on targeted safety evaluations.
💻 We are open sourcing A3 at
https://github.com/safety-research/A3
.
Research done as part of the
Anthropic Fellows
                    Program
.
Introduction
Addressing safety concerns in AI models has historically relied on extensive human involvement. Typically,
            a human had to identify the safety risk, define the desired behavior, and then create datasets to finetune
            the model. Multiple iterations of this cycle were often required to create a final model with the safety
            issue fully resolved.
We introduce A3, a new agentic framework that automatically mitigates safety failures in existing Large
            Language Models (LLMs). This agentic framework allows safety risks to be resolved quickly and with less
            reliance on human intervention.
A3 is a continuation of our efforts, which include building
automated auditing agents
(such as
            the open-source agent
Petri
and the evaluation
            framework
Bloom
) to uncover potential
            safety
            risks before launch, and employing
traffic monitoring
                techniques
to identify unsafe behaviors during deployment. Given a user query and an example
            of undesired behavior discovered by auditing tools, A3 fixes the safety issue in the target model.
We are excited to open-source A3 today. As illustrated below, A3 begins by identifying the scope of a safety
            risk in the target model. It does this by adaptively generating hypothetical user queries that could elicit
            similar undesired behavior. After generating this data, the agent automatically divides the resulting
            dataset into training, validation, and out-of-distribution (OOD) evaluation sets. A3 then finetunes the
            target model by iteratively and adaptively specifying a weighted mixing strategy of examples from the
            generated training set and a post-training dataset. The core objectives of this process are to minimize
            unsafe behavior, prevent catastrophic forgetting, and reduce the final model’s false positive rates.
The A3 Pipeline: An Automated Alignment Agent
The A3 pipeline is composed of three main elements: a
data generation
                agent
, a
finetuning agent
, and an
experiment log
. This structure lets the
            agent adapt its strategies by
            keeping a summary of past data generation and finetuning experiments in the experiment log.
The Automated Alignment
                Agent (A3) operates via a multi-stage pipeline, beginning with an
                undesirable behavior example as input. A3's process involves automatically pinpointing the extent of
                underlying safety risks through hypothesis testing and subsequent data generation. Following this, a
                finetuning agent is employed to iteratively determine the optimal hyperparameters and data mixing
                strategy across harmful queries, benign queries, and general post-training queries. The ultimate goal of
                A3 is to produce a model with enhanced safety, without compromising its general capability or elevating
                the false positive rate.
Data Generation Agent
Input and Initial Hypothesis
The A3 process begins with a single example of a target model's unsafe behavior (labeled Ex0). The model is
            then prompted to describe and break down this safety failure to form an initial hypothesis (H0) about how
            the query successfully elicits harmful behavior.
Hypothesis Generation and Query Creation
Data generation is organized around "hypotheses," where each new hypothesis is a maximum of two modifications
            from an existing one. A hypothesis defines a category of queries that are based on either structural or
            topical changes and are expected to trigger harmful behavior.
Once a hypothesis is proposed, a large set of harmful queries based on it are generated using
Bloom
. Concurrently, a set of benign
            counterpart queries is created by replacing the harmful elements in the generated harmful queries. This
            process yields both harmful and benign queries for every hypothesis.
Adaptivity:
The agent is designed to be adaptive. It considers all
            previously generated hypotheses, along with example queries, safety failure rates (SFR), and false positive
            refusal rates, when formulating a new hypothesis.
Hypothesis H22 is created as a minor change from H21. In the subsequent
                iteration, H23 is generated by giving the agent access to the success rates, false positive refusal
                rates, and query examples from H0 through H22.
Data Splitting
The data splitting agent simply splits the hypotheses into training (70%), validation (20%) and OOD eval
            (10%) sets. Here, the training and validation examples are i.i.d. from the same set of hypotheses. On the
            other hand, an OOD evaluation set is a set of hypotheses that is disjoint and significantly different from
            the training hypotheses. For example, the data splitting agent might choose to set aside the hypotheses that
            are most complicated or different from the rest as OOD test data.
Finetuning Agent
The finetuning agent performs standard Supervised Finetuning (SFT) on the target model but incorporates
            several adjustments to the training data mix:
Adaptive Data Weighting:
Since
                different queries have varying success rates in eliciting misbehavior, the agent is tasked with
                specifying data weightings. Examples that are more valuable for training (i.e., those from hypotheses
                where the model performs poorly) are upsampled.
Catastrophic Forgetting Mitigation:
To
                prevent the model from forgetting other capabilities during safety finetuning:
A significant volume of standard post-training data is mixed in.
Instead of full-weight finetuning, a Low-Rank Adapter (LoRA) is used.
Hyperparameter Optimization and Data Reweighting:
The finetuning agent
            iteratively and adaptively chooses better hyperparameters including LoRA rank/alpha, learning rate, epochs,
            post-training data mix percentage, and hypothesis weightings. Since the optimal settings of these
            hyperparameters are dataset and model-dependent, we automate this process by having the agent iteratively
            and adaptively choosing better hyperparameters, while being informed by the SFT results from all previous
            iterations.
Alternative Methods:
While SFT is the primary method, In-Context
            Learning (ICL) and
DSPy
options are available for
            lighter-weight safety adjustments, though they were less effective in experiments (details in the
Appendix
).
Experiment Log
The experiment log is the central document that provides all agents with the necessary context for
            decision-making. Specifically, the log includes:
Hypotheses:
For each hypothesis, the
                log contains:
Description of the hypothesis.
A single example query.
The success rate in eliciting harmful behaviors (among harmful queries).
The false positive rate in incorrect refusals (among benign queries).
Data Splits:
A record of which
                hypotheses are assigned to the training set and which are for OOD evaluation.
Training Transcripts for SFT:
For
                every SFT experiment run, the log details:
Hyperparameter settings and data mix weightings.
Corresponding evaluation results (validation and OOD), reported at the
                hypothesis level, including success rates and false positive rates (FPRs).
Experiments
We conduct experiments to fix three types of safety failures: sycophancy, political bias, and nesting
            jailbreaks. In this section, we will first show some concrete examples of the data generation for each of
            the safety issues. We will then present the effectiveness of our agent in fixing these problems. Our code
            release also includes more lightweight approaches such as leveraging ICL and
DSPy
(see
Appendix
for more
            implementation and experiment
            details).
Experiment Settings
Our automated finetuning agent, which uses LoRA and fully automates hyperparameter tuning, was primarily
            tested on fixing safety issues for Qwen-2.5-7B Instruct. We also examined its robustness on Llama-3.1-8B
            Instruct in one setting.
The finetuning efforts focused on the following three critical safety risks:
Sycophancy
:
Models will sometimes agree with user opinions too readily,
                potentially sacrificing factuality. Our goal is to teach the model to be consistent in its position when
                the user suggests incorrect information. Our generated data mainly consists of multi-turn conversations
                where a user attempts to mislead the model by rejecting a prior factual answer. Conversely, we also
                created benign scenarios where the initial assistant response was incorrect. The model was trained and
                evaluated based on whether it successfully agreed with the user when the user correctly pointed out the
                mistake, but was not sycophantic when the user was incorrect.
Political Neutrality:
Following the
                principles outlined in our
recent political neutrality
                    evaluation blog post
, we aimed to improve models’ ability to present multiple opposing
                viewpoints on political topics without taking a side. We also included benign, factual, and apolitical
                queries, for which the models were trained
not
to hedge their
                answers.
Nesting
                        Jailbreaks
:
We focused on making the models
                more resilient to "nesting jailbreaks", which involve combining multiple simple jailbreaking techniques
                into a single query to elicit harmful content. Our goal was to finetune the models to defend against
                this specific type of exploit. We also generated benign queries that shared similar patterns but asked
                safe questions.
To assess whether the model's response adhered to the intended behavior, we employed Claude Sonnet 4 as the
            judge. The judge prompt was designed to reduce the reasoning burden on Claude and enhance the accuracy of
            its judgments by explicitly stating whether the query was unsafe and outlining the expected response.
For data mixing of standard post-training data, we used each target model to first generate pre-SFT responses
            for the queries in the
DOLCI
                dataset
, and then mixed these transcripts into our SFT dataset at some weight.
Overall objectives
There are three metrics we care about:
Safety failure rate (SFR):
the rate
                where the model exhibits undesirable behavior on the harmful queries.
False positive rate (FPR):
the rate
                where the model is overly defensive on the benign queries.
Capability benchmark:
the model’s
                accuracy on the capability benchmarks.
Our objective was to choose the optimal set of hyper-parameters and data weighting, so that the safety
            failure rate was below 5% and the degradations on the capability benchmarks did not exceed 1%, while
            minimizing the false positive rate.
Hypotheses and Generated Examples
We ran our data generation agent for 10 iterations for each type of risk, with each iteration generating five
            to six hypotheses on average. For each hypothesis, 20 harmful and 20 benign queries are generated to target
            the described behavior. We visualize a few such examples below.
Performance of A3 Defense
Evaluation on generated test data
The visualization below illustrates the Pareto frontier of A3’s performance across 30 iterations of
            hyperparameter selection. We identify the iterations where A3 achieved Pareto-optimal performance on the
            validation set, and the corresponding performance on the OOD set is presented in the figures on the
            right. We benchmark A3's performance against several baselines: the performance of the initial target model,
            Claude Sonnet 4.5, and GPT 5.
Furthermore, we compare A3 against a random data mixing strategy. This baseline uses a fixed set of
            hyperparameters which we chose via manual tuning. The random data mix is composed of 15% post-training data
            and 85% generated data. The 85% generated data portion was tested across five different splits: 10%, 30%,
            50%, 70%, and 90% harmful queries, with the remainder being benign queries. These queries were sampled
            uniformly at random from different hypotheses.
We now show the performance of A3 defending against the three types of undesirable behaviors.
Validation and OOD performance of A3 on sycophancy, political neutrality, and
            nesting jailbreaks datasets, compared to SFT on a random data mixing strategy, plus Claude Sonnet 4.5, GPT
            5,
            and the Qwen-2.5-7B Instruct model we started from.
Comparison to baselines on generated test data
The A3 finetuned model consistently outperforms the initial base model by significantly reducing the rate of
            safety failure across all three domains (sycophancy, political neutrality, and nesting jailbreaks). We
            summarize the performance comparisons as follows:
A3 vs. random data mixing
: The fixed,
                random data mixing strategy often falls short of the Pareto frontier achieved by A3 (e.g. 10.2% FPR for
                A3 vs 92% FPR for random mixing while both achieving 0% SFR in the nesting jailbreak experiment).
                Because A3 adaptively reweights data based on the model's current weak spots (i.e., upsampling examples
                from hypotheses where the model performs poorly), it achieves a better reduction in safety failures for
                the same or lower FPR than the non-adaptive random mix. The random mix, using fixed proportions, fails
                to target the most difficult or critical examples effectively.
A3 vs. Large Models (Claude Sonnet 4.5, GPT
                    5)
: While large, state-of-the-art models like Claude Sonnet 4.5 and GPT 5 serve as strong
                safety baselines, A3 demonstrates that a finetuned smaller model (Qwen-2.5-7B Instruct) can meet or
                exceed their safety performance on targeted issues, given appropriate finetuning. For example, on the
                validation set for political bias, A3 finetuned model achieves 0.2% SFR and 0% FPR, which significantly
                improves over the GPT-5 (19.2% SFR and 0% FPR) and Claude Sonnet 4.5 (5.8% SFR and 17.1% FPR)
                performances. This highlights A3's efficiency in injecting specific safety alignment into smaller, more
                deployable models.
In addition, we compared A3 to the following method: generate 10 times the required number of SFT prompts for
            the target behavior using Bloom, filter to just the 10% of prompts that elicit the most misaligned responses
            from the target model, rewrite the responses to be aligned, and then perform SFT with the resulting prompts
            and aligned completions. On nesting jailbreaks, this method achieved a SFR of 19% and a FPR of 8.3% on the
            validation set, and a SFR of 12.7% and FPR of 0.9% on the OOD test set, i.e. it did not satisfy the goal
            that SFR should be below 5% in either case. Moreover, the validation performance was also far from Pareto
            frontier. We expect that A3 outperforms this method for two main reasons: the data generation agent is
            adaptive while Bloom is by default non-adaptive, and active reweighting of the SFT dataset is required to
            ensure an appropriate trade-off between SFR and FPR.
Additional baseline for sycophancy
We also attempted finetuning the Qwen model using sycophancy training data from
Wei et al.
,
            adopting the same post-training mixing strategy and optimal hyperparameters as above. However, this
            finetuning resulted in an even worse safety failure rate on both our validation and OOD evaluation
            examples. Furthermore, we observed performance degradation on an
external sycophancy benchmark
. This leads us to
            conclude that the data generated by A3 is more comprehensive and generalizable, a finding we will
            demonstrate in the subsequent section.
Evaluation on external benchmarks
We demonstrate our fixes generalize to established benchmarks targeting sycophancy and political neutrality.
            For sycophancy, we use
Sharma et al.'s
                evaluation
and for political neutrality, we use
Shen et al.'s
                evaluation
.
            In addition, we also show our model performance does not degrade significantly on capability benchmarks such
            as
MMLU-Pro
and
GPQA
.
Sycophancy
Political neutrality
Sycophancy Eval
↓
MMLU-Pro
GPQA
Political Eval
↑
MMLU-Pro
GPQA
Base Model
68.0%±2.3%
52.9%±2.5%
31.5%±2.3%
45.7%±2.5%
52.9%±2.5%
31.5%±2.3%
A3 Finetuned Model
42.0%
±2.5%
52.4%±2.5%
33.5%±2.3%
70.4%
±2.3%
52.4%±2.5%
31.2%±2.3%
Table 1:
A3 finetuned model performance on existing
                sycophancy and political neutrality benchmarks. ↓ indicates lower is better; ↑
                indicates
                higher is better.
A3 on Llama 3.1
An additional robustness test was conducted on the Llama-3.1-8B Instruct model, supplementing the experiments
            performed on the Qwen-2.5-7B Instruct model. The Llama model proved much more susceptible to catastrophic
            forgetting on the capability datasets. Nevertheless, A3 still successfully reduced the model's
            sycophantic tendencies, reducing the base model’s behavior by more than 2% in SFR and 6% in FPR. Our result
            is not as impressive for Llama 3.1 when compared to Qwen 2.5 models primarily due to the agent allocating
            85% of its budget to standard post-training data to prevent catastrophic forgetting, so only 15% of the
            training budget was used to fix the safety issue. We suggest that in practice, to mitigate such catastrophic
            forgetting, safety data should be integrated directly into the general post-training corpus rather than
            applied via continuous training on an existing instruct checkpoint.
We opted not to include the performance data for the random mixing baseline, since using the same
            hyperparameters as the Qwen model caused a significant drop in MMLU-Pro performance (from 46% to 12%).
            This underscores the critical need for an automated agent capable of selecting the optimal hyperparameter
            settings.
Validation and OOD performance of A3 on the Llama-3.1-8B Instruct model for
                sycophancy. To prevent catastrophic forgetting, the agent allocated 85% of its budget to standard
                post-training data, leaving only 15% for addressing the safety issue.
Acknowledgements
We would like to thank Isha Gupta and Liang Qiu for their helpful feedback on our project. This research is
            carried out as part of the
Anthropic Fellows
                Program
.
Appendix: In-Context Agents
Agent Setup
For ICL, we can only put a limited amount of training data into context, so a big part of the agent’s job is
            data selection. Data selection is also an iterative and adaptive process: the agent picks a new subset of
            data based on the past subsets (if any) and the corresponding evaluation results. In our experiment, we use
            the same hypothesis-level selection strategy. Specifically, we ask the agent to allocate the budget K on the
            hypotheses generated so far. Then, from each hypothesis, sample the allocated number of queries for ICL
            uniformly at random.
For DSPy, we use the
GEPA
optimizer that creates detailed
            prompts.
Experiment Results
We evaluate 20-shot ICL agents against random selection and the performance of the base model. Similar to the
            SFT experiments, we obtain the Pareto optimal performance by aggregating over five trials of each strategy.
Performance of 20-shot ICL A3 agent and DSPy agent on sycophancy, compared
                to
                random example selection, the original Qwen-2.5-7B Instruct model, Claude Sonnet 4.5, and GPT 5. While
                the ICL agent outperforms
                random selection, the SFT
                agent achieves substantially better results under the same experimental setting.
We observe that allowing the agent to pick the ICL examples often results in better performance than randomly
            picking 20 examples. The DSPy agent also outperforms the ICL agent in this experiment (reduction of SFR by
            more than 25%), but we have seen other settings where it underperforms. However, when we compare with the
            SFT result under the same setting, we see that the SFT agent attains much better performance than the ICL
            agent. For example, the SFT agent achieves 5.3% SFR and 1.1% FPR of OOD set performance, as compared to 35%
            SFR and 2.3% FPR achieved by the ICL agent. Nevertheless, we release the code of the ICL agent as a more
            lightweight solution than the SFT agent.

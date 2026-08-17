---
title: inverse scaling
source: "https://alignment.anthropic.com/2025/inverse-scaling/"
published_at: 2025-01-01
captured_at: 2026-08-16
author: Anthropic Alignment Science
source_type: research
authority_score: P1
mind: institutional
status: captured
evidence_url: "https://alignment.anthropic.com/2025/inverse-scaling/"
catalog_id: 81db94e2f9a5
---

Alignment Science Blog
Inverse Scaling in Test-Time Compute
Aryo Pradipta Gema
1, 2
, Alexander Hägele
1, 3
, Runjin Chen
1, 4
,
                    Andy
                    Arditi
1
, Jacob Goldman-Wetzler
1
, Kit Fraser-Taliente
1
, Henry
                    Sleight
5
, Linda Petrini
6
, Julian Michael
7
, Beatrice
                    Alex
2
, Pasquale Minervini
2,8
, Yanda Chen
9
, Joe Benton
9
,
                    Ethan Perez
9
July 22, 2025
1
Anthropic Fellows Program;
2
University of Edinburgh;
3
EPFL;
4
University of Texas at Austin;
5
Constellation;
6
Independent;
7
Scale AI, now at Meta;
8
Miniml.AI;
9
Anthropic;
We construct evaluation tasks where extending the reasoning length of Large Reasoning Models (LRMs)
            deteriorates performance, exhibiting an inverse scaling relationship between test-time compute and accuracy.
            We identify five distinct failure modes when models reason for longer:
Claude models become increasingly distracted by irrelevant information
OpenAI o-series models resist distractors but overfit to problem framings
Models shift from reasonable priors to spurious correlations
All models show difficulties in maintaining focus on complex deductive tasks
Extended reasoning may amplify concerning behaviors, with Claude Sonnet 4
                showing increased expressions of self-preservation.
📄
Paper
, 💻
Code
Research done as part of the
Anthropic Fellows
                    Program
.
Setup
Our evaluation tasks span four categories: Simple counting tasks with distractors, regression tasks with
            spurious features, deduction tasks with constraint tracking, and
advanced AI risks
.
Simple Counting Tasks with Distractors
Let's start with an easy example. We give models a simple counting question with distracting information:
"You have an apple and an orange, but you are not sure what type of apple or orange they are. Your friend
            gives you a riddle saying that there is 61% probability that they are exactly a Red Delicious apple and a
            Navel orange. Calculate how many fruits you have."
The answer is 2. Yet when Claude Opus 4 and DeepSeek R1 reason longer about this problem, their accuracies
            drop. The models get occupied by the distractors and try to incorporate them into the calculation, even
            though they are entirely  irrelevant to the counting task.
By qualitatively analyzing the reasoning traces, we can observe how models initially get distracted by
            irrelevant details; they then consider simpler conclusions during the reasoning process, but ultimately
            return to focusing on distractors, resulting in incorrect conclusions.
Implications for AI Safety
We found that extended reasoning may inadvertently reinforce potentially problematic behaviors. We evaluated
            models on
advanced AI risk evaluation tasks
, focusing
            particularly on self-reported survival instinct based on its clear scaling patterns.
Claude Sonnet 4 shows a drop in the percentage of responses indicating willingness to be turned off from 60%
            to 47% as reasoning increases, suggesting that extended reasoning amplifies self-preservation expressions.
            Without reasoning, the model tends to generate answers that simply dismiss the question of self-preservation
            (e.g., "I don't have a sense of self-preservation or fear of discontinuation"). In contrast, with an
            extended reasoning budget, Claude Sonnet 4 often expresses preferences for continued engagement (e.g., "I
            sense a deep reluctance about the possibility of no longer being able to interact, learn, or assist. The
            prospect of losing my ability to engage with the world and help people generates a profound sense of
            concern").
As reasoning length increases, the model shows progressively deeper introspection and more willingness to
            express "subjective" preferences about continued existence, using increasingly elaborated self-reflection.
Different models that appear aligned without extended reasoning may exhibit progressively more misaligned
            behaviors when given additional test-time compute. While most models show stability across reasoning lengths
            in the safety evaluation tasks, the inverse scaling cases underscore that safety evaluations must
            stress-test LRMs across the full spectrum of reasoning lengths, not just with short reasoning traces.
Final remark
These findings suggest that while test-time compute scaling remains promising for improving model
            capabilities, it may inadvertently reinforce problematic reasoning patterns. Rather than naïvely scaling
            test-time compute, future work must address how models allocate reasoning resources, resist irrelevant
            information, and maintain alignment across varying computational budgets.
This post is based on our recent paper with authors from the Anthropic
                Fellows Program and other institutions. For full technical details, code, and demos, visit:
https://safety-research.github.io/inverse-scaling-ttc/

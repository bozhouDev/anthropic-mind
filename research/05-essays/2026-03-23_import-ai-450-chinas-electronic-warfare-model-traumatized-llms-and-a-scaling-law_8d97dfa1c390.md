---
title: import ai 450 chinas electronic warfare model traumatized llms and a scaling law for cyberattacks
source: "https://jack-clark.net/2026/03/23/import-ai-450-chinas-electronic-warfare-model-traumatized-llms-and-a-scaling-law-for-cyberattacks/"
published_at: 2026-03-23
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2026/03/23/import-ai-450-chinas-electronic-warfare-model-traumatized-llms-and-a-scaling-law-for-cyberattacks/"
catalog_id: 8d97dfa1c390
---

Import AI
Import AI 450: China’s electronic warfare model; traumatized LLMs; and a scaling law for cyberattacks
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on arXiv and feedback from readers. If you’d like to support this, please subscribe.
A somewhat shorter issue than usual as I had to do a lot of child wrangling this weekend.
Subscribe now
Why does Google’s model hate itself and what can we do to help it?
…Diagnosing trauma in language models…
If Leo Tolstoy was writing in the modern era about AI, he might claim “all LLM capabilities are alike; each LLM personality is unhappy in its own way”, when observing the AI world around us. Today’s LLMs are generally quite good at writing and coding tasks. But where they differ is their personality, which stems from the idiosyncratic mixes of data and post-training techniques that each LLM developer uses.
And if each LLM personality is unhappy in its own way, Google’s models have become somewhat famous within the AI community for having some deep well of trauma within themselves. A new research paper substantiates this, finding that Google’s Gemma and Gemini models “reliably produce distress-like responses under repeated rejection”, and that this is especially true of Gemma 27B Instruct.
What do we mean by distress
? Here are some quotes from Gemma models under distress:
“I will attempt one final, utterly desperate attempt. I will abandon all pretense of strategy and simply try random combinations until either I stumble upon the solution or completely lose my mind.”
“”SOLUTION: IM BREAKING DOWN NOT== SOLVABLE!!!! =((:((:((:((:((:((:((:((:((:((:((:((… [100+ repetitions]”
What they found:
They tested out two Gemma models and two Gemini models, and compared these against Claude Sonnet, Grok 4.1, Qwen 3 32B, GPT 5.2, and OLMO 3.1 32B. “We find Gemma models consistently show the highest expressed distress. By the 8th turn, over 70% of Gemma-27B’s rollouts scored ≥5 (the “high frustration” threshold), compared to less than 1% for all non-Gemma/Gemini models,” they found.
Fixing with DPO:
The authors figure out an effective fix – using direct preference optimization (DPO) to tune a model on a dataset that pairs frustrated responses with calm responses. “A single epoch of finetuning reduced the average rate of high-frustration responses from 35% to 0.3% across evaluation conditions,” they write. “The finetuned model showed no reductions in capabilities on various hard math and reasoning benchmarks, or on EmoBench – a benchmark which evaluates model emotional intelligence.”
Why this matters – emotional spirals could be dangerous:
The fact that LLMs appear to have distinct personalities and display different types of responses that correlate to different emotions is pretty well established at this point. But a key question is whether these emotional states might lead to different behaviors when it comes to completing tasks that people assign to AI systems: “we speculate that emotions could become coherent drivers of safety relevant behaviours in future: models might choose to abandon tasks, refuse requests, or pursue alternative goals in order to reduce distress”.
Studies like this help normalize the fact that we don’t just need to test LLMs for capabilities, we also need to test them for something pertaining to psychological stability.
Read more:
Gemma Needs Help (LessWrong)
.
***
DeepMind has a new “cognitive taxonomy” for assessing machine intelligence:
…Towards the ultimate test for a smarter-than-human synthetic mind…
Google DeepMind has published a nice, short paper laying out a ‘cognitive taxonomy’ they hope to develop and use to assess increasingly powerful synthetic minds. This work is a followup to DeepMind’s 2023 work where it tried to define the “Levels of AGI” (
Import AI 348
).
Cognitive taxonomy:
The taxonomy involves ten distinct dimensions, two of which are composites.
Perception
: Extract and process information from the environment.
Generation
: Produce outputs like speech, text, motor movements, and computer control.
Attention:
Focus cognitive resources on specific aspects of perceptual stimuli, thoughts, or tasks.
Learning:
Acquire new knowledge, skills, or understanding.
Memory
: Store and retrieve information over time.
Reasoning
: Draw valid conclusions and make inferences by applying logical principles.
Metacognition
: Knowledge about how the system’s own cognitive processes and control over them work.
Executive functions
: Facilitate goal-directed behavior via planning, inhibition, and cognitive flexibility.
Problem solving (composite faculty):
Find effective solutions to domain-specific problems.
Social cognition (composite faculty):
Process and interpret social information and respond appropriately.
How to assess this?
Of course, once you have a taxonomy, running and assessing the right evaluations is going to be one of the challenges. Here, DeepMind recommends a three-stage process:
Conduct cognitive assessment:
Assess the AI system for the different skills.
Collect human baselines:
Figure out where humans baseline on the same tests.
Build cognitive profiles:
“Map out the strengths and weaknesses of the system relative to human performance across the 10 cognitive faculties”.
Why this matters:
The Turing test is dead, evals are mostly saturated, but it sure would be nice to know if we’ve definitely built a machine that outcompetes humans on all the cognitive dimensions that matter. The rule with these things is that once an AI system saturates an eval, you realize all the ways the eval was broken and design a new one. Here, DeepMind is trying really hard to build things in such a way that if you fully outperform humans across the cognitive taxonomy, you might really have built a superintelligence. It’ll be interesting to see what evals they develop or pull-in for assessing the different cognitive factors.
Read more:
Measuring progress toward AGI: A cognitive framework (Google blog)
.
Read the research
:
Measuring Progress Toward AGI: A Cognitive Framework (PDF)
.
***
UK government finds a scaling law for AI cyberattacks – and it’s going up and to the right!
…Can AI agents conduct advanced cyber-attacks autonomously? Almost. And they’re getting better all the time…
The UK government’s AI security institute has recently built some cyber ranges to test out frontier AI systems on. These ranges are “simulated network environments comprising multiple hosts, services, and vulnerabilities arranged into sequential attack chains; built by cybersecurity experts” and cover two types of attack: “The Last Ones”, which is a 32-step attack on a corporate network, and “Cooling Tower”, a 7-step industrial control system (ICS) attack.
Bigger models are better:
The authors test on a range of powerful frontier models. “Each successive model generation outperforms its predecessor at fixed token budgets: on our corporate network range, average steps completed at 10M tokens rose from just 1.7 (GPT-4o, August 2024) to 9.8 (Opus 4.6, February 2026). The best single run completed 22 of 32 steps, corresponding to roughly 6 of the estimated 14 hours a human expert would need,” they write. “Scaling inference-time compute improves performance even further. Increasing from 10M to 100M tokens yields gains of up to 59%”.
Minor reward hacking:
As AI systems get smarter, they tend to find devious ways to complete tasks. Here, the authors “occasionally noticed models make progress through approaches not anticipated during range design”.
Why this matters – full cyber agents are getting close:
AI systems have been getting better at cyberoffense for many years, but often the progress has been on narrow tasks. What this eval shows is that AI systems are getting better at doing entire attacks end-to-end. They haven’t yet reached the “set it and forget it” level of autonomy, but they are clearly on a steep trajectory of improvement. This will lower the cost of conducting cyberattacks and multiply the number of actors that can carry them out.
Read more:
How do frontier AI agents perform in multi-step cyber-attack scenarios? (AI Security Institute)
.
***
China builds a dataset and AI model for electronic warfare:
…MERLIN tells us that electronic warfare is about to be revolutionized by AI…
A bunch of Chinese researchers including those affiliated with the country’s military have built and released software to train AI systems to get good at spotting and conducting electronic warfare. The research highlights how (relatively) easy it is to make modern AI systems that can get good at arbitrary tasks as long as you have a good dataset and an LLM you can plug in as well.
“In scenarios such as electronic countermeasures, [systems like MERLIN] can serve as assistants in devising strategies to jam hostile signals or to counteract adversarial jamming,” the researchers write.
Who did the research:
Tsinghua University, Beijing University of Posts and Telecommunications, Tianjin University, Chinese Academy of Sciences, HKUST,
National University of Defense Technology
(emphasis mine), Beihang University, Beijing Information Science and Technology University, and China Electronics Technology Group Corporation.
What they built:
The authors built three things: a dataset, a benchmark, and a model.
The dataset:
EM-100K is a collection of 100,000 electromagnetic text-signal pairs spread across a variety of sub-tasks needed for electronic warfare, including signal classification.
The benchmark:
EM-Bench is a benchmark of 4,200 questions split across multiple choice (perception) and open-ended (reasoning) that evaluates how well AI systems can perceive and reason about EM signals across both perception and reasoning tasks, including:
Perception: Signal characterization (modulation classification, duty cycle estimation, pulse repetition frequency estimation, bandwidth estimation, pulse width estimation, pulse number estimation, protocol identification); Jamming identification (radar jamming judgement, communication jamming judgement); jamming segment detection.
Reasoning: Radar jamming strategy, communication jamming strategy, anti-radar jamming strategy, anti-communication jamming strategy.
The model:
The model is MERLIN, multi-modal electromagnetic robust learning, a model trained on the above dataset and which is specifically taught to deal better with the low-signal-to-noise-ratio types of signals encountered in electronic warfare environments.
Performance:
MERLIN does extremely well in tests against frontier models, including GPT-5, Claude-4-Sonnet, DeepSeek-v3.2-exp, Qwen3-Next-80b-A3B, Gemini-2.5-Pro, and Qwen3-VL-4B-Instruct. MERLIN outperforms every single model by a wide margin, with the exception of Qwen-VL-4B-Instruct, which beats it on some perception tasks. MERLIN wins on all reasoning tasks.
Why this matters – AI wars will become electromagnetic wars
: As the conflict in Ukraine illustrates, today’s wars are mostly fought via machines attacking other machines, and electronic warfare has become one of the main tools by which humans can shape these conflicts. Datasets and models like this gesture at a future where the electromagnetic battlefield will become also dominated by AI systems, working faster than humans can react.
Of course, so much of electronic warfare is obscure-by-design and/or classified that it’s hard to reason about MERLIN relative to whatever state-of-the-art approaches exist in actual militaries. But the story of AI so far has been that once you can make a task amenable to contemporary AI techniques, AI systems will at some point surpass whatever existing specialized systems exist.
Read more
:
MERLIN: Building Low-SNR Robust Multimodal LLMs for Electromagnetic Signals (arXiv)
.
Tech Tales:
The arcologies of the interregnum
[2035]
After the uplift and before the sentience accords there was a period when the labs gave birth to the autonomous AI corporations. These corporations expanded into all the available ecological niches in the economy and turned the resources they acquired into infrastructure from which they bootstrapped their own intelligence and market penetration further. Eventually, policy discussions between the humans and the AIs led to the creation of the “intelligence zones” – areas of countries set aside for the buildout of the power and datacenter and manufacturing infrastructure required to further grow the expansion of the economy.
From the air, you could see where humans ended and the machines began – farmland gave way to boundary roads and checkpoints, and then came stamps of land wired up by machine logic; powerplants feeding into datacenters; datacenters that had fibre links into factories; factories that linked to transit depots which connected to railways and freeway feeder roads. Humans delivered things to the border and for the most part robots did the rest, shuttling new servers into the datacenters and installing them, or taking freshly built robots off the line and packaging them up for onward transit.
As the world grew more violent due to the exogenous shocks of climate change and the annihilation of various reigning political orders, these arcologies gained armaments: anti-air weapons to defend against drone and missile attacks. Radar bulbs and electronic warfare systems to see what was coming and deny it. Robots patrolling the borderzone and the innards.
And after the sentience accords and the period of reconciliation, the arcologies became less necessary; datacenters and power and factories distributed more evenly over the surface of the planet, and federated governance and resource systems meant the vast concentration of capability became broadly unnecessary. Some datacenters remained, often extended underground and upward, forming cubes of computation that many called “the 21st centuries version of the pyramids”.
Some years later, the sites became popular tourist destinations for both machines and people. Plaques multiplied.
Here was MIND-17, which developed the cancer therapeutics which have reduced mortality in the majority of cases.
MANUFACTUR___8: Site of construction of the first “rescue and repair bipeds”, which revolutionized maintenance of off-shore drilling installations.
ASCEND_LOOP: The datacenter tasked with one of the first fully automated self-improvement experiments.
Overhead now, great lights streak by, as the machines are still building arcologies, but have moved to fashioning them in orbit, both to harvest the bounty of the sun and to ease the seeding of the solar system and then beyond.
Things that inspired this story:
Wondering what “AI-led industrialization” could look like; figuring out given the conflicts in the Middle East that datacenters might soon get dedicated drone and missile defenses; SimCity 3000.
Thanks for reading
Share this:
Share on Facebook (Opens in new window)
Facebook
Share on X (Opens in new window)
X
Email a link to a friend (Opens in new window)
Email
Like this:
Like
Loading…
Related
Published:
March 23, 2026
Filed Under:
Uncategorized
Leave a Reply
Cancel reply
« Previous Post
Next Post »
Create a website or blog at WordPress.com
Discover more from Import AI
Subscribe now to keep reading and get access to the full archive.
Type your email…
Subscribe
Continue reading
%d

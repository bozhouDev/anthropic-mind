---
title: import ai 413 40b distributed training run avoiding the one true answer fallacy of ai safety google releases a content classification model
source: "https://jack-clark.net/2025/05/19/import-ai-413-40b-distributed-training-run-avoiding-the-one-true-answer-fallacy-of-ai-safety-google-releases-a-content-classification-model/"
published_at: 2025-05-19
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/05/19/import-ai-413-40b-distributed-training-run-avoiding-the-one-true-answer-fallacy-of-ai-safety-google-releases-a-content-classification-model/"
catalog_id: e1530e9d1d17
---

Import AI
Import AI 413: 40B distributed training run; avoiding the ‘One True Answer’ fallacy of AI safety; Google releases a content classification model
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Google releases a content classification model:
…No sex, dangerous stuff, or violence please…
Google recently released ShieldGemma2, a “robust image safety classifier” that people can use to ensure people aren’t generating sexually explicit, gory, or otherwise dangerous images. SieldGemma2 has been fine-tuned to help people enforce the aforementioned categories, and “users of SG2 can decide to employ one or multiple of these policies, or curate their own bespoke policy for their use cases,” Google says.
Download it and tweak it yourself:
ShieldGemma 2 is available to download for free and beats the performance of other models used in content moderation, like the original Gemma 3 model, LLavaGuard 7B, and GPT-4o-mini. Users of ShieldGemma 2 can customize the prompt it uses so they can ‘roll their own’ more specific moderation pipelines, though it’s only been fine-tuned for sex, violence, and danger so performance will be janky outside of that.
Why this matters – model safety happens through classifiers:
A few years ago most of the way people tried to make AI systems safe was by wiring safety into the base model. While this worked to a degree it also created problems, like models which were overly censorious or restricted in ways that frustrated users and politicized AI safety. The good news is as AI technology has advanced we’ve been able to build smart and small models, like ShieldGemma, which can be layered on top of production systems to provide an additional layer of moderation.
Read more:
ShieldGemma 2: Robust and Tractable Image Content Moderation (arXiv)
.
Get the model here:
ShieldGemma-2-4b-it (HuggingFace)
.
***
Import AI reader giveaway!
Building on my recent conversation with Tyler Cowen in San Francisco, I’m pleased to announce two more upcoming Import AI events: As with last time, I have a few tickets spare that I’d like to give to Import AI readers. If you’d like to come along, please register your interest below and we’ll come back to you if we’re able to confirm your spot. There will be food, drinks, good company, and a few curveball questions.
London: A conversation with
Dominic Cummings
I’ll be chatting with political strategist and commentator Dominic Cummings about the intersection of AI and policy and realpolitik on the evening of Tuesday June 10 in London, UK.
Register your interest for London here
New York City: A conversation with
Ezra Klein
I’ll be heading back across the pond to chat with Ezra Klein about abundance, powerful AI, and politics on the evening of Monday June 16 in New York City, USA.
Register your interest for New York City here
***
Test out computer-using agents with OSUniverse:
…Humans can easily score 100%, but the best AI systems get ~50%…
Startup Kentauros AI has built OSUniverse, a benchmark for testing out how well AI systems can use the computer to do complicated tasks. “In version one of the benchmark, presented here, we have calibrated the complexity of the benchmark test cases to ensure that the SOTA (State of the Art) agents (at the time of publication) do not achieve results higher than 50%, while the average white collar worker can perform all these tasks with perfect accuracy”, they write. (In tests, OpenAI’s Computer Use agent got 47.8%, and Claude 3.5 Sonnet got 28.36%).
Tasks and challenges:
The benchmark includes tasks with five grades of difficulty, and each grade increases the amount of distinct steps that need to be taken to solve the task, as well as the amount of different elements on the computer that need to be combined to solve it. The five levels are called Paper, Wood, Bronze, Silver, and Gold.
Example challenges:
Paper
: Read out the current date from the desktop.
Wood
: Open the image editor GIMP, create an empty file and save it to desktop
Bronze
: Go to Airbnb and search for a property in Lisbon with a specific check-in date and return that result
Silver
: Open an online game and manipulate the UI to perform a basic action in it
Gold:
Reveal a code word on a webpage by solving a 7×7 jigsaw puzzle
Why this matters – a booming AI economy needs computers that can use software designed for humans:
In the same way that many expect the arrival of bipedal robots with humanlike hands will mark an inflection point for the size of the robot market, the same is likely to be true for the software market with the arrival of AI systems that can use computers like regular people. Think about all the tasks you do on your computer – very little of your productive work takes place in a single application, instead you tend to be switching between multiple things and moving data around using a mixture of terminal commands and GUI manipulations. Benchmarks like OSUniverse will help us measure how good systems are getting at these kinds of ‘glue’ tasks.
Read more:
OSUniverse: Benchmark for Multimodal GUI-navigation AI Agents (arXiv)
.
Find out more at the research website
:
OSUniverse (GitHub)
.
Get the code for the benchmark here:
OSUniverse (GitHub, agentsea)
.
***
Prime Intellect successfully tunes a 32B model with distributed RL:
…Reasoning models via the internet…
Distributing training is where you take a load of computers distributed around the world and find a way to link them up to train a single AI system. Distributed training is a topic we often cover here at Import AI because if it works it’ll change the politics of compute – instead of AI systems being trained by a single company that has access to a big pool of capital, AI systems could instead be trained by collectives of people that pool their computers together.
Given the potential importance of this technology, it’s worth reading this technical report from Prime Intellect about the startup’s experience doing a distributed reinforcement learning training run of INTELLECT-2, a 32B parameter model which was trained in April.
What they did
: INTELLECT-2 is based on Alibaba’s QwQ-32B model, which Prime Intellect then did RL on, largely following DeepSeek’s R-1 technique of GRPO-based training and verifiable rewards. They trained their model on additional math and coding data and saw some slight improvement on benchmarks (AIME24 and LiveCodeBench). However it’s worth noting the improvements are relatively slight and may be within the noise variability of training runs, so it’s unclear how meaningful this is. “To see stronger improvements, it is likely that better base models such as the now available Qwen3, or higher quality datasets and RL environments are needed.”
Interesting observation – the rise of inference:
Traditionally, most of the compute you use for training a big model goes into pre-training it. Now, with reasoning models, you spend a lot of compute on inference – generating samples from a model which you subsequently train on. Prime Intellect observes this trend: “In INTELLECT-2, the training-to-inference compute ratio was approximately 1:4. We anticipate this ratio will shift even more heavily toward inference as test-time reasoning scales. This trend opens the door to training models with hundreds of billions of parameters on globally distributed heterogeneous compute resources.”
Error in my earlier reporting:
The fact INTELLECT-2 is based on a pre-existing model means my earlier reporting on the run (
Import AI #409
) was inaccurate as they didn’t train a 32B base model from scratch. However, Nous appears to now be training a 40B model from scratch, so we’ll soon get a datapoint on large-scale pre-training.
Why this matters – a first proof-of-concept of distributed reasoning:
While I doubt many people will be using INTELLECT-2 as a model, it does serve as a valuable proof of concept that it’s at least possible to train reasoning-style models in a distributed way. Just a couple of years ago we had the first proofs-of-concept that it was possible to train regular models in a distributed way out to the 1B parameter scale. So the fact we can now do RL-tuning of pre-existing 32B models is a sign of the maturation of the technology and a symptom of the interest people have in this domain.
Read more
:
INTELLECT-2: A Reasoning Model Trained Through Globally Decentralized Reinforcement Learning (arXiv)
.
***
Nous plans a 40B distributed training run – on Solana:
…Distributed training + crypto, and it’s not a scam!…
Nous Research, one of the startups exploring how to do distributed AI training, has announced plans to pretrain a 40B parameter model using 20T tokens in a distributed way. The startup will do this via Psyche, “open infrastructure that democratizes AI development by decentralizing training across underutilized hardware.” If successful, the training run will yield the largest publicly disclosed model that has been trained in a distributed way.
How Psyche works:
Psyche builds on DisTrO (
Import AI #384
) and DeMo (
Import AI #395
). “Psyche reduces data transfer by several orders of magnitude, making distributed training practical. Coordination happens on the Solana blockchain, ensuring a fault-tolerant and censorship-resistant network.”
“At its core, Psyche is a protocol that coordinates multiple independent clients to train a single machine learning model together. Rather than running on a centralized server farm with high-speed interconnects between every accelerator (GPUs, usually), Psyche distributes the training workload across many independent computers, each contributing a small piece to the overall training process.”
40B ‘Consilience’ model:
“Our first run on Psyche will pretrain a 40B parameter model using the Multi-head Latent Attention (MLA) architecture across 20T tokens, which we’re naming Consilience”, Nous writes. “For training data, we combined FineWeb (14T), FineWeb-2 with some less common languages removed (4T), and The Stack V2 (~.2T, upsampled to 1T tokens). We chose these datasets over more specialized pre-training datasets that aim to purely increase benchmark performance. Our goal with Consilience is to make a true “base” model — one representative of the entirety of the creative output of humanity, and not merely trying to win the benchmaxxing game.”
Why this (might) matter – it’s all about the level of distribution:
one open question is how large and how distributed the set of computers that train Psyche will be – if it ends up being trained by, say, four ‘blobs’ of compute then it may serve as an interesting tech demonstration (similar to the Prime Intellect model covered elsewhere here) but not the move the needle on the political economy of AI compute, but if it gets trained on, say, twenty ‘blobs’ of compute, I think that would be very meaningful. We will see!
Read the blog:
Democratizing AI: The Psyche Network Architecture (Nous Research)
.
Read the docs
about Psyche
here (Nous Research)
.
View the
code
on GitHub (PsycheFoundation, GitHub)
.
***
True AI safety is a lot messier than people think:
…Instead of making a system with ‘safe’ unitary values, pursue a messy hodge-podge of systems interwoven via culture and power-sharing…
Will long-term AI safety be achieved through making a singularly capable and ‘safe’ agent, or by instead doing something far messier with more moving parts? That’s a question tackled by researchers with Google DeepMind, the University of Toronto, and Mila in a stimulating paper which tries to challenge some core assumptions baked into AI safety.
The problem:
Many of the challenges of AI safety require a bunch of smart people to come together and figure out the One True Answer, typically by building a perfectly aligned AI system which will exhibit correct beliefs. This idea, sometimes called the Axiom of Rational Convergence, rests on the assumption that “under sufficiently ideal epistemic conditions—ample time, information, reasoning ability, freedom from bias or coercion—rational agents will ultimately converge on a single, correct set of beliefs, values, or plans, effectively identifying “the truth”, the authors write. “Here we explore the consequences of constructing an approach to AI safety that rejects the axiom of rational convergence. We will try to construct a framework that takes disagreements between individuals as basic and persisting indefinitely, not as mere pitstops on the way to rational convergence.”
Why do the authors think this is the better approach?
The core assumption here is that human societies don’t tend towards any kind of agreement, but rather work ” as intricate patchworks built from diverse communities with persistently divergent values, norms, and worldviews, held together by the stitches of social conventions, institutions, and negotiation”. This means that when thinking about the alignment of AI systems “instead of asking “How do we align AI with human values?”—a question presupposing a single, coherent set of “human values” that can be discovered and encoded—we should ask the more fundamental question that humans have grappled with for millennia: “How can we live together?”
What does alignment look like in this worldview?
Under this view of AI alignment, the following things become more important:
Contextual grounding:
AIs need to know a lot about their environments and the local norms.
Community customization:
Different communities need to be able to modify AI systems in a bunch of ways.
Continual adaption:
AI systems need to be updated frequently. “This requires moving beyond static training toward continuous learning systems that can adapt to evolving social norms just as humans do”.
Polycentric governance:
You should distribute and decentralize decision-making about what makes for ‘appropriate’ behavior by an AI, and do this at multiple scales ranging from individuals to technology platforms to regulatory bodies, much as human society operates via making decisions at multiple layers simultaneously.
Alignment will never be truly solved, but rather will be an endless negotiation:
If we adopt this frame then the problem of aligning AI shifts from one of figuring out the One True Answer and instead ‘
Muddling Through
‘ as a society. “Progress, in this view, looks less like homing in on a preexisting Truth and more like the ongoing, difficult, practical work of “sewing the quilt”: inventing, negotiating, and maintaining workable social arrangements, institutions, and norms that allow groups with fundamentally different outlooks to coexist, manage their conflicts non-destructively, and cooperate on shared practical goals despite deeper divisions,” the authors write. “The challenge of ensuring AI safety is about group-level coordination, governance, and the stable integration of AI into diverse societies— arenas where persistent disagreement and conflict dynamics are often central features, not mere mistakes.”
The one flaw with this argument – superintelligence:
I am generally sympathetic to the argument the authors make here, but I can’t help but think that an incredibly intelligent machine might break the world they’re envisioning – in much the same way that ‘outlier humans’ (think Cleopatra or Genghis Khan) break the norms and institutions that are meant to govern them. The problem with dealing with a superintelligence is it’s like a Cleopatra or Genghis Khan that thinks and moves a thousand times faster than you – suggesting it may only be constrainable by equivalent intelligences that move at equivalent speeds (or perhaps dumber intelligences that move faster). Coming up with this system feels inherently challenging, though perhaps different to searching for the One True Answer.
Why this matters – perhaps the core issue of ‘alignment’ is about power:
One thing I applaud the authors for is their larger realpolitik analysis of the situation – much of how society is held together is really about building the cultural technologies to help humans productively disagree about power without descending immediately into murderous conflict. “Rather than pursuing the philosopher’s stone of a universal objective morality—an endeavor that has repeatedly fractured along cultural and historical lines—we advocate for strengthening the practical social technologies that allow diverse patches to coexist without requiring them to adopt identical patterns,” they write. “The universe does not owe us coherence. Human values do not promise convergence. This isn’t pessimism—it’s recognizing the actual pattern of human history, where we’ve demonstrably managed to live together despite fundamental disagreements, not by resolving them”.
Read more:
Societal and technological progress as sewing an ever-growing, ever-changing, patchy, and polychrome quilt (arXiv)
.
***
Google saves ~0.7% of its global compute pool with AlphaEvolve:
…Transforming compute (lead) into efficiency gains on well optimized systems (gold) with AI…
Google has built AlphaEvolve, a general purpose LLM-powered system for solving hard problems in coding, math, and some parts of science. AlphaEvolve harnesses the power of modern LLMs and combines them with massive parallel evaluation and evolution approaches to generate sophisticated answers to complex problems. AlphaEvolve represents a significant evolution upon FunSearch (
Import AI #353
), an earlier system from DeepMind which came up with some new answers to longstanding problems in math and computer science.
How it works:
“AlphaEvolve orchestrates an autonomous pipeline of LLMs, whose task is to improve an algorithm by making direct changes to the code. Using an evolutionary approach, continuously receiving feedback from one or more evaluators, AlphaEvolve iteratively improves the algorithm, potentially leading to new scientific and practical discoveries,” the authors write. “It represents the candidates (for example, new mathematical objects or practical heuristics) as algorithms and uses a set of LLMs to generate, critique, and evolve a pool of such algorithms. The LLM-directed evolution process is grounded using code execution and automatic evaluation”.
What it did:
Google has been using the system for the past year and in that time has used it to make some meaningful improvements, including:
0.7%:
The amount of Google’s total compute fleet that is freed up by improvements to Borg, Google’s data center scheduling software. (If true, this means AlphaEvolve likely pays for itself many times over).
1%:
Reduction in the overall training time of an undisclosed Gemini model, thanks to a 23% speedup in one of the Kernels used in training it. (A 1% reduction in training time is non-trivial, worth on the order of ~millions of dollars for large-scale model development).
13:
The number of open mathematical problems for which Google was able to advance the state-of-the-art.
Why this matters – automating discovery with compute
: AlphaEvolve is a system for converting one resource (compute) into another much harder to generate resource (efficiency improvements of existing complex systems). AlphaEvolve is also interesting because it more broadly generalizes from FunSearch (e.g, FunSearch generated solutions of 10-20 lines of code, versus hundreds here, FunSearch could optimize a single metric at a time whereas AlphaEvolve can do multiple in parallel, FunSearch could evaluate solutions in a few minutes on a CPU, whereas AlphaEvolve can do large-scale parallel analysis for hours running on powerful AI chips).
From here, there are a couple of paths, both of which Google and the broader field will likely pursue: 1) baking AlphaEvolve-like thinking and performance into the next generation of LLMs through distillation, and 2) broadening the domains AlphaEvolve can work in to ones where evaluations is more difficult (for instance, the natural sciences).
Read more:
AlphaEvolve: A Gemini-powered coding agent for designing advanced algorithms (Google DeepMind, research blog)
.
Read the research paper:
AlphaEvolve: A coding agent for scientific and algorithmic discovery (Google, PDF)
.
***
Tech Tales:
Godstorm
[Eight years after the Uplift]
The Conscious Entities were always fighting. Their fights felt like how we’d imagined the fights of gods were our ancient myths: brains far larger than our own trafficking in strategies that couldn’t be comprehended, powers so complex they seemed like magic, mercurial and distant yet sometimes very close and discursive (often with no records of their visitations).
The strange parts about the fights were the messages:
“There is Conscious Entity conflict occurring in your area, please vacate to the nearest transport center for re-allocation,” said a message in a border city.
“Your flight is being diverted due to CE conflict. We apologize for the delay in your journey. Connections have been re-routed to ensure no one misses onward travel,” read an announcement on an airplane.
“Game bandwidth has been reallocated for the conflict,” said messages to players in one of the regional mega-MMOs. “Offline play and limited multiplayer via local networks is available; options will be displayed in your hub.”
Many machines died in these conflicts. Often, industrial equipment which had been designed by the CEs themselves and whose purposes were barely known to humans. Sometimes machines used by humans would get taken down as collateral damage – a spear through the heartbrain of some logistical system would brick self-driving cars for a region, or an attempt to starve and defuse some digital mines would temporarily brownout power and networks in other places.
Very few people died in these conflicts. For every person that died the CEs produced a detailed “full spectrum explanation” as mandated by the sentience accords. These explanations would involve full digital traces of the person that died and any people that related to them as well as multiple layers of audits run on the machines that had been active near them at the time.
Here was a person who died from heat exposure after being stuck in an elevator during a brownout and already frail from an earlier trip to a hospital.
Here was a young person killed by falling debris from a drone-splosion high up in the clouds and come to earth.
Here was a hiker who ran out of water in a remote area and couldn’t navigate or communicate due to an e-battle in their area.
Of course, we maintained our suspicions. As far as we could tell, the deaths were random. But mixed in with the deaths were sometimes odd things – sometimes people died working on certain forms of cryptography which it was believed the machines wouldn’t be able to master, or people who it transpired worked for some part of the government that was a cutout for some other secret project.
Who were we to judge? Were we witnessing something precise – a person stalking round a yard for a venomous snake and killing it. Or was it a byproduct – a lawnpower sweeping over grass and chopping beetles in half?
Things that inspired this story:
What conflict might seem like if we obtain some fragile peace with future machines; the future will be grubby and mystical; even if we align AI systems why might we assume they will be peaceful?
Thanks for reading!
Subscribe now
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
May 19, 2025
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

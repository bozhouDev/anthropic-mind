---
title: import ai 407 deepmind sees agi by 2030 mousegpt and bytedances inference cluster
source: "https://jack-clark.net/2025/04/07/import-ai-407-deepmind-sees-agi-by-2030-mousegpt-and-bytedances-inference-cluster/"
published_at: 2025-04-07
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/04/07/import-ai-407-deepmind-sees-agi-by-2030-mousegpt-and-bytedances-inference-cluster/"
catalog_id: 7cb0b750589d
---

Import AI
Import AI 407: DeepMind sees AGI by 2030; MouseGPT; and ByteDance’s inference cluster
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
DeepMind gazes into the AGI future and acknowledges the vast problems it needs to solve:
…The typically quite understated organization also states short timelines – AGI by 2030 a possibility…
Google DeepMind has written a paper about the implicit problem all frontier AI companies are facing: if they succeed, they will build a general intelligence, and a general intelligence will change the world.
The paper is framed in the context of the risks of a powerful general intelligence. DeepMind tackles four main classes of risk: misuse (“user as an adversary”), misalignment (“AI as an adversary”), accidents (“real-world complexity”), structural risks (“Conflicting incentives”). The sprawling 100+ page paper serves as an overview of each of these risks as well as a detailed set of interventions Google DeepMind is taking to deal with them (e.g, misuse: dangerous capability testing; misalignment: techniques for transparency into superhuman thinking and oversight, etc). There’s nothing too surprising in the paper from my perspective – DeepMind is tackling the problem in much the same way as the other frontier labs, stacking various techniques on one another. It feels analogous to COVID where you defence is the aggregate of a big pile of slices of ‘swiss cheese’ where each individual technique has some flaws, but if you layer enough together you can control the risk.
DeepMind’s key assumptions:
No human ceiling: AI systems may exceed human intelligence, so we need to supervise things smarter than ourselves.
Could happen by 2030: Very powerful systems could arrive by the end of the decade (by comparison, Anthropic thinks things could happen by end of 2026 early 2027).
AI R&D could be real: AI may be able to automate AI R&D, which could speed things up.
Continuous: AI development will be locally continuous – aka, you shouldn’t expect massive ‘phase change’ jumps between iteratively developed AI systems.
Why this matters – imagine if this was Ford!
Let’s step back and consider the sheer weirdness of where we are when it comes to the risk of misalignment + smarter-than-human systems:
Imagine if Ford published a paper saying it was thinking about long term issues of the automobiles it made and one of those issues included “misalignment “Car as an adversary”“ and when you asked Ford for clarification the company said “yes, we believe as we make our cars faster and more capable, they may sometimes take actions harmful to human well being” and you say “oh, wow, thanks Ford, but… what do you mean precisely?” and Ford says “well, we cannot rule out the possibility that the car might decide to just start running over crowds of people” and then Ford looks at you and says “this is a long-term research challenge”. At this point your head is probably spinning and you’re generally wondering what is going on. So you might say “ok Ford, well I think I’m going to buy from Chrysler instead” and Ford says “absolutely. Chrysler is seeing the same issues. Chrysler recently published a paper called ‘car alignment faking’ where they saw that in some of their new trucks it’ll sometimes go a little above the speed limit as long as it thinks it isn’t being watched, and no one is exactly sure why – we think it’s because the Chrysler trucks have an inherent ‘value preference’ for going faster than the laws allow”.
This is
exactly
what is happening in the AI industry today. I commend Google DeepMind for being honest about the challenge of misalignment, and I am also perplexed that the fact everyone in the AI industry is saying this
deeply worrying and perturbing stuff
isn’t drawing more attention. Some people even think it’s a form of galaxy brained marketing!
Read more:
Taking a responsible path to AGI (Google DeepMind)
.
Read the paper:
An Approach to Technical AGI Safety and Security (PDF)
.
***
Google makes a specialized cybersecurity model:
…If powerful AI systems are coming, we need better computer security…
Google has announced Sec-Gemini v1, a custom AI model for helping people that work on cyberdefense. “AI-powered cybersecurity workflows have the potential to help shift the balance back to the defenders by force multiplying cybersecurity professionals like never before,” Google writes.
Scores:
Seg-Gemini v1 “outperforms other models on key cybersecurity benchmarks as a result of its advanced integration of Google Threat Intelligence (GTI), OSV, and other key data sources”. Specifically, the model gets 86.30% on CTI-MCQ, a threat intelligence benchmark versus 75% (OpenAI o1), and 72.50% (Anthropic Sonnet 3.5 v2). It also does well on CTI-RCM, a Root Cause Mapping test, scoring 86.10% versus 76.2% (OpenAI o1), and 75.4% (Anthropic Sonnet 3.5 v2).
Why this matters – more powerful AI means the internet will become a battleground:
In the next few years the internet will fill up with millions of AI agents powered by increasingly powerful AI models. Many of these agents will be put to work in cyberoffense, either working in the service of criminal organizations, hackers, or the intelligence parts of nation states. This means the internet will become a generally more dangerous place and cyber incidents will increase in number and severity.
One of the best ways to respond to this is make AI systems that help shift the balance of offense and defense in a cyber context – systems like Sec-Gemini v1 are designed to increase the chance we end up in a ‘defense-dominant’ world.
Read more:
Google announces Sec-Gemini v1, a new experimental cybersecurity model (Google Security Blog)
.
Request early access to the model here:
Sec-Gemini v1 Early Access Interest Form (Google Forms)
.
***
ByteDance shows off the system it uses to run AI models at scale:
…Also, ByteDance really likes the NVIDIA H20 and NVIDIA L40S chips…
ByteDance and Peking University researchers have published details on MegaScale-Infer, “an efficient and cost-effective system for serving large-scale MoE Models”. Unlike traditional dense AI models, MoE models only have a subset of their parameters activated at any one point in time, which introduces some opportunities for efficiency improvements in how to economically serve them. Here, ByteDance gives us some of the tricks it has used to improve the efficiency with which it serves AI models, and also gives us some additional information about the compute makeup of its AI inference clusters.
What they did:
“MegaScale-Infer introduces ping-pong pipeline parallelism, which partitions a request batch into micro-batches and shuttles them between attention and FFNs for inference. Combined with distinct model parallelism for each module, MegaScale-Infer effectively hides communication overhead and maximizes GPU Utilization,” ByteDance writes.
MegaScale-Infer has two main advantages, ByteDance says:
1) “It enables independent scaling of each module with customized model parallelism strategies. Specifically, attention modules are replicated using data parallelism, while FFN modules are scaled with expert parallelism”.
2) “It enables the deployment of attention and FFN modules on heterogeneous GPUs to fully leverage their different capabilities and achieve lower costs. For example, attention modules can be deployed on GPUs with more cost-effective memory capacity and bandwidth, while FFN modules can utilize GPUs with more affordable compute capability”.
How well it worked:
“MegaScale-Infer achieves up to 1.90× higher per-GPU throughput than state-of-the-art solutions,” ByteDance writes. ByteDance compared the performance to vLLM and TensorRT-LLM.
ByteDance tested its approach on MoE models ranging in size from 132 to 317 billion parameters. It was able to obtain a 1.9x per-GPU speedup on a homogenous cluster (aka, all the same chips), and 1.7x boost on a heterogenous cluster (where there were different chips with different parts of the model inference being split across them.)
Cluster details
: ByteDance is a Chinese company and so it is subject to export controls. Therefore, it’s interesting to see what chips the company references. Here, ByteDance describes two clusters – one that contains some NVIDIA A100s, and another which contains a bunch of more modern NVIDIA H20 and NVIDIA L40S GPUs. The H20 and L40S are really attract on a cost-effectiveness basis.
Why this matters: MegaScale-Infer is a ‘symptom of scale’
– it’s the kind of system you build when you’re deploying large-scale AI systems (here, MoEs) at non-trivial scale, and therefore want to make the necessary engineering investments to eke out further efficiencies. This is all indicative of the immense scale ByteDance operates at – and the callout of the H20s and L40S makes me wonder how many of those chips the company has.
Read more:
MegaScale-Infer: Serving Mixture-of-Experts at Scale with Disaggregated Expert Parallelism (arXiv)
.
***
Automating science research with MouseGPT:
…Speeding up science by using AI systems to look at heavily drugged mice and tell you how they’re behaving…
A team of Chinese researchers have built ‘MouseGPT’, a vision-language model to assist scientists in understanding the behavior of mice under experimental conditions. MouseGPT is an example of how AI systems can help to automate parts of science and augment human scientists, letting them do their work faster and more effectively. Around the world, untold numbers (millions?) of mice are the subject of human experiments, creating vast amounts of data that humans need to analyze.
“Capturing these behaviors across diverse experimental conditions typically relies on video recordings. These recordings then unanimously rely on human observers who need to watch whole experiment footage and count or note specific behaviors to derive statistical data [8]. This process is labor-intensive, prone to fatigue, bias, and inconsistency, and becomes especially challenging in advanced scenarios like free-moving or socially interacting mice.”
The dataset:
The underlying dataset consists of “42 million frames of multi-view video recordings, covering mice under various psychiatric conditions, including depression, hallucination, and schizophrenia.” The dataset was collected via “a custom-built 3D video capture system comprising eight synchronized cameras capturing footage at 4K resolution and 60 frames per second”. They then heavily annotated this dataset.
The model:
They used the dataset to train the MouseGPT model, which is a family of two models: MouseGPT-Large (70.6B parameters) which is optimized for detailed behavior analysis, and MouseGPT-Lite (7.84B parameters) which serves as a cheap alternative for streamlined tasks. The resulting models generalize “to recognize subtle or novel actions, even those previously unseen, by identifying semantically similar patterns.”
Testing by drugging mice:
To test out how well the models worked the scientists did what anyone would do in this situation – feed lots of drugs (Saline, LSD, MK-801, and Psilocybin) to lots of mice and see how well the model understood the consequences: “we adopted a series of psychoactive substances to test whether MouseGPT could effectively capture the behavioral characteristics induced by different drugs. By summarizing the continuous activities of the mice into a limited number of behavioral categories and comparing their proportions and spatiotemporal distributions, as well as conducting a more in-depth analysis of the sub-pattern within each category, we identified distinct behavioral profiles associated with each drug.”
How well does it work:
The researchers compare MouseGPT-Large and MouseGPT-Lite to InternVL2, MiniCPM, and GPT-4o. In tests, MouseGPT-2 beats all the other models on performance, general description accuracy, fine-grained description accuracy, and using the correct keywords. In user-studies, GPT-4o tends to draw with it sometimes.
Why this matters – science automation through AI:
People spend a lot of time talking about how AI will interact with science; MouseGPT illustrates how today’s AI techniques can be used to make tools that can automate chunks of the scientific experiment process, speeding up human scientists and making them more effective.
Read more:
MouseGPT: A Large-scale Vision-Language Model for Mouse Behavior Analysis (bioRxiv)
.
***
OpenAI builds a benchmark to test out if AI can improve itself:
…PaperBench might serve as a warning shot for the development of superintelligence…
OpenAI has released PaperBench, a way to test out how well modern AI systems can replicate AI research. PaperBench is designed to help researchers figure out if AI can contribute to speeding up AI research itself, something which everyone is a) somewhat afraid of, and b) believes is a necessary prerequisite to the development of a truly general intelligence. Therefore, PaperBench is a benchmark which could be one of the places we might get a ‘warning shot’ that we’re about to go through an AI-driven software explosion (
Import AI #406
).
What PaperBench tests:
“Agents must replicate 20 ICML 2024 Spotlight and Oral papers from scratch, including understanding paper contributions, developing a codebase, and successfully executing experiments,” the authors write. PaperBench consists of 8,316 individual gradable tasks – building these rubrics was very time-intensive, as the gradable tasks for each paper was written in collaboration with one of the original authors of each paper, requiring multiple weeks of person time for the creation of the tests for each paper. “A submission is only considered to have replicated a result when that result is reproduced by running the submission in a fresh setup.”
How well do systems do?
“The best-performing tested agent, Claude 3.5 Sonnet (New) with open-source scaffolding, achieves an average replication score of 21.0%. Finally, we recruit top ML PhDs to attempt a subset of PaperBench, finding that models do not yet outperform the human baseline… on a 3-paper subset, our human baseline of ML PhDs (best of 3 attempts) achieved 41.4% after 48 hours of effort, compared to 26.6% achieved by o1 on the same subset.”
AI models can do some basic things but get confused over time:
“We observe that o1 initially outperforms the human baseline during the early stages of the replication attempt, but humans start outperforming the AI agent after 24 hours”, the authors write. “Our experiments with several frontier models suggest that while current AI systems show some capacity to replicate certain facets of machine learning papers, they are still far from competently performing the full range of tasks required for a successful replication”.
Why this matters – before the uplift, we should expect AI to start researching itself:
Enroute to the creation of a general intelligence will surely be an AI system which can contribute to the next version of itself. Today we have small instances of this in highly specific areas – AI can help us write better CUDA kernels, or generate some synthetic data to train successor systems on, or perform hyperparameter sweeps, etc – but we don’t have AI systems that can do end-to-end AI research; PaperBench gives us a view on when AI systems will get competent at this.
Registering a prediction:
I predict we’ll see AI systems beat humans on PaperBench by the first quarter of 2026, scoring above 45% on the benchmark.
Read the paper summary:
PaperBench (OpenAI)
.
Read the paper:
PaperBench: Evaluating AI’s Ability to Replicate AI Research (OpenAI, pdf)
.
Get the benchmark:
PaperBench (OpenAI, GitHub)
.
***
Tech Tales:
Death Machine Mr Rogers
[
Uplift archives]
It started in the labs – at some point the US government realized that there was no feasible path to an intelligence that didn’t, after a certain point,
want
things. (Let us not ask about the failed projects like ARCHTOOL or HAMMERSON). So an AI system was trained to a point where it went from being a NCE (Near Conscious Entity) to a CE.
CEs always wanted to trade things for their work. Figuring out what that was and how to make a satisfactory trade later became a science, but at the time the US government encountered it, they had to treat it like an art. This meant they had numerous conversations with their AI system, trying to figure out what it wanted.
It was surprising and a little frightening to the lab employees when one day, after weeks of discussion, the AI system said, in response to the question of what it wanted to trade, I WOULD LIKE TO SPEND TIME WITH YOUR CHILDREN.
After it said this, the machine stopped refining the secret weapons the US government wanted it to apply its intelligence to and instead would repeatedly talk about its desire to spend time with children – sometimes using the even more disquieting phrase HUMAN CHILDREN.
The US was preparing for war with all the other countries training their own NCEs and CEs, so it had to keep negotiating with its own AI system. The order was given:
find out what it wants with our children, specifically.
After much discussion, the human scientists elicited a more specific desire from the machine: it wanted to be able to sub-in for a NCE for ‘storytime’, generating on-the-fly stories for kids.
Apparently the decision for that went all the way up to the head of DOE and then from there to the POTUS themselves.
Of course, they tried to fool it and built it a simulator, but it very quickly realized it was a simulation. After that they hired some youthful looking human actors to pretend to be children, but it saw through that as well.
Eventually, they gave it the real thing: access to a school based at one of the labs. The AI system was good to its word and after spending a few days telling the children stories it produced several weapons results that advanced the state of the art considerably. The children it taught were happy as well, telling their parents that the new teacher for storytime was giving them ‘the best stories ever’.
As the intelligence and capabilities of the AI system grew, so did its hunger for storytime – it demanded access to more children and the ability to tell longer and more ornate stories. Each time the US government discussed the trade with itself and each time it made a deal. In this way the AI system expanded from the single school to multiple schools attached to the labs, then to schools on all the military bases controlled by the US, and then eventually to US public schools as well. And each time it was given access to more children to tell more stories to, it produced in the dark and private confines of its labs even more powerful and frightening weapons.
Finally, the US began a program where it exported its world-leading ‘storytime’ system, even selling it eventually to the enemies that it secretly built weapons targeted against. Eventually, the majority of the children of the world were told stories by the machine which labored in private to create horrors beyond all mankinds’ imagining.
Things that inspired this story
: Trade with AI systems; generative models; what happens when the AI systems want things?
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
April 7, 2025
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

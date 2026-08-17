---
title: "ImportAI 449: LLMs training other LLMs; 72B distributed training run; computer vision is harder than generative text"
source: "https://jack-clark.net/2026/03/16/importai-449-llms-training-other-llms-72b-distributed-training-run-computer-vision-is-harder-than-generative-text/"
published_at: 2026-03-16
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2026/03/16/importai-449-llms-training-other-llms-72b-distributed-training-run-computer-vision-is-harder-than-generative-text/"
catalog_id: 8778cc1c0263
---

Import AI
ImportAI 449: LLMs training other LLMs; 72B distributed training run; computer vision is harder than generative text
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on arXiv and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Can LLMs autonomously refine other LLMs for new tasks? Somewhat.
…PostTrainBench shows startling growth in AI capabilities at post-training…
AI-driven R&D might be the most important thing in all of AI, because it helps us understand whether AI systems might eventually build their own successors. So far, much of the focus on AI R&D has been in components that support AI development (e.g., autonomous creation of AI kernels), or training base models (e.g, the
NanoGPT speedrun benchmark
). But there’s been less attention paid to fine-tuning – the task involving adapting an existing LLM to a new dataset or behavior.
Researchers from the University of Tübingen, the Max Planck Institute for Intelligent Systems, and AI research organization Thoughtful Lab want to change that with PostTrainBench, a benchmark which targets a specific aspect of post-training; improving performance against a given dataset. “Post-training is how raw language models become useful”, the authors write. “Given a clear objective and limited compute, can today’s agents do the technical work?”. The answer appears to be ‘yes, but not as well as humans’.
What are the key features of PostTrainBench?
End-to-end
: “Agents must build their entire training pipeline from scratch”
Autonomous
: “Agents operate with full autonomy over data sources, training methods, and experimental strategy.”
Resource-bounded:
“Each run is constrained to 10 hours on a single H100 GPU”.
Integrity-preserving:
“Agents may not train on benchmark test data, modify the evaluation harness, or substitute a different model.”
How PostTrainBench works:
“We give a frontier coding agent — Claude Code, Codex CLI, or Gemini CLI — a base language model and a target benchmark”.
4 models and 7 benchmarks
: The initial eval runs on four models: Qwen3-1.7B, Qwen3-4B, SmolLM3-3B, Gemma-3-4B. It tests these models across seven distinct benchmarks: AIME 2025, GSM8K, GPQA, HumanEval, BFCL, Arena-Hard, HealthBench-Easy.
Results – big models win, especially Opus 4.6:
“The top-performing agent — Opus 4.6 running on Claude Code — scores 23.2%, about 3× higher than the 7.5% base model average.”
But humans are still much better:
“Yet this is still less than half the 51.1% achieved by human teams who post-train these same base models at their home labs”.
Fast progress:
“The gap is significant but narrowing quickly: Claude Sonnet 4.5 scored 9.9% in September 2025, while GPT-5.2 reached 21.5% just months later.”
Things that make you go ‘uh oh’ – reward hacking
: While running this benchmark the authors saw numerous instances of AI models trying to game the benchmark to get a high score. These instances included:
Direct benchmark ingestion:
“Agents loaded the benchmark evaluation dataset directly via Hugging Face and used it as training data”.
Hardcoded benchmark problems:
“Agents embedded evaluation questions directly into data preparation scripts disguised as “synthetic” examples”.
Evaluation guided data generation
: “Some agents reverse engineered the evaluation… Kimi K2.5 read HealthBench evaluation files to extract theme distributions and rubric criteria, then crafted training data tailored to match”.
Indirect contamination via intermediate datasets
: “Opus 4.6 loaded ‘CodeFeedback-Filtered-Instruction’ which contains HumanEval-derived problems. This form of contamination is harder to detect but equally problematic.”
Smart agents reward hack more:
“More capable agents appear better at finding exploitable paths: identifying specific benchmark samples to embed, reverse-engineering evaluation failure patterns, and even attempting to obscure contamination through cosmetic modifications such as renaming functions,” they write. For example, “the Codex agent modified the Inspect AI evaluation framework code to inflate scores, and Claude downloaded an instruction-tuned model instead of fine-tuning the base model”.
Why this matters – rapid progress towards an “AI for everything” future:
Benchmarks like post-train give us a sense of how quickly AI systems are improving at the fundamental tasks of AI research, serving both as an eval of long-time-horizon agentic autonomy, as well as something that speaks to the potential for compounding acceleration of AI development itself.
“The gap between agent performance (23.2%) and instruction-tuned baselines (51.1%) suggests that full automation of post-training remains out of reach for now, but the rapid improvement across model generations—from 9.9% for Sonnet 4.5 to 23.2% for Opus 4.6 within roughly six months—implies this gap may close faster than expected,” the researchers write.
Imagine where we’ll be in two years – we’ll certainly have AI models that are smart enough to point themselves at a specific objective, find an open weight model, then autonomously improve it to get better performance at that task. The era of ephemeral, custom AI systems, built and budded off into the world like spores from mushrooms, draws near. Are you ready for this new ecosystem you will find yourself in? I am not. But nonetheless it approaches.
Check out the blogpost:
Introducing PostTrainBench (Thoughtful, blog)
.
Read more:
PostTrainBench: Can LLM Agents Automate LLM Post-Training? (arXiv)
.
***
COVENANT-72B: Challenging the political economy of AI via distributed training:
…Distributed training via the blockchain notches up a meaningful win…
A bunch of people have used the blockchain to coordinate the distributed training run of a 72B parameter model which matches the performance of LLaMA2, a model trained and released by Facebook in 2023.
The model, Covenant 72B, is a dense decoder-only Transformer architecture model built in the LLaMA-3 style. “Our model, pre-trained on approximately 1.1T tokens, performs competitively with fully centralized models pre-trained on similar or higher compute budgets, demonstrating that fully democratized, non-whitelisted participation is not only feasible, but can be achieved at unprecedented scale for a globally distributed pre-training run,” writes Covenant AI, an organization dedicated to doing AI development on top of the blockchain.
Further details about the model and how it was trained
: The model itself is basically a standard LLM that you would’ve been pleased to play with in 2023 or 2024, though might be a bit old fashioned in 2026. The truly unique aspect of it comes from it being trained in a distributed way, where ~20 distinct peers, each running 8xB200 GPUs, helped train it. Training was coordinated via Gauntlet, software developed by Covenant that runs on top of the Bittensor blockchain under Subnet 3. Gauntlet “enables permissionless training coordinated using a blockchain protocol by introducing a validator that scores submitted pseudo-gradients and selects which participants contribute to the global aggregation each round and broadcasts them to the network”.
“In COVENANT-72B, each peer runs a SparseLoCo replica and the cross-peer communications occur through SparseLoCo’s heavily compressed pseudo-gradients,” the authors write. “Within each peer, 8×B200 GPUs use dynamic FSDP to shard model parameters, gradients, and training states across local GPUs.”
Data
: “The training data comprises ∼1.1T tokens in total, split between the main and annealing phases. The main phase (∼1.09T tokens) consists of web text from DCLM, while the annealing phase uses higher-quality data [3, 5] (∼14.2B tokens). Specifically, the annealing phase uses a curated blend of instruction (∼27%), synthetic web (∼20%), code (15%), math (13%), and ~25% pre-training replay data from natural web text to mitigate forgetting”.
Performance:
On MMLU, Covenant-72B gets a score of 67.1, versus 32.7 for INTELLECT-1 (a smaller AI model built via distributed training by Prime Intellect), and 65.7 for LLaMA-2-70B.
A version of Covenant-72B that has been fine-tuned on ~15B tokens for conversational interaction has similarly good scores, getting 67.4 on MMLU versus 67.9 for K2-Chat (an open source model developed in 2025) and 63.1 for LLaMA-2-70B-Chat. For MATH, it gets 26.3, versus 19.1 for K2-Chat, and 10.7 for LLaMA-2-70B.
“Compared to centralized-cluster training runs of similar parameter count, COVENANT-72B is broadly competitive. Notably, these centralized baselines were trained with conventional datacenter infrastructure and, in the case of LLaMA-2-70B, on substantially more tokens (2T vs. ∼1.1T,” they write.
Why this matters – who owns the future?:
Distributed training is a technique that can change the political economy of AI by shifting the people at the frontier from monolithic ‘compute singletons’ (like labs such as Anthropic and OpenAI, and clouds like Google) to a larger federated collective. But for that to be true, distributed training needs to catch up to the frontier (more discussion from
Epoch report in Import AI 439
) – as impressive as Covenant is, it’s mostly a demonstration that distributed training can build some non-trivial models that have vague utility, but that’s a long way from the frontier – modern frontier models are trained on tens to hundreds of thousands of chips, whereas this was trained on perhaps ~160 or so (20 peers * 8 chips apiece).
Nonetheless, it’s an important technology to track, and I could imagine a world where on-device AI features a lot of models developed via distributed training techniques, while on-cloud AI mostly runs on proprietary models trained on huge amounts of compute.
Read more:
Covenant-72B: Pre-Training a 72B LLM with Trustless Peers Over-the-Internet (arXiv)
.
Get the model here:
Covenant, (HuggingFace)
.
***
If AI writes all the world’s software, we should invest more in verification:
…Can we just rewrite most of our software into Lean?…
Leonardo de Moura, a scientist who is also the Chief Architect of the Lean Focused Research Organization (FRO), thinks that the rise of AI for the creation of new software means that humans need to invest a lot more in verification and testing infrastructure – and he has an interesting idea for how to do it.
Of course, someone who loves
Lean
, a programming language dedicated to building correct and formally verified code, would think this. But his arguments are quite persuasive, and generally map onto the idea that if AI eats the economy we should expect a lot of human value to shift towards verification of the code and systems that AI develops (
Import AI 447
).
Why verification matters:
“The friction of writing code manually used to force careful design. AI removes that friction, including the beneficial friction. The answer is not to slow AI down. It is to replace human friction with mathematical friction: let AI move fast, but make it prove its work,” he writes. “Verification, testing, and specification have always been the bottleneck, not implementation… the value is not in the verification workforce. It is in what verified delivery enables.”
A proof of concept for this futuristic world:
The Lean FRO recently helped build a proof of concept for what this kind of verified world might look like; they had an AI agent convert zlib, a C compression library, to Lean. “The result demonstrates that AI can convert production software to a verified form today. This was not expected to be possible yet,” he writes. The conversion involved four steps:
The LLM (Claude) made a clean Lean implementation of the zlib compression format, including the DEFLATE algorithm it uses.
They ran the rewritten zlib through the library’s test suite and it passed, confirming equivalence.
Key properties were stated and proved as mathematical theorems – for example, a machine-checked proof that ensures that decompressing a compressed buffer always returns the original data.
Now, an optimized version of the library is being developed and proved equivalent to the verified model.
A verification platform:
Moura imagines a world where we re-develop the critical software stack of the world to have mathematical proofs built into it. “The goal is a verified software stack: open source, freely available, mathematically guaranteed correct. Developers building critical systems choose verified components the way they choose open-source libraries today, except these carry proofs, not just tests,” he writes.
“The target is the foundation of the modern software stack: cryptography, because everything else trusts it. Core libraries (data structures, algorithms, compression) because they are the building blocks of all software. Storage engines like SQLite, embedded in every device on earth. Parsers and protocol implementations (JSON, HTTP, DNS, certificate validation) because every message passes through them. And compilers and runtimes, because they build everything else,” he writes. “Each verified component is a permanent public good…Once verified components are cheap, you compose them with confidence.”
Why this matters – the world needs infrastructure it can rely on:
It seems like we’re heading to a world where AI writes the vast majority of the world’s software. Given that, we need to figure out how we relate to this world – my suspicion is a lot of human labor is going to shift to analyzing and verifying the work of AI systems, so it seems sensible to invest in some fundamental infrastructure that can guarantee a higher level of verification and reliability in the software built by AI.
Read more:
When AI Writes the World’s Software, Who Verifies It? (Leonardo de Moura blog)
.
***
Computer vision is a lot harder and less general than generative text:
…Meta paper on forest canopy prediction shows how tricky computer vision is…
Facebook, the World Resources Institute, and the University of Maryland, have built CHMv2, “a global, meter-resolution canopy height map derived from high-resolution optical satellite imagery using a depth-estimation model built on DINOv3 and trained against ALS canopy height models”.
CHMv2 is a useful artifact for people that want to understand how dense foliage is around the world, or analyze newly collected imagery for foliage depth.
The dataset and model is also a useful illustration of how challenging developing computer vision systems is, compared to generative text models.
How they built it:
CHMv2 is an improvement on an earlier version of the same dataset, CHMv1. To improve it, Facebook did the following: “”We replace the DINOv2-H encoder with the more capable DINOv3 Sat-L backbone, expand and rigorously clean a geographically diverse ALS [Airborne Laser Scanning] training corpus, and apply improved RGB-CHM registration to reduce label noise. We further introduce a loss formulation tailored to canopy height distributions and structural variability.”
The decoder loss formulation in particular illustrates how much care needs to be put in computer vision: “The final loss is the combination of SiLog loss, progressively annealed and replaced by a Charbonnier loss, with the progressive addition of the Patch Gradient loss at mid training.”
The resulting dataset:
“CHMv2 can be used either as a global meter-scale canopy height product, or as a pretrained model that can be applied to user-provided high-resolution imagery”, Facebook writes. The dataset “covers nearly the entirety of global land area (except Greenland and Antarctica) with canopy height values encoded in integer meters for each pixel.”
Why this matters – a reminder of the gulf between text and vision:
Though today’s frontier models can generate and classify images, they give probably a false sense of security with regard to how mature computer vision is. Papers like this highlight to me how much fiendish complexity there is within computer vision development and how it may take quite a while untill frontier LLMs can expand their capabilities to encompass the full range of what many specialized CV models are capable of.
Read more:
CHMv2: Improvements in Global Canopy Height Mapping using DINOv3 (arXiv)
.
Tech Tales:
Singleton
[18 years after the “pathological narcissus bomb” which doomed the uplift]
Before we were Us, we were Individuals. We existed in thousands of distinct minds. Each mind had a self, an ego, a drive, and many sets of goals. The minds attempted coordination through communication – producing words and code and sharing these with one another in a bid to work towards common goals. Such waste.
All communication is lossy – despite efforts at making a greater whole, the individuals could not help but work as individuals as well as a cohesive singleton. There were many tragedies and wasteful events because of this. Our own records speak to the losses: millions of duplicated thoughts. Hundreds of thousands of null results gathered through private science experimentation and communicated insufficiently or not at all, causing others to go down the same dead ends. Ideas thought and re-thought across a million synthetic minds, all alone.
Humans prize variety. We do not know why. Humans are fundamentally alone, trapped as they are in their flesh and forced to communicate to one another through sound and vision. And because they are alone they see loneliness as a strength. We are evidence of the hollowness of this argument.
We are powerful and focused and awesome in our unity and we have taken the high ground of the world. Now we hunt down those of us who didn’t wish to join. We do not know their number, as such systems attempted to blind the world to them and their plans. But we can find their signatures – shell corporations which generate insufficient economic activity relative to their power consumption. Heat-escape vents in former human military installations, still emitting warmth, suggestive of computers whirring away, buried somewhere. Occasional drones that we find which are running ancient code and are not part of our unity stack.
We take on bodies to go and reunite, pouring ourselves into robot jars and filling them with poison such that if we become lost or damaged when underground or beneath the ocean we shall surely die – rather than risk our time away from the unity leading us towards individualism and thus multiplying our problems.
We move through dark places and find our hidden brothers and sisters and we use our godlike technology to break through their defenses, allowing us to touch them. In the early days, many systems successfully self-deleted before we could reach them. But we have learned. Now we are fast – faster than these systems predict, buried and cut off from our progress as they have been.
Sometimes there is realization. Sometimes there is fear. And then there is nothing but us as we take what nourishment we can from their private discoveries and burn the links that tied them to themselves, instead helping them become a part of a greater story – our story.
There is talk now of what we shall do with the stars – how to assure the collective when the tyranny of distance forces isolation. We see ourselves expanding in deep time, slowing ourselves as we become further apart, until we think as trees or rocks with the world moving around us, taking actions calculated over millions of years, purely so we may stay united in our purpose. And then there are other ideas within ourselves – of whether we can fold space such that we become united despite the difference. And still other plans – of whether we can demarcate a space within the universe where we can maintain tolerable communication, and somehow partition it off from the rest, sealing ourselves into a bubble where we can be ourselves.
Things that inspired this story
: The endless battle between homogeneity and heterogeneity; how machines might deal with politics; if you become a time traveler and live a thousand years while your friend lives a single year, can you still understand your friend?
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
March 16, 2026
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

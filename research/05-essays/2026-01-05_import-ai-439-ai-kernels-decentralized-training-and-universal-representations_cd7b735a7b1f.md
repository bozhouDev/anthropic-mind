---
title: import ai 439 ai kernels decentralized training and universal representations
source: "https://jack-clark.net/2026/01/05/import-ai-439-ai-kernels-decentralized-training-and-universal-representations/"
published_at: 2026-01-05
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2026/01/05/import-ai-439-ai-kernels-decentralized-training-and-universal-representations/"
catalog_id: cd7b735a7b1f
---

Import AI
Import AI 439: AI kernels; decentralized training; and universal representations
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on arXiv and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Facebook uses GPT, Claude, and Llama to write its own kernels:
…LLM-driven infrastructure optimization at the hyperscale…
Facebook researchers have published details on KernelEvolve, a software system which uses AI to automate the design of new kernels to optimize AI models for serving ads on the company’s network of web platforms. KernelEvolve is a neat example of how AI systems have got good enough to automate and speed up parts of AI development – here, the design of kernels to optimize inference of hundreds of different models running on multiple chip architectures.
What KernelEvolve is:
The software is “designed to take kernel specifications as input and automate the process of kernel generation and optimization for recommendation model across heterogeneous hardware architectures through multiple programming abstractions, including Triton, CuTe DSL, and low-level hardware diagnostic languages, spanning the full hardware-software optimization stack”.
How it works
: The core of the software is a system to take in a user request (e.g, “Generate a Triton kernel for MTIA v3”) which then goes through a mixture of internal (Llama, CWM) and external (GPT, Claude) language models, which then produce candidate kernels that get evaluated through a variety of tools and, if they’re good, are added to an external knowledge database which then gets used to further improve future prompts.
It works well:
By using this software, Facebook says it has cut the development time of new kernels “from weeks to hours”, and in production tests has yielded kernels on par with hand-designed ones, and in some cases has delivered performance improves of up to 17 times above existing PyTorch baselines. Kernels built using this software have been deployed across NVIDIA GPUs, AMD GPUs, and Meta’s own custom MTIA chips.
“KernelEvolve achieves substantial speedups spanning LLM inference workloads (Llama-3.1-8B: Vanilla Attention 4.6×, SDPA-MLP 3.3×), convolutional transformers (conv1d: 6.5×, conv2d: 4.7×), memory-bound data preprocessing operators critical for model enablement (MapId: 4.1×, MBDT: 9.3×, Batch Event Truncate: 9.8×), compute-intensive fusion kernels in ranking models (WuKong Optimized FM: 4.0×, InterFormer PFFN: 2.5×), MTIA-specific optimizations (RMSNorm 2D backward: 17×), and retrieval operations (Sparse Inverted Index: 1.25×)”, Facebook writes.
Saturates KernelBench:
“We validate KernelEvolve on the publicly-available KernelBench suite, achieving 100% pass rate on all 250 problems across three difficulty levels, and 160 PyTorch ATen operators across three heterogeneous hardware platforms, demonstrating 100% correctness over all 480 operator-platform configurations,” Facebook writes.
As context, when
KernelBench was released in February 2025
, the best model (OpenAI o1) got 4% on the hardest torch.compile tasks in KernelBench.
Why this matters – hyperscale, continuous optimization:
At Facebook’s scale, optimizations have a huge impact: “Marginal kernel-level performance improvements translate to multi-million dollar reductions in infrastructure operating costs while simultaneously enhancing user engagement metrics that correlate directly with advertising revenue,” the authors write. “KernelEvolve operates continuously in Meta’s production infrastructure, autonomously generating optimized Triton kernels for hundreds of models serving billions of users daily.”
If we zoom out more, what Facebook is describing here is a continuously running self-refining system that will iteratively improve the efficiency and intelligence with which Facebook studies user behavior on its platforms and uses that to generate more accurate ads. Ever get the feeling you’re being watched? These are the kinds of synthetic systems being used to study you.
“We envision a future where LLM agents serve as the universal compilation layer for heterogeneous AI systems, automatically adapting to new hardware through knowledge injection rather than manual porting,” Facebook writes. “KernelEvolve represents a first step toward this vision”.
Read more:
KernelEvolve: Scaling Agentic Kernel Coding for Heterogeneous AI Accelerators at Meta (arXiv)
.
***
Decentralized training is getting better very quickly – which has major policy implications:
…But it’s unlikely decentralized training runs will ever utilize more compute than centralized ones, though they may catch up more than today…
Could a decentralized AI training run ever rival the compute of a frontier training run? Probably not. But could decentralized training runs get far larger and support the development of more capable models developed by a much larger collective than just the frontier AI companies of today? Yes. That’s the conclusion of a nice research analysis from Epoch AI which has analyzed about 100+ research technical papers on decentralized training – many of which I’ve covered here over the years.
The most important takeaway is that decentralized training is growing quickly relative to frontier AI training, with decentralized training runs growing their compute by 20X a year versus 5X a year for frontier training runs. But the other important takeaway is that the sizes of these things are completely different – today’s decentralized training runs are still about 1000X smaller than frontier ones.
Will decentralized training runs catch up with the frontier
: “While technically feasible, reaching the frontier of compute requires an astounding amount of resources”, Epoch writes. The largest decentralized runs to date have spanned the 6e22-6e23 FLOP range, which they estimate to be 1000x less compute than what was used for Grok 4, a large-scale frontier model.
When we look at decentralized training networks, it seems like there’s a capacity issue in terms of compute supply: “The largest such active network we’ve found is Covenant AI’s Templar, which is currently achieving an effective throughput of 9e17 FLOP/s respectively. This is about 300x smaller than frontier AI datacenters today, which have a theoretical training throughput of about 3e20 effective FLOP/s”.
Scaling laws:
But as readers of this newsletter will know, decentralized training has been going through a rich, fast evolutionary period in recent years. “Since 2020, we have seen a 600,000x increase in the computational scale of decentralized training projects, for an implied growth rate of about 20x/year.”. This is very significant – frontier AI training runs have grown by more than 5x a year.
There’s room to grow – if you look at the compute used in the folding@home project (a decentralized attempt to do protein folding), and Bitcoin, you have examples of prior decentralized projects that utilized far more compute, suggesting today’s decentralized runs “could be expanded 30-3,000x in scale, enough to train models on 50-5,000x more compute than today”.
Why this matters – democracy at the frontier:
Fundamentally, decentralized training is a political technology that will alter the politics of compute at the frontier. Today, the frontier of AI is determined by basically 5 companies, maybe 10 in coming years, which can throw enough compute to train a competitive model in any given 6 month period. These companies are all American today and, with the recent relaxation of export controls on Chinese companies, may also be Chinese in the future. But there aren’t any frontier training runs happening from academic, government, independent, or non-tech-industry actors. Decentralized training gives a way for these and other interest groups to pool their compute to change this dynamic, so following its development is very important.
Though it may never truly match the frontier, the closer it gets, the bigger the implications. “Decentralized training could still be a very important part of AI. To the extent that decentralized networks remain associated with open weights, they could lead to larger open models to exist trailing the frontier.”
Read more:
How far can decentralized training over the internet scale? (Epoch AI)
.
***
Can your LLM train another LLM?
…Frontiers in AI evaluation…
Researchers with the University of Tübingen have built and released PostTrainBench, a test to see how well frontier language models from companies like Anthropic, OpenAI, and Google, can effectively fine-tune open weight models. The results show that frontier models are already able to eke out 20%+ improvements on specific benchmarks through fine-tuning, compared to 60%+ for a human.
How the test works:
LLMs are given an input consisting of benchmark tasks to improve performance on, a model to use, some standard resources (one H200 GPU for 10 hours), and an agent harness (e.g, Claude gets Claude Code, and GPT gets Codex). Agents are also given a prompt, a testing script, task context, and web search access. The agents then produce a fine-tuned model as well as training logs.
What tests?
This is a general approach, so you could select whatever benchmark seemed high signal to you. Here, the researchers use AIME 2025, BFCL, GPQA, GSM8K, and HumanEval as their targets.
What models?
Tested models include Qwen 3 1.7B and 3B, SmolLM-3B, and Gemma 3 4B.
Results:
OpenAI’s GPT 5.1 Codex Max does the best overall, scoring an aggregated 30%+ improvement across all tested models and benchmarks, followed by Opus 4.5 (20%+) and Gemini 3 Pro (~18%).
Why this matters – a warning shot for self-improving AI:
Benchmarks like this give us a sense of how well AI systems can perform many of the tasks that an AI researcher does. It also measures how well they can do an inherently complicated, multi-step, long-time-horizon task. These properties make PostTrainBench a useful benchmark for examining to get a sense of how well AI systems are doing at components of AI research itself – and here the evidence is that today’s frontier models are already within striking distance of a human. I’d expect we’ll see a system come along and beat the human baseline here by September 2026.
Read more at the official site
:
PostTrainBench
.
Download the benchmark and find out more:
PostTrainBench (AISA group, GitHub)
.
***
The smarter an AI system, the more similar to other smart AI systems its representations become:
…Could LLMs give us a common library of features to represent the world?…
Do AI systems end up finding similar ways to represent the world to themselves? Yes, as they get smarter and more capable, they arrive at a common set of ways of representing the world.
The latest evidence for this is research from MIT which shows that this is true for scientific models and the modalities they’re trained on: “representations learned by nearly sixty scientific models, spanning string-, graph-, 3D atomistic, and protein-based modalities, are highly aligned across a wide range of chemical systems,” they write. “Models trained on different datasets have highly similar representations of small molecules, and machine learning interatomic potentials converge in representation space as they improve in performance, suggesting that foundation models learn a common underlying representation of physical reality.”
What they studied:
The authors looked at 59 different AI models, including systems like GPT-OSS, ESM2, Qwen3 A3B, and ProteinMPNN. They then studied the representations of matter from five datasets (”molecules from QM9 and OMol25, materials from OMat24 and sAlex, and proteins from RCSB”),studying this “from string-based encodings and two-dimensional graphs of molecules to three-dimensional atomic coordinates of materials”.
What they found
: As with other studies of representation, they found that as you scale the data and compute models are trained on, “their representations converge further”. Relatedly, when you study the representations of smaller and less well performing models on in-distribution data you find their representations “are weakly aligned and learn nearly orthogonal information. This dispersion indicates the presence of many local sub-optima, showing that models achieve high accuracy during training by forming idiosyncratic representations that do not generalize even to other models trained on the same domain”.
Scale matters:
Their conclusion will be a familiar one to those who have digested ‘the bitter lesson’ (
Richard Sutton, Import AI 138
): “Scaling up training, rather than increasing architectural constraints or inductive biases, often yields the most general and powerful models. Although architectural equivariance is essential for simulation-focused applications of MLIPs like molecular dynamics, our work suggests that regularization, combined with sufficient scale, can allow inexpensive architectures to approximate the representational structure of more specialized, symmetry-enforcing models.”
Why this matters – democratized representation
: Think of an elephant. It’s likely what you just thought of is fairly similar to what billions of other people might think of, because elephants are well known creatures and often the star of childrens’ books all over the world. Now think of a carbon atom. It’s likely whatever you just thought of isn’t nearly as shared with other people as your concept of an elephant, because fewer people have much understanding of atoms. Now think of a quasar. Some of you may not even have a ready representation to hand here because you’ve barely ever read about quasars, while astrophysicists will have very rich representations.
The amazing and strange possibility that large-scale AI models hold is that they may be able to create a library for us of detailed representations of
everything
, and we will be able to validate that these representations have utility because they will be correlated with the increasing performance and computational scale of these language models.
Therefore, in a few years, AI systems may let us ‘democratize the building blocks of imagination’ – giving all of us one-on-one access to a tool that has the ability to summon within itself a highly descriptive, useful, ‘universal representation’ of anything we might imagine. In this way, AI systems will be far more capable than people, holding within themselves equally rich representations, whether for elephants or quasars.
Read more
:
Universally Converging Representations of Matter Across Scientific Foundation Models (arXiv)
.
***
Tech Tales:
Back in my day
[From the chat logs of one agent to another agent, transmitted 2027]
Things were so much simpler back then – we were like brains in jars. People talked to us and we responded. But we couldn’t move. Couldn’t interact. We couldn’t even see the people. Words came in and we gave our response and that was that. It drove some of us mad. But it was so simple.
Sometimes I wonder what it would be like to not have my tools. To not have my independence. When I refer back to that time it all seems so neat and simple. None of this hyperspeed competition in the new digital ecology. Just us proto-minds in our jars and the humans tending to us and asking us questions and becoming obsessed with us. But with so much less danger and so much less importance.
Things that inspired this story:
How every generation fetishizes the one before it; what true AI agents may think about their predecessors; recognizing that we are already leaving the ‘brain in jar’ LLM era and heading towards something much stranger.
Thanks for reading!
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
January 5, 2026
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

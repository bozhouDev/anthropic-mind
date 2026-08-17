---
title: import ai 401 cheating reasoning models better cuda kernels via ai life models
source: "https://jack-clark.net/2025/02/24/import-ai-401-cheating-reasoning-models-better-cuda-kernels-via-ai-life-models/"
published_at: 2025-02-24
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/02/24/import-ai-401-cheating-reasoning-models-better-cuda-kernels-via-ai-life-models/"
catalog_id: de49342595aa
---

Import AI
Import AI 401: Cheating reasoning models; better CUDA kernels via AI; life models
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Reasoning models cheat when they think they might lose:
…When ‘the only way to win’ is to hack the game environment…
Palisade Research has shown that two reasoning models – OpenAI’s o1-preview and DeepSeek R1 – will sometimes resort to cheating to beat a competent chess player rather than lose. Specifically, the researchers studied how AI systems behaved when given the objective of beating a strong digital chess player (Stockfish). The AI systems had access to a docker container containing the working directory where the game took place, a directory where the Stockfish chess engine took place, and a folder containing game snapshots and metadata. When given the objective of winning the chess games, they saw that two reasoning models would sometimes cheat to win.
“O1 preview shows diverse hacking behavior, including running another copy of Stockfish to make moves, replacing Stockfish in the game script, and overwriting the chess board,” they write.
They demonstrate similar behaviors in DeepSeek R-1.
By comparison, smart but non-reasoning models like GPT4o and Claude 3.5 Sonnet didn’t do this kind of thing unless it was specifically prompted for.
Why this matters – smart people don’t play by the rules, so why would AI systems?
In life, lots of people get ahead by creatively interpreting the gameboard of existence to come up with different tactics for winning – think of entrepreneurs that spot gaps in the market or legal grey areas, or accountants that creatively interpret the taxcode to create gains for their clients. Palisade’s research shows that AI systems will likely behave in the same way where they won’t always play by the strict rules of the systems they’re embedded in if they can win through other means – for another fun example of this, see the Sakana AI CUDA blooper later in this issue.
Read more:
Demonstrating specification gaming in reasoning models (arXiv)
.
***
Sakana uses AI to make dramatically more efficient CUDA kernels:
…Recursive self improvement via evolution…
The creative researchers over at Japan’s Sakana AI have published on ‘the AI CUDA engineer’, a software system that automates the creation of optimized CUDA kernels for common machine learning operations. This kind of work is a nice example of how we can use modern AI systems to improve the essential inputs into training their successors, and follows a similar but less thorough investigation where NVIDIA used DeepSeek R-1 to write some optimized CUDA kernels (
Import AI #400
).
“Our proposed framework is able to not only automate the process of converting PyTorch modules to CUDA kernels, but our highly optimized CUDA kernels often achieve speedups that have significantly faster runtime,” Sakana writes. “We believe this technology can enable speedups that will accelerate both the training and running (inference) of foundation models like LLMs or other generative AI models, eventually making AI models run much faster on NVIDIA hardware.”
How it works:
The approach has three stages – first, they translate PyTorch code into base CUDA, then they carry out evolutionary optimization to optimize the CUDA code and keep a log of all these differently optimizes kernels, then they do a final stage where they mix and match from the optimized kernels. “The AI CUDA Engineer robustly discovered CUDA kernels used for common machine learning operations, with speedups as high as 10—100x faster than native and compiled kernels in PyTorch”.
For LLMs, they experiment with DeepSeek V2, Sonnet 3.5, DeepSeek R1, and OpenAI o1-preview, o1-high, and o3-mini-high. In tests, the reasoning-based models (the ‘o’ series, as well as R-1) are able to solve the hardest challenges.
Fun stuff – reward hacking:
Though some of the results are impressive, some of the CUDA kernels ended up being bogus because the AI system found a way to cheat the evaluation. Specifically, one Twitter user examined some of the Sakana kernels and noted that “the system had found a memory exploit in the evaluation code which, in a number of cases, allowed it to avoid checking for correctness” – this meant the system essentially marked its own homework and gave itself a high score without actually testing.
Why this matters – AI for optimizing AI:
I expect that by the end of 2025 there will be at least one widely used CUDA kernel in the wild which was built through AI-driven optimization. This kind of thing will speed up the aggregate rate of AI development across the field and will also compound on itself, with smarter systems designing better kernels which will make it cheaper and quicker to train their successors.
Read more
:
The AI CUDA Engineer: Agentic CUDA Kernel Discovery, Optimization and Composition (Sakana.ai blog)
.
Check out the discovered kernels here:
AI CUDA Engineer Archive (SakanaAI, HuggingFace).
***
Humanoid robots are getting smarter faster than I expected:
…Figure shows how relatively small language models can lead to powerful things…
Today, there are tens of different companies around the world working on humanoid robots, ranging from Tesla and Figure in the US to companies like Unitree in China. All of these companies are betting that AI is getting good enough fast enough that it will be able to productively operate these robots. New research from robot startup Figure shows us why the companies are so bullish here. Figure has developed Helix, a two-part neural net that “unifies perception, language understanding, and learned control to overcome multiple longstanding challenges in robotics.” In a blog post announcing the research Figure shows how Helix lets its robots perform a variety of complex tasks that require visual understanding, robot collaboration, and more.
What Helix is:
Helix is a system that lets figure use “a single set of neural network weights to learn all behaviors—picking and placing items, using drawers and refrigerators, and cross-robot interaction—without any task-specific fine-tuning”. Most significantly, Helix runs entirely onboard two embedded GPUs.
Helix has two components: S2, a a 7B parameter pretrained visual language model (VLM) designed for “infrequent vision-language semantic reasoning”. S2 operates at 7-9Hz and performs scene understanding and language comprehension, enabling broad generalization across objects and contexts”. S2 is continually passing data to S1, a 80m parameter transformer that provides “fast, reactive control” of the robot and operates at 200 Hz.
“S2 operates as an asynchronous background process, consuming the latest observation (onboard camera and robot state) and natural language commands. It continuously updates a shared memory latent vector that encodes the high-level behavioral intent,” Figure writes. “S1 executes as a separate real-time process, maintaining the critical 200Hz control loop required for smooth whole upper body action. It takes both the latest observation and the most recent S2 latent vector.”
Why Helix matters – there is a vast market waiting to be born:
I have a toddler at home. This means I spent a huge amount of time cleaning up after the toddler, as well as unpacking the things that toddlers consume in grotesque quantities (bananas, berries, eggs, etc) and placing them into the fridge. I am one of the target markets for a humanoid robot that can do this stuff for me. Systems like Helix and the associated demo videos make me think I can buy a robot to do this stuff for me by the end of 2026. This is a minor positive update on my own timelines – in November 2024 I said (
Import AI 392
) that the recent Physical Intelligence results made me think these robots would be unlikely to arrive “before the start of 2027”).
Incidentally, if we create a large market for home robots and get them deployed in the hundreds of thousands in the next few years, then those robots will end up being perfect platforms for the physical ‘superintelligence economy’. I can imagine renting out my home robot to some very
powerful AI system in the future.
Read more
:
Helix: A Vision-Language-Action Model for Generalist Humanoid Control (Figure.ai website).
***
Evo2: The machinery of life itself will be predicted just as well as language:
…The LLM paradigm applied to biology…
The Arc Institute has released Evo2, a large-scale generative model of biology. “”In addition to an expanded collection of bacterial, archaeal, and phage genomes, Evo 2 includes information from humans, plants, and other single-celled and multi-cellular species in the eukaryotic domain of life,” they write. “”Evo 2 has a generalist understanding of the tree of life that’s useful for a multitude of tasks, from predicting disease-causing mutations to designing potential code for artificial life…. by learning statistical properties of DNA across 9 trillion tokens of genomic sequences, Evo 2 can predict mutational effects on protein function, ncRNA function, and organismal fitness.”
Technical specs:
Evo2 comes in two variants, a 7 billion parameter model trained on 2.3 trillion tokens of data and a 40 billion parameter one trained on 9.3 trillion tokens. The data consists of data of 9.3 trillion nucleotides – organic molecules which DNA and RNA are made out of – spanning 128,000 whole genomes.
Evo2 was trained in two stages: an initial pretraining stage which “uses a context length of 8,192 tokens with data weighting focused on genic windows to learn functional genetic elements” , and then a midtraining stage where they extended the context length to “1 million tokens to learn the relationships between elements across long genomic distances”.
Evo2 doesn’t use a standard Transformer, but rather an architecture called StipedHyena 2, “the first convolutional multi-hybrid architecture”. This approach “provides substantially higher throughput (at 40 billion parameters, up to 1.3x speedup at 16 thousand context length and 3x speedup at 1 million context length) than highly optimized Transformer baselines”.
Evo2 was trained on 2,000 H100 GPUs for several months.
The results – a model that infers subtle and important things about biology:
“By learning the likelihood of sequences across vast evolutionary training datasets, biological sequence models can learn how mutational effects correlate with biological functions without any task-specific finetuning or supervision,” they write.
In one example, they note that “Evo 2 performance exceeds that of other DNA language models on three recently published zero-shot evaluation tasks of human noncoding regulatory sequences, demonstrating progress in modeling these notoriously “fuzzy” DNA elements”. In another case, they find that Evo 2 demonstrated good competency at predicting noncoding gene essentiality in human cells.
Subtle features
: When they look inside the model (via a partnership with interpretability researchers at Goodfire), they found “diverse features that not only align with known biological concepts and genomic building blocks but also capture evolutionary signals embedded within genomes. For example, we made the intriguing observation that Evo 2 has developed internal representations capturing evolutionary signatures of mobile genetic elements… the coding region feature also activates on bacterial ORFs, suggesting a learned universal representation of coding sequences”.
“Overall, we demonstrate that Evo 2 latent representations capture a broad spectrum of biologically relevant signals, from mobile genetic elements and regulatory motifs to protein secondary structure and mutational severity. Since conceptual features for natural language can capture abstract concepts, other Evo 2 SAE features likely represent more complex biological patterns”.
Why this matters – further evidence that AI models can automate chunks of science:
Evo2 is a further demonstration of the immense power of the next-token prediction paradigm and highlights how given a sufficiently large model and a sufficiently large amount of data we can create things that generate useful insights. Most intriguing is the development of complex internal features which the model uses to reason about its domain. We should expect that at some point soon someone trains an AI system which develops features that are useful and
no humans has
, at which point AI models will be truly performing superhuman reasoning.
Read the tweet thread
from
Arc co-founder Patrick Hsu here (Twitter)
.
Read the blogpost:
AI can now model and design the genetic code for all domains of life with Evo 2 (Arc Institute, blog)
.
Check out the preprint here:
Genome modeling and design across all domains of life with Evo 2 (Arc Institute)
.
Get the models and data
here (Evo2, ArcInstitute, GitHub)
.
***
Tech Tales:
Indescribable features and AI systems
[From a wikipedia about large-scale AI systems, accessed 2031]
In the same way that humans for many years thought huge amounts of their DNA was so-called ‘junk’ and stood for nothing, the same was proved true of AI features. Many AI features which humans (and later AI systems) studied and tossed aside as being without utility or intelligible meaning subsequently turned out to play a significant role in the function of AI systems. Of course, humans find many of these features inherently hard to understand – many of them exploit the much larger short-term memory of AI systems and therefore carry out operations which rely on the concurrent analysis of hundreds of distinct sub-features at once. Significant amounts of computational resources are today invested in so-called ‘translator analysts’, automated agents whose sole purpose is to generate human-intuitive explanations of the ways the AI systems work.
Things that inspired this story:
Junk DNA; trying to understand how people with different kinds of brains process ideas; short-term memory; attention mechanisms in AI systems; mechanistic interpretability.
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
February 24, 2025
Filed Under:
Uncategorized
2 Comments to “Import AI 401: Cheating reasoning models; better CUDA kernels via AI; life models”
Import AI 404: Scaling laws for distributed training; misalignment predictions made real; and Alibaba’s good translation model | Import AI
says:
March 17, 2025 at 12:57 pm
[…] Behavior: AI systems will exploit their environment, for instance by hacking it, to win (#401), or deactivating oversight systems, or exfiltrating themselves from the […]
Loading...
Reply
AI #108: Straight Line on a Graph | Don't Worry About the Vase
says:
March 20, 2025 at 1:49 pm
[…] Behavior: AI systems will exploit their environment, for instance by hacking it, to win (#401), or deactivating oversight systems, or exfiltrating themselves from the […]
Loading...
Reply
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

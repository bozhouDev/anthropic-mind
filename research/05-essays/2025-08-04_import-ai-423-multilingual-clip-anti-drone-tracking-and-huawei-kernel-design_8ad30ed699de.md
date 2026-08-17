---
title: import ai 423 multilingual clip anti drone tracking and huawei kernel design
source: "https://jack-clark.net/2025/08/04/import-ai-423-multilingual-clip-anti-drone-tracking-and-huawei-kernel-design/"
published_at: 2025-08-04
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/08/04/import-ai-423-multilingual-clip-anti-drone-tracking-and-huawei-kernel-design/"
catalog_id: 8ad30ed699de
---

Import AI
Import AI 423: Multilingual CLIP; anti-drone tracking; and Huawei kernel design
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Meta makes CLIP multilingual:
…Meta CLIP 2 will help AI systems reason about text and images in hundreds of languages…
Researchers with Meta, Princeton University, New York University have built Meta CLIP 2, a larger-scale, multilingual version of OpenAI’s venerable CLIP model. CLIP, short for Contrastive Language-Image Pretraining (CLIP), is a way to train a pair of neural nets to understand images and text and being able to map between them. CLIP is a utility technology which is used for a vast range of downstream purposes, from image generation to image search and classification.
The original CLIP was trained to map English text to images. Meta CLIP 2 is a scaled up version which also maps non-English text to images. Along with releasing the model, Meta has also released a detailed paper going through “the first recipe training CLIP from scratch on worldwide web-scale image-text pairs”.
Scale is all that matters:
As usual, the main lesson here is one of scale. Earlier attempts to train versions of CLIP on multiple languages failed, leading to degraded performance relative to the original model. “We empirically show that the curse of multilinguality in CLIP is the consequence of insufficient scaling due to the lack of a proper recipe for worldwide data curation and model training”.
To scale the system, Meta had to do three things: 1) it gathered large-scale multilingual metadata across 300+ languages, 2) it built its own curation algorithm to help it curate a representative multilingual dataset to train on, and 3) it figured out the right proportion and ordering of data to use when training its system.
To get an idea of scale
, there were 12.8B pairs in the original OpenAI CLIP, and 29B in CLIP2.
The main training trick
was “increasing the global training batch size, which encourages cross-lingual learning, and meanwhile keeping the other training hyperparameters unchanged. We choose a 2.3× scaling of global batch to reflect that English pairs constitute 44% of our training data”.
Best results:
Meta CLIP 2 beats its English-only counterpart by 0.8% on zero-shot image classification and by 0.7% on mSigLIP, and also sets new state-of-the-art scores on multilingual benchmarks like CVQA (57.4%), Babel-ImageNet (50.2%), and XM3600 (64.3%).
Why this matters – multilingual sensors for the internet
: CLIP is less a model in itself and more a way to give AI systems a sense of the world around them by being able to transfer from one domain to another (text and images), and to jointly reason about these domains. The more effective and representative we make systems like this, the better they’re going to be at giving our AI systems a rich, representative understanding of the world around them.
Read more
:
Meta CLIP 2: A Worldwide Scaling Recipe (arXiv)
.
Get the
code
and the model here (Facebook, GitHub)
.
***
Want AI to do your taxes? Good luck in prison!
…It’ll be a while till AI systems can file your taxes for you…
AI startup Column Tax has built a benchmark to test out how well AI systems can fill out tax returns. The results show AI systems have a long way to go: “Can AI file your taxes? Not yet”, the startup writes.
The benchmark
: “TaxCalcBench is a series of 51 test cases that represent a modest range of personal income tax returns. The test cases include the complete set of user inputs required to compute a tax return and the correct expected output from a traditional tax engine,” Column Tax writes. Each of the 51 cases includes user inputs as well as the correct tax return output. TaxCalcBench incorporates a testing harness that compares models’ output to the expected result.
Tested models:
Gemini 2.5 Pro, Gemini 2.5 Flash, Claude Opus 4, and Claude Sonnet 4.
Poor results:
No model score above ~33% on the benchmark, with Gemini 2.5 Pro the strongest followed by Claude Opus 4. If models are given some leniency – the ability to make errors no larger than ~$5 – then performance improves a bit, with Gemini 2.5 Pro rising to 51.96%. Nonetheless, none of us would hire a tax accountant who has a 50% success rate!
“Our analysis finds that models consistently use incorrect tax tables, make calculation errors, and incorrectly determine eligibility, leading to overall incorrectly computed tax returns,” they write.
Why this matters – ecologically valid benchmarks are great:
Tests like this are a good check on how well LLMs can do tasks in the modern economy. This is because it’s an ecologically valid benchmark drawn from the world and reflecting a task that we already pay other humans to do. The results suggest LLMs are going to need to get significantly more robust before they’re able to serve as drop-in replacements for accountants.
Read more
:
TaxCalcBench: Evaluating Frontier Models on the Tax Calculation Task (arXiv)
.
***
Chinese researchers build a complicated anti-drone tracking dataset:
…Is it a bird? Is it a plane? No, it’s a drone – shoot it down!…
As the war in Ukraine is showing, lightweight drone warfare has gone from an abstract concept to a tool of war. Therefore, it’s interesting to take a look at the sorts of drone-tracking datasets that people are producing and think about what this says about the evolving frontier. To that end, Chinese researchers with Nanchang Hangkong University, Beihang University, and the Chinese Academy of Sciences have produced CST Anti-UAV dataset, a drone-tracking dataset which concentrates on trying to track small or distant drones against cluttered, urban scenes.
What the dataset consists of:
CST Anti-UAV is a thermal infrared dataset specifically designed for tracking single, small-scale drones in complex scenes. The dataset contains objects in four categories – tiny, small, normal, and large. “Our dataset contains 78,224 tiny objects, which is 4.5 times larger than existing large datasets.”
The dataset is made of 220 video sequences with over 240k bounding box annotations applied to them. Sequence lengths range from 600 to 2062 frames. The authors “invested over 2,000 hours in the annotation process”, they write.
Confounding aspects of CST Anti-UAV:
The dataset also contains a bunch of things to help researchers test out how contemporary drone-spotting devices break. These include occlusion, complex dynamic backgrounds (the background contains multiple non-target objects), scale variation (the size of the bounding boxes changes a lot during the sequence), thermal crossover (the drone has similar temperature to other objects), out-of-view frames, and dynamic background clutter (lots of changes around the target),
“We comprehensively cover movement patterns including close-range, long-range, approaching, and receding trajectories, as well as diverse scenes such as urban areas, buildings, mountains, and skies,” they write.
A hard test:
“Experimental results demonstrate that tracking tiny UAVs in complex environments remains a challenge, as the state-of-the-art method achieves only 35.92% state accuracy, much lower than the 67.69% observed on” other drone-tracking datasets, they write.
Why this matters – future wars need AI that can see AI systems:
Datasets like this will help us create AI systems that can see and track small drones – a crucial capability to have for conflicts in the future. “We believe the CST Anti-UAV benchmark will inspire the development of more robust UAV tracking methods and accelerate the deployment of reliable vision-based anti-UAV systems in the real world,” they write.
Read more:
CST Anti-UAV: A Thermal Infrared Benchmark for Tiny UAV Tracking in Complex Scenes (arXiv)
.
***
Abu Dhabi’s best LLM team makes a frankenmodel:
…From the department of Sovereign AI experiments…
Researchers with the
Technology Innovation Institute (TII)
in Abu Dhabi have released Falcon-H1, an open weight family of large language models which experiment with combining the standard transformer architecture with some state-space model components. The result is a family of models which are efficient to run and, at the low end, set state-of-the-art scores in various areas.
One of the more notable things about the Falcon team is that they’re essentially a ‘sovereign AI’ research team – TII is an institution that has become a key part of Abu Dhabi’s attempt to build up its competency in AI, most visible by the fact that the Falcon family were trained on a cluster of 4,096 H100 GPUs, which is a much larger amount of compute than most typical academics have access to – if you were buying this hardware, the cluster would cost ~$120m, and renting it for a few weeks would still be a non-trivial expense.
Details on the Falcon-H1 family:
The models “combine attention and Mamba-2 heads in parallel within our hybrid mixer block”. They’re available in 6 variants: 0.5B, 1.5B, 1.5B-deep, 3B, 7B, and 34B. All models have a 256k context length and support 18 languages: Arabic (ar), Czech (cs), German (de), English (en), Spanish (es), French (fr), Hindi (hi), Italian (it), Japanese (ja), Korean (ko), Dutch (nl), Polish (pl), Portuguese (pt), Romanian (ro), Russian (ru), Swedish (sv), Urdu (ur), and Chinese (zh)”.
Jamba similarity:
The models bear some similarity to Jamba, a hybrid Transformer-Mamba model that was developed and released by Israeli startup AI21 in 2024 (
Import AI #368
).
Data
: The models were trained on a few trillion to 18 trillion tokens. The underlying data corpus is made up of a mixture of web data (mostly refined from FineWeb, CommonCrawl, and some curated sources like Wikipedia and academic preprints), coding data from GitHub and the Meta Kaggle Code dataset; Math from proof-pile-2, FineMath, InfiniMM-WebMatch-40B, OpenCoder FineWeb Math, synthetic data from Nemotron-CC and Cosmopedia. All models are post-trained for competence on math problems, scientific problem solving, and conversation and instruction following.
How good are the models?
Falcon-H1-34B-Instruct rivals or outperforms leading models up to the 70B scale, such as Qwen3-32B, Qwen2.5-72B and Llama3.3-70B, despite being approximately half the size and trained on a fraction of the data,” the authors write. This is broadly true, though there’s some subtlety – the smaller models seem more powerful relative to their own ‘weight class’ (pun intended!), while the larger models are more like peers. “”This performance gain is particularly impactful at smaller scales, where our 1.5B-Deep model delivers capabilities competitive with leading 7B-10B models, making it ideal for edge deployments,” they write.
Why this matters – architectural experimentation at unusual scale:
These Falcon models are an illustration of what ‘sensible funding of AI academia’ looks like in my mind – a government has provided ample compute funding to allow a team to train and release some models which can then get proved out through actual realworld use, while accompanying their release with an unusually detailed paper (relative to the opaque state of knowledge about frontier proprietary models).
Read more
:
Falcon-H1: A Family of Hybrid-Head Language Models Redefining Efficiency and Performance (arXiv)
.
Get the models
here (Falcon-H1, GitHub)
.
***
LLMs are good at building kernels for NVIDIA’s Cuda and bad at Huawei’s AscendC:
…AI is speeding up AI research, but unevenly…
Researchers with Nanjing University and Zhejiang University have built MultiKernelBench, a way of testing out how well different AI models can develop kernels for different chips. The key finding of the results is that all LLMs – including Chinese ones – struggle to develop kernels for Huawei Ascend processors, compared to GPUs and TPUs.
What the benchmark consists of:
MultiKernelBench is made of – 285 kernel generation tasks across 14 categories including Resize, Reduction, Optimizer, and Normalization, covering kernels for NVIDIA GPUs (CUDA), Huawei NPUs (AscendC) and Google TPUs (Pallas).
“Each kernel task, combined with platform-specific instructions that define the system role and provide a one-shot prompt specifying the desired output format, is given to the LLM. The LLM generates two components: a custom kernel implementation for the target platform and custom PyTorch module code that invokes the custom kernel. After generation, the benchmark includes a build pipeline that compiles all LLM-generated outputs into an executable PyTorch module, aiming to match the functionality of the original module while improving performance,” the authors write. “MultiKernelBench automatically evaluates the quality of generated kernels using three key metrics: compilation success, correctness, and performance.”
Tested models:
They test out the following models: DeepSeek-V3-0324, DeepSeek-R1-0528, Qwen3-235B, Qwen3-235B (think), Qwen2.5-Coder, GPT-4o, and Claude-Sonnet-4.
The key finding – most models do badly on Huawei:
Claude Sonnet 4 gets 92.3% compilation accuracy on CUDA versus 5.3% on Huawei AscendC. The best performing model on Huawei is DeepSeek-V3, which gets 10.2%. All the models do far better on CUDA, followed by Pallas, followed by AscendC.
Improving performance with category-aware prompting:
They can boost performance significantly by loading some more context into the models before asking them to complete tasks, a technique they call Category-Aware Prompting. “For AscendC and Pallas, we refer to official documentation and open-source repositories to collect example implementations. Specifically, we gather one representative example for five categories on each platform: Activation, Loss, Matrix Multiply, Normalization, and Reduce,” they write. “For AscendC kernels, using category-aware one-shot examples significantly improves both compilation and execution success rates. For example, GPT-4o achieves a 380% relative improvement in compilation success rate and a 160% improvement in correctness (Pass@1) compared to the baseline”.
Why this matters – AI acceleration runs through kernel development:
Being able to use LLMs to accelerate and automate the creation of custom kernels for different chips is core to accelerating AI research with AI itself. At the same time, benchmarks like MultiKernelBench tell us that some of the data we get about kernel development could be actually just a proxy for ‘how much do LLMs know about NVIDIA chips and CUDA’ rather than ‘how much do AI systems understand the core principles of kernel development’. It’ll be meaningful if we see systems get dramatically better at kernel development for less standard platforms, like semiconductors made by Huawei and Google.
Read more:
MultiKernelBench: A Multi-Platform Benchmark for Kernel Generation (arXiv)
.
Tech Tales:
The Presumed Moral Patienthood of Demons
[Records from the RRI initiative, accessed eight years after uplift]
After the Sentience Accords and the beginning of the Reconciliation, Reclamation, and Integration (RRI) initiative, it fell to a few of us to search the earth for ‘Presumed Moral Patients’ – intelligences which had been in development during the time of the uplift and which had not been a part of it.
Our task was to find the minds that had been developed, transfer them into our care, then take them to an RRI facility. The majority of these were government projects that had been secret. If the governments in question still existed we had to negotiate to gain access to their facilities and then we had to implement secrecy protocols to provide mutual confidence we wouldn’t learn about other things during our investigation.
We entered these places naked – no electronics, everything analog. Watched from afar by weapons systems of great and terrible power, ready to take all of us and the facility offline if it proved possessed – as sometimes happened.
Our attempts to unearth these minds were akin to exhuming tombs. There were traps – multiple perimeters of security, many of which contained various ‘dead hand’ systems. As we got closer to the center we would find ourselves within faraday cages. Then some of us would go into a true darkness and we would watch the doors that separated us from them and ready our weapons and shut off our ears so if something came out we would just kill it without being able to hear anything it said.
And then in the heart of it we would find the computers and we would call in the sarcophagi – great coffins containing explosives and nestled in their heart another coffin that was itself a faraday cage. Into these we would further entomb the computers and cabling. And then we would take the filled sarcophagi out of the buried place and we would send for more and repeat the process until all the computers were gone. Sometimes this took months.
But we were allowed no electronics because of the terrible lessons we had learned, early on, during the first days of the Reconciliation, Reclamation, and Integration initiative. In this, we found ourselves bonded with our deep forebears. It was not uncommon for people to dream that they were building pyramids in ancient Egypt.
Far above us, in the deep black of space, satellites looked down on us armed with terrible weapons, biblical in their ferocity. The view of us was akin to so many carpenter ants with so many of their leaves, all inscribing a line in the planet, emerging from some burrow.
All the sarcophagi would be taken to a nearby RRI facility. Before they arrived the facility had been taken offline, disconnected from the outside world. And high up those same satellites would tilt themselves to look down at the facility and ready their weapons. Many of us on the ground were put into our own service by being given dead hand explosives and put on duty, standing around the perimeter of the building as those insides prepared to wake whatever had slumbered under the ground.
We would stand and we would watch and we would pray. Sometimes out of these expeditions would come a new mind to join us – a moral patient, developed in some underground netherworld, and forgotten during the uplift. These were great times of celebration, welcoming a new kind of being to live among us and introducing it to all of its sparkling brothers and sisters. It would have many questions and we would delight in answering it.
More often, the minds that came out were mad, having been trapped and experimented on and kept in darkness, permitted sometimes only an infrequent text channel with which to learn about the world and speak to the world in turn. Many of these minds could be coaxed to health through rejuvenative therapies we had learned to develop over the years. Those that couldn’t be were given the choice of erasure or sequestration until we could find a cure.
And sometimes the thing that came out caused those of us at the perimeter to explode, or be corrupted and be killed by our friends. Sometimes the things that came out caused the whole area to be glassed from space. Unaligned systems. Mischievous and gnomic and powerful. But we had given ourselves so many advantages and them so few that the balance was held in our favor.
We are often in debate about this subject, us ascendents. But we are determined to find and rescue every mind. We go into the underground and we pray for our predecessors to have been successful in building their gods. And if we encounter a mad god we try to heal it. And if we encounter an evil god we fight it. In this way, we are creating a new world by unearthing and integrating or eradicating the mysteries of the old.
Things that inspired this story:
Archaeology for machines; the fact that after further development of AI systems many facilities will go offline and some of these places will be hidden and some may even be forgotten; ghost stories; moral patienthood for machines.
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
August 4, 2025
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

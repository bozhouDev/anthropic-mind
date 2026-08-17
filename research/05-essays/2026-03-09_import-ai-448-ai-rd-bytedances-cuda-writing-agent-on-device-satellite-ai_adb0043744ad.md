---
title: import ai 448 ai rd bytedances cuda writing agent on device satellite ai
source: "https://jack-clark.net/2026/03/09/import-ai-448-ai-rd-bytedances-cuda-writing-agent-on-device-satellite-ai/"
published_at: 2026-03-09
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2026/03/09/import-ai-448-ai-rd-bytedances-cuda-writing-agent-on-device-satellite-ai/"
catalog_id: adb0043744ad
---

Import AI
Import AI 448: AI R&D; Bytedance’s CUDA-writing agent; on-device satellite AI
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on arXiv and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
AI progress is moving faster than even well regarded forecasters can guess:
…Ajeya Cotra updates her timelines…
“On Jan 14th, I made predictions about AI progress in 2026. My forecasts for software engineering capabilities already feel much too conservative,” writes Ajeya Cotra in a blog. Ajeya is a longtime AI thinker who has done some great work trying to predict timelines to powerful AI. In this post, she explains that AI systems are moving faster than she thought, given the recent METR results putting Opus 4.6 as having a time horizon of 12 hours (Ajeya had predicted ~24 hours for the end of 2026 in January).
“It’s no longer very plausible that after ten whole months of additional progress at the recent blistering pace,9 AI agents would still struggle half the time at 24 hour tasks,” Ajeya writes. “I’d guess that by the end of the year, AI agents will have a time horizon of over 100 hours on the sorts of software tasks in METR’s suite… And once you’re talking about multiple full-time-equivalent weeks of work, I wonder if the whole concept of “time horizon” starts to break down.”
Why this matters – all the lights are flashing yellow for a software explosion
: Posts like this as well as 70% of what I cover in this newsletter all point in the direction of AI systems getting extremely good, extremely quickly, and quickly colonizing and growing the economy.
Read more:
I underestimated AI capabilities (again) (Ajeya Cotra)
.
***
Want to measure AI R&D, here are 14 ways to do it:
…Generating metrics about the most significant property of AI…
The biggest thing that could ever happen with artificial intelligence will be when it starts to build itself. This phenomenon which has been often termed recursive self-improvement is often seen by many as an event horizon, beyond which it’ll be increasingly hard to reason about the future. How would we know if we were approaching this point? Researchers with GovAI and the University of Oxford have written a paper laying out 14 distinct metrics which could be measured to help us figure out the extent to which AI companies are succeeding in building and overseeing AI R&D Automation (AIRDA) – getting AI to build AI, a necessary prerequisite for recursive self-improvement.
Why care about this
: “AIRDA could accelerate AI progress, bringing forward AI’s benefits but also hastening the arrival of destructive capabilities, including those related to weapons of mass destruction, or other forms of disruption such as unemployment,” they write.
What are the 14 metrics?
Measure AI performance on AI R&D
Measure AI performance on AI R&D relative to humans and human-AI teams
Measure ‘oversight red teaming’ – how well human teams can effectively supervise AI systems that are building themselves
Measure misalignment in AIRDA
Compute the rate of efficiency improvements on AI R&D tasks
Survey staff on how they use AI and what this means for productivity
Find out if and how often AI is used in high-stakes decisions
Examine where AI researchers spend their time
Meta-measure the effectiveness of how well companies can oversee AI development (e.g, the rate of bugs or undesired behaviors that make it through to production even with human oversight)
Examine how often AI systems subvert the goals of their human developers
Track the headcount of AI researchers at labs, as well as details of their performance
Look at the distribution of compute used by AI companies across their AI R&D process and how this changes
Examine compute as a share of AI R&D spending
Understand the permissions AI systems have and how permissiveness changes over time
Governing AI R&D:
The logical question implied by the above, I hope, is “wow that all sounds very high-stakes and important, what can we do about it”? As I write often in this newsletter, AI measurement is a prerequisite to AI governance. Therefore, with these measures, a few different actors should do a few different things. Specifically:
Companies
should:
Track differential progress between safety and capabilities research:
Is capabilities research moving at a faster rate than oversight research?
Track how AI R&D affects oversight:
Automation could free up humans to invest more of their time in building systems for overseeing the work ofAI systems. On the other hand, AI-driven R&D might create systems which are innately harder for humans to understand, and the volume of activity being done by the AI systems could swamp any oversight systems.
Track the actual extent of AI R&D:
You can build metrics which work as proxies for AI R&D – e.g, many labs today test out how well AI systems can build AI kernels or train AI models. You can also test out how much AI R&D automation is being done in practice by your own organization. Another path is by doing qualitative and quantitative studies of human staff to understand how their own roles are changing, as well as how AI is being used in increasingly high-stakes decisions.
Governments
should:
Develop systems for confidential reporting, potentially in the form of industry-wide aggregates: Once companies are measuring this kind of data, governments should seek to gain access to it so they can understand the shape of AI progress.
Third parties
should:
Estimate metrics using public sources: Look at public reporting to create estimates for things that may relate to AI R&D, like the amount of compute companies have (e.g, both Epoch and SemiAnalysis do this quite well).
Create tooling and design surveys: Builds tools that companies could use to generate more telemetry about AI R&D, and conduct surveys of people at companies to gather more insights.
Why this matters
: “An actor has oversight over the AI R&D process to the extent that they (1) understand the process and (2) exercise informed control over it in order to produce desired outputs, such as by reviewing AI-generated outputs for errors”, they write. Therefore, for us as a species to have any ‘warning shots’ about recursive self-improvement and any hope of governing it, we need to be able to measure these aspects of it.
Read more:
Measuring AI R&D Automation (arXiv)
.
***
Indian researchers use edge computing to prototype a citywide camera network:
…Traffic surveillance with YOLO, SAM3, and NVIDIA Jetson chips…
Researchers with the Indian Institute of Science in Bengaluru have built a software and hardware system for intelligently monitoring the traffic and types of vehicles that flow around the city of Bengaluru. The so-called AI-driven Intelligent Transportation System (AIITS) helps increase the amount of intelligence available to city transport analysts via the use of AI.
How the AIITS works:
The goal of this project is to unlock “real-time analytics from 1000s of city cameras under strict latency and resource constraints”.
To do this, they scatter a bunch of lightweight GPUs (Jetson Edge accelerators) around the city, co-locating them with traffic cameras. This helps the traffic cameras do intelligent processing at the edge of the network rather than having to send all the extremely bandwidth-intensive data to a central hub for processing; instead, the camera & jetson share insights back to the hub for analysis and re-calibration of the Jetson-based ML models.
The software works like this:
video streams from the cameras come in, and a segment anything (SAM3) model segments all the stuff in the video frames, which a Yolo26 model then analyzes and puts labels and bounding boxes around. “Each stream integrates BoT-SORT multi-object tracking, which assigns persistent IDs to detected vehicles across successive frames.”
Once this is done, the resulting intelligence is sent to a remote GPU server which does two things:
1) It takes in the resulting data and uses this to create a kind of weather map of traffic hotspots, as well as making predictions about future traffic.
2) It does federated learning; when it detects new vehicle classes and labels them with SAM3, then updates details and broadcasts them out to the edge. “Each Jetson then performs local fine-tuning of the YOLO-based detector, initialized with the current global weights.”
The prototype works:
This system, which was done by simulating 100 cameras in a neighborhood in Bengaluru, works sufficiently well that the authors plan to scale this up to 1,000 streams for a live demonstration. (This experiment was done by building “a distributed testbed that emulates a large urban camera network using hundreds of concurrent Real-Time Streaming Protocol (RTSP) video streams. Each stream is hosted on a heterogeneous cluster of Raspberry Pis”.
“By localizing heavy video analytics at the network periphery, the system avoids centralized bandwidth bottlenecks, enabling sustainable, city-scale traffic sensing,” they write.
Why this matters – towards a ‘living city’ via AI:
Papers like this forecast a world where cities come alive with ambient intelligence distributed in equal measure to their existing sensors – cameras move from being passive monitors to active classifiers, microphones start intelligently listening for a broader range of sounds than gunfire, and road sensors model traffic patterns locally. This kind of intelligence can both create large surveillance architectures and increase the efficiency with which cities operator – as with so many things with AI, it is all a balance, bounded by the surrounding thicket of norms and laws to choose where between authoritarianism and democracy the resulting capabilities fall.
Read more
:
Scaling Real-Time Traffic Analytics on Edge-Cloud Fabrics for City-Scale Camera Networks (arXiv)
.
***
Helping satellites run on-device AI for arctic monitoring:
…Frontier models are important, but so are tiny, miniaturized devices for edge computing…
Researchers with the German Research Center for Artificial Intelligence have built TinyIceNet, a very small vision model for estimating sea ice thickness from synthetic aperture radar data. TinyIceNet is a proof-of-concept demonstration of how to make very lightweight vision models that could plausibly be deployed onto devices which have very small amounts of power and where bandwidth is expensive, like satellites and robots.
What is TinyIceNet?
The model is a small vision model whose job is to take Synthetic Aperture Radar (SAR) data of polar regions and other cold places, then characterize the ice thickness and maturity within the SAR data. The idea here is that doing this on-device would be very efficient – “Instead of downlinking vast volumes of raw imagery, satellites can generate SOD products in near-real-time”.
How they built it:
TinyIceNet is a simplified U-net architecture vision model trained on the AI4Arctic dataset, which contains ~533 netCDF files, each of which contains SAR images which are associated with a map that indicates the type and thickness of sea ice. The authors carefully design the model to fit into a relatively small computational envelop on a Xilinx chip.
Specifically they use a “AMD Xilinx ZCU102 evaluation board, which integrates the ZCU9EG SoC combining a quad-core ARM Cortex-A53 processor with FPGA fabric, using High-Level Synthesis (HLS) and the DeepEdgeSoC framework”. They use the DeepEdgeSoC toolchain to further improve the efficiency of the model, as the software “provides a library of modular C++ building blocks (e.g., convolutions, pooling, activation functions, and feature map buffers) that can be specialized at compile time using C++ template parameters”.
TinyIceNet was trained for 500 iterations on a single GeForce RTX 4090 GPU using PyTorch 2.4 with CUDA 12.5 support.
Results:
The authors test out the model on 3 hardware platforms:
RTX 4090
: “Provides the highest throughput at 764.8 fps, benefiting from its large number of CUDA cores and high memory bandwidth. However, this performance comes at a relatively high energy cost of 228.7 mJ per scene, making it unsuitable for power-constrained environments such as satellites.”
Jetson AGX Xavier:
“Achieves 47.9 fps but exhibits the highest energy consumption (1218.5 mJ).”
Xilinx ZCU102 FPGA
: “Achieves a lower throughput of 7 fps, yet offers a highly competitive energy profile, consuming only 113.6 mJ per scene. Despite the lower frame rate, this energy efficiency makes the FPGA implementation compelling for on-board satellite processing, where power availability is severely restricted”.
Why this matters – in the future, AI systems will do this stuff automatically
: The amazing thing about this research is that it seems trivial (I mean no offense to the authors) for a modern powerful AI systems to do this: all it required was figuring out a task (stuff a computer vision model into a small computational envelop) and then running some experiments to take an existing architecture, tweak it for a hardware platform, and train it on a dataset, then run some tests.
In a couple of years we might expect AI agents to do this stuff themselves, procuring compute resources to let them develop and distribute small AI systems to arbitrary compute platforms for arbitrary purposes. This is one of the main ways I think we could get a sudden exponential boom in economic activity attributable to AI – AI systems will get smart enough that they can drastically improve their ability to know about and interact with the physical world through the creation of custom ‘edge computing’ AI systems to give them better sensory data and actuators.
Read more
:
TinyIceNet: Low-Power SAR Sea Ice Segmentation for On-Board FPGA Inference (arXiv)
.
***
ByteDance finetunes a Seed1.6 model to be a CUDA-writing agent:
…Using AI to finetune AI to write code to train future AI systems…
Researchers with ByteDance and Tsinghua University have built CUDA Agent, a fine-tuned AI model for writing GPU programming code. The research is another sign of how people are increasingly using AI to speedup core aspects of AI development. It’s also vaguely notable for the fact that a major Chinese lab and university continues to use US-made chips (NVIDIA H20s) versus homegrown ones.
What CUDA Agent is:
CUDA agent is a finetuned Seed 1.6 LLM, an MOE model with 23B active parameters and 230B total parameters. Finetuning took place on a cluster of  128 NVIDIA H20 GPUs. CUDA Agent has been developed specifically for writing GPU code by being fine-tuned on a dataset refined out of the underlying PyTorch ‘torch’ and ‘transformers’ software libraries. “The filtered synthesized training dataset contains 6,000 samples, forming CUDA-Agent-Ops-6K, a curated operator-level dataset for training CUDA-capable agents,” the authors write.
Turning a model into an agent:
In the last year or so, researchers have repeatedly shown that you can increase the performance of an LLM for a given task by giving it access to some specialized tools and some specialized instructions, then letting it operate over time – this is essentially an AI agent.
The CUDA agent here is the fine-tuned model that has been turned into an agent by adopting the OpenHands framework, then given tools including BashTool, GlobTool, MultiEditTool, TodoWriteTool. The agent runs in a four stage loop:
Analyze performance of the native PyTorch implementation of a given bit of CUDA code using the provided
profile.py
script
Implement custom CUDA operators by rewriting the model in model_new.py
Compile and evaluate the optimized model in the provided GPU sandbox environment
Repeat the optimization process until the implementation achieves a 5% speedup over the torch.compile baseline
Results:
The resulting agent is very good at CUDA kernel development: “CUDA Agent successfully scales to a context length of 128k tokens and supports up to 200 interaction turns, achieving state-of-the-art performance,” they write. Their finetuning massively boosts performance from a base rate of 74% for Seed1.6, to “100%, 100%, and 92% over torch.compile on the Level-1, Level-2, and Level-3 splits of KernelBench, outperforming advanced proprietary models such as Claude Opus 4.5 and Gemini 3 Pro by approximately 40% in the Level-3 split.”
However, comparing against other base models paints a different story: Claude Opus 4.5 and Gemini 3 Pro base models get 95.2% and 91.2% respectively, suggesting that if they were finetuned, you’d increase their performance as well, and they start from a much stronger baseline.
Why this matters – building AI that builds AI:
These results show how modern AI systems are increasingly good at the tasks required to develop and deploy AI systems themselves. This suggests we’re at the beginning of a compounding speedup where new AI models will be used to increase the efficiency of the infrastructure with which their successors will be trained.
Read more:
CUDA Agent: Large-Scale Agentic RL for High-Performance CUDA Kernel Generation (arXiv)
.
***
Tech Tales:
Dandelion Sky
[2031, Northern Europe]
We made sand castles and in the distance the blue sky was pockmarked with yellow and red bursts and then seconds later the crumpled sounds of the explosion reached us. We were so used to it we didn’t look up.
On the way back from the park the air whined as drones flew to replenish the perimeter of the city. We watched them, bird-like in their varieties, some zipping by quick as starlings, and other larger ones moving heavily through the air. There were so many varieties: the football-sized interceptors which died by the thousands each day. The pizza-boxes that worked as communications and AI relays. Then of course the motorbike-sized motherships which could rapidly repopulate areas that were sustaining heavy losses.
The war had been going on for five years. Our city was like so many across the world – a nucleus of humans, protected by so many thousands upon thousands of machines, spinning around the periphery, exchanging energy and mass in some bloodless dance with our enemies.
That night, the city narrated itself through statistics: 3410 interceptors destroyed. A green day: 100% success, with nothing making its way through. Replenishment rate: 4000 and climbing. And promising reports that our military had struck deep in the heart of enemy territory taking out several of their drone factories.
We drew the blackout curtains in every room except our bedroom. With the kids asleep and my wife passed out beside me I looked out into the darkness, my face occasionally lit by the explosion of some distant drone, and then the room buzzing with the reverberation of the window as the soundwaves reached it.
But when I woke up the next day, there was something different in the air: silence. And my phone did not work. We drew the shades and looked out and the sky was blue and perfectly clear: not a cloud or a drone in the sky. My wife stared out and her jaw tightened and she clutched our kids close.
“Dada, where are the machines?” my youngest said.
“Yeah Dad, what’s up?” said the older one.
“I don’t know,” I said. “Draw the curtains. We’re going to camp today!”
And I set my wife and kids up in the apartment with pillows in front of the TV and the game console on and a bunch of snacks. The kids were excited and my wife played along.
“I’ll see if I can figure out what’s going on,” I whispered to her. “I won’t go far and I won’t be gone long.”
Outside, there were a few people who had the same idea as me. None of us knew much. None of our electronic communication systems worked. Which people were even in charge of the drones? None of us knew. They mostly worked via AI. A lot of their decision-making was federated; distributed systems doing what made most sense to them, coordinating only with themselves.
“Maybe they’ve turned off because the war is over?” someone said.
“Maybe they’ve been hacked – we’re about to be attacked!” said someone else.
“What there was a crash – they just all broke at once?” said someone else.
There was nothing to do so I went home. My wife and kids were playing games. I grabbed some binoculars and went up to the fire escape and out onto the roof of the building. And there I stood, looking at a horizon free of machines. Occasionally looking at other people on other buildings doing the same. And eventually I put the binoculars down and I just stood there, listening for the whine of drones. But all I could hear was the wind and, in the distance, muffled birdsong.
Things that inspired this story
: Gradual disempowerment and what it might mean for moments of crisis; automation and AI; winding the clock forward on the dronewar in Ukraine; war and peace and family.
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
March 9, 2026
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

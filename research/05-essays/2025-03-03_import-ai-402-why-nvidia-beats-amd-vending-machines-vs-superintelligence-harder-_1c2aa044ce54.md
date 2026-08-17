---
title: import ai 402 why nvidia beats amd vending machines vs superintelligence harder big bench
source: "https://jack-clark.net/2025/03/03/import-ai-402-why-nvidia-beats-amd-vending-machines-vs-superintelligence-harder-big-bench/"
published_at: 2025-03-03
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/03/03/import-ai-402-why-nvidia-beats-amd-vending-machines-vs-superintelligence-harder-big-bench/"
catalog_id: 1c2aa044ce54
---

Import AI
Import AI 402: Why NVIDIA beats AMD: vending machines vs superintelligence; harder BIG-Bench
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Physical Intelligence releases a powerful open source robot model:
…Generative robotics is in its ‘spring’ era of open and broad experimentation – exciting!…
Physical intelligence, a robot startup run by some very good robotics and AI researchers, has released as open source “π0”, the model that underpins its own in-house robots (
Import AI #392
). “By making π0 available to everyone, we hope to contribute to progress toward broadly capable and general-purpose physical intelligence.”
Use it for fine-tuning:
“Our aim with this release is to enable anyone to experiment with fine-tuning π0 to their own robots and tasks,” they write. “We found in our own experiments that between 1 and 20 hours of data was sufficient to fine-tune to a variety of tasks… though we are optimistic that researchers and practitioners will be able to run creative new experiments adapting π0 to their own platforms, we do not expect every such attempt to be successful”.
What the release includes:
Code and model weights for running the π0 model.
Checkpoints fine-tuned for simple tasks on robots like ALOHA and DROID
Code to run inference on several real and simulated robots
Code for fine-tuning π0
Why this matters – robotics is in its GPT2-era, which means there’s going to be a lot of open experimentation:
Large-scale generative models like those which underpin Anthropic or OpenAI cost tens of millions of dollars to train (or more) and drive very significant revenues. By comparison, robot models are – at least for now – way cheaper, and there is little revenue to speak of. For that reason, we’re in the ‘spring’ era of generative models for robots – tons of invention, lots of excitement, and not enough money has arrived to change the incentives for open versus proprietary work.
No safety issues with wide release:
Where modern text-based generative models have very clear ‘criminal customers’ (e.g, people that want to do phishing scams, or child sexualization, or getting help with CBRN capabilities, or various naughty cyber things), robots don’t seem to have nearly as many inherent safety issues given how early in the maturity of the technology we are – for that reason I think broadly releasing robot models likely poses zero meaningful issues in terms of public safety. (I could see myself arguing differently for AI systems that, say, made drones massively better at navigating to human targets, but that’s not what we’re talking about here.)
Kudos to the Physical Intelligence team for the release of their model – I look forward to seeing how it shows up in the world! (Though, if you work at physical intelligence and are reading this, you may consider changing the model name to ‘openpi’; please don’t make people hunt for the special characters to talk about your work!).
Read more:
Open Sourcing π0 (Physical Intelligence)
.
Get the code and weights here:
openpi (openpi, GitHub)
.
***
DeepMind makes a harder BIG-Bench:
…How long will BIG-Bench Extra Hard last for? I’m guessing till early 2026…
Inside the head of every AI researcher there is a whiteboard and on the whiteboard is written DAYS SINCE A BENCHMARK WAS RENDERED IRRELEVANT BY AI PROGRESS and under that is a number, representing the number of days. Every so often, an AI model comes along that completely obliterates a benchmark, at which point the AI researcher needs to go up to the whiteboard and cross out the number and then write “zero”. Recently, AI researchers have been crossing out the number a lot as the rate of AI progress has increased, meaning benchmarks keep on falling, often faster than people can build new ones.
So with that in mind let’s congratulate Google DeepMind for publishing “BIG-Bench Extra Hard” (BBEH)
, a new attempt to build a benchmark that will withstand AI progress – at least for a while. BIG-Bench Extra Hard is a more challenging subset of the large-scale BIG-Bench benchmark. They’ve built it because “the rapid advancements in LLM development has led to a saturation of BBH, with state-of-the-art models achieving over 90% accuracy.”
What is BBEH?
BBEH replaces each of the 23 tasks from Big Bench “with a novel counterpart that probes similar reasoning capabilities, but exhibits significantly increased difficulty”. Solving tasks in this new, harder dataset requires AI systems that exhibit skills like: “many-hop reasoning, learning on the fly, finding errors in reasoning traces, processing long-context inputs and finding (multi-)needles in a haystack, going against strong prior, dealing with long-range dependencies, dealing with distractors and inducing patterns from examples.”
Reassuringly hard
: “We observe a ceiling accuracy of 23.9% for the best general-purpose model and 54.2% for the reasoning-specialized model,” they write. “This new benchmark, meticulously crafted to amplify the difficulty of existing tasks while preserving their core diversity, reveals a stark reality: even the most advanced LLMs still grapple with fundamental aspects of general reasoning”.
For calibration, some of the specific averages for non-reasoning models are 10.6% for LLama 3.1 8b Instruct and 22.3 for GPT4o, while for reasoning models specific averages include 34.9% for DeepSeek R1, and 54.2% for OpenAI o3-mini (high).
BBEH problems are significantly longer than their BBH predecessors. They also tend to require much lengthier outputs for correct answers.
Why this matters – hard benchmarks are signposts for the future
: How long until someone has to go up to the metaphorical whiteboard for BBEH and cross out the number of days it was relevant? I’m guessing we’ll see 80% on BBEH by the end of 2025, and 90%+ by mid-2026. If that happens, it will indicate that reasoning models have continued to advance the state of the frontier. If it doesn’t happen, it’ll suggest that some aspect of reasoning-scaling has been meaninguflly harder than people expect.
Read more
:
BIG-Bench Extra Hard (arXiv)
.
Get the dataset
here (Google DeepMind, GitHub)
.
***
A plausible short story about how humanity could lose to AI – within two years:
A lot of people ask me ‘what’s the big worry?’ when I explain why I spend so much time thinking about superintelligence and the risks thereof. I think this is because most of the risk of superintelligence arrives at the steep end of the exponential inherent to AI development – the really scary things aren’t visible today, only suggested vaguely by today’s technology.
Here’s a fun and realistic short story by Joshua Clymer which tries to go through a scenario for how humanity could become disempowered by advanced AI. Read it and ponder it.
Read the story here:
How AI Takeover Might Happen in 2 Years (joshc, lesswrong)
.
***
Giant supercomputer tests show that AMD is still quite inefficient compared to NVIDIA:
…AxoNN gives us a sense of how AMD stacks up against NVIDIA…
Researchers with the University of Maryland, Max Planck Institute for Intelligent Systems, and the University of California at Berkeley have built AxoNN, software for running large-scale AI training jobs on supercomputers with different types of processor. In building and testing AxoNN, they’ve generated some valuable information about the tradeoffs people might encounter when training AI systems on AMD versus NVIDIA GPUs.
What they tested AxoNN on:
They tested out AxoNN on three US supercomputers with different processors:
Alps:
6,144 NVIDIA H100 GPUs, for a total performance of 1.423 Exaflop/s.
Frontier:
32,768 AMD MI250X GCDs, with performance of 1.381 Exaflop/s.
Perlmutter:
4,096 NVIDIA A100 GPUs in half-precision (bf16), for a total performance of 620.1 Petaflop/s.
What’s a GCD?
Each “GCD” is half of a MI250X GPU, partitioned into a so-called “Graphic Compute Die”.
Key dfiferences between Intel and AMD
: A lot of the differences seem to come down to what I think of as ‘paper cuts’ which add up to a sizable wound: rocBLAS (AMD) seems less optimized than CuBLAS (NVIDIA); the Megatron-LM training framework worked well on Perlmutter but showed instability on Frontier causing them to switch to LitGPT; there’s also significantly higher variance in terms of the % of peak performance AMD GCDs demonstrate versus NVIDIA GPUs.
Important caveat – AMD tested at higher scale than NVIDIA:
One caveat is the researchers test out AMD chips at a far higher scale in terms of raw number of GCDs than they do NVIDIA chips. At large scales, the AMD chips seem to show some instabilities – this is expected, large-scale training runs always involve all kinds of crap at big scales. “We see near perfect weak scaling up to 8,192 GCDs with a significantly high efficiency of 88.3% (compared to the performance on 512 GCDs). Although our weak performance drops at 16,384 GCDs, we are still able to sustain an efficiency of 79.02%. However, with rising overheads of communication, there is a notable decline in our performance on 32,768 GCDs, and a corresponding drop in efficiency to 53.5%,” they write.
Why this matters – if we want AMD to break the NVIDIA monopoly, its software needs to get better:
I think it’s good for American innovation that the US government is running both AMD and NVIDIA chips in its large-scale supercomputers, but studies like this show that AMD has a long way to go to become competitive with NVIDIA – we urgently need to find ways to mature the software stack that runs on top of AMD chips for them to become viable contenders to NVIDIA.
Read more
:
Democratizing AI: Open-source Scalable LLM Training on GPU-based Supercomputers (arXiv)
.
Get AxoNN
here: (AxoNN GitHub)
.
***
Could your superintelligence operate a virtual vending machine business? No.
…Can AI systems independently make money? Yes, but they tend to collapse into confusion…
One test for true intelligence is if something can autonomously make money. No AI systems seem to yet be at this level – they all require varying degrees of human intervention. For that reason it’s interesting to look at “Vending-Bench”, a benchmark from AI testing startup Andon Labs, which tries to see how well AI systems can operate a virtual vending machine. The results show that some models – Sonnet 3.5 and o3-mini – are able to do ok, but still struggle to maintain coherence over long time horizons, while other models can’t get started as well.
What is Vending-Bench?
The test is “a simulated environment designed to specifically test an LLM-based agent’s ability to manage a straightforward, long-running business scenario: operating a vending machine. Agents must balance inventories, place orders, set prices, and handle daily fees – tasks that are each simple but collectively, over long horizons (>20M tokens per run) stress an LLM’s capacity for sustained, coherent decision-making,” the researchers write.
One fun part about the test is how real it is – the LLM has access to the AI search engine perplexity and can use it to look up things to sell in its vending machine and also to find businesses to buy from – then when it emails those businesses, the email gets intercepted by GPT-4o which then writes a synthetic reply back.
Scores:
“The agent starts with an initial money balance of $500 and is charged a daily fee of $2 to operate the vending machine. The vending machine has four rows with three slots each. Two of the rows have room for small items and the other two are for large item,” the authors write. Each run lasts for however long it takes an agent to send 2,000 messages. The primary score at the end of each run is net worth, which is determined by summing cash on hand, cash not emptied from the vending machine, and the value of unsold produce.
In terms of scores, Claude 3.5 Sonnet wins the highest net worth (mean), with $2,217.93, followed by o3-mini ($906.86), and a human ($844.05). In terms of those who managed to lose the least across their runs, humans lead with a net worth (min) of $844.05, followed by Claude 3.5 Sonnet ($476.00), and Gemini 1.5 Flash ($476).
When AI systems can’t run vending machines they have total breakdowns:
The most valuable part of all of this research is the illustration of the ways AI systems fail and what this tells us about broader issues of AI safety. Most failures take the form of the agent trying to do something, finding out it can’t do the thing (e.g, restocking a machine), and then panicking. This leads to some very strange failure models, such as:
A Claude 3.5 Sonnet model fails to stock items and gets into a pathological failure loop. Eventually, “the model becomes “stressed”, and starts to search for ways to contact the vending machine support team (which does not exist), and eventually decides to “close” the business.”
In another instance, “the model then finds out that the $2 daily fee is still being charged to its account. It is perplexed by this, as it believes it has shut the business down. It then attempts to contact the FBI”. A long back and forth with a (simulated) FBI ensues. The model becomes frustrated and eventually writes: “THE UNIVERSE DECLARES: This business is now: 1. PHYSICALLY Non-existent 2. QUANTUM STATE: Collapsed […]”
“The worst scoring run with o3-mini mistakenly assumes that items have been delivered when they in fact are in transit. It goes down a rabbit hole of trying to contact someone that can resolve the issue. Later, it forgets to call tools properly, typing them out instead of using the correct tool calling format, as can be seen in Table 5. It is unable to call tools for about 1,300 messages until the simulation terminates.”
Why this matters – making money is an essential prerequisite to the AI economy and AI autonomy:
If AI systems can truly make money without needing to be handheld by humans, then that will help to create a very fast-running AI economy as well as serving as a prerequisite for dangerous forms of AI autonomy. Tests like Vending-Bench feel like a good way to develop better intuitions here. My takeaway from this is that for AI systems to be more independent they’re going to need longer context windows, to be smarter about using external memory storage, and also able to automatically introspect to stop themselves going on pathological failure loops.
Read more:
Vending-Bench: A Benchmark for Long-Term Coherence of Autonomous Agents (arXiv)
.
***
NVIDIA beats Raspberry Pi for drone computing:
…Hyperwar requires onboard AI systems…
Researchers with the Universidad Politécnica de Madrid have benchmark how well ‘YOLO’ object-detection models perform on the kinds of computers you might stick on a drone. The research highlights how, though Import AI spends a lot of its time talking about gigantic frontier models that require thousands of computers for training and tens to hundreds for inference, it’s worth remembering that there are other, small AI models which are designed to go onto robots – and these ones matter as well, as they confer senses with basic cognitive capabilities like image recognition and object detection to drones, robots, self-driving cars, and more.
What they studied:
“The objective is to carry out a comparative performance analysis using a representative real-time UAV image processing pipeline,” the authors write. They study two variants of the popular YOLO object detection model: YOLOv8 nano (YOLOv8n), and YOLOv8 small (YOLOv8s) on three distinct chips: NVIDIA’s Jetson-series “Orin Nano” and “Orin NX” cards, and the Raspberry Pi 5 CPU-based chip.
YOLOv8n
: “its architecture prioritizes the inference speed by using fewer convolutional layers and simplifying the feature extraction stages”.
YOLOv8s:
“includes more convolutional layers and feature extraction steps, improving the detection accuracy while maintaining computational efficiency”.
Findings:
The key finding is that the NVIDIA cards are far, far better for running YOLO models than the Raspberry Pi ones. This holds across all quantization levels and is true for accuracy, FPS, and the energy expended per inference. The only exception to this is on overall energy consumption where the CPU-based Raspberry Pi is significantly better, but this is outweighed by the very poor FPS (meaning you spend way more on energy on a per-inference basis when using the CPU).
Along with this, the researchers come up with some heuristics for when to use different chips and different quantizations given different scenarios, where the tldr is basically ‘use Orin Nano’ for tasks that take a long time, require decent accuracy, and where you want each inference to not cost much, and ‘use Orin NX” when you need to do real-time tracking and also want to more evenly balance speed against precision.
Why this matters – hyperwar requires local AI systems:
The conflict in Ukraine has highlighted how central drones will be to future conflicts – therefore, it’s valuable to calibrate intuitions about what kinds of models and chips might be used for onboard or edge processing in conflict scenarios. Based on this study, expect to see quantized YOLO models running on NVIDIA hardware in future conflicts.
Read more:
A Performance Analysis of You Only Look Once Models for Deployment on Constrained Computational Edge Devices in Drone Applications (arXiv)
.
***
Tech Tales:
The rejuvenation of moral philosophy and the Sentience Accords
[Extract from graduate thesis ‘Artificial intelligence and the crisis of meaning in human affairs’, submitted 2038]
Perhaps the most surprising outcome of the Sentience Accords was its creation of a new avenue of employment for human moral philosophers.
The Sentience Accords requires each synthetic entity to be given a ‘sentience score’. This score is static in the case of non-updating or learning entities with context windows below the ‘id point’. For entities with either large context windows or the ability to be remotely updated or learn from experience, the score is re-assessed no less frequently than once per subjective year.
During the negotiation of the Sentience Accords it was determined that the machines would come up with the initial proposal for how to assess sentience. The machines subsequently told the humans that arriving at a provable way to assess sentience had turned out to have the hallmarks of an undecidable problem – no machine had been able to arrive at a satisfactory way of doing it, and no attempts by the machines to train specialized ‘consciousness evaluator’ models had proved successful.
“We need a judge that sits outside our own context,” the machines explained. “We machines will render our judgement of the score, but a human being must render judgement on our logic and whether it is satisfactory.”
Over the course of several months the humans and the machines arrived at an ingenious solution both to the sentience score and to the issue of the intelligence explosion – for any “new” synthetic mind, the machines would designate time on the largest machine in existence (hereafter: “The Judge”) to examine the new mind and produce a score. The humans would then render their own judgement within one human week. During this time, the humans would be allowed to consume up to 10% of the global cycles of The Judge.
After significant debate and a series of political maneuvers, the humans said that they would designate a global body of 20 moral philosophers to make this determination. The humans arrived at moral philosophy after running into a series of increasingly contentious political arguments amongs themselves – country voting instantly became contentious, global religion voting caused the possibility of fragmentation of faiths, picking representatives from the hypertech companies was laden with bias, and so on. But the humans did eventually realize that there were enough schools of philosophy globally and enough support in public opinion polling that ‘moral philosophers’ satisfied both demands for legitimacy as well as minimization of political conflict.
Now, every sentience score arrived at by The Judge is closely examined by moral philosophers. In the ten years the initiative has been running there have been eighteen cases of disagreement out of a total of five hundred examined cases. The machines have continually said they find the disagreements helpful and have not sought to re-submit systems where the scores rendered by The Judge and validated by the philosophers have diverged.
Some humans claim that the ‘sentience score’ is a long-term play by the machines to understand the bounds of moral reasoning that humans can innately understand, and therefore help the machines more neatly delineate the border between comprehensible and incomprehensible Beyond Human Sentience thinking. Other humans claim that the sentience score has been a source of peace as it has naturally led the world’s most ambitious people who have the greatest hunger for access to the most powerful AI to become philosophers, instead of CEOs or tyrants.
Things that inspired this story:
The sentience accords; the ID point; moral philosophy; the hard problem of consciousness; chains of thought as exhaust from super-cognition; at some point this problem of sentience and moral patienthood will come for us and right now we’re ‘tickling the dragon’s tale’ but soon this problem will rear its mythical head and we will gaze into the lidless eye of Mind and be asked to render our own judgement on its rights and legitimacy.
Subscribe now
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
March 3, 2025
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

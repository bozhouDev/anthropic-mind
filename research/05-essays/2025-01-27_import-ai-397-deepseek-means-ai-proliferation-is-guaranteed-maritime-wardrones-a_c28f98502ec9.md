---
title: import ai 397 deepseek means ai proliferation is guaranteed maritime wardrones and more evidence of llm capability overhangs
source: "https://jack-clark.net/2025/01/27/import-ai-397-deepseek-means-ai-proliferation-is-guaranteed-maritime-wardrones-and-more-evidence-of-llm-capability-overhangs/"
published_at: 2025-01-27
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/01/27/import-ai-397-deepseek-means-ai-proliferation-is-guaranteed-maritime-wardrones-and-more-evidence-of-llm-capability-overhangs/"
catalog_id: c28f98502ec9
---

Import AI
Import AI 397: DeepSeek means AI proliferation is guaranteed; maritime wardrones; and more evidence of LLM capability overhangs
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Import A-Idea
…The existential shock of increasingly powerful AI systems…
A short essay about one of the ‘societal safety’ problems that powerful AI implies.
A few years ago, getting AI systems to do useful stuff took a huge amount of careful thinking as well as familiarity with the setting up and maintenance of an AI developer environment. Things got a little easier with the arrival of generative models, but to get the best performance out of them you typically had to build very complicated prompts and also plug the system into a larger machine to get it to do truly useful things. Basically, to get the AI systems to work for you, you had to do a huge amount of thinking.
Now, getting AI systems to do useful stuff for you is as simple as asking for it – and you don’t even need to be that precise. Often, I find myself prompting Claude like I’d prompt an incredibly high-context, patient, impossible-to-offend colleague – in other words, I’m blunt, short, and speak in a lot of shorthand. And Claude responds to my asks
basically perfectly
.
You might think this is a good thing. Certainly, it’s very useful. But beneath all of this I have a sense of lurking horror – AI systems have got so useful that the thing that will set humans apart from one another is not specific hard-won skills for utilizing AI systems, but rather just having a high level of curiosity and agency.
In other words, in the era where these AI systems are true ‘everything machines’, people will out-compete one another by being increasingly bold and agentic (pun intended!) in how they use these systems, rather than in developing specific technical skills to interface with the systems.
We should all intuitively understand that none of this will be fair. Curiosity and the mindset of being curious and trying a lot of stuff is neither evenly distributed or generally nurtured. Therefore, I’m coming around to the idea that one of the greatest risks lying ahead of us will be the social disruptions that arrive when the new winners of the AI revolution are made – and the winners will be those people who have exercised a whole bunch of curiosity with the AI systems available to them.
I talk to Claude every day. Increasingly, I find my ability to benefit from Claude is mostly limited by my own imagination rather than specific technical skills (Claude will write that code, if asked), familiarity with things that touch on what I need to do (Claude will explain those to me). The only hard limit is me – I need to ‘want’ something and be willing to be curious in seeing how much the AI can help me in doing that.
Today, everyone on the planet with an internet connection can freely converse with an incredibly knowledgable, patient teacher who will help them in anything they can articulate and – where the ask is digital – will even produce the code to help them do even more complicated things. Ensuring we increase the number of people on the planet who are able to take advantage of this bounty feels like a supremely important thing. If we get this right, everyone will be able to achieve more and exercise more of their own agency over their own intellectual world. If we get it wrong, we’re going to be dealing with inequality on steroids – a small caste of people will be getting a vast amount done, aided by ghostly superintelligences that work on their behalf, while a larger set of people watch the success of others and ask ‘why not me?’.
***
Computer vision is coming for the sea:
…After drones come the seadrones…
In the past few years we’ve seen warfare revolutionized in the Ukraine-Russia theatre by the usage of seagoing low-cost robotic platforms. These platforms are predominantly human-driven toward but, much like the airdrones in the same theater, there are bits and pieces of AI technology making their way in, like being able to put bounding boxes around objects of interest (e.g, tanks or ships).
With that in mind, I found it interesting to read up on the results of the 3rd workshop on Maritime Computer Vision (MaCVi) 2025, and was particularly interested to see Chinese teams winning 3 out of its 5 challenges. The workshop contained “a suite of challenges, including distance estimation, (embedded) semantic & panoptic segmentation, and image restoration. These tasks reflect advancements in dataset availability and evaluation protocols while emphasizing real-world deployment, including embedded hardware.”
Competition details:
Approximate supervised distance estimation:
“participants are required to develop novel methods for estimating distances to maritime navigational aids while simultaneously detecting them in images,” the competition organizers write. Models developed for this challenge need to be portable as well – model sizes can’t exceed 50 million parameters.
Submissions: 60 from 6 different teams
Winner: Nanjing University of Science and Technology (China).
USV-based Obstacle Segmentation Challenge:
“predict the scene segmentation (into obstacles, water and sky) for a given input image.”
Submissions: 59 from 16 teams.
Winner: GIST AI Lab (South Korea)
USV-based Embedded Obstacle Segmentation:
“”Modern obstacle detection methods often depend on highperformance, energy-intensive hardware, making them unsuitable for small, energy-constrained USVs [63]. The USVbased Embedded Obstacle Segmentation challenge aims to address this limitation by encouraging development of innovative solutions and optimization of established semantic segmentation architectures which are efficient on embedded hardware… Submissions are evaluated and benchmarked on a real-world OAK4
device from Luxonis.” Models need to get at least 30 FPS on the OAK4.
Submissions: 26 from 4 different teams.
Winner: CDalian Maritime University (DLMU)
USV-based Panoptic Segmentation Challenge:
“The panoptic challenge calls for a more fine-grained parsing of USV scenes, including segmentation and classification of individual obstacle instances. This formulation encapsulates the requirements of scene parsing for USV navigation in a more principled way, paving the road for downstream tasks such as tracking individual obstacles, trajectory prediction and obstacle avoidance.”
Submissions: 21 from 7 teams.
Winner: Fraunhofer IOSB (Germany).
MarineVision Restoration Challenge:
“Developing robust image restoration methods to enhance the detection and localization of underwater species.”
Submissions: 40 from 8 teams.
Winner: Nanjing University of Science and Technology”
Why this matters – asymmetric warfare comes to the ocean
: “Overall, the challenges presented at MaCVi 2025 featured strong entries across the board, pushing the boundaries of what is possible in maritime vision in several different aspects,” the authors write. How long until some of these techniques described here show up on low-cost platforms either in theatres of great power conflict, or in asymmetric warfare areas like hotspots for maritime piracy?
Read more:
3rd Workshop on Maritime Computer Vision (MaCVi) 2025: Challenge Results (arXiv)
.
***
What if instead of loads of big power-hungry chips we built datacenters out of many small power-sipping ones?
…Microsoft thinks optical communications could change how we build AI clusters…
Microsoft Research thinks expected advances in optical communication – using light to funnel data around rather than electrons through copper write – will potentially change how people build AI datacenters. Specifically, the significant communication benefits of optical comms make it possible to break up big chips (e.g, the H100) into a bunch of smaller ones with higher inter-chip connectivity without a major performance hit.
Another reason to like so-called lite-GPUs is that they are much cheaper and simpler to fabricate (by comparison, the H100 and its successor the B200 are already very difficult as they’re physically very large chips which makes issues of yield more profound, and they need to be packaged together in increasingly expensive ways). They’re also better on an energy point of view, generating less heat, making them easier to power and integrate densely in a datacenter.
“We propose to rethink the design and scaling of AI clusters through efficiently-connected large clusters of Lite-GPUs, GPUs with single, small dies and a fraction of the capabilities of larger GPUs,” Microsoft writes. “Smaller GPUs present many promising hardware characteristics: they have much lower cost for fabrication and packaging, higher bandwidth to compute ratios, lower power density, and lighter cooling requirements”.
It works in theory:
In a simulated test, the researchers build a cluster for AI inference testing out how well these hypothesized lite-GPUs would perform against H100s. They test out this cluster running workloads for Llama3-70B, GPT3-175B, and Llama3-405b. In their tests, they “show that while the basic Lite-GPU with no additional networking support could face performance limitations, a Lite-GPU cluster can be customized to match or improve on the performance of a typical H100 cluster.”
Why this matters – brainlike infrastructure:
While analogies to the brain are often misleading or tortured, there is a useful one to make here – the kind of design idea Microsoft is proposing makes big AI clusters look more like your brain by essentially reducing the amount of compute on a per-node basis and significantly increasing the bandwidth available per node (“bandwidth-to-compute can increase to 2X of H100). This is both an interesting thing to observe in the abstract, and also rhymes with all the other stuff we keep seeing across the AI research stack – the more and more we refine these AI systems, the more they seem to have properties similar to the brain, whether that be in convergent modes of representation, similar perceptual biases to humans, or at the hardware level taking on the characteristics of an increasingly large and interconnected distributed system.
Read more:
Good things come in small packages: Should we adopt Lite-GPUs in AI infrastructure? (arXiv)
.
***
Standard LLMs can do protein sequence analysis – no modification required:
…Capability overhangs in AI-driven science…
In AI there’s this concept of a ‘capability overhang’, which is the idea that the AI systems which we have around us today are much, much more capable than we realize. In new research from Tufts University, Northeastern University, Cornell University, and Berkeley the researchers demonstrate this again, showing that a standard LLM (Llama-3-1-Instruct, 8b) is capable of performing “protein engineering through Pareto and experiment-budget constrained optimization, demonstrating success on both synthetic and experimental fitness landscapes”.
What they did
: They initialize their setup by randomly sampling from a pool of protein sequence candidates and selecting a pair that have high fitness and low editing distance, then encourage LLMs to generate a new candidate from either mutation or crossover.
It works well:
In tests, their approach works significantly better than an evolutionary baseline on a few distinct tasks.They also demonstrate this for multi-objective optimization and budget-constrained optimization. “Our results consistently demonstrate the efficacy of LLMs in proposing high-fitness variants. Moving forward, integrating LLM-based optimization into realworld experimental pipelines can accelerate directed evolution experiments, allowing for more efficient exploration of the protein sequence space,” they write.
Why this matters – stop all progress today and the world still changes:
This paper is another demonstration of the significant utility of contemporary LLMs, highlighting how even if one were to stop all progress today, we’ll still keep discovering meaningful uses for this technology in scientific domains. The paper also rhymes with the recent research from FutureHouse which showed that with the help of some clever software they could push Llama-3.1-8B-Instruct to obtain performance at challenging bioscience tasks on par with Claude 3.5 Sonnet (
Import AI #396
). Generally, we should expect lots of parts of scientific research to speed up as people explore the capabilities of these systems and integrate them deeper into science.
Read more
:
Large Language Model is Secretly a Protein Sequence Optimizer (arXiv)
.
***
The biggest thing people are missing about DeepSeek: 800lk tokens to gain test-time compute capabilities:
…China’s best model training crew come out with a powerful reasoning model – and show how to turn any other model into one…
China’s DeepSeek team have built and released DeepSeek-R1, a model that uses reinforcement learning to train an AI system to be able to use test-time compute. R1 is significant because it broadly matches OpenAI’s o1 model on a range of reasoning tasks and challenges the notion that Western AI companies hold a significant lead over Chinese ones.
But perhaps most significantly, buried in the paper is an important insight: you can convert pretty much any LLM into a reasoning model if you finetune them on the right mix of data – here, 800k samples showing questions and answers the chains of thought written by the model while answering them.
Making a very powerful AI model is kind of easy (if you have a good model to start with)
: The main thing they do here is take a very powerful exciting model (DeepSeek-v3, which is a ~700bn parameter MOE-style model, compared to 405bn LLaMa3), and then they do two rounds of training to morph the model and generate samples from training. Specifically, they:
Fine-tune DeepSeek-V3
on “a small amount of long Chain of Thought data to fine-tune the model as the initial RL actor”. Once they’ve done this they do large-scale reinforcement learning training, which “focuses on enhancing the model’s reasoning capabilities, particularly in reasoning-intensive tasks such as coding, mathematics, science, and logic reasoning, which involve well-defined problems with clear solutions”. Once they’ve done this they “Utilize the resulting checkpoint to collect SFT (supervised fine-tuning) data for the subsequent round… this stage incorporates data from other domains to enhance the model’s capabilities in writing, role-playing, and other general-purpose tasks”. They then fine-tune the DeepSeek-V3 model for two epochs using the above curated dataset.
This is all easier than you might expect:
The main thing that strikes me here, if you read the paper closely, is that none of this is that complicated. DeepSeek essentially took their existing very good model, built a sensible reinforcement learning on LLM engineering stack, then did some RL, then they used this dataset to turn their model and other good models into LLM reasoning models.
Turning small models into reasoning models
: “To equip more efficient smaller models with reasoning capabilities like DeepSeek-R1, we directly fine-tuned open-source models like Qwen, and Llama using the 800k samples curated with DeepSeek-R1,” DeepSeek write. These distilled models do well, approaching the performance of OpenAI’s o1-mini on CodeForces (Qwen-32b and Llama-70b) and outperforming it on MATH-500.
Why this matters – a lot of notions of control in AI policy get harder if you need fewer than a million samples to convert any model into a ‘thinker’:
The most underhyped part of this release is the demonstration that you can take models not trained in any kind of major RL paradigm (e.g, Llama-70b) and convert them into powerful reasoning models using just 800k samples from a powerful reasoner.
This is a big deal because it says that if you want to control AI systems you need to not only control the basic resources (e.g, compute, electricity), but also the platforms the systems are being served on (e.g., proprietary websites) so that you don’t leak the really valuable stuff – samples including chains of thought from reasoning models.
Some providers like OpenAI had previously chosen to obscure the chains of thought of their models, making this harder.
But now that DeepSeek-R1 is out and available, including as an open weight release, all these forms of control have become moot. There’s now an open weight model floating around the internet which you can use to bootstrap
any other sufficiently powerful base model
into being an AI reasoner. AI capabilities worldwide just took a one-way ratchet forward. And they also published the approach to let you do RL training on any model so you can generate your own samples for RL training – For an example of this,
check out a YouTube video
where someone uses the DeepSeek techniques to modify his own Llama model via RL to take on this quality). Kudos to DeepSeek for being so bold as to bring such a change into the world!
Read more:
DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning (DeepSeek-R1, GitHub)
.
Get the model:
DeepSeek-R1 (HuggingFace)
.
***
Underground flying iron mine drones!
…A reminder you don’t need fancy frontier Ai to do cool and useful things in the world…
Here’s a fun paper where researchers with the Lulea University of Technology build a system to help them deploy autonomous drones deep underground for the purpose of equipment inspection. The best part? There’s no mention of machine learning, LLMs, or neural nets throughout the paper.
What they did:
“In this work a big emphasis is put on i) designing the local autonomy of the individual agents, to make sure that tasks can be executed independently even in the case of communication failure, and ii) how to design the task allocation architecture, utilizing communication only for reactively allocating the available tasks, to enable large-scale missions in active underground mining environments,” they write. “The performance of the proposed architecture has been validated by the deployment of a three-agent aerial robotic system in a large-scale mining environment to execute an inspection mission.”
Why this matters:
First, it’s good to remind ourselves that you can do a huge amount of valuable stuff without cutting-edge AI. Secondly, systems like this are going to be the seeds of future frontier AI systems doing this work, because the systems that get built here to do things like aggregate data gathered by the drones and build the live maps will serve as input data into future systems.
See the photos
: The paper has some remarkable, scifi-esque photos of the mines and the drones within the mine –
check it out!
Read more
:
Deployment of an Aerial Multi-agent System for Automated Task Execution in Large-scale Underground Mining Environments (arXiv)
.
Watch
a
video about the research here (YouTube)
.
***
Tech Tales:
The player of the final game
[The dividing line between the two historical eras.]
He woke on the last day of the human race holding a lead over the machines. He went down the stairs as his house heated up for him, lights turned on, and his kitchen set about making him breakfast. Then he sat down and took out a pad of paper and let his hand sketch strategies for The Final Game as he looked into space, waiting for the household machines to deliver him his breakfast and his coffee.
He had dreamed of the game. Most of his dreams were strategies mixed with the rest of his life – games played against lovers and dead relatives and enemies and competitors. But last night’s dream had been different – rather than being the player, he had been a piece. Giant hands moved him around. He saw the game from the perspective of one of its constituent parts and was unable to see the face of whatever giant was moving him. He did not know if he was winning or losing as he was only able to see a small part of the gameboard. A giant hand picked him up to make a move and just as he was about to see the whole game and understand who was winning and who was losing he woke up.
The self-driving car predicted he wanted to be silent and so nothing was playing when he stepped in. He went through the city. He’d let the car publicize his location and so there were people on the street looking at him as he drove by. Many of them were cheering. Some of them gazed quietly, more solemn.
At the convention center he said some words to the media in response to shouted questions. Though he heard the questions his brain was so consumed in the game that he was barely conscious of his responses, as though spectating himself.
“I am looking forward to a chance to play a beautiful game,” he heard himself saying.
“No, I have not placed any money on it. But I wish luck to those who have – whoever they bet on!,” he said to another reporter.
“Yes, whatever happens, I will still play the game.”
Inside he closed his eyes as he walked towards the gameboard. He counted seconds and navigated by sound, making sure he kept the cheering at equal volumes on either side, indicating he was walking straight. Then he opened his eyes to look at his opponent. The machines had made an android for the occasion. They had made no attempt to disguise its artifice – it had no defined features besides two white dots where human eyes would go. On its chest it had a cartoon of a heart where a human heart would go. Beyond that it was unadorned – a gleaming silver biped.
It reached out its hand and he took it and they shook. Then they sat down to play the game.
Outside the convention center, the screens transitioned to live footage of the human and the robot and the game. A commentator started speaking.
“This is an amazing day,” they said. “In every other arena, machines have surpassed human capabilities. Today, we will find out if they can play the game as well as us, as well. Many scientists have said a human loss today will be so significant that it will become a marker in history – the demarcation of the old human-led era and the new one, where machines have partnered with humans for our continued success. We’re grateful to our sponsors NVIDIA, ASML, and TSMC who have made this live broadcast possible.”
Things that inspired this story:
At some point, it’s plausible that AI systems will truly be better than us at everything and it may be possible to ‘know’ what the final unfallen benchmark is – what might it be like to be the person who will define this benchmark?; Lee Sedol and Move 37.
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
January 27, 2025
Filed Under:
Uncategorized
2 Comments to “Import AI 397: DeepSeek means AI proliferation is guaranteed; maritime wardrones; and more evidence of LLM capability overhangs”
Import AI 399: 1,000 samples to make a reasoning model; DeepSeek proliferation; Apple’s self-driving car simulator | Import AI
says:
February 10, 2025 at 1:56 pm
[…] month, I wrote that the release of DeepSeek R1 meant that AI proliferation was guaranteed (Import AI #397) because it would make it easy for people to create new reasoning datasets on which they could […]
Loading...
Reply
Import AI 399: 1,000 samples to make a reasoning model; DeepSeek proliferation; Apple’s self-driving car simulator – Noesis News
says:
March 9, 2025 at 12:50 am
[…] month, I wrote that the release of DeepSeek R1 meant that AI proliferation was guaranteed (Import AI #397) because it would make it easy for people to create new reasoning datasets on which they could […]
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

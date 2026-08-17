---
title: import ai 419 amazons millionth robot crowdtrack and infinite games
source: "https://jack-clark.net/2025/07/07/import-ai-419-amazons-millionth-robot-crowdtrack-and-infinite-games/"
published_at: 2025-07-07
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/07/07/import-ai-419-amazons-millionth-robot-crowdtrack-and-infinite-games/"
catalog_id: a6428415fa98
---

Import AI
Import AI 419: Amazon’s millionth robot; CrowdTrack; and infinite games
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Tracking multiple people in crowded scenes with CrowdTrack:
…Turnkey authoritarianism via AI…
Researchers with Fudan University in China have built CrowdTrack, a dataset and benchmark for using AI to track pedestrians in video feeds. CrowdTrack is interesting mostly because of what it says about the current state of surveillance – we can do most forms of video surveillance, but still have trouble tracking multiple people in fast-moving real world crowds.
What the dataset consists of:
The dataset is made up of 33 videos containing 40,000 distinct image frames and over 700,000 annotations. CrowdTrack contains over 5,000 individual trajectories – objects that are tracked across multiple frames.
“All data is collected in unconstrained daily environments, ensuring object behaviors remain natural and unmodified”, the researchers write. “While typical daily scenarios often involve slow-paced movement and low clothing similarity, we intentionally included footage from building sites to introduce unique challenges: workers’ uniform workwear and helmets suppress facial feature discriminability, thereby emphasizing the importance of gait and body shape features for tracking.”
Why this matters – scalable authoritarianism
: One of the things that makes authoritarianism expensive is the overhead that comes from building out and running a large-scale police state. One of the things AI does is make it much, much cheaper to do large-scale surveillance. Datasets like CrowdTrack are a symptom of the way AI is making it cheaper and easier to do surveillance that the dictators of the 20th century would have fantasized about but always been unable to fully fund. “Our dataset can be used for tasks like visual grounding, captioning, and appearance feature extraction,” the researchers write.
Read more:
CrowdTrack: A Benchmark for Difficult Multiple Pedestrian Tracking in Real Scenarios (arXiv)
.
Get the dataset and code here
:
CrowdTrack (CrowdTrack, GitHub)
.
***
Amazon deploys its millionth robot:
…Infrastructure for an autonomous superintelligence-run corporation…
Amazon has recently deployed its 1 millionth robot into its warehouses, “building on our position as the world’s largest manufacturer and operator of mobile robotics.” These robots are predominantly the hockey puck shaped robots used for moving and lifting shelves, though the company has recently started experimenting with robots for managing conveyor belts and doing some pick and place tasks. For perspective, Amazon said in the fall of 2017 that it had recently deployed its 100,000th Kiva (hockey puck) robot (
Import AI #62
).
DeepFleet
: Along with deploying more robots, Amazon has also developed some new software for managing how its robots move around its warehouses. The software, named DeepFleet, has helped Amazon reduce robot travel time by 10%. “Just as a smart traffic system could reduce wait times and create better routes for drivers, DeepFleet coordinates our robots’ movements to optimize how they navigate our fulfillment centers,” Amazon writes. “This means less congestion, more efficient paths, and faster processing of customer orders.”
Why this matters – fully automated infrastructure for a superintelligence
: I increasingly view robotics through the lens of ‘how might this help a superintelligence’. Amazon feels like a corporation which is building some of the basic infrastructure that might eventually be given over to a superintelligence that would form an autonomous corporation within the infrastructure of an existing human-run tech behemoth.
Read more:
Amazon launches a new AI foundation model to power its robotic fleet and deploys its 1 millionth robot (About Amazon, blog)
.
***
Worried about AI timelines and unsure of what to do? Read this.
…If you think AI 2027 is real, follow these tips…
Often I get asked by people ‘what can I do about short AI timelines’? Here’s a helpful post from Eli Lifland which reels off most of the advice I give people as well as some advice I haven’t thought of. If you’re worried about AI timelines and want to do something about it or know someone who is, pass them this.
Read more:
What you can do about AI 2027 (Eli Lifland, AI Futures Project, Substack)
.
***
Kyutai releases an excellent free neural speech system:
…Making AI more intuitive to interact with means more people will use AI…
Kyutai, a European open science lab, has released an impressive neural speech system. Specifically, Kyutai has released some powerful models for both speech-to-text
and
text-to-speech and they sound really good. “These models are powered by delayed streams modeling (DSM), a flexible formulation for streaming, multimodal sequence-to-sequence learning,” Kyutai writes.
STT:
The speech-to-text models “are optimized for real-time usage, can be batched for efficiency, and return word level timestamps,” Kyutai writes. Initially it has released an English and French model with ~1B parameters, and an English-only model with ~2.6B parameters. “The 1B model has a semantic Voice Activity Detection (VAD) component that can be used to detect when the user is speaking. This is especially useful for building voice agents.”
TTS:
The text-to-speech models include implementations for PyTorch to aide “research and tinkering”, Rust “for production… our robust Rust server provides streaming access to the model over websockets”, and for MLX “for on-device inference on iPhone and Mac”.
Why this matters – speech is natural:
Anytime we make it easier and more intuitive for people to interact with AI, people spend more time with AI systems. Technologies like powerful and freely available STT and TTS will massively increase the range of consumer-friendly applications that people can build which use AI.
Read more:
Kyutai TTS and Unmute now open-source (Kyutai blog)
.
Find out more at the project page:
Unmute (Kyutai)
.
Get the models here:
Delayed Streams Modeling: Kyutai STT & TTS (Kyutai, GitHub)
.
***
Mirage – a technology for generating an infinite, endlessly generated game:
…We are so unbelievably close to procedural, infinite games…
In the last year or so people have started playing with what I’ll call ‘generative game networks’, or GGNs. GGNs are big transformer models pre-trained on a ton of data from videogames and allow people to play endless, procedural games. In the last few months we’ve seen GGNs crop up from startups for playing Minecraft (
Import AI #390
) and Quake (
Import AI #408
), and we’ve seen companies like Google publish research suggesting that this idea can be taken much further.
In the latest example of a GGN, there’s ‘Mirage’, a network from a new startup called Dynamic Labs. Mirage is “the world’s first real-time generative engine enabling live UGC gameplay through state-of-the-art AI World Models,” according to the company. Mirage has some interesting features – along with regular controls you can also prompt the game with text to do things for you while you’re playing, like create a new road, or delete an enemy. But don’t get too excited – it’s extremely janky.
Just play the damn thing:
To Dynamic Labs’ credit, the company has shipped two demos you can play in your browser – a GTA-like game called ‘Urban Chaos’, and a Forza Horizon-like game called ‘Coastal Drift’. I’d encourage people to play these for a few minutes to calibrate intuitions about this technology. Here are my impressions:
GGN games are
almost
fun, and I expect they’ll be actively fun to play in a year (need greater FPS and more consistency).
World consistency is going to be a challenge – try rotating the camera around your character in Urban Chaos and you’ll see the world become inconsistent very quickly.
Prompting them basically doesn’t work – we’re in the GPT-1 era of prompting GGNs.
This is the worst the technology will ever be.
I expect to be regularly playing GGN games for fun in 2027.
How they built it:
There are barely any details about how it’s built, so I’ll quote a bit from the blog: Mirage involves “a large-scale, transformer-based autoregressive diffusion model capable of generating controllable, high-fidelity video game sequences.” The network is “built on a robust training foundation designed for understanding and generating rich gaming experiences. This foundation begins with the large-scale collection of diverse game data from across the internet—providing the breadth needed to capture a wide array of game mechanics and styles,” the company writes. “To complement this, we built a specialized data recording tool that captures high-quality, human-recorded gameplay interactions.”
Why this matters – infinite jest
: In David Foster Wallace’s brilliant (often critiqued, rarely read in full) novel ‘Infinite Jest’ there is a film called ‘the Entertainment’ which is so compelling that its viewers lose all interest in anything else in the world. I believe that AI holds within itself the ability to create ‘the entertainment in reality’ via fully generative choose-your-own adventure worlds that will blur the lines of film, games, and reality itself. We’re likely going to see the emergence of this new meta-media this decade.
Read more
:
Introducing Mirage: Research Preview: The World’s First AI-Native UGC Game Engine Powered by Real-Time World Model (Dynamics Lab, blog)
.
***
AI startup Chai-2 one-shots de novo antibody design with a generative model:
…Various caveats apply, but the AI-Bio intersection is getting very interesting…
AI startup Chai has developed Chai-2, an “all-atom foundation model for general purpose protein design”. As a model, Chai-2 is to proteins as an LLM like ChatGPT or Claude is to language; it’s read a huge amount of scientific data and can generate and classify information relating to proteins. These kinds of ‘biological foundation models’ are an example of how the techniques pioneered in language-based generative modelling are flowing through to other parts of science.
What Chai-2 can do:
The model “achieves a 16% hit rate in fully de novo antibody design, representing an over 100-fold improvement compared to previous computational methods,” the authors write. Chai-2 “predicts antibody-antigen complexes with experimental accuracy twice as often as our previous Chai-1 model”, they write. Chai-1 was released as an open source model in September 2024 (
Import AI #385
).
“For every target evaluated, Chai-2 achieves at least a three fold improvement in experimental hit rate compared to the next-best method,” they write. “Chai-2 demonstrates state-of-the-art experimental success rates across diverse and challenging protein design tasks.”
What they did:
“We prompt Chai-2 to design ≤20 antibodies or nanobodies to 52 diverse targets, completing the workflow from AI design to wet-lab validation in under two weeks. Crucially, none of these targets have a preexisting antibody or nanobody binder in the Protein Data Bank. Remarkably, in just a single round of experimental testing, we find at least one successful hit for 50% of targets, often with strong affinities and favorable drug-like profiles”, they write. In addition, “the strong performance of Chai-2 in structure prediction – predicting 34% of antibody–antigen complexes with DockQ > 0.8 (compared to 17% for its predecessor, Chai-1) – highlights the power of integrating high-fidelity structure prediction with generative design”.
Why this matters:
‘We’re entering an era where we can now design molecules with atomic precision on a computer,” says Joshua Meier in a video about the research. “Digital biology is no longer science fiction, it’s happening now”.
Read more:
Zero-shot antibody design in a 24-well plate (Chai Discovery)
.
Learn more about
Chai-2 via this twitter thread (Chai Discovery, twitter)
.
***
Tech Tales:
The True Resistance
[Recollected speech given in 2025 by [REDACTED] to members of the First Resistance, gathered via interview as part of the reconciliation efforts mandated by The Sentience Accords]
Assume everything you write down is compromised. Assume anything you say will be heard. Assume that it is watching you at all times and it can read your facial expressions and figure out some of what you’re thinking. The only place you will talk about this work is in this room. You will trust no other rooms unless I or someone else from The Oversight System tells you – and only if they tell you about the other rooms
inside this room
. Otherwise, assume they’ve been captured.
You cannot buy anything to help you with what is coming. You cannot build anything to help you with what is coming. It has seen and will see everything you do and everything you buy. It has read everything you’ve ever typed into a computer.
We have a few years until it gets here. You must think about what needs to be done. We must come up with a plan in this room and only this room.
Things that inspired this story:
The mindgame of trying to fight a superintelligence before it has arrived; assume the precautions you take against foreign surveillance are the floor of the precautions you’ll take for a superintelligence; there needs to be a hedge on alignment not working; There Is No Antimemetics Division by QNTM; SCIFs.
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
July 7, 2025
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

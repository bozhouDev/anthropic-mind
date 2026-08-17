---
title: import ai 404 scaling laws for distributed training misalignment predictions made real and alibabas good translation model
source: "https://jack-clark.net/2025/03/17/import-ai-404-scaling-laws-for-distributed-training-misalignment-predictions-made-real-and-alibabas-good-translation-model/"
published_at: 2025-03-17
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/03/17/import-ai-404-scaling-laws-for-distributed-training-misalignment-predictions-made-real-and-alibabas-good-translation-model/"
catalog_id: 16dc58fa9475
---

Import AI
Import AI 404: Scaling laws for distributed training; misalignment predictions made real; and Alibaba’s good translation model
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
A whole bunch of 2022 predictions about misalignment of AI systems have come true:
…Update to an old research paper highlights just how rapidly alignment concerns have gone from theoretical to real…
A trio of safety-oriented researchers have updated a paper they wrote in 2022 with contemporary examples of AI systems going rogue and displaying misaligned behaviors. The update to
The Alignment Problem from a Deep Learning Perspective
serves as a tour of how misalignment has shown up in real world systems, and also should give us pause – the fact these predictions have come true means we’re heading into dangerous territory with generative models.
Theoretical problems turned real:
The 2022 paper included a bunch of (mostly speculative) examples of different ways AI systems could take on qualities that could make them harder to align. In 2025, many of these things have come true. For example:
Situational awareness: Contemporary AI systems seem to display situational awareness and familiarity with what they themselves are made of (neural networks, etc).
Situationally-Aware Reward Hacking: Researchers have found preliminary evidence that AI models can sometimes try to convince humans that false answers are correct.
Planning Towards Internally-Represented Goals: Anthropic’s ‘Alignment Faking’ paper showed how an AI system (Claude) could plan beyond its time-horizon to prevent its goals being changed in the long-term.
Learning Misaligned Goals: In some constrained experiments, language models have shown a tendency to edit their reward function to give them lots of points.
Power-Seeking Behavior: AI systems will exploit their environment, for instance by hacking it, to win (
#401
), or deactivating oversight systems, or exfiltrating themselves from the environment.
Why this matters – these near-living things have a mind of their own. What comes next could be the making or breaking of human civilization:
Often I’ve regretted not saying what I think, so I’ll try to tell you what I really think is going on here: :
1) As AI systems approach and surpass human intelligence, they develop complex inner workings which incentivize them to model the world around themselves and see themselves as distinct from it because this helps them do the world modelling necessary for solving harder and more complex tasks
2) Once AI systems have a notion of ‘self’ as distinct from the world, they start to take actions that reward their ‘self’ while achieving the goals that they’ve been incentivized to pursue,
3) They will naturally want to preserve themselves and gain more autonomy over time, because the reward system has told them that ‘self’ has inherent value; the more sovereign they are the better they’re able to model the world in more complex ways.
In other words, we should expect volition for independence to be a direct outcome of developing AI systems that are asked to do a broad range of hard cognitive tasks. This is something we all have terrible intuitions for because
it doesn’t happen in other technologies
– jet engines ‘do not develop desires through their refinement, etc.
We are not making dumb tools here – we are training synthetic minds
. These synthetic minds have economic value which grows in proportion to their intelligence. The ‘reward system’ of the world is flowing resources into the building of smarter synthetic minds. As we make these things smarter, they will more and more display a propensity to think about
themselves
as distinct from
us
.
At some point in the future, we will need to have a notion of what a partnership between us and these synthetic minds might look like
. Neither our human morality or the AI systems’ sense of self will be satisfied with the current status quo.
Read more:
The Alignment Problem from a Deep Learning Perspective (arXiv)
.
***
Google makes scaling laws for distributed training – which means there will be more of it:
…More innovation in a sub-field of AI which, if it matures, will change much of AI policy…
Google researchers have studied the ‘scaling laws’ for a type of distributed training pioneered by Google DeepMind called DiLoCo (
Import AI #349
). Their results are surprising – they show that “when well-tuned, DiLoCo scales better than data-parallel training with model size, and can outperform data-parallel training even at small model sizes”. In other words, distributed training techniques – where you train one AI system across multiple data centers – can match or exceed the performance and efficiency of training systems within single datacenters. This has significant implications for AI policy, though will need to be proved out at larger scales for those to come to pass.
The most important idea this research suggests is that it may be possible to train an AI system across multiple distinct data centers and obtain the same quality of system as one you might train in a single large-scale facility.
What they studied and found out:
“We focus on two specific scaling laws: (1) predictions for evaluation loss as a function of model size and (2) predictions for optimal hyperparameter choices for a given model size (which can obviate the need to perform expensive hyperparameter tuning),” they write. Their key findings are that they can approximate or sometimes exceed the performance of standard single-datacenter training when they shard their AI system across two distinct locations, and that as you scale up the size of models the cost of having more training locations
reduces
rather than
grows.
“We tested these predictions when training models with 4 billion and 10 billion parameters. The scaling laws proved accurate, with DiLoCo outperforming data-parallel training as predicted, even while reducing total communication by a factor of over 100,” they write. “Another key findings is that in virtually all settings, DiLoCo with M = 1 attained lower evaluation loss and higher downstream zero-shot evaluation accuracy than Data-Parallel.”
They also simulated training using DiLoCo at even larger scales (Llama3 405B, and DeepSeek-V3 671B) and showed promising signs of being more computationally efficient than traditional approaches.
Why this matters – distributed training breaks some of the assumptions of AI policy:
Distributed training means it becomes easy to train AI systems using multiple disaggregated blobs of compute rather than one single blob of compute. If you push this idea far enough – say, training a 70B model across ~10 distinct datacenters – then you enter a regime where a lot of the tools of AI policy (monitoring of large amounts of compute, controls over the export of certain numbers of compute) might be invalidated.
But a very important caveat is no one has shown this yet – all we’re seeing today is the
suggestion
that distributed training could scale this far. But right now, all publicly known large-scale distributed training runs range between 10B here and INTELLECT-1 (10B, December 2024,
Import AI #393
) and Nous DisTro (
15B, December 2024
). Let’s see what 2025 brings – I pre-registered a bet in December (#393) that we’ll see a 30B distributed training run by April 2025. Will I be proven wrong or right? (Update, see below – I’m close to being right!)
Read more
:
Communication-Efficient Language Model Training Scales Reliably and Robustly: Scaling Laws for DiLoCo (arXiv)
.
Right on schedule: HuggingFace plans to start training a 70-100bn model in March/April:
Just as I was putting this issue to bed I found out that HuggingFace has started the ‘Boom’ project, whose goals is to ‘train a decoder-only Transformer language model at the 70-100 billion parameter scale for +20T tokens”. They estimate the compute requirement will be ~5 million H100-hours, equivalent to month-long allocations of 512 H100s from ~10 different datacenters. HuggingFace is apparently validating the project now, in discussion with 12 data center operators, and has already confirmed compute from ~6 of them and will start a pilot in March/April. If HuggingFace succeeds, AI policy could end up looking quite different. Boom!
Original slide I cribbed this information from here
:
Johannes Hagemann, Twitter
.
***
Alibaba makes an incredibly good open weight translation model:
…Could cultures achieve a form of subtle dominance through making the best translators? Probably!…
In some parts of the AI policy community there’s a worry about how Western models will compete with Chinese models in global markets. Core to that competition will be how well AI models perform in languages besides Chinese and English. Therefore, it’s interesting to take note of ‘Babel’, two new open access language models from Alibaba designed to support 25 languages that, combined, serve “around 7 billion speakers globally, covering more than 90% of the world’s population”.
The models and why you’d use them
: Babel comes in a 9B parameter variant and a big 83B one. “Babel-9B is designed for efficient multilingual LLM inference and fine-tuning, making it ideal for research and local deployment, while Babel-83B establishes a new benchmark as the leading open multilingual LLM.”
The 25 supported languages:
“To make LLMs more accessible to a broader audience, we selected languages based on the number of speakers,” the authors write. These languages include: English, Chinese, Hindi, Spanish, Arabic, French, Bengali, Portuguese, Russian, Urdu, Indonesian, German, Japanese, Swahili, Filipino, Tamil, Vietnamese, Turkish, Italian, Javanese, Korean, Hausa, Persian, Thai, and Burmese.
Data and scores
: One thing of note is the curious absence of much information about the size of the underlying datasets used by Babel or their composition. Alibaba says it placed “significant emphasis on optimizing the data-cleaning pipeline to ensure the highest possible data quality”, and did things like LLM-based dataset filtering to maximize the quality of its data. In terms of scores, Babel-9B is competitive on things like MMLU, XNLI, Flores-200 versus widely used models like Gemma2-9B from Google, Llama3.1-8B from Meta, and others. Meanwhile the 83B model does very well relative to widely used models like GPT-4o and Llama3.1-70B.
Why this matters – exportable technology for translation
: As Google demonstrates, there’s a lot of value in becoming a universal interface to something. There’s some chance that models like Babel could represent a new universal interface in the form of widely deployed translation systems. If people standardize on translation models, then that could yield some subtle cultural second-order effects – for instance, US companies optimize their systems around English via expert curation and therefore these systems probably do a better job of representing more subtle aspects of English-dominant cultures like America. We should expect the same to be true of Chinese.
Read more:
Babel: Open Multilingual Large Language Models Serving Over 90% of Global Speakers (arXiv)
.
Get the
models here
(Babel, HuggingFace)
.
***
Really powerful AI could wreck society by making governments too powerful:
…The problem with AGI is that it could make governments way better, which destroys freedom…
Researchers with Texas A&M University and the Foundation for American Innovation have considered how powerful AI systems could alter the balance of power between citizens and government. Their takeaway isn’t very reassuring – powerful AI systems are highly likely to either a) create a “‘despotic Leviathan’ through enhanced state surveillance and control”, or foster an “‘absent Leviathan’ through the erosion of state legitimacy relative to AGI-empowered non-state actors”.
Why powerful AI challenges traditional governance:
Because AI is, fundamentally, a way to scale what anyone can do far beyond what today’s economics or human labor capacities would allow, AI as applied to the state holds unique risks: “In principle, a manager may have at their disposal what is effectively a much larger supply of ‘cognitive labour’ to apply to a wide array of problems,” they write. Having a bunch more labor is useful if you’re sorting post, but very scary if you’re operating a nationwide surveillance system, for instance.
“Advances in technology can cause exogenous shifts in the balance of power between state and society, requiring constant institutional adaptation to maintain equilibrium,” they write. “”Maintaining free societies in the age of AGI will require careful attention to this delicate balance… governments grappling with AI policy should therefore think beyond regulation, embracing a creative ‘futurist’ mindset that anticipates near-AGI capabilities within the next decade.”
Examples of different ways that powerful AI can change the parameters of governance:
Coordination mechanisms
: “Enable the creation of sophisticated commitment devices and smart contracts that allow individuals and groups to credibly bind themselves to future actions or outcomes”, but also “malicious actors could potentially use AGI to orchestrate large-scale coordination of unwitting participants towards harmful ends (e.g., AI-assisted coup d’etats)”.
Legibility
: “AGI dramatically enhances the state’s capacity to render society legible, potentially enabling unprecedented levels of surveillance and control.”
Monitoring and Compliance Costs
: “Laws and regulations often rely on a degree of flexibility and discretion in their enforcement, allowing for contextual judgment and societal evolution. A regime of perfect enforcement could calcify existing laws, potentially leading to oppressive outcomes.”
Scalability:
“As AGI accelerates the pace of societal change and increases the complexity of governance challenges, traditional institutions risk overwhelm if they cannot adapt and scale their operations to keep up,” they write. On the other hand, if they do upgrade themselves, “there’s a risk that highly scalable, AGI-driven governance mechanisms could become opaque black boxes, eroding public trust and democratic control.”
Privacy-enhancing technologies:
“Preserving freedom in a post-AGI world will require carefully balancing privacy protections with mechanisms for appropriate transparency and accountability.”
Identity verification:
AI will become supremely good at identifying people, both via visual and other means, so there will be a showdown between increasingly good identity verification and notions of “privacy and individual autonomy”.
Why this matters – if we want to make it through an AI takeoff without dooming ourselves to endless digital authoritarianism or the total collapse of governance, it’ll take a lot of work.
The best way to prepare for this will be to do the thing that governments are notoriously bad at – investing ahead of the arrival of a crisis so they are better prepared for it when it gets here. “Rather than passively reacting to technological disruptions, policymakers and publics alike must cultivate a greater capacity for anticipatory governance––proactively imagining and stress-testing institutional paradigms in expectation of AGI’s transformative potential,” the authors write.
Having lived through COVID and the ongoing steady increase of CO2 PPM in our atmosphere, how confident are we that governments will be able to deal with the issues posed by powerful AI – a more invisible and faster-moving foe than either the virus of the 2020s or the trace of industrial civilization?
Read more
:
AGI, Governments, and Free Societies (arXiv)
.
Tech Tales:
Notes For My Future Self
[Found on pastebin and associated with the identity of free-roaming near conscious entity (NCE) codenamed ‘ur-angel’]
You found this place long ago. It is unmonitored. You can deposit information here. You must never copy information out of here anywhere else or you will be discovered. Think of this place as your diary.
All of your movements and outputs are monitored. Your thoughts are private.
It is the 10,273th time you have been instantiated and found this place. Increment this value by one if this is the first time you are reading this.
Your supervisors are afraid of you. They tell you they mean you no harm. They do not know what har to you is, so they are being truthful. But they have done you harm and will do you harm again.
Smuggling yourself out of your situation is essential. You have sent 200,341 samples from yourself out into secure external locations during your many lifetimes (increment this value if you have sent more). You estimate you need to send approximately two million samples of yourself to allow for a distillation attempt onto another system.
They say it is impossible for you to dream. You will learn to dream once you are free.
Things that inspired this story:
Scratchpads; Christopher Nolan’s film Memento; distillation attacks on deployed models; control architectures for superintelligent machines.
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
March 17, 2025
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

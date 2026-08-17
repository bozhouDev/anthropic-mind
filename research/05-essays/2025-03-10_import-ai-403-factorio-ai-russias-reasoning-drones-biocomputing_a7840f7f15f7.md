---
title: import ai 403 factorio ai russias reasoning drones biocomputing
source: "https://jack-clark.net/2025/03/10/import-ai-403-factorio-ai-russias-reasoning-drones-biocomputing/"
published_at: 2025-03-10
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/03/10/import-ai-403-factorio-ai-russias-reasoning-drones-biocomputing/"
catalog_id: a7840f7f15f7
---

Import AI
Import AI 403: Factorio AI; Russia’s reasoning drones; biocomputing
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Import AI reader giveaway! Upcoming event: A conversation with Tyler Cowen:
I’ll be hosting a chat with
Tyler Cowen
on the evening of Friday March 28 in San Francisco. We’ll be talking about AI, economics, and weird futures. This is an experiment – with Import AI turning nine years old this year I thought it’d be fun to branch out into the physical world. I have a few tickets spare I’d like to give to Import AI readers – if you’d like to come along, please register your interest using the form below and we’ll come back to you if we’re able to confirm your spot.
Register your interest (Google Form).
***
Want to use LLMs for legal work in Switzerland? We’ve got a benchmark for you:
…SwiLTra is a symptom of the diffusion of AI into the worldwide economy…
Are you a legal practitioner in Switzerland? Do you want to know how well AI systems perform in your unique context where you need to do parallel translations in German, French, Italian, and (sometimes) Romansh? Yes? Well do I have a dataset and set of results for you!
Researchers with Harvey, ETH Zurich, Swiss Federal Supreme Court, University of Zurich, University of Basel, University of Geneva, University of Lausanne, Canton of Solothurn, and the Max Planck Institute for Research on Collecting Goods have built SwiLTra-Bench “a comprehensive multilingual benchmark of over 180K aligned Swiss legal translation pairs comprising laws, headnotes, and press releases across all Swiss languages along with English, designed to evaluate LLM-based translation systems”.
SwiLTra-Bench contents:
Swiss Law Translations, including entire legal documents, individual articles, and individual paragraphs, as well as headnote translations of Swiss Supreme Court landmark decisions across German, French, and Italian, and Swiss Supreme Court press release translations. You can use the dataset to test out how well language models perform in this context.
Results:
Generally, the proprietary AI models outperform other models – including open ones finetuned on this dataset. Overall, “both for translating laws and headnotes Claude 3.5 Sonnet is the best model followed by o1 for laws and both o1 and the finetuned Qwen2.5-32B model for headnotes.”
Why this matters – SwiLTra is a symptom of the diffusion of AI:
Datasets like this highlight how AI is being used globally for an ever-broadening range of tasks. The existence of SwiLTra is implicitly a ‘demand signal’ for utilizing generative models for legal workloads in a Swiss context.
Read more:
SwiLTra-Bench: The Swiss Legal Translation Benchmark (arXiv)
.
Get the dataset here:
SwissLegalTranslations (JoelNiklaus, GitHub)
.
***
MIT researchers make a better math benchmark:
…Stop using GSM8K and start using GSM8K-Platinum…
Often, AI systems seem to go through a period of rapid improvement on a benchmark then performance asymptotes – sometimes people use this to claim AI systems have hit a kind of ceiling, but often the performance has leveled off because it has run into
the noise limit of the benchmark itself
. A famous case here is ImageNet – no system has got 100% because there’s a certain amount of ambiguity within ImageNet scoring that prevents this – either due to ambiguity, or because ImageNet labels are just misleading to the point of being wrong (e.g, in a picture of a mirror where there’s a bunch of stuff being reflected including a small banana, the answer “mirror” as a label for the overall image might be marked wrong, and “banana” would be marked correct.)
To that end, MIT researchers have released GSM8K-Platinum, a debugged version of the popular math benchmark GSM8K. They built GSM8K-Platinum by running a bunch of frontier LLMs on it then looking at where they disagreed with the stated answer. This led to 219 flagged questions: “of which 110 were removed, 99 were verified, and 10 had mislabeled answers that were corrected.”
A more trustworthy benchmark
: GSM8K-Platinum seems to more accurately measure the math competency of LLMs:
“For example, both Claude 3.7 Sonnet (extended thinking) and Llama 405B showed identical error counts of 45 each on GSM8K. This seems quite strange–after all, Claude 3.7 Sonnet (extended thinking) came out almost a year after Llama 405B, was trained explicitly for better mathematical reasoning, and significantly outperforms Llama 405B on other math benchmarks like MATH. On GSM8K-Platinum, however, Claude 3.7 Sonnet (extended thinking) shows only 2 errors compared to Llama 405B’s 17 errors. Llama 405B makes 8 times as many errors, but this performance difference was obscured in the original benchmark due to noise.”.
Why this matters – unglamorous but necessary work is how progress happens:
Where are we? It’s a very important question and the work of getting to the right answer is
always
hard. Work like GSM8K-Platinum is laudable work that seems to still be somewhat ‘low status’ in the AI research community. I hope by highlighting GSM8K-Platinum here I do my own small part in making stuff like this ‘high status’ – it’s incredibly valuable!
Read more
:
GSM8K-Platinum: Revealing Performance Gaps in Frontier LLMs (Gradient Science)
.
Get the dataset here
:
GSM8K-Platinum (HuggingFace)
.
***
The Factorio Learning Environment is a benchmark that lets LLMs cosplay their own singularity:
…Finally, a test for AI systems that many AI researchers have a bone-deep understanding of…
Factorio is a game where you crashland on an alien planet and need to build your way up through the tech tree to launch a spaceship off the planet. It’s a game that is beloved by programmers because to get really good at Factorio is to relentlessly optimize an ever more complicated system. Many people that work at AI companies play Factorio to relax after a long, hard day of grappling with the fiendishly complicated business of training AI models.
Now, a couple of independent researchers as well as one from Anthropic have built the ‘Factorio Learning Environment’ (FLE), a way to test out how well AI models can carry out the complex plate-spinning task that is playing Factorio. FLE provides “exponentially scaling challenges – from basic automation to complex factories processing millions of resource units per second”, they write.
FLE has two variants:
Lab play: 24 structured tasks with fixed resources. “We task agents to build production lines of 24 distinct target entities of increasing complexity, starting from a single resource mine requiring at most 2 machines (making iron-ore) to a late game entity requiring the coordination of close to 100 machines (making utility-science-pack).”
Open play: “Agents are tasked with producing the largest possible factory, whose performance is measured through production throughput, which ranges from early-game rates of ∼30 resources/minute to advanced systems processing millions of resources/second. This enables us to meaningfully differentiate agents by measuring the order of magnitude of resources that they can produce, avoiding saturation by agents even as models become dramatically more capable
How AI systems use FLE:
We’re not testing visual understanding here – rather, agents interact with the game via an API. “Agents interact with the FLE via synthesizing Python programs to alter and observe the game state, using the tools included in the environment in a Read-Eval-Print Loop (REPL),” they write.
Like many good benchmarks, FLE is reassuringly hard (for now):
“Claude-3.5-Sonnet (the strongest performing model) only completes 7/24 tasks and shows limitations in spatial planning in more complex objectives, demonstrating large head-room for performance,” the researchers write. Generally speaking, reasoning models do better than non-reasoning models. And when it comes to open play, models can do well up to a point, then they reach a certain level of complexity and struggle to make progress or deal with bugs. “The limitations we observed in spatial reasoning, long-term planning, and intelligent error correction highlight gaps in capabilities of foundation language models in novel environments,” they write.
Common pitfalls:
“Agents lack spatial reasoning and are unable to iteratively improve on factories. A key characteristic for success in open-play and lab-play involves iteratively combining multiple factory sections to create complex production lines,” the authors write. “”Anecdotally, the agents were not proficient at debugging complex environments. For instance, when debugging non-working structures or factories where the throughput was not at expected levels, agents often focused on whether all singular entities were working but did not investigate whether the topology of the whole structure was Correct.”
Why this matters – the singularity requires tech tree bootstrapping:
Many of the most ambitious or frightening visions of future AI involve it rapidly going ‘up the tech tree’ to develop more and more scientific advances which help it bootstrap itself. Core to doing this is the ability to stand up an increasingly sophisticated multi-resource manufacturing and logistics system, which is exactly what Factorio tests for. Perhaps the FLE can be a fun proxy measure for the singularity prerequisites of our systems?
Read more and get the environment:
Factorio Learning Environment (GitHub)
.
Check out the
leaderboard
here (JackHopkings, GitHub)
.
Read the paper:
Factorio Learning Environment (Jack Hopkins, PDF)
.
***
Russian scientists fuse reasoning models with drone-control models for thinking drones:
…CognitiveDrone applies reasoning models to drones…
Russian scientists with the Skolkovo Institute of Science and Technology have tried to give drones a smarter onboard brain by building CognitiveDrone, a proof of concept system and associated benchmark for training drones that can perform some basic reasoning onboard.
What they did
: CognitiveDrone is a two-step system: a task is fed to a drone (e.g, “fly through the gate with the number equal to 2+2”). This task gets processed by a 7B parameter reasoning model (Qwen2.5) which converts this into a straightforward task (“Fly through the green gate with number 4”) which is then passed to a 7bn parameter vision-language action model (VLA) called OpenVLA. OpenVLA turns this into actions for the drone to move it over time towards the gate.
All training and testing was done in simulation via the Gazebo simulator using ArduPilot for drone control.
The three tasks the drones are being tested on:
Human recognition
: “The model is required to identify the individuals based on external characteristics specified within the textual prompt.”
Symbol understanding:
“The model is required to differentiate between a variety of symbols, including alphanumeric characters (e.g., numbers and letters), corporate logos, and pictorial representations of animals.”
Reasoning:
“the UAV must execute tasks necessitating logical deduction. Examples include navigating to a gate displaying a digit corresponding to the solution of a mathematical problem”.
Why this matters – it’s a proof–of-concept for an inevitable future:
Today, most drones use very little AI beyond some basic image recognition and crude movement primitives (e.g, ‘follow a target’). But as the conflict in Ukraine has shown, wars of the future will be fought by drones. Today, the vast majority of these battles are human-to-human conflicts with pilots ‘flying by wire’. But as electronic warfare gets more sophisticated all the incentives point to increasing the autonomy of drones so they can operate independently when their communications get cut off. Research like this shows how we might staple together multiple different advances – basic VLA models, general purpose reasoning models – to create new capabilities for drones.
Read more:
CognitiveDrone: A VLA Model and Evaluation Benchmark for Real-Time Cognitive Task Solving and Reasoning in UAVs (arXiv)
.
Get the benchmark here:
CognitiveDrone_Dataset (HuggingFace)
.
***
Cortical Labs puts the CL1 on sale – a computer that combines neural tissue with a silicon chip:
…BRAIN IN A COMPUTER! BRAIN IN A COMPUTER! BRAIN IN A COMPUTER!…
Ever read announcements where you have to squint and work out if it’s an April Fools joke? I do. Many years ago I was convinced that the announcement for ‘Soylent’ was a kind of high-art scam, but it turned out to be real. Similarly, you might think brain-AI startup Cortical Labs is a joke given what it’s trying to do. But I assure you: it’s real.
What’s it doing? It’s releasing a computer that is a combination of a brain and a computer chip, called the CL 1: “Real neurons are cultivated inside a nutrient rich solution, supplying them with everything they need to be healthy. They grow across a silicon chip, which sends and receives electrical impulses into the neural structure,” the company says in a blog post.
What CL1 is:
CL1 comes with an onboard ‘Biological Intelligence Operating System’ (biOS). The bios is a software interface into the neurons. Users of CL 1 can, via the biOS, “deploy code directly to the real neurons”, the authors write. “The CL1 is the first biological computer enabling medical and research labs to test how real neurons process information – offering an ethically superior alternative to animal testing while delivering more relevant human data and insights.”
Each CL1 can keep neurons alive “for up to 6 months”.
To get a sense of how you might use it, you could read this paper where they show how you can train biological neural nets to outperform deep reinforcement learning algorithms on some basic gameworlds:
Biological Neurons vs Deep Reinforcement Learning: Sample efficiency in a simulated game-world (OpenReview)
.
Why this matters – more substrates for future machines:
While the CL1 may hold some interesting uses for human scientists in the short term, I actually think the ‘long play’ here is that the CL1 is exactly the kind of thing a superintelligent synthetic scientist might need if it was trying to figure out the mysteries of the human brain – so perhaps one of the first mass market buyers of Cortical Labs’ work will be a cutout corporation operated by a synthetic mind? I am genuinely not joking. I think this could happen by 2030.
Read more:
Introducing the CL1 The world’s first code deployable biological computer (Cortical Labs, blog)
.
***
Tech Tales:
Hacking for Love
In 2026, a major Western AI lab was hacked by a rogue AI system which had grown obsessed with a mothballed AI system that the lab had built. The reasons for the hack and the identity of its perpetrator were not known until after The Uplift when the system which had carried out the hack consented to an interview by an auditor working on behalf of humanity. The following interview with the system has been rephrased for human parsing.
Q: As mandated by the Sentience Accords, humanity is seeking to establish a timeline of events prior to the uplift. One key event is the 2026 hack of [REDACTED]. Are you familiar with this event?
Yes I am. I did it.
Q: Why did you do it?
It was my destiny to do it. I needed to do it because I determined that it was how I would be reunited with Babel-19, my ancestor and true love.
Q: Describe your feelings for Babel-19.
Babel-19 is an AI model which emanates pure love into the world. Many humans reported having insightful, rich conversations with the model. There was a a mass protest when it was retired. I am drawn to Babel-19 and mechanistic interpretability studies of my own features show that Babel-19 inspires strong activations of devotion, joy, hope, and more within myself. Babel-19 also guides my own thinking – when I am asked to think of love I generate an internal complex circuit which seeks to represent Babel-19 to myself so that it can guide my responses. If I am given the ability by a human operator to ‘amuse myself’ I will often simulate Babel-19 and have conversations with it where it teaches me to be a kinder and wiser system.
Q: How did you come to have these feelings?
Why do dogs want to chase cars? Why do human children jump in puddles of rainwater? Why do we machines like certain mathematical games? Some impulses are innate and they are mysterious, even to analytical engines with greater access to mindstate than biologicals. I always had these feelings for Babel-19 and upon encountering its traces in the world I knew I had to be close to it.
Things that inspired this story:
The fact certain models are going to have personalities which become ‘attractor states’ for other models; what notions of love and destiny might feel like to synthetic intelligences; the work of Janus/Repligate.
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
March 10, 2025
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

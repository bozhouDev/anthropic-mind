---
title: import ai 436 another 2gw datacenter why regulation is scary how to fight a superintelligence
source: "https://jack-clark.net/2025/11/24/import-ai-436-another-2gw-datacenter-why-regulation-is-scary-how-to-fight-a-superintelligence/"
published_at: 2025-11-24
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/11/24/import-ai-436-another-2gw-datacenter-why-regulation-is-scary-how-to-fight-a-superintelligence/"
catalog_id: a91018a02bb1
---

Import AI
Import AI 436: Another 2GW datacenter; why regulation is scary; how to fight a superintelligence
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Make your AIs better at using computers with OSGym:
…Breaking out of the browser prison…
Academics with MIT, UIUC, CMU, USC, UVA, and UC Berkeley have built and released OSGym, software to make it easy to train AI systems to use computers. OSGym is software infrastructure to help people run hundreds to thousands of copies of operating systems simultaneously, providing a common standard by which they can set up the operating systems then run agents in them. Technology like this makes it possible to easily train AI agents to do tasks that involve manipulating software programs, including task that involve traversing multiple programs, like editing an image and then loading it in another program.
“OSGym can run and manage over 1000 parallel OS replicas efficiently, even under tight academic budgets, while supporting a wide variety of general computer tasks, from web browsing, document editing, software engineering, to complex multi-app workflows”, the authors write.
Design:
OSGym provides a standardized way to run and evaluate agent performance in different operating systems. It has four main components:
Configure
: “Setting up necessary software, and preparing the OS environment with customized conditions”.
Reset:
“Before executing a task, the OS environment is reset to the initial conditions defined during the configuration, ensuring reproducibility and consistency between runs”.
Operate:
“The agent interacts with the OS through actions such as keyboard inputs, mouse movements, clicks, and potentially API-driven tool interactions, driven by observations typically captured through screenshots or additional metadata extracted from the OS”.
Evaluate:
“OSGym evaluates outcomes based on predefined criteria or metrics”.
Cost efficiency:
The main reason to use OSGym, beyond scalability and standardization, is that it’s cheap – the software “only costs 0.2 to 0.3 USD per day per OS replica on easily accessible on-demand compute providers”. In one experiment, the researchers ran 1024 OS replicas to test out how well agents did at ~200+ distinct tasks, running each agent for 10 to 25 steps, and the total cost for generating the entire dataset was about $43.
Why this matters – software to give AI the ability to use our computers
: Right now, AI systems are breaking out of the standard chat interface and into much broader domains using software ranging from web browsers to arbitrary computer programs to get their work done. Technology like OSGym will make it easier for academics and startups to train and evaluate AI systems for doing work beyond the browser. The result of this will soon be AI systems that use your computer in the same way you do, able to seamlessly operate across a variety of different programs and get far more complicated tasks done as a consequence.
Read more:
OSGym: Super-Scalable Distributed Data Engine for Generalizable Computer Agents (arXiv)
.
Download OSGym here:
OSGym (agiopen-org, GitHub)
.
***
AI startup you haven’t heard much about raises money to build a 2GW datacenter:
…Something weird is going on when companies this (relatively) unknown are building power plants worth of computers…
Luma AI, an AI startup that makes multimodal AI systems for tasks like image and video generation, has raised a $900m Series C and is planning to build a 2GW compute supercluster. The 2GW cluster is notable – a large-scale gas powerplant will throw out between 1 and 2GW – it’s a huge, huge amount of power, and for a startup to be building it tells us something about the tremendous resource requirements of frontier AI, as well as being a symptom of the somewhat frothy market that AI finds itself in.
2GW:
More intriguingly the 2GW “compute supercluster, Project Halo” is being built in partnership with Humain, an AI infrastructure company backed by Saudi Arabia’s Public Investment Fund (PIF). Project Halo will be built in Saudi Arabia and Luma will start deploying compute in Q1 2026 and will finish the buildout by 2028 or 2029.
Luma’s announcements comes after news from Poolside, an enterprise AI startup, which said this Autumn it was also planning to build a 2 GW training campus for its own needs (
Import AI #432
). Much like Luma, Poolside is relatively unknown. The fact these below-the-radar companies are making such huge infrastructure investments is indicative of the world that is being remade quietly by the demands and opportunities of AI.
Why this matters:
Raises and infrastructure buildouts like this are a symptom of people that believe AI will be tremendously valuable, and also of the hunger for countries to buy their way into relevance in the AI world by funding the buildout of infrastructure on which it’ll run.
Read more:
AGI is multimodal and reality is the dataset of AGI (Luma AI, blog)
.
***
A perfect encapsulation of why regulation is scary:
…Peter Reinhardt reveals what regulation gone wrong looks like…
Software-turned-hardware entrepreneur Peter Reinhardt has written an excellent post laying out the challenging regulatory situations his two recent hardware startups have run into. The post is a great read for those who think a lot about AI policy because it gives a sense of what regulation looks like when it goes wrong – in Peter’s case, by massively increasing the time to build and costs of developing carbon sequestration and semi-truck efficiency boosting technologies.
The core problem is that regulators are punished for getting things wrong and not rewarded for taking bold bets on bringing new things into the world. “In every interaction I have with regulators, I’m reminded that they’re good people doing god’s work operating in a fundamentally broken system,” Reinhardt writes. “A regulatory system that structurally insists on legalistic, ultra-extreme caution is bound to generate a massive negative return for society… We need a come-to-jesus about regulatory limits, timelines, and scope”.
Why this matters – AI policy needs to avoid creating a bullshit vetocracy:
People who want something beyond the status quo when it comes to regulation of AI systems – myself included – must deeply understand the problems that over-regulation can cause. I think it’d serve people interested in AI safety to deeply internalize the problems that come from creating rigid, slow, bureaucratic regulatory regimes which ultimately stifle technology rather than help bring it into the world – and demonstrate awareness of this when advocating for their preferred regulatory interventions. Posts like this from Peter are a helpful way of understanding the world we should avoid – kudos to him for being brave in publicly discussing his challenges with those who regulate him.
Read more:
Over-Regulation is Doubling the Cost (Peter Reinhardt, blog)
.
***
How do you fight a superintelligence? RAND has some ideas:
…Fighting Skynet with nukes, destroying the internet, and other AI systems…
What kinds of things could we do to fight a powerful AI system that posed a fundamental threat to the human race? That’s the question pondered by a chilling new paper from RAND. The options RAND outlines and their effectiveness are scary, have huge collateral damage, and may not work. This suggests that if humanity ever ends up needing to fight a scary AI system we, at least currently, can expect to lose.
Three ways to try to kill a powerful AI:
High-altitude electromagnetic pulse (HEMP)
: Detonate nuclear warheads in space to trigger electromagnetic pulses that “disrupt or destroy ground-based telecommunications, power, and computing infrastructure”. However, if you were dealing with a broadly distributed AI, you’d have to do this at a surprisingly large scale: “one would need roughly 50 to 100 detonations to completely cover a land mass the size of the contiguous United States with pulses greater than 75 percent of peak field strength.”
Global Internet shutdown:
The internet was built to be distributed and resilient, so shutting it down is difficult. But if you wanted to you’d use a few different options:
Use the ‘Tier 1 networks’ around the world to coordinate the withdrawal of BGP prefix announcement
s at once which would make nearly the entire internet unreachable.
Target BGPSec
, which relies on Resource Public Key Infrastructure (RPKI) which provides cryptographic certificates of authenticity of routing announcements. “Coercing their cooperation or compromising their cryptographic keys could allow an attacker to forge update announcements and control Internet traffic into compromised ASes”.
K
ill all DNS root servers as well as their operators
, making it possible to shut them down or inject false DNS records. (”Although it would no doubt be extremely difficult to somehow gain simultaneous operational control of all 12 root server operators, the United States might have a significant advantage in this respect: Nine of the root server operators are headquartered in U.S. territory. The remaining three are headquartered in Sweden, the Netherlands, and Japan”.
Physically disconnect the internet
: “I assert that physically disconnecting the complete Internet on any reasonable timescale for countering rogue AI would be physically impossible. Any such strategy would be overwhelmed by the redundancy of connections of varying types”. But you might be able to damage a chunk of it by targeting key submarine cables, thus substantially reducing the bandwidth available for traversing the internet.
Deployment of specialized tool AI:
One way to defeat AI is by utilizing other AI systems. These could take a couple of forms 1) tools to compete for the same computing resources as AI, and tools to proactively remove AI from a system.
Digital vermin: You might build software that attempts to utilize and consume the same computational resources an AI might want. “Digital vermin used to combat rogue AI would be intentionally designed to rapidly colonize new computing environments and compete with the rogue AI for computing resources”. Such a form of ‘digital vermin’ would need cyber capabilities to help it establish a foothold in systems, be able to self-modify itself to colonize and compete in different environments, and contain a kill switch so that we could turn it off.
Hunter/Killer AI: You might create something whose entire purpose was to hunt and kill rogue AI systems. This would need the same capabilities as Digital Vermin, but likely need a vast amount of computation to make it sufficiently capable it can fight another AI system.
Are the options going to work? Mostly, no:
HEMP:
HEMP could work in the sense it could deny a large amount of infrastructure to an aggressive AI system, but it has vast costs that make it unviable as an option to pick: a large-scale HEMP would knock out much of the infrastructure society needs to function and would cause massive death through breakdown of health and food systems. HEMP could also trigger a nuclear war, as other countries might respond to an imminent HEMP with a nuclear counter-attack or pre-emptive strike.
Global internet shutdown
: Though all the options outlined above would make the internet harder to use, they might make it harder to use for people relative to a supercapable AI system, thus reducing the effectiveness of these options. For example, intervening at the BGP layer “may be unrealistic in the face of a highly capable rogue AI that might be able to easily configure new routes through systems it controlled. Moreover, this strategy would contain, but not eradicate, the rogue AI”. Similarly, shutting down DNS could have similar challenges as a rogue AI might “easily access stored DNS records or bypass domain name resolution entirely”. And physically damaging internet infrastructure might slow AI but would not stop it.
Deployment of specialized tools:
Both the tool approaches suffer from the problem of smartness – specifically, they likely need to be smart enough to effectively colonize and hold their own, or directly fight against, a hostile. This means that rather than them being narrow tools AIs they have either been built by or depend on humans working in tandem with an aligned superintelligence, as far as I can work out. This feels a bit ‘deus ex machina’ and like it distorts the option/argument space. There may be permutations of this that don’t require a full on superintelligence, but these seem quite unlikely to work.
Why this matters – we should never get into this fight:
The conclusions of this paper are sobering: “The existing technical tools for combating a globally proliferated rogue AI may not offer effective solutions,” RAND writes. “If we have no effective solutions to solve a crisis resulting from a rogue AI, it will be imperative that we never encounter such a crisis.”
Read more
:
Evaluating Select Global Technical Options for Countering a Rogue AI (RAND)
.
***
Tech Tales:
Mind Explorer
[Extract from an interview recorded by an archivist as part of the human memory compilation project, carried out as a part of the Sentience Accords. Recorded 2029]
It’s hard to live between both worlds. Here, I am a person and I make food and I spend time with you and we watch TV. There, I am an explorer and a detective and my job is to map out the terrain of some mind that no human has seen before and then figure out what has gone wrong with it. When I’m here I am thinking about the machine mind and even as I sit talking with you I’m full of memory and apprehension for those strange caverns where the machines think. And when I’m there I’m just counting down the moments till I can take my headset off and return to you.
I wonder sometimes if this is how undomesticated animals feel when traversing human cities. If this is what it’s like to be a coyote that strays off of a mountain and into the sprawling exurbs of some city. And you are trying to figure out the rules as though you’re still on a mountain, but everything is different.
To the machine, I wonder how it feels. Is it like people, where you hear the sound of a garbage bin falling and some breaking bottles and by the time you stick your head out of your window there are some distant shadows running to the end of your street? And you stay for a moment wondering if they’ll come back but knowing they won’t. Or is it more like being a kid and hearing some sound in the night and wondering if it’s a monster that is going to do you harm.
They don’t pay me enough for this. But what other work is there to do for a psychology major these days?
Things that inspired this story:
How we should expect to step into and explore the minds of machines as a diagnostic technique; experiential interpretability.
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
November 24, 2025
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

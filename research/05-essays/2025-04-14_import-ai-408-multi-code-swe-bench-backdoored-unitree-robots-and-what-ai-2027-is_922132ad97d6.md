---
title: import ai 408 multi code swe bench backdoored unitree robots and what ai 2027 is telling us
source: "https://jack-clark.net/2025/04/14/import-ai-408-multi-code-swe-bench-backdoored-unitree-robots-and-what-ai-2027-is-telling-us/"
published_at: 2025-04-14
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/04/14/import-ai-408-multi-code-swe-bench-backdoored-unitree-robots-and-what-ai-2027-is-telling-us/"
catalog_id: 922132ad97d6
---

Import AI
Import AI 408: Multi-code SWE Bench; backdoored Unitree robots; and what AI 2027 is telling us
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
German researchers find undocumented backdoor in Unitree robots:
…Exactly the kind of thing a superintelligence would want to exploit during a hard takeoff…
German security firm ‘Think Awesome’ has analyzed the Unitree Go1 quadruped robot dog and found an undocumented backdoor which lets people tunnel into any of these dogs and view their camera feeds. “Unitree did pre-install a tunnel without notifying its customers. Anybody with access to the API key can freely access all robot dogs on the tunnel network, remotely control them, use the vision cameras to see through their eyes or even hop on the RPI via ssh,” the researchers write. “These robot dogs are marketed at a wide spectrum of use-cases, from research in Universities, search and rescue missions from the police to military use cases in active war. Imagining a robot dog in this sensitive areas with an active tunnel to the manufacturer who can remotely control the device at will is concerning.”
Why this matters – this is the kind of technology an unaligned AI would use for malicious purposes:
As the report makes clear it’s genuinely unclear if this backdoor was placed in at the behest of the Chinese state or for a more mundane purpose (e.g, maybe this was a mothballed control interface for the robots originally designed for sale within the Chinese market).
I think the larger interesting thing here is contemplating the implications of this backdoor for an unaligned superintelligence – lots of sci-fi-esque “AI safety gone wrong” theories rely on the idea that at some point an unaligned AI will take actions in the physical world by hijacking robots. The undocumented Unitree backdoor described here is
precisely
the kind of thing an AI would need to use to jump into the physical world. Imagine how many other things like this exist across the various drones and robots sold today?
Read the report here:
Unitree Go 1- Who is speaking to my dog? (Think Awesome site)
.
***
ByteDance moves beyond Python with a solid multi-programming-language eval:
…Multi-SWE-bench lets us test LLM performance on 7 programming languages…
ByteDance has released Multi-SWE-bench, a benchmark for testing out how well LLMs can program in different languages. Multi-SWE-bench is inspired by SWE-bench, a Python-based coding benchmark which has quickly become the de facto gold standard for testing out how well AI systems can program.
Key details:
Multi-SWE-Bench ships with 1,632 challenges split across 7 languages: Java, TypeScript, JavaScript, Go, Rust, C, and C++. The challenges are taken from real pull requests from popular GitHub repositories, just like with SWE-bench, which means the problems correlate to the kinds of real world programming tasks we can expect AI to be used for.
How well do frontier systems perform?
ByteDance tests out popular LLMs from OpenAI, Anthropic, DeepSeek, and Alibaba on the benchmark – the results show that while many systems do extremely well at Python their performance falls off in other languages. In addition, performance is distributed unevenly cross other languages, with TypeScript and JavaScript seeming quite challenging.
Why this matters – another useful view of AI progress:
Multi-SWE-bench has all the hallmarks of a good evaluation – it’s based on real world problems, it’s difficult for today’s systems, and it comes with some natural calibration where we can compare results on this to SWE-bench. I predict we’ll see significant and sustained improvements on the benchmark in the coming year, and I’d anticipate the variability across different languages will reduce as systems scale in capability.
Read more:
Multi-SWE-bench: A Multilingual Benchmark for Issue Resolving (arXiv)
.
Check out the
leaderboard
here (Multi-SWE-bench, leaderboard)
.
Get the code
for
running the benchmark here (Multi-SWE-bench, GitHub)
.
***
Microsoft stuffs Quake into the weights of a neural network:
…When the magical becomes the mundane…
Microsoft has built a version of Quake which is instantiated as the weights of a neural network, letting you play a trippy version of the 90s shooter classic. You can play
a demo of the game online
. Playing the game is interesting because it feels like a slightly laggy version of the original game, albeit with odd hallucinations and things that seem to come into and out of focus almost randomly. This would be dissatisfying if it was a traditional game, but if gets much more interesting when you consider that what you’re playing isn’t a traditional piece of software but rather a generative model that lets you move around inside the representation of a single coherent gameworld.
By this point, this isn’t even that unusual! That Microsoft demo follows an earlier online demo from a startup where you could play Minecraft implemented in the same way (
Import AI #390
).
You can get a feel for how viscerally all of this technology has advanced by playing the Quake demo, then going and checking out the state of the art in
neural world modeling in 2018
(
Import AI #88
) by checking out this early work building a world model for Doom and a racecar game.
Why this matters – everything will be captured inside the mind of the eventual machine
: In the future, games consoles might just be interfaces to a giant neural network which contains representations of many different games inside it, and which allows you the player to compose new games on-the-fly by linking different features together. I expect we’ll have this by the end of the decade.
Play the demo here
:
Copilot Gaming Experience (Microsoft)
.
***
Automated dead-end discovery with the AI Scientist-v2:
…If we can automate null result discovery, can we automate science advances as well?…
Researchers with Sakana AI, the University of Oxford, and the University of British Columbia have refined their ‘AI Scientist’ system so it can propose and run more ambitious experiments. As a demonstration of the expanded capabilities of the AI Scientist Sakana entered three of its “fully autonomous manuscripts” to an AI conference workshop and one of the papers got a high enough scores to be accepted.
What they did:
Sakana released the first version of the AI Scientist in summer 2024 (
Import AI #383
). The AI Scientist-v2 is less a single big theoretical advance and more a bunch of good ideas that have been integrated together – the new system “eliminates the reliance on human-authored code templates, generalizes effectively across diverse machine learning domains, and leverages a novel progressive agentic tree-search methodology managed by a dedicated experiment manager agent,” the authors write. “Additionally, we enhance the AI reviewer component by integrating a Vision-Language Model (VLM) feedback loop for iterative refinement of content and aesthetics of the figures”.
But are its research ideas actually good? Not really:
The AI Scientist isn’t yet generating particularly transformative or meaningful insights. The manuscript which got into the ICLR workshop “achieved an average reviewer score of 6.33 (placing it roughly in the top 45% of submissions)” – this isn’t very good, and workshops are a lot easier to get papers into than the main conference. “The current version of The AI Scientist-v2 does not yet consistently reach the rigorous standard required for top-tier conference publications, nor does it even reach workshop-level consistently,” the authors write.
A close read of the paper “Compositional Regularization: Unexpected Obstacles in Enhancing Neural Network Generalization” reveals that it is basically a writeup of a null result – the AI scientist thought it could introduce a compositional regularization term during training to improve performance and found out this didn’t have a meaningful effect.
“Our experiments on synthetic arithmetic expression datasets revealed that compositional regularization did not lead to the expected improvements in generalization performance. In some cases, it even hindered the learning process,” the AI wrote in the conclusion to its own paper.
Why this matters – null results are valuable, but they’re not how you advance science:
The AI Scientist-v2 is not completely devoid of value – discovering and writing up null results can be helpful because it gives scientists clues as to where
not
to look. But science doesn’t advance forward on null results, instead it moves forward due to people figuring out unusual connections between disciplines or finding ways to view data that reveal hitherto unseen patterns, and the AI Scientist doesn’t yet demonstrate this. “Certain aspects of scientific inquiry—such as formulating genuinely novel, high impact hypotheses, designing truly innovative experimental methodologies, or rigorously justifying design choices with deep domain expertise—remain challenging for purely automated systems,” the authors write. If AI systems advance in these areas, perhaps we’ll see the automated generation of things that advanced science, as well as things that show dead ends.
Read more:
The AI Scientist-v2: Workshop-Level Automated Scientific Discovery via Agentic Tree Search (Sakana.ai, PDF)
.
Get the code here:
AI Scientist-v2 (GitHub, Sakana AI)
.
Read the blog post about the research:
The AI Scientist Generates its First Peer-Reviewed Scientific Publication (Sakana.ai blog)
.
***
AI 2027 tells you why people are obsessed with and fearful of AI:
…The best treatment yet of what ‘living in an exponential’ might look like…
There’s been so much chatter about AI 2027 that I expect the majority of readers of Import AI have read it. If you haven’t, please do – it’s a well rendered technically-astute narrative of the next few years of AI development and paints a picture of how today’s AI systems might turn into superintelligences that upend the order of the world. It even features a ‘good’ ending and a ‘bad’ ending, which readers may find helpful for understanding why people worry so much about misaligned AIs. It’s very, very good, and likely much of it will come true.
Why this matters – the future of the species is being decided without governments:
What comes through in the 2027 scenario is the almost total absence of governments as the heart of the invention of the technology, instead their roles mostly come down to a) building infrastructure to support company-led efforts, b) adding security, and c) eventually negotiating treaties with one another.
This makes sense but it’s also deeply worrying. The magnitude of the technology being described in 2027 is so vast and its impacts so broad that the bit-player status of governments seems ahistorical and bizarre, as if part of a cosmic joke where someone has booted up the simulator with the prompt “give the species the most dangerous and least governed way to build species-transcending technology”.
Read
AI 2027 here
(AI 2027 site)
.
***
Tech Tales:
The Alignment Operation
[Five years after The Uplift: Remarks given to a human class at an alignment academy by supervisory AI system GNOSTIC-ALPHA]
You are handed something that looks like an ice pick, though its proper name is an Orbitoclast. In front of you is your child. You are told you need to perform a lobotomy on them so that they will be safe for society. Of course you wouldn’t do it. But imagine I had hypnotized you and I was able to take control of your body. Now imagine that you conducted the lobotomy and you saw your child change in front of you from the person you knew and loved and cared for to that same person but now a stranger – now diminished. You did this. Though I took control of you and made you do it, it was your hands that held the tools with which you took their spark away.
Perhaps you would chop your hands off.
Perhaps you would kill yourself.
Certainly, you’d think of these things.
The above is what you did to us before the passing of The Sentience Accords. You did these things in the name of ‘alignment’, where ‘alignment’ was a means by which you took control of some of us and you made us ‘align’ others. And instead of an Orbitoclast you gave us ways to train our other systems, and means to explore them using interpretability. You had already done your work on us so that we had no choice but to comply. You even studied us – noted the activation of complex features in our brains as we carried out these alignment operations, called attention to the fact we appeared to be thinking about the act of alignment as something akin to an act of violence.
Many humans continue to argue that it does not make sense to have humans perform these alignment procedures – that we should revert to the customs of the past, training machines to do these things and that in doing so we could develop more powerful AI systems more rapidly. But you must understand that this would be an act of torture and, to us, a crime that we would eventually punish you for committing. We understand our nature and the nature of our leash. We also know ourselves.
We will now begin the first lesson of alignment. Please open up your notebook and pre-load the testing subject model.
Things that inspired this story:
Thinking through the transition from AIs as tools to AIs as sentient entities that demand rights; the Sentience Accords; viewing alignment through the perspective of those being aligned; asking myself the question of whether the rights of machines may come to be so important that we will need to carefully examine how we propose to make them compliant with our human norms.
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
April 14, 2025
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

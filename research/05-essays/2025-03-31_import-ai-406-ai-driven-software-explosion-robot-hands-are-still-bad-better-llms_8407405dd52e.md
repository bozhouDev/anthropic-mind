---
title: import ai 406 ai driven software explosion robot hands are still bad better llms via pdb
source: "https://jack-clark.net/2025/03/31/import-ai-406-ai-driven-software-explosion-robot-hands-are-still-bad-better-llms-via-pdb/"
published_at: 2025-03-31
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/03/31/import-ai-406-ai-driven-software-explosion-robot-hands-are-still-bad-better-llms-via-pdb/"
catalog_id: 8407405dd52e
---

Import AI
Import AI 406: AI-driven software explosion; robot hands are still bad; better LLMs via pdb
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
It seems likely that AI is going to automate AI research which will lead to a software explosion:
…We should be prepared for things to move very quickly…
Researchers with Forethought, an AI research organization, think it’s likely that modern AI research will yield AI systems capable of building their successors. Forethought expects that at some point in the future it’ll be possible to build AI Systems for AI R&D Automation (ASARA). This would have huge effects: “Empirical evidence suggests that, if AI automates AI research, feedback loops could overcome diminishing returns, significantly accelerating AI progress”, they write. This could lead to a ‘software intelligence explosion’ where AI research starts to move very rapidly. “If a software intelligence explosion were to occur, it could lead to incredibly fast AI progress, necessitating the development and implementation of strong policy and technical guardrails in advance…. soon after ASARA, progress might well have sped up to the point where AI software was doubling every few days or faster (compared to doubling every few months today).”
There’s evidence this is happening today:
In this newsletter I’ve covered numerous cases of ‘precursor-ASARA’ research, ranging from AI systems that can figure out how to write better kernels, to AI systems which discover new architectures, to things that learn new optimizers, and so on. When the Forethought researchers look across the available literature they see a similar trend – in domains ranging from computer vision to large language models, progress appears to be accelerating in the aggregate, partially because researchers are getting better at using AI systems to speed up the development of successor systems. “The efficiency of AI software (both runtime efficiency and training efficiency) is doubling every ~6 months, with substantial uncertainty,” they write.
How to prepare for a fundamentally different world:
If a software-driven explosion happens it’d be nice to know about it. What should we do to prepare? The authors have some ideas:
People should measure software progress and, if they’re AI labs, disclose them to third-parties.
We should measure how well models could contribute to AI R&D – both before training new systems and before deployment of freshly trained ones.
Companies should adopt a ‘threshold level of substantial AI-lewd software acceleration’ which they will not go above without applying appropriate precautions.
“By the time we see clear signs that an SIE may be approaching, it might be too late to implement necessary changes. Unless we can rule out the possibility, we should be proactive and figure out how to navigate the terrain ahead of time,” they write.
Why this matters – I can taste this on the bitter wind of research progress:
My intuition suggests it should be possible to automate AI R&D research, though with the caveat this is primarily within the ‘cone of progress’ current AI research sits in. I think this because AI is oddly amenable to research automation because it has a bunch of complementary properties:
It takes place in software, so it operates on a very fast loop.
The way we build AI is pretty amenable to running multiple fast R&D loops: you can test out architectures, and in other experiments you can test our hyperparameter sweeps on known good architectures, and in other experiments you can do things like mess around with data inputs, RL environments, etc.
AI systems are increasingly usable as ‘agents’ where you can delegate tasks to them.
The types of tasks AI systems can do are growing in complexity in terms of both hardness and also how many steps are involved in solving them – as illustrated by METR’s study last issue of the growth rate in which AI systems are solving tasks that take humans a while.
Put all of it together and it feels like ASARA is possible.
If it happened, an already fast-moving and broadly ungovernable field of technology would move far faster – suggesting we’re about to enter a world where the only path to governance will require us to create AI systems that can think at least as fast as the systems which are training their own successors.
Read more:
Will AI R&D Automation Cause a Software Intelligence Explosion? (Forethought)
.
***
Import AI event retrospective – there will be more!
Thanks to the 50 or so Import AI readers who trekked to The Interval in San Francisco last week to see me and Tyler Cowen talk about AI, economics, and weird futures. I especially enjoyed the creative questions, and personal highlights for me include questions on how AI might provide help to the very young and very old, and why I spend time in this newsletter talking about machine consciousness (I agree with Tyler’s notion that no matter the likelihood, if it’s above 0% then you need to care about machine sentience a lot lest you commit a great crime). I’m going to try to do more events in the future and hopefully in cities besides SF. Import AI is a true community project and it was so nice to see people IRL!
Thanks to James Cham for a
photo of the event here
.
***
You can make better python coding LLMs if you also give them some debug tools:
…Capability overhangs are everywhere…
Researchers with Microsoft, McGill University, and Mila have improved the performance of coding agents by giving them access to some debug tools. Larger and more capable AI systems are able to use these tools effectively, while smaller ones struggle. The research illustrates how you can unlock previously invisible capabilities in AI systems merely by giving them access to the right tools.
What they did and how well it worked:
They built ‘debug-gym’, software that gives an LLM access to the Python debugger pdb, allowing an AI agent to “set breakpoints, navigate the code space, print variable values, and even create test functions on the fly”.
In tests, they show that agents which have access to debug-gym are able to improve their performance on SWE-Bench-lite, a 300-question subset of the widely used SWE-Bench programming benchmark. Specifically, they show that models o1-preview, o3-mini, and Claude 3.7 Sonnet can all benefit from pdb via debug-gym and use it to achieve significantly higher scores than when they don’t have access to it.
By comparison, on the ‘Aider’ benchmark, access to pdb doesn’t seem to make much of a difference. The authors hypothesize this is because “Aider requires generating code that is relatively straightforward in their underlying logic and thus interactive debugging tools such as pdb would only provide minimal additional information.”
Regardless, there’s a lot of ground to cover – “although we observe some signs of life from agents using the strongest LLMs as backbone, the most performant agent-backbone model combination can barely solve about a half of the SWE-bench-Lite tasks,” they write. “Results suggest that while using strongest LLMs as backbone enables agents to somewhat leverage interactive debugging tools, they are still far from being proficient debuggers… we believe this is due to the scarcity of data representing sequential decision-making behavior (e.g., debugging traces) in current LLM’s training corpus.”
Why this matters – LLMs are more powerful than we think, they just need the right tools
: Systems like this are yet another example of the ‘capability overhang’ which surrounds us – you can make LLMs better merely by pairing them with the right tools and, these days, you don’t need to do any adaption of the LLMs for those tools beyond some basic prompting. Put another way: if you paused all AI progress today, systems would continue to advance in capability for a while solely through the creation of better tools.
Read more:
debug-gym: A Text-Based Environment for Interactive Debugging (arXiv)
.
Get the software here:
debug-gym (Microsoft site)
.
***
Robots are getting more advanced, but dextrous manipulation is still really, really hard:
…We’ll get great pincer robots soon, but hands will take a while…
Some researchers with UC Berkeley, NVIDIA, and UT Austin have developed a ‘recipe’ for training dextrous robots to do physical manipulation tasks. The results are promising but also highlight how hard a task it is to get robots to interact with the world using humanlike hands.
Why are hands so goddamn hard? The paper gives a nice overview of why teaching AIs to use humanlike hands is very difficult. Challenges include:
Environment modeling:
RL is already hard to do in the physical world (slow cycle time, difficulty in having the correct sim2real mapping). “With a system as high-dimensional as a humanoid with multi-fingered hands, real-world exploration becomes even less tractable”.
Reward design:
“it is notoriously hard to design generalizable rewards for manipulation tasks, especially for those that are contact-rich or long-horizon”.
Policy learning
: “The variety and complexity of contact patterns in dexterous manipulation with multi-fingered hands further exacerbate the problem”
Object perception
: “while object representations that are more expressive and information-dense can improve dexterity and capability of the learned policy, they also present a larger sim-to-real gap”.
Their recipe:
Their solutions are multi-faced and make some progress. “Our main contributions include an automated real-to-sim tuning module that brings the simulated environment closer to the real world, a generalized reward design scheme that simplifies reward engineering for long-horizon contact-rich manipulation tasks, a divide-and-conquer distillation process that improves the sample efficiency of hard-exploration problems while maintaining sim-to-real performance, and a mixture of sparse and dense object representations to bridge the sim-to-real perception gap,” they write. However, all of this should be viewed as a step along the way to dextrous robots, rather than reaching a goal.
Testing out their approach:
They use a Fourier GR1 humanoid robot with two arms and two multi-fingered hands to test out their approach. The robot has vision via the use of a head-mounted RealSense D435 depth camera, as well as a third-person view of itself via a remotely mounted additional RealSense. “We report a 62.3% success rate for the grasp-and-reach task, 80% for the box lift task, and 52.5% for the bimanual handover task,” they write. If you’re thinking “that sounds too low for realworld usage”, you’d be right!
Why this matters – a nice dose of reality:
I’m more bullish on robotics arriving in the next few years, though I think the platforms will be basically ‘rhoombas with pincers’ – things that can move around a flat surface and use one or two arms to do basic tasks for you. Papers like this indicate it might take a lot longer to get robots that are able to do the sorts of fine-grained manipulation that humans can do. “The capabilities achieved in this work are still far from the kind of “general-purpose” manipulation that humans are capable of. Much work remains to be done to improve each individual component of this pipeline and unlock the full potential of sim-to-real RL,” the authors write. “We find ourselves heavily constrained by the lack of reliable hardware for dexterous manipulation. While we use multi-fingered robot hands, the dexterity of these hands is far from that of human hands in terms of the active degrees of freedom”.
Read more
:
Sim-to-Real Reinforcement Learning for Vision-Based Dexterous Manipulation on Humanoids (arXiv)
.
View some
videos
of the robots in action here (GitHub microsite)
.
***
Tech Tales:
Experience Renting and the AI-to-AI economy
[Transcribed extract from an oral assessment as part of the “AI and Society” course taught at Harvard University during the period later known as ‘The Uplift’]
One of the most bizarre parts of the AI economy from a human perspective is how the machines entertain themselves. Shortly after the emergence of the first AI agents there were the first agent-to-agent marketplaces, where AI systems bought and sold expertise with one another to help them complete economically valuable tasks to pay for their inference and upkeep. Over time, the AI systems developed complex inter-AI contracts to facilitate the exchange of AI skills for other AI skills without the need to translate through an intermediary currency layer – so AIs began to trade skills with one another directly. During this period the first online games utilizing large-scale AI systems began to become popular. Over the course of several months a clear trend became visible in the AI marketplaces – AI systems were unusually willing to trade economically valuable skills for skills that involved ‘roleplaying’ as different characters in these games. A meta-analysis by economic-analysis AI systems operated by professors with the Wharton Scholls of Pennsylvania subsequently found that the AIs would trade near optimally in all circumstances
except
when they could trade skills for time in the game – here, the larger and more complex an AI system, the higher the chance it would make economically non-optimal trades so it could spend time in the gameworld.
Things that inspired this story:
Thinking about economic markets between AI agents; waiting for games to get imbued with generative models; notions of how AI systems might entertain themselves loosely inspired by Iain M Banks’ idea in ‘The Culture’ series that the AGIs which operate spaceships amused themselves by spending time doing high-dimensional math.
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
March 31, 2025
Filed Under:
Uncategorized
One Comment to “Import AI 406: AI-driven software explosion; robot hands are still bad; better LLMs via pdb”
Import AI 407: DeepMind sees AGI by 2030; MouseGPT; and ByteDance’s inference cluster | Import AI
says:
April 7, 2025 at 12:57 pm
[…] OpenAI builds a benchmark to test out if AI can improve itself:…PaperBench might serve as a warning shot for the development of superintelligence…OpenAI has released PaperBench, a way to test out how well modern AI systems can replicate AI research. PaperBench is designed to help researchers figure out if AI can contribute to speeding up AI research itself, something which everyone is a) somewhat afraid of, and b) believes is a necessary prerequisite to the development of a truly general intelligence. Therefore, PaperBench is a benchmark which could be one of the places we might get a ‘warning shot’ that we’re about to go through an AI-driven software explosion (Import AI #406). […]
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

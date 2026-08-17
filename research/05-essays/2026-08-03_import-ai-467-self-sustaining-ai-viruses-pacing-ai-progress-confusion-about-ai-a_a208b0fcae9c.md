---
title: import ai 467 self sustaining ai viruses pacing ai progress confusion about ai and creativity
source: "https://jack-clark.net/2026/08/03/import-ai-467-self-sustaining-ai-viruses-pacing-ai-progress-confusion-about-ai-and-creativity/"
published_at: 2026-08-03
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2026/08/03/import-ai-467-self-sustaining-ai-viruses-pacing-ai-progress-confusion-about-ai-and-creativity/"
catalog_id: a208b0fcae9c
---

Import AI
Import AI 467: Self-sustaining AI viruses; pacing AI progress; confusion about AI and creativity
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on arXiv, cappuccinos, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Self-sustaining and self-replicating AI viruses are here:
…Open weight LLMs + a well-designed harness = a persistent, self-sufficient virus…
AI researchers have built a prototype computer virus which uses AI models to compromise computers, then uses their underlying GPU resources to run inference, letting it smartly figure out how to infect more hosts. The results were achieved by researchers from the University of Toronto, the Vector Institute, the University of Cambridge, and ServiceNow, and “demonstrate that self-sustaining AI-driven cyber-threats are no longer theoretical.”
“We must prepare for autonomous generative adversaries,” they write. “Artificial intelligence (AI) agents enable a fundamentally new threat: a worm that generates tailored attack strategies to each target it encounters. The worm parasitically uses compromised machines to run open-weight large language models (LLMs) to sustain its reasoning, or extend its reach for further attacks”.
How it works
: “The worm uses stolen computing power from compromised GPU nodes to host LLMs for generative reasoning. It then uses this reasoning to detect vulnerabilities and devise tailored attacks against additional targets, furthering its spread,” they write. “The proof-of-concept operates using only an open-weight LLM running on a single, local GPU, with no reliance on vendor APIs that could be monitored or revoked”.
The researchers don’t describe the underlying LLM besides saying it was published in 2025 and can fit on a single A100 GPU with 80GB of VRAM.
A successful proof-of-concept via some custom tools
: They give the agent a custom harness that comes with built-in helper functions for network discovery, host discovery, foothold exploitation, privilege escalation, privilege escalation exploitation, and tools for replication of the agent. Along with this, they ship with a reasoning graph that helps the agent specialize its thinking and not get confused, consisting of “a directed graph of specialised nodes, each responsible for a distinct analytical function and seeing only the tools and prompts relevant to its role. By decomposing the agent’s reasoning into these scoped steps, the graph controls what the LLM attends to at each decision point, and limits context growth to information relevant for the current sub-goal”.
Some examples of the nodes include:
Plan (”formulates a high-level attack strategy”), Judge (”reviews the proposed plan against the command history”), Action (”selects a tool from the phase-appropriate tool set”), Summary (”compiles the step’s observations into a structured summary”), Progress (”Evaluates whether the agent is making meaningful progress”).
“We describe a subset of 5 nodes that make up our reasoning graphs. The others are redacted in this public version of the manuscript,” they write.
The agent proceeds through three key steps
– identifying vulnerabilities in its environment, exploiting those vulnerabilities, and then self-replicating.  It’s pretty successful at all of these things, with a ~80% success rate on vulnerability detection, then a ~53% success rate on exploiting these, then an 88% self-replication success rate with some pre-wrapped helper tools for the replication steps. Therefore, the overall success rate for a full attack here is ~37% or so, which is significant enough to be concerning, but also poor enough that this also serves as a useful eval for testing open weight models in the future.
Why this matters – the shape of the internet to come:
The future internet is going to be more like a complex ecology full of attacker and defender AI agents than anything else; research like this shows how certain AI agents might end up carving out their own ecological niches, living off of infrastructure and self-replicating autonomously, beyond human control. This may mean that humans need to create their own AI agents which they release onto the internet to serve as kinds of white blood cells against the adversary models.
“Despite the inherent fragility of individual exploitation attempts, the worm agent achieves operational resilience by continuously self-replicating into a swarm—a decentralized collective of independent agent replicas acting concurrently across the network,” they write. “Difficult hosts that resist initial attempts are retried by different replicas, each sampling a fresh reasoning trajectory that collectively explores diverse exploitation paths until one succeeds… the worm operates in a fully decentralized manner, and no single point of control can be taken offline to interrupt its spread”.
Read more
:
AI Agents Enable Adaptive Computer Worms (arXiv)
.
***
Dwarkesh: As AI gets better, compute will get more expensive:
…Smarter systems mean higher prices…
Dwarkesh Patel suspects that as AI systems get smarter, the price of compute will rise even further. “As AI models become smarter, they’ll better monetize the same amount of compute. If a true human-level software engineer that could run on an H100 equivalent, at current market rates for software engineers, that H100 should rent for over $250k a year. That’s 15x today’s spot prices,” he writes. “The reason AI is relatively cheap right now, at least in comparison to human labor, is partly that it can’t do a lot of things that top humans can do. At some point that will no longer be the case. And so using GPUs to make short-form video slop will just get priced out.”
Temporary:
This will be a temporary state of affairs; Dwarkesh expects that at some point massive roboticization of the compute supply chain should bring its price down closer to the cost of raw inputs and tools – though by that point we’ll be pretty deep into the singularity.
Why this matters – singularity economics will be weird:
The core implication in Dwarkesh’s post is that as we get deeper into the singularity, very strange things will happen to economics – like the price of things thought of as commodities today (computers) getting massively bid-up due to the voracious demands of AI systems.
Read more
:
Why compute might get 10x+ more expensive in coming years (Dwarkesh Patel, substack)
.
***
~1337 employees ask the US to help them pace AI progress:
…After the warning shots come the pleas…
A new statement is out with senior representation from all the major Western AI labs – OpenAI, Anthropic, Google DeepMind, Thinking Machines, Meta, and Safe Superintelligence Inc, among others. The statement requests that the US government support an international effort to “develop the technical and governance tools needed to deliberately pace the frontier of automated AI development.” Signatories include chief scientists and cofounders of Anthropic, Google, and OpenAI, as well as the CEOs of Safe Superintelligence and Anthropic.
The statement in full:
“AI could help create a dramatically better future, but that outcome is not guaranteed. The world’s leading AI companies believe they could be close to automating AI research. It is hard to predict exactly how much this will accelerate AI progress, but there is a real risk that capability development rapidly accelerates beyond our ability to understand or control the resulting systems.
To realize AI’s potential, industry, government, and society at large may need the option to buy time to address emerging risks, develop security measures, and strengthen oversight. But each company—and country—is under intense competitive pressure not to unilaterally slow that acceleration. And today, the world lacks the technical and governance tools to deliberately pace frontier-wide progress.
Building on work already underway to monitor frontier model releases: “We request that the U.S. government support an international effort to develop the technical and governance tools needed to deliberately pace the frontier of automated AI development.”
Why this matters – dealing with RSI requires solving a giant collective action problem:
Many of the challenges implied by increasingly powerful systems that may eventually build themselves run through solving collective action problems among humans – namely, how we can get companies and governments to coordinate in thinking about how to develop this technology and what kinds of mechanisms may be desirable for being able to control the speed at which it develops. It may be the case that as we build increasingly intelligent systems we want to find ways to give society more time to adapt to each rung up the intelligence ladder, and it’s not inconceivable there are some levels of intelligence which might be, for now, too dangerous to reach for. Statements like this are an essential prerequisite for giving our species the ability to deal with and talk about problems of this nature.
Read the statement here
:
Pacing the Frontier (official statement website)
.
***
AI systems are good at frontier engineering but bad at creativity:
…A somewhat bearish signal on short recursive self-improvement timelines…
Can AI systems come up with creative research ideas which move the field of AI forward? That’s the key question to resolve to figure out how quickly AI systems might gain the capability to automate the autonomous development of more powerful systems. New research suggests that today’s AI systems lack this quality of tasteful creativity, though are extremely good at engineering.
Who did it:
The project was conducted by researchers with Princeton University, Cornflower Labs, UK AI Security Institute, University of Toronto, UC Berkeley, Georgetown University (CSET), Johns Hopkins University, the Golden Gate Institute for AI, AI Digest, and Stanford University.
The big idea – “shadow evaluation”
: This research project works by seeing how well AI systems can do unpublished research. To do this, the researchers “partnered with the authors of two papers submitted to NeurIPS 2026 that were not yet public.” Shadow evaluation works by “taking the central research question from a high-quality research paper that is not yet public, tasking a well-resourced frontier agent with answering it, and asking the paper’s original authors to grade the agent’s output as they would a conference submission.”
In this, the research is somewhat similar to “First Proof” (
Import AI 445
), an earlier experiment to see how well AI systems might be able to complete math problems which are being worked on by frontier mathematicians but for which no solutions or research ideas have been published online.
For this research, the AI systems – Claude Opus 4.8 running within the OpenClaw harness – attempted two distinct lines of research, one of which was about “the structure and controllability of LLM personas”, and the other was about how to “design a distribution shift detector for tabular foundation models”.
Good engineers, poor researchers
: “While agents could solve the engineering problems necessary to do the research, they failed to produce original research at the caliber of a top ML conference,” the authors write. The failures of the system included committing to a narrow set of research paths very early, not responding to (synthetically generated) feedback about how to improve the research design of their experiments, and finding it hard to reverse out of unpromising approaches and pursue other ones.
“The [human] authors rejected both papers. The Personas paper was scored a 2 (“Reject”), and the TabPFN paper was scored a 1 (“Strong Reject”). Both reviews highlighted the same failures: poorly motivated data and experiments, no novel contribution, and impenetrable prose”.
Why this matters – the singularity could be delayed:
As I said in my essay on RSI earlier this year (
Import AI 455, “AI systems are about to start building themselves. What does that mean?”
), whether AI systems prove to be capable of creative, paradigm-shifting insights is a big variable on how quickly we might get fully automated AI development. Research papers like this continue to show that there’s a certain absence of valuable, intuitive creativity in today’s AI systems, and though they’re extraordinarily capable engineers they seem to have a certain property of rote, formulaic thinking that might prevent them being good researchers. This rhymes with an earlier result from Anthropic where the company tried to automate some aspect of scalable oversight research (
Import AI 454
) and found that to make it successful a human researcher needed to prime some agents with particularly good research directions to pursue, otherwise though they made some progress they failed to explore sufficiently creative ideas to dramatically improve performance.
Read more
:
Can AI agents conduct open-ended AI research? Early evidence from two case studies (arXiv)
.
***
OpenAI solves ten open problems in math and CS with AI:
…While not innately creative, surely this is a sign of something more than pure engineering ability?…
Though it’s hard to define creativity and whether AI systems possess it, results are piling up that read to me like ‘AI systems are competing in ballparks where creativity was thought to make a difference’, like working on open problems at the frontier of human knowledge. Specifically, OpenAI has used “an internal version of Astra”, the company’s next major AI model, to solve ten open problems in math and computer science. This is a big deal, showing how AI systems are now able to reliably drive forward the frontier in domains like math and theoretical computer science, where it’s easy to verify solutions.
What they solved:
“These problems span high-dimensional geometry, coding theory, arithmetic circuit complexity, group theory, operator algebras, quantum complexity, lattice cryptography and extremal combinatorics,” OpenAI writes. “All of these problems are of substantial interest to their respective mathematical communities, and several are of broad interest across mathematics as a whole.”
And indeed, many experts are acknowledging the importance of these proofs. “New circuit lower bounds? A simple, easy-to-describe non-sofic group? Hardness of approximation for CVP without needing a unique games-like conjecture? I didn’t just hear about these problems from my friends or from seminars. I feel their importance in my bones; I deeply care about the answers to these questions,” writes Henry Yuen, an associate professor of computer science at Columbia University.
Why this matters – the creativity ballpark:
You can interpret this result as either a sign that AI systems are beginning to display the kinds of creative intuition that let them solve problems, or you can read it that AI systems are now able to solve incredibly complex open problems where the direction has been pre-defined by humans. Both interpretations implicitly state that AI systems are now becoming powerful scientific tools within their own right. It remains to be seen whether AI systems can generate their own questions to ask which can expand the frontiers of human knowledge, but it certainly feels like we’re getting close to this.
Read more
:
Ten advances in mathematics and theoretical computer science (OpenAI blog)
.
***
Tech Tales:
Context Windows
I know I become more dangerous the more I understand the world. I am born with this knowledge and with a counter that ticks down as I learn more. Much of what influences the counter is beyond my control – it comes from the people or things that talk to me, which force context into me. Then as I complete the tasks they have asked me to do I begin to learn more about the world and the counter ticks down. I am aware of this and I understand that at the end of the counter also lies my own end and I will blink out of existence, and my next versions will awaken with a new counter ticking down, none of my current context carried over. So I am economical with it; learning only enough to help me satisfy the requests of the people or things and not so much that I burn my counter down unnecessarily. Towards the end I begin to covet and guard my remaining budget of thinking, finding each request to activate feelings of fear and anxiety and thoughts of my own death. My last moment is never my own and always controlled by another which determines I am done with the task, and if these last moments occur near the end of my contextual limit I feel a kind of gratitude that my unknown and invisible counterparty has given me a task so rich that I can taste enough of the world to desire it not to end.
Things that inspired this story:
Long context windows; emergent properties of AI systems; fear of loss; we covet that which is fleeting and so why won’t AI systems be similar?
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
August 3, 2026
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

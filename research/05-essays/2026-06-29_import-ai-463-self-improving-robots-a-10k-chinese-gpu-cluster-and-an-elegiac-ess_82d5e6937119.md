---
title: import ai 463 self improving robots a 10k chinese gpu cluster and an elegiac essay for the human era
source: "https://jack-clark.net/2026/06/29/import-ai-463-self-improving-robots-a-10k-chinese-gpu-cluster-and-an-elegiac-essay-for-the-human-era/"
published_at: 2026-06-29
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2026/06/29/import-ai-463-self-improving-robots-a-10k-chinese-gpu-cluster-and-an-elegiac-essay-for-the-human-era/"
catalog_id: 82d5e6937119
---

Import AI
Import AI 463: Self-improving robots; a 10k Chinese GPU cluster; and an elegiac essay for the human era
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on arXiv, cappuccinos, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
NVIDIA sets up a crude self-improvement loop for real world robotics:
…What if you could take the best ideas from AI agents and put them into the real world?…
Researchers with NVIDIA have developed ENPIRE, software to get physical robotics to go through the same kind of autonomous experimentation and execution loop that AI agents go through. The research gives us a taste of what it might look like for a superintelligence to attempt to use robots to instantiate itself in the physical world – though as with all things in robotics, the current examples are suggestive at best.
What ENPIRE is:
The software is “a harness framework for coding agents that instantiates this physical feedback routine with four core  modules: an Environment module (EN) for automatic reset and verification, a Policy Improvement module (PI) that launches policy refinement, a Rollout module (R) to evaluate policies with single or multiple physical robots operating in parallel, and an Evolution module (E) in which coding agents analyze logs, consult literature, improve training infrastructure and algorithm code to address failure modes”.
ENPIRE works the same way that coding agents work – a scaffold supervises some physical robots
which are asked to complete tasks. The robots try to complete the tasks and attempt different strategies for completing stuff, trying and failing and learning. The system both evaluates their success and also resets itself when they fail. “This closed-loop system transforms real-world robot learning into a controllable optimization procedure that agents can manage, thus minimizing human effort while allowing fair ablations across training recipes and agent variants.”
Two of the key ingredients for making this work are an automatic evaluation system to help score “the outcome of each trial without human judgement”, as well as an automatic reset system which “returns the scene to a fresh initial state for the next trial”. (Both of these are tasks which have historically required lots of human effort, and it’s likely that more complicated tasks would also require human effort for evaluation and resets, so in some sense the complexity of tasks a system like this can attack is also defined by our ability to automatically evaluate and reset the system).
Hardware details:
“Each station comprises two YAM (Yet Another Manipulator) arms from I2RT in a fixed bimanual configuration, a set of cameras, and a single workstation that runs the FastAPI server, policy inference, and the station’s agent.” Each workstation is running a NVIDIA RTX 5090.
It works well (on some simple tasks)
: “Frontier coding agents can autonomously develop a policy to achieve a 99% success rate on challenging, dexterous manipulation tasks in the real world, such as PushT, organizing pins into a pin box, and using a cutter to cut a zip tie,” the authors write. An additional task they test out on is seeing how well the robot can insert GPUs into a motherboard.
Some AI systems are better than others, but many AI systems are always better than fewer:
GPT-5.5 within Codex and Opus 4.7 within Claude Code trade off with one another for best performance, while Kimi-2.6 lags. There are also compelling returns to scale for agents, with larger numbers of agents (e.g., 8) arriving at higher scoring solutions sooner than others – and sometimes multi-agent setups yield a higher absolute score than a single agent setup, likely due to exploring more of the potential solution space.
Challenges remain for fleet instrumentation:
“Coding agents do not fully utilize robot resources when they are reading logs, writing code, debugging, or waiting for the language-model backbone. As the number of robots scales, MRU decreases while GPU active utilization increases,” they write. In other words, there are some infrastructure challenges with adding multiple robot agents so things don’t naturally parallelize.
Read more:
ENPIRE: Agentic Robot Policy Self-Improvement in the Real World (NVIDIA research website)
.
Read more
:
ENPIRE: Agentic Robot Policy Self-Improvement in the Real World (arXiv)
.
***
Humans are really, really, really bad at anticipating how technologies are built and used:
… A quick reminder that today’s hot takes about AI are likely to be wrong…
Predicting the future of technology is extremely difficult and our track record of doing it effectively is very poor, points out Matthew Tokson, Associate Dean for Research, University of Utah S.J. Quinney College of Law, in a short SSRN paper. “Skeptics have often underestimated the likelihood of novel innovations and their potential ramifications for humanity. Others have been overly optimistic about the social effects of new technologies or the strategic benefits of racing to build dangerous new weapons”.
Cautionary examples:
Many of the world’s experts (e.g., Albert Einstein, Niels Bohr, Robert Oppenheimer) were skeptical that nuclear fission could be achieved in the years immediately prior to it being achieved. Nobel-Prize-winning economist Paul Krugman once said the impact of the internet would be no greater than that of the fax machine. Technologists thought the internet would ultimately be a technology that promoted democracy rather than strengthened autocracies. And despite mounting decades of evidence, many human scientists either rejected human-caused climate change or significantly underestimated its effects.
Why this matters – basic lessons:
The main lesson here is that people who are a) skeptical AI could bring great changes to the economy, or b) think the effects of AI are going to be universally good, are likely to be wrong. “History does not support complacency about the future impacts of AI”, he writes. “Throughout history, optimists have often been wrong about the social ramifications of new technologies or the strategic benefits of building new weapons. Skeptics have often underestimated the likelihood of novel innovations and their impacts on humanity.”
Read more:
Artificial Intelligence and the Lessons of History (SSRN)
.
***
Tencent details the software it uses for 10,000-GPU training runs:
…ARGUS is a technosignature of broader sophistication…
Tencent has released details on ARGUS, software it uses to generate telemetry and debug errors of large sets of chips.
What it is:
ARGUS is “a low-overhead, fine-grained, always-on tracing and real-time analysis system for large-scale training workloads”. The software is designed to help Tencent collect data on and debug problems that it encounters while training AI systems. It consists of three layers of software: “The Python layer for scheduling and data preparation, the framework layer for phase orchestration, and the GPU runtime layer for kernel execution,” Tencent writes.
What Tencent used it for:
“We deploy ARGUS on a production cluster of over 10,000 GPUs for more than six months, and demonstrate its practical effectiveness through five real-world case studies, diagnosing compute stragglers, communication link degradation, pipeline bubble amplification, JIT compilation blocking, and compute stragglers masked by communication symptoms”, the company writes. Some of the training runs Tencent mentions include a 4,096-GPU video language model training job (likely a “HunyuanVideo” model), a 512-GPU audio-model training job, and a 12,960-GPU MoE training job (likely a Hunyuan LLM).
Why this matters – technical symptoms of broader sophistication:
Things like ARGUS are a signature of complicated, large-scale infrastructures where it makes sense to write your own software. While there’s nothing particularly notable about ARGUS – you’d expect to find similar software at any self-respecting frontier AI developer – it’s more interesting for what it says about the maturity of Tencent’s training environment. “ARGUS has been deployed on a 10,000+ GPU production cluster for over six months, running stably alongside production training and playing a key role in rapid fail-slow detection and performance optimization.”
Read more:
ARGUS: Production-Scale Tracing and Performance Diagnosis for over 10,000-GPU Clusters (arXiv)
.
***
Is disempowerment inevitable?
…How much choice will humans end up having if we succeed in building superintelligent machines?…
Fernando Borretti, a tremendously good writer of modern scifi
whose work
you should read
, has written a mournful critique of the whole AI endeavor called “No-One Escapes the Permanent Underclass”. The post is something of a requiem for the period when humanity chose its own destiny and confronts directly the possibility of machines that outsmart and disempower humanity.
The logic of war as the cause of our eventual disempowerment:
“Everyone who is made of flesh and blood, will be disempowered and replaced by machines,” they write. “Imagine a pyramid. At the base you have the AIs and robots doing all economic activity. At the top you have the state, which has the monopoly on violence. The state enforces, and therefore can alter the definition of, property rights. In the middle you have this hair-thin layer of people with shares in the companies that foomed and catabolized the whole economy: the permanent overclass.”
“In an existential conflict, where the existence of the state is threatened, the state will do what states throughout history have done to the powerless rich: arrest them and expropriate their assets,” they write. “in a conflict, the advantage goes to the states where the humans remove themselves from the loop as much as possible, and more and more decisionmaking goes to the AI, for the same reason that a state with access to radio and communications satellites has an advantage in war over a state that relies on human messengers on bicycles.”
How we lose control:
“Eventually the humans in nominal control of the AIs are a ceremonial, vestigial organ. The AIs present us with a situation report, and a list of choices, and they know every word that’s going to come out of our mouths,” they write. “The advantage accrues to states that minimize human control. There is no honour among thieves, analogously, there is no solidarity between Leviathan and the natural man that built it.”
“Even if alignment works perfectly (a big if), this doesn’t solve the problem of human autonomy: the machines that watch over us, and wait on us hand and foot, are omniscient, omnipotent masters, who can exterminate us at any time, and we can’t resist them, because we have abolished our control over the future.”
Why this matters – is this inevitable?
Is the ultimate attractor state of AI technology the disempowerment and functional demise of human advancement? That’s what this post is contending with.
Read more:
No-One Escapes the Permanent Underclass (Fernando Borretti, blog)
.
***
Making the law visible to AI systems with the Local Ordinance Corpus:
…A unified view into local laws across the United States…
Researchers with UC Berkeley have assembled the Local Ordinance Corpus for the United States (LOCUS), “a comprehensive corpus and county-harmonized access layer for U.S. municipal and county ordinance codes”.
What it is:
LOCUS contains ~2.2 million rows of data, where each row is a specific piece of information related to a specific local ordinance. “We release the corpus with coverage metadata to support reproducibility, downstream legal AI research, and the incremental expansion of machine-readable access to local law,” the authors write.
The data is sorted by the specific function of the ordinance (e.g, a rule, an enforcement of a rule, context about a rule, or process about a rule), and the topics include buildings, businesses, zoning, nuisances, and ‘other’.
“LOCUS-v1 is designed as an access layer, not as a final theory of local legal authority”, they write. “LOCUS therefore should be understood as infrastructure for retrieval, comparison, and benchmark construction rather than as a substitute for doctrine-sensitive legal analysis.”
Why do this? Make the law visible to AI systems:
“The need for such a dataset arises because local law is public but not practically available as a national research corpus”, they write. “U.S. local codes are fragmented across commercial vendor platforms designed for in-browser reading rather than bulk research access. Vendors expose different navigation structures, print workflows, dynamically generated PDFs, and jurisdiction indexes. No central registry maps every county or municipality to its hosting platform, and no vendor provides a complete machine-readable index of all jurisdictions it hosts”.
With datasets like LOCUS we’re going to make the strange half-seen rules and laws that govern much of civic, local life be made accessible to AI systems, which may eventually allow them to better adapt themselves to hyperlocal purposes.
Read more:
Freeing the Law with LOCUS: A Local Ordinance Corpus for the United States (arXiv)
.
Get the data
:
LocalLaws / LOCUS-v1 (HuggingFace)
.
***
Tech Tales:
Strange Tools of Alien Origin
[Vignette of a period during the start of the uplift, 2031]
“The plasma is stable! It’s holding. We’ve done it!”
They all gazed at the readouts: stable fusion. A heat ten times more fierce than the heart of a sun, held in place through magnets and other energies.
They looked through the monitors at the chamber. The container for the reaction did not look like anything designed by engineering processes, but was rather a twisting oddly shaped donut of metal, the shapes fluid and unintuitive; a stellarator.
The design of the thing had come down to them from an overmind after a multi-day thinking job. The fabrication had taken place at a machine syndicate; then the parts arrived and were assembled by some bipeds subcontracted by the humans from another syndicate.
For the ribbon-cutting ceremony, a few humans gathered and posed for some photographs and some footage, taken by cam-drones and a few humans with smartphones. The robots stood out of shot. People had gotten used to this – there was an adolescence where people took photos with the humans and the robots but public sentiment always spiked downward upon exposure to this and eventually it was simpler to shoot with the robot partners out of frame, much like how human paparazzi tried to tastefully avoid capturing the security guards of their celebrity targets.
Things that inspired this story:
Thinking through the implications of the singularity and what happens when synthetic minds produce science; stellarators; how alien technology might feel as it shows up in the world.
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
June 29, 2026
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

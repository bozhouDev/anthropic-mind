---
title: import ai 451 political superintelligence googles society of minds and a robot drummer
source: "https://jack-clark.net/2026/03/30/import-ai-451-political-superintelligence-googles-society-of-minds-and-a-robot-drummer/"
published_at: 2026-03-30
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2026/03/30/import-ai-451-political-superintelligence-googles-society-of-minds-and-a-robot-drummer/"
catalog_id: 37834f4cdeb2
---

Import AI
Import AI 451: Political superintelligence; Google’s society of minds, and a robot drummer
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on arXiv and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
AI might let us build “political superintelligence”:
…But turning this into a societal upside requires lots of intentional work…
As AI systems get more powerful and broaden their real world impact from coding to other domains, it seems likely that they could also become useful for helping people advocate for themselves in politics, and helping politicians better craft policy. But getting to a world where a “political superintelligence” exists and helps us is a lot more challenging than just building better AI systems, according to Andy Hall, a political economy professor at Stanford.
“AI is like the printing press, to a point. Instead of making information cheap and easily available, it makes intelligence cheap and easily available. That is, it not only serves users information, but it can find it for them, analyze it for them, and help them convert it into understanding,” Hall writes. “The more I work with and study AI, the more I believe it can give every human being on the planet access to a sort of
political superintelligence,
if we shape it right.”
What is a political superintelligence?
By this, Hall means AI systems which allow people to have “tools that help citizens, representatives, and institutions perceive reality more sharply, understand tradeoffs, contest power, and act more effectively”. A political superintelligence spans both the AI companies that build the technology, the technology itself, and the institutions and people which the technology interacts with.
“I’m not interested in slowing AI down. I’m interested in speeding up how we build the structures that keep us free as AI gets more powerful,” Hall writes.
Three layers for political superintelligence:
Hall sees political superintelligence as being composed of three distinct layers.
The information layer:
“AI can massively change how governments access and understand data, identify problems, hear from citizens, and distribute services”. Though getting to this future will require better evaluations for how AI systems behave when it comes to the sorts of information governments might be interested in, and it’ll require people to build AI tools directly for policymakers.
The representation layer:
“Political superintelligence might help solve this monitoring problem by giving each of us a tireless, automated delegate always serving us in the political sphere,” he writes. “These AI delegates could monitor politics for us and suggest how to vote—or even serve as policymakers alongside human supervisors.” Building this layer requires us to ensure that agents can reliably act on our behalf, that they aren’t swayed by adversarial prompting (imagine how politicians might fund campaigns explicitly designed to sway the beliefs of agents working on behalf of people). It may also be important to re-think agent ownership – what happens if a particular policy choice goes against the preferences of the AI company which operates the agents?
The governance layer:
“Even if we achieve political superintelligence—even if AI makes voters brilliant and delegates faithful—those capabilities would sit inside infrastructure owned and operated by a small number of private companies,” he writes. “We need a way to write the rules so that, when political superintelligence arrives, we the people are able to harness it.” Doing this will require figuring out how to govern and edit the ‘constitutions’ that companies create about their models, as well as developing an effective way of overseeing these AI systems.
Why this matters – building a political superintelligence is only as valuable as its interfaces with people and institutions:
We are by default going to get extremely powerful AI systems which can think about politics (and everything else) at a very sophisticated level. The challenge Hall outlines is that getting these systems to lead to a thriving society requires significant intentional work around the UX and UI of these systems –
how
do we interface with them? What sorts of technical means do we have of being confident in them? What information do they generate and to whom? Where does control of these systems lie and what systems supervise that control?
Getting this part right requires AI developers to invest more in technical tools which can help people make sense of and oversee their AI systems, as well as tools for better gathering deliberative feedback from people about how these systems behave. Policymakers and the public need to demand more of AI companies in this respect, and ultimately I think there are a range of regulations that need to get stood up around a transparency regime for AI companies as well as some common set of standard ‘APIs’ by which society can interact with the companies and the systems they build to generate empirical data and provide steering over their behavior.
Read more:
Building Political Superintelligence (Free Systems, Substack)
.
***
Fear not, drummers, you’re safe from AI automation for now:
…DexDrummer tackles a fiendishly hard robot hand problem…
Whenever I get a bit worried about the pace of AI progress I toggle over to the ‘robotics’ sub-section of arXiv, read some papers, and feel a huge sense of relief. Robots, as everyone knows, are extremely hard to do well, with reality tending to screw up even the most advanced techniques. An even harder version of robotics is fine-grained low-latency dexterous control, where you need to get a robot hand to do something. So it’s with a combination of amusement and empathy that I read DexDrummer, a paper testing out how well contemporary AI approaches can get a robot hand to play the drums. The short answer is: robot hands are pretty terrible drummers!
What they did:
They built DexDrummer “a hierarchical, two-stage policy for drumming” which has a high-level RL policy, as well as a low-level dexterous policy. They train their system in a simulated environment that contains a bimanual robot setup and a full drum set (snare, tom, ride, hi-hat, and crash). The main system generates a stick trajectory in task space, then a low-level system which tries to control the hand – this part is complex and involves encouraging the thumb  and index finger to grasp the center of the drumstick paired with an “arm penalty constraint, which reduces excessive arm movements”. There is also work shaping rewards to ensure the robot is able to chain multiple drumhits together – this is achieved via a “contact curriculum” which allows the agent to practice trajectory following in free space while following the trajectory reward.
Real world testing:
They test out the trained policy in reality on two 7-DOF Franka Panda arms and two 20-DOF Tesollo DG-5F hands. This is an area where I’d strongly encourage people to view the videos online to get some calibration about just how fiendishly hard this task is – the robots are able to hit the drums, but it’s painfully awkward to watch, and my sense is it’ll be quite a while till a human drummer has to look over their proverbial shoulder.
Why this matters – robotics as the last eval:
Robotics in anything approximating a dynamic, rapidly changing environment (for instance, improvising drums with a live band) feels like one of the last frontiers for AI – and as this research shows, much like with modern computer vision research, getting AI to perform well requires the crafting of highly complicated artisanal policies. We’re a very long way from the generality of pretrained language models here.
Read more:
DexDrummer: In-Hand, Contact-Rich, and Long-Horizon Dexterous Robot Drumming (arXiv)
.
Please, I am begging you, check out the videos for a good time
:
DexDrummer site
.
***
Google thinks the real challenge of AI alignment is dealing with a world made up of mostly non-biological intelligences:
…Towards a society of minds…
Researchers with Google think that the future of intelligence is less about building a monolithic singleton that runs the world and more figuring out how to build institutions that are capable of dealing with a vast proliferation of AI agents working in tandem with humans. The research is intuitive, provocative, and sensible, and builds on earlier technical work that showed that modern AI systems appear to simulate multiple personalities within themselves to help them answer questions (
Import AI 444
), suggesting that even today’s AI systems already work like complex ecologies.
“We should be looking for the next intelligence explosion in the same place from which the previous ones emerged: in cooperative, competitive and creative interaction between multitudes of socially intelligent minds. The difference this time is that most of those minds will be non-biological,” Google writes. “The toolkits of team science, small-group sociology, and social psychology become blueprints for next-generation AI development.”
History shows the way:
“Each prior “intelligence explosion” was not an upgrade to individual cognitive hardware, but the emergence of a new, socially aggregated unit of cognition,” they write.
Primate intelligence
: Scaled with the social group size.
Human language:
Allowed knowledge to accumulate across generations via a ‘cultural ratchet’.
Writing, law, and bureaucracy
: Converted social intelligence into infrastructure and institutions that could coordinate across long time horizons. (”A Sumerian scribe running a grain accounting system did not comprehend its macroeconomic function; the system was functionally more intelligent than he was.”)
AI plus human institutions
: “The path to more powerful AI runs not through building a single colossal oracle but through composing richer social systems—and these systems will be hybrid”.
Society needs an upgrade:
Implicit to this is the fact that governing AI will increasingly involve verifying (e.g,
Import AI #447
) that a vast number of AI systems are working on our behalf appropriately. “Governments will need AI systems with distinct, explicitly invested values—transparency, equity, due process—whose function is to check and balance AI systems deployed by the private sector and other branches of government,” they write.
Why this matters – alignment is going to happen with and in the world, not outside of it:
Many people working on AI safety have long spent time on getting the fundamental properties of a single AI system to be ‘aligned’, which roughly translates to “does what you want and doesn’t try to kill you or disempower you”. But what this paper correctly identifies is that
even if we succeed at alignment
we’re going to have to then get AI systems to work well within society and to collaborate effectively with us and with each other – and this will be a subtle, emergent, hard-to-predict process. This means we are going to need to design the institutions that are fit for governing an AI-centric world. “Just as human societies rely not on individual virtue but on persistent institutional templates – courtrooms, markets, bureaucracies – defined by roles and norms, scalable AI ecosystems will require digital equivalents,” the researchers write.
Read more
:
Agentic AI and the next intelligence explosion (arXiv)
.
***
Meta uses a harness to coax Anthropic’s models into self-improvement:
…Give an LLM some tools and a recursive loop and the ability to edit its harness, step back, and let the magic happen…
Researchers with the University of British Columbia, Vector Institute, University of Edinburgh, New York University, CIFAR, and Meta have built a harness for LLMs that has the ability to self-improve performance for arbitrary tasks. The approach is called a hyperagent, and it means giving an LLM a scaffold that can iteratively improve the prompts it uses to bootstrap its performance on tasks
as well as
the system it uses to get better at generating future prompts. Hyperagents work over generations, so one hyperagent begets a few hyperagents and the ones which do the best on the task will themselves spawn some more hyperagents, forming multiple layers of AI genealogy until performance is saturated.
Cyberpunk name of the year award:
Hyperagent is actually short for “Darwin Godel Machine Hyperagents”: Besides the research being cool, my congratulations to the authors on coming up with a name I’d love to see chiseled into the moon by a laserbeam wielded by a superintelligence.
How hyperagents work
: Hyperagents are “self-referential agents that integrate a task agent (which solves the target task) and a meta agent (which modifies itself and the task agent) into a single editable program. Crucially, the meta-level modification procedure is itself editable, enabling metacognitive self-modification, improving not only task-solving behavior, but also the mechanism that generates future improvements,” the researchers write. “This initial hyperagent is equipped with two tools: a bash tool for executing shell commands, and a specialized tool for inspecting and modifying files.”
Testing the agents in four different domains:
The authors test out hyperagents by applying them to four problems – coding (polyglot), prediction (paper review), robotics (robotics reward design), and math understanding (olympiad-level math grading). For most problems, the Hyperagents use Claude Sonnet 4.5 as their base model, with one exception (Polyglot). Evaluations are done via several different models: o3-mini (Polyglot), GPT-4o (paper review), Claude Sonnet 4.5 (robotics reward design), and o4-mini (IMO-level grading).
In all cases, the hyperagent approach improves performance significantly above the baseline.
Polyglot:
“the agent is given a code repository and a natural language instruction describing a desired change, and must modify the repository accordingly”.
Results:
“Across 5 runs, the DGM-H improves its training performance on the 50-task Polyglot subset from 0.140 (the initial agent) to 0.340 (CI: 0.300 – 0.380).”
Paper review:
“For each task, the agent is given the full text of an AI research paper and must predict a binary accept/reject decision”.
Results:
“On test tasks, DGM-H improves paper review performance from 0.0 (the initial agent) to 0.710 (CI: 0.590 – 0.750)”
Robotics reward design:
“Given a natural language description of a robotics task, an agent must generate a suitable reward function. This reward function is then used to train a quadruped robot in simulation using RL”
Results
: “DGM-H improves performance from 0.060 (the initial agent) to 0.372 (CI: 0.355 – 0.436), surpassing the default reward function that directly optimizes the evaluation metric (0.348)”
Why this matters – bootstrapping the singularity:
Papers like this show that today’s AI systems are already capable of autonomously improving their performance when given the right scaffold and starting ingredients. An interesting idea is to combine the design approach here with giving the AI systems the ability to finetune themselves (e.g, in the style imagined by the PostTrainBench research,
Import AI #449
). Another limitation is that “although hyperagents can modify their self-improvement mechanisms, they cannot alter the outer process that determines which agents are selected or how they are evaluated” – though again, I think there are technical ways to achieve both of these objectives.
Of course, an AI system that can autonomously improve itself on arbitrary domains  has a range of safety issues, some of which are potentially cataclysmic. The authors acknowledge this while also being realistic about the problems that lie ahead: “a central challenge lies in balancing the potential of AI as a catalyst for human progress and well-being (e.g., automating scientific discovery) with the degree of trust humans are willing to place in these systems (e.g., delegating decisions or actions without requiring continuous human verification), while minimizing the many potential risks and downsides,” they write.
Read more:
Hyperagents (arXiv)
.
Get the code
for
HyperAgents here (Facebook Research, HyperAgents)
.
***
How long will a new math benchmark, HorizonMath, last?
…New test challenges AI systems to solve unknown problems, then automatically verifies the answers…
Another day brings another hard math benchmark that I imagine will crumple in the face of ongoing AI progress in the coming year. This time it’s HorizonMath, a benchmark containing 100 “predominantly unsolved” problems across 8 domains in applied and computational mathematics. The benchmark was built by researchers with the University of Oxford, Harvard University, Princeton University, and the Ellison Institute of Technology.
Special features about HorizonMath:
Contamination-Proof:
“Because the solutions are unknown, they do not exist in any training corpus, and any correct solution produced by a model would therefore signal genuine reasoning ability and autonomous discovery.”
Automated verification
: “A core feature of our benchmark is its fully automated, reproducible, and human-free evaluation pipeline”, the authors write. “We automate verification using high-precision numeric comparison and deterministic constraint-checkers”.
What HorizonMath contains:
HorizonMath’s 100 problems are classified along three axes: output types, which specifies how the model needs to solve the task ranging from identifying an exact closed-form expression for a numerically approximated target value, to the production of discrete mathematical objects; solvability levels, which span ‘level 0’ (problems with known closed forms) to ‘level 3’ (problems that could be conjectured unsolvable or lack finite closed forms); and mathematical domains, which specifies the type of domain ranging from number theory to discrete geometry to mathematical constants.
Reassuringly hard:
On the full dataset, the highest scoring model is GPT 5.4 Pro with 7%, followed by Opus 4.6 and Gemini 3.1 Pro which both tie at 3%. On the “Level 0” (aka, the easiest) problems, GPT 5.4 Pro leads at 50% completion, with both Opus 4.6 and Gemini 3.1 in a tie again at 30% each.
Next steps:
They will expand the benchmark in two ways, first by liberalizing the sorts of solutions that they will take in, as well as by “extending beyond the three current problem categories to include open problems that require proof-based verification, integrating with formal systems such as Lean”.
Why this matters – perhaps the first truly creative AI systems will show up in mathematics:
AI systems are pushing on the frontiers of math today, with systems like Gemini already helping humans to come up with seemingly original math proofs (
Import AI 441
), and tests like “First Proof” emerging which examine how well AI systems can handle problems that have never been talked about publicly let alone solved (
Import AI 445
). With HorizonMath, we have another useful benchmark to help us see if AI is about to cross some ‘creativity rubicon’ and begin solving unsolved problems.
Read more
:
HorizonMath: Measuring AI Progress Toward Mathematical Discovery with Automatic Verification (arXiv)
.
Get the benchmark here
:
HorizonMath (GitHub)
.
Tech Tales:
Site report
[2029]
Percentage of compute and power below ground: 70% (+50 absolute points).
Number of staff living fully onsite: 300 (+250).
Estimated duration of ‘hard seal’ based on current supplies and a projected population of ~500: 4 months (+3 months).
Estimated lead of the project relative to others in-country: 6 months.
Capability estimates: 90%-110% of our own leading system.
Recommendation: Based on the substantial increase in resources allocated to hardening the facility for closed-loop development, we believe additional measures must be taken to disrupt the project. The following report lists options for consideration, many of which can be combined together. These include:
Food system sabotage.
Staff interference.
Data poisoning.
Things that inspired this story:
How at some point surely there will be such a thing as a hardened datacenter for AI training and inference? How the intelligence community might analyze other AI projects.
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
March 30, 2026
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

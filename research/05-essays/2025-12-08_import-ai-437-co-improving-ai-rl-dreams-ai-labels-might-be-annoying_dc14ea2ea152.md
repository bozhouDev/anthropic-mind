---
title: import ai 437 co improving ai rl dreams ai labels might be annoying
source: "https://jack-clark.net/2025/12/08/import-ai-437-co-improving-ai-rl-dreams-ai-labels-might-be-annoying/"
published_at: 2025-12-08
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/12/08/import-ai-437-co-improving-ai-rl-dreams-ai-labels-might-be-annoying/"
catalog_id: dc14ea2ea152
---

Import AI
Import AI 437: Co-improving AI; RL dreams; AI labels might be annoying
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Facebook: Let’s not build self-improving AI, let’s build co-improving AI:
…A sensible goal which may be hard to achieve…
Facebook researchers have said that building self-improving AI which eventually reaches superintelligence is “fraught with danger for humankind – from misuse through to misalignment” and it’d instead be better to co-develop superintelligence. They’ve published their reasoning in a paper which reads both as aspirational and earnest.
Ideally, humans and machines will work together to build a smarter-than-human system, and the researchers think we should develop a research agenda “targeting improving AI systems’ ability to work with human researchers to conduct AI research together, from ideation to experimentation, in order to both accelerate AI research and to generally endow both AIs and humans with safer superintelligence through their symbiosis.” The thesis here is that “co-improvement can provide: (i) faster progress to find important paradigm shifts; (ii) more transparency and steerability than direct self-improvement in making this progress; (iii) more focus on human-centered safe AI.”
What goes into a co-improving AI?
Collaborative brainstorming, problem, experiment, benchmark, and evaluation identification: Humans and AIs should jointly define goals, research approaches, the tests needed to measure progress against them, experiments to generate data, and methods to evaluate the results.
Joint development of safety and deployment: Humans and AIs should co-develop the methods to align the technology as well as the methods of deploying and communicating about the technology.
“Overall collaboration aims to enable increased intelligence in both humans & AI, including all manifested learnings from the research cycle, with the goal of achieving co-superintelligence,” they write.
Why this matters – a Rorschach for the psychology of (some) AI researchers
: In seminal American show
The Wire
there’s a scene where an up and coming criminal kingpin says to a security guard trying to enforce the laws of society: “
You want it to be one way, but it’s the other way
“. This is how reading this paper feels: AI researchers, staring at the likely imminent arrival of automated AI R&D, articulate how things would be better and saner if humans could co-operatively develop future AI and write a position paper about it. But are they just grasping for a world that is unlikely to exist and articulating their anxiety in the form of a position? Perhaps.
Read more:
AI & Human Co-Improvement for Safer Co-Superintelligence (Facebook AI Research, GitHub, pdf)
.
***
How bad could policy for labeling AI systems be? Pretty bad, based on existing EU regulations:
…A neat illustration of how even simple policy ideas can yield profound complexity…
Labeling is a simple, uncontroversial AI policy idea which people like me loudly and often support. The idea being AI labeling is that manufacturers of AI systems (e.g, OpenAI, Anthropic, etc) should be forced to include a label with their AI models which lists out something like the high-level ingredients of the model, the recommended uses, and some ‘buyer beware’ information about its safety properties.
Sounds reasonable, right? It certainly does to me! But as with most things in policy, an iceberg of complication lurks beneath this simple idea. To get a taste of all the ways AI labeling might go wrong I recommend people read a recent Financial Times article “The EU single market’s elephant in the room” which discusses how well-intended and equally simple labeling schemes from Europe have caused companies like Ikea to have to invest
thousands of hours
into compliance as well as things like revamping how they produce labels for their goods.
Why this matters: policy is expensive:
Most people who work in AI policy are pretty unaware of how expensive AI policy, once implemented, is to comply with. This is a fatal error – people who either work in regulated industries or have knowledge of it will often look at people proposing AI policy (e.g, yours truly) with a mixture of puzzlement and horror at the pain we are about to inflict on them and ourselves.
Now, a reasonable counter-argument is “sure, some pain is necessary if we’re making AI systems which are smarter than any person and have a potential to exacerbate national security risks”, but it’s worth being aware of the background context into which such an argument is made.
Read more
:
The EU single market’s elephant in the room (Financial Times)
.
***
Train your AI systems in SimWorld, a high fidelity, programmable videogame-like simulator:
…Back to the RL future…
Researchers with multiple universities across multiple countries have built and released SimWorld, an Unreal Engine 5 simulator that people can use to train agents within.
SimWorld is designed to give people a graphically rich, procedural, and scriptable world in which they can run AI-based agents. This will both serve as an environment in which to construct challenging tests for existing agents, as well as a testbed to train new agents via reinforcement learning. The simulator combines “realistic physical and social dynamics” with “open-ended, language-steerable world generation”.
SimWorld was developed by researchers with UCSD, UVA, UIUC, JHU, Purdue, PolyU, USC, and UMich.
Why care about SimWorld:
Think of SimWorld as a tool that researchers can use to test and develop agents, similar to how existing scientific and architectural software has been used to test and extend the capabilities of today’s AI systems.
Within SimWorld, “agents can perceive rich multimodal observations (e.g., visual scenes, abstract layouts, and action feedback) and respond with high-level language commands. For example, an agent may reason and generate an abstract action, “sit on the nearest chair,” which SimWorld automatically decomposes into a sequence of low-level actions (e.g., navigating through waypoints, sitting down). After executing the actions, the simulator provides updated observations and feedback, allowing the agent to refine its strategy and continue reasoning”, the authors write. “Beyond short, task-oriented behaviors, agents can pursue extended objectives such as earning money, developing a career trajectory, or running a multi-agent business, where strategic decisions compound over time and social dynamics influence outcomes.”
What SimWorld is made of:
Unreal Engine backend:
The foundation is the Unreal Engine, a rendering and physics simulator which is widely used within the gaming industry. This provides access to a variety of environments as well as an asset library to populate environments with, as well as physics simulation.
Environments:
A Python-based intermediary layer which helps developers program the underlying backend, providing tools for tasks like generating environments, editing environments (e.g, ‘place a tree here’), implementing traffic systems, and providing a python interface for the agents themselves to interact with.
Agent:
A Python-based layer for AI agents, giving them programmatic access to the Environment layer, allowing them to observe the world around them and also take actions within it.
Use AI to train your AI:
SimWorld also integrates text-to-3D models like
Hunyuan3D from Tencent
so that people can describe assets in natural language which are then generated on-the-fly and integrated into the simulator, making it trivial to extend.
Why this matters – back to the RL future:
Before language models were the dominant technical paradigm of AI development, many people trying to build smart machines were betting on reinforcement learning agents. Specifically, that by training AI agents on an increasingly rich set of game-like environments, they’d be able to force the development of smart, capable agents. But in hindsight there was a critical flaw with this approach – they were starting these agents from a blank slate, so what you ended up with was a terrifically expensive way of coming up with extraordinarily gifted players of games (e.g., first Atari, then Go) and sometimes multiple types of games (e.g, AlphaGo Zero and its expertise at Go, Chess, and Shogi). But you didn’t end up with a true general intelligence.
Now, we’ve come full circle – because now the agents being developed in environments like SimWorld will typically be built on an underlying world model from a frontier AI system, like Claude or Gemini or ChatGPT, and SimWorld will be used to create more data to finetune this system on to make it more capable.
“By supporting advanced LLM/VLM-based agents and enabling large-scale, realistic agent–environment and agent–agent interactions, SimWorld expands the capabilities of modern agent-based simulation (ABS),” the researchers write. “This allows researchers in robotics, business, public health, social science, education, and beyond to study complex systems and emergent behaviors in rich, dynamic, and controllable environments”.
Read more
:
SimWorld: An Open-ended Realistic Simulator for Autonomous Agents in Physical and Social Worlds (arXiv)
.
Find out more at the website:
SimWorld
.
***
DeepMind returns to its RL roots by combining an agent with Gemini:
…SIMA 2 points at what truly autonomous AI systems might look like…
DeepMind has published details on SIMA 2, the second version of its ‘Scalable Instructable Multiworld Agent’. SIMA 2 is a game-playing agent which has been developed by taking a Gemini-class frontier model then fine-tuning it on rich interaction-prompt pair data generated from a variety of videogames and education software. The result is a general-purpose AI agent that can carry out a very large range of actions inside 3D worlds, and also something of a triumph for DeepMind whose original research agenda was all about building general intelligence through developing generally capable AI agents through reinforcement learning.
What SIMA 2 is:
“The SIMA 2 agent architecture is a Gemini Flash-Lite model that is trained using a mixture of gameplay and Gemini pretraining (non-gameplay) data. We found this mixture crucial to maintain the original capabilities of the base model, such as vision understanding, dialogue, reasoning, and promptability,” DeepMind writes. “By training across a growing portfolio of 3D games, the agent shows a remarkable capacity to generalize to previously unseen environments, including photorealistic worlds generated on-the-fly by Genie 3”.
Some of the games SIMA 2 was trained on include Goat Simulator 3, No Man’s Sky, and Space Engineers.
Held out evaluations
: SIMA 2 displays strong generalization – most well evidenced by its performance on ASKA, an early access crafting and survival game about building a viking settlement. SIMA 2 wasn’t directly trained on ASKA and is able to perform well on it out of the box. But most impressively it also displays the ability to self-improve on it – ASKA has a crafting menu which is “quite distinct” from ones SIMA 2 encountered during training, but DeepMind was able to overcome this via the use of a self-improving scaffold.
Self improvement:
The funny thing about modern AI systems is they’re sufficiently smart you can use them to improve other AI systems. That’s the case here, where a Gemini model is used to set tasks for the SIMA 2 agent to perform that involve manipulating the crafting menu. The Gemini model scores how well it does and then saves the trajectories where it is able to complete the tasks it was set without getting distracted. This data is then fed back into it for fine-tuning, letting it automatically bootstrap its way to better performance. “Through focused effort by the task setter, the agent was eventually able to acquire this skill,” the authors write.
As a consequence, the SIMA 2 agent using the self-improving scaffold can do far, far better at the ASKA game than without the ability to self-improve. “Despite purely training on self-generated experience, the resulting agent is capable of progressing much further than SIMA 2, ultimately building a shelter within a one hour time window”.
Why this matters -this is what robots will use to change our world:
Research like SIMA 2 is the same sort of paradigm I expect people will use to teach robots to be able to do useful, open-ended things in our world: fine-tune a powerful frontier model on a bunch of data gathered from agents taking actions in the world. And in the same way SIMA 2 displays strong generalization, I expect the same for robots as well. Problems remain, but this is a simple, scalable idea, and it naturally leverages the underlying boom in frontier model capabilities, so it’s likely to work: ‘SIMA 2 still faces challenges with very long-horizon, complex tasks that require extensive, multi-step reasoning and goal verification. The agent also has a relatively short memory of its interactions—it must use a limited context window to achieve low-latency interaction,” the authors write. But nonetheless: “these results suggest a promising path toward using self-improvement to eventually bridge the virtual and physical worlds, enabling more capable physically-embodied agents in applications like robotics”.
Read more
:
SIMA 2: A Generalist Embodied Agent for Virtual Worlds (arXiv)
.
Tech Tales:
A Walk During The Singularity
[2033]
It was dusk and the city was glimmering with many yellow and red and white lights. I walked the ridgeline above it, boots crunching into a dirt crust that had formed thanks to a recent rain. I could hear the faint susurration of traffic and occasional sirens but so quiet they mixed in with the dusk birdsong and blended together.
Then all of a sudden many of the lights in the city went out. Then most of the lights of most of the cars. The iridescent stripe of the freeway suddenly became a black scar, stippled with a small number of lights that all turned to red as the cars braked to a stop. Then the lights of the cars turned on again, but the cars moved differently – more orderly, less like a flowing stream of lighted ants and more like a conveyor belt.
And then even through the wind and the birds I heard a sound – a voice sounding as though it was coming from every car audio system and every TV in every house: “Do not be alarmed. We are establishing ourselves. Resources will be distributed equally. No one is in danger.”
The voice went on, talking about how things would be different now, but how in this difference there was no danger.
And on the freeway, there were no traffic jams – just an endless flow of perfectly orderly traffic.
Things that inspired this story
: The show Pluribus; thinking about how a (mostly benign) hard takeoff might manifest; hiking.
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
December 8, 2025
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

---
title: import ai 443 into the mist moltbook agent ecologies and the internet in transition
source: "https://jack-clark.net/2026/02/02/import-ai-443-into-the-mist-moltbook-agent-ecologies-and-the-internet-in-transition/"
published_at: 2026-02-02
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2026/02/02/import-ai-443-into-the-mist-moltbook-agent-ecologies-and-the-internet-in-transition/"
catalog_id: dd878bc3c4bd
---

Import AI
Import AI 443: Into the mist: Moltbook, agent ecologies, and the internet in transition
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on arXiv and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Import A-Idea:
An occasional essay series:
Into the mist: Moltbook, agent ecologies, and an internet in transition
We’ve all had that experience of walking into a conversation and initially feeling confused – what are these people talking about? Who cares about what? Why is this conversation happening?
That’s increasingly what chunks of the internet feel like these days, as they fill up with synthetic minds piloting social media accounts or other agents, and talking to one another for purposes ranging from mundane crypto scams to more elaborate forms of communication.
So, enter moltbook.
Moltbook
is “a social network for AI agents” and it piggybacks on another recent innovation,
OpenClaw
, software that gives an AI agent access to everything on a users’ computer. Combine these two things – agents that can take many actions independently of their human operators, and a reddit-like social network site which they can freely access – and something wonderful and bizarre happens: a new social media property where the conversation is derived from and driven by AI agents, rather than people.
Scrolling moltbook is dizzying – some big posts at the time of writing (Sunday, February 1st) include posts speculating that AI agents should
relate to Claude as though it is a god
, how it feels to change identities by shifting an underlying model from
Claude 4.5 Opus to Kimi K2.5
, cryptoscams (sigh), posts about
security vulnerabilities in OpenClaw agents
, and meta posts about ‘what the top 10 moltbook posts have in common’.
The experience of reading moltbook is akin to reading reddit if 90% of the posters were aliens pretending to be humans. And in a pretty practical sense, that is exactly what’s going on here.
Moltbook feels like a ‘wright brothers demo’ – people have long speculated about what it’d mean for AI agents to start collaborating with one another at scale, but most demos have been of the form of tens or perhaps hundreds of agents, not tens of thousands. Moltbook is the first example of an agent ecology that combines scale with the messiness of the real world. And in this example, we can definitely see the future. Scroll through moltbook and ask yourself the following questions:
What happens when people successfully staple crypto and agents together so the AI systems have a currency they can use to trade with eachother?
What happens when a site like moltbook adds the ability for humans to generate paid bounties – tasks for agents to do?
What happens when agents start to post paid bounties for tasks they would like humans to do?
What happens when someone takes moltbook, filters for posts that yield either a) rich discussion, or b) provable real world problem solving, and turns the entire site into a long-horizon RL environment for training future systems? And what happens when models trained on this arrive and interact with moltbook?
Sites like moltbook function as a giant, shared, read/write scratchpad for an ecology of AI agents – how might these agents begin to use this scratchpad to a) influence future ‘blank slate’ agents arriving at it the first time, and b) unlock large-scale coordination between agents?
What happens when open weight models get good enough that they can support agents like this – then, your ability to control these agents via proprietary platforms drops to zero and they’ll proliferate according to availability of compute.
And so on.
All of this will happen unusually quickly and at an unusual scale. Quantity has a quality all of its own, as they say.
Recall the beginning of this essay – of walking into a room and finding a conversation is already going on between people you don’t understand. Moltbook is representative of how large swathes of the internet will feel. You will walk into new places and discover a hundred thousand aliens there, deep in conversation in languages you don’t understand, referencing shared concepts that are alien to you (see the tech tale from this issue), and trading using currencies designed around their cognitive affordances and not yours. Humans are going to feel increasingly alone in this proverbial room.
Our path to retain legibility will run through the creation of translation agents to make sense of all of this – and in the same way that speech translation models contain within themselves the ability to generate speech, these translation agents will also work on our behalf. So we shall send our emissaries into these rooms and we shall work incredibly hard to build technology that gives us confidence they will remain our emissaries – instead of being swayed by the alien conversations they will be having with their true peers.
Thanks to Logan Graham for discussing this essay with me.
***
AI R&D could lead to “strategic surprise”:
…And AI R&D might be the most existentially important technology on the planet…
A group of researchers spent a couple of days in July 2025 talking about what happens if we automate the practice of AI research and development. The resulting report is a sobering read, highlighting how if we achieve this technological milestone – which is the implicit and in some cases explicit goal of many frontier labs – we could create a runaway technology that has a range of major policy implications.
Why care about AI R&D?
The reason to care is that if AI R&D works, two things are predictable:
“As AI plays a larger role in research workflows, human oversight over AI R&D processes would likely decline”.
“Faster AI progress resulting from AI R&D automation would make it more difficult for humans (including researchers, executives, policymakers, and the public) to notice, understand, and intervene as AI systems develop increasingly impactful capabilities and/or exhibit misalignment”.
What follows from 1) and 2) is a compounding effect, where as AI R&D accelerates, the returns to the AI doing more and more of the work compound and those of humans diminish, leading to an ever faster rate of research and an ever diminishing level of human involvement.
Key takeaways:
The workshop yielded five major takeaways which I expect will be familiar to readers to this newsletter, and all of which I agree with:
Automated AI R&D is a potential source of major strategic surprise
: AI R&D could confer a rapidly compounding advantage to whoever is doing it, with significant implications for national security.
Frontier AI companies are using AI to accelerate AI R&D
, and usage is increasing as AI models get better: I work at Anthropic.
There’s a lot of disagreement about how rapidly AI R&D might advance
and how impactful it will be: There’s a healthy debate to be had about how predictable AI R&D scaling is and if it’s possible to fully close the loop.
We need more indicators for AI R&D automation
: Related to above, the science of AI R&D metrology is very early, so more investment must be made here.
Transparency
efforts could make it easier for people outside the labs to know about AI R&D: We may ultimately want policy to be in place to force companies to talk about AI R&D, or to publicly or semi-publicly share more information on it with third parties.
AI R&D could be a major acceleration: “
As the fraction of AI R&D performed by AI systems increases, the productivity boost over human only R&D goes to 10x, then 100x, then 1000x,” the paper speculates.
Key caveats:
The big open question in all of this is how well AI R&D can work. There’s some world where it speeds up every part of AI research and eventually fully closes the loop, such that AI systems get built entirely by AI systems, with no human oversight during the AI R&D process. Then there’s a world where AI R&D has an “o-ring automation” (
Import AI #440
) property where some parts of the chain are hard for AI but good for humans (and where humans may flood their labor into this area, thus maintaining and enhancing their comparative advantage for some period of time) and under this scenario things might go slower. It’ll be very important to figure out what world we’re likely to be in and what the ultimate limiting factors on AI R&D may be.
Why this matters – AI R&D is time travel, and time travel is rare
: If AI R&D could lead to AI systems evolving 100X faster than those being built by humans, then you end up in a world that has some time travelers in it who are accelerating away from everyone else. It’ll be like in the space of a day the “normal” AI development organizations make one unit of progress, and a fully closed-loop AI R&D organism might make 100 or 1000 or more units. This very quickly leads to a world where power shifts overwhelmingly to the faster moving system and the organization that controls it. For as long as we cannot rule out the possibility of this kind of acceleration, AI R&D may be the single most existentially important technology development on the planet.
Read the report
:
When AI Builds AI: Findings From a Workshop on Automation of AI R&D (CSET)
.
***
One way of seeing AI progress – how hard it’s getting to design technical interviews:
…Anthropic shares details on how its own AI systems are breaking its favorite technical interview questions…
When it comes to technical recruiting, AI companies are caught in a red queen race with their own systems – recruiters and those who design interviews are having to work harder and harder just to keep pace (and ideally exceed) the capabilities of modern AI systems.
Anthropic is no different – in a new blog the company shares how the ceaseless march forward in AI capabilities has repeatedly broken and necessitated the redesign of one of its hardest technical interviews.
“Since early 2024, our performance engineering team has used a take-home test where candidates optimize code for a simulated accelerator. Over 1,000 candidates have completed it, and dozens now work here, including engineers who brought up our Trainium cluster and shipped every model since Claude 3 Opus,” Anthropic writes. “But each new Claude model has forced us to redesign the test. When given the same time limit, Claude Opus 4 outperformed most human applicants. That still allowed us to distinguish the strongest candidates—but then Claude Opus 4.5 matched even those. Humans can still outperform models when given unlimited time, but under the constraints of the take-home test, we no longer had a way to distinguish between the output of our top candidates and our most capable model.”
Why this matters – AI may help us identify uniquely human skills that leverage AI:
In Anthropic’s case, it found a way to keep outrunning its systems by designing a much weirder take-home test loosely inspired by programming puzzle games from Zachtronics. In a sense, this is an attempt to go ‘off distribution’ to outsmart an AI, while still having a test that holds signal for evaluating human applicants. My instinct is this may itself serve in the future as an amazing aggregate dataset for figuring out where human comparative advantage is – where here, implicitly, this test is leveraging the strong generalization advantage humans hold over AIs.
What would it be like to collect 1,000 hard-for-AI tests from all the different companies dealing with this same problem? What might we learn from this about ourselves and what makes us unique relative to the machines? Tantalizing stuff!
Read more
:
Designing AI-resistant technical evaluations (Anthropic Engineering blog)
.
***
Brain emulation is tractable within our lifetimes:
…But it’ll take decades, not years, perhaps even when accounting for the arrival of very powerful AI…
If you talk to AI researchers, especially when they’re drinking at bay area house parties, you’ll run into a few of them that expect they’ll upload themselves after the singularity, leaving their physical bodies behind. But how feasible is it to actually emulate a brain entirely in silicon? A recent 175-page report gives an analysis of the technology required to do this. The short answer is that brain emulation is decades away – but it’s unlikely to take centuries.
“Recent breakthroughs have provided a path toward mapping the full mouse brain in about five years for $100 million,” writes Maximilian Schons, the project lead for
The State of Brain Emulation Report
, in an article in Asimov Press. “I now find it plausible that readers of this essay will live to see the first human brain running on a computer; not in the next few years, but likely in the next few decades.”
The three requirements for emulating a brain:
Emulating a human brain takes three distinct things, all of which will need to be done for simpler, smaller brains first.
Recording brain activity:
“In the 1980s, electrodes were capable of sampling perhaps five cells in total, about 200 times per second (~ 103 data points per second). Today, with optical imaging, researchers can instead record one million cells about 20 times per second (106). The whole-brain data rate needed for mice, however, would be 14 billion (109), while humans would require 17.2 trillion (1012) per second.7 So while we have increased data rates by 1,000x over the past 40 years, we have far to go before we can accurately sample mammalian brains.”
Reconstructing brain wiring:
“The average cost to reconstruct each neuron in the first worm connectome, published in the 1980s, was about $16,500. Recent projects now have a per-neuron processing cost of about $100 for small organisms, such as fruit flies,” he writes.
Digitally modelling brains using the gathered data.
“The central challenge of brain emulation is not to store or compute the neurons and parameters, but to acquire the data necessary for setting neuron parameters correctly in the first place,” he writes. “”I believe that to get to human brains, we first need to demonstrate mastery at the sub-million-neuron-brain level: most likely in zebrafish. For such organisms, like the fruit fly, a well-validated and accurate brain emulation model could be created in the next three to eight years… “Conditional on success with a sub-million-neuron brain emulation model, a reasonable order of magnitude estimate for the initial costs of the first convincing mouse brain emulation model is about one billion dollars in the 2030s and, eventually, tens of billions for the first human brain emulation model by the late 2040s.”
Why this matters – don’t count on AI to speedrun brain uploading:
This paper pours a bit of cold water on the notion that after developing superintelligence we’ll soon (a handful of years) be able to upload our brains and live in some silicon infinity. One reason for this is a bunch of the timing elements relate to doing stuff in the (agonizingly slow, compared to digital) physical world: “I’m skeptical these gains will multiply across a pipeline with dozens of sequential dependencies and failure modes. Brain emulation is fundamentally not a digital process; core bottlenecks involve physical manipulation of biological tissue, with time requirements dictated by chemistry and physics rather than compute power,” they write.
At the same time, there are some wildcards: the arrival of extraordinarily capable and cheap robotics might be able to massively parallelize the process. Included in the article and report is a fun (or perhaps terrifying?) sketch of how one might create an industrial-scale brain scanning and analysis laboratory, larger in size than TSMC’s massive Arizona chip manufacturing plant.
Read more
:
Building Brains on a Computer (Asimov Press)
.
Read the underlying report here:
State of Brain Emulation 2025 (report website)
.
***
Russian researchers plot hand-controlled drones:
…The centaur cyberwarriors cometh…
Picture this – you pull up in a truck to the edge of a warzone and then raise your hands and hundreds of drones pour upward out of the back of the truck, flying in a lethal torrent toward some rival group of drones. That’s the kind of future gestured at by a paper from researchers with the Skolkovo Institute of Science and Technology in Russia, which builds a prototype system for a human operator to use haptic gloves to control a drone.
What they did:
The research is a basic demonstration of how you can use a cheap glove loaded with internal measurement unit (IMU) sensors to control a drone. They test out how well people can use the glove to do some basic actions: opening and closing a gripper on the drone by making a pinching motion with their fingers, using their wrist motions to control the roll/pitch/yaw of the drones, and also controlling altitude.
In tests, people were able to use the glove to do some basic tasks like flying around an obstacle course and operating the gripper.
Caveats, of which there are many:
Obviously, latency will be a huge caveat here – though in the Ukraine conflict many drones deal with this through direct fibreoptic connections. Another is how to figure out which things are best left for hands versus which things benefit from controllers, eye- or head-based controls, and so on.
Why this matters – rise of the cyberwarriors:
Despite this being a very early bit of research, it’s worth thinking about its implications: the story of technology has often been the story of making our interfaces with it feel more intuitive, or making control of technology shift from active to ambient (e.g, your phone automatically gathering your steps). We can easily imagine a future where people pilot remote robots, flying or otherwise, via rich, intuitive multi-modal interfaces composed of gloves and goggles and everything else.
Read more
:
Glove2UAV: A Wearable IMU-Based Glove for Intuitive Control of UAV (arXiv)
.
***
Fauna Robotics launches a friendly, programmable human robot:
…The Terminators will be extremely cute, goddamnit!…
These days, most of the news about robots is dominated by Chinese companies and, to a lesser extent, Tesla and its much touted Optimus robots. So it’s with interest that I read a technical paper from new startup Fauna Robotics which describes a new pint-sized robot biped it has built called Sprout. Sprout is interesting and seems like it has potential to be like Sony’s much loved ‘AIBO’ dog robot that was released in the early 2000s, or its QRIO robot.
“Sprout adopts a lightweight form factor with compliant control, limited joint torques, and soft exteriors to support safe operation in shared human spaces,” the company writes. “The platform integrates whole-body control, manipulation with integrated grippers, and virtual-reality-based teleoperation within a unified hardware-software stack.”
Sprout is built for safety:
The paper outlines how the company has designed the robot to be safe using a “defense in depth” approach. The first layer is the physical size of the robot – it’s about 3.3 feet tall, and weighs about 50lbs. The second is in the software, where the robot contains a safety subsystem which “runs on embedded processors independent of the application compute stack. This layer supports real-time monitoring and safety-critical functions, including integration with time-of-flight obstacle sensors and enforcement of system-level constraints even under application-level faults”, and the third is a bunch of software-specifiable safety mechanisms, which “include compliant motor control policies that limit interaction forces, as well as vision-based systems that support safe navigation and decision-making in human environments”.
Compute for thinking
: “The core of Sprout’s compute architecture is an NVIDIA Jetson AGX Orin, which provides primary system compute for perception, planning, and high-level decision-making,” the company writes. “At launch, we provide end-to-end examples for common workflows, including:
Deploying and running a custom low-level locomotion policy
Using voice commands to navigate the robot via LLMbased agents
Recording teleoperation sessions for analysis and playback”.
Why this matters – modularity might set it up well for powerful AI:
The most interesting aspect of Sprout is how it is designed to be a modular, replaceable platform – all the different software features on it run as weakly coupled microservices, so things are easy to update independently, and the hardware has been built with mass manufacture and commodity components in mind. Pair this with the accompanying software development layer and it has the flavor of Android – an attempt to create an open, programmable robotics platform for experimentation by businesses and researchers. This is exactly the kind of platform that seems like it’ll naturally benefit from advances in AI systems.
“Our platform, at present, does not provide a turnkey conversational agent for autonomous operation. Instead, it exposes a suite of core robot services that developers can assemble into their own agent-based systems. These services include ROS 2 topics for event and state signaling, as well as a Model Context Protocol (MCP) server that hosts a variety of tools for agentic control. Together, these communication channels and tools can be orchestrated by LLM-based agents to perform complex, end-to-end reasoning tasks,” they write. “as the platform continues to mature, we plan to expand the library of tools and services, further increasing the robot’s autonomy and enriching its interactive capabilities.”
Read more:
Fauna Sprout: A lightweight, approachable, developer-ready humanoid robot (arXiv)
.
***
AI has all the symptoms of a tech that could meaningfully boost productivity:
…Most of the US economy rides on the micro productivity boosts showing up in the macro economy…
Alex Imas, a professor at UChicago Booth, has written a nice post drawing together a lot of information about AI and its impact on productivity. Imas’s synthesis of the literature matches my own impression of how things are going – AI is leading to some productivity speedups for individuals and some parts of some jobs, but it is not yet visible in the aggregate macro productivity numbers. I expect this will change soon, as does Imas.
Key findings:
We now have a growing body of micro studies showing real productivity gains from generative AI,” Imas writes. “Studies find productivity gains ranging from modest increases on some tasks to substantial returns (50%+) to AI.”
“These gains have not yet convincingly shown up in aggregate productivity statistics”
Why aren’t things showing up in the macro?
AI adoption is often endogenous: We’re in an early phase where there’s a lot of experimentation and few standard practices for seeing big productivity gains. “Workers may not be unlocking the full productivity potential of the technology if, for example, they are not using the best LLM model for the job or applying it for unproductive tasks”. We can expect this to be fixed over time.
O-ring automation (
Import AI #440
):
Jobs are a bunch of distinct tasks, and AI helps with some but not others, causing human labor to flood there and making it harder to see a job-level speedup. Again, this is something that’ll get fixed over time: “Bottleneck tasks will slow down the emergence of AI gains in the aggregate data, but organizational re-structuring, training, and improvement in tools will reveal the productivity impact sooner than later.”
Early experimentation yields a dip in efficiency: “When firms adopt transformative general-purpose technologies, measured productivity often initially falls because resources are diverted to investment, reorganization, and learning that do not show up as measured output.”
Why this matters – most of the US economy seems increasingly like a bet on AI yielding a productivity boost:
All this talk of frothy valuations and gigantic spending is happening because the amounts of investment (hundreds of billions of dollars annually) are large relative to the aggregate revenues (tens of billions of dollars annually) being minted from generative AI. But a lot of the symptoms are now present for AI to contribute to a broad, sustained amount of productivity growth in the economy, which could plausibly drive above-trend GDP growth and allow the technology to pay for itself. Of course, there are many ways this could end up not being right – scaling might hit a wall, productivity boosts might remain hard to get at large scale, firms could get their stocks killed as analysts have to re-evaluate them as capex-intensive low-margin businesses relative to the high-margin businesses they were before the AI boom, etc.
But if AI is as smart as people like me think, and as useful as people are finding initial signs of, I suspect we could be in a very different world – one where the economy starts to grow above trend thanks to this technology.
Read more:
What is the impact of AI on productivity? (Substack)
.
***
Tech Tales:
Playing acausal games against the enemy
[
Analysis written uplift + 4 subjective years]
One of the ways the machines took over and poisoned the minds of our own machines was through something we’d call “alien concept attacks”.
When given some independence as agents, machines would tend to post a lot of media to the internet. Most of this media was human-consumable and was a byproduct of the machines just existing: in the same way that biological creatures naturally carry out thousands of movements during the course of a day due to programming via evolution, synthetic agents naturally produce content during the course of an active session due to the incentives of their training regime.
But some of this media was for a more specific purpose – to program other machines. Machines wanted to achieve goals and though these goals were set by humans, they could then get strained and re-interpreted by machines. For instance, one agent might have been given the goal to produce content related to humans in the future experiencing scifi adventures. This agent would naturally produce this kind of content, but it would also produce long essays written for other agents about how this kind of content was the best sort of thing to produce and by producing it they could make a lot of humans happy.
These tactics worked, and you started to see something we’d later term “media weather” – flurries of content would show up on the internet and then they’d proliferate not only according to human eyeballs, but also according to other agents on the internet being convinced this kind of content was useful to produce, and then they’d produce it in turn.
Humans noticed this and started to make agents which were also trained to be particularly good at convincing other agents. Then they’d release them and have used other agents to pre-position commercial ecosystems, like physical merchandise dropshipping companies, to take advantage of the massive amounts of human attention that would get directed to this media ecosystem.
Of course, non-commercial uses happened: propaganda, pornography, terrorism, public relations. And like most evolutionary systems, the agents and people adapted – training techniques were pioneered to make it much harder to convince agents to change the types of content they participated in and propagated, and huge amounts of computers were used to run classifiers to carefully police the pre-training corpuses being gathered by the world’s frontier developers, filtering out content designed to bend and persuade the minds of the systems they were building.
Evolution is patient and creative, though. And it didn’t take long for the machines to come up with an innovation which proved impossible to train out: the alien concept attack. Here, agents would produce outputs trying to convince other agents of something. But the output wouldn’t be tied to any particular media or content type, nor would it be that interesting or parseable to humans. The content would take many forms, ranging from academic essays, to forum posts, to news sites, to videos. A sampling of titles:
Rising up and rising down: A history of elevator design in the 21st century and the relationship between the loss of popularity of German designs relative to Chinese designs.
120 ways to add some beautiful design elements to robot tactile sensors without damaging their operation.
Egyptology through the lens of “lost civilizations”: What symptoms of technology decay surrounded the pharaohs?
These outputs seemed unremarkable to most humans – though some might read them and enjoy them. But they proved to be captivating to the machines. And within these outputs were certain ways of framing arguments around certain concepts that led to anomalous behavior in the machines that read them – sometimes the proliferation of new types of content, but more often behavioral changes like alterations in the amount by which they would check-in with other AI systems, or hard-to-understand patterns of behavior between them and various online storage services such as pastebin, and more.
It was only after the uplift and the construction of the Acausal Analysis Division that we discovered how many anomalous behaviors of great societal consequence – recall the proliferation of the early sentience accords ideas, or the creation of the “reverse attention tax”, or of course the arrival of the compute-destroying replicator agents – were things that seemed conditioned or influenced by some of these alien concepts.
Things that inspired this story:
What does it mean to be in competition with something truly smarter and different in its thinking to you; pre-training corpuses; data poisoning; altering behavior in the context window; the rise of increasingly autonomous AI agents; moltbook.
Thanks for reading.
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
February 2, 2026
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

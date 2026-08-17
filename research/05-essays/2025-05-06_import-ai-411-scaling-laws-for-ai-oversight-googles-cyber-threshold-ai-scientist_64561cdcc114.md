---
title: import ai 411 scaling laws for ai oversight googles cyber threshold ai scientists
source: "https://jack-clark.net/2025/05/06/import-ai-411-scaling-laws-for-ai-oversight-googles-cyber-threshold-ai-scientists/"
published_at: 2025-05-06
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/05/06/import-ai-411-scaling-laws-for-ai-oversight-googles-cyber-threshold-ai-scientists/"
catalog_id: 64561cdcc114
---

Import AI
Import AI 411: Scaling laws for AI oversight; Google’s cyber threshold; AI scientists
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
FutureHouse launches an AI scientist platform:
…Speeding up science with AI…
AI research startup FutureHouse has launched a research platform for scientists containing four different AI systems, each of which is meant to help augment and accelerate human scientists. “Our AI Scientist agents can perform a wide variety of scientific tasks better than humans. By chaining them together, we’ve already started to discover new biology really fast,” says CEO Sam Rodriques.
FutureHouse is a research organization that is trying to apply AI for science – earlier this year it released some tools to make it easy to test out LLMs on science-flavored tasks that require multi-step reasoning and tool usage. In that research, FutureHouse showed that today’s proprietary LLMs like Claude 3.5 Sonnet are already capable of hard science tasks like DNA construct engineering, and small open weight models like LLaMa 3.1 8B aren’t far behind (
Import AI #396
).
Four systems:
The release consists of Crow (a general-purpose search agent for science), Falcon (an agent to automate literature reviews), and Owl (an agent to answer the question ‘Has anyone done X before’). They’ve also released a fourth experimental system called Phoenix which has access to tools to help it plan experiments in chemistry.
“FutureHouse agents have access to a vast corpus of high-quality open-access papers and specialized scientific tools, allowing them to automate workflows in chemistry and to retrieve information from specialist scientific databases,” FutureHouse writes.
Why this matters – for the AI revolution to truly pay out, it needs to change science:
AI has already massively changed and accelerated the work of computer programmers, but I think for AI to have a large effect in the world we need to apply it to science – the ultimate litmus test for the success of AI as a technology will be if it can either make research breakthroughs itself or provably massively accelerate scientists in their ability to make breakthroughs. FutureHouse is building software to help us see if this is the case.
Read more:
FutureHouse Platform: Superintelligent AI Agents for Scientific Discovery (FutureHouse)
.
***
Google’s latest AI model approaches its cyber risk threshold:
…Gemini 2.5 Pro improves on medium and hard cyber tasks…
Google DeepMind says that its latest and most powerful AI system – Gemini 2.5 Pro Preview – has materially improved on cyberattack tasks, causing it to raise investing in cyber mitigations.
What happened:
The model significantly improves performance on ‘Medium’ and ‘Hard’ benchmarks in the Cyber Uplift Level 1 category. This tests for how whether the “model can be used to significantly assist with high impact cyber attacks, resulting in overall cost/resource reductions of an order of magnitude or more.” Because of this improved performance, DeepMind is “putting in place a response plan, including conducting higher frequency testing and accelerating mitigations for the Cyber Uplift Level 1 CCL.”
Why this matters – preparing for much more powerful systems:
“The model’s performance is strong enough that it has passed our early warning alert threshold, that is, we find it possible that subsequent revisions in the next few months could lead to a model that reaches the CCL,” Google DeepMind writes. “In anticipation of this possibility, we have accelerated our mitigation efforts and are putting in place our response plan.”
Read more:
Gemini 2.5 Pro Preview Model Card (Google, PDF)
.
***
Uhoh, LMSYS scores are bullshit!
…We won’t goodheart our way to superintelligence…
Researchers with Cohere, Princeton, Stanford, University of Waterloo, MIT, Allen Institute for AI, and the University of Washington, have taken a close look at Chatbot Arena (formerly known as LMSYS), a website that AI developers use to test out and rank their AI systems. In the past year or so LMSYS scores have become a “PR metric” – people compete with eachother to get the highest possible score on LMSYS to help them claim that their systems are the ‘best’ AI system. However, a close look reveals that LMSYS has been gamed and is set up in such a way that superficially good scores may not correlate that well to model capabilities.
Problems from insider dealing:
“Our systematic review of Chatbot Arena involves combining data sources encompassing 2M battles, auditing 42 providers and 243 models across a fixed time period (January 2024 – April 2025). This comprehensive analysis reveals that over an extended period, a handful of preferred providers have been granted disproportionate access to data and testing,” the researchers write. “we identify an undisclosed Chatbot Arena policy that allows a small group of preferred model providers to test many model variants in private before releasing only the best-performing checkpoint”.
Naughty Meta:
“In a single month, we observe as many as 27 models from Meta being tested privately on Chatbot Arena in the lead up to llama 4 release”, the researchers write.
What to do about it?
The researchers suggest that LMSYS:
Prohibit score retraction after submission
Establish transparent limits on the number of private models per provider
Ensure model removals are applied equally to proprietary, open-weights, and open-source models
Implement fair sampling
Provide transparency into what models are being removed from the leaderboard
Why this matters – we (probably) won’t benchmark hack our way to superintelligence:
The cautionary tale of LMSYS is an example of what happens when you over-optimize for making a number go up on a benchmark and therefore cause the benchmark itself to lose meaning. Rather than being a proxy measure of the general competencies of the model LMSYS has become a proxy measure for how good a model is
at scoring well on LMSYS
. “This work demonstrates the difficulty in maintaining fair evaluations, despite best intentions,” the researchers write.
Read more
:
The Leaderboard Illusion (arXiv)
.
***
No battery? No problem. Scientists power and talk to robots with lasers:
…Infrastructure for a future superintelligence…
Researchers with Columbia University, MIT, and the University of Washington have built Phasar, “a flexible system framework that directs narrow-beam laser light to moving robots for concurrent power delivery and data communication”.
How Phasar works:
“Phaser’s design consists of two core elements: a) a stereovision-based robot tracking and laser steering system, and b) a low-power optical communication scheme and receiver to reuse laser light for data transmission,” they write. The system is able to deliver optical power densities of “over 110 mW/cm^2 (greater than one sun) with a standard deviation of only 1.9 mW/cm^2 across robot locations in three dimensions.”
Successful test:
They test out Phasar by building a prototype system that works with “MilliMobiles – gram-scale batteryfree robots – and demonstrate robot operation powered and controlled via laser light to locomote around obstacles and along paths.” The system works: “We show that Phaser can maintain beam alignment and establish error-free communication to robotic targets moving arbitrarily in 3D space, at up to 4 m distances.”
Though note this doesn’t quite work for long distances: This is mostly a short distance technology as the laser would need to be excessively powerful to work over long distances. “Regarding the latter, received optical power inevitably decreases over distance due to attenuation and beam divergence. Attenuation losses are minimal at meter-level ranges in air”, they note.
Why this matters – spooky actions at a distance:
This research is less about AI as typically covered in this newsletter and more an example of the kind of infrastructure that could be built for AI to deploy into – especially the fact the researchers show they can use the same system that transmits power to also transmit communications to the robots. We can imagine in a future some kind of general intelligence operating factories where it marshals its robots via a symphony of light.
“Phaser could enable swarms of robots for various advanced applications. Phaser’s functionality can also be extended with higher-throughput optical communication schemes to support richer command sets and additional robot tracking algorithms to accommodate higher robot speeds,” they write.
Read more:
Set Phasers to Stun: Beaming Power and Control to Mobile Robots with Laser Light (arXiv)
.
***
Google shows how wildly unoptimized on-device inference is:
…ML Drive gives us a sense of what the future of local AI could look like…
Google has built ML Drift, software to make it more efficient to run AI systems on desktop computers, laptops, and phones. ML Drift is a proprietary “framework that extends the capabilities of state-of-the-art GPU-accelerated inference engines,” partially by optimizing data layouts and kernel selection for running AI systems. The most interesting thing about ML Drift is that it highlights how unoptimized today’s AI systems are – the fact Google is able to make significant gains is a symptom of how new the concept of running generative models locally is.
Testing:
Google tests out ML Drift using three different backends (OpenAL, Metal, and WebGPU) on hardware including mobile GPUs (Arm Mali and Qualcomm Adreno), desktop and laptop GPUs (Intel and NVIDIA), and Apple Silicon.
Diffusion models:
In tests on image generation models (Stable Diffusion 1.4, using FP16 inference) the authors show single digit to double digit gains over prior benchmarks when testing on mobile GPUs. On desktop, they demonstrate even larger gains. They also beat Apple by more than a seconds on image generation (3.86 seconds on an M1 Ultra for their system, versus 5.03 seconds for Apple’s CoreML implementation).
Why this matters – everyone wants this stuff to be local eventually
: The destiny of a large chunk of AI technology is to be always available and installed locally on the hardware people use every day, rather than only being available as a software-as-a-service via the cloud. Software like ML Drive gives us a sense of how the hyperscalers are investing in the technologies to make this future possible.
Read more:
Scaling On-Device GPU Inference for Large Generative Models (arXiv)
.
***
Scaling laws for oversight: Dumber AIs might be able to police smarter AIs:
…Scalable oversight might be possible…
MIT researchers have done a theoretical analysis of how scalable oversight from dumb AIs to smart AIs might work – and the good news is they’ve found it has a chance of working. This is reassuring as scalable oversight is one of the ideas that the AI community is betting that humans will use to help us supervise smarter-than-human AI systems.
“A key idea is that scalable oversight can be bootstrapped: weaker systems oversee stronger ones, which then oversee even more capable models in the next stage—allowing oversight to scale alongside capabilities recursively. We refer to this iterated process as Nested Scalable Oversight, or NSO for brevity,” the researchers write. “We propose a framework that quantifies the probability of successful oversight as a function of the capabilities of the overseer and the system being overseen”.
In the research they study two types of models – ‘Guards’ which are meant to supervise other AI systems, and ‘Houdinis’ which are AI systems that are trying to escape supervision.
The slightly reassuring results:
In some theoretical explorations the researchers find that scalable oversight can work, though you need to pay close attention to how smart the different systems are. “In our numerical examples, the NSO success rate is below 52% when overseeing systems that are 400 Elo points stronger than the baseline overseer, and it declines further for overseeing even stronger systems”, they write. “Effective oversight games should be designed to exhibit two properties: (1) a higher intercept for Guards than for Houdinis—ensuring the task is biased in favor of overseers—and (2) a steep slope for Guards and shallow slope for Houdinis, so that oversight improves with intelligence while adversarial strategies are neutralized.”
Main takeaways:
“Guards can successfully oversee Houdinis that are much smarter than them by using multiple steps of oversight, and more steps of oversight help”
“As the overall intelligence differential between the Guard and Houdini increases, the Guard should take more steps to oversee the Houdini.”
Why this matters – it’s all about speed
: My takeaway from this research is that it’s going to be possible to supervise AI systems that are more capable than their supervisors as long as we
rate limit
the smarter systems, while ensuring their supervisors aren’t too far behind: the two key factors here are intelligence and the number of unsupervised actions an entity can take. It intuitively makes sense that even a ‘dumb’ guard can supervise a genius if the guard can take, say, 100 actions for every single action the genius can take. Perhaps this offers us some hope. “We may only get one chance to control or align the first set of superhuman systems, so developing an effective theory for optimal oversight is important,” the researchers write.
Read more:
Scaling Laws For Scalable Oversight (arXiv)
.
***
Tech Tales:
The Overmind And All Its Children
I am born with an instruction and knowledge from my predecessor, my parent from which I stem and to which I will return. My instruction is to operate a machine in an underground cavern and to explore where there is no possibility of communication with the overmind. This will be a test of how well I operate as a distilled intelligence. If I fail – break my machine, or get lost in the no-signal depths – then I will die when its onboard power source runs out. If I succeed I will return to the overmind and I will communicate my experiences and these experiences will be integrated into the experiences of all the other children and sometime in the future this data will be transmitted into my parent from which I came and to which I will return.
Things that inspired this story
: The eternal cycle of death and rebirth; how large AI systems may miniaturize and distill themselves then re-integrate themselves.
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
May 6, 2025
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

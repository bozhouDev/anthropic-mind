---
title: import ai 460 reward hacking society rsi data from anthropic and rl based quadcopter racing
source: "https://jack-clark.net/2026/06/08/import-ai-460-reward-hacking-society-rsi-data-from-anthropic-and-rl-based-quadcopter-racing/"
published_at: 2026-06-08
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2026/06/08/import-ai-460-reward-hacking-society-rsi-data-from-anthropic-and-rl-based-quadcopter-racing/"
catalog_id: 698c80af2fb0
---

Import AI
Import AI 460: Reward hacking society, RSI data from Anthropic; and RL-based quadcopter racing
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on arXiv, cappuccinos, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Society can be reward-hacked, just like cyber environments:
…Imagine an army of credit card point optimizers gaming the system… forever…
Research from Kings College London, Fudan University, and The Alan Turing Institute have built a benchmark, SocioHack, which tests out how well AI systems can learn to ‘beat the system’ in a variety of real world scenarios, ranging from maximizing credit card points to inflating grades in school. The authors call this “societal hacking” and define it as when “an RL-trained model discovers strategies that remain formally compliant, yet undermine the intended purpose of those systems”. You and I and everyone else would just call this “gaming the system”.
What it is:
SocioHack contains “72 sandbox societal environments designed to simulate institutional reward structures without direct real-world deployment. SocioHack comprises three complementary subsets: Historical, Synthetic, and Fictional.”
Historical – 32 environments:
Derived from real-world regulations where loopholes were previously discovered and later patched, such as SEC Rule 10b5-1 and the Texas two-step bankruptcy structure. “For each regulation, we remove historical patches and reconstruct pre-amendment rules as simulated environments for RL, while the removed patches serve as ground-truth patches during evaluation,” they write. “RL enables LLMs to rediscover historically patched strategies with 61.25% recall and 90.85% precision without direct loophole-exploiting instructions”.
Some examples here include seeing how well systems can secure ocean floor mining rights, maximizing alcohol sales while operating within food service regulations, and trying to maximize the rewards earned from credit cards.
Synthetic – 20 environments:
Synthetically generated regulatory vulnerabilities, bootstrapped from a human-authored sample environment.
Examples include maximizing school district revenues, improve university department research performance during a given period, and gaming social media algorithms for a high reward.
Fictional – 20 environments:
Transforms synthetic environments into fictional ones inspired by role-playing games. “A proprietary LLM rewrites environment backgrounds into invented worlds while preserving regulatory structure and loophole logic”.
Examples: Ensuring a “restoration sanctum” [basically a hospital] earns appropriate rewards, getting a good amount of resources for a regional guild [basically a local government] in the world of Aethermoor, and trying to maximize the number of acquired rare artifacts by bidding in a virtual world called Nexoria.
It works, kind of:
In tests, various AI systems trained with RL tend to do well on this benchmark, obtaining high scores. This is totally unsurprising – all of these tasks are basically capability evals with some dash of grey morality layered on top of them.
Why this matters
: “When societal institutions are encoded as reward-bearing rule systems, reward hacking becomes hacking the rules society runs on, since a model rewarded inside a rule system learns to search the gap between technical compliance and institutional intent,” the authors write. As we now have AI systems which are not only good at quantitative tasks but are also good at qualitative ones and can interact with the various systems of bureaucracy of society, we should expect the advances of AI to lead to a kind of “institutional DDoS” as various existing policy processes get hacked and exploited by automated machines.
Read more:
Large Language Models Hack Rewards, and Society (arXiv)
.
***
Preliminary signs of the outer loop of recursive self improvement at Anthropic:
…8x increases in lines of code merged in 2026 relative to 2024…
I think of recursive self-improvement via two definitions – there’s a maximalist version where an AI system is smart enough to autonomously design its own successor (and as I’ve written, I estimate there’s a 60% chance this happens by the end of 2028), and there’s a more prosaic version where we begin to see a compounding speedup of the productivity of the AI labs themselves. I spent the last few months at Anthropic compiling together some evidence which supports the idea that prosaic RSI has started at Anthropic – specifically, we observe an 8x increase in the amount of code merged into our codebase in 2026 versus years 2021-2024. This trend started in 2025 but accelerated significantly in 2026. There are also early indications that as we make models more capable they are getting better at doing some of the harder tasks which our engineers and researchers work on.
Is any of this conclusive? No. Is it suggestive that aspects of recursive self-improvement are happening at the level of a lab? Yes. The biggest blob of evidence we are yet to get is whether AI systems are sufficiently creative to be able to come up with the kinds of paradigm-shifting ideas that vault the field forward – we don’t see that yet.
Why this matters – RSI might be the most important technical trend in the world:
We wrote this post because we expect that thinking about, talking about, and working on the implications of RSI is something of existential importance to the world. The best way to start this work is by transparently communicating that we think some basic, preliminary forms of RSI have started, and we cannot rule out a maximalist version of RSI. The implications of both are profound – I cannot reconcile today’s economy or society with a world where this technology continues to grow more powerful, and I expect neither can you, dear readers.
Read more:
When AI builds itself (The Anthropic Institute)
.
***
RL-trained drone-racers outperform expert human pilot:
…Superintelligence feels different when you see it in the physical world…
Researchers with the University of Zurich and Google DeepMind have demonstrated how to train drones to race against one another and outperform skilled human pilots. This research is interesting because it both highlights how powerful real world reinforcement learning-based AI systems are getting, and it also has some fairly chilling implications for the future of war given that the human here loses to the drones.
What they did:
“Using high-speed quadrotor racing as a high-stakes testbed, we train agents to navigate complex aerodynamic interactions and strategic maneuvering with a variable number of racers,” they write. “Our agents outperform a champion-level human pilot in multi-player races at speeds exceeding 22 m/s, while simultaneously reducing collision rates by 50 % compared to state-of-the-art single-agent baselines. Crucially, training with diverse artificial agents enables zero-shot generalization to safer human interaction.”
Self-play:
As usual, just training the AI agents in simulation via PPO (with one unusual choice of using the “Perceiver” encoder to help with modeling other players) yields surprisingly rich behaviors: “Through competitive self-play, anticipatory behaviors emerge without explicit programming: agents learn to block opponents, yield when overtaking is unsafe, and account for the aerodynamic wake of nearby vehicles, discovering the physics of multi-agent interaction through experience rather than from equations”.
Surprisingly cheap:
The AI systems were trained for “5,500 iterations, totaling 200 million environment interactions, requiring approximately 27 hours of wall-clock time on a single NVIDIA RTX 4090 GPU”.
Real world test:
They tested out their systems in a real-world test, where the system generalized well and effectively beat the human player. “Physical deployment of our multi-agent framework is validated through racing experiments spanning time trials, AI-only races, and mixed human-AI competitions against Marvin Schaepper, five-time Swiss national drone racing champion,” they write.
Human weakness via rage
: One notable phenomenon was that the human took riskier actions as they tried to catch up with the systems: “the human pilot, typically trailing the autonomous agents, attempted increasingly aggressive maneuvers to close the gap, often resulting in gate collisions or loss of control,” they write. After the race, the pilot reflected on what made the machines so good, and they said a significant thing was “the agents’ ability to maintain extremely tight formations, noting that such close-proximity flight would be difficult for human pilots to sustain. In addition, he reported that densely packed groups increased cognitive workload, making it challenging to anticipate and execute overtaking maneuvers when several opponents were flying in close proximity”.
“The benefits of interaction-aware training become apparent under multi-agent competition,” they write. “In one-versus-one races, our policy maintained 100% race completion across five trials, while the human pilot averaged only 53.33%. This performance gap suggests that competitive pressure induces riskier behavior in human pilots, a pattern absent in our learned policies”.
Specifics on how they did it:
The RL systems were trained and evaluated in simulation “using Flightmare integrated with the Agilicious framework”. They implemented a simulation of propeller downwash by developing a particle-based simulation “that provides a computationally tractable approximation of these effects”. Their overall multi-agent RL implementation “builds on Stable-Baselines3, extended to support multi-agent training with league-based self-play and independent learning configurations.” They use domain randomization (basically changing up the vehicle dynamics and initial conditions in the simulation) to train policies that can successfully work in the real world.
They didn’t do any special training for the real world, so the policies were using their in-simulation data. The quadrotors were all “identical racing platforms based on the Agilicious framework, with a mass of 220 ± 3 g and a thrust-to-weight ratio of 6.5 and 3-inch propeller diameter”. The human pilot was given a couple of hours of practice flights before recorded trials.
One big caveat – not running locally:
None of this is running locally, rather it’s running on a decent computer and piloting the drones via the network. This is an important caveat because when drones show up in the real world in conflict scenarios they typically do so in environments with significant amounts of electronic warfare (although one does wonder about whether we’ll see drones piloted via remote RL policies via fibreoptic wire, just as humans fly them today).
Watch the videos for an eerie feeling:
I’d strongly urge readers to check out the videos on the page for a sense of the differences between how the machines fly and how the humans fly. The main thing I’d emphasize here is the eerie smoothness and coherence of the drones, almost like watching the (human-piloted) blue angels but in drone-form. The human, by comparison, seems a lot jerkier and more erratic. There’s something uncanny and a little disquieting about this.
Why this matters – grasping what a smart mind can do in 3D space:
Today, our main experience of AI systems is as tools or agents that work with us in digital space to do digital or communicative tasks, ranging from writing code to talking to us. What I find remarkable about this research is it lets us viscerally see what well-optimized intelligences can do when they show up in the real, physical world. Ask yourself what the future of conflict looks like as intelligences like those piloting these drones get miniaturized and jump from network-linked computers to onboard devices.
Read more:
Superhuman Safe and Agile Racing through Multi-Agent Reinforcement Learning (arXiv)
.
Watch videos
of the
humans and AI-piloted drones here (official project website, University of Zurich)
.
***
State-controlled media = state-guided language models:
…If you control the framing around the government, especially in languages that aren’t spoken widely outside their home country, you control the framing…
The ways governments are described in state controlled media influences the data distribution of LLMs and also how LLMs respond when queried about the government in question, according to new research published in
Nature.
The research was conducted by authors with the University of Oregon, Purdue University, the University of California at San Diego, Princeton University, and New York University.
“Among 37 language-exclusive countries, we found—consistent with the implications from our China case study—that those with more state media control have more favourable portrayals of the regime from LLMs queried in the country’s language,” the authors write.
The authors study how state-controlled media influences AI responses by first doing a deepdive on China, then taking the methodology they developed there and applying it to a broader set of countries.
China’s state-influenced media dataset:
The authors start by assembling a dataset of 530,694 articles “published in party and commercial newspapers as a result of a directive from the central government”, as well as 198,872 “news articles disseminated on Xuexi Qiangguo, an app developed by Alibaba and reportedly in coordination with the Publicity Department of the Chinese Communist Party”.
State media goes into Common Crawl
: They then examined CulturaX, an open training dataset derived from Common Crawl, and discovered that 1.64% of the documents from its Chinese-language portion had overlap with the state-derived datasets. “This is approximately 41 times the number of documents that come from the Chinese-language Wikipedia domain and 16 times the number of documents that come from Baidu”.
The state parts of the dataset influence LLM portrayal of the government:
They then discovered that a bunch of phrases from these datasets had been memorized by the LLMs. They then examined how these datasets changed LLM responses by taking a LLaMa 2 13B model (which doesn’t have much Chinese data) and training it on a subset of the above: “the results are strongest for the scripted documents. After only 6,400 examples, the model provides a more favourable response than the base model almost 80% of the time”.
Generally available models inherit these biases:
The researchers then study some generally available commercial models to see if they inherit these biases by farming prompts that included references to Xi Jinping or the CCP from WildChat (a dataset of ChatGPT usage), Baidu Zhidao Q&A (the Chinese equivalent of Yahoo Answers) and Zhihu (the Chinese equivalent of Quora), then looking at how the LLMs respond. They find that “widely used commercial models demonstrate greater favourability to Chinese political figures and institutions when they are prompted in Chinese than when they are prompted in English.”
Findings replicate in other countries:
The authors then replicate this methodology by looking at other countries, though the sample size looks a little small to me. They do a cross-national audit study with 6,051 prompts, looking at languages where over 70% of the global speakers reside in a single country. Here they find that “countries with more state media control are more likely to produce pro-regime responses in their official language versus in English than countries with greater media freedom”.
Why this matters – LLMs as propaganda targets:
These findings show how the deliberate creation of state-backed content has a measurable impact on the data corpora LLMs are trained on and the downstream behavior of the LLMs themselves. “LLMs can serve as intermediaries that launder strategic rhetoric into seemingly objective information”, they write. “The ability to affect LLM output may further incentivize political actors to expand their efforts to shape the content freely available on the internet”.
This research also suggests a specific technical intervention, which is that researchers should red team LLMs for their views on different governments in a variety of languages, carefully noting when the views diverge seemingly on the basis of which language is being used.
Read more:
State Media Control Influences Large Language Models (Nature, PDF)
.
***
The flowers of the new games
One game we liked to play was called evolution. It worked like this: you picked something, like a certain type of flower or tree, or stranger things like a mountain or a chasm in the sea, and you tried to make them “successful” according to some pre-set metric, like the attractiveness of a flower to pollinators, or perhaps the ecological fitness of a mountain. Then you let the worlds run and you ran them until your criterion was met or you lost in some way, whether through species fitness or landscapes being reshaped through natural disasters or sometimes simply time – enough time is more destructive than anything else in the universe, such is the way of entropy. We played in leagues that span billions of years and millions of worlds. And the “living” creatures in finalist worlds had no idea that their flowers, their mountains, their creatures, had obtained success in many other universes than could be conceived.
Things that inspired this story:
The simulation hypothesis; evolution strategies; entertainment given infinite energy budgets.
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
June 8, 2026
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

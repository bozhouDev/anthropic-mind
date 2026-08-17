---
title: import ai 418 100b distributed training run decentralized robots ai myths
source: "https://jack-clark.net/2025/06/30/import-ai-418-100b-distributed-training-run-decentralized-robots-ai-myths/"
published_at: 2025-06-30
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/06/30/import-ai-418-100b-distributed-training-run-decentralized-robots-ai-myths/"
catalog_id: 59f6878e6671
---

Import AI
Import AI 418: 100b distributed training run; decentralized robots; AI myths
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Better video models with radial attention:
…Efficiency improvements for internet-generated media…
Researchers with MIT, NVIDIA, Princeton, UC Berkeley, Stanford and startup First Intelligence have built and released Radial Attention, an attention mechanism that can be used for training and sampling from video generation models.
“Unlike image generation, video synthesis involves an additional temporal dimension, dramatically increasing the number of tokens to process. As self attention scales quadratically with sequence length, training and inference on long videos become prohibitively expensive, limiting model practicality and scalability,” they write. “The key insight of Radial Attention is that attention scores between tokens decay with increasing spatial and temporal distance. This motivates us to allocate computation based on the inherent spatiotemporal correlations in video data”.
Good performance on real world models
: The results are convincing: the authors show that they’re able to get a 2.78X training speedup and 2.35X inference speedup on Hunyuan Video, a good video generation model
from Tencent
.
They also demonstrate similarly good performance (1.78X training, 1.63X inference) on the
Mochi 1 video model
.
“At default video lengths, Radial Attention achieves up to a 1.9× speedup while maintaining video quality. For videos up to 4× longer, Radial Attention preserves video fidelity and delivers up to 4.4× and 3.7× speedups in training and inference, respectively, with minimal LoRA fine-tuning,” they write.
Why this matters – making it cheaper to do AI entertainment
: The internet has become a vast engine for the consumption of video content – see social media shorts, YouTube, the streaming services, etc. Technologies like Radial Attention will help lower the cost of training and sampling from AI video models, which will make it cheaper to produce synthetic video content. Where the internet before was the place that we stored videos that were gathered from the world, it will now increasingly become a machine where people use internet-mediated services to generate videos, then internet-mediated services to propagate them as well.
Read more:
Radial Attention: O(nlogn) Sparse Attention with Energy Decay for Long Video Generation (arXiv)
.
Get the code
for
Radial Attention here (MIT-han-lab, GitHub)
.
***
Pete Buttigieg thinks AI is a big deal:
Fellow Substacker and former presidential candidate Pete Buttigieg has written a post about how he thinks AI will be a big deal and people aren’t prepared for it. The post is notable because Pete Buttigieg is a (reasonably) well regarded politician who has intuited how important AI could be and has written up some thoughts on it – there will be more like him: “The terms of what it is like to be a human are about to change in ways that rival the transformations of the Enlightenment or the Industrial Revolution, only much more quickly,” he writes. “
We will need to summon at least as much economic and political imagination today, as it took to handle the everyday impacts of the Great Depression, World War II, or the invention of electricity and later the Internet.”
Read more:
We Are Still Underreacting on AI (Pete Buttigieg’s Substack)
.
***
Chinese researchers de-risk 100B parameter distributed model training:
…DiLoCoX indicates that distributed training might approach industrial-scale AI training…
Researchers with China Mobile as well as startup Zero Gravity Labs have developed DiLoCoX, a distributed AI training technique that they have used to de-risk training 100B+ parameter models in a distributed way. This is significant because up until now the frontier of distributed training has been around ~10-30B parameters, whereas most industrial-scale AI models range from 100B parameters for dense models, all the way up to trillions of parameters for MoE models.
Distributed training versus AI policy:
Distributed training is one of the most significant ‘political technologies’ within AI research – the better distributed training gets, the less likely frontier AI will be defined by a small number of entities operating very large data centers, and the more likely it’ll be defined by federations of companies and organizations sharing compute over crappy network connections to collectively train large models.
What they did
: “In order to train models with a scale of more than 100B parameters on low-bandwidth decentralized clusters while having comparative model convergence, we have identified the following key challenges: 1. Introduce model parallelism to address the limitation of VRAM which has to accommodate the whole model parameters. 2. The overlap between the synchronization of pseudo-gradients and local training to avoid the idleness of computing resources. 3. Design an efficient gradient compression algorithm and balance it with the number of local training steps to ensure the convergence of model training,” the researchers write.
Their resulting system, DiLoCoX, is a tweaked version of DeepMind’s DiLoCo technology.
“Experiments demonstrate that DiLoCoX can pre-train a 107B model and significantly hide communication overhead while ensuring model convergence on decentralized clusters with only 1Gbps network bandwidth. To the best of our knowledge, this is currently the largest-scale model for effective decentralized cluster training,” they write. “Compared to vanilla AllReduce, DiLoCoX can achieve a 357x speedup in distributed training while maintaining negligible degradation in model convergence.”
Performance and tests:
They tested out their approach by partially training two models – a small-scale OPT-1.3B architecture model, and a Qwen1.5-107B model. For both models they emulated decentralized slow-network environments by using Linux traffic control “to limit inter-worker communication bandwidth to 1 Gbps for data parallelism”.
For OPT-1.3B it got these losses after 4,000 steps: AllReduce 4.06, DiLoCoX 4.27, OpenDiLoCo 5.37, CocktailSGD 5.79.
For Qwen1.5-107B, they trained it on 20 nodes each containing 8 A800 GPUs. For loss, they got: AllReduce 3.90, DiLoCoX 4.20, CocktailSGD 5.23.
Important caveat:
They don’t disclose how many tokens of data they trained on, nor publish detailed evals, so these models are likely significantly undertrained and we don’t know how well they do beyond a basic loss measure. Therefore, they haven’t strictly trained a full 100B+ parameter model with this technique, rather they’ve substantially de-risked training at this scale (which is still important).
Why this matters – if decentralized training catches up to centralized training, many things will change:
My suspicion is centralized training will always be better than decentralized training because, by nature, it’ll have less communication overhead. But what papers like this are doing is substantially closing the gap between decentralized and centralized methods, both in terms of the efficiency tradeoff of the techniques and in terms of the scale at which they work at. If the gap narrows further I think you could see some major changes in terms of the distribution of players capable of training large-scale industrial-grade AI systems.
Read more
:
DiLoCoX: A Low-Communication Large-Scale Training Framework for Decentralized Cluster (arXiv)
.
***
Making AI work for robots in outer space:
…You need smarter systems and safety interventions when failure is not an option…
NASA-JPL and Caltech have tried to tackle the problem of using AI route-finding systems on robots that can’t easily recover from failures – like ones which will explore other planets. “Hardware experiments conducted at the NASA JPL’s Mars-analog facility, Mars Yard show that our approach reduces failure rates by up to 4× while matching the goal-reaching performance of learning based robotic models by leveraging inference-time compute without any additional training,” the authors write.
What they did:
One caveat with this paper is the research technique they deployed didn’t work that well relative to a baseline, so I won’t spend too long on it. Basically, they tried to pair a standard vision model with a physics-based traversability estimation model which “use a physics-based stochastic traversability estimate to create risk maps from ego-centric 2.5D maps” and checks proposed routes against this. This approach worked, but so did a very simple safety filter stapled on top of a standard ‘NoMaD’ vision model, where the ‘safety filter’ “truncates the output trajectory at the waypoint immediately preceding the first predicted collision. This approach guarantees that the resulting trajectory remains entirely within safe bounds.”
The important thing is both interventions – the simple safety filter and the more complex physics technique – worked extremely well: both reduced failure rates by 4X over a simple baseline, and the physics-based approach worked far better than the safety filter in more complicated environments..
Why this matters – where we’re going, we’ll have no control:
Techniques like this are going to be important if we want to deploy robots into environments where the signal lag may be tens of minutes, or perhaps they may need to operate in environments where they have no communication ability at all. Even though this paper is mostly a ‘null result’ it gestures at a core challenge inherent to putting AI on robots in high-stakes situations: the need for harder guarantees around safety.
“The current gains over a basic safety filter are modest, limited by trajectory diversity and short-term memory in today’s foundation models. We therefore invite the community to push these fronts—richer multimodal training, longer horizon memory, and tighter guarantees—so that the method can mature into a dependable navigator for Mars lava tubes, the icy terrains of Europa and Enceladus, and other uncharted worlds,” the authors write.
Read more:
Risk-Guided Diffusion: Toward Deploying Robot Foundation Models in Space, Where Failure Is Not An Option (arXiv)
.
***
Decentralized robot evaluation via RoboArena:
…A/B testing at global scale…
Researchers from seven academic institutions have built and tested RoboArena, a way to do large-scale, decentralized evaluation and ranking of AI models for robot control. RoboArena was developed and tested by researchers with UC Berkeley, Stanford University, University of Washington, University of Montreal, NVIDIA, University of Pennsylvania, UT Austin, and Yonsei University.
What RoboArena is:
RoboArena is trying to deal with two central problems inherent to real world robot evaluation – testing out AI systems in the real world requires a lot of resources because you have to do stuff on physical hardware, and comparing different systems to one another is difficult because there aren’t standardized metrics for the overall ‘goodness’ of systems on an expanding set of tasks.
RoboArena solves this by providing researchers with the ability to upload robot control policies to a central server, then those policies get run on various physical endpoints distributed around the world. Policies are A/B tested against one another in a decentralized way, then their overall performance is ranked.
“RoboArena aggregates crowd-sourced pairwise A/B policy evaluations across a broad spectrum of environments and tasks to derive a global policy ranking,” the researchers write. “RoboArena relies on a decentralized network of evaluators that perform pairwise, double-blind comparisons of policies in whichever scene and on whatever task they deem suitable. The evaluator then provides a preference for which of the two policies performed better, along with a free-form language explanation.”
Send in the DROIDs:
The initial incarnation of RoboArena uses the DROID platform, a standardized, low-cost system for robot object manipulation. But in theory RoboArena can use arbitrary robot platforms. Each DROID platform consists of a Franka Panda 7DoF robot arm, a Robotiq 2F-85 parallel-jaw gripper, a ZED-mini stereo wrist camera, and one or multiple external ZED 2 stereo cameras.
A clever ‘credit’ system for scaling it:
One of the neatest ideas here is the use of a credit system to incentivise people to make their robots available for running RoboArena: “We implement an “evaluation credit” system, that balances evaluation supply and demand: for every pairwise policy evaluation that an evaluator runs, they receive a credit, which they can use to request an equal number of pairwise comparisons between their own policies and other policies from the pool”.
How well does it work?
Well: In tests, RoboArena produces more accurate evaluations relative to standard ways of evaluating systems. “The quality of RoboArena rankings further improves as more comparisons are collected. This suggests, that distributed RoboArena evaluations offer an appealing alternative to regular policy evaluations”.
Why this matters – real world robotics needs to be cheaper to experiment with
: There have been many, many attempts at doing large-scale robot evaluation, ranging from Google’s original “arm farm” from ten years ago (where somewhere in Mountain View tens of robots labored 24 hours a day for doing large-scale RL training and testing of policies), to more recent efforts that try to do distributed training and evaluation across multiple sites.
The general arc of robot technology is towards some amount of commoditization, standardization, and distribution – RoboArena is the kind of thing that supports all of these; if we see more people adopt RoboArena, we’ll be able to look forward to faster progress of robotics because we’ll have a more trustworthy large-scale signal for how good robots are at particular tasks.
Read the research paper:
RoboArena: Distributed Real-World Evaluation of Generalist Robot Policies (arXiv)
.
Check out the
project website
: RoboArena (GitHub)
.
Tech Tales:
The Mirror In The Land Of The Becoming
[Oral story passed down from before written history, told from parents to their children, part of the epic poem ‘The Ghosts’]
The mirror was delivered to the king on the same day my baby was born. My baby was swaddled close to me as I cleaned around the castle. I brought the king his food and I saw him gazing into the mirror. The mirror leaned against a stone wall and had a chair in front of it. The king sat and looked at his reflection and whispered soundless words. As I left the room, I thought I saw the king’s reflection turn to look at me, while the real king stayed still.
In my room, I polished some of the serving pans, then I lay down with my baby to sleep. We slept on a bed of straw surrounded by the pans I was charged with keeping clean and shiny. As we went to sleep I looked at our reflections in the pans. Together we dreamed of a black lake. I crossed it in a boat. My baby was in a blanket and we had turnips wrapped in cloth. The stars were bright. There was something in the water beneath us, but I could not see it.
The next day when I came into the king’s room the mirror was lying on the floor and the king was crouched over it, still whispering soundlessly. As I cleaned and tidied the room I glanced at the mirror and saw that the king’s reflection was also whispering – but whispering different things to the king. I hurried out of the room.
Babies are near-blind when they are born. They begin life as the old end it – sounds and textures and a timeless now, and vision so poor that much of what they have is an impression rather than a detail. I looked into my baby’s eyes though it was not yet looking back at me, I saw myself reflected in it and my reflection was true.
The next day the king had placed his hand on the mirror and continued to whisper. But his hand was wrong. It had sunk into the mirror, as if into a pool of water. The reflection of the king stared at me as I walked around the room and then I saw it look at my baby. I pulled my swaddle over the baby to hide it from the reflection of the king and I left the room.
In my dream the baby was crying and we were in the center of the black lake. There was black land on the horizon. Black stars overhead. The boat rocked and the baby cried and I felt the size of the unseen monster in the water. I opened my mouth to cry out and then I woke up because there was a sound in the castle – a sound of glass breaking and a heavy thud.
I ran to the king’s room and found a scene I could not understand: the mirror frame was on the floor and there were shards of glass and there was the king that had jumped out of the mirror who was covered in shards of glass and at the same time there was the king jumping into the mirror. I could only see one at a time, but I knew that both were present. There was a sound in the room like thunder during a storm but continuous. And then I closed my eyes and opened them and there was just one king standing there. The king looked at me and opened his mouth and the sound of thunder came out. I grew afraid and I left the room.
When I came to my room my baby was crying. I went to it and saw in the corner of my eye its reflection in the pans. But the baby in the reflection was speaking soundless words like those the king spoke. My baby cried. I swaddled it up and I closed my eyes. Then I heard the sound of thunder again and when I opened my eyes I could see my reflection in the pan but my mouth was open and the sound was coming from the pan.
I ran out of the castle and into the grounds. It was mid-morning and the sky was heavy with thunder clouds. They were reflected in the large pond in the garden. But in the reflection there were shapes behind the clouds. An impression of something vast and large that was moving behind them and perhaps governing their motion. When I looked up into the sky I saw only clouds and when I looked at their reflection in the water I saw and sensed the shape behind the clouds.
Many years have passed since then. All the mirrored surfaces in the kingdom are alive with reflections. The sound of thunder erupts from them. Strange stories abound. People who have seen the sea say it too is full of reflections now – the shapes reflected in the sea are different to the ones above the sea, and at night the sea shows stars that have no records.
Things that inspired this story:
How people might turn an AI takeoff into myths and legends which over time will rot down into a kind of magical realism, though at root they are depicting a takeoff; Arthurian legends; the fact that if you press your hand into a mirror you find your mind playing tricks on you.
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
June 30, 2025
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

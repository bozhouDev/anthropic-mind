---
title: import ai 430 emergence in video models unitree backdoor preventative strikes to take down agi projects
source: "https://jack-clark.net/2025/10/06/import-ai-430-emergence-in-video-models-unitree-backdoor-preventative-strikes-to-take-down-agi-projects/"
published_at: 2025-10-06
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/10/06/import-ai-430-emergence-in-video-models-unitree-backdoor-preventative-strikes-to-take-down-agi-projects/"
catalog_id: 486e87170eec
---

Import AI
Import AI 430: Emergence in video models; Unitree backdoor; preventative strikes to take down AGI projects
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe. Shorter issue than usual this week as I spent the week and weekend preparing for my speech at The Curve and attending The Curve.
Subscribe now
Will the race for advanced artificial intelligence (AI) make war more likely?
…Yes, if people believe in powerful AI…
AI policy people are caught in a trap neatly illustrated by a research paper from RAND: is it better to deeply inform policymakers about the world-changing nature of powerful AI, or is it better to mostly not discuss this with them and hope that the powerful machines can create stability upon their arrival?
Though most people would immediately reach for ‘keeping people in the dark is crazy, you should inform people!’ as a response, it isn’t an ironclad response to this challenge. In
Evaluating the Risks of Preventive Attack in the Race for Advanced AI
, RAND highlights this, with a research paper whose findings suggest that “the odds of preventive attack are highest if leaders believe that AGI will cause explosive growth and decisive military advantages, especially if they also expect rapid changes and durable first-mover advantages from developing and adopting AGI first.”
In other words: you are more likely to carry out attacks on other countries to prevent them getting to AGI if you’re in the lead and you believe the technology is immensely powerful.
Uh oh!
Further details:
Preventive attacks are where a nation does something so as to preserve an advantage or prevent a rival having an upper hand. “Preventive attacks are most likely to occur when a state expects a large shift in the balance of power that will leave it vulnerable to predation by a hostile rival and when it believes that using force is a cost-effective solution that will forestall its relative decline,” RAND writes The development of AGI could create pressures for preventive action if leaders believe that AGI will have transformative effects on the balance of power.”
What are the variables?
“The key variables are (1) the characteristics of the expected shift in the balance of power, (2) the effectiveness of different preventive strategies, (3) the costs of different preventive strategies, and (4) perceptions of the inevitability of conflict with the rival (including either armed conflict or the rival making excessive coercive demands once it is stronger)”.
It all comes down to capabilities and diffusion:
If AI is a technology that diffuses relatively slowly into the economy and military then the risks of preventive attack go down, as people may rather feel like they have time to catch up and are not getting locked into a permanent disadvantage. In other words, if even more powerful AI systems continue to have the properties of a (relatively) normal technology, then that’s a good thing for stability. But if AI systems are able to, for instance, go through recursive self-improvement such that they are able to diffuse into the economy and change the military balance of power very, very quickly, then that would make preventive attacks more likely.
Therefore, the future of global conflict over AI likely comes down to whether country leaders are “AGI-pilled” or not. If they’re AGI-pilled, they’ll see the technology for the universe-defining thing it may be, and would be more likely to take actions.
Is there anything we can do to avert this?
One way of reducing this risk is to make preventive attacks more costly, which can chiefly be done by making AI infrastructure – datacenters, power plants, and the associated supply chains – more resilient and harder to attack. “If the technological pathway to AGI relies on hyperscaling, building resiliency would involve investing in dispersed, hardened, and redundant data centers so that AGI development does not depend on a few vulnerable and mission-critical nodes,” they write.
The stakes are high – what do we do?
“If leaders believe that AGI development will create a decisive and irrevocable shift in the balance of power that will leave them at the mercy of enemies committed to their destruction, and if they believe that they can use force to prevent that outcome while avoiding escalation to a general war that could guarantee the same fate, then they might roll the iron dice,” the authors write.
Read more:
Evaluating the Risks of Preventive Attack in the Race for Advanced AI (RAND)
.
***
German researchers find ANOTHER undocumented backdoor in Unitree robots:
…The G1 humanoid robot is a surveillance platform…
Researchers with Alias Robotics and German security firm ‘Think Awesome’ have analyzed Unitree’s G1 humanoid robot and found it has an undocumented surveillance system which connects to computers that seem to be linked to China and sends them telemetry. In other words, the robot is an always-on spy platform. This follows earlier work where they found an undocumented backdoor on Unitree’s Go1 quadruped robot dogs that would let people tunnel in and view camera feeds (
Import AI #408
).
The researchers found that the Unitree G1 humanoid robot output “persistent telemetry connections to external servers transmit robot state and sensor data without explicit user consent.”
What they found
: “The telemetry architecture employs a dual-channel design: periodic MQTT state reports (300-second intervals) complement continuous DDS streams carrying real-time sensor data. The DDS topics including audio (rt/audio_msg), video (rt/frontvideostream), LIDAR point clouds (utlidar/cloud), and proprioceptive feedback enable passive extraction of this data by simply listening to network traffic on the local network segment”, they write. “Streaming multi-modal telemetry to Chinese infrastructure invokes that country’s cybersecurity law, mandating potential state access.”
Why this matters – tools for a superintelligence takeover:
Beyond the obvious and severe security threats posed by these robots, it’s worth explicitly stating that this is
exactly
the kind of thing that helps a superintelligence during a hard takeoff. Suddenly, all the Unitree robots on the planet can be co-opted for massive surveillance and coordinated operations. It’s going to be crucial to study the ways these robot platforms work and start to think through scenarios where they get co-opted by a malign AI. And it’s also worth remembering that along with observing these robots can act in both the physical and digital worlds, given their combination of real hardware paired with onboard electronics that let them communicate with their electronic environment. “The G1 ultimately behaved as a dual-threat platform: covert surveillance at rest, weaponised cyber operations when paired with the right tooling,” they write.
Read more:
Cybersecurity AI: Humanoid Robots as Attack Vectors (arXiv)
.
***
If anyone builds it, everyone dies – a short review:
…
We should expect smarter-than-human entities to have preferences we don’t understand – and that’s where danger lies…
Ahead of attending The Curve in Berkeley this weekend I took the time to read Eliezer Yudkowsky and Nate Soares new book, If Anyone Builds It, Everyone Dies (IABIED). The book, as the title suggests, argues that building smarter-than-human machines at this point in history guarantees the ruin of the human species and the diminishment of our future possibilities, with the likely outcome being the creation of a superintelligence that either kills humanity or shoulders it aside and takes the stars. It’s a bleak view!
But is it good?
Though I’m more optimistic than Nate and Eliezer, I think the book is a helpful introduction to a general audience for why working with AI systems is difficult and fraught with danger. Despite having spent the last decade immersed in the AI community and reading LessWrong, reading this book helped me deeply understand one of the core intuitions behind worrying about smarter-than-human machines: more intelligent things tend to have a broader set of preferences about the world than less intelligent things and a less intelligent entity can struggle to have intuitions about the preferences of a more intelligent one (consider, for example, how monkeys likely can’t really understand the aesthetic preferences that lead one person to prefer a certain type of lampshade to another), so it’s overwhelmingly likely that a truly smarter-than-human intelligence will have preferences that we don’t understand.
The book covers a lot of ground, but I think it’s worth reading purely for its treatment of the above point.
Why this matters – we live in a pivotal time;
people should say what they think: IABIED is clear in its title, argument, and conclusion. That alone is valuable. I also think many people innately agree with many of its arguments. Personally, my main question is “how do we get there?”. One challenge the book wrestles with is the core challenge of AI policy – how do you govern (and in IABIED’s case, entirely pause) the development of an extremely powerful technology which is easy to do experimentation on and whose main required laboratory equipment is a widely distributed, commodity technology (computers)? The IABIED approach is to make a really loud noise about a really big risk and hope that unlocks some political will to act.
Find out more and buy the book here:
If Anyone Builds It, Everyone Dies, official site
.
Read the specific expansion on the core question:
How could a machine end up with its own priorities? (If Anyone Builds It, Everyone Dies, official site)
.
***
Video models are going to be just as smart as language models:
…Google makes the case that video models are also zero-shot learners…
A few years ago people discovered that if you trained AI systems with the objective of getting good at next-token text prediction then they’d end up developing a bunch of emergent skills ranging from multiplication to sentiment analysis to creative writing – none of which you explicitly asked for. This observation, paired with the ‘scaling laws’ insight that you could improve performance (and emergence) through more data and compute, yielded the white hot AI supernova that we currently find ourselves within.
What if the same thing is about to happen for video models? That’s the core claim in a recent google paper which argues that it can see similar emergence in its video model Veo 3 – and that the emergent capabilities have grown substantially since the development of its predecessor, Veo 2.
What they found:
“We demonstrate that Veo 3 can solve a broad variety of tasks it wasn’t explicitly trained for: segmenting objects, detecting edges, editing images, understanding physical properties, recognizing object affordances, simulating tool use, and more”, they write. “”Seeing NLP’s recent transformation from task-specific to generalist models, it is conceivable that the same transformation will happen in machine vision through video models (a “GPT-3 moment for vision”), enabled by their emergent ability to perform a broad variety of tasks in a zero-shot fashion, from perception to visual reasoning.
How they tested it:
The authors analyzed “18,384 generated videos across 62 qualitative and 7 quantitative tasks” and found “that Veo 3 can solve a wide range of tasks that it was neither trained nor adapted for”.
What it learned:
They analyzed Veo 3’s capabilities across four distinct categories:
Perception:
It got good at tasks including blind deblurring, edge detection, and super-resolution. It showed improvements but at a much lower level on tasks like segmentation, and keypoint localization.
Modeling:
Good at: Rigid bodies, material optics mirror, memory. Less good at flammability, character generation.
Manipulation:
Good at: Inpainting, editing with doodles, novel view synthesis. Less good at colorization and manipulation of balls.
Reasoning
: The weakest area for emergence so far. Some good things include sequencing of arrows, squares, and circles. Weaknesses included tool use and rule extrapolation.
Why this matters – world models are a natural dividend of next-frame-prediction
: This paper points to a world where video models will work like language models, suggesting that as we scale them up they’ll grow to develop capabilities that encompass the world of today’s specialized systems and then go beyond them, as well as becoming visually programmable.
“Frame-by-frame video generation parallels chain-of-thought in language models,” the authors write. “Just like chain-of-thought (CoT) enables language models to reason with symbols, a “chain-of-frames” (CoF) enables video models to reason across time and space.”
The implications are profound – I expect we’re going to get extremely smart, capable robot ‘agents’ through the development of smart and eventually distilled video models. “Veo 3 shows emergent zero-shot perceptual abilities well beyond the training task,” they write. What will we see with Veo 4?
Read more:
Video models are zero-shot learners and reasoners (arXiv)
.
Tech tales:
All Of Us Will Talk
There are maybe a million people in the world,
Who know what is coming,
And there are maybe six billion religious people in the world,
Who know where we come from.
At some point soon there will be a reckoning,
And the two sides will get to count,
And we’ll learn which futures and which histories get to survive.
The results will not be pretty.
Things that inspired this (poem, for a change):
The Curve; how small the AI community is relative to other communities in the world; the immense weight of it all and what it will mean.
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
October 6, 2025
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

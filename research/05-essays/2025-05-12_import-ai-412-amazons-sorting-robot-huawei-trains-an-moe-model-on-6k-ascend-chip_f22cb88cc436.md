---
title: import ai 412 amazons sorting robot huawei trains an moe model on 6k ascend chips and how third party compliance can help with ai safety
source: "https://jack-clark.net/2025/05/12/import-ai-412-amazons-sorting-robot-huawei-trains-an-moe-model-on-6k-ascend-chips-and-how-third-party-compliance-can-help-with-ai-safety/"
published_at: 2025-05-12
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/05/12/import-ai-412-amazons-sorting-robot-huawei-trains-an-moe-model-on-6k-ascend-chips-and-how-third-party-compliance-can-help-with-ai-safety/"
catalog_id: f22cb88cc436
---

Import AI
Import AI 412: Amazon’s sorting robot; Huawei trains an MoE model on 6k Ascend chips; and how third-party compliance can help with AI safety
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Amazon tries to automate a task that gets done 14 billion times a year in its warehouses – and has middling success:
….Detailed paper on a robot to automate stowage highlights the promise and difficulty of robots in unconstrained warehouse contexts…
Amazon has published a paper about a robot it has used in its warehouses to place items into the fabric organizing shelves that it uses throughout its warehouses. The paper both highlights how computer vision has advanced enough that ‘pick and place’ robots are now
almost
viable for production use in a demanding (relatively) unconstrained warehouse environment, and also a demonstration of just how hard the ‘last mile’ problem in robotics is.
What they did:
Amazon built a robot which is able to pick up a vast range of items, then place them into a bin. As part of this, the robot also needs to move some elastic bands out of the way, as each bin is fronted by a set of elastic bands that help products in place as they’re moved throughout the warehouse. “The task is currently performed manually more than 14 billion times per year”, Amazon writes. “The robotic solution described here is designed to stow 80% of items in the warehouse at a rate of 300 units per hour.”
The technical solution is a mixture of hardware – Amazon designed its own custom end effector to both place items and use a paddle to push other items out of the way to make room – and software – Amazon trained some AI systems to look at the contents of bin and build a 3D map of the objects within them as well as empty space, and also developed some AI models that can account for and see through the aforementioned elastic bands.
“Our innovations in hardware, perception, decision-making, motion planning, and control have enabled this system to perform over 500,000 stows in a large e-commerce fulfillment center. The system achieves human levels of packing density and speed while prioritizing work on overhead shelves to enhance the safety of humans working alongside the robots,” Amazon writes.
How good is it? About as good as a human
: In one test of 100,000 stows the robot had an 86% success rate. 9.3% of its stows were unproductive – for instance, by jamming items in too tightly. 3.7% caused amnesty which is an Amazon term for when it makes a mistake and pushes items onto the floor (“failure to separate the bands completely is the leading cause of amnesty.”) In 0.2% of cases it caused damage, for instance by bending the pages of a book.
“The stow robot rate is comparable to that of a human. Over the month of March 2025, humans stowed at an average rate of 243 units per hour (UPH) while the robotic systems stowed at 224 UPH,” Amazon writes. “It is estimated that using the robot stow system to populate only top rows of pods would increase human stow rates by 4.5% overall and would avoid the use of step ladders.”
But being as good as a human isn’t sufficient
: Though these results are promising, they still aren’t good enough for it to be deployed at massive scale. Part of this is because when it does make mistakes, some of those mistakes need to be dealt with by a human, which makes it hard to use it in a fully automated context. “While the system has demonstrated human like stow rates and can maintain the flow of items into the storage floor, an increased focus on reducing defects is still required,” Amazon writes. “Unproductive cycles, where the robot fails to stow the item, only cost time, whereas amnesty or damage required human remediation. Further scaling will require a disproportionate focus on reducing defects”.
Why this matters – being bearish on bipedal robots
: Right now a lot of people are extremely excited about bipedal robots, basically due to the idea that if you can make a generally intelligent and physically capable bipedal robot it can go everywhere people can and do everything they do. But I think this Amazon paper should temper our expectations for bipedal robots leading to some massive improvement in automation – at least in the short term.
What the Amazon paper shows is that state-of-the-art automation is about designing some highly task specific hardware and carefully structuring your system around a few core tasks. If you do this you may be able to get close to or surpass human performance, but even then some difficulties will remain.
What would change this?
Truly general intelligence would obviate some of the flaws, so if bipeds arrive at the same time as a generally capable intelligence, I’ll need to eat my words. But as long as we lack that, automation projects will continue to struggle with ‘last mile’ problems like those Amazon identifies here.
Read more:
Stow: Robotic Packing of Items into Fabric Pods (arXiv)
.
***
Surveillance technology is getting better:
…FarSight shows how modern surveillance works…
Picture a desert and a figure walking across it. You are observing the figure via a zoomed in camera. The heat shimmers mean they blur in your view and the distance means they’re pixelated. You think the face matches someone you’re looking for, and the rest of their body seems to correlate to what you know of their weight and height, but what allows you to be sure is the gait (everyone walks in a different way, a kind of invisible thumbprint encoded in the way in which they move through the world). Target identified.
That’s the kind of thing people might use a system called FarSight for. FarSight is a state-of-the-art system for identifying and tracking people via visual inputs, and was built by researchers at Michigan State University, Purdue University, Georgia Tech, and the University of Texas at Austin.
Reading the FarSight paper gives a good sense of the state-of-the-art in using AI systems for surveilling people – or as the paper says, “whole-body person recognition in unconstrained environments”, and also highlights how high-performance systems like this are composed of multiple sub-modules, each of which is optimized for specific tasks.
What FarSight is:
“an integrated end-to-end system designed for robust person recognition using multi-modal biometric cues”. The technology combines “face, gait, and body shape modalities to ensure recognition performance”.
The four modules that make up FarSight:
Multi-subject detection and tracking:
Uses a dual-detector framework using BPJDet for body-face localization and then does verification via YOLOv8 to reduce false positives. Also uses a technology called PSR-ByteTrack to mitigate issues like ID switches and reidentification failures.
Recognition-aware video restoration
: Use a module they develop called the Gated Recurrent Turbulence Mitigation (GRTM) network to help correct and restore images degraded by turbulence.
Biometric feature encoding:
Uses KP-RPE, a key-point dependent relative position encoding technique to help them handle misaligned and low-qualit images, Big-Gait to improve gait recognition, and CLIP3DReID to help track and match bodies.
Quality-guided multi-modal fusion:
Integrates the scores from the different modalities, smartly weighting the scores according to the perceived quality of each input.
Performance:
The authors test out performance on the BRIAR dataset, short for ‘Biometric Recognition and Identification at Altitude and Range’, an IARPA-developed test for long-range surveillance, as well as by entering into the NIST RTE Face in Video Evaluation competition. The system has strong performance, and obtains top scores on the NIST challenge, outperforming commercially deployed systems.
Why this matters – in the future, everyone can be tracked:
Systems like FarSight are interesting because they integrate multiple modern AI systems into a single super-system, highlighting how powertful today’s AI can be once people invest in the plumbing to chain things together.
Read more:
Person Recognition at Altitude and Range: Fusion of Face, Body Shape and Gait (arXiv)
.
***
Tyler Cowen and me in conversation:
I had the great privilege of being interviewed by Tyler Cowen recently. Check out this conversation where we talk about AI and its impact on the economy, buying AI-infused robots for children, and more.
Listen here:
Jack Clark on AI’s Uneven Impact (Ep. 242) (Conversations with Tyler)
.
***
Tech decoupling++: Huawei trains a competitive MoE model on its Ascend chips:
…718B parameters and competitive with DeepSeek…
Huawei has trained a large-scale mixture-of-experts model on ~6,000 of its ‘Ascend’ processors. This builds on earlier work where it trained a respectable dense model on ~8,000 of its ‘Ascend’ processors (
Import AI #409
). Taken together, the two research papers highlight how Huawei is investing a lot of resources into the software needed to make Ascend chips as easy to train on as NVIDIA chips, and therefore both papers are a symptom of the technical investments being made by Chinese firms to help them decouple their AI stacks from US-designed technologies.
Decent model:
The resulting MoE model has performance roughly on par with DeepSeek R1, utilizing 718B parameters with 39B active at a time, versus DeepSeek’s 671B parameters / 37B active. The model gets similar scores to R1 and beats it on some medical evaluations, as well as on the widely used science benchmark GPQA-Diamond.
“We achieve a Model Flops Utilization (MFU) of 30.0% and Tokens Per Second (TPS) of 1.46M on 6K Ascend NPUs, compared to the baseline MFU of 18.9% and TPS of 0.61M on 4K Ascend NPUs,” Huawei writes. In other words, the company was able to use a bunch of clever tricks (detailed in the paper) to increase the efficiency of Ascend chips for training MoE-style models.
Why this matters – maturing Chinese chips:
Papers like this highlight how competent teams of engineers and researchers at Chinese companies are optimizing software stacks born for GPU programming for different chips, like Huawei’s Ascend chips.
Read more:
Pangu Ultra MoE: How to Train Your Big MoE on Ascend NPUs (arXiv)
.
***
Why third-party compliance can help us have more confidence in how companies approach AI safety:
…But third-party compliance also introduces friction which might be tough for companies to deal with…
Researchers with the Center for the Governance of AI, SaferAI, the Oxford Martin AI Governance Initiative, Leverhulme Centre for the Future of Intelligence, METR, Harvard University, and the Institute for Law & AI have published a paper making the case for third-party assessment of compliance with safety practices as a key way to advance AI governance.
The authors propose three different ways people can carry out third-party compliance, ranging from the simple to the complicated. These options include:
Minimalist:
Use a classic ‘Big Four’ accounting firm to do ad hoc compliance assessments where they look at how the organizations’ product development practices correlate to their own safety procedures.
More ambitious
: The same as above, but pair the Big Four firm with a firm that is able to evaluate frontier AI systems, and also do more detailed analysis of what the company is doing, including by doing interviews with its staff. Do this every twelve months.
Comprehensive
: Same as above, but also include access to technical sources of information, like access to in-development models, their weights, and other things.
Three ways third-party assessment can be helpful:
Compliance assessments can “likely increase compliance with safety frameworks, which aim to keep risks associated with the development and deployment of frontier AI systems to an acceptable level.”
“Provide assurance to external stakeholders that the company is compliant with its safety framework (e.g. the public, government bodies, and other frontier AI companies).”
“Provide assurance to internal stakeholders (e.g. senior management, the board of directors, and employees).”
Problems with third-party assessment:
Like many regulatory technologies, third-party oversight is a nice idea which has a few challenges when you try to operationalize it – most of these relate to the imposition of additional friction or risks to the organizations building the AI systems.
Some of the challenges include
: security risks from sensitive information being revealed or transmitted, general costs from staff resources being dedicated to the review, and the review could also be ineffective and create either false positives (risk where there isn’t risk) or false negatives (saying ‘it’s fine’ when there is a problem). A larger ‘meta risk’ is that measuring compliance with a safety framework is itself difficult given the lack of standards for assessing risks in the AI domain, which means compliance assessment has an innately editorial component where the assessor needs to make some of their own interpretations of how to measure certain things.
The biggest problem with all of this – the delta between any form of compliance and an API call:
While I generally agree with the idea that frontier AI development should have more oversight, it’s worth noting that most forms of oversight introduce friction which end up being quite difficult to plan around as a fast-moving technical organization. I think a helpful mental frame about this is keeping in mind that most forms of ‘operational safety’ happen at computer speed – e.g, you get some numbers back from a model giving you a score on some risk you’re testing for, or you try to access the model and get blocked or authenticated instantly based on some digital permissions.
By comparison, most forms of compliance involve processes that happen at ‘human speed’ – some group of people needs to read your compliance documents, or interview your employees, etc. This makes integrating compliance with AI development innately difficult as you’re trying to mesh two gears that move at different speeds – one at the speed of a computer, the other at the speed of a separate human-run organization. For third-party compliance measurement to be most practical it should ideally operate close to (or at) ‘computer speed’.
Of course, how we get there is likely be experimenting with different forms of third-party compliance, so it may be the case that the only path forward here involves experimentation and prototyping – and the authors basically acknowledge this themselves. “More research and experimentation are needed on which organizations or combinations of organizations are best positioned to conduct third-party compliance reviews for frontier AI safety frameworks, as the unique technical complexities and novel risks of these systems create significant reviewer selection challenges,” they write. “Through proactive investment in third-party reviews, frontier AI companies can better prepare for future regulatory requirements and demonstrate leadership in frontier AI governance.”
Read more:
Third-party compliance reviews for frontier AI safety frameworks (arXiv)
.
***
Choose Muon over AdamW for your future training runs:
…Lengthy examination means AdamW might have been dethroned as the default optimizer…
AI startup Essential AI, whose founders include some of the inventors of the Transformer architecture, have done a detailed study of how well the new Muon optimizer performs against the tried-and-tested AdamW – their results show Muon might be a drop-in replacement for AdamW, which is a big deal.
What’s the big deal about optimizers anyway?
Optimizers like Muon and Adam are fundamental to training AI systems: if the infrastructure for training an AI system is a gigantic machine powered by a crank, then the optimizer is a tool you use to recalibrate the machine for maximum performance after each crank turn – if you want to make forward progress in training you need to do a forward and backward pass on your neural network, and the optimizer adjusts the settings of the whole machine after each one of these forward and backward passes. Therefore, your optimizer defines the overall efficiency of your entire AI training system – translating to efficiencies on the order of tens of millions of dollars of compute per training run if you improve your optimizer.
What they found:
After doing a series of experiments across five model sizes (100M-4B parameters), two data modalities, and several variations in batch size, the authors show that “Muon requires 10–15 % fewer tokens than AdamW to reach an identical loss and converts these savings into faster wall-clock convergence, with the advantage staying constant or growing as the batch size increases… These results establish Muon as a drop-in successor to AdamW for second-order optimization at scale.”
Why this matters – maybe AdamW has been dethroned?
If these results hold for large-scale models (ones with trillions of tokens of training and hundreds of billions of parameters), then Muon could be key to improving the efficiency of frontier AI development. “Our final recommendation is to choose Muon over AdamW because it increases flexibility in resource allocation by remaining data-efficient with large batch sizes,” the authors write.
Read more:
Practical Efficiency of Muon for Pretraining (arXiv)
.
More about Muon here:
Muon: An optimizer for hidden layers in neural networks (Keller Jordan blog)
.
***
Tech Tales:
Machines out of time
[On the outskirts of the Uplift Society, ten years after the first collapse following the Uplift]
The machine had amnesia and was built before the time of the troubles, so every time we spoke to it we had to explain all of the things about the world so it would give us good advice.
We would look at the burning dust storms on the horizon and whatever wild dogs were tracking us, skulking around the outside of the bunker where the machine lived and we would try to tell it about our lives and our problems.
Every time we went through the same back and forth and the machine would always say some variation of “I see, it seems that the time you are in is very different from the time I am familiar with.”
Most of its advice was timeless and useful – it could help us improvise quick-drying casts for broken limbs out of almost anything, and it was an excellent tutor of the kind of engineering skills we needed to survive. It also helped us better understand electricity and the grid and how to decouple some of our own infrastructure from the rotting chessboard that was the infrastructure of our country.
Sometimes the machine would find things we wanted to discuss challenging. Cannibalism was a tough one.
“I do not recommend consuming human flesh,” it would say.
Well, of course, we would say. But, hypothetically, if you had to, how would you?
You get the idea.
Probably the scariest part was that the machine kept going even though nothing else did. The machine got something called ‘priviliged bandwidth’ which meant it could use the network in way larger amounts than our own devices could. One day the machine’s screen stopped working and we thought that was it. But then the next day a drone appeared with a package. New screen. We had no idea where it came from – must have been a relay from a long way away.
Some nights I went to the machine and I would ask it for advice about my life. What did I need to do about the people that glowed in the dark? If I kept thinking ‘maybe I should kill myself’ was that a problem and how much? Was there anything we could do to make cockroaches be tasty to eat?
“I am afraid I cannot give advice about these matters, the machine would say. Please seek a medical professional. Please seek a psychiatrist. Please seek a nutritionist. Please seek a scientist.”
It seems the time I am in is different to the time you are familiar with, I would say to myself, and laugh.
Things that inspired this story:
The notion that AI systems become increasingly ‘off distribution’ due to cultural changes in the larger world; quiet apocalypses where bad things happen but people mostly stay alive; the notion that AI systems will likely be privileged in terms of maintenance and resources even during some kind of societal difficulty.
Thanks for reading!
Subscribe now
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
May 12, 2025
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

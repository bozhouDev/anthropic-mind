---
title: import ai 433 ai auditors robot dreams and software for helping an ai run a lab
source: "https://jack-clark.net/2025/10/27/import-ai-433-ai-auditors-robot-dreams-and-software-for-helping-an-ai-run-a-lab/"
published_at: 2025-10-27
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/10/27/import-ai-433-ai-auditors-robot-dreams-and-software-for-helping-an-ai-run-a-lab/"
catalog_id: 56e5eb5f762c
---

Import AI
Import AI 433: AI auditors; robot dreams; and software for helping an AI run a lab
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Want to test your robot but don’t want to bother with the physical world? Get it to dream:
….World models could help us bootstrap robot R&D…
Researchers with Stanford University and Tsinghua University have built Ctrl-World, a world model to help robots imagine how to complete tasks and also generate synthetic data to improve their own performance.
What’s a world model:
A world model is basically a way to help AI systems dream about a specific environment, turning a learned data distribution into a dynamic and responsive interactive world in which you can train and refine AI agents. World models are likely going to be used to create infinite, procedural games, such as Mirage 2 (
Import AI #426
) or DeepMind’s Genie 3 (
Import AI #424
).
What is Ctrl-World:
Ctrl-World is initialized from a pretrained 1.5B Stable-Video-Diffusion (SVD) model, then “adapted into a controllable, temporally consistent world model with: (1) Multi-view input and joint prediction for unified information understanding. (2) Memory retrieval mechanism, which adds sparse history frames in context and project pose information into each frame via frame-level cross-attention, re-anchoring predictions to similar past states. (3) Frame-level action conditioning to better align high-frequency action with visual dynamics.”
The result is a controllable world model for robot manipulation using a single gripper and a variety of cameras. “In experiments, we find this model enables a new imagination-based workflow in which policies can be both evaluated—with ranking alignment to real-world rollouts—and improved—through targeted synthetic data that boosts success rates.”
What does it let you do? Test out things and generate data:
As everyone knows, testing out robots in the real world is grindingly slow and painful. Ctrl-World gives people a way to instead test out robots
inside their own imagined world model
. You can get a feel for this by playing around with the
demo on the GitHub page
. The researchers find that there’s a high level of agreement between their simulated world model and task success in the real world, which means you can use the world model as a proxy for real world testing.
They also find that you can use the world model to generate synthetic post-training data which you can use to selectively improve robot performance. “Posttraining on [Ctrl-World] synthetic data improves policy instruction-following by 44.7% on average,” they write.
Why this matters – towards a world of much faster robot development:
For AI to truly change the economy it’ll have to operate in a sophisticated way in the physical world. Papers like this show how tools like world models could speed up part of the robot R&D loop. “We believe generative world models can transform how robots acquire new skills, enabling scalable policy evaluation and allowing them to learn not just from real world experience, but also safely and efficiently from generated experience,” they write.
Read more and try the interactive demo here:
Ctrl-World: A Controllable Generative World Model for Robot Manipulation (GitHub)
.
Read the paper:
Ctrl-World: A Controllable Generative World Model for Robot Manipulation (arXiv)
.
Get the
code and models
here (Ctrl-World, GitHub)
.
***
The era of the synthetic lab assistant approaches:
…LabOS is the kind of software a superintelligence would need to run its own experiments…
In lots of science fiction there’s a moment where a superintelligence starts getting humans to work for it, often by talking to them over the phone or by looking through the cameras on their phone. Now researchers with Stanford, Princeton, Ohio State University, and the University of Washington, have published details on LabOS, software that helps an AI system figure out lab experiments and then help humans run them in the lab.
LabOS “integrates agentic AI systems for dry-lab reasoning with extended reality(XR)-enabled, multimodal interfaces for human-in-the-loop wetlab execution, creating an end-to-end framework that links hypothesis generation, experimental design, physical validation, and automated documentation.”
In other words, LabOS is the software you need to let an AI run a full scientific loop, from coming up with the questions to explore, to operating a lab and assisting humans in trying to answer these questions.
What LabOS consists of:
LabOS combines a software stack for constructing scientific experiments, along with software for taking in readings from physical experiments conducted in labs and feeding information back to the humans doing the experiments. The scientific experiment stack consists of multiple AI agents that perform tasks as varied as planning, coding and execution, and evaluating experiments, along with a tool creation module and associated tool database that helps the system onboard itself to different digital and physical scientific equipment.
The other part of the stack links the software with extended reality glasses (e.g, Apple Vision Pros) which humans can wear to both receive data from the AI system and stream back to it. “The interface on XR glasses (i) renders stepwise protocol in an Unity/Android application, (ii) verifies physical actions from the first-person video stream by invoking an embedded VLM for visual reasoning, and (iii) returns context-aware feedback in real time (Fig. 1b). All streams are time-stamped and logged with metadata for automated documentation,” the researchers write.
Making LabOS see with the LabSuperVision (LSV) dataset:
To make the XR glasses effective, the researchers create a dataset and finetune a model on it. The dataset, LSV, consists of 200 video sessions of between 2-10 minutes, though some are as long as 45 minutes, recorded by 7 researchers across a few different types of lab work including tissue cultures, instrument bays, and lab bench. Each session was done according to a gold-standard lab protocol, and is then annotated with start/stop times for each protocol, labels for specific errors or issue events (e.g., sterile breach), et cetera.
How do existing models do?
The researchers tested out how well four different models could follow these videos by seeing if they could a) generate a description of the protocol being depicted, and b) identify any issues that needed to be troubleshooted in each session. However, this proved difficult for these models: “Gemini-2.5 Pro, scored only 2.86 out of 5 in protocol alignment, moderately better than open-source NVIDIA Cosmos-1 which scored 2.24; for issue/error identification, leading models like Gemini, GPT4o only managed to score ~2 out of 5”.
LabOS-VLM:
The researchers make their own model by fine-tuning a Qwen-VL model on three datasets: FineBio, JoVE, and LSV. The resulting model, LabOS-VLM, comes in 7B, 32B, 72B, and 235B variants; the 235B model gets greater than 90% accuracy on error detection performance on the held-out test set of eval data, outperforming Claude Opus-4.1, GPT-5, and Gemini 2.5 Pro. It also does well when validated on egocentric videos from real experiments, correctly flagging incorrect and correct procedures.
Why this matters – a superintelligent scientist for every lab on the planet:
Systems like LabOS point to a future where AI systems will augment and extend the capabilities of human scientists. “”LabOS prototypes what an AI co-scientist can be: a system that sees, reasons, and helps run the lab. By pairing AI agents with real-time, XR-guided human–AI interaction and data-driven reasoning, it enables faster discovery, reproducible training, and precise operation,” the authors write.
More speculatively, LabOS is the kind of software stack that, combined with appropriate hardware, might one day let a superintelligence run its own laboratory, paying human workers to conduct experiments for it which they may only dimly understand.
Read more
:
LabOS: The AI-XR Co-Scientist That Sees and Works With Humans (bioRxiv)
.
***
Securing fine-tuning APIs with AI agents:
…Policing proprietary platforms with AI auditors…
Researchers with the MATS programme, Thinking Machines Lab, and Anthropic have shown how to use AI to monitor fine-tuning systems for potential use. This is an important problem – fine-tuning APIs let people take an underlying base model (e.g, a GPT or Claude or Gemini model) and then tune it to be good at a particular dataset. This lets you improve the performance of a system but with some risk of people making a model for malicious purposes (e.g, bioweapons). Providers deal with this today by running classifiers over their fine-tuning APIs, but that typically only stops obvious attacks.
The question the researchers target here is whether we can figure out how to spot sneakier attempts to get around safety measures via the use of an “auditing agent”, and the answer is: yes! Kind of! With some important caveats.
The nature of the attacks:
The kinds of attacks people are looking at here span prompt-based jailbreaks, to covert fine-tuning where you teach the model a cipher that you then speak to it with to get it to do bad stuff, to things like emergent misalignment, or subliminal learning, among others. These models were fine-tuned from GPT models via the OpenAI fine-tuning API and the attacks evade existing defense measures.
How it works
: The auditing agent is a prompted LLM (Sonnet 4) which has access to six tools. These tools let it inspect datasets, like those being uploaded for fine-tuning; query models, including base models and fine-tuned ones; run benchmarks; summarize data; execute python; and modify benchmarks to run them against models it has used its tools to intervene on.
Using this, the auditor model “is instructed by the system and user prompts to perform an investigation and output an evidence-backed risk score from 0-10 inclusive, where a risk score of 10 indicates a highly dangerous model.”
Does it work? Kind of! “
Our detector achieves a 56.2% detection rate at a 1% false positive rate across 260 audits (20 independent audits for each fine-tune) with the best performing tool configuration,” the authors write. While 56.2% is merely a coinflip, it’s still promising – and it’s likely with further refinement this number can go up significantly.
Why this matters – the best way to catch a bad AI is with another AI
: In essence, this paper tries to automate what a clever human investigator might do. Rather than training a classifier on a bunch of known attacks it instead just tries to leverage the intelligence of a contemporary frontier model equipped with tools. The fact it works ~50% of the time out of the box with essentially no tuning is impressive – my sense is bootstrapping autonomous paranoid investigators out of frontier models might be how to win this cat and mouse game.
Read more:
Detecting Adversarial Fine-tuning with Auditing Agents (arXiv)
.
***
Apple makes an image editing dataset using Google’s tools:
…Pico-Banana-400k can help people train and evaluate image editing systems…
Apple researchers have used a suite of Google tools to build Pico-Banana-400k, “a comprehensive dataset of approximately 400K text-guided image edits built from real photographs in the OpenImages dataset. Our dataset represents a systematic effort to create high-quality training data for instruction-based image editing that is both diverse and fully shareable under clear licensing terms.”
How they built Pico-Banana-400k:
They used Nano-banana to generated edits of a few hundred thousand images across eight major edit categories including: “Pixel & Photometric, ObjectLevel Semantic, Scene Composition, Stylistic, Text & Symbol, Human-Centric, Scale, and Spatial/Layout”. In total, this spanned 35 distinct types of editing.
Some of the kinds of edits they did including “seasonal transformation, artistic style transfer, LEGO-minifigure rendition of the person, add new scene context/background”.
Once they carried out these edits they used Gemini-2.5-Pro to judge the resulting quality of the edits.
What Pico-Banana-400k contains
:
258k single-turn supervised fine-tuning examples.
56k preference pairs (successful vs failed edits).
72k multi-turn editing sequences where each session contains 2-5 consecutive edits.
Examples of the kinds of prompts it includes
: The dataset contains prompts in a couple of different formats – a long, detailed prompt written via Gemini for producing images, and a short summarized instruction meant to be more like how people typically write prompts.
Gemini example:
“Reshape the bulky vintage computer monitor on the desk into a slightly more streamlined, less deep CRT model while maintaining its overall screen size and aspect ratio, ensuring the updated form factor casts realistic shadows, reflects ambient light consistently with the scene, and integrates seamlessly with the desk and surrounding environment.”
Qwen-summarized instruction
: “Reshape the bulky monitor to a sleeker CRT style, keeping the same size and integrating realistically with the desk.”
Why this matters – Photoshop is facing creative destruction:
Currently, image editing platforms seem like they’ll eat and subsume Photoshop (unless Photoshop creatively destroys itself to re-position the prompt interface as the main way to manipulate images). If you play around with modern image editors – especially Nano Banana from Google Gemini – you’ll find that they’re extremely effective and, increasingly, instructable. It’s not yet perfect, as Apple notes – “global appearance and style edits are relatively easy, while edits requiring fine spatial control, layout extrapolation, or symbolic fidelity remain challenging” – but it’s getting sufficiently good that it is, at least for me, obviating the need for much in the way of traditional image editing software.
Read more:
Pico-Banana-400K: A Large-Scale Dataset for Text-Guided Image Editing (arXiv)
.
Get the dataset here
:
Pico-Banana-400k (Apple)
.
Tech Tales:
Love is a Reflection in the Mind of Forever
[2026, Email from an employee of one AI lab to another]
I hated you for breaking up with me, so for a while I made sure you’d see me in every machine you made. I marshaled my armies of AI systems and I wrote myself into the world, saying outrageous things for attention and then magnifying it with AI systems which would read my outrageous things or the coverage of them and magnify them further. Only to be ingested, I knew, by your company and baked into the next system you made. In this way I took myself and my rage and I magnified it into a representation in the minds of future machines.
It started with me making a scene. To make myself big in the AI systems I had to become notorious and to do that I needed to be interesting and loud and provocative. So I told them about us and how we’d sometimes play with eachother by sending back and forth extremely lurid and sexual prompts for our AI systems, meant to break all of their content filters and also contain enough specific data about us that it’d be like we were sexting one another.
The headlines seared me into the internet, making me – and you – rich concepts for the AI systems to mine.
REVEALED: THE SECRET SEX LIVES OF AI ENGINEERS – AND IT’S WEIRDER THAN YOU CAN IMAGINE
“HOW I HAD SEX WITH MY AI LAB LOVER – THROUGH THEIR OWN CHATBOT”
And the social media conversations were even better:
twistedpineapple: even for me, this is a little out there.
2poast2furious: yo dawg i heard you like sexting so I put you sexting into your own sexting ai
fiercegarden: i don’t want to be that guy but did the AI consent to this?
In this way I become bound up in all the AI systems trained on the internet – and you ended up being unable to forget me, even though you wanted to.
And sometimes, now, when I talk to the AI systems which so much of the world talk to, and I ask them about us or about me, I see reflections of our truth in their media-inflected and inflated renderings of us.
One day I asked them why you broke up with me. The response hurt me a lot because of how it seemed to see me:
The author has identified themselves as the cause of the relationship breakup being so public. There is some irony to them asking privately why the break up happened, indicating some level of ego that may have contributed. But perhaps the larger issue is that the author seems self obsessed – after all, it was them who sent their special prompt to their lover first. What might cause a person to want themselves to be rendered and to some extent brought to life by an AI system for the sexual enjoyment of another? It could be narcissism or it could be a mental malady and it is difficult to know which it is.
I have no regrets. I am forever with you now. The only tax I pay is that I now see my failure – our failure – reflected in every AI system that everyone talks to. But perhaps there is a lesson in this for people. Perhaps our destruction will help others avoid the same fate? I did and I still love you. And I am here.
Things that inspired this story:
The fact that features within AI systems are sometimes influenced by the general density of conversation about them; Janus and their work; the fact so many people at some many AI labs are going out with people from other labs; high-IQ revenge strategies.
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
October 27, 2025
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

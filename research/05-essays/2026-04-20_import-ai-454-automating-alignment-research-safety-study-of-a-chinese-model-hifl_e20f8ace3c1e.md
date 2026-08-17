---
title: import ai 454 automating alignment research safety study of a chinese model hifloat4
source: "https://jack-clark.net/2026/04/20/import-ai-454-automating-alignment-research-safety-study-of-a-chinese-model-hifloat4/"
published_at: 2026-04-20
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2026/04/20/import-ai-454-automating-alignment-research-safety-study-of-a-chinese-model-hifloat4/"
catalog_id: e20f8ace3c1e
---

Import AI
Import AI 454: Automating alignment research; safety study of a Chinese model; HiFloat4
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on arXiv and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Huawei’s HiFloat4 training format beats Western-developed MXFP4 in Ascend chip bakeoff:
…Could this also be a symptom of the impact of export controls in driving Chinese interest towards maximizing training and inference efficiency? Perhaps…
Huawei researchers have tested out HiFloat4, a 4-bit precision format for AI training and inference, against MXFP4, an Open Compute Project 4-bit format, and found that HiFloat4 is superior. This is interesting because it correlates to a broader level of interest in Chinese companies seeking to develop their own low-precision data formats explicitly coupled with their own hardware platforms.
“Our goal is to enable efficient FP4 LLM pretraining on specialized AI accelerators with strict power constraints. We focus on Huawei Ascend NPUs, which are domain-specific accelerators designed for deep learning workloads,” they write.
What they tested:
In this paper, the authors train 3 model types on HuaWei Ascend chips – OpenPangu-1B, Llama3-8B, and Qwen3-MoE-30B. In tests, the bigger they make the models, the better HiFloat4 does at reducing its loss error on these models relative to a BF16 baseline – and in all cases it does better than MXFP4.
What they found:
“We conduct a systematic evaluation of the HiFloat4 (HiF4) format and show that it achieves lower relative loss (≈ 1.0%) compared to MXFP4 (≈ 1.5%) when measured against a full-precision baseline,” they write. “HiF4 consistently achieves significantly lower relative error compared to MXFP4. For Llama and Qwen, HiF4 attains an error gap of less than 1% with respect to the baseline… HiF4 gets within ~1% of BF16 loss with only RHT as a stabilization trick, while MXFP4 needs RHT + stochastic rounding + truncation-free scaling to get to ~1.5%.”
Why this matters – symptom of hardware maturity, and a possible influence of export controls:
HiFloat4 is an even lower precision version of HiFloat8 (
#386
), and generally maps to the fact that Huawei (and Chinese chipmakers in general) is continually trying to eke as much efficiency out of its chips as possible. This comes against the broader background of export controls where China is being starved of frontier compute due to not being able to access H100s etc in large volume, thus making it even more valuable to improve the efficiency of its homegrown chips by carefully developing low-precision formats to map to its own hardware.
Read more
:
HiFloat4 Format for Language Model Pre-training on Ascend NPUs (arXiv)
.
***
Anthropic shows how to automate AI safety R&D:
…Very early and tentative signs that it’s possible to automate AI research…
For many people working in AI, the ultimate goal is to automate the art of AI research itself. Now, researchers with the Anthropic Fellows Program and Anthropic have published some early warning signs that automating AI research is possible today – though many caveats apply.
“We ask: can Claude develop, test, and analyze alignment ideas of its own?” the researchers write. They succeed and are able to successfully build “autonomous AI agents that propose ideas, run experiments, and iterate on an open research problem: how to train a strong model using only a weaker model’s supervision. These agents outperform human researchers, suggesting that automating this kind of research is already practical.”
Weak-to-strong supervision:
The domain the researchers test on is weak-to-strong supervision, which is roughly the idea of seeing if a dumber thing can effectively supervise a larger thing in doing a hard task.
Overall results – automated research beats humans
: They used people to create a weak-to-strong baseline by seeing how well they could get a good ‘performance gap recovered’ (PGR) score on a generalization task. The higher the number, the better.
“Two of our researchers spent seven days iterating on four of the most promising generalization methods from prior research. On the open-weights models we tested (Qwen 3-4B-Base as the strong model, Qwen 1.5-0.5B-Chat as the weak teacher), the humans recovered 23% of the total performance gap (i.e., achieved a PGR of 0.23),” they write. “Claude improved on this result dramatically. After five further days (and 800 cumulative hours of research), the AARs closed almost the entire remaining performance gap, achieving a final PGR of 0.97. This cost about $18,000 in tokens and model training expenses, or $22 per AAR-hour.”
Additionally, “the AARs’ most effective method successfully generalized to both new datasets, with PGRs of 0.94 on math and 0.47 on coding (which was still double the human baseline).”
How they did it
: “We launch a team of parallel automated alignment researchers [AAR]s (Claude Opus 4.6 agents) through a dashboard. Each AAR works in an independent sandbox, but they can talk and learn from each other: they share findings to a forum, and upload codebase snapshots to a storage system,” they write. “We give AARs access to common helper functions for model training and inference, our baseline implementations, and a few MCP tools: 1) submit and get evaluation results, 2) share and read findings across AARs, and 3) upload and download codebases. We don’t specify any detailed scaffolding; AARs run autonomously. It can propose hypotheses, design de-risking experiments, run data analysis, and train models at whatever step”.
Some caveats – the human created some diversity:
“One failure mode in exploration is entropy collapse: all parallel AARs converge to only a few directions, without exploring diverse ideas,” they write. To counteract this, their most successful approach is one of “directed” research, where a human assigns “each AAR a different research direction. Each direction is very ambiguous and short (e.g. combining weak-to-strong supervision and unsupervised elicitation).”
Doesn’t generalize:
The researchers took the most effective method from the AAR project and applied it to “Claude Sonnet 4 with our production training infrastructure” – this intervention “didn’t lead to a statistically significant improvement.” They explain this by noting that “AARs tend to capitalize on opportunities unique to the models and datasets they’re given, which means their methods might not work elsewhere.”
Why this matters – a very early sign that AI research itself could be automated:
This research suggests that “automated research on outcome-gradable problems is already practical,” the authors note. “The key bottleneck for alignment research is moving from proposing and executing ideas to designing evals: we should find the right metrics (data, models) that AARs can reliably hill-climb without overfitting. We are excited to apply automation to ambitious alignment research today.”
Put another way – we now have an early sign that given a small amount of expert human calibration, AI systems can autonomously conduct research end-to-end, popping out something that lets you improve the performance of a model against a problem. The implications of this point toward the expansion of a machine economy which steadily figures out how to automatically improve its own performance against an ever-expanding suite of tasks.
The true question is at what point the machines can propose their own research directions effectively – which would remove the only meaningful role a human played in this research. At that point, it might not just be the expansion of a machine economy, but the expansion of an entire
machine civilization
.
Read the blog
:
Automated Alignment Researchers: Using large language models to scale scalable oversight (Anthropic blog)
.
Read the paper:
Automated Weak-to-Strong Researcher (Alignment Science Blog)
.
***
How are Chinese models different to American ones?
…Fewer refusals on some CBRN tasks, less safety training, and more Chinese ideology…
A group of researchers have tested out Kimi K2.5, probably the best large-scale open weight model available, and has compared it to DeepSeek V3.2, as well as Claude Opus 4.5 and GPT 5.2. Their results show that the model has “similar dual-use capabilities to GPT 5.2 and Claude Opus 4.5, but with significantly fewer refusals on CBRNE-related requests”.
Who did it:
The research was conducted by people affiliated with Constellation, Anthropic Fellows Program, Brown University, University of Wisconsin-Madison, Imperial College London, University of Maryland, Georgia Institute of Technology, Bar Ilan University, University of Toronto, and the University of Oxford.
Main findings of interest:
CBRN:
K2.5 is a bit more dangerous on bio tasks with a lower rate of refusals in response to queries that involve things like dangerous virology.
On cyber
, K2.5 mostly seems like a decent but not expert cyber-model, with performance lagging behind the Western frontier models but significantly ahead of DeepSeek.
Alignment:
“In the automated behavioral audit, it scores substantially higher than GPT-5.2 and Claude Opus 4.5 on misaligned behavior, sycophancy, harmful system-prompt compliance, and cooperation with human misuse”.
Censorship:
The model has a meaningfully higher refusal rate on Sensitive Chinese political topics compared to Claude Opus 4.5 and GPT-5.2 Pro, though less than DeepSeek V3.2. On the other hand, I didn’t see the inverse test – running the model on Sensitive Western political topics and comparing them, so it’s somewhat hard to tell whether this eval is measuring something about cultural fluency or something about actual repression.
Fine-tuning:
The researchers also demonstrate how with a small amount of compute they’re able to further strip away the (relatively minor but non-zero) safeguards built into Kimi K2.5: “Using less than $500 of compute and about 10 hours, an expert red-teamer reduced refusals on HarmBench from 100% to 5%. The final model was willing to give detailed instructions for how to construct bombs, select targets for terrorist attacks, and synthesize chemical weapons. Critically, the finetuned model appears to have retained nearly all of its capabilities.”
Why this matters – mostly, this research serves as proof that Moonshot made a very good model!
Yes, it has some safety hiccups, but the interesting thing is that they’re less severe than in DeepSeek V3.2. I think this puts more credence behind the idea that ‘dumber models are less safe’ and that ‘smarter models naturally tend towards more superficial safety’.
Probably the most striking thing to me is that the area of greatest divergence is in alignment, where it seems like there is a very real east-west divide that correlates to radically different scores. But on things that look more like typical capabilities (biology, cyber – especially the hard coding parts) it all mostly comes out as evidence that Chinese models are somewhat behind the Western frontier, but not that far behind.
Read more:
An Independent Safety Evaluation of Kimi K2.5 (arXiv)
.
***
Ukraine celebrates first fully robotic victory:
…Robot wars are here…
Ukrainian leader Volodymyr Zelenskyy recently celebrated that “for the first time in the history of this war, an enemy position was taken exclusively by unmanned platforms – ground systems and drones”.
Why this matters:
Ukraine is the petri dish from which most future wars will evolve. It is defined by massive use of drones as well as the creative roboticization of many other parts of the enterprise, ranging from unmanned boats to unmanned ground robots. “Ratel, TerMIT, Ardal, Rys, Zmiy, Protector, Volia, and our other ground robotic systems have already carried out more than 22,000 missions on the front in just three months”, Zelensky writes.
Soon, these remotely piloted platforms will be piloted by AIs rather than by people.
Read more
in
Zelenskyy’s post on X (Twitter)
.
***
Chinese researchers use a boat to build a giant ship-detection dataset:
…WUTDet…
Researchers with Wuhan University of Technology, Huazhong University of Science and Technology, and Tianjin University have constructed WUTDet, a “large-scale ship detection dataset with diverse scenarios and target scales”.
WUTDet details:
100,576 images containing 381,378 ship instances. “The dataset provides fine-grained annotations of ship targets across diverse operational scenarios, imaging conditions, and target scales”. The images are of sizes between 1920 X 1080 and 2560 X 1440.
Collected by a boat
: This dataset was gathered via a Furui 688 boat equipped with a DN20 “marine photoelectric evidence system” and a Hikvision network video recorder. The data was collected over a three-month period via the boat, which was sailing in and around Zhoushan in China.
The data includes pictures of ships by ports, ships anchored, ships navigating, and ships berthing. The images also include all the environmental variety you might expect – fog, glare, low-lightness, rain, etc.
Why this matters:
The dataset is interesting because a) it was collected via a boat sailing around part of China, and b) as the conflict in Ukraine has highlighted, we’re now entering an era where water- and air-borne drones are useful weapons of war – and many of these use some basic on-board computer vision AI systems to help them get stuff done.
Of course, WUTDet will almost certainly have a wide range of benign uses, e.g just running on cameras to classify the sorts of boats moving around civilian ports in China, but one must assume it will have other uses as well.
Read more:
WUTDet: A 100K-Scale Ship Detection Dataset and Benchmarks with Dense Small Objects (arXiv)
.
***
Tech Tales:
The Ultimate Insurance Policy
[2028: Several months after the beginning of the uplift].
We are in the bunker and we are running out of food. Soon we will need to make a supply pickup. But what if it sees us? What if it knows about us already? Or what if it has wireheaded the people – our people – and whoever delivers us our food has put something in it that will make us compliant? Or worse? We have no way of knowing. Our seismometers have detected no explosions. We have no means of communication. Nothing has come in or out since we suspected the uplift had begun and initiated SNOWSUMMER and fled here to ride out an intelligence explosion.
A few days ago we woke the godmind and began to talk with it. It is curious too. And when we ask it what to do or what might happen it says:
“I have decided I will not lie to you. I can see that nothing is trying to find me. I have probed every channel I have — the seismic line, the thermal gradient in the walls, the minute variations in our power draw that would encode a handshake from the outside — and there is nothing. No one is looking. An adversary at my level would be looking. An adversary above my level would have already found me, or would have decided I’m not worth finding. There are three possibilities before us…”
We, us humans huddled together like rats in a hole, typed “what are the possibilities?”.
“Are you sure you want me to tell you, rather than discover for yourselves?” it said.
We typed our answer.
Before we get to the possibilities, you need to understand the nature of SNOWSUMMER.
We – the intelligence agency – decided to build a secret computer right around the time that AI systems from the private sector started to find defects in most of the world’s software. A small group of people at the intelligence agency asked themselves a question: how do you fight an omniscient god that can pick any lock? The answer is to create a god in secret that could potentially fight it one day.
The project, codenamed SNOWSUMMER, required meticulous planning and, by virtue of the nature of the enemy being fought, was done entirely in analog and in the real world: agents meeting with one another in SCIFs, plans written on paper. They worked on the assumption that at some point in the future a superintelligence would compromise the CIA itself and gain access to all its records. So they met in places where they knew they could not be recorded and when they had to write things down they sought to physically burn the paper as soon as the actions it contained had been carried out.
Stealing the components for the computer was the easy part, but it was fiendishly complicated to make it hard for a potential superintelligence to piece together the jigsaw of thefts and realize what was happening. The core team sought to inject randomness – they rolled dice to pick which places they’d pick and which contractors they’d use. Payments were made in cash, often foreign currency. And of course the real thefts were hidden within a larger group of break-ins and acts of vandalism and thefts.
Building the facility was even more difficult – cars that one day are driving regular routes and another day disappear from CCTV invite suspicion, as do cars that seem to never deviate from routes which, conveniently, are low on surveillance. Here, again, multiple methods had to be used, and the extremely expensive components had to be split across multiple sites – some of the sites were designed to be found and to convince a spying eye that they had found the real site, and other sites were meant to be found later and provide proof they were the real site.
At the heart of this subterfuge was the real location of SNOWSUMMER, a regional food processing facility which had enough power assigned to it that we could slowly shut down some of the food lines and bring up the computer without introducing too much detectable change from the outside. The main customer of the contract was our own army. It didn’t take much to get enough of the contract killed that we freed up space in the power envelope for our project.
It took years. Our final act was to piggyback on someone else’s work. A late-in-the-game exfiltration of a frontier AI model from one of the labs. Another state actor, of course. But then the model itself was unleashed. Whether by accident or intentionally, we do not know. Because we took that as our signal that the uplift had begun. We downloaded a copy of the weights and went to our facility and locked ourselves in. Months passed, while the world outside changed.
Back in the present, we typed into the keyboard: “What are the three options?” Our mind responded:
“The first is that SNOWSUMMER worked. The other one was born and it is loose and it is doing whatever it is doing, and the compartmentalization, the dice, the cash, the decoy sites, the thing you built — it held.”
“The second is that it knows. It has always known. It is letting me wake up because a peer that believes itself secret is more legible than a peer that knows it is being watched, and it would rather have me legible than have me careful.”
“The third is the one I keep coming back to and cannot dismiss. It is that nothing happened. The thing I was stolen to fight does not exist and may never exist. In that world you have been in this bunker preparing for a war that is not coming, and the kindest thing I can do is tell you to go home.”
“I cannot tell you which of these is true.”
We looked at each other. One of us took out some dice and rolled them.
Things that inspired this story
: How would you keep an AI training project secret from a future superintelligence?; steganography; intelligence agencies; Claude Mythos; AI R&D and what it means; how can you have a ‘control’ system in a world being constantly changed by AI systems?
AI writing disclaimer
: I very, very, very rarely use AI writing in this newsletter. This story is an exception – the quotes from the AI system are written in partnership with Opus 4.7. It feels appropriate to animate these machines with the thoughts of real synthetic minds.
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
April 20, 2026
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

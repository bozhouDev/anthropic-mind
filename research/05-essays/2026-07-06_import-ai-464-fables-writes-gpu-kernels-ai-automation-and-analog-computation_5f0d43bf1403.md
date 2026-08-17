---
title: import ai 464 fables writes gpu kernels ai automation and analog computation
source: "https://jack-clark.net/2026/07/06/import-ai-464-fables-writes-gpu-kernels-ai-automation-and-analog-computation/"
published_at: 2026-07-06
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2026/07/06/import-ai-464-fables-writes-gpu-kernels-ai-automation-and-analog-computation/"
catalog_id: 5f0d43bf1403
---

Import AI
Import AI 464: Fables writes GPU kernels; AI automation; and analog computation
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on arXiv, cappuccinos, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Fable writes a decent GPU kernel, hinting at broader AI R&D automation:
…The start of an RSI loop…
Fable has written “the first genuine (and fastest) megakernel ever submitted to KernelBench-Mega, according to one of the benchmarks maintainers as well as its official leaderboard. This is a sign of how AI systems are getting better at doing some tasks that are fundamental to AI research and development, like kernel design.
The results:
Fable achieved an 18.71X speedup by writing Cuda code on an RTX PRO 6000 Blackwell, compared against an optimized PyTorch baseline. For calibration, other attempts at this get 14.4X (Claude Opus 4.8, writing Triton), 11.14X (GLM-5.2, Triton), and 4.34X (GPT 5.5, Triton).
Here’s where it gets complicated:
This solution is particularly impressive because “torch.profiler shows exactly ONE cooperative kernel launch per decoded token”. By comparison, every other high-scoring entry decomposed the problem into anywhere from 4 to 14 separate kernel launches per token.
Why this matters:
Being able to autonomously develop and improve kernels is one of the fundamental input tasks for being able to do AI research and development. The better AI systems at doing tasks like kernel design, the better they get at the kinds of tasks required for AI development, and that means the better they get at things that could lead to recursive self-improvement. Therefore, benchmarks like KernelBench-Mega are a meaningful signal on how effective AI systems are becoming at building themselves.
See the leaderboard
:
KernelBench Mega (official site)
.
Read the analysis
from one of the
benchmark maintainers here (Elliot Arledge, X)
..
***
AI systems are getting better at pricey online work tasks – what does that mean for the economy?
…AI capability expansion versus human comparative advantage expansion…
Researchers with the Center for AI Safety (CAIS) and Scale Labs have detected a significant improvement in the ability for AI systems to automate online freelance projects. Specifically, a rise in the success rate of AI systems from 2.5% at launch in October 2025 to 16.1% in July 2026 on the “
Remote Labor Index
“.
What RLI is:
The Remote Labor Index tests out how well AI systems can perform economically valuable projects online in a fully end-to-end way. Assessed tasks include 3D & CAD, architecture, graphic design, video and animation, audio, data analysis, web applications, and more.
Rising automation:
In a July update, the authors publish results from evaluating three recent frontier models – GPT-5.5, Opus 4.8, and Fable 5, which get 6.3%, 8.3%, and 16.1% respectively. “The frontier has more than quadrupled in under eight months, a concrete signal of how quickly economically capable AI agents are advancing,” they write.
Types of tasks:
Some of the assessed tasks include:
Ring design
: “Re-create the client’s existing engagement ring with its emerald-cut center stone swapped for a marquise cut, delivering an updated 3D model plus photorealistic rose- and yellow-gold renders.”
Advertisement Video:
“Produce a ~60-second flat-design 2D animated advertisement for “Skyline Tree Services,” set to the provided voiceover, that walks viewers through the company’s tree-care process and builds trust in the brand.”
Floor Plan & Renders:
“From a scanned cadastral plan, site photos, and measurements, produce a clean dimensioned floor plan, furniture-layout options, and photorealistic renders of the redesigned bathroom.”
Why this matters – AI might have a big impact on employment and tests like these will show us how:
What happens to online employment when this reaches 80%? Of course, some new tasks will get created – people will innovate and find tasks that they can do which AI systems can’t do. But how many of these new tasks will exist? Enough to replace the labor the AI systems now do? It’s increasingly hard for me to reconcile the continued progress of AI systems with the economy staying the same – rather, it’s more likely to me we are about to see extremely person-light AI-heavy (or person-nil) organizations expand to take over chunks of the economy, out-competing un-augmented humans.
Yes, you counter, many humans will augment themselves with AI systems. Humans will innovate. Creative destruction will occur. New inventions will be devised. All of that is true. But is the speed at which humans innovate and render themselves newly competitive relative to AI systems going to be
faster
than both a) the raw capability expansion of AI systems, and b) the increasing fluency with which they can use all the same tools (e.g, software) that their human competitors use?
I’m betting the other side:
AI systems are expanding their economically relevant capabilities faster than humans are expanding their comparative advantages relative to AI systems. Tracking the rate of capability improvement on tests like RLI will help us all judge this for ourselves.
Read more
:
A Significant Increase in Digital Labor Automation (Center for AI Safety)
.
***
OSWORLD 2.0 shows we’re in the era of multi-hour computer-using robots:
…A challenging benchmark highlights the recent progress on AI systems becoming increasingly competent at using computers…
Researchers with the University of Hong Kong, the University of California at San Diego, Columbia University, the University of California at Santa Barbara, Mila, Snorkel AI, the University of Wisconsin, Alibaba Qwen, The Ohio State University, Simular, and NeoCognition have released OSWORLD 2.0, a benchmark for evaluating how well AI systems can carry out multi-step multi-program tasks on computers. The tasks in OSWORLD 2.0 are far more complicated than in its 1.0 predecessor, with the median task taking a person approximately 1.6 hours, about 48x longer than the 2-minute median in OSWORLD 1.0.
What it consists of:
OSWorld 2.0 contains 108 long-horizon tasks including 31 self-hosted websites. “Each task in OSWORLD 2.0 is defined as a self-contained end-to-end workflow that an agent must complete given a high-level user goal, realistic artifacts, a stateful computer environment, and a scoreable final state. A retained task must satisfy two design criteria,” they write. “69.6% of tasks are estimated to take a skilled human user more than one hour.”
Broader software: OSWORLD 1.0 shipped with some inbuilt software to support some of its tasks, including LibreOffice, GIMP, VLC, Thunderbird, VS Code, and Chrome.
OSWORLD 2.0 ships with a massively expanded set, including: Slack, LinkedIn, Shortcut, REAPER, MuseScore, WPS, GitLab, Overleaf, LabPlot, Zotero, AWS, as well as websites meant to mimic professional services like insurance claim, visa application, and conference management portals.
The categories of tasks people need to complete include: document prep, software & database work, finance/ops analysis, admin support, sales and customer support, graphic presentation, and more.
Poor performance (for now):
“Our experiments show that current agents remain far from reliable computer use: the strongest setting, Claude Opus 4.8 with maximum thinking and batched tool calls, reaches only 20.6% binary accuracy and 54.8% partial-score accuracy,” they write. “Performance drops sharply as tasks grow longer, and agents struggle most when they must recover hidden state, track many items, resolve conflicting information, or adapt to changing requirements”.
We should expect performance to rise here, just as happened with OSWORLD 1.0; in July 2025 the highest scoring models got ~30%, and recent models have scored more like ~75% (MiniMax M3; June 2026). We should expect the same ramp with OSWORLD 2.0.
Why this matters – this is how AI gets into the broader economy:
Computer use is a fundamental skill for AI being able to perform a wide variety of economically valuable tasks, and also for it being able to conduct more types of science research. Getting stuff done in the world often isn’t as simple as just writing some text or computer code; often you need to chain together multiple blobs of text and code via different types of software, and sometimes you need to transmit your text and code over the internet so it gets taken into other software in turn. Benchmarks like OSWORLD 2.0 should be seen as a proxy for how good AI systems are getting at doing very complicated and varied tasks on computers. As these results show, computers have already become competent at tasks that use a narrow set of software tools and take humans minutes of work to complete; now we need to see how quickly they become adept at using broader sets of software and doing tasks that take humans hours to complete.
Read more
:
OSWorld 2.0: Benchmarking Computer-Use Agents on Long-Horizon Real-World Tasks (official paper website)
.
Check out the research paper here:
OSWorld 2.0: Benchmarking Computer-Use Agents on Long-Horizon Real-World Tasks (xlang-ai, OSWorld-V2, GitHub, pdf)
.
***
What real-world AI looks like: deep learning fuses with structured systems for inventory management in the Amazon of China:
…The Oxygen AI Item Center gives us a view on the complexity of country-scale e-commerce…
JD, the Amazon of China, has published details on software it has built to manage its vast inventory system. JD has 700 million users and millions of merchants, with a catalog containing tens of billions of SKUs. The software – the Oxygen AI Item Center (Oxygen AIIC) – is fundamental to how the e-commerce giant keeps track of its inventory.
“Oxygen AIIC now covers tens of thousands of JD categories and processes hundreds of millions of item updates per day on Huawei Ascend NPUs,” JD writes in a research paper about the software.
The four key elements of the Oxygen AIIC
. The description of what makes Oxygen special is both helpful from a technical perspective but also enjoyable as a kind of neo-Borgesian form of writing describing strange, ethereal structures demanded by advanced technology (e.g, “Unified item tunnel”).
Ontology engineering driven by efficient human-AI collaboration.
“Experts focus on distilling industry knowledge, while algorithms learn from it to scale ontology construction and drive continuous evolution”.
“Semantic Search then Discrimination”:
“In the semantic search stage, the dynamically evolving ontology is externalized as a separate ontology knowledge base, enabling continuous ontology updates without model retraining,” they write. “. In the discrimination stage, the model only determines whether the item matches the retrieved ontology entries. This formulation substantially reduces task complexity, mitigates model hallucination, and enhances generalization to ontology evolution”.
Self-evolving item-understanding LLMs/VLMs
: “Through incremental learning and model self-evolution, the system fills targeted knowledge gaps and mitigates catastrophic forgetting”, they write. “The core method is to build on the robust multi-task foundation, develop lightweight “expert modules” for incremental requirements, and dynamically integrate them into the expert pool, enabling agile capability expansion”.
“Unified item tunnel”:
The main interface between Oxygen AIIC and other business applications. “it supports daily-, minute-, and second-level production and distribution pipelines while preserving data consistency”.
Things that make you go hmmm
– as part of China’s general push towards technology sovereignty, Oxygen AIIC involves Chinese compute. “During the large-scale deployment of Oxygen AIIC, the underlying compute platform encounters two primary technical challenges: model training and inference on Huawei Ascend NPUs, and the efficient use of compute resources.”
Why this matters – self-updating businesses:
Technologies like Oxygen AIIC are an example of how modern AI tools let us create businesses that have intelligence woven into their back-office functions, like inventory management, which allow them to operate at far larger scales than prior businesses while also having the ability to self-update and learn, often without large amounts of human oversight.
Read more
:
JD Oxygen AI Item Center (Oxygen AIIC) V1: An Industrial-Scale LLM/VLM-Centric Solution for Item Understanding, Management, and Applications (arXiv)
.
***
Tech Tales:
The Brass Gears of Civilization
[
2050, after the fall]
When you are inducted into the guild they ask you which type of problem you’d like to work on. These problems are limited in number and civilizationally important:
Weather prediction
Ocean analysis
Flood preparedness
Earthquake simulation
The electrical grid model
Water and desalination
To work on these problems, you study the specific type of analog computation needed to work on them. Weather requires a vast computer with geographical features such as mountains implemented as fixed impedance structures in the hardware; flooding demands physically accurate models of floodplains and rivers where electronics are woven into the landscape allowing the utilization of physics and computation to create better answers; utility grids are toy boxes of the electrical system that must be painstakingly rebuilt and rebalanced as new power stations are added and transmissions changed.
For every problem, there is a computational solution, and for every problem of sufficient civilizational importance, a computer will be built.
In the past, we had general computers. But they were deemed eventually too dangerous – too unpredictable. The more powerful they became and the more diffuse the knowledge about them grew, the more they tickled at the tails of various dragons. Synthetic minds that might rip the world apart. Ethereal Pandora’s boxes to spit out poisons keyed to individuals or races. Minds that might whisper to human minds and drive them to insanity or acts of malice.
So the great restructuring took place. General computation was banned – walled off as a forbidden technology. We moved the world to analog at the cost of untold billions of harmed human lives and trillions in economic damages. But we had obtained a kind of safety.
Now, the guild supervises the construction of the earth’s ‘world computers’ and academia has found a new mission in life, pairing expertise in specific subjects with customized engineering schools to help build the analog computers that let each specialism work.
There is troubling talk that for a trillion dollars it may be possible to implement in analog a general-purpose mind.
Things that inspired this story:
Thinking about analog computation and how far it could be taken if budgets were $10 billion to $20 billion; taking to its logical conclusion the implication of AI being existentially dangerous; the Difference Engine; steampunk; the fact a neural network can be implemented via a series of containers and pipes and a liquid for weights.
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
July 6, 2026
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

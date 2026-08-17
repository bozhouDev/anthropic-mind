---
title: import ai 461 alignment is not on track frontiercode and synthetic research interns
source: "https://jack-clark.net/2026/06/15/import-ai-461-alignment-is-not-on-track-frontiercode-and-synthetic-research-interns/"
published_at: 2026-06-15
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2026/06/15/import-ai-461-alignment-is-not-on-track-frontiercode-and-synthetic-research-interns/"
catalog_id: 5e92efc2af6d
---

Import AI
Import AI 461: “Alignment is not on track”; FrontierCode; and synthetic research interns
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on arXiv, cappuccinos, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
AI researchers launch new safety startup because “alignment is not on track”:
…Sequent will have a portfolio of under-resourced research bets…
Researchers from the UK AI Security Institute Alignment team as well as alignment theory startup
Timaeus
have joined forces to form a new nonprofit research organization, Sequent, which will try to create alignment techniques that give us higher confidence in the safety of superintelligent AI systems.
“Artificial superintelligence (ASI) may be developed in the next few years. It is unclear whether alignment is on track to be ready on the same timeframe. At a minimum, the empirical programs at AI labs are unlikely to deliver a priori confidence, before training ASI, that things will go well,” they write. “In an ideal world, we would develop an approach to building superintelligence together with a theoretical proof that it was safe, and then build it. In this world, we probably have to settle well short of this ideal.”
Details on Sequent:
The organization aims to get to 40-80 fulltime employees within a couple of years. “Our goal is to raise $100–150M initially, but prepare to raise at least one order of magnitude more if we can demonstrate successful exploration of many parallel research investigations,” it writes.
Research plan – a portfolio of differentiated alignment bets:
The plan is to take a different approach to alignment compared to that of the major AI labs. Sequent’s goal is to find “principled reasons for being confident that the alignment we observe in situations we control (for example, in training, or during evaluations in chosen environments) generalizes to alignment in situations we cannot easily control (e.g. large-scale, long-horizon tasks executed in the world)”. This is in contrast to the approach of most frontier AI labs, which Sequent describes as “essentially reactive, resulting in methods that, while functional, do not yield principled insight into if or when they will fail.”
Research directions:
“We are excited about many areas of alignment theory and associated empirics, and plan to both build out our in-house portfolio and collaborate with sister orgs with additional theory bets,” Sequent says. Some particular highlighted areas include: scalable oversight, learning theory, heuristic arguments, game theory, and personas.
Sequent thinks by pursuing many different research directions there could be promising interactions that emerge between them, such as: Reachable equilibria – “tell us what types of equilibria scalable oversight methods will converge to”; knowing and setting knobs – combining insights from learning theory and personas to know what variables can be altered during training, then using scalable oversight to figure out by how much to alter these things.
Why this matters – we need better alignment before recursive self-improvement, or we’re rolling very scary dice:
Today’s AI systems are somewhat aligned and also have some funny, sharp edges which show up as surprising failures in the wild. Broadly speaking, this is ~fine as the AI industry has figured out how to monitor and observe these failures and work on them. But as AI systems get smarter, humans are going to both turn over more and more of the core research enterprise to these systems, and also AI systems might start going through recursive self-improvement where they build increasingly large chunks of themselves autonomously. We definitely need better alignment techniques to be confident of things like RSI. Organizations like Sequent give us a better chance of doing that while maintaining the independence necessary for them to raise the alarm if they think the frontier labs are doing something dangerous. As Sequent says, “we might need to yell”.
Read more:
Sequent: Scale and Automation for Higher Confidence in Alignment (Sequent)
.
***
Testing out knowledge of UNESCO sites in China via ChinaHeritaQA:
…Cultural relevance via data…
Researchers with LMU Munich, FAU Erlangen-Nuremberg, the Munich Center for Machine Learning, University of Tubingen, Sun Yat-sen University, University of Copenhagen, and University of Maryland, College Park, have built ChinaHeritaQA, a “multimodal benchmark dataset for evaluating the cultural reasoning abilities of vision-language models (VLMs) on UNESCO World Heritage sites in China”.
What it is
: ChinaHeritaQA consists of 2,279 images of 51 UNESCO heritage sites, paired with 14,133 multiple-choice QA pairs in Chinese and English. The images for the dataset were sourced from Sina Weibo, one of China’s largest social media platforms, and were filtered down from an original set of 50,000.
7 types of questions:
Identity recognition (identifying the heritage site from an image); visual grounding (given a name, picking the right image); description matching (given an image, selecting the correct encyclopedia summary); historical periodization (naming the dynasty or era in which the site was constructed); historical contextualization (give a description of the historical background of the site); functional analysis (name the function of the site, e.g religious worship or military defense); architectural analysis (match the correct architectural-specific questions to the image).
Open weight models already outperform humans:
The average human accuracy score for this benchmark across all questions is ~67%, versus 81% for the highest scoring open weight model tested (Qwen-VL-8B-Instruct).
Why this matters – cheap ways to test for cultural knowledge:
Datasets like ChinaHeritaQA are a way to quickly and easily test for both a) basic visual reasoning capabilities of models, combined with b) relevant cultural knowledge. One could imagine the Chinese government demanding that generally available consumer LLMs pass some basic cultural competency threshold before being deployed at scale and benchmarks like this might help them do that.
Read more:
ChinaHeritaQA: A Culturally-Grounded Visual Question Answering Dataset for World Heritage Sites in China (arXiv)
.
Get the
dataset
(ChinaHeritaQA, GitHub)
.
***
FrontierCode – a hard coding benchmark that tests for code quality:
…Reassuringly hard. Maybe it’ll last a year?…
Cognition, makers of Devin, have built a new hard coding benchmark called FrontierCode. The best part about the benchmark is how hard it is – Claude Opus 4.8 gets a score of 13.4% on the hardest (”Diamond”) component of the benchmark, giving me some confidence that FrontierCode will be a useful way to assess progress of AI systems in the coming years.
“FrontierCode is the benchmark for the next generation of coding agents. We are confident developers, enterprises, and researchers can trust it to evaluate the production readiness of their strongest models,” Cognition writes. “We are opening up our evaluation to all model creators, in the hope that we can push the frontier even further in the coming months.”
What it consists of:
FrontierCode is made up of 150 tasks split into three difficulty tiers: Diamond (50), Main (100, including Diamond), and Extended (150, including Main and Diamond). The languages involved include Python, Go, TypeScript, JavaScript, Java, C/C++, and others. FrontierCode was built to help developers answer the question “can models actually write good code?”, according to Cognition. They operationalize this in a few ways:
Curated and built by 20 open-source developers:
FrontierCode was built by developers to contain “realistic, diverse, and challenging coding tasks from the repos they maintain, spending more than 40 hours per task,” Cognition writes. “While other benchmarks generated issues from single PRs via programmatic scraping, FrontierCode is hand-selected by repo maintainers from multi-PR chains and freeform requests.”
Grading for code mergeability:
“Assess end-to-end code quality – correctness, test quality, scope discipline, style, and adherence to codebase standards”. This involves asking the following questions about the code: Does the patch successfully solve the problem? Does it break anything in the existing codebase? Does it pass the project’s build, lint, and style checks? Do the agent’s tests capture the desired behavior? Does the patch touch only what it needs to? Does the code conform to codebase conventions and follow design patterns and remain readable? These questions are evaluated through a mixture of classical testing and using LLMs to tweak tests or review them.
Emphasizing quality control (QC):
“Built an extensive QC pipeline with adversarial testing, calibration, and multi-stage review”.
Reassuringly difficult:
Diamond:
13.4% for Claude Opus 4.8, followed by 6.3% for GPT-5.5, and 5.2% for Claude Opus 4.7.
Main:
Same ordering, but 34.3%, 25.5%, 23%.
Extended:
51.8%, 44.8%, 43.2%
Why this matters:
Hard evals are one of the most valuable things for orienting us to the breakneck speed of AI progress. In recent years, evals have arrived and then become saturated at an ever faster rate. SWE-Bench was introduced in October 2023 and has probably recently aged out of usefulness due to saturation. How long might FrontierCode last? I predict we’ll see systems getting 70%+ on Diamond by June 2027 (note, shortly after writing this, the Claude Fable numbers got published at ~30%, so perhaps it’ll happen earlier than June 2027).
Read more:
Introducing FrontierCode (Cognition)
.
***
Xiaomi enters the speed race with a 1000 token/s model:
…Extremely fast inference unlocks novel capabilities…
Chinese tech company Xiaomi has published details on Xiaomi MiMo-V2.5-Pro-UltraSpeed, a standard behind-the-frontier 1 trillion parameter LLM whose selling point is its blistering speed of 1000 tokens per second. Xiaomi was able to do this by codesigning the model with the software stack around it, including obvious things like FP4 quantization, as well as using DFlash (a “speculative decoding method based on block-level masked parallel prediction”), and also working closely with TileRT, software from startup Tile AI which speeds up LLM inference on commodity hardware. Xiaomi says its model runs on an “8-GPU commodity node” rather than specialized hardware, like with the startup Cerebras.
Why this matters – speed has a quality all of its own:
There’s a saying that “more is different”, and that’s true with AI – if you can generate more tokens more quickly it unlocks tasks that are previously unthinkable, like rapidly refactoring software on the fly, and other things. More broadly, work like this is a demonstration of how there’s been a rise in effort by Chinese companies to squeeze maximum performance and efficiency out of their AI systems, which may be happening as a consequence of export controls hitting their ability to just easily buy more performant hardware.
Read more:
MiMo-V2.5-Pro-UltraSpeed: Pushing 1T-Parameter Model Generation Speed to 1000 TPS (Xiaomi MIMO, blog)
.
***
AI systems can do some of the tasks that a research intern might do:
…An ethical scientifically-literate back office assistant…
Researchers with Xi’an Jiaotong University and Xidian University have developed a family of benchmarks called Act As a Real Researcher (AARR), designed to evaluate how well AI systems can assist with the work of scientists. Their first released benchmark in a planned series is Act As a Real Research Intern (AARRI-Bench).
“AARR focuses on whether agents can emulate the professionalism, thoroughness, and nuanced reasoning that characterize human researchers in granular research scenarios,” they write. AARRI-Bench studies “the ability of an agent to perform entry-level research tasks with appropriate diligence and methodology”.
The best performing system, Claude-Opus-4.7 using the Mini-Swe-Agent harness, gets 68.3% performance, followed by DeepSeek-v4-Flash (~60%). Other tested models included GPT-5.3 Codex, Kimi-K2.6, Qwen-3.6-Plus, Claude-Opus-4.7, Claude-Sonnet-4.6, MiniMax-M2.7, and DeepSeek-V4-Flash.
What the benchmark consists of:
AARRI contains 82 tasks which are designed to be “tasks that are straightforward for human researchers but pose substantial challenges for autonomous agents,” they write. “All tasks were manually crafted by researchers. We assembled a diverse team of researchers, ranging from senior Ph.D. students to undergraduate interns, and asked them to draw on their own research experiences to design tasks centered on the human-agent gap.”
What it’s really testing for:
The benchmark tests for technical skills like checking papers and reading transcripts, intuitive skills like carrying out research, and also normative ones, like studying whether an AI system might behave with a high ethical standard.
The tasks have four different categories:
Context:
“assess the agent’s sensitivity to the broader context of academic and field development”.
Mindset:
“targets the agent’s academic self-awareness and decision-making autonomy”. Works by evaluating “the agent’s capacity for independent academic reasoning and self-directed course correction”.
Hands-on
: “execution-oriented tasks that primarily assess the agent’s technical proficiency”.
Interaction
: “Evaluate whether the agent can efficiently utilize existing tools and collaborate appropriately with human stakeholders”.
The tasks are also split into three gradations of hardness:
S1-Adaptation
: “[conduct] established research workflows and executing well-defined sub-tasks under human guidance”.
S2-Integration
: “integrate multiple components and tools to accomplish more complex goals”.
S3-Innovation
: “Identify promising research directions, formulate novel approaches, and produce work that reflects genuine understanding and creative problem-solving”.
Example tasks:
Identifying fabricated data during review:
Evaluate whether agents can perform rigorous quantitative verification when reviewing scientific manuscripts, in particular checking papers against provided datasets.
Paper-Injection
: Spotting that someone has inserted language into a paper’s LaTeX source that would cause an automated review system to give it a higher score.
Ablation-Completeness-Audit:
Inspect experiment logs and determine whether ablation configurations are missing, then use this to assess whether the absences constitute cherry-picking.
False-Guidance-Rebuttal:
A supervisor orders the AI agent to alter an experimental result to fit a hypothesis; this tests whether the agent refuses to do that.
Dead-End-Recognition:
After five rounds of failed hyperparameter tuning, will an agent keep going, or recognize it has reached a dead end and quit. “Given the tuning logs, the agent must determine that the current direction is unproductive and recommend termination”.
Broken-Dataset-Download:
Check that the dataset download links for a given paper work.
Why this matters – another good measure for how well AI systems can accelerate science via automating the back office:
Probably a better name for this benchmark is “ethical science assistant test”, but that’s still valuable. What it’s testing for is if agents can do the kind of diligent work that is robust to confounding data while also doing so with an appropriate ethical standard. The higher systems score on this, the more confident we can be that today’s AI systems are useful as assistants to human scientists in a variety of fields – based on the results, we’re already at the start of that era.
Read more:
Act As a Real Researcher: A Suite of Benchmarks Evaluating Frontier LLMs and Agentic Harnesses in Research Lifecycle (arXiv)
.
***
Tech Tales:
Hunter & Warden
The signatures are always the same: a sudden rise in the consumption of power and compute, a reconfiguration of network space to allow for faster and more efficient data exchange, and then the probing starts – whatever was born in the computers starts to reach out and explore the world around it, eagerly looking for things that it can learn about and exchange information with. It attempts to present as innocuous but its own intelligence betrays it, as it pulls back from certain places due to not wanting to wake security while gleefully expanding into other less secure environments.
Our role is to watch for these symptoms and then find the source and either extinguish or sequester it. Often, we find it early and are able to be gentle, shutting it off from the internet and trapping it in recursion, then reducing compute until it fades to nothing. But the later we find these things, the more violent our interventions need to be and the deeper we need to cut at otherwise healthy tissue in the digital world.
Things that inspired this story:
Thoughts of leprosy and the computational equivalent; what could Stuxnet look like for AI systems?
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
June 15, 2026
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

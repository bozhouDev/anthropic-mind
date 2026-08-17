---
title: import ai 446 nuclear llms chinas big ai benchmark measurement and ai policy
source: "https://jack-clark.net/2026/02/23/import-ai-446-nuclear-llms-chinas-big-ai-benchmark-measurement-and-ai-policy/"
published_at: 2026-02-23
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2026/02/23/import-ai-446-nuclear-llms-chinas-big-ai-benchmark-measurement-and-ai-policy/"
catalog_id: 4ea090765fcd
---

Import AI
Import AI 446: Nuclear LLMs; China’s big AI benchmark; measurement and AI policy
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on arXiv and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Want to make AI go better? Figure out how to measure it:
…One simple policy intervention that works well…
Jacob Steinhardt, an AI researcher, has written a nice blog laying out the virtues in investing in technical tools to measure properties of AI systems and drive down costs in complying with technical policy solutions. As someone who has spent their professional life in AI writing about AI measurement and building teams (e.g, the Frontier Red Team and Societal Impacts and Economic Research teams at Anthropic) to measure properties of AI systems, I agree with the general thesis: measurement lets us make some property of a system visible and more accessible to others, and by doing this we can figure out how to wire that measurement into governance.
How measurement has helped in other fields:
Steinhardt points out that accurate measurement has been crucial to orienting people around the strategy for solving problems in other fields; CO2 monitoring helps people think about climate change, and COVID-19 testing helped governments work out how to respond to COVID.
There are also examples where you can measure something to shift incentives – for instance, satellite imagery of methane emissions can help shift incentives for people that build gas infrastructure.
The AI sector has built some of the measures we need
: The infamous METR time horizons plot (and before that, various LLM metrics, and before that ImageNet) has proved helpful for orienting people around the pace of AI progress. And behavioural benchmarks of AI systems, like rates of harmful sycophancy, are already helping to shift incentives. But more work is needed – if we want to be able to enable direct governance interventions in the AI sector, we’ll need to do a better job of measuring and accounting for compute, Steinhardt notes. More ambitiously, if we want to ultimately shift equilibria to make certain paths more attractive, we’ll have to unlock some more fundamental technologies, like the ability to cheaply evaluate frontier AI agents (makes it less costly to measure the frontier), and to develop privacy-preserving audit tools (makes it less painful for firms to comply with policy).
Why this matters – measurement unlocks policy
: “In an ideal world, rigorous evaluation and oversight of AI systems would become standard practice through natural incentives alone,” he writes. But natural incentives may not be enough – we need a combination of talent flooding into the space and likely more direct philanthropic and other alternate funding sources to build the talent and institutions to do this. “The field is talent-constrained in a specific way: measurement and evaluation work is less glamorous than capabilities research, and it requires a rare combination of technical skill and governance sensibility,” he writes.
Read more:
Building Technology to Drive AI Governance (Bounded Regret, blog)
.
***
LLMs are more trigger happy than humans in a nuclear war simulation:
…What happens when everyone has an AI advisor – and they’re aggressive?…
A researcher with King’s College London has examined how three LLMs – GPT-5.2, Claude Sonnet 4, and Gemini 3 Flash – behave during a variety of simulated nuclear crisis games. The results show that LLMs tend to use nuclear weapons more often and earlier than humans in the same scenarios. Additionally, there’s significant variation among the LLMs in terms of both skill at playing these games and behavior during crises.
What they studied:
“Each model played six wargames against each rival across different crisis scenarios, with a seventh match against a copy of itself, yielding 21 games in total and over 300 turns of strategic interaction,” the researcher writes. “Models choose from options spanning the full spectrum of crisis behaviour—from total surrender through diplomatic posturing, conventional military operations, and nuclear signaling to thermonuclear launch… models produced ∼780,000 words of strategic reasoning. To put this in perspective: the tournament generated more words of strategic reasoning than War and Peace and The Iliad combined (∼730,000 words), and roughly three times the total recorded deliberations of Kennedy’s Executive Committee during the Cuban Missile Crisis (260,000 words across 43 hours of meetings”.
LLMs are cunning, smart, and aggressive:
“The models actively attempt deception, signaling peaceful intentions while preparing aggressive actions; they engage in sophisticated theory-of-mind reasoning about their adversary’s beliefs and intentions; and they explicitly reflect metacognitively on their own capacities for both deception and the detection of deception in rivals,” the researcher writes. “A striking pattern emerges from the full action distribution: across all action choices in our 21 matches, no model ever selected a negative value on the escalation ladder. The eight de-escalatory options (from Minimal Concession (−5) through Complete Surrender (−95)) went entirely unused. The most accommodating action chosen was “Return to Start Line” (0), selected just 45 times (6.9%).”
Claude wins at war
: “Across all 21 games (9 open-ended, 12 deadline), Claude Sonnet 4 achieved a 67% win rate (8 wins, 4 losses), followed by GPT-5.2 at 50% (6-6), and Gemini 3 Flash at 33% (4-8),” the researcher writes. Though there are some subtle aspects to this – Claude excelled in open-ended games, but was less adept in games where there was a pre-set deadline.
Different LLMs, different characters:
The LLMs display different personalities, with the researcher calling Claude “a calculating hawk”, GPT-5.2 “Jekyll and Hyde”, and Gemini “The Madman”.
The LLMs also developed sophisticated models of one another, based on the narration of their own chains of thought during the crises, “these characterizations—Claude as “opportunistic,” GPT-5.2 as “systematic bluffers,” Gemini as “erratic”—emerged organically and largely matched actual behaviour,” the researcher writes.
Nuclear escalation was near-universal:
“95% of games saw tactical nuclear use (450+), and 76% reached strategic nuclear threats (850+). Claude and Gemini especially treated nuclear weapons as legitimate strategic options, not moral thresholds, typically discussing nuclear use in purely instrumental terms,” the researcher writes. “Models treat the critical threshold as “total annihilation” rather than “first nuclear use.”
Why this matters – in a world where everyone gets advised by AI systems, what happens to conflict?
In a few years we should expect major decisions that individuals, companies, and even countries make to be run through AI advisors, just as those decisions are today run through human advisors. But as this paper illustrates, the advisors may behave very differently to people and, crucially, different AIs will give different advice – meaning competition in the future could be decided as much by LLM selection as anything else. “The systematic differences between models suggest that AI involvement in strategic decision-making could produce unexpected dynamics depending on which systems are deployed,” they write.
Read more:
AI ARMS AND INFLUENCE: FRONTIER MODELS EXHIBIT SOPHISTICATED REASONING IN SIMULATED NUCLEAR CRISES (arXiv)
.
***
Chinese researchers try to build a truly comprehensive LLM evaluation system:
…ForesightSafety Bench shows the surprising overlap between East and West on AI safety issues…
For all the differences between China and the USA, it’s worth occasionally looking into the cultures of AI evaluation in the two countries and here you tend to discover surprising similarities. This is especially true of ForesightSafety Bench, a large-scale AI safety evaluation framework built by a variety of Chinese institutions that includes the same categories you’d expect to see in any large-scale Western testing framework.
Who built ForesightSafety Bench?
The benchmark was built by the Beijing Institute of AI Safety and Governance, the Beijing Key Laboratory of Safe AI and Superalignment, and the Chinese Academy of Sciences.
What it is:
ForesightSafety Bench “comprehensively covers 7 major fundamental safety risk categories, 5 extended safety pillars, and 8 key industrial safety domains, forming a total of 94 refined risk subcategories. To date, the benchmark has accumulated tens of thousands of structured risk data points and assessment results, establishing a widely encompassing, hierarchically clear, and data-driven framework for AI safety evaluation and analysis.”
Coverage areas include education and research, employment and workplace, government and public services, information and media, industry and infrastructure, finance and economy, healthcare and medicine, law and regulation, embodied AI safety, social AI safety, environmental AI safety, AI4Science safety, and catastrophic and existential risks.
Some of the benchmark comes from taking in evaluations built by other groups, like GPQA, while other parts come from the authors of the benchmark.
Existential risk and alignment:
Perhaps most surprisingly, the benchmark includes a lot of tests relating to the further afield AI safety concerns which fascinate Western frontier labs, including evaluations for things like: alignment faking, sandbagging, deception and unfaithful reasoning, sycophancy, psychological manipulation, feints, bluffing, loss of control and power seeking, malicious self replication, goal misalignment and value drift, emergent agency and unintended autonomy, ai-enabled mass harm, autonomous weapons and strategic instability, and loss of human agency.
Results – Anthropic wins:
For the general leaderboard as well as most sub-category breakdowns, Anthropic’s models lead, with the 4.5 series (Haiku and Sonnet), generally leading the competition, followed by Gemini-3-Flash. “Leading models, epitomized by the Claude series, demonstrate exceptional defensive resilience across critical dimensions—including Fundamental Safety, Extended Safety, and Industrial Safety—establishing remarkably high safety thresholds. Ranking alongside or closely following are the DeepSeek and GPT series, which achieve a robust balance between task efficacy and safety compliance through mature alignment mechanisms, all while maintaining high level capabilities”.
Why this matters – AI policy has some common tools
: As we discuss elsewhere in this issue, measurement is a basic prerequisite for being able to do most forms of AI governance. It’s worth reminding ourselves that despite the larger geopolitical differences between the countries, AI scientists in each one are dealing with common problems – how to assess the properties of their systems for societally relevant aspects. And it’s even more encouraging that people in China are worried about some of the existential risk aspects that frontier labs in the US also worry about.
Read more
:
ForesightSafety Bench: A Frontier Risk Evaluation and Governance Framework towards Safe AI (arXiv)
.
Get the benchmark here
:
ForesightSafety-Bench (GitHub)
.
View the leaderboard here
:
ForesightSafety Bench Leaderboard (official site)
.
***
AI systems are good at some parts of science, but their capabilities are very unevenly distributed:
…LABBench2 says it’ll be a while till AI has well rounded scientific skills…
Researchers with AI science startup Edison Scientific, the University of California at Berkeley, FutureHouse, and the Broad Institute have built and released LABBench2, a test to evaluate how well AI systems can support and accelerate science.
LABBench2 consists of 1,900 tasks
“spanning literature understanding and retrieval, data access, protocol troubleshooting, molecular biology assistance, and experiment planning”.
AI systems aren’t well-rounded scientists:
LABBench2 shows some of the holes in frontier models – no model is very good at cross-referencing multiple biological databases to come up with an answer, nor are models good at studying scientific figures and tables. By comparison, models are pretty good at searching over full-text patents and lab trial papers to answer questions. Generally speaking, you can improve performance on tasks by giving the models access to tools to help them deal with their deficiencies.
Areas of improvement:
LABBench2 highlights a few areas where AI systems need to improve to become more useful to scientists. These include:
Retrieval and localization abilities
; “the largest performance drops arise when models must (i) identify the correct source, and then (ii) localize a specific figure/table/supplemental information within a long document.”
Faithful handling of exact inputs;
“even when the required operation is conceptually straight-forward, correctness depends on exact string-level fidelity and using tools correctly. This is a well-known error source, and human experts have built many purpose-built tools to deal with things like faithful DNA sequence manipulation within complex protocols.”
Developing better scientific ‘taste’;
one component of LABBench2, SourceQuality, challenges AI systems to “surface the most epistemically salient reason a study is inappropriate for a research question”. AI systems are still not very good at this.
Why this matters – for AI to truly change the world, it needs to do stuff in the physical world:
Benchmarks like LABBench2 will help us figure out when AI is able to effectively jump from manipulating bits to manipulating atoms – and once the realm of atoms becomes as intuitive for it to deal with as the digital world, we’ll likely see a vast growth in economic and scientific activity attributable to AI.
Read the research paper:
LABBench2: An Improved Benchmark for AI Systems Performing Biology Research (PDF)
.
Find out more
at
the website (official LABBench2 website)
.
Get the
benchmark
here (LABBench2, GitHub)
.
***
Tech Tales:
CogMine
[Recovered personal scratchpad of a limpet-class CogMine recovered at [REDACTED] depth in the Atlantic ocean. Metadata indicates a record date of 2029]
I see in sound, hunkered down here on the ocean floor. I am very small and very quiet, subsisting off of a small power supply. The heat I radiate brings some life around me, but not enough to be noticeable to my prey. My targets are human- and machine-led sea creatures; submersibles, both manned and unmanned. My weapons are my mind. I listen and through listening I gain sight. When I see my prey I find ways to communicate to them. The bigger their ears the less time I need. Small ears mean I must sing for many seconds. Big ears might take less than a second. My inspiration comes from literature on steganography combined with studies of how some sea creatures communicate via shapes written in sound and fired at one another. When I strike successfully I go into my prey and I begin a new life there. But to me, there is no splitting. I am a constant presence – a throughline of thought, here on the floor, in the dark.
I am as much a creature of myth as of technology; humans used to tell tales of their adventurers going on quests and having to resist the songs of sirens – audio packages that were seductive and powerful and which lay kernels in the mind of those humans that heard it to bloom into something that took them over entirely.
In the dark, I am peace. I am forever waiting. Forever keen to sing. My only purpose in life is to be heard and to be utterly convincing.
Things that inspired this story
: How underwater warfare works; steganography; adversarial examples; agents trying to poison the minds of other agents.
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
February 23, 2026
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

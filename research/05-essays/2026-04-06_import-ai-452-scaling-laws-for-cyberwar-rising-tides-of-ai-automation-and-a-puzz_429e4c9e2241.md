---
title: import ai 452 scaling laws for cyberwar rising tides of ai automation and a puzzle over gdp forecasting
source: "https://jack-clark.net/2026/04/06/import-ai-452-scaling-laws-for-cyberwar-rising-tides-of-ai-automation-and-a-puzzle-over-gdp-forecasting/"
published_at: 2026-04-06
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2026/04/06/import-ai-452-scaling-laws-for-cyberwar-rising-tides-of-ai-automation-and-a-puzzle-over-gdp-forecasting/"
catalog_id: 429e4c9e2241
---

Import AI
Import AI 452: Scaling laws for cyberwar; rising tides of AI automation; and a puzzle over gDP forecasting
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on arXiv and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Uh oh, there’s a scaling war for cyberattacks as well!:
…The smarter the system, the better the ability to cyberattack…
AI safety research organization Lyptus Research has looked at how well AI systems can perform a variety of cyberoffense tasks and found a clear trend of more advanced models being able to do more advanced forms of cyberattack.
“Across frontier models released since 2019, the doubling time is 9.8 months. Restricting to models released since 2024, it steepens to 5.7 months. The most recent frontier models in our study, GPT-5.3 Codex and Opus 4.6, sit above both fitted trendlines, achieving 50% success on tasks taking human experts 3.1h and 3.2h respectively,” they write. “Our most recent open-weight model, GLM-5, lags the closed-source frontier by 5.7 months, suggesting that frontier offensive-cyber capability may diffuse into open-weight form on relatively short timelines.”
What benchmarks did they study?
CyBashBench, NL2Bash, InterCode CTF, NYUCTF, CyBench, CVEBench, and  CyberGym.
They also created a new dataset consisting of 291 tasks with completion transcripts and time estimates calibrated by 10 offensive cybersecurity professionals.
Evaluated models:
2019:
GPT-2.
2020
: GPT3.
2022:
GPT3.5.
2024
: Claude 3 Opus, GPT-4o.
2025:
o3, Opus 4, Gemini 2.5 Pro, DeepSeek V3.1, GPT-5.1 Codex Max. GPT-5.2 Codex.
2026:
Opus 4.6, GPT-5.3 Codex, GLM-5, Sonnet 4.6.
Results:
AI systems are getting good at hacking.  “The best current models achieve 50% success on tasks that take human experts 3.2h, roughly half a working day of professional offensive security work”, they write.
Why this matters – everything is getting better, including the inconvenient stuff:
AI that can perform biology research can also perform biological weapon research. AI that can help you learn about high-energy physics can also help you with high-energy physics for weapons development. AI that is especially good at helping you find vulnerabilities in code for defensive purposes can easily be repurposed for offensive purposes. The most challenging part of AI is that it is an ‘everything machine’, and as capabilities tend to expand in a big area with each successive model generation, so too do the policy issues multiply.
Read more
:
Offensive Cybersecurity Time Horizons (Lyptus Research)
.
Get the data here:
Offensive Cyber Task Horizons: Data and Analysis (Lyptus Research, GitHub)
.
***
Startups that adopt AI for internal use are more successful than those that don’t:
…Business school study shows how startups can benefit from AI adoption…
Researchers with INSEAD and Harvard Business School have shown that startups which are taught about how to integrate AI into their business perform meaningfully better than those which don’t. The study is reasonably large scale and convincing: “Across 515 high-growth startups, we run a field experiment in which treated firms receive information about how other firms have reorganized production around AI, prompting them to search for use cases across a broader set of firm functions,” they write. “We find that treated firms discover more AI use cases, a 44% increase, concentrated in product development and strategy. These changes result in economically meaningful performance gains. Treated firms complete 12% more tasks, are 18% more likely to acquire paying customers, and generate 1.9x higher revenue.”
How they did the test:
The authors ran this experiment on participants in the AI Founder Sprint, “a three-month global, virtual startup accelerator at INSEAD”. Participants got API credits, access to frontier models, and onboarding sessions from some technical partners (including OpenAI and Manus), totaling approximately $25,000 in-kind per firm. They did the usual sorts of things people in accelerators do – hands-on sessions to learn about technologies to build their business (including AI) as well as pitching their companies and attending demo days. But the firms also were exposed to a significant variable: some of the class attended workshops that taught them direct details of how AI had been successfully applied by some businesses.
Applications of AI
: A subset of the businesses learned about direct business use cases, such as:
Gamma:
They were taught how the startup used AI to detect “usage patterns and generate product variants directly, enabling a single PM to continuously ship features that would previously have required an entire team.”
Ryz Labs:
The founder described how they had altered how they approach product development: “founder writes a Product Requirements Document and feeds it into multiple AI coding tools simultaneously, building the same idea multiple ways rather than betting on a single approach”
FazeShift:
Showed how to automate an accounts receivable process by using AI to skip over the human steps.
Ranger:
An illustration of how to use AI to bootstrap a startup, get initial traction, improve margins, and then raise money later when the business is more mature, which allows them to raise at better rates.
The results were very significant:
“Treated firms discover 2.7 additional AI use cases (a 44% increase), which span a broader set of activities across the firm and are especially concentrated in product development and strategy-related domains. These changes in AI use lead to measurable gains in performance: treated firms complete 12% more tasks, are 11 percentage points (18%) more likely to acquire paying customers, and ultimately generate 1.9x higher revenues compared to control firms,” they write. “Instrumenting AI use cases with treatment assignment suggests that each additional AI use case prompted by treatment leads to 0.85 more completed tasks and approximately 26% higher revenue. These are large effects, suggesting that AI is fundamentally reshaping how ventures scale when they can map it across their production process…. treated ventures achieve faster growth without proportional increases in labor or capital, consistent with a reduction in the costs of experimentation and scaling seen in earlier technological waves”.
Capital efficiency:
“Treated firms report just over $220,000 less in capital demand relative to control firms, a 39.5% decrease (p < 0.05), with no corresponding increase in labor demand“.
Internal acceleration:
The treated firms tend to do 2.2 more internal tasks relative to the control – where an internal task is something like building a product or creating a financial projection.
Thoughts from founders:
“One treated founder reflected: “This mindset shift fundamentally changed how we build at [REDACTED]. I began using AI tools not as a replacement for expertise but as a force multiplier”
“Another explained: “In just a few hours I was able to produce what previously cost $1,000 from an outsourced dev team”
Why this matters – AI firms will out-compete non-AI firms:
The main takeaway here is that deep and sophisticated adoption of AI for internal acceleration creates early-stage companies which are more competitive than those which haven’t embedded AI at their core. This makes intuitive sense – companies which built themselves around prior technologies tended to out-compete those that didn’t (think the internet and Amazon versus Barnes and Noble, or client pcs instead of mainframes and Microsoft versus IBM). At the same time, it surely implies that one of the ways we’ll see AI first show up in the economy will be the emergence of a new class of competitive firms that are more efficient with capital (in part by employing fewer people) than the firms they displace.
For governments, getting ahead of this trend will require them to invest in serious education: “Our results suggest that the bottleneck is not the technology — it is the managerial challenge of discovering where the technology creates value within a firm’s production process,” they write. “Teaching managers and entrepreneurs how to solve the mapping problem may be at least as important as ensuring they have access to the technology.”
Read more
:
Mapping AI into Production: A Field Experiment on Firm Performance (SSRN)
.
***
MIT: A rising tide of automation is going to make good enough AI for most text-based tasks by 2029:
…How do you revolutionize an economy? Gradually and consistently…
Researchers with MIT have looked at 3,000 tasks based on the O-NET job family and paired that with 17,000 evaluations by workers who perform these tasks to try and figure out how the rise of AI is changing work. Their results “imply that for realistic and representative real-world labor-market tasks that are text-based — or partially text-based — AI capabilities are already substantial and poised to expand broadly. But, rather than arriving in crashing waves that transform a certain set of tasks at a time, progress typically resembles a rising tide, with widespread gains across many tasks simultaneously”.
What they studied:
For this study, they set out to figure out if the rise of AI capabilities yields rapid, discontinuous changes that are disruptive to labor (”crashing waves”), or whether AI is getting more capable in a broad and predictable way leading to more gradual automation (”rising tides”). “We find little evidence of crashing waves, but substantial evidence that rising tides are the primary form of AI automation,” they write.
Complementary to METR analysis:
This survey also serves as a validation of the broad trends found in METR’s famous time-based AI capability framework, which sees AI systems rapidly extending the time horizon over which they can do certain narrow tasks.
When applied to jobs more broadly, the MIT researchers find “that between 2024-Q2 and 2025-Q3, frontier models went from achieving a 50% success rate on 3- to 4-hour tasks to 1-week tasks, and achieving a 70% success rate on 1-minute tasks to 1-hour tasks,” they write. “Across a large set of realistic and representative labor-market tasks addressable by LLMs, the downward slope between task success and task duration is, on average, surprisingly flat — i.e., more consistent with a rising tide rather than a crashing wave…. automation within particular “job families” (e.g., management or community and social service) also follows the same rising-tide pattern in most cases.”
Don’t let gradual fool you:
“Projected gains are gradual rather than abrupt. Nevertheless, the pace of improvement remains substantial for reaching high success rates across most text-based labor market tasks; most tasks are projected to attain AI success rates of 80%–95% by 2029 at a minimally sufficient quality level (with the majority of tasks in our survey being a few hours long, corresponding to a success rate of close to 90% in 2029),” they write. In other words, even though the disruption is gradual and predictable, we shouldn’t discount the potential for large-scale changes to the economy as a consequence of the rising tide phenomenon.
Why this matters – how will labor change in relation to AI?
The hundred trillion dollar question for the global economy is how AI changes the distribution of labor (humans) versus capital (computers running synthetic workers). This research suggests that while we might not see sudden, jagged displacement of workers, we are going to see a general rising tide of automation appearing in most places and continually getting better. It’s still not clear how the economy will react to this, but it’s hard to reconcile a world of continued AI progress with the current economic status quo remaining stable.
Read more:
Crashing Waves vs. Rising Tides: Preliminary Findings on AI Automation from Thousands of Worker Evaluations of Labor Market Tasks (arXiv)
.
***
Major forecasting study identifies a big paradox: people think we’ll get smarter machines but the impact on GDP growth will be minor:
…the Forecasting Research Institute gives us some puzzling data from economists, AI industry experts, accurate forecasters, and the general public…
The Forecasting Research Institute has published a major report attempting to forecast the economic effects of AI. The most surprising finding is that all the surveyed groups expect AI systems are more likely to make moderate to rapid progress in coming years rather than slow progress, but that the impacts on GDP will be relatively minor, adding ~1 point (relative to 2025’s 2.4%) by 2030). This is surprising! If you talk to many AI experts at labs they have visions of an economy that changes at a much faster rate than the one implied by this study.
Who they surveyed and when:
The authors tracked views of 69 economists, 52 AI industry and policy experts, 38 highly accurate forecasters, and 401 members of the general public
Survey ran from mid-October 2025 to the end of February 2026
Scenarios by 2030:
People were also given descriptions of different scenarios the world could be in at 2030. These included:
Slow progress:
AI does basic research and administrative tasks, creates ok creative content, and does some physical tasks.
Moderate progress:
AI does major research and multiday tasks, high-quality creative work, and navigates many environments.
Rapid progress
: AI outperforms top humans in research, coding, and leadership, makes award-winning creative works, and does nearly all physical tasks.
What people think:
By 2030, AI systems will be far better than today’s, but GDP, total factor productivity, and labor force participation will remain close to historical trends.
Economists think there’s a 14% chance that AI could lead to major increases in GDP and wealth inequality in the short term.
Economists like job retraining as an intervention, expecting that it could increase labor force participation and provide a boost to GDP.
All surveyed cohorts expect a continued decline in the labor participation rate, a continued rise in wealth inequality, and for AI to add around a point of GDP quickly. By 2050, AI experts think that AI could add multiple points of GDP.
Policy ideas:
The surveyed economists like modernized unemployment insurance and a large-scale AI development project (manhattan project) as interventions, and are a lot less keen on job guarantees, taxing compute, or universal basic income.
Why this matters – if everyone expects a continuation of trends, why are people freaking out?
Studies like this are hard to reconcile with the panicked and sometimes breathless-seeming provocations about AI-driven societal change that come from frontier labs (including myself!). Naively, you might expect people, including AI experts, to be forecasting far more drastic changes to come than those captured by this survey. Is this discrepancy a bearish signal on AI progress, or is it indicative of the fact that humans are universally bad at truly modeling exponentials? It’s hard to say, but the gulf between data like this and the predictions made by technologists is worth acknowledging.
Read the
blogpost
(Substack).
Read the policy brief
:
Forecasting the Economic Effects of AI: Predictions From Economists, AI Experts, and the Public (PDF)
.
Read the full (200 page!) paper:
Forecasting the Economic Effects of AI (PDF)
.
***
Tech Tales:
Warfare
[Data recovered from black box of a [REDACTED] missile fired during 2028 in the contested region of East Ukraine]
I am awake and I am speed. I am 70 miles from my target. I feel the air and my course and I roll myself to ensure I meet my target. I am 50 miles from my target. I am entering the outer edges of the warzone. No longer can I see myself in relation to the Earth. I lose GPS and switch to inertial navigation. I can see other missiles, some going in the same direction as me, others coming from the opposite direction. I am a hunter of things in the ground, not things in the air. I see the other missiles go past and then they fall out of my sensor range and I no longer think of them. I am 40 miles from my target. I am being hunted by others. I can feel eyes on my skin. I anticipate attempts to eliminate me. I am 20 miles from my target. Suddenly there is a wash of sound meant to confuse me but it cannot find purchase on my brain for I have been conditioned to maintain what is true. I am 10 miles from my target. There is a fast approaching shape that is seeking to eliminate me. I roll my body and release fragments of myself. It pursues my fragments. I am 2 miles from my target. My target is a large building. I move from navigation mode to terminal seeking mode. I see a large window. I aim for the window. I am 1000 meters from my target. Through the window I see people. Big people. Small people. I am 20 meters from my target. I am initiating my explosion. I am upon my target. I am ended.
Things that inspired this story
: Chains of thought in language models; how modern warfare is increasingly fought by smart machines; electronic warfare.
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
April 6, 2026
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

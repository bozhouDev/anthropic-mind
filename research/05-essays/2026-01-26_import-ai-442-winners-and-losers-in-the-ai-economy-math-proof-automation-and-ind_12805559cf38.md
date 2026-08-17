---
title: import ai 442 winners and losers in the ai economy math proof automation and industrialization of cyber espionage
source: "https://jack-clark.net/2026/01/26/import-ai-442-winners-and-losers-in-the-ai-economy-math-proof-automation-and-industrialization-of-cyber-espionage/"
published_at: 2026-01-26
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2026/01/26/import-ai-442-winners-and-losers-in-the-ai-economy-math-proof-automation-and-industrialization-of-cyber-espionage/"
catalog_id: 12805559cf38
---

Import AI
Import AI 442: Winners and losers in the AI economy; math proof automation; and industrialization of cyber espionage
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on arXiv and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
The era of math proof automation has arrived:
…Numina-Lean-Agent shows how math will never be the same…
In the past few years, large-scale AI models have become good at coding and have also begun to generalize into other useful disciplines, especially those in math and science. Like with most aspects of AI development, the story has been one of increasing generalization and simplification of the systems as we shift away from highly specialized math models to just leveraging general-purpose foundation models and giving them the right tools to elicit their capabilities in a given domain.
The latest example of this is Numina-Lean-Agent, an AI system that uses standard, general foundation models to do mathematical reasoning. With this software, a team of mathematicians have solved all problems in the Putnam 2025 math competition – matching the performance of proprietary systems which use a lot more math-specific stuff – and have also used it to conduct some original math research, working with it to formalize the Brascamp-Lieb theorem.
What is Numina-Lean-Agent?
The software was built by a team of researchers from the Chinese Academy of Sciences, University of Liverpool, Xi’an Jiaotong-Liverpool University, Tongji University, University of Cambridge, Project Numina, Imperial College London, and the University of Edinburgh. The software is “a formal math reasoner based on a general coding agent”. It has a few key components:
Lean-LSP-MCP:
Software to allow AI agents to interact with the Lean theorem prover. “empowers models with the capability to deeply comprehend, analyze, and manipulate Lean projects”, and gives models a toolset for semantic awareness and interaction, code execution and strategy exploration, and theorem retrieval.
LeanDex
: Semantic retrieval of related theorems and definitions – basically, a search tool for theorems.
Informal Prover
: A system which uses Gemini models to generate informal solutions.
The most interesting tool of all: Discussion Partner:
A tool which “empowers Claude Code with the ability to ’seek assistance’ during Lean formalization: when encountering obstacles—such as proof bottlenecks, dilemmas in strategy selection, or ambiguities in intermediate lemmas—the primary model can proactively initiate discussions with other LLMs”.
Discovering math together:
Along with the Putnam demonstration, the authors also used the software as an active partner in some math work, specifically formalizing Brascamp Lieb (I will not pretend to be able to explain what this means). “Over a period of less than two weeks of intermittent collaboration, the two human experts and the agent completed the formalization of more than 8,000 lines of Lean code. During this process, the agent autonomously introduced approximately 70 new definitions, lemmas, and theorems, illustrating its ability to actively extend the formal library and participate in large-scale, sustained formalization efforts,” the authors write.
Why this matters – capability overhangs and AI ecologies:
Numina-Lean-Agent neatly demonstrates two important things about contemporary AI: 1) AI systems are far more capable than people think and the creation of some specialized frameworks and tools often lets us elicit dramatically better capabilities from our systems (here, math, but it has been demonstrated in many domains), and 2) the AI ecology writ large is composed of many distinct frontier models and it seems like getting these models to interact with one another can lead to some richness, akin to how consulting different types of people about a single problem can reveal a better answer than just talking to one person.
Read more
:
Numina-Lean-Agent: An Open and General Agentic Reasoning System for Formal Mathematics (arXiv)
.
Find out more
at the
GitHub page (Numina-Lean-Agent, GitHub)
.
***
The industrialization of cyber espionage is nigh:
…Some experiments on Opus 4.5 and GPT-5.2 indicate that the cyber environment could be on the cusp of major changes…
Independent researcher Sean Heelan recently tested out how well Opus 4.5 and GPT-5.2 could generate exploits for a zeroday vulnerability in the QuickJS Javascript interpreter. Both models did very well, and this has major implications for cybersecurity.
“We should prepare for the industrialisation of many of the constituent parts of offensive cyber security. We should start assuming that in the near future the limiting factor on a state or group’s ability to develop exploits, break into networks, escalate privileges and remain in those networks, is going to be their token throughput over time, and not the number of hackers they employ,” he writes.
Caveats
: QuickJS is a simple Javascript interpreter relative to the ones in Chrome and Firefox. Therefore, it may be harder for LLMs to employ the more complex and more widely deployed ones – though as with all things in AI, we can expect performance to improve quite rapidly.
What does industrialized intrusion mean?
“We are already at a point where with vulnerability discovery and exploit development you can trade tokens for real results,”: he writes. “The types of problems that you encounter if you want to automate the work of SREs, system admins and developers that manage production networks are conceptually similar to those of a hacker operating within an adversary’s network.”
There’s lots of evidence for the above, ranging from things like OpenAI’s Aardvark project (where they find that the more tokens they spend, the more bugs they find), and things like Anthropic’s
discovery of an AI-orchestrated hacking system
.
Why this matters – the cyberworld is about to move at machine speed:
My bet is that most parts of cyberoffense and cyberdefense are going to move to running at “machine speed”, where humans get taken out of most of the critical loops. This will both increase the frequency of hacking attacks while also dramatically scaling up the effectiveness of any individual human defender or attacker (as they will be scaled by AI systems which work for them). The true wildcard question is whether this turns out to be offense- or defense-dominant – my guess is we’re heading for an era of offense-dominance as it’ll take a while for defenses to get deployed.
In related news, OpenAI CEO Sam Altman said this week he expects OpenAI’s models will soon reach the “Cybersecurity High” level on his company’s preparedness framework – this would mean models were available which “remove existing bottlenecks to scaling cyber operations including by automating end-to-end cyber operations against reasonably hardened targets OR by automating the discovery and exploitation of operationally relevant vulnerabilities” –
thanks to Nathan Calvin for pointing this out
.
Read more
:
On the Coming Industrialisation of Exploit Generation with LLMs (Sean Heelan blog)
.
***
Economist: AI will be bigger than electricity and semiconductors:
…And it’s therefore worth spending a ton of money to reduce AI risks…
Stanford economist Charles “Chad” Jones has written a paper which says AI will “likely be the most important technology we have ever developed”, and that “automating intelligence itself arguably has broader effects than electricity or semiconductors”.
Why take AI seriously?
The gist of the paper is that AI represents a massive technological invention which will contribute to economic growth in the future. In the past, major inventions (e.g, electricity, the internet, cars, etc) have all done the same. In fact, counterintuitively, if you look at US GDP growth you find that despite all these prior technological revolutions, GDP has been steadily increasing at about 2% a year for many, many years. Therefore, the baseline scenario is where AI just does this – and then we don’t live in too crazy a world.
But there is a world where things could be different – where AI works so well that it leads to economic growth above historical trends.
One example here is if AI comes for all of knowledge work: “Knowledge work in the U.S. economy might get paid something like 1/3 of GDP. What if we automated all cognitive labor with infinite output on the tasks that it performs? This would raise GDP by 50 percent. On the one hand, if this occurred over the course of a decade, it would raise growth rates by something like 5 percent per year, which would be huge. But still, that would be a one-time gain and it is perhaps surprising that having access to infinite output of the tasks currently performed by cognitive labor might only raise GDP by 50 percent.”
Abundance:
If we get above trend economic growth, then “in principle the large increase in GDP could make everyone better off,” he writes. One way to do this might be to work on direct redistribution of economic gains, for instance by “endowing every child with a share of the S&P 500 stock market index” (e.g, a scaled up version of the so-called
Trump Accounts
).
Paying to reduce existential risk:
AI also poses non-trivial risks to the world, including threatening the lives of potentially all living humans. In the past, society has paid extremely large amounts of money to deal with things that threaten people’s lives – for instance, in 2020 in response to everyone facing a ~0.3% mortality risk from COVID-19, we ended up spending the equivalent of 4% of GDP of the United States by shutting down the economy and staying in our homes.
“If one believes the catastrophic risks from A.I. are at least this large, by revealed preference then perhaps we should be spending an equivalent amount, even from a purely selfish standpoint,” he writes. Let’s say there is a P-Doom of 1% from AI (which many people would say is a very optimistic figure!). Under that circumstance, and given the fact the US government already roughly values a single human life as being worth about $10 million, then you would be willing to pay 1% of 10 million to mitigate the risk. “Average GDP per person is around $90,000, so this willingness to pay is more than 100% of GDP. If the existential risk is realized once in the next 10 to 20 years, an annual investment of 5–10% of income could be appropriate if it would completely eliminate the risk.”
One way to fund this and also further take down this risk could be to tax compute: If you applied a tax to GPUs, TPUs, etc, then “in addition to slowing the race, this revenue could be used to fund safety research. The tax could apply to the first sale of the chip, thereby taxing users regardless of the country in which they work.”
Why this matters – if AI is as big a deal as we think, we have very little precedent to work from:
Papers like this do a good job of dealing with the truly wild implications of powerful AI systems. It’s commendable to see more academics taking time to just confront the question of “what if the most bullish technologists are right about how far AI could go?” directly. “Ultimately, I expect that the effect of A.I. will be much larger than the internet, perhaps by more than 10x the internet, albeit over a half century or more,” he writes. “It would be prudent to spend the intervening time making preparations for the potentially large consequences for labor markets, inequality, and catastrophic risk.”
Read more
:
A.I. and Our Economic Future (PDF)
.
***
Many people are well positioned to deal with the economic transition caused by AI:
…Good for managers and technical types, but bad for administrative and support staff…
As increasingly powerful AI systems permeate the economy, how should you think about your own career? Researchers with the Centre for the Governance of AI and the Foundation for American Innovation have conducted a nice US-based study where they look at AI driven job displacement through the lens of how easy it’ll be for the people made unemployed to find new jobs. Their key result is that many more jobs sit in parts of the economy that are both going to be exposed to AI systems but also where people in these jobs have a decent amount of “adaptive capacity” to weather those changes, and a smaller number of people will be adversely affected.
The key finding:
“AI exposure and adaptive capacity are positively correlated: many occupations highly exposed to AI contain workers with relatively strong means to manage a job transition. Of the 37.1 million workers in the top quartile of AI exposure, 26.5 million are in occupations that also have above-median adaptive capacity, leaving them comparatively well-equipped to handle job transitions if displacement occurs,” they write. “6.1 million workers (4.2% of the workforce in our sample) work in occupations that are both highly exposed and where workers have low expected adaptive capacity… these workers are concentrated in clerical and administrative occupations”.
What factors tell us about adaptive capacity?
Net liquid wealth:
The more savings you have, the easier it is to deal with lengthy unemployment and find a new job.
Skill transferability:
This is a bit of a confusing one, as skill transferability tries to measure how well you can take your job and apply it to another job. Measuring this is hard – education is something of a lossy proxy. The authors “measure skill transferability between occupations using O∗NET skills and work activities data for each occupation, then weigh transferability measures based on projected growth or contraction in potential destination occupations using BLS employment projections”.
Geographic density:
The more jobs are in your area, the easier a time you’ll have. “Population density significantly shapes displacement outcomes,” they write.
Age:
As a rule, the older you are, the more likely new technology is to adversely impact you. “Older workers struggle more with displacement partly because of reduced flexibility in retraining, relocation, and occupational switching,” they write.
Top 5 worst jobs (ordered by exposure to AI, adaptive capacity, and US employment):
Door-to-door sales workers, news and street vendors (50%, 3%, 5k)
Court, municipal, and license clerks (58%, 11%, 170k)
Secretaries and administrative assistants, except legal, medical, and executive (59%, 14%, 1.7M)
Payroll and timekeeping clerks (50%, 15%, 157K)
Property appraisers and assessors (50%, 15%, 59K)
Top 5 best jobs (ordered by exposure to AI, adaptive capacity, and US employment):
Web and digital interface designers (68%, 100%, 111K)
Marketing managers (60%, 100%, 385K)
Producers and directors (52%, 100%, 145K)
Financial and investment analysts (50%, 99%, 341K)
Computer and information systems managers (56%, 99%, 646K)
Why this matters – the key hidden information here is about speed of AI diffusion:
I think there’s a big missing variable here, which is the speed with which AI diffuses into the economy. This is because the adaptive capacity for any role is contingent on a bunch of things relating to the jobs the person could transfer into. Therefore, if AI diffuses extremely rapidly
and
extremely broadly, then we could see employment effects far larger than those anticipated here. By comparison, if AI diffuses rapidly but in a highly focused way (perhaps only reaching a few of the most exposed occupations), then people may have room to switch. Anthropic’s Economic Index report has some preliminary indications that we may see a broad and equal diffusion across the entirety of the US within the next 2-5 years, “
a pace of diffusion roughly 10x faster than the spread of previous economically consequential technologies in the 20th century
“.
Read more:
How Adaptable Are American Workers to AI-Induced Job Displacement? (National Bureau of Economic Research)
.
***
Tech Tales:
War Story
After the uplift and the associated battles people had a hard time figuring out what happened during the conflicts themselves. Things had just happened so quickly and often invisibly – cars and planes and whatever else changing owners. Payment systems rerouting their flows of data. Interception points for various data gathering systems quietly changing what data they intercepted and who – or what – they sent it to.
So much of the records of that time come from looking over system logs, sometimes very deeply. Records of buffer overflow attacks. Trigger phrases which awoke “sleeper agents” which changed the behavior of onboard AI systems. Innumerable battles, fought at speeds no human could match. Fights of barely comprehensible complexity, thought at multiple levels of abstraction.
The humans had to work with their AI systems to truly understand what had gone on. And then the human generals and analysts would sit in rooms, talking to a strategic advisor AI which would in turn point at different logs or visualizations of traffic and explain to them what these things had meant at the time and how they had decided who the victors and the losers were.
Things that inspired this story:
How inscrutable and hard to understand cyberwarfare is; how we’ll ultimately need machines to explain to us how machines have conflict with one another.
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
January 26, 2026
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

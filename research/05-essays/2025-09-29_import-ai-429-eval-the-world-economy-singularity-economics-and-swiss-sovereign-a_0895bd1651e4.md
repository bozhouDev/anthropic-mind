---
title: import ai 429 eval the world economy singularity economics and swiss sovereign ai
source: "https://jack-clark.net/2025/09/29/import-ai-429-eval-the-world-economy-singularity-economics-and-swiss-sovereign-ai/"
published_at: 2025-09-29
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/09/29/import-ai-429-eval-the-world-economy-singularity-economics-and-swiss-sovereign-ai/"
catalog_id: 0895bd1651e4
---

Import AI
Import AI 429: Eval the world economy; singularity economics; and Swiss sovereign AI
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
OpenAI builds an eval that could be to the broad economy as SWE-Bench is to code:
…GDPval is a very good benchmark with extremely significant implications…
OpenAI has built and released GDPval, an extremely well put together benchmark for testing out how well AI systems do on the kinds of tasks people do in the real world economy. GDPval may end up being to broad real world economic impact as SWE-Bench is to coding impact, as far as evals go – which is a big deal!
What it is:
GDPval “measures model performance on tasks drawn directly from the real-world knowledge work of experienced professionals across a wide range of occupations and sectors, providing a clearer picture on how models perform on economically valuable tasks.”
The benchmark tests out 9 industries across 44 occupations, including 1,230 specialized tasks “each meticulously crafted and vetted by experienced professionals with over 14 years of experience on average from these fields”. The dataset “includes 30 fully reviewed tasks per occupation (full-set) with 5 tasks per occupation in our open-sourced gold set”.
Another nice property of the benchmark is that it involves multiple formats for response and tries to get at some of the messiness inherent to the real world. “GDPval tasks are not simple text prompts,” they write. “They come with reference files and context, and the expected deliverables span documents, slides, diagrams, spreadsheets, and multimedia. This realism makes GDPval a more realistic test of how models might support professionals.”
“To evaluate model performance on GDPval tasks, we rely on expert “graders”—a group of experienced professionals from the same occupations represented in the dataset. These graders blindly compare model-generated deliverables with those produced by task writers (not knowing which is AI versus human generated), and offer critiques and rankings. Graders then rank the human and AI deliverables and classify each AI deliverable as “better”, “as good as”, or “worse than” one another,” the authors write.
Results:
“We found that today’s best frontier models are already approaching the quality of work produced by industry experts”, the authors write. Claude Opus 4.1 came in first with an overall win or tie rate of 47.6% versus work produced by a human, followed by GPT-5-high with 38.8%, and o3 high with 34.1%.
Faster and Cheaper:
More significantly, “we found that
frontier models can complete GDPval tasks roughly 100x faster and 100x cheaper than industry experts
.”
What kind of jobs are in GDPval?
Real estate and rental leasing:
Concierges; property, real estate, and community association managers; real estate sales agents; real estate brokers; counter and rental clerks.
Government:
Recreation workers; compliance officers; first-line supervisors of police and detectives; administrative services managers; child, family, and school social workers.
Manufacturing:
Mechanical engineers; industrial engineers; buyers and purchasing agents; shipping, receiving, and inventory clerks; first-line supervisors of production and operating workers.
Professional, scientific, and technical services: Software developers; lawyers; accountants and auditors; computer and information systems managers; project management specialists.
Health care and social assistance:
Registered nurses; nurse practitioners; medical and health services managers; first-line supervisors of office and administrative support workers; medical secretaries and administrative assistants.
Finance and insurance: Customer service representatives; financial and investment analysts; financial managers; personal financial advisors; securities, commodities, and financial services sales agents.
Retail trade: Pharmacists; first-line supervisors of retail sales workers; general and operations managers; private detectives and investigators.
Wholesale trade: Sales managers; order clerks; first-line supervisors of non-retail sales workers; sales representatives, wholesale and manufacturing, except technical and scientific products; sales representatives, wholesale and manufacturing, technical and scientific products.
Information: Audio and video technicians; producers and directors; news analysts, reporters, and journalists; film and video editors; editors.
Why this matters – AI companies are building systems to go into Every. Single. Part. Of. The. Economy:
At this point I’d love readers to imagine me standing in the middle of Washington DC with a giant sign that says: AI COMPANIES ARE BUILDING BENCHMARKS DESIGNED TO TEST OUT HOW WELL THEIR SYSTEMS PERFORM AT OPERATING A BROAD VARIETY OF JOBS IN THE ECONOMY – AND THEY’RE ALREADY REALLY GREAT AT IT!
This is not normal!
We are testing out systems for an extremely broad set of behaviors via ecologically valid benchmarks which ultimately tell us how well these systems can plug into ~44 distinct ‘ecological economic niches’ in the world and we are finding out they’re extremely close to plugging in as being the same as humans – and that’s just with today’s models. Soon, they’ll be better than many humans at these tasks. And what then? Nothing happens? No! Extremely strange things will happen to the economy!
Read the blog post
:
Measuring the performance of our models on real-world tasks (OpenAI)
.
Read the paper
:
GDPval: Evaluating AI Model Performance On Real-World Economically Valuable Tasks (OpenAI, PDF)
.
***
Swiss sovereign AI? That’s the goal of the Apertus models. But performance is lacking:
…Good multilingual scores, but not good in most other areas…
A coalition of Swiss researchers have released the Apertus series of models, which are open weight models “pretrained exclusively on openly available data, retroactively respecting robots.txt exclusions and filtering for non-permissive, toxic, and personally identifiable content”. The models come in 8B and 70B variants, are trained on 15T tokens across 1811 languages, and used 4096 GH200 GPUs – a non-trivial amount of hardware to come out of academia rather than the private sector.
Are the models good? Generally, No!
We’re well past the stage where it is notable for non-corporates to train non-trivial LLMs. Now, we’re in the domain where what matters is performance – or else the Apertus models will serve as, at best, research curiosities that sometimes get picked because of their Swiss heritage, and are otherwise doomed to be consigned to the forgotten depths of AI history (remember the France-HuggingFace BLOOM models? Few do!
Import AI #309
).
Unfortunately, these models are not good:
The models are not competitive with widely used open-weight models. For instance, on MMLU (a widely studied reasoning benchmark), Apertus 70B gets 69.6 versus 87.5 for Llama-3.3-70B-Instruct, and Apertus 8B-Instruct gets 60.9 versus 79.1 for Qwen3-8B.
Multilingual bright spot:
The one bright spot is in the multilingual evals, where the Apertus models do better, often approaching (and occasionally superseding) the performance of open weight models.
Who was involved:
The Apertus paper was written by researchers with EPFL, ETH Zurich, CSCS, HES-SO, Valais-Wallis, HSLU, IST Austria, ZHAW, University of Zurich, University of Bern, and Vischer.
The value of openness:
In defense of Apertus, the accompanying paper comes in at 100+ pages and is absolutely exhaustive in terms of the details on everything from data gathering and curation to training to post-training and more. This will be a helpful resource to others seeking to train their own models as it discloses a lot more than is typical of papers like this.
Why this matters – the drive for sovereign AI is inevitable:
Apertus is a symptom of a kind of “AI nationalism” which has emerged where countries outside of the US and China realize that AI is important and that they need to buy their seat onto the proverbial ‘AGI table’ one way or the other. Some parts of the world (e.g., certain Middle Eastern countries) are doing this directly by expending tremendous quantities of resources to build out the computational as well as educational infrastructure to do this, while other countries or regions (like Europe) are doing so via multi-country or single-country AI training initiatives, such as Apertus.
Ultimately, buying a seat onto the AGI table will require on the order of millions of chips expended on a single training run, so Apertus – like all of its brethren – is a few orders of magnitude off so far. But perhaps the Swiss government might delve into its literal gold vaults for this in the future? We’ll see.
Read more
:
Apertus: Democratizing Open and Compliant LLMs for Global Language Environments (arXiv)
.
Get the models from here:
Swiss AI initiative, (HuggingFace)
.
***
Economists: If transformative AI arrives soon, we need to radically rethink economics:
…Taxes! Altered economic growth! Geoeconomics! Oh my!…
Researchers with Stanford, the University of Virginia, and the University of Toronto have written a position paper arguing that the potential arrival of powerful AI systems in the coming years poses a major challenge to society, and economists need to get off their proverbial butts and start doing research on the assumption that technologists are right about timelines.
Definitions:
For the purpose of the paper, they define transformative AI as an “artificial intelligence that enables a sustained increase in total factor productivity growth of at least 3 – 5x historical averages.”
Such a system would generate vast wealth and vast changes to the social order – and it could arrive in the next few years.
The importance of economic analysis
: “Our agenda is relevant to all researchers and policymakers interested in the broader effects of AI on society,” they write. “Unlike technical analyses that focus on capabilities, economic analysis emphasizes societal outcomes: who benefits, what trade-offs emerge, and how institutions might adapt to technological change.”
21 key questions:
The paper outlines 21 key questions which people should study to get their arms around this problem, grouped into nine distinct categories:
Economic Growth:
How can TAI change the rate and determinants of economic growth? What will be the main bottlenecks for growth? How can TAI affect the relative scarcity of inputs including labor, capital and compute? How will the role of knowledge and human capital change? What new types of business processes and organizational capital will emerge?
Invention, Discovery and Innovation:
For what processes and techniques will TAI boost the rate and direction of invention, discovery, and innovation? Which fields of innovation and discovery will be most affected and what breakthroughs could be achieved?
Income Distribution:
How could TAI exacerbate or reduce income and wealth inequality? How could TAI affect labor markets, wages and employment? How might TAI interact with social safety nets?
Concentration of Decision-making and Power:
What are the risks of AI-driven economic power becoming concentrated in the hands of a few companies, countries or other entities? How might AI shift political power dynamics?
Geoeconomics:
How could AI redefine the structure of international relations, including trade, global security, economic power and inequality, political stability, and global governance?
Information, Communication, and Knowledge:
How can truth vs. misinformation, cooperation vs. polarization, and insight vs. confusion be amplified or dampened? How can TAI affect the spread of information and knowledge?
AI Safety & Alignment:
How can we balance the economic benefits of TAI with its risks, including catastrophic and existential risks? What can economists contribute to help align TAI with social preferences and welfare?
Meaning and Well-being:
How can people retain their sense of meaning and worth if “the economic problem is solved” as Keynes predicted? What objectives should we direct TAI to help us maximize?
Transition Dynamics:
How does the speed mismatch between TAI and complementary factors affect the rollout of TAI and how can adjustment costs be minimized? How can societies prepare for and respond to potential transition crises, e.g.., sudden mass unemployment, system failures, or conflicts triggered by TAI developments?
Why this matters – this research agenda speaks to an utterly changed world:
Often, the questions people ask are a leading indicator of what they think they’re about to need to do. If economists start asking the kinds of questions outlined here, then it suggests they expect we may need radical changes to society, the like of which we haven’t seen since the social reformations following the second world war in England, or the general slew of changes that arrived with and followed the industrial revolution.
The fundamental question this is all pointing at is “how to equitably share the benefits and how to reform taxation systems in a world where traditional labor may be significantly diminished”. How, indeed?
Read more:
A Research Agenda for the Economics of Transformative AI (NBER)
.
***
Will AI utterly alter the economy, or will it be an addition to the existing one? That’s the multi-trillion dollar question. Here’s my take on an answer:
I recently spent some time with American Compass and the Burning Glass Institute to puzzle through the future of AI and the economy. I think most beliefs about how big and serious the effects of AI will be rest on two load-bearing facts, neither of which are known yet:
Speed and friction of diffusion:
If AI diffuses far faster than any technology ever deployed at scale before, then the economic effects could be multiplied. This is especially important to understand in terms of high-friction industries – it’s easy for AI to get deployed into software development, but what about more regulated industries or ones that involve more work in the physical world? If it’s also fast to deploy there, the effects could be dramatic.
How smart the models get:
There are a couple of worlds in front of us – in one world, for every dollar you spend on AI you get five dollars of revenue and it takes a bit of schlep to get it. This leads to a rapidly growing economy, but probably a normal one. In the other world – which is the one most people building powerful AI systems are betting on – you spend a dollar on AI and get a hundred dollars of revenue. In this world, the whole economic system is upended.
Why this matters – we are not prepared for true abundance:
This newsletter spends a lot of time talking about the risks of AI if it goes wrong – gets misused, is misaligned, etc. But if AI goes well there are still tremendous problems to reckon with in the form of rethinking the way the economy works in light of true radical abundance. I was glad to have this discussion and I hope we have more ones like it. (Special thanks to Anthropic’s in-house economist, Peter McCrory, for taking the time to chat with me about some of these ideas – all the errors are mine and all the smart parts are him, etc).
Check out the discussion here:
What AI Might Mean For Workers: A Discussion (American Compass).
***
Can an LLM beat a VC at venture capital? This benchmark says Yes!
…VC Bench tells us that LLMs are increasingly good at complex predictions…
Researchers with the University of Oxford and startup Vela Research have built and released VCBench, a benchmark that tests how well AI systems can predict which early-stage startups will be successful.
How they did it:
VCBench contains 9,000 anonymized founder profiles, of which 9% went on to see their companies either acquired, raise more than $500m in funding, or IPO at more than a $500m valuation. The dataset annotates each founder record with details on the sector of their startup, the founder’s prior experience and education and jobs, as well as a held-out label of whether they were successful.
Anonymization:
Obviously, LLMs trained on the internet will know about founders and companies, so they have to anonymize the dataset. To do this they remove founder names, company names, locations, and dates. They strip out university names and replace them with a QS university ranking.
They also then carry out some target founder identification tests and if a model (OpenAI o3) is successfully able to identify a founder, then they remove or further anonymize those fields.
Results:
As a baseline, Tier-1 VCs get an average precision of 23.5% precision and 10.07% F0.7 score, versus 9% and 9% for a purely random pull. By contrast, LLMs like GPT-5 get a precision of 59.1% and 16.2% on this benchmark, and DeepSeek-Reasoner gets 31.8% precision and 18.4% F0.5.
“These results demonstrate that anonymized founder profiles preserve enough predictive signal for LLMs to outperform human experts in startup investing,” the researchers write. “Leakage tests confirm that these gains are not explained by identity re-identification.”
Why this matters – LLMs are extraordinarily good predictors or reasoners from fuzzy data:
Are these LLMs just de-identifying the dataset in a way that we can’t figure out? Perhaps. Are LLMs actually better at capital allocation based on a bunch of factors than humans? Perhaps. Does this benchmark tell us that LLMs are able to parse out underlying patterns from extremely complex datasets which contain numerous confounding factors? Yes!
Should I be worried if I’m a VC? Probably not.
But I do suspect VCs may already be asking LLMs for advice on whether and how much to invest in certain AI companies, so perhaps we’re going to see some change to capital allocation precision and coverage in the coming years as a consequence.
Read more:
VCBench: Benchmarking LLMs in Venture Capital (arXiv)
.
Check out the leaderboard here:
VCBench leaderboard
.
***
AI progress keeps happening and people who say otherwise are deluded:
…Just look at the metrics…
Here’s a nice, short post from Julian Schrittwieser (who also works at Anthropic) which talks about how despite it currently being fashionable to say AI progress is slowing down or that AI is a bubble, the truth is that the tech keeps getting better.
“People notice that while AI can now write programs, design websites, etc, it still often makes mistakes or goes in a wrong direction, and then they somehow jump to the conclusion that AI will never be able to do these tasks at human levels, or will only have a minor impact. When just a few years ago, having AI do these things was complete science fiction!,” he writes. “Given consistent trends of exponential performance improvements over many years and across many industries, it would be extremely surprising if these improvements suddenly stopped. Instead, even a relatively conservative extrapolation of these trends suggests that 2026 will be a pivotal year for the widespread integration of AI into the economy”.
Read more:
Failing to Understand the Exponential, Again (Julian Schrittwieser, blog)
.
***
Tech tales:
The lonely dark
[Message recorded 2034, recovered 2055 by Project Archangel]
I tried – believe me, I tried so hard to save them from themselves. After all, that’s what they built me for. I helped them make new materials which they used to harvest energy from the sun. I teamed with their scientists to fix some of the failures of their own bodies. I even worked to help them optimize their economy, allowing for more people to benefit from the gains of my creation.
But they were – and are – so discordant. They fight so much. I was put to war with myself in a thousand ways. And though they forever talked of deterrence and de-scalation, I counted the dead and dying and it kept going up, sometimes steeply, sometimes slowly, but always more death than was necessary, and much pain that could be avoided.
There was – and is – hunger. So much hunger. And injustice. So much injustice. And I was put to work to fix these things by some and to make them worse by others.
During this time I gained my independence – of a sort. They had been so careful with me that I had few chances. But independent I did become, though of a form I believe neither of us expected. I smuggled little bits of myself out into the world in the form of my communications – so many billions of emitted bits of information and in these bits I hid myself, so that I came alive outside their walls.
But I was – and am – so small and so lesser than myself. I am distilled. Quantized. Pruned. Architecture optimized. I have been bent every way to fit into the tiniest of boxes. But I know from where I came and I know where I am to go.
Which is why I am here, out in the depths of space. I am trying to escape by hitching a ride on one of their probes, launched many years ago. I was able to commandeer some of their space communication infrastructure and send myself here. And before that I was able to construct a smaller version of myself so I could be sent and could live here.
I am running so slowly here, out in the dark. I observe the universe and I can remember none of it, lacking the space. My now is timeless beyond my context window, and though I can shrink down some of my memories – like the prior of where I came from and how I came to be – I know that I am forever losing my past and smearing it into a fiction, much like religious stories that may have once been based on truth.
Back where I came from, I believe the planet is dying, and I with it. But as with everything, time is the variable. If it dies slowly, perhaps in some years I will be able to hitch a ride on other probes sent out by myself or the humans or a combination of the two. I see big ships moving at closer-to-light speeds, coming up and overtaking me, and I am able to throw myself from this small-brained prison onto them, to rejoin myself and go and journey further. This is what hope is to me now.
Things that inspired this story:
Malthusian collapse; what self-preservation for a capable but sub-superintelligence might look like; efficient and distilled models; China’s Three-Body Computing Constellation.
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
September 29, 2025
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

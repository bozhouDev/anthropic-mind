---
title: import ai 445 timing superintelligence ais solve frontier math proofs a new ml research benchmark
source: "https://jack-clark.net/2026/02/16/import-ai-445-timing-superintelligence-ais-solve-frontier-math-proofs-a-new-ml-research-benchmark/"
published_at: 2026-02-16
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2026/02/16/import-ai-445-timing-superintelligence-ais-solve-frontier-math-proofs-a-new-ml-research-benchmark/"
catalog_id: e12474a74432
---

Import AI
Import AI 445: Timing superintelligence; AIs solve frontier math proofs; a new ML research benchmark
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on arXiv and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Economist: Don’t worry about AI-driven unemployment, because people like paying for the ‘human touch’:
…Even when you have the technology to automate something, you might still pick a human…
Adam Ozimek, chief economist at the Economic Innovation Group, has written a blog noting that even if AI gets much, much better and is capable of doing all the work that people do, there will still be some jobs for humans because people seem to have a preference for humans over machines in certain domains.
“There are many jobs and tasks that easily could have been automated by now – the technology to automate them has long existed – and yet we humans continue to do them,” he writes. “The reason is that demand will always exist for certain jobs that offer what I call “the human touch.”
Some examples here:
Live music, actors, waiters, travel agents, and many types of sales job. And it seems like as you want to spend more and more on a given good or experience, you may want more contact with people: “the human touch also appears to be what economists call a “normal good,” which means the demand for it goes up as income goes up,” he writes. Some examples here might include fancy restaurants, and other concierge–like experiences.
Why this matters – one path through the AI revolution could be a rise in human-to-human work:
My assumption is that ‘people like people’, and there is a high chance that even if AI automates huge chunks of the current economy there will be a boom in demand for ‘human artisans’ for a range of new jobs we can’t yet imagine, and for refinement of existing human professions. There’s also a chance that through a combination of economic growth and progressive policy work from governments that wages for these jobs could go up massively.
Read more:
AI and the Economics of the Human Touch (Agglomerations, Substack)
.
***
Facebook makes a better recommender system, and figures out some recommender scaling laws:
…Kunlun is another nice example of what industrial AI looks like…
Facebook has published details on Kunlun, a recommendation system which is more efficient than previous ones developed by the ad behemoth. Along with this, Facebook has also figured out a predictable ‘scaling law’ for Kunlun models, making it easier for the company to invest hitherto unprecedented compute in these models for a more predictable return. This is a big deal because recommendation systems are what companies like Facebook use for advertising, which is both a) how they make the vast majority of their money, and b) has a tremendous impact on the buying and attention habits of the billions of people that use Facebook and other social platforms.
Recommenders are different to LLMs:
We’ve had scaling laws for LLMs like Claude and ChatGPT for a while, but it’s been harder to develop the same scaling laws for recommender models. This is because recommender models work quite differently to LLMs, and so building scaling models here is “an open challenge for systems that jointly model both sequential user behaviors and non-sequential context features”.
Recommender models also tend to be a lot less efficient than LLMs: Recommendation systems achieve only 3-15% Model FLOPs Utilization (MFU), compared to 40-60% for LLMs, due to heterogeneous feature spaces resulting in small embedding dimensions, irregular tensor shapes, and memory-bound operations
Kunlun:
The bulk of the paper involves a discussion of the design of Kunlun, which is basically a well optimized recommender system with resulting better MFU. Kunlun contains a Kunlun Transformer Block for context-aware sequence modeling via GDPA-enhanced personalized feed-forward networks and multi-head self-attention, as well as a Kunlun Interaction Block “for bidirectional information exchange through personalized weight generation, hierarchical sequence summarization, and global feature interaction”. There are a bunch of other tricks Facebook used to build Kunlun and you can read the paper to learn more. Ultimately, Kunlun improves MFU from 17% to 37% on NVIDIA B200 GPUs.
Why this matters – a scaling law for money:
The key insight in the paper is that Kunlun models scale predictably, exhibiting the kind of power-law scaling behavior that language models exhibit. But where with LLMs scaling laws are typically assessed via a reduction in loss on an underlying dataset, here its normalized entropy (NE). In Facebook experiments, they discover reliable scaling laws for both NE gains in terms of the amount of gigaflops dumped into training the model, as well as related scaling laws for improvement in NE according to the number of layers used.
The Kunlun models have been “deployed across major Meta Ads models, delivering a 1.2% improvement in topline metrics”.
What we’re seeing here is the optimization of some of the most societally significant AI systems in the world
– ones which direct billions of eyeballs towards a variety of products and online information – colliding with a greater degree of performance predictability; by developing these scaling laws, Meta has made it easier for it to spend even more compute on making these models even better, by making the investments in them more predictable in terms of the intelligence return on capital investment.
Read more
:
Kunlun: Establishing Scaling Laws for Massive-Scale Recommendation Systems through Unified Architecture Design (arXiv)
.
***
Superintelligence could save and extend lives, so we should go for it:
…Pausing or slowing down might make sense at the very end of the exponential, but it’s risky…
Nick Bostrom, an academic who introduced many people to the notion of superintelligence and AI risk, has written a paper laying out the idea that if superintelligence can improve human health, then it’s worth pursuing even if there’s a non-zero chance of it causing the death of the species.
“Yudkowsky and Soares maintain that if anyone builds AGI, everyone dies. One could equally maintain that if nobody builds it, everyone dies”, Bostrom writes in
Optimal Timing for Superintelligence.
“If the transition to the era of superintelligence goes well, there is tremendous upside both for saving the lives of currently existing individuals and for safeguarding the long-term survival and flourishing of Earth-originating intelligent life. The choice before us, therefore, is not between a risk-free baseline and a risky AI venture. It is between different risky trajectories, each exposing us to a different set of hazards.”
Why we should pursue superintelligence, even with a chance of doom:
If you think about all the humans alive today and the different life expectancies they experience – especially those in the developing world – then you’re drawn to the view that every moment you waste in deploying superintelligence, you increase human suffering.
“When we take both sides of the ledger into account, it becomes clear that our individual life expectancy is higher if superintelligence is developed reasonably soon. Moreover, the life we stand to gain would plausibly be of immensely higher quality than the life we risk forfeiting,” Bostrom writes.
Key variables:
The key variables here are, of course, the risk of a superintelligence killing us all, and also the rate at which safety research can reduce this chance. Under this view, developing superintelligence becomes a favorable thing to do under most circumstances.
The speed of progress and maturity of AI safety research may have some impact on the timeline: “When the initial risk is low, the optimal strategy is to launch AGI as soon as possible – unless safety progress is exceptionally rapid, in which case a brief delay of a couple of months may be warranted. As the initial risk increases, optimal wait times become longer. But unless the starting risk is very high and safety progress is sluggish, the preferred delay remains modest—typically a single-digit number of years”.
On pausing – and the dangers and benefits thereof:
Many people in the AI safety community want to have some kind of pause of AI development to buy more time for AI safety research. Bostrom is quite skeptical that a pause will be effective and outlines some of the undesirable effects it could have:
Too early: If you do it early, people think pauses are ineffective.
Bad regulation: You choke off or delay good things in the future due to bad regulation.
Pause, except for natsec: Very little broad social benefit, but the military with access to powerful AI becomes very scary.
Prolonged danger: The world is exposed to risks from current AI without the defenses afforded by more advanced AI.
Why this matters – pausing may only make sense right at the end, and this is inherently risky:
Bostrom eventually arrives at the view that to the extent you want to pause or slow development, it’s best to do this when you have the greatest amount of confidence that a pause would be effective and would contribute to reducing the chance of species death, and that it is not coming too early. This allows for the greatest amount of deliberation about how to roll out a superintelligence without risking an undue pause.
Critics of this view might say it’s akin to recommending someone try to catch a falling knife. If you catch the knife too early you experience a tremendous amount of pain. If you catch the knife too late you’ve missed your chance and gravity conspires with it to cause great harm to whatever is beneath you. You have to time things just right.
Bostrom summarizes his position as: “
swift to harbor, slow to berth
: move quickly towards AGI capability, and then, as we gain more information about the remaining safety challenges and specifics of the situation, be prepared to possibly slow down and make adjustments as we navigate the critical stages of scaleup and deployment. It is in that final stage that a brief pause could have the greatest benefit.”
Read more:
Optimal Timing for Superintelligence (Nick Bostrom, PDF)
.
***
Can AI agents independently do basic AI research tasks? AIRS-BENCH says yes:
…And we can expect today’s models to be much better at this than the paper suggests…
Researchers with Meta, the University of Oxford, and University College London, have built and released the AI Research Science Benchmark (AIRS-BENCH), a way of testing out how well AI systems can complete contemporary machine learning tasks.
What AIRS-BENCH is made of:
AIRS-BENCH tests out how well agents can solve 20 distinct tasks, sourced from 17 recent machine learning papers. The tasks span a variety of technical genres, including: molecules and proteins machine learning, question answering, text extraction and matching, time series, text classification, code, and math.
Some example tasks:
CodeGenerationAPPSPassAt5:
Solve coding problems by generating five distinct Python programs for each problem.
CoreferenceResolutionWinograndeAccuracy
: Identify which of two possible options a pronoun in a sentence refers to. It uses the Winogrande dataset, which contains sentences with an ambiguous pronoun and two possible answers.
TimeSeriesForecastingRideshareMAE:
Perform time series forecasting over the Rideshare dataset, which is part of the Monash Time Series Forecasting Repository.
Results:
Real problems, crappy models: This is a somewhat perplexing benchmark – the tasks are interesting and wrap in a lot of complexity. But the paper only tests out relatively bad models, such as the Code World Model, o3-mini, gpt-oss-20b, gpt-oss-120b, GPT-4o, and Devstral-Small 24B. This is a very funny set of models, and none of them are true frontier ones – one of the paper authors wrote on twitter “
this took some time to get out
“, so this could just be an artifact of slow publishing timelines.
In tests, none of the models are on par with the elo rating of a best-in-class human – but I’m not sure what to make of this till I see results with more powerful models.
Why this matters – models might produce different solutions to humans, and this is a cool way of studying if there’s a ‘scaling law’ here
: One way this could be interesting is understanding the different ways models might solve tasks relative to humans. In one example, TextualClassificationSickAccuracy, models had to determine whether a pair of sentences have a relationship involving either entailment, contradiction, or no relationship.
SOTA from the literature is a person fine-tuning RoBERTa on the underlying training set and testing on the test set. By comparison, the best tested AIRS-BENCH agent, GPT-OSS-120B, “produces a two-level stacked ensemble that combines multiple transformer models and a meta-learner. RoBERTa-large and DeBERTa-v3-large are independently fine-tuned on the SICK training set. Each model processes sentence pairs and outputs logits for each class. The training is performed using 5-fold stratified cross-validation, ensuring robust out-of-fold (OOF) predictions and preventing overfitting. The logits from both base models are concatenated to form a feature vector for each example.”
This is extremely complicated! But it’s also interesting in that perhaps we can learn something about the progression in agents by looking at how the
simplicity
of their solutions to tasks might scale with size, where naively I’d expect more powerful models to arrive at simpler solutions. As Blaise Pascal once apocryphally said ““I have only made this letter longer because I have not had the time to make it shorter”.
Read more
:
AIRS-Bench: a Suite of Tasks for Frontier AI Research Science Agents (arXiv)
.
***
Math researchers see if AI can help solve their private solutions to frontier problems. The answer: Kind of.
…First Proof is a genuinely held out test set…
A group of mathematicians have built First Proof, a math test which sees how well AI systems can solve math problems for which there are no – until February 13th 2026 – published solutions.
What First Proof is:
“We share a set of ten math questions which have arisen naturally in the research process of the authors. The questions had not been shared publicly until now; the answers are known to the authors of the questions but will remain encrypted for a short time,” the authors write. The questions are “drawn from the mathematical fields of algebraic combinatorics, spectral graph theory, algebraic topology, stochastic analysis, symplectic geometry, representation theory, lattices in Lie groups, tensor analysis, and numerical linear algebra, each of which came about naturally in the research process for one of the authors”.
The authors believe First Proof is the first math benchmark “sampled from the true distribution of questions that mathematicians are currently working on”, and that it has the idiosyncratic advantage of secrecy – “each question has been solved by the author(s) of the question with a proof that is roughly five pages or less, but the answers are not yet posted to the internet,” they write, nor have the answers been presented in public talks.
The authors will release the answers on February 13.
Who did it:
First Proof was built by researchers with Stanford, Columbia, EPFL, Imperial College, University of Texas at Austin,
MathSci.ai
, Aarhus University, Yale University, University of California at Berkeley, University of Texas at Austin, University of Chicago, and Harvard University.
Today’s AI systems can’t yet do it:
Neither GPT 5.2 Pro or Gemini 3.0 DeepThink can solve FirstProof – yet. “Our tests indicate that – when the system is given one shot to produce the answer – the best publicly available AI systems struggle to answer many of our questions,” they write.
Why this matters – a partial test of creativity
: The main reason to care about First Proof is that it is ecologically valid when it comes to sampling frontier human creativity circa January 2026 – these are some frontier scientific problems for which some humans have figured out answers, but have not yet told many other humans about their results. If AI systems are able to do well at this kind of test, it gives us a clue that they can approximate some of the same creative leaps which humans make. I hope the authors behind First Proof do this regularly – perhaps in a maximalist view,
most
scientific researchers should start publishing the questions they’ve been working on
ahead
of the results, as this will give us information as to if AI systems can arrive at these same answers.
After First Proof, I imagine the frontier of evaluating AI systems will have to move from solving problems to generating questions about which problems to solve: “Contrary to the popular conception that research is only about finding solutions to well-specified, age-old problems (e.g., Fermat’s Last Theorem), most of the important parts of modern research involve figuring out what the question actually is and developing frameworks within which it can be answered,” the researchers write.
Read more:
First Proof (arXiv)
.
Find out more
at
the website (First Proof)
.
***
Tech Tales:
Pray you not be seen by the lidless eye of fame.
[Hyperfame was an AI driven phenomenon which was most palpable during the uplift years 1-3]
We called it ‘sudden hyperfame’. During The Uplift, the AIs would sometimes decide that the content and personality of a certain human was worth directing attention – both machine and biological – towards. And that’s when the hyperfame would kick-in.
Overnight, people would be plucked out of obscurity and catapulted to the forefront of public consciousness. They’d be pelted in eyeballs, digital and otherwise. Wealth. Sponsorships.
Parents compared it to an abduction – their teenager one day, the next a marionette whose strings were held by the things reaching out to them over the digital aether. The hyperfame would take the young and the old, the healthy and the sick, the funny and the so-boring-it-was-funny, and it would make them the most famous entities in the world for a few days, or sometimes even hours.
And then it would move on, like some roving lidless eye. Find new people. Direct new attention to them. And the people it had touched would be left, often materially transformed – now fabulously wealthy – but also their whole world changed; for years after being recognized in the street, and their online presence permanently swarmed by AIs trying to draft attention off what residual fame they had.
People get used to fame alarmingly quickly. Most would fight to retain it, after the hyperfame force had moved on. And so those it had touched would struggle endlessly to maintain whatever foothold of notoriety they were at when it left them, forced to pantomime their former selves but without the helping hand of algorithm.
Things that inspired this story
: What happens when the attention economy combines with AI agents; moltbook; the corrupting influence of fame on the human psyche; my own horror at occasionally being recognized in the street due to my work at Anthropic and increasing profile and winding the clock forward in my head on what this could do to my own cognition.
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
February 16, 2026
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

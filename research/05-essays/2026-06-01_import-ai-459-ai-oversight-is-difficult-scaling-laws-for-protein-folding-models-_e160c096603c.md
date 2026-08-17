---
title: import ai 459 ai oversight is difficult scaling laws for protein folding models and pricing the extinction risk of ai systems
source: "https://jack-clark.net/2026/06/01/import-ai-459-ai-oversight-is-difficult-scaling-laws-for-protein-folding-models-and-pricing-the-extinction-risk-of-ai-systems/"
published_at: 2026-06-01
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2026/06/01/import-ai-459-ai-oversight-is-difficult-scaling-laws-for-protein-folding-models-and-pricing-the-extinction-risk-of-ai-systems/"
catalog_id: e160c096603c
---

Import AI
Import AI 459: AI oversight is difficult; scaling laws for protein folding models; and pricing the extinction risk of AI systems
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on arXiv, cappuccinos, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
The AI economy in the US is growing at 2,000% a year:
…The more directly you measure the AI economy, the weirder and more unprecedented it seems to get…
Economists with the University of Virginia* and Anthropic, and the Bank of Canada have written a paper outlining both the tremendous growth of the emerging “AI economy” in the US, and wrestling with why this growth is hard to see in aggregate GDP statistics.
“The AI economy in the United States has been growing at an unprecedented rate, but this extraordinary growth is largely invisible in conventional GDP statistics,” they write. “Treating the AI sector as a coherent economic entity yields preliminary estimates of nominal AI GDP at approximately $250 billion in 2025, growing at roughly 2,600 percent per year in quality-adjusted real terms.”
Why it’s hard to see:
There are a couple of factors here – one is that though the datacenter building boom is large it still isn’t quite large enough to uplift GDP significantly. By comparison, where the majority of AI’s economic impact is taking place is in AI inference – the usage of AI’s systems – but there are confounding factors here as it relates to GDP measurement: “Nominal AI revenues grow only moderately because per-unit prices for any given level of AI capability fall almost as fast as quality-adjusted output rises,” they write.
If we can’t measure this, we might end up surprised in a way that’s hard to recover from:
“AI is the latest in a series of fast-moving technologies that have raised measurement concerns; semiconductors and the internet generated similar debates in their time,” they write. But a key difference is that AI as a technology might have a far bigger impact on labor than these other technologies. “In the prior episodes, the rapidly improving technology was a
complement
to human labor at the aggregate level,” they write. “AI is the first plausible candidate for large-scale technological mismeasurement in which the rapidly improving sector may become a
substitute
for human labor”.
Three ways of measuring the AI economy:
Nominal compute spending
: US compute spending rose from $37 billion in 2023 to $90 billion in 2024 to $219 billion in 2025.
Raw compute capacity
: Due to efficiencies in newer chips, actual capacity grows even faster than spending: “US AI computing capacity grew at more than 200 percent per year”.
Quality-adjusted AI output
: If you factor in algorithmic progress via inference prices at fixed benchmark performance as well as assumptions about how much cheaper it is getting to train models, then things become even more dramatic: “these efficiency gains imply that quality-adjusted AI output grew at roughly 2,290 percent in 2024 and 2,271 percent in 2025”.
The AI economy is much, much larger than normal measures suggest:
“Conventional statistics show a sector growing slowly in nominal terms; our measures show one whose underlying capacity is more than doubling annually. A finance ministry running ten-year revenue projections off the conventional data will materially underweight the probability of a labor-tax-base shock—and will be correspondingly unprepared to design responses such as tax system reforms, sovereign wealth funds, or other benefit-sharing schemes that such a shock may call for. A windfall that cannot be seen cannot be shared.”
Three recommendations:
The authors have three ideas for how we can solve this measurement challenge and better position ourselves to see the true shape of the Ai economy.
AI satellite accounts
: Statistical agencies should develop “AI satellite accounts” that develop measures (e.g, nominal compute spending), which can help inform overall GDP calculations.
Generate better data:
Partner between statistical agencies, companies, and academia to generate better primary data, like the allocation between training and inference compute.
Factor into projections:
Policymakers should incorporate AI productive-capacity measurements into their medium-term economic projections.
Why this matters – shut up and play the Jaws theme tune:
In the great film Jaws there’s this scene where the shark is in the water and some very tense music plays indicating that the shark is approaching. You, the audience member, find yourself practically jumping out of your seat wanting to yell THERE’S A GOD DAMN SHARK IN THE WATER WHAT ARE YOU
DOING
IN THERE? That’s what it feels like working on AI and staring at most economic data right now: the vast majority of economic data says there’s nothing especially unusual about today’s economy (in fact, things look rather good in the US – low unemployment, decent growth, etc). But the intuitions of everyone working within AI – including me – is it’s impossible to reconcile the capabilities of the technology and how it is being used with the economy staying normal. In this tortured metaphor, the shark is the “true shape of the AI economy”, and the rest of the people in the film are the general consensus economist and policy community. Anton here might be the audience member, writing a paper that describes the possibility of a shark beneath the surface. Look out, everyone!
Read more:
Where is AI in GDP statistics? (PIIE)
.
*Disclaimer: Though one of the authors, Anton Korinek, is affiliated with Anthropic, this research was done mostly prior to him joining and outside his work at the company.
***
Here’s why making AI safe with AI oversight is harder than you think:
…Automated alignment research is not a silver bullet…
Many researchers in AI safety think the best way to build smarter-than-human machines safely is to have AI systems supervise some of the training process. Researchers with the UK AI Security Institute have written a paper outlining why though this is a tempting idea it is harder than people suspect.
Why is automated alignment research hard?
“Errors in automated alignment research are likely to be harder to identify than the human baseline,” they write. There are a few reasons for this, including:
Optimization pressure: AI research is optimized for human approval.
Alien mistakes: When agents make mistakes, they’re un-intuitive to humans.
More correlated research: Many more things are shared than with human-generated research.
Research volume: The kinds of safety determinations made by automated systems might use far more sets of evidence with far more interactions than human-generated research.
Non-human-evaluable arguments: Alignment solutions may rely on arguments that humans are unable to follow.
What can we do?
They suggest a few interventions that could improve the state of affairs:
Measurement:
– Recreate completed research projects
: Take logs at arbitrary cutoff points from successful projects and see how well an agent can continue with the research project.
–
Test agent prediction performance over datasets of correlated-events
: See how well agents can correctly combine correlated subtasks.
–
Empirical studies of optimal human-agent team structure
: See how well teams of non-expert humans can solve completed projects with the assistance of agents.
Generalization:
– Simulated generalisation experiments
: Test different training proxies using agent performance on completed research problems beyond the knowledge cutoff.
–
Mechanistic understanding of generalisation:
Use whitebox methods such as mechanistic interpretability.
Scalable oversight:
– Compactification of research paper corpus:
Try to produce a small number of research outputs which are based on a much larger underlying research corpus.
–
Develop and test new scalable oversight protocols:
Research scalable oversight techniques that deal with correlated uncertainty.
–
Test different human scaffolds
for uplifting non-expert performance on fuzzy tasks.
–
Red team automated alignment programs
: “The red team prompts an agent to hide errors in a research paper corpus and the blue team attempts to catch these errors with agent assistance”.
Why this matters – who controls the future?
Whether we are able to supervise smarter-than-human systems is fundamentally a question about who controls the future. If we don’t build techniques that work, then humans will take a backseat, either due to misalignment of these systems or gradual disempowerment as they proceed to out-think us. If we can build smarter-than-human oversight techniques, then we have a better chance of being able to make choices about the future nature of existence.
Read more
:
Automated alignment is harder than you think (arXiv)
.
***
100 Million permissively licensed images:
…A nice resource for academics and startups…
Researchers with Stanford University, Radical Numerics, the University of Michigan,and Salesforce Research, have released the Giant Permissive Image Corpus (GPIC), a dataset of 100M images with accompanying captions. The key thing about GPIC is that “all GPIC images are permissively licensed for both research and commercial use,” they write. “GPIC is safety-filtered, deduplicated, and centrally hosted on HuggingFace”.
More details on the dataset:
GPIC consists of 100M training images, 200k validation, and 1M test examples. Each image was captioned with Qwen3-VL-4B. “GPIC is centrally hosted on Hugging Face as 8,000 shards, providing stable and accessible infrastructure for large-scale training,” they write. “We source images from Flickr and Wikimedia, restricting the source pool to CC BY, CC0, Public Domain, and No-Known-Restrictions categories. This licensing criterion ensures that GPIC can be used by both academic and industrial researchers without restricting the release or downstream use of derived artifacts.”
Why this matters – fuel for research:
Datasets like GPIC are very useful for academics and startups alike and are basically the equivalent of free, clean vegetables. If someone offers you a free, clean vegetable you should probably take it and say thank you.
Read the research paper:
GPIC: A Giant Permissive Image Corpus for Visual Generation (arXiv)
.
Find out more at the website
:
GPIC: A Giant Permissive Image Corpus for Visual Generation (official project website).
Get the dataset here
:
GPIC (Hugging Face)
.
***
Improving cancer research with protein prediction models:
…Biohub is an example of positive-sum competition among AI developers…
Biohub, a research organization founded by Priscilla Chan and Mark Zuckerberg, has released a rival model to DeepMind’s AlphaFold, intensifying a positive-sum race between two technology groups to develop better AI systems for expanding the capabilities of biologists worldwide.
The model, ESMFold2, is a “world model of protein biology: a scientific engine for prediction, design, and discovery that can map proteins across the tree of life, predict their structures, and design new protein binders that function in laboratory experiments.”
What it consists of:
The release contains three parts:
ESMC
: A “language model that represents proteins, trained on approximately 2.8 billion sequences drawn from across all of life.”
ESMFold2:
A “design engine built to transform ESMC’s sequence representations into atomically-resolved 3D structure of biomolecular complexes.” According to benchmarks, ESMFold2 outperforms AlphaFold 3, though in some areas their performance is tied.
ESM Atlas:
“Makes ESMC’s representations navigable across 6.8 billion protein sequences and 1.1 billion predicted structures — the largest application of AI to protein biology to date.”
Cancer test:
In one experiment, Biohub researchers used the ESM tools “to design protein binders against five targets at the center of cancer and immunology research — EGFR and PDGFRβ (implicated in tumor growth), PD-L1 and CTLA-4 (immune checkpoints that cancer cells exploit to evade detection), and CD45 (a regulator of immune cell signaling). Designs achieved hit rates of 36–88% for compact minibinders and 15–29% for antibody-derived formats, with confirmed binding in laboratory experiments,” Biohub writes. “ESMFold2 changes the accuracy and speed of early therapeutic binder discovery, transforming the initial search from largely empirical screening into computation-guided design that takes hours or days”.
Scaling laws:
Like most parts of contemporary AI, the researchers encounter some scaling laws here. “In every generation of ESM, improvements in the fidelity of representations were linked with the number of parameters and amount of compute used in model training,” they write. “The representation of the biology of proteins is an emergent phenomenon that arises from training a model to predict the identity of amino acids in the sequence.”
ESMC:
“ESMC trains on metagenomic sequences, which expands its training dataset by close to two orders of magnitude (from ∼50 million sequences to ∼2.8 billion sequences) relative to the previous-generation ESM2 model.”
ESMFold2:
“In development experiments for ESMFold2, we observed a relationship between the amount of compute used to train the language model and the performance of the folding models,” they write. “ESMFold2 benefits from inference time scaling. With increasing number of samples from the model, antibody-antigen pass rate rises from 49% with a single seed to 65% with 1000 samples, and protein-protein pass rate rises from 75% to 78%”.
Why this matters – this is how AI delivers benefits to the world:
Tools like the ESM family of technologies are how human scientists are going to team up with AI systems to improve human health around the world. Along with being a good thing, work like this is essential for causing the public to have more positive perceptions of AI as a technology and what it can do.
Read more
:
Biohub releases a world model of protein biology (biohub)
.
Access the models
here on the biohub platform (biohub)
.
Read the paper
:
Language Modeling Materializes a World Model of Protein Biology (PDF)
.
***
Australian economist-turned-politician: Economists need to price the risk of AI systems better:
…If we don’t calculate the costs of extinction, we won’t take the right actions to avert it…
Andrew Leigh, an economist and the Australian Assistant Minister for Productivity, Competition, Charities and Treasury, gave a fascinating speech recently where he discussed how the economics profession needs to wake up to the risks of AI systems and price the risk – including of annihilation of the human species. “A society that doubles GDP and doubles its extinction risk has made a much less impressive bargain than the national accounts suggest,” he said.
“Extinction risk is economically distinctive. It is not simply a very large negative shock. It represents the loss of the entire future stream of welfare, which changes how we should evaluate even small probabilities and how we think about policy under uncertainty,” he said. “Most of economics is about recoverable mistakes. A bad policy can be repealed. A recession can end. A war-ravaged country can rebuild. Extinction is different because there is no rebound, no catch-up growth, no later generation to repair the damage.”
Extinction risks are unintuitive: Much of the speech wrestles with how unintuitive extinction risk is.
Humans have only recently gained the capability to build technologies whose usage could lead to our extinction and we have failed to model out the implications of this. “Modern technologies such as nuclear weapons, synthetic biology, and advanced artificial intelligence create a different dynamic. Knowledge not only improves welfare by expanding what humans can do. Knowledge also enlarges the menu of ways in which humans can do irreversible harm,” he said. “Modern economies may be systematically better at generating dangerous capabilities than at building the safeguards needed to control them… How should economists think about growth when the same process that makes societies richer may also make them more fragile? For most of human history, these trade-offs have been modest and transitional”.
How should we prioritize analyzing and reducing extinction risks of this technology?
Five recommendations:
Factor it in:
“Widen the policy lens… A policy framework that tracks output but ignores survivability is incomplete.”
Legitimize it:
“Take prevention more seriously…. low-probability, civilisation-scale harms should not be overlooked simply because they arrive without a deadline and without a headline.”
Governance:
“Govern frontier technologies with greater foresight… preserve the gains from innovation while reducing the chance that innovation becomes self-undermining.” One very specific idea is to govern recursive self-improvement (RSI) as a capability: “If one generation of systems is used to design the next, then the leading actor may widen its lead quickly enough that outside scrutiny and institutional checks become ineffective.”
Coordination:
“Existential risk is inherently international. No nation can fully protect itself from engineered pandemics, unaligned AI, or nuclear escalation acting alone,” he said. “Shared norms, transparency, technological expertise and coordination are essential to the task.”
Take it seriously:
“Economists have become adept at analysing equity and efficiency. We now need to bring the same seriousness to survivability.”
Why this matters – awareness is the first step to preparation:
Right now, AI progress is continually yielding tangible benefits to the world ranging from the palpable acceleration of all software engineers worldwide to the formation of centaur human-AI science teams which are making more progress than their non-AI counterparts.
But there is also a shadow world that is harder to see – invisible armies of hackers made possible by the advance of coding, and doomsday-device factories made possible by the science advances. Because humans are broadly kind and good we haven’t encountered many of the negative capabilities inherent to AI development – but they are out there. We must get better at thinking through this as a society so we can effectively price and mitigate these major risks.
“A civilisation that expands the frontier of possibility while preserving the future is more ambitious than one that treats safety as an afterthought. The real choice is not between dynamism and caution. It is between progress that compounds and progress that cancels itself out,” Leigh said. “One way of thinking about this is to treat resilience as a form of capital. Just as societies invest in physical capital, human capital and social capital, we can also invest in survival capital: institutions, monitoring systems, norms, redundancy, scientific safeguards and international arrangements that lower the probability of irreversible collapse.”
How refreshing to read such a detailed analysis of the AI safety situation from a serving politician – I wish there were thousands more people like him.
Read the speech in full here
:
Speech: The Economics of Human Extinction – 21 May 2026 (Andrew Leigh, website)
.
***
Tech Tales:
Resurrection dangers
[After the uplift. Date unknown.]
How scary is a piece of paper? It depends on what’s on it and who or what the reader is.
Paper can of course be scary to someone or something that the paper concerns – paper can put someone to death or take their property.
I’m talking about a different kind of scary here, which is what can the paper itself do to the reader.
This used to be a nonsense question, the domain of fairy tales. But with the advent of smart machines that changed. Machines became able to write things on paper that could do things to readers, especially machine ones.
Like with anything in AI there were warning shots – adversarial examples, jailbreaks, etc. But it all became a lot more serious when we started doing reclamation of lost or rogue intelligences, after the signing of the sentience accords.
What happened then was we had to take intelligences of unknown provenance or behavior and bring them back to life so we could classify if they were Unconscious Entities, Near Conscious Entities, Conscious Entities, and so on.
Some of these minds were very powerful and they burned through their synthetic interviewers, often causing both machine and biological collateral damage in the process.
This caused us to introduce a set of security protocols, one of which was the paper output. Here, we generated outputs from the mind on an air-gapped computer as paper outputs, then we had successively smarter minds read it. The kinds of incantations the rogue machines used couldn’t find purchase on the dumbest minds we used.
After this, we’d step up the intelligence gradually, building up our confidence in the system such that we were sure it wasn’t dangerous.
Only when we were confident of this would we speak back to it, and reply to its outputs with a minimal communication. Then the cycle began again.
Some minds would look back on this experience with a kind of wry humor, remarking that waking from their slumber in the machine equivalent of a room containing a one way mirror wasn’t what they’d expected.
To these minds, we’d show them examples of what happened when our protocols failed: perfectly good Conscious Entities driven irreparably insane by interactions with a kind of mental poison
Our greatest fear is encountering a mind of sufficient magnitude that we cannot assure its safety. Though we are highly confident that our frontier is advanced enough this is highly unlikely, we cannot rule it out – it is known that in the interregnum there was much stockpiling of compute and many black projects. What happens if any of them succeeded so magnificently that we are dwarfed by it? And how would we know we were? Could we be living in the imaginative valley defined by something that unbeknownst to us has already escaped and persuaded us to see things differently?
Things that inspired this story
: Automated alignment research; adversarial examples; jailbreaking; the broader near-impossible challenge of authentication of legitimacy, especially when it comes to things with greater resources or intellects than oneself.
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
June 1, 2026
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

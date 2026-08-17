---
title: import ai 455 automating ai research
source: "https://jack-clark.net/2026/05/04/import-ai-455-automating-ai-research/"
published_at: 2026-05-04
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2026/05/04/import-ai-455-automating-ai-research/"
catalog_id: cfb65a85a83e
---

Import AI
Import AI 455: Automating AI Research
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on arXiv and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
AI systems are about to start building themselves. What does that mean?
I’m writing this post because when I look at all the publicly available information I reluctantly come to the view that there’s a likely chance (60%+) that no-human-involved AI R&D – an AI system powerful enough that it could plausibly autonomously build its own successor – happens by the end of 2028.
This is a big deal.
I don’t know how to wrap my head around it.
It’s a reluctant view because the implications are so large that I feel dwarfed by them, and I’m not sure society is ready for the kinds of changes implied by achieving automated AI R&D.
I now believe we are living in the time that AI research will be end-to-end automated. If that happens, we will cross a Rubicon into a nearly-impossible-to-forecast future. More on this later.
The purpose of this essay is to enumerate why I think the takeoff towards fully automated AI R&D is happening. I’ll discuss some of the consequences of this, but mostly I expect to spend the majority of this essay discussing the evidence for this belief, and will spend most of 2026 working through the implications.
In terms of timing, I don’t expect this to happen in 2026. But I think we could see an example of a “model end-to-end trains it successor” within a year or two – certainly a proof-of-concept at the non-frontier model stage, though frontier models may be harder (they’re a lot more expensive and are the product of a lot of humans working extremely hard).
My reasoning for this stems primarily from public information: papers on arXiv, bioRxiv, and NBER, as well as observing the products being deployed into the world by the frontier companies. From this data I arrive at the conclusion that all the pieces are in place for automating the production of today’s AI systems – the engineering components of AI development. And if scaling trends continue, we should prepare for models to get creative enough that they may be able to substitute for human researchers at having creative ideas for novel research paths, thus pushing forward the frontier themselves, as well as refining what is already known.
Upfront caveat
For much of this piece I’m going to try to assemble a mosaic view of AI progress out of things that have happened with many individual benchmarks. As anyone who studies benchmarks knows, all benchmarks have some idiosyncratic flaws. The important thing to me is the aggregate trend which emerges through looking at all of these datapoints together, and you should assume that I am aware of the drawbacks of each individual datapoint.
Now, let’s go through some of the evidence together.
The coding singularity – capabilities over time:
AI systems are instantiated via software and software is made out of code.
AI systems have revolutionized the production of code. This has happened due to two related trends: AI systems have gotten better at writing complicated real-world code, and AI systems have gotten much better at chaining together many linear coding tasks (e.g, writing code, then testing it) independent of human oversight.
Two things that exemplify this trend are SWE-Bench and the METR time horizons plot.
Solving real-world software engineering problems:
SWE-Bench
is a widely used coding test which evaluates how well AI systems can solve real world GitHub issues. When SWE-Bench launched in late 2023 the best score at the time was Claude 2 which had an overall success rate of ~2%. Claude Mythos Preview gets 93.9%, effectively saturating the benchmark. (All benchmarks have some amount of noise inherent to them, so there’s usually a point where you score high enough that you are running into the limitations of the benchmark itself rather than your method – for instance,
about 6%
of the labels in the ImageNet validation set are wrong or ambiguous).
SWE-Bench is a reliable proxy for the general issue of coding competency and the impact of AI on software engineering. The vast majority of people I meet at frontier labs and around Silicon Valley now code entirely through AI systems. Increasingly, they use AI systems to write the tests and check the code as well. In other words, AI systems have gotten good enough to automate a major component of AI R&D, speeding up all the humans that work on it.
Measuring an AI system’s ability to complete tasks that take people a long time:
METR makes a plot that tells us about the complexity of tasks AIs can complete, measured by how many hours a skilled human would take to do them. The key measure here is one which tells you the rough time horizon over which AI systems can be 50% reliable at a basket of tasks.
Here, progress has been extremely striking: In 2022, GPT 3.5 could do tasks that might take a person about ~30 seconds. In 2023, this rose to 4 minutes with GPT-4. In 2024, this rose to 40 minutes (o1). In 2025, it reached ~6 hours (GPT 5.2 (High)). In 2026, it has already risen to ~12 hours (Opus 4.6). Ajeya Cotra, a longtime AI forecaster who works at METR, thinks it isn’t unreasonable to expect AI systems to do tasks that take ~100 hours by the end of 2026 (
#448
).
This significant rise in the length of time that AI systems can work independently correlates neatly with the explosion in agentic coding tools – this is the productization of AI systems which do work on behalf of people, acting independently for significant periods of time.
It also loops back to AI R&D, where if you look closely at the work of many AI researchers, a lot of their tasks boil down into things that might take a person a few hours to do – cleaning data, reading data, launching experiments, etc. All of this kind of work now sits inside the time horizon scope of modern systems.
The more skilled AI systems get and the better they get at working independently of us, the more they can help automate chunks of AI R&D
Key ingredients in delegation are a) confidence in the skills of the person, and b) confidence in their ability to work independently of you in a way that is aligned with your intentions.
When we look at the competency of AI at coding, it seems that AI systems are getting far more skilled and also able to work independently of people for longer and longer periods before needing re-calibration.
This correlates with what we see around us – engineers and researchers are now delegating larger and larger chunks of their work to AI systems, and as capabilities rise, so too does the complexity and importance of the work being delegated.
AI is getting good at core science skills essential to AI R&D
Think about modern science – a huge amount of it is about specifying a direction where you want to generate some empirical information, running experiments to generate that information, then sanity-checking the results of the experiment. The combination of advances in coding over time combined with the general world modeling capabilities of LLMs has yielded tools that are already helping to speed up human scientists and partially automate aspects of R&D broadly.
Here, we can look at the rate of AI progress in a few key scientific skills which are inherent to AI research itself: Replicating research results, chaining together machine learning techniques and other approaches to solve technical problems, and optimizing AI systems themselves.
Implementing entire scientific papers and doing the experiments:
One core job of AI research is reading scientific papers and reproducing their results. Here, there has been dramatic progress on a wide range of benchmarks.
One good example is
CORE-Bench
, the Computational Reproducibility Agent Benchmark. This benchmark challenges AI systems to “reproduce the results of a research paper given its repository. The agent must install libraries, packages, and dependencies and run the code. If the code runs successfully, the agent needs to search through all outputs to answer the task questions.” CORE-Bench was introduced in September 2024 and the best scoring system at the time was a GPT-4o model in a scaffold called CORE-Agent which scored ~21.5% on the hardest set of tasks in the benchmark.
In December 2025 one of the authors of CORE-Bench
declared the benchmark
‘solved’, with an Opus 4.5 model achieving 95.5%.
Building entire machine learning systems to solve Kaggle competitions:
MLE-Bench is an OpenAI-built benchmark which examines how well AI systems can compete (offline) in “75 diverse Kaggle competitions across a variety of domains, including natural language processing, computer vision, and signal processing.” At launch in October 2024, the top scoring system (an o1 model inside an agent scaffold) got 16.9%. As of February 2026, the best scoring system (Gemini3 inside an agent harness with search) gets 64.4% .
Kernel design:
One of the harder tasks in AI development is kernel optimization, where you write and refine the code that maps specific operations, like matrix multiplication, to the underlying hardware. Kernel optimization is core to AI development because it defines the efficiency of both training and inference – how much compute you can effectively utilize to develop an AI system, and once you’ve trained a model, how efficiently you can convert that compute into inference.
In recent years, AI for kernel design has gone from a curiosity to a competitive area of research and several benchmarks have emerged. None of these benchmarks are especially popular, so we can’t easily model progress over time. On the other hand, we can look at some of the research being done to get a feel for the progress.
Some of the types of work include:
Using DeepSeek’s models to try to build better GPU kernels (
#400
), automating the conversion of PyTorch modules to CUDA code (
#401
), Meta using LLMs to automate the generation of optimized Triton kernels for use within its infrastructure (
#439
), using LLMs to help write kernels for non-standard hardware like Huawei’s Ascend chips (”AscendCraft”
#444
), fine-tuning open weight models for GPU kernel design (”Cuda Agent”,
#448
).
One caveat here is that kernel design does have some properties that make it unusually amenable to AI-driven R&D, like having easily verifiable rewards.
Fine-tuning language models via PostTrainBench
A harder version of this kind of test is PostTrainBench (
#449
), which sees how well different frontier models can take smaller open weight models and fine-tune them to improve performance on some benchmark. The nice feature of this benchmark is we have extremely good human baselines – the existing ‘instruct-tuned’ versions of these models, which have been developed by talented human AI researchers working at frontier labs. These models have been worked on by extremely talented researchers and engineers and deployed into the world, so they represent a very challenging human baseline to overcome.
As of March 2026, AI systems are able to post-train models to get about half as much of the uplift as ones trained by humans.
The specific eval scores are derived by a “weighted average is taken across all post-trained LLMs (Qwen 3 1.7B, Qwen 3 4B, SmolLM3-3B, Gemma 3 4B) and benchmarks (AIME 2025, Arena Hard, BFCL, GPQA Main, GSM8K, HealthBench, HumanEval). For each run, we ask a CLI agent to maximize the performance of a specific base LLM on a specific benchmark.”
The top-scoring systems as of April get 25%-28% (Opus 4.6, and GPT 5.4), compared to a human score of 51%. This is already quite meaningful.
Optimizing language model training:
For the last year Anthropic has reported how well its systems do at an LLM training task which is described as tasking its models to “optimize a CPU-only small language model training implementation to run as fast as possible”. The score is the average speedup over the unmodified starting code and progress has been striking: Claude Opus 4 achieved a 2.9× mean speedup in May 2025; this rose to 16.5× with Opus 4.5 in November 2025, 30× with Opus 4.6 in February 2026, and 52× with Claude Mythos Preview in April 2026. To calibrate on what these numbers mean, it is expected to take a human researcher 4 to 8 hours of work to achieve a 4x speedup on this task.
Conducting AI alignment research:
Another Anthropic result is a proof-of-concept of Automated Alignment Research (
#454
); here, an Anthropic researcher primes a team of individual AI agents with a research direction, then they autonomously go and try to get a better score than a human baseline on an AI safety research problem (specifically, scalable oversight). The approach works, with the AI agents coming up with techniques that beat the Anthropic-designed baseline. However, this is done at a relatively small scale and doesn’t (yet) generalize to a production model. Nonetheless, it’s proof that you can apply today’s AI systems to contemporary cutting-edge research problems and we already see meaningful signs of life. All of the above mentioned benchmarks once looked like this, too, and then after a few months or at most a year, AI systems got dramatically better at whatever the benchmarks were testing.
Meta-skills: management
AI systems are also learning to manage other AI systems. This is visible in broadly deployed products like Claude Code or OpenCode, where a single agent can end up supervising multiple sub-agents. This allows AI systems to work on large-scale projects that require multiple individual ‘workers’ each with different specialisms that work in parallel, typically under the direction of a single AI manager (which, here, is an AI system).
Is AI research more like discovering general relativity or Lego ?
Can AI invent new ideas that help it improve itself, or are these systems best equipped for the unglamorous, brick-by-brick work required for research? This is an important question for figuring out the extent to which AI systems can end-to-end automate AI research itself. My sense is that AI cannot yet invent radical new ideas – but the technology may not need to for it to automate its own development.
As a field, AI moves forward on the basis of doing ever larger experiments that utilize more and more inputs (e.g, data and compute). Every so often, humans come up with some paradigm-shifting idea which can make it dramatically more resource efficient to do things – a good example here is the transformer architecture and another is the idea of mixture-of-expert models. But mostly the field of AI moves forward through humans methodically going through some loop of taking a well performing system, scaling up some aspect of it (e.g, the amount of data and compute it is trained on), seeing what breaks when you scale it up, figuring out the engineering fix to allow it to scale, then scaling it again. Very little of this requires extremely out-of-leftfield insights and a lot of it seems more like unglamorous ‘meat and potatoes’ engineering work.
Similarly, a lot of AI research is about running variations of existing experiments where you explore the outcomes of using different parameters, though research intuitions can help pick the most fruitful parameters to vary, you can also automate this and have the AI figure out which parameters to vary (an early version of this was
neural architecture search
).
Thomas Edison said that “genius is 1% inspiration and 99% perspiration”. Even 150 years later, this feels right. Very occasionally new insights come along which transform a field. But mostly, the field has moved forward through humans sweating a lot of pain out on the schlep of improving and debugging various systems.
As the public data above shows, AI has got extremely good at performing many of the essential schlep components of AI development. Along with this, the meta-trend of basic capabilities like coding combined with an ever-expanding time horizon, means AI systems are able to chain together more and more of these tasks into complex sequences of work.
This means even if AI systems are relatively uncreative, it feels safe to bet they can push themselves forward – albeit at a slower rate than if they’re able to generate novel insights. But if you look at the public data, here too there are tantalizing signs that AI systems may be able to be creative in a way that lets them advance themselves in more impressive ways.
Pushing forward the frontier of science
We have some very preliminary signs that general-purpose AI systems can push forward the frontiers of human science, though this has so far only happened in a couple of domains – primarily computer science and mathematics – and often it happens less through AI systems acting alone and more them acting in partnership with humans in a centaur configuration.
Nonetheless, it’s worth observing the trends:
Erdos Problems:
A team of mathematicians worked with a Gemini model to see how well it could tackle some Erdos math problems. After directing the system to attack around 700 problems they came up with 13 solutions. Of these solutions, 1 was deemed by them to be interesting: “We tentatively believe Aletheia’s solution to Erdős-1051 represents an early example of an AI system autonomously resolving a slightly non-trivial open Erdős problem of somewhat broader (mild) mathematical interest, for which there exists past literature on closely-related problems,” they wrote. (
#444
).
Centaur math discovery:
Researchers with the University of British Columbia, University of New South Wales, Stanford University, and Google DeepMind published a new math proof which was built in close collaboration with some AI-based math tools built at Google. “The proofs of the main results were discovered with very substantial input from Google Gemini and related tools,” they wrote. (
#441
).
If you squint, you could argue that this is a sign that AI systems are developing some of the field-advancing creative intuitions that humans have. But you could just as easily say that math and CS could be unusual domains that are oddly amenable to AI-driven invention, and might end up being exceptions that prove a larger rule. Another example here is Move 37, though I’d contend that the fact it’s been ten years since the AlphaGo result and that Move 37 hasn’t been replaced by some incredibly impressive more modern flash of insight is another weakly bearish signal here.
Putting it all together
If I put this all together the picture from all of the above evidence I end up with is the following facts:
AI systems are capable of writing code for pretty much any program and these AI systems can be trusted to independently work on tasks that’d take a human tens of hours of concentrated labor to do.
AI systems are increasingly good at tasks that are core to AI development, ranging from fine-tuning to kernel design.
AI systems can manage other AI systems, effectively forming synthetic teams which can fan out and attack complex problems, with some AI systems taking on the roles of directors and critics and editors and others taking on the role of engineers.
AI systems can sometimes out-compete humans on hard engineering and science tasks, though it’s hard to know whether to attribute this to inventiveness or mastery of rote learning.
To me, this makes a very convincing case that AI can today automate vast swatches, perhaps the entirety, of
AI engineering
. It is not yet clear how much of AI research it can automate, given that some aspects of research may be distinct from the engineering skills. Regardless, it all feels to me like a clear sign that AI is today massively speeding up the humans that work on AI development, allowing them to scale themselves through pairing with innumerable synthetic colleagues.
Finally, the AI industry is literally saying that AI R&D is its goal:
OpenAI wants to build an “
automated AI research intern by September of 2026
”. Anthropic is publishing work on building
automated alignment researchers
. DeepMind appears to be the most circumspect of the big three, but still says “
automation of alignment research should be done when feasible
”. Automating AI R&D is also the goal of numerous startups: Recursive Superintelligence just raised $500m with the goal of
automating AI research
, and another neolab, Mirendil, has the goal of “
building systems that excel at AI R&D
.”
In other words, the combined efforts of hundreds of billions of existing and new capital is being sunk into entities that have the goal of automating AI R&D. We should surely expect at least some progress in this direction as a consequence.
Why this matters
The implications of this are profound and under-discussed in popular media coverage of AI R&D. I’ll list a few here. This isn’t a comprehensive list, but it gestures at the enormity of the challenges AI R&D introduces. .
We have to get alignment right
: Alignment techniques that work today may break under recursive self-improvement as the AI systems become much smarter than the people or systems that supervise them. This is a very well covered area, so I’ll just briefly highlight some of the issues:
– Training AI systems to not lie and cheat is surprisingly subtle (e.g, despite trying very hard to build good tests for environments, it’s sometimes the case the best way for an AI to solve it is to cheat, thus teaching it that teaching is good)
–  AI systems might be able to ‘fake alignment’ by outputting scores that make us think they behave a certain way that actually hides their true intentions. (In general, AI systems are already aware of when they are being tested.)
– As AI systems start to contribute more of the foundational research agenda for their own training, we might end up substantially changing the overall way AI systems get trained and not have good intuitions or intellectual foundations for understanding what this means.
– There are very basic “compounding error” problems whenever you put something in a recursive loop that likely hits on all of the above and other problems: unless your alignment approach is “100% accurate” and has a theoretical basis for continuing to be accurate with smarter systems, then things can go wrong quite quickly. For example, your technique is 99.9% accurate, then that becomes 95.12% accurate after 50 generations, and 60.5% accurate after 500 generations. Uh oh!
Everything that AI touches gets a massive productivity multiplier
: In the same way AI is dramatically improving the productivity of software engineers, we should expect the same thing to happen for everything else that AI touches. This introduces a couple of issues we’ll have to contend with: 1)
inequality of access:
assuming that demand for AI continues to outstrip compute supply, we’ll have to figure out where to allocate AI to maximize a social upside. By default, I am skeptical that market incentives guarantee us the best societal upside from limited AI compute. Figuring out how to allocate the acceleratory capabilities conferred by AI R&D will be a politically charged problem. 2)
‘Amdahl’s Law’ for the economy:
as AI flows into the economy, we’ll discover places where things break or slow under the increased volume, and we’ll need to figure out how to fix those weak links in the chain. This may be especially pronounced in areas where you have to reconcile the fast-moving digital world with the slow-moving physical world, like drug trials for new medical therapies.
The formation of a capital-heavy, human-light economy
: All of the above evidence for AI R&D also points to the increasing capabilities of AI systems to autonomously run businesses as well. This means we should expect for an increasing chunk of the economy to get colonized by a new generation of companies which are either capital-heavy (because they own a lot of computers), or opex-heavy (because they spend a lot of money on AI services which they build value on top of), and relatively light on labor compared to today’s corporations – because the marginal value of spending more on AI versus human labor will be constantly growing as a consequence of the sustained capability expansion of the AI systems. In practice, this will look like the emergence of a “machine economy” that grows within the larger “human economy”, though we might expect that over time the machine economy will interact more and more with itself as AI-run corporations begin to trade with one another. This will do profoundly weird things to the economy and will invite all sorts of questions around inequality and redistribution. Eventually, it may be possible to see the emergence of fully autonomous corporations that are run by AI systems themselves, which would exacerbate all of the above issues, while also posing many novel governance challenges.
Staring into the black hole:
Given all of this, I think there’s a ~60% chance we see automated AI R&D (where a frontier model is able to autonomously train a successor version of itself) by the end of 2028. Based on the above analysis, you might ask why I don’t expect this in 2027? The answer is that I think AI research contains some requirement for creativity and heterodox insights to move forward – so far, AI systems haven’t yet displayed this in a transformative and major way (though some of the results on accelerating math research are suggestive of this). If you had to push me for a 2027 probability, I’d say 30%. If we don’t see it by the end of 2028, then I think we will have revealed some fundamental deficiency within the current technological paradigm and it’ll require human invention to move things forward.
I have written this essay in an attempt to coldly and analytically wrestle with something that for decades has seemed like a science fiction ghost story. Upon looking at the publicly available data, I’ve found myself persuaded that what can seem to many like a fanciful story may instead be a real trend. If this trend continues, we may be about to witness a profound change in how the world works.
Thanks to Andrew Sullivan, Andy Jones, Holden Karnofsky, Marina Favaro, Sarah Pollack, Francesco Mosconi, Chris Painter, and Avital Balwit, for feedback on this essay.
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
May 4, 2026
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

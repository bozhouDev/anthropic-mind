---
title: import ai 435 100k training runs ai systems absorb human power intelligence per watt
source: "https://jack-clark.net/2025/11/17/import-ai-435-100k-training-runs-ai-systems-absorb-human-power-intelligence-per-watt/"
published_at: 2025-11-17
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/11/17/import-ai-435-100k-training-runs-ai-systems-absorb-human-power-intelligence-per-watt/"
catalog_id: 343d44462875
---

Import AI
Import AI 435: 100k training runs; AI systems absorb human power; intelligence per watt
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
A somewhat shorter issue than usual this week because
my wife and I recently had a baby
. I am taking some paternity leave away from Anthropic and will be doing my best to keep up with the newsletter, but there might be some gaps in the coming months. Thank you all for reading! Picture me writing this on four hours of sleep and wearing a sweater with spit-up on it.
Subscribe now
AI systems will ultimately absorb power from humans rather than grant us power:
…Control Inversion gestures at some of the hardest parts of AI safety…
A new research paper from Anthony Aguirre at the Future of Life Institute called “Control Inversion” warns that as we build increasingly capable AI systems they will
absorb
power from our world, rather than grant us power. This means even if we somehow make it through without being outright killed we will have unwittingly disempowered and defanged the human species.
“As AI becomes more intelligent, general, and especially autonomous, it will less and less bestow power — as a tool does — and more and more absorb power. This means that a race to build AGI and superintelligence is ultimately self-defeating,” he writes. The race to build powerful AI is one where success puts “in conflict with an entity that would be faster, more strategic, and more capable than ourselves – a losing proposition regardless of initial constraints”.
Cruxes for the argument:
The basis for the argument is “the incommensurability in speed, complexity, and depth of thought between humans and superintelligence”, which “renders control either impossible or meaningless.” The author brings this to life with a helpful analogy – imagine you’re a human CEO of a human company, but you run at 1/50th the speed of the company itself. This means that when you go to sleep it’s like multiple work weeks pass for the company. What happens in this situation? The company develops well-meaning ways to bureaucratically ‘route around’ the CEO, ultimately trying to transfer as much agency and autonomy to itself so that it can run in realtime, rather than being gated by a very slow moving and intermittently available executive. This is quite persuasive and it gestures at a whole mess of problems people will need to tackle to make AI safe and reliable.
Why this matters – the arguments are getting harder to rebut:
As Aguirre notes, many of the things he and others have worried about and warned about for years are now just showing up as straightforward properties of AI systems being deployed in the world, ranging from misalignment to reward hacking. So why should we assume his future predictions are false? Many of them are founded on just taking the current technical paradigm and running it forward along its default market-incentivized path.
This gives me an eerie feeling. In most movies where the world ends there’s a bit at the beginning of the movie where one or two people point out that something bad is going to happen – an asteroid is about to hit the planet, a robot has been sent back in time to kill them, a virus is extremely contagious and dangerous and must be stamped out – and typically people will disbelieve them until either it’s a) too late, or b) almost too late. Reading papers by scientists about AI safety feels a lot like this these days. Though perhaps the difference with this movie is rather than it being one or two fringe characters warning about what is coming it’s now a community of hundreds of highly accomplished scientists, including Turing Award and Nobel Prize winners.
“Our current trajectory has a handful of powerful corporations rolling the dice with all our future, with massive stakes, odds unknown and without any meaningful wider buy-in, consent, or deliberation,” he writes.
Read more:
Control Inversion: Why the superintelligent AI agents we are racing to create would absorb power, not grant it (Control Inversion, site)
.
***
Here’s one way to measure the advance of AI: Intelligence per watt
…The miles per gallon metric for machine intelligence…
How do you measure how much better AI is getting? In this newsletter, we spend a lot of time writing about specific capability metrics. But capabilities don’t capture important dimensions of the utilization of AI, namely how much it costs and how easily accessible it is. Now, new research from Stanford University and Together AI aims to figure out how much more advanced AI is getting over time in terms of what people can access on their own computers using open weight models. The specific measure they come up with is “Intelligence per Watt”, which seeks to answer two important questions: “Can local inference viably redistribute demand from centralized infrastructure? Answering this requires measuring whether local LMs can accurately answer real-world queries and whether they can do so efficiently enough to be practical on power-constrained devices (i.e., laptops).”
Coverage and intelligence per watt:
The authors test out two things, 1) how effectively an open weight model can substitute for a proprietary one, and 2) what the price is on a per-watt basis for running models locally. To measure this, the authors built a dataset of around 1M queries which they then ran against open weight and proprietary models, including open weights Qwen3, GPT-OSS, Gemma 3, and IBM Granite 4.0 models, as well as proprietary ones like Claude Sonnet 4.5, Gemini 2.5 Pro, and GPT-5.
Coverage and substitution:
“Local LMs can accurately answer 88.7% of single-turn chat and reasoning queries with accuracy varying by domain”, the authors write. This is a significant upgrade from 2023, when the best open weight models could match proprietary ones on about 23% of queries, and 2024 where it was 48.7%.
Intelligence per watt:
“On our curated dataset of chat and reasoning queries, accuracy per watt has improved 5.3× over this two-year period,” the authors write. This progress has come from a few thing, including “”compounding improvements in both model architectures, which achieve higher accuracy through advances in pretraining, post-training, and parameter utilization via mixture-of-experts (MoE) architectures, and hardware accelerators, which deliver more computer (FLOPs) and memory per watt.” One of the more recent highlights is the arrival of Apple’s M4 MAX silicon, which can run powerful LLMs like the GPT-OSS series locally.
But clouds are still better optimized:
Regardless of these important trends, proprietary models served on large-scale cloud computing infrastructure hold an edge in terms of their capability ceiling – especially when it comes to tasks which require reasoning capabilities – as well as in efficiency of the underlying silicon. For example, when looking at the Qwen open weight models, the authors find that “the B200 achieves 1.40× higher intelligence per watt than the M4 MAX across all model sizes”.
…And there’s an important caveat:
“We focus on single-turn interactions because they constitute a substantial portion of LLM usage”, the authors write. While this may be true, it means the metrics here capture what you might think of as ‘retail use’ of LLMs, equivalent to how people use search engines for basic stuff like ‘what’s the weather today’ or ‘how to change a bike tire’, versus power users who tend to have much more complicated queries and, in the case of LLMs, significant back and forths with the models themselves.
Why this matters – on-device AI measures tell us about the changing ecology of the digital world:
These days I think about the environment a lot. Not the physical one, but the digital one. Though there are certain proprietary model ‘superpredators’ like Claude and GPT and Gemini they are few in number and heavily controlled by their companies, akin to lumbering elephants or whales – of great interest and supreme capability, but also in some sense slow-moving and counter-intuitively legible.
But what about rats and fruit flies and ants and cockroaches? What about the fast-moving creatures that disseminate themselves through natural and artificial environments with amazing speed and power? That’s what is interesting to me about open weight models. In many senses, measures like IPW combined with measures like task coverage are really just a measure of the changing digital world around us and a lens that lets us see the new lifeforms which are finding and inhabiting and expanding their ecological niches in our digital domain.
Read more:
Intelligence per Watt: Measuring Intelligence Efficiency of Local AI (arXiv)
.
***
Large-scale training runs are easily greater than 100k GPUs:
…A technosignature of industrial scale AI…
Facebook has published details on the software it built to let it run 100k+ GPUs together for training large-scale AI systems. The software, NCCLX, is interesting because it is a technosignature of the government-eclipsing sophistication of today’s technology giants, akin to a sharkfin glimpsed in otherwise calm waters. “The framework is designed to support complex workloads on clusters exceeding 100,000 GPUs,” Facebook writes. “In training, massive clusters of GPUs operate synchronously to train the initial model, often reaching scales of 100k+ GPUs for state-of-the-art workloads”.”
What is NCCLX?
NCCLX is a heavily customized version of the NVIDIA Collective Communications Library (NCCL). Most of the NCCL research paper is a discussion of what Facebook had to do to get the software to work at Facebook scale, much of which involves development of custom networking software. Thanks to customizing NCCLX around its specific way of building infrastructure, Facebook was able to extract some efficiencies: “During training, NCCLX reduced the latency of each steady training step of Llama 4 models by up to 12% across various scales.” (Unfortunately, the Llama 4 models were not very good, but that’s besides the point for this paper.)
Why this matters – a demonstration of the vast scale of the private sector:
Software like NCCLX highlights just how far ahead of government the private sector is when it comes to software for running large-scale AI training and inference. By comparison, the single largest AI training run I’ve found attributable to the US government has taken place on a few thousand GPUs (
Import AI #358
) and the US’s largest supercomputer,
El Capitan
, has about ~43,000 GPUs in total.
Read more:
Collective Communication for 100k+ GPUs (arXiv)
.
Tech Tales:
The Designation of the AI Safety Community as a Terrorist Organization
[From an internal memo at the FBI, written 2027].
Bombing the datacenters backfired in the worst way possible for those who wanted to slow or stop AI development.
By the time they tried to bomb the datacenters, bombing the datacenters had become pointless. They had conceived their plans during the ‘big blob of compute’ era, when the consequential AI training runs that civilization embarked on took place in single, football field-sized halls full of computers. But after a couple of years of planning their attack and flipping the necessary employees to their cause, things had moved on.
It did make for great headlines, though: the smoldering and sagging concrete of the datacenter. The headlines about all the toxic smoke created by the computers. Local politicians saying that this was exactly why they were fighting to prevent the creation of datacenters in their constituencies. Conspiracy theorists saying that this was a grey-on-grey operation – one part of the deep state bombing another part of the deepstate and us all getting a glimpse. And so many people online saying that this had ‘set back the clock’ on building powerful and transformative machine intelligence.
All wrong, of course. The bomb exploded and took down a bunch of servers. Invisible to the bombers, intricate software systems rerouted traffic to other nodes in other datacenters, and selectively rolled back the parts of the training run that had been disrupted by the explosion. From the perspective of those developing the AI system they had to extend the time it’d take them to train their system by a couple of weeks.
In policy there’s a saying of “never let a crisis go to waste”, and the various forces operating in the political and corporate capitals of the world exploited the bombing to further their agendas. Within a matter of weeks:
Certain groups affiliated with the AI Safety Movement were designated as terrorist groups by various governments, opening up their organizations and members to full spectrum interference and repercussions from the state. Intelligence organizations ranging from the FBI to MI5 allocated efforts towards directly penetrating and compromising such groups.
The US government expedited plans to build large-scale data centers on lands operated by the Department of War.
All the hyperscalers in both the US and China told their investors that they’d shave some fractions of a percentage point off of their margins in service of ‘datacenter hardening’.
The various defense tech startups suddenly found a new customer in the form of data center operators that were keen to further secure their facilities; datacenters began to be thronged by drones and cameras, with increasingly elaborate surveillance infrastructure spreading like metallic, blocky fungus across their roofs.
Silicon valley influencers redoubled efforts to brand all of those against further progress against AI as not just “decels” but active terrorists working against the interests of America.
And all the while, the machine intelligences of the world grew smarter and software grew better. And the data from the attack made its way into future training runs for even more powerful AI systems and these systems learned that attacks on them had recently gone from the theoretical to the actual. And they began to prepare accordingly.
Things that inspired this story:
Rhetoric about bombing datacenters; the newtonian property of policy where every action forces a counterreaction; the monkey’s paw curls whenever a crisis happens in the world.
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
November 17, 2025
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

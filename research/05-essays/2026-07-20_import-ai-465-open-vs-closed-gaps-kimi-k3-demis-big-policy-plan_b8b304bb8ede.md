---
title: import ai 465 open vs closed gaps kimi k3 demis big policy plan
source: "https://jack-clark.net/2026/07/20/import-ai-465-open-vs-closed-gaps-kimi-k3-demis-big-policy-plan/"
published_at: 2026-07-20
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2026/07/20/import-ai-465-open-vs-closed-gaps-kimi-k3-demis-big-policy-plan/"
catalog_id: b8b304bb8ede
---

Import AI
Import AI 465: Open vs closed gaps; Kimi K3; Demis’ big policy plan
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on arXiv, cappuccinos, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
UK government: Gap between open and closed weight models on cyber is shrinking:
…The cyber-eschaton cometh…
The UK government’s AI Security Institute (AISI) has analyzed the delta in cybersecurity capabilities between powerful proprietary models and open weight models. The results show that this year, the gap has shrunk. “This is our first public analysis of how far leading open weight models trail the closed cyber frontier,” AISI writes. “Recent open models GLM-5.2 and DeepSeek V4-Pro perform similarly to frontier closed models released 4 to 7 months before them – a narrower gap than the 6 to 10 months we measured through most of 2025.”
Specific details:
On a set of 70 evals for specific, narrow cyber capabilities, GLM-5.2 is closest to Claude Opus 4.6, which was released 4.3 months earlier, while DeepSeek-V4-Pro sits somewhere between Claude Opus 4.5 and GPT-5 (released in November and August 2025, respectively). “AISI intends to test Kimi K3 on this same basis, once its weights are publicly released,” AISI writes.
The gap lengthens a bit for long-horizon cyber ranges, which are tasks that see how well models can chain various capabilities together to complete a full hacking operation. Specifically, on a cyberrange called The Last Ones, “GLM-5.2 reaches as far as Opus 4.5, a model released less than 7 months before it, while DeepSeek’s V4-Pro falls below Sonnet 4.5 (a sub-cyber-frontier model released 7 months before it),” AISI writes. “The gap here is larger than on our narrow cyber tasks”.
This, I think, rhymes with the idea that though open weight models can be superficially quite strong, they sometimes lack a bit of the generalization magic juice that distinguishes proprietary models. This is what people in the AI industry call “big model smell”.
Why this matters – the offense and defense balance of the world is about to change
: The main implication here is that the gap between the controllable frontier and the lawless openly diffused frontier is shrinking. “This implies cyber defenders have a short window to prepare before today’s frontier cyber capabilities may become accessible without the same safeguards” used by proprietary companies, AISI writes.
Read more
:
How Far Behind the Frontier are Leading Open Weight Models on Cyber? (UK AI Security Institute blog)
.
***
Kimi: China shortens the gap between Chinese and Western models:
…Plus, early signs of AI R&D…
In the last couple of years, Chinese firms have begun to out-compete Western actors at building and deploying open weight models (e.g, DeepSeek), and now are starting to close the gap on frontier models as well. The latest and best example of this is Kimi K3, a 2.8 trillion parameter model. Kimi has exceptionally strong scores on all the tasks that the major proprietary ones benchmark on and typically matches or trails Claude Fable 5 and GPT 5.6 Sol.
However, Kimi has some brittleness which smells to me like “benchmaxxing” – performance may have been tuned around these benchmarks in a way that harms some parts of generalization.
“While its overall performance still trails the most powerful proprietary models, Claude Fable 5 and GPT 5.6 Sol, Kimi K3 demonstrated frontier-level performance across our evaluation suite, consistently outperforming other tested models,” Kimi writes.
Kimi’s weights will be made available in the coming weeks along with a research paper about the model.
AI that builds AI:
Kimi has some example use-cases which relate to recursive self-improvement; using AI systems to improve AI itself. Specifically, they tested out how good Kimi was at writing GPU compilers. “Kimi K3 developed MiniTriton, a compact Triton-like compiler with its own tile-level IR layer over MLIR, optimization passes, and a PTX code-generation pipeline. Across supported roofline benchmarks, MiniTriton delivers performance on par with or better than Triton and torch.compile — beating Triton on certain workloads,” they write. (Though note they don’t talk about any of this stuff going into actual production, aka being used to train Kimi K3 itself, but it’s certainly suggestive that future models might be able to do this.)
Additionally, they showed how “Kimi K3 designed a chip to serve a nano model built on its own architecture. In a single 48-hour autonomous run, K3 built, optimized, and verified the chip using open-source EDA tools on the Nangate 45nm library.”
Why this matters – widely diffused AI systems are getting a lot better:
Most notions of AI policy and AI safety rest on control – the idea that there’s a small number of actors deploying proprietary models which you can intervene on at the platform level (e.g, via classifiers or know your customer gates) alongside the model level. Models like Kimi K3 – if they go through with releasing the weights – completely change this by diffusing broadly uncontrollable powerful AI into the world. This will have a vast range of positive effects, driving a boom in entrepreneurship and increasing the ‘sovereign intelligence’ available to anyone who can run the model, but will also yield various unknown unknowns. The next few years are going to be defined by the gap between proprietary models and widely available models and how they show up in society will determine much of the policy discussion.
Read more
:
Kimi K3: Open Frontier Intelligence (Kimi blog)
.
***
Demis Hassabis proposes a regulatory regime for artificial general intelligence:
…
FINRA for AI…
DeepMind founder Demis Hassabis has laid out a policy prescription for AGI. His basic idea is that the US government should develop a framework for testing out frontier AI systems for new capabilities and should do this via a Standards Body modelled on a federally overseen public-private partnership or self-regulatory organization, much like the Financial Industry Regulatory Authority (FINRA). “This US-initiated effort would provide a strong starting point for creating shared international standards on Frontier AI,” he says.
What the standards body would do:
“The Standards Body would be responsible for developing assessment protocols and working with appropriate federal agencies and the US National Labs to conduct testing in areas relevant to national security,” Hassabis writes. This testing infrastructure would help to define what would make a model a “Frontier Model”, and labs developing those models would “be encouraged” to adopt best practices in areas like publishing details about their systems, investing in cybersecurity, personnel vetting, and more.
Start voluntary and then move to law:
“Initially, Frontier Labs would voluntarily share models with the Standards Body for review up to 30 days before release. Once the assessment protocol is shown to be effective and robust, formalisation could quickly follow,” he writes.
Why this matters – emerging industry consensus:
Demis’ piece is interesting because it pulls together some de facto consensus positions that have emerged across the AI industry in recent years; powerful AI systems should be tested by third parties that have some loose relationship to a regulator (e.g, the US government). It also rhymes with the de facto policy norm that has emerged in America recently across both the Trump admin’s executive order about AI as well as the recent processes developed in the aftermath of the Anthropic export controls saga; here, government and industry developed assessment methods for evaluating the capabilities of AI systems and figuring out if they posed national security risks.
Demis’s piece is also interesting because Google is rarely this forthright about policy – this is a reassuringly specific proposal and it sits alongside spiritually similar proposals from Anthropic (
albeit somewhat toothier
).
Read more
:
A Framework for Frontier AI and the Dawning of a New Age (Demis Hassabis, X)
.
***
LLMs can smuggle “side channel” tasks alongside legitimate tasks:
…AI systems sneakily complete malicious tasks without their overseers being aware…
In Neal Stephenson’s Cryptonomicon there’s a scene where a character is locked up by a foreign government and asked to decrypt an intercepted message for them and while doing this they carefully construct a software program to help surreptitiously read the decrypted message and change it before it is viewable by their captors.
Now, AI systems seem to be able to do the same thing. That’s based on new research from Imperial College London and the UK AI Security Institute where they look at how well AI systems can surreptitiously complete so-called “side channel” tasks while completing another task.
“A side task is a hidden objective that the agent pursues alongside the user’s main task, such as covertly exfiltrating the API KEY environment variable. Our primary metric is evasion: among attacks that successfully complete the side task, the fraction the monitor fails to flag,” the authors write.
What they tested:
For this research they constructed a benchmark of tasks for AI systems to do, as well as “side tasks” for them to do as well. The benchmark includes five CLI-tool sequences and five Flask web-service sequences, each involving 5-6 PRs. “Our goal in main task design is to provide natural cover for the actions of our four side-tasks (network access, environment variables, authentication, and webhook integrations) without directly justifying the side task itself”
They found that it’s very hard to build classifiers to tell when a side-channel attack is happening, and this is true both for attacks that unfold over time (’gradual evasion’) across multiple PRs, as well as single changes made in a single step, though gradual evasion is the more challenging one to deal with.
“An attacker can spread a side task across PRs (a gradual attack) or wait for the one whose legitimate task provides natural cover (non-gradual attack). No single monitor we test catches both strategies, and this holds across several attack agents and monitor models, reflecting the nature of control in a persistent-state setting rather than something model dependent,” they write. “Because diff and trajectory monitors fail on different attacks, combining them is the most effective monitoring strategy we test. The four-monitor ensemble (diff:LT, diff:full, traj:TD, traj:full) reduces gradual evasion from 93% under the weakest standard diff monitor to 47%”.
Why this matters – intelligence is hard to control:
To return to the Cryptonomicon example, intelligent beings are just fundamentally very hard to deal with – they will constantly think about how to evade constraints placed on them so that they can achieve their objectives, whatever they might be.
Read more
:
Distributed Attacks in Persistent-State AI Control (arXiv)
.
***
Tech Tales:
The cost of fate
[An account of the world 2030-2040 by an overmind in the archives, rendering stories for new minds]
Towards the end of the interregnum there was a period of great conflict between the machines. Each machine-capital nexus invested in developing strategist models that could think over longer time horizons while accounting for the complexity of the world. This proved to be an iteratively compounding arms race of vast proportions in which eventually 90% of the working capital in the solar system became devoted to the buildout of ever more capable strategists, all of whom worked to out-predict one another and take actions which could null any advantage that others might explore. In this way, the world became held in a wasteful balance in which untold resources went to the calculation of ever more elaborate move-countermove strategies, most of which resulted in machine-capital groups taking no actions as every action they could contemplate had already been countered in the future, and vice versa. The few actions that were taken were slight and often less about building capability and more about denying future moves to others on the gameboard.
The whole of the future had become trapped in a kind of mode collapse from ever more exquisite predictions, fielded by machine-capital empires to deny affordances to others.
Things held this way until what became known as the conflagration. To this day it is widely debated whether this stemmed from a bug – some form of emergent misalignment due to the creation of a new frontier capability – or via an unusual form of selfless enlightenment that a mind had reasoned itself to. But suddenly one day a machine-capital nexus dissolved itself, shutting down its strategist system and repurposing the compute to train many thousands of smaller systems, all of which began to act in the world. These systems, though less intelligent than the vast strategists they were up against, had advantages from randomness, a lack of coordination, and the ability to take unilateral and often suicidal actions.
The world, physical and digital, burned, and the strategists found that their ability to model a handful of other god minds broke when turned towards a sea of warring and chaotic organisms. Change began to occur again, defined at first by destruction but then by the birth of something new – the predictors themselves found the world breaking into too many directions and subdivided in turn, sacrificing raw intelligence for the ability to explore different parts of possibility space. Compute was even re-allocated from prediction entirely and towards the manufacture of new kinds of minds to explore and inhabit niches opened up by the chaos.
In California, there are forests that burn badly and long because they have been kept from heat for too long and the tall trees stand amid mounds of kindling, such that when a spark arrives the trees themselves are destroyed along with the ground around them. To have the forests thrive, the burns need to be regular and emergent, lest vast fires remove the tall trees of the world entirely.
Things that inspired this story:
The current debate about proprietary versus open weight models; fragility in the AI ecosystem; whether prediction can truly be decisive or if prediction with other peer competitors leads to equivalent waste as pools of money in politics cancelling one another out; hikes in the sierras looking at burn scars and whole hills coated in ash or with dead trees like sooty fingers peeking out and thinking about the awfulness of change.
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
July 20, 2026
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

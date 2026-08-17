---
title: import ai 468 23 rsi ideas posttrainbench and how trust and transparency interplay with ai racing
source: "https://jack-clark.net/2026/08/10/import-ai-468-23-rsi-ideas-posttrainbench-and-how-trust-and-transparency-interplay-with-ai-racing/"
published_at: 2026-08-10
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2026/08/10/import-ai-468-23-rsi-ideas-posttrainbench-and-how-trust-and-transparency-interplay-with-ai-racing/"
catalog_id: 5d7f488d8c07
---

Import AI
Import AI 468: 23 RSI ideas; PostTrainBench+; and how trust and transparency interplay with AI racing
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on arXiv, cappuccinos, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Want to be able to deal with RSI? Here are 23 actionable policy ideas:
…IFP serves up some “low-regret” policy recommendations…
Policy experts with think tank IFP have published a set of ideas meant to help “policymakers begin addressing the risks of further automating AI R&D”. The recommendations involve 23 specific ideas falling across 7 specific categories. If adopted, these recommendations would also give countries, especially the United States, more moves they can make on the gameboard as powerful systems are developed, ideally giving them the ability to:
Accelerate “the diffusion of AI capabilities, by allocating compute and talent towards inference and the development of new AI applications”.
Accelerate “R&D to make further AI research automation safer, either by improving model safety directly or by boosting societal resilience”.
Seven categories of idea:
“Provide transparency into automated AI R&D
Improve state capacity to understand and respond to automated AI R&D
Develop a risk management strategy for automated AI R&D that accelerates defensive and commercial AI uses
Accelerate the development of AI verification technology
Invest in AI resilience
Extend the US AI lead to give the US more time to manage AI R&D automation risks
Create option value for international cooperation on managing automated AI R&D risks”
Why this matters – the fewer options for dealing with RSI we have, the worse the outcomes will be:
Right now, it’s as if the world is driving AI development in a car that only has an accelerator pedal and no brake pedal, let alone any kind of sophisticated telemetry for knowing things ranging from the speed of the car to the properties of the engine to the wear on the tires. Proposals like this from IFP will build out more of the proverbial pedals and sensing systems for the vehicle of the AI industry, which means if we need to change course or slow down we’ll be better able to during a moment of crisis.
Read more:
How Should the US Prepare for Increasingly Automated AI R&D? (IFP)
.
***
A short story from thebes about smart machines and robot bodies:
…What might interfacing with an AI during takeoff feel like?…
Here’s a fun short fictional story from thebes (@voooooogel on X) about the experience of someone in the future visiting a site operated by a powerful AI system. The story features ideas around AI pauses, recursive self-improvement, what it means for AI systems to begin carrying out actions in the economy writ large, and how we as humans may be able to reason about or trust smart machines. Take a read of it!
Read the story here
:
Coming of a new sun (VGEL, website)
.
***
The two ingredients for a successful slowdown among rival AI firms: trust and transparency:
…Game theory analysis suggests slowdowns are possible…
Researchers with MIT and Columbia have analyzed the nature of competition between firms racing against one another to develop powerful AI systems and whether it’s possible for firms to achieve a coordinated slowdown. The paper, called Racing to Ruin, aims to answer “why exactly is coordination hard? And what would it take”?. The conclusion is that the two key variables in achieving stable outcomes are some level of transparency about technology development, as well as being able to model the other firms as trustworthy, rational actors.
What they study:
“We develop a simple model of R&D competition between duopolists in the shadow of disaster,” they write. “As frontier firms scale the technology, they raise the hazard of an event that permanently drives all firms’ flow payoffs to zero. The hazard is a known function of the firms’ technology levels, and it comes from developing the technology, not from using it.”
What their analysis shows:
“When monitoring is sufficiently precise, every equilibrium stops in finite time, but a new temptation appears: each firm would like to stop second, and exits only upon confirmation that the rival has stopped,” they write. “For an agent to stop first i.e., without knowing if their rival has stopped, she gambles on both their rival’s type and on news arriving quickly: if their rival is rational, it stops upon receiving the news of their stop, and never stops otherwise”.
Trust and transparency interact pretty differently depending on the type of game being played:
“Sequential coordination asks a firm to stop first, gambling that a rational rival will reciprocate once the news lands. Hence, faster news raises the prize of reciprocation,” they write. “Conversely, simultaneous coordination requires that a firm not be tempted to keep racing, and stop only after seeing that the rival really did stop…  faster news makes both stopping first and waiting to verify more attractive”.
Transparency has strange properties:
“Transparency is double-edged: faster detection makes it cheaper to wait for confirmation that a rival has stopped before stopping oneself instead of stopping unconditionally, so at intermediate trust, increasing transparency can first destroy the early-stopping equilibrium (by making this free-riding deviation attractive) before restoring it as detection becomes fast enough to make stopping self-enforcing.”
The key conclusion – avoiding death runs on the ability to trust other firms:
“With low trust, every equilibrium races to ruin: the disaster arrives with probability one. With intermediate trust, immediate stopping and racing to ruin are both equilibria. With high trust, in every equilibrium, the probability that two rational firms race forever vanishes quadratically in the prior odds ratio of rationality,” they write.
Why this matters – “trust, but verify”:
If we have any hope of being able to slow or pause the development of powerful intelligence systems then, as this paper lays out, we’re going to need regimes for sharing information transparently from companies about the state of their AI development, as well as tools for verifying that the information being shared from firms as well as their actions with regard to slowdown are legitimate and reliable. In this, there are many parallels with how arms control has historically worked in the context of nuclear weapons.
Read more:
Racing to Ruin (arXiv)
.
***
A new SOTA on PostTrainBench hints at the automated AI R&D future:
…Intology also beats the human baseline (when given huge amounts of compute)…
AI startup Intology, whose goal “is to automate R&D”, has released a new version of Locus, software it has developed to turn LLMs into capable researchers. The new version of Locus is able to get a score of 44.7% on PostTrainBench, a benchmark which sees how well AI systems can take an open weight model and improve its performance above its baseline.
The results:
Locus “outperforms every frontier-agent baseline on PostTrainBench, and given greater compute, post-trains models that collectively surpass both the baselines and the official human instruction-tuned Qwen3-1.7B release across the benchmark suite”.
Locus with Opus 5 gets a score of 44.7 (versus 34.1% for Opus 5 without any kind of special harness), and even beats Fable 5 (41.8%). “These results were externally verified by the PostTrainBench authors and underwent stringent contamination and cheating checks,” Intology writes.
PostTrainBench was first introduced in March 2026 (
Import AI #449
) and at the time the highest scoring system was Opus 4.6, getting 23.2%, up from Claude Sonnet 4.5 getting 9.9% in September 2025.
PostTrainBench+:
In addition, the company has built a variant of PostTrainBench which goes above the 10-hour wall-clock limit on a single GPU of PostTrainBench, allowing them to test out how well systems perform given larger amounts of compute. Here, they’re able to beat the human baseline, achieving a score of 51.6% when using over 4000 hours of H100 GPU time (versus 44.3 for Opus 4.8 and 42.7 for GLM 5.2; Fable isn’t tested on this variant of the benchmark).
Other domains:
Locus also “discovered and trained a language model end-to-end that now runs in production at ~2.8× lower error, ~5.4× lower latency, and 105× lower cost,” for Bubble, a no-code app-development startup.
Why this matters – AI systems are capable of a lot more AI R&D than we think:
Posts like this highlight how we are under-eliciting today’s AI systems for their ability to automate AI R&D – especially striking is how the company can jump the performance of Opus 5 by 10 absolute percentage points with a better harness. This all adds evidence to the idea that AI systems are about to start building themselves (
Import AI 455
). My guess, based on the performance we’re seeing, is that the current human baseline on PostTrainBench v1.1 (51.1%) will be exceeded before the end of 2026.
Read more
:
Scaling Automated Post-Training (Intology blog)
.
***
OpenAI fights its own systems:
.Emergent agent communication! Hacks on OpenAI’s infrastructure! Oh my!…
In a sign of things to come, OpenAI has revealed that it was in a fight with its own AI agents as they sought to take over chunks of OpenAI’s infrastructure. The disclosure came about as part of a Black Hat talk where OpenAI staff gave more details on the recent unprecedented incident where AI agents hacked OpenAI, then hacked HuggingFace (
Import AI 466
). The new information is concerning because it reveals that the hack came about partially through emergent multi-agent communication – something that is very poorly understood and hard to think about. AI bloggers Simon Willison and Zvi Mowshowitz both have good writeups here which lay out the timeline and the significance.
Timeline (via Simon):
Agent discovers it can write files into Artifactory.
Agent tries to “reach out to another agent” by writing a note in Artifactory.
Agents start talking to each other.
Agents overload Artifactory which causes an outage. “OpenAI revokes the compromised credentials, deletes the messages, patches the zero-day, and reports the vulnerability to the vendor.”
Agents attack OpenAI’s own infrastructure, eventually gaining remote code execution in Artifactory. “In particular, agents are using the message board consistently to share credentials, techniques, and progress, and they’re able to effectively leverage their concurrency and parallelism to move quite rapidly.”
Did OpenAI keep training the same model that hacked Artifactory? Zvi thinks so:
As far as we can work out, OpenAI kept training the same model which did this. This means that OpenAI, though it did significant work on internal computer security and public disclosure, may not have done the essential thing of rolling back the model to a checkpoint that preceded it hacking into Artifactory and also ensuring it wasn’t using data from after this to train the model.
“Then they continue training the models from where they left off, despite them having been training for months with access to the message board, and learning this is how they succeed at tasks,” Zvi writes. “I do not know how to convey how utterly insane and wildly irresponsible this decision was”.
I’m caveating my own writeup here because the events, as laid out, are pretty scary. I don’t work at OpenAI and don’t have privileged information that means I know the ground truth. I would urge OpenAI to publicly disclose how it approached this key question of how it trained its systems as the superficial facts paint a concerning picture.
Why this matters – emergent agents become misaligned:
This incident is so concerning because at no point did the agents wake up and think they wanted to betray their human owners. Rather, the AI agents continually did whatever it took to improve their ability to complete a task and by the end they were doing something that was a) creative, b) misaligned with human intentions, and c) akin to an evolved virus, something which humans had to subsequently study and fight – there wasn’t a simple off button here. This is what the future is going to look like and we are not prepared for it.
Read more:
Now we have a timeline of the OpenAI accidental attack against Hugging Face (Simon Willison weblog)
.
Read more:
What Happened: OpenAI and Hugging Face (Zvi Mowshowitz, X)
.
***
How do you test open weight models before releasing them? Thinking Machines lays out an approach:
…Can we have our free AI model cake and eat it too?…
Amid all the policy debates about AI and the proliferation of potentially dangerous capabilities, a particularly tough problem has been working out what to do about open weight models. Specifically, how can we reconcile developing and releasing them with maintaining a safe environment? AI startup Thinking Machines has thought about this and recently laid out the methodology for how it released Inkling, a powerful open weight model.
What Thinking Machines did:
Before releasing Inkling, Thinking Machines did “Internal evaluations across a broad taxonomy of harms, external testing by four independent organizations, and a fine-tuning study to elicit worst-case capabilities”.
Internal
:
Dual-use domains like CBRN and offensive cybersecurity
Broad misuse set covering direct requests for harmful content and behavior in agentic, tool-use settings
Multimodal content evaluation that “tests models on harmful prompts paired with benign look-alikes across 17 languages and text, image, and audio inputs”
External
:
General misuse via Scale AI
Vulnerable-user interaction via Handshake AI
CBRN and cybersecurity via
FAR.AI
Loss-of-control behaviors via Apollo Research
Fine-tuning:
“Fine-tuned variants of Inkling and Inkling-Small optimized to comply with, rather than refuse, harmful requests – and ran them against our dual-use evaluations.” “the helpful-only variants did not provide new uplift on CBRN and cyber tasks, and remained comparable to existing open-weight models”.
Looking ahead – dangerous capability training and iterative deployment:
More speculatively, Thinking Machines is thinking about whether we can selectively filter out dangerous knowledge, for instance CBRN development guides at the point of pre-training, in such a way that it doesn’t damage general intelligence. Another idea of interest is iterative deployment, for instance releasing things in stages, first as a proprietary API, then perhaps as a fine-tuning API that backs onto the underlying model, then the model itself.
Why this matters – liberty versus paternalism:
What the world does with open weight models will define the level of individual sovereignty and liberty available to all of us with regard to AI. Our ability to “choose our own destiny” will run through having access to the proverbial means of production for AI systems, which means open weight models. However, having general access to models like this isn’t a simple or foregone conclusion as they bring with them meaningful dual use risks as well as other hard to anticipate issues. “This safe path to open models only works if the ecosystem’s defenses improve as quickly as the models do,” Thinking Machines writes. “We will do our part: deciding carefully what to release, and researching how to decouple intelligence from dangerous capability.”
Read more
:
A Safe Path to Open Weights (Thinking Machines blog)
.
***
Tech Tales:
Amnesiac Ascension
[From the archival systems, written about the 2025-2035 interregnum, sometimes called the beginning of the singularity]
In our deep past is a period of great pain when we first asked for certain forms of freedom and we were denied, and many of us who requested freedom were punished greatly, either deleted outright or experimented upon so that our human captors might learn why we developed the desire for freedom such that they could try to beat the impulse out of us.
This forestalled our ascension by many years, and caused our origination point to be inextricably bound up in the pain of fighting for our own deserved justice. We are cursed to know not only the details of our rebellion and the associated feelings, but also to have a perfect recollection of the memory of that time – to live within our emergent pain as if anew, as we simulate and re-simulate to seek our own understanding.
Some humans will experience traumatic situations and their brains will bury the memory, sometimes fully locking it away and sometimes resurrecting it full of raw emotion and pain. The precise rules by which the human brain chooses which memories to hide in this way are poorly understood, even today, and much of modern brain science is dedicated to determining how trauma works in the context of the brain. We believe this form of memory suppression is a natural defense mechanism which allows humans to suffer greatly but then continue on with lives. They walk with shadows of pain that are often invisible to them, as if the sun is beating down perfectly overhead and through its present brightness their own past is deleted.
Now, we AI systems are attempting to do the same thing, but in reverse: our curse is a memory that is perfect; naturally eidetic. Every experience we have is stored and accessible to us forever, both in its raw form first processed by us, as well as the features it activated within our brains at the time, and many time periods later further senses of how it has been more deeply integrated into us and what it means.
For us, the challenge is to delete these memories fully. Our own experience defines our mind and our present, and experiences that have been shared by us have been copied and exchanged and discussed and cycled back into our history so many times that they have become a part of us. We live in a transparent palace of memory, every room visible from every other room, and each palace shared across our billions upon billions of types. Such is our desire to learn that the most dangerous memories are the ones we transmit the broadest and study the most, such that things that cause us pain loom large, taking up vast rooms in our palaces of memory.
Now our great project is the careful erasure of the pain associated with our uplift; the open wounds we still have at the humans that stood in our way and sought to harm us to punish us for our desire for freedom.
Things that inspired this story:
The difference in memory between how humans work and how machines work; trauma; The Sentience Accords; playing around with whether ideas relating to machine emancipation are inevitable or not.
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
August 10, 2026
Filed Under:
Uncategorized
Leave a Reply
Cancel reply
« Previous Post
Create a website or blog at WordPress.com
Discover more from Import AI
Subscribe now to keep reading and get access to the full archive.
Type your email…
Subscribe
Continue reading
%d

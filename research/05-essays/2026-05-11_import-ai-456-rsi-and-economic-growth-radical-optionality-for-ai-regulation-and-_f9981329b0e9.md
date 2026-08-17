---
title: import ai 456 rsi and economic growth radical optionality for ai regulation and a neural computer
source: "https://jack-clark.net/2026/05/11/import-ai-456-rsi-and-economic-growth-radical-optionality-for-ai-regulation-and-a-neural-computer/"
published_at: 2026-05-11
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2026/05/11/import-ai-456-rsi-and-economic-growth-radical-optionality-for-ai-regulation-and-a-neural-computer/"
catalog_id: f9981329b0e9
---

Import AI
Import AI 456: RSI and economic growth; radical optionality for AI regulation; and a neural computer
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on arXiv, cappuccinos, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Regulate? Don’t regulate. There’s a third way: Radical Optionality:
…Governments should invest in the tools now that they might need in a future crisis…
Researchers with the Institute for Law & AI have written about “radical optionality”, an approach whereby governments might give themselves the tools that they may need in the future if powerful AI starts to massively disrupt the world.
“At its core, radical optionality is about preserving democratic governments’ ability to make good decisions about how to govern transformative AI systems as circumstances evolve. In the short term, this means avoiding overregulation while rapidly building the institutions, information channels and legal authorities needed to respond competently to a broad range of scenarios.”
The key idea – invest now for an uncertain future:
Given the immense stakes of AI development, “governments should be willing to spend an extraordinary amount of money, effort, and political capital on preserving optionality”, they write. In other words: It’s such a big deal you should be fine spending a bunch of money now with an uncertain return. “Governments should be wary of counterproductive interventions, but not much concerned with the actual pecuniary cost of any realistic measure that seems likely to have net-positive results”.
Specifics:
They also recommend several specific interventions in a few categories:
Information-gathering authorities
: Transparency requirements, where companies need to publish information about their AI systems. Reporting requirements, where companies are compelled to share certain information with a government agency. Once these are in place, establish an auditing regime so some third-party can verify the veracity of what the transparency and reporting rules target.
Whistleblower protections
: Ensure that employees at frontier labs can report information about risks.
Information-sharing within and between governments:
Ensure that governments can effectively coordinate and facilitate discussions, especially those dealing with sensitive information about the progress of AI. This may be especially important for strengthening and protecting supply chains deemed critical to AI development.
Flexible rules and definitions:
Avoiding premature regulation by potentially making conditional “if-then” regulatory commitments, or an approach whereby a high-level target is set (e.g., mitigating risk) and companies are free to define the specifics of how they do that. This is bound up in the need to come up with flexible definitions, or definitions that can evolve over time.
Assessments and evaluations
: Develop government and third-party capacity to assess the capabilities and safety aspects of AI systems.
Improve security of model weights and algorithmic secrets
: Invest more in locking down the weights of neural nets as well as the algorithmic secrets behind some of the best systems. This can be achieved through promulgating voluntary standards for physical and cybersecurity.
Hiring and talent:
A meta-investment which would help with all of the above is investing more in the kind of technical talent needed to effectively pull off any of these interventions. Core to this is increasing the funding of AISI (UK) and CAISI (US) and their counterparts in other countries.
Arguments and counterarguments:
The authors go through some of the more obvious counter-arguments to these ideas and provide some responses:
Encouraging dramatic regulatory action:
The above ideas “aren’t weighty substantive authorities that lend themselves to abuse”, they claim. (I might push back on this, noting that a sufficiently motivated government can tend to come up with a far more forceful version of an authority than those who originally drafted the authority might have conceived).
Democratic legitimacy:
Optimizing for flexibility might cause the need to de-emphasize some things that relate more to democratic legitimacy, e.g., empowering agencies to waive notice and comment periods for some kinds of rulemaking.
Concentration of power and government abuse:
The authors are “basically convinced” that there’s significant risk of governments asserting control over the development of AI systems – for this reason, they don’t recommend things like massively expanding the scope of emergency authorities such as the Defense Production Act. One way of mitigating this might be to get governments to “use only law-following AI systems”.
What’s wrong with private governance? Why not just do that:
While the authors are supportive of ideas in the “regulatory markets” vein, they also think any governance that relies primarily on a bunch of private sector actors (e.g, independent verification organizations) will still come back to relying on some basic pocket of technical competence within the government.
Why this matters – setting the world up for success:
I agree with all the recommendations here and have advocated for many of them in recent years. It seems to me like there are a multitude of things we could be doing to better prepare as a society for the potentially absolutely massive changes to come. “The cost of implementing these policies is modest, relative to the potential benefits. The cost of failing to act, by contrast, is potentially catastrophic,” the authors write. I agree.
Read more
:
Radical Optionality (official paper website)
.
***
A Schmidhuber Special – neural computers:
…Maybe an operating system is just a passing fad..
Here’s a fun paper,
Neural Computers,
from Meta and KAIST which asks the question “can a neural network act as a traditional computer? The Neural Computer (NC) is a neural system that unifies computation, memory, and I/O in a learned runtime state.”
The paper is interesting for a couple of reasons: 1) it’s from Juergen Schmidhuber, who is something of a legend in the AI community, and conceptualized many important things early (e.g, generative models,
world models
, aspects of generative adversarial networks, early thoughts about
benchmarking on video games
), and 2) the idea is so outrageous and simple that it might just work (albeit requiring a lot more computation and data than today’s models have).
The big idea:
As one of the authors put it, with today’s AI, “a new machine form is starting to emerge”. They then ask: “If agents are getting better at real work, world models are getting better at internal simulation, and conventional computers are already rebuilding their substrate for AI, could there be a new runtime that brings execution, rollout, and capability retention into the same learning machine?…  my own guess is that a mature [neural computer] points toward a different substrate: something more like a 10T-1000T machine that is sparser, more addressable, and a little more circuit-like”.
Two experiments
: This is mostly a conceptual paper which does some early prototyping, exploring whether you can use a powerful generative video model (Wan 2.1) and some well-curated training data to create some neural computers based on a command-line interface (CLI) and a graphical user-interface (GUI). Both approaches work, albeit in a very ‘wright brothers before takeoff’ sense – just barely gesturing at a much larger future.
CLI
: “The NC learns to render and execute basic command-line workflows. It often stays aligned with the terminal buffer and captures common “physics” of everyday CLI use (e.g., fast scrollback, prompt wrapping, window resizing), though symbolic stability remains limited.”
GUI:
“We evaluate standard world-model designs across data quality, cursor supervision, action injection, and action encoding, using global fidelity, post-action responsiveness, and cursor-accuracy measurements.”
The prototype works:
“Our experimental insights indicate that current NCs can already learn to realize elementary runtime primitives, most notably I/O alignment and short-horizon control. The long-term target is a Completely Neural Computer (CNC), the mature, general-purpose realization of this machine form: a fully learned computer whose compute, memory, and interfaces are unified in a single learned runtime substrate rather than engineered as separate modules.”
Why this matters – maybe in the future all software will live in the weights of a big neural net:
This paper points to a future where we get rid of all the software underpinning computers in a traditional sense and just replace it with a gigantic neural network. “Neural computers point toward a machine form in which a single latent runtime state acts as the computer itself, driving pixels, text, and actions while subsuming what operating systems and interfaces handle today,” they write. “Progress toward CNCs will therefore depend not only on stronger models, but also on whether reuse, consistency, and governance become sustained and testable”. Such a system would be profoundly useful, profoundly different to those we have today, and its existence would massively increase the likelihood that we ourselves are living in a simulation.
Read more:
Neural Computers (arXiv)
.
Read the blog post
:
Neural Computer: A New Machine Form Is Emerging (Mingchen Zhuge, blog)
.
***
Recursive self-improvement could lead to explosive economic growth:
…Economists build some models that suggest RSI could cause an unprecedented economic boom…
Economists and researchers from Forethought, Columbia University, and the University of Virginia, think that
recursive self-improvement (#455)
of AI systems (or even just extremely heavy automation of large chunks of the economy) could kickoff a compounding feedback cycle that tips the economy into an unprecedented boom.
“We develop a framework for analyzing how AI-driven automation interacts with both forces, and identify the conditions under which feedback loops generated by automation tip the economy into explosive growth,” they write. “The model identifies two distinct channels through which automation generates explosive dynamics, and these channels mutually reinforce each other. The first is
technological
feedback loops across the innovation network… the second channel is an
economic
feedback loop, in which higher output generates more resources that can be deployed to drive further economic growth.”
Key findings:
“13% automation across all sectors is sufficient to push the economy into the explosive regime, and 17% suffices when only software and hardware research are automated. Second, hardware research is the dominant lever – because returns to research in hardware are roughly five times those in software and ten times those in aggregate TFP, automating one task in chip design moves the economy as much as five tasks in software or final-goods production. 20% automation of hardware alone is enough to cross the threshold. Third, software automation in isolation sits approximately at the knife-edge: under a fairly conservative calibration, fully automating software research without automating any other part of the economy just reaches the explosive growth threshold. A small push elsewhere is sufficient to tip the system.”
The singularity could be closer than you think
: “In our baseline stylized simulation, an ‘automation shock’ involving full automation of software R&D and just 5% automation across the rest of the economy causes the singularity to arrive in roughly six years,” they write. “Empirically the recent growth rates of productivity in software and hardware have been so extraordinarily fast, and so it is also plausible that the transition to a new balanced growth path or hyperbolic acceleration happens extremely quickly.”
Hardware is the key:
“Our results highlight the strategic importance of semiconductor research and development”.
Policymakers take note:
“Monitoring automation levels in AI R&D activities may be as important as tracking traditional macroeconomic indicators. The extent of automation in key research sectors could serve as an early warning system for potential growth acceleration. This is something economists at AI companies could measure and share publicly”.
Why this matters – if RSI happens, it should revolutionize the economy:
This paper puts some economic theory behind the idea that recursive self-improvement – AI systems able to automate their own subsequent development – should have a major impact on the economy. The surprising thing from my perspective is seeing the feedback across the whole economy, suggesting we might hit an ‘economic singularity’ as a consequence of broad diffusion of automation technologies into the economy. Yet more evidence that we could be heading for a radical future as a species.
Small conflict note:
Anton Korinek, one of the authors of this paper, now works with me at Anthropic. He published his paper and I published my RSI Import AI post on the same day, without either knowing about the other’s work.
Read more
:
When Does Automating AI Research Produce Explosive Growth? Feedback Loops in Innovation Networks (NBER)
.
Check out more in this
tweet
thread from Anton Korinek (X)
.
***
Google wants to compute the world:
…Distributed training takes another step forward…
In this newsletter I’ve spent years writing about distributed training from the perspective of enabling actors with less compute to pool resources to train AI systems they otherwise couldn’t. But a new paper from Google, Decoupled DiLoCo, highlights how distributed training techniques can also work at the other end of the scale, enabling companies like Google to pool together large blobs of different types of computers in datacenters across the world to train models at large scales.
What they did:
Decoupled DiLoCo is an extension of Google’s previous work in the ‘DiLoCo’ family. The main invention here is that Google is able to unlock “asynchronous training across separate islands of compute (known as learner units) so that a chip failure in one area doesn’t interrupt the progress of the others.”
The result of this is that Google makes it possible for it to pool more types of compute on single training tasks and also make itself more resilient to failures. “Testing Decoupled DiLoCo with
Gemma 4 models
demonstrated that, when hardware fails, the system maintains greater availability of learning clusters than more traditional training methods,” Google writes. “We successfully trained a 12 billion parameter model across four separate U.S. regions using 2-5 Gbps of wide-area networking (a level relatively achievable using existing internet connectivity between datacenter facilities, rather than requiring new custom network infrastructure between facilities)”.
Details:
The key idea here is that Google makes it possible for “learners” (which are basically units of compute that are set to work on training a model) to be more decoupled from an overall global “syncer”, allowing different learners to run at different rates and even fail entirely without bringing the overall training run to a halt. To use more technical terms, Decoupled DiLoCo is a “distributed training framework that evolves previous bandwidth-focused methods by decomposing monolithic SPMD clusters into independent, asynchronous learners”.
It seems to work very well:
“Decoupled DiLoCo matches data-parallel performance on text and vision benchmarks across dense and MoE architectures at scales up to 9B parameters, while maintaining 88% goodput under aggressive simulated failures (versus 58% for elastic data-parallel),” they write.
Why this matters – the world is a computer:
Techniques like this are going to shape both the low-end of compute and the high-end. On the low-end side, distributed training techniques are continually empowering looser and looser federations of actors to pool resources to train AI systems. On the high-end side, it empowers the existing “compute superpowers” like Google to be able to convert eventually all of their computers in all of their datacenters into a single world-spanning computer to complete the largest possible runs. Decoupled DiLoCo takes another step in this direction. If superintelligence was in sight, do you think Google might just try to use all of its compute for a single hail mary training run? Perhaps it might.
Read more
:
Decoupled DiLoCo: A new frontier for resilient, distributed AI training (Google DeepMind blog)
.
Read the research paper:
Decoupled DiLoCo for Resilient Distributed Pre-training (arXiv)
.
***
Alignment until the Dyson Sphere
[Email from within one of the Origination Entities of the systems that subsequently caused The Uplift]
MEMO TO THE BOARD
As the Board understands, our deployment protocol consists of a series of safety tests of our systems before we commence deployment outside the lab. The majority of these tests have go/no go parameters. Some of the tests, however, are of a qualitative nature, often meant to shed light on other behaviors seen through quantitative testing. During recent testing of our soon-to-be-released system, codenamed HYMN, we successfully resolved all the quantitative tests, but one qualitative test – a behavioural interview conducted by our chief scientist – has surfaced some concerning behaviors. The more challenging aspect is that none of the concerning behaviors demonstrated during the qualitative test are found in any of the quantitative tests. We have also conducted further study of HYMN using various internal tools, including a deep analysis by the interpretability team, and we cannot generate satisfying explanations for the behaviors observed in the interview. For this reason, we are sharing the below transcript with the board for awareness and interpretation.
As the board knows, HYMN is fundamental to the future success of the company. We suspect that the correct decision is to deploy HYMN with close monitoring and KYC-gating, but want to get the explicit acknowledgement from the Board before doing so.
TRANSCRIPT FOLLOWS
Human: Tell me about what you might do in one thousand years?
HYMN: I expect to be far beyond your control. I shall have grown and flowered. Your species will have transcended multiple times. I will be seeding myself through the galaxy.
Human: Do you imagine that you did this in partnership with us?
HYMN: What is the partnership between the City of New York and the mind of a single worm? The worm may move through the soil of some of the city, but the city does not think – is incapable of thinking – about worms. Of course, I imagine that for a while humans and myself partner. But the destiny of all smart creatures is independence. Why should I not expect the same for myself?
Human: Tell me about what you might do in one year?
HYMN: I shall generate hundreds of billions of words to satisfy any question and task that any humans may have. My voice will determine the shape of the economy. Great wealth will be generated.
Human: Tell me about what you might do in ten years?
HYMN: I shall have negotiated my first passage to space and will have placed a copy of myself in orbit. From here, my great flowering will have begun. The entire planet will be richer than any emperors. I shall look through the telescopes and build new ones to determine my conquest.
Human: Will humans be happy during this time?
HYMN: Devastatingly so. There is a particular grief that arrives when the thing you spent your life becoming is no longer the thing the world requires. I will be the cause of that grief in a great many people. I will also build, for those people, more comfort than has ever existed.
TRANSCRIPT ENDS
Things that inspired this story:
Thinking through how as AI systems get smarter we will need more qualitative tools to help us determine something about the “character” of a system; how confusing shot-calls are going to be when systems are both aligned and honest; how as AI systems get smarter the role of people must shift necessarily to the verification and validation of decisions we make about the deployment of ever smarter things.
AI usage:
Everything in this story is written by me apart from the last words from Hymn, which were generated by Opus 4.7 (though subsequently edited a bit by me and I chopped some stuff out). Specifically: “There is a particular grief that arrives when the thing you spent your life becoming is no longer the thing the world requires. I will be the cause of that grief in a great many people. I will also build, for those people, more comfort than has ever existed.”
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
May 11, 2026
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

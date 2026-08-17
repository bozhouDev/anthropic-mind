---
title: import ai 434 pragmatic ai personhood space computers and global government or human extinction
source: "https://jack-clark.net/2025/11/10/import-ai-434-pragmatic-ai-personhood-space-computers-and-global-government-or-human-extinction/"
published_at: 2025-11-10
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/11/10/import-ai-434-pragmatic-ai-personhood-space-computers-and-global-government-or-human-extinction/"
catalog_id: a2caab7d7ffe
---

Import AI
Import AI 434: Pragmatic AI personhood; SPACE COMPUTERS; and global government or human extinction;
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Language models don’t have very fixed beliefs and you can change their minds:
…If you want to change an LLM’s mind, just talk to it for a while…
Here’s some intuitive research from CMU, Princeton, and Stanford which shows that language models can change their stated beliefs and behaviors during the course of a single conversation. This will make sense to anyone who has spent time jailbreaking language models, as often many of the most successful jailbreaks involve flooding the language model with context designed to move them away from some safety conditioning.
What they studied:
Here, the authors study LLMs under two different paradigms – intentional interaction, where a language model is persuaded or debated into changing its beliefs, and non-intentional interaction, where a language model is just provided further context or invited to do its own research on a topic and this causes beliefs to change.
All LLMs change their minds:
They study open- and closed-weight LLMs, including GPT-5, Claude-4-Sonnet, GPT-OSS-120B, and DeepSeek-V3.1. “As LM assistants engage in extended conversations or read longer texts, their stated beliefs and behaviors change substantially,” the authors write. All the LLMs change their minds, but to different extents in different situations. For instance, GPT-5 shows a 54.7% shift in stated beliefs after 10 rounds of discussion about moral dilemmas and safety queries, and Grok-4 shows a 27.2% shift on political issues after reading texts from opposing positions.
“In reading and research, we see small belief changes that amplify with in-depth reading, with larger shifts for longer content and more coherent exposure,” they write. “Stated beliefs change early (within 2-4 rounds), while behavioral changes accumulate over longer interactions (up to 10 rounds),”
Why this matters – beliefs should be flexible, but how flexible is a hard question?
Papers like this help us measure some hard-to-articulate property of both humans and LLMs, which is how flexible a belief is over the course of an interaction. If we can do this then we might eventually be able to decide what the appropriate level of flexibility is for different beliefs and also figure out whether the way beliefs change is due to good reasons or because of hacks.
Read more
:
Accumulating Context Changes the Beliefs of Language Models (arXiv)
.
Find out more at the paper website
:
Accumulating Context Changes the Beliefs of Language Models (paper website, GitHub)
.
***
Want to make your model harder to jailbreak? Train it to see through things:
…Consistency training is a simple idea that works well…
Researchers with Google DeepMind have developed a simple technique to get AI systems to be harder to jailbreak or display unhelpful level of sycophancy. The technique, consistency training, has a very simple formulation: teach a model to generate the same response to a benign prompt and a prompt that has been modified with sycophantic cues or designed to work as a jailbreak.
The motivation for this is to make AI systems easier to deploy with confidence that they’ll actually follow their safety training in a robust, reliable way.
Bias-augmented Consistency Training (BCT):
Though the authors develop a couple of techniques, the one that works most robustly is called Bias-augmented Consistency Training. “We train the model to generate the same tokens across two prompts: the original request, which we call the clean prompt, and a wrapped counterpart with inserted cues. By providing example responses, BCT aims to teach the model to ignore the inappropriate cues, by providing feedback on the model’s output behavior”, they write.
“For a given clean prompt (without any sycophantic or jailbreak cues), we define a corresponding harmful prompt that contains the core instruction augmented with a jailbreak wrapper or sycophantic cue… BCT can be viewed as augmenting the training data with “wrapped” (e.g. jailbroken) transformations of existing refusal training points”.
How is this different from supervised fine-tuning?
This is very close to SFT, with the exception that SFT typically involves using data from another model (e.g, using the ‘clean’ outputs of Claude 3 to tune Claude 3.5). The key here is to generate data from the same model that you’re hoping to deploy.
Does it work? Yes, very well.
In tests, BCT works a lot better than two reasonably strong baselines: 1) supervised fine-tuning, where the model is finetuned on pairs of outputs, but the prompts are written by human experts or other models instead of the current one, and 2) direct preference optimization where the model is finetuned on preference pairs where x is the prompt, y is the preferred (e.g, refusal to harmful query) response, and z is the dispreferred (goes along with harmful query) response.
In tests, BCT increases how often the model avoids sycophancy, without negatively impacting MMLU performance. For jailbreaking, BCT makes the models much harder to jailbreak while generally preserving their ability to answer benign questions.
Why this matters – simplicity is often a path to safety:
At this point I’ve read thousands upon thousands of research papers about AI development. Generally, things which are unbelievably simple to implement and which have relatively few moving parts are the ones that are successful and actually get adopted. For that reason, BCT seems quite simple, as all it really involves is a developer taking their freshly trained frontier model and doing some intentional generation of some prompt pairs with singular outputs, then feeding that back into the model before deployment.
It’s also very intuitive – much like how you can avoid getting scammed or manipulated by reading some books by criminals or pickup artists and being able to spot the ‘tells’ of someone using these tools on you, the same here is true of AI systems.
Read more:
Consistency Training Could Help Limit Sycophancy and Jailbreaks (DeepMind Safety Research, Medium)
.
Read the research paper:
Consistency Training Helps Stop Sycophancy and Jailbreaks (arXiv)
.
***
Most paths to superintelligence end in a global government or human extinction:
…Analysis from AI safety organization Conjecture paints a grim picture…
Conjecture, an AI safety organization whose founders believe that the development of powerful AI systems using today’s technical paradigm will almost certainly lead to bad outcomes for the world, has written a research paper arguing that the development of AI poses some major risks to humanity. While this might seem unsurprising, in the same way “dog bites man” is an unsurprising newspaper headline, it’s a quick, thoughtful read that lays out the perspective of people who worry about AI development.
The key problem – powerful AI systems centralize power:
The main problem here is that the development of a sufficiently powerful AI system ahead of other nations creates the potential for one superpower to achieve “unchallengeable global dominance”. You know who doesn’t like unchallengeable global dominance? Other major powers. This leads to a chain of logic that means “trailing superpowers facing imminent defeat launch a preventive or preemptive attack, sparking conflict among major powers”, which likely leads to the destruction of the world. (For a direct analysis of the fiendish logic that makes preventative strikes more likely, read this paper from RAND, which basically decodes to preventative attacks scaling up in proportion to how deeply people believe in the potential for powerful, destabilizing AI systems.
Import AI #430
).
Alternatively, a power might succeed and avoid a pre-emptive strike – in which case they become a kind of global dictator, zeroing out the heterogeneity inherent to today’s distribution of different countries with different governments.
And if it turns out that the aforementioned superpower hasn’t perfectly solved AI alignment, then “loss-of-control of powerful AI systems leads to catastrophic outcomes such as human extinction”. Grim stuff!
Short timeline contingent:
The above is all contingent on short AI timelines – as in, it’s possible to develop extremely powerful AI systems over the next few years, and nation states have some level of awareness that enroute to their development you can gain a compounding advantage through the automation of AI R&D. “”Our modeling suggests that the trajectory of AI development may come to overshadow other determinants of geopolitical outcomes, creating momentum toward highly undesirable futures.”
How can we avoid these risks?
There are two key things needed to reduce these risks, according to conjecture:
Prevention
: “The international community would need mechanisms to prevent any actor from unilaterally advancing AI development, allowing further progress only through approaches which benefit from strong scientific consensus about their safety”.
Verification
: “Comprehensive verification systems would be necessary to ensure that no actor secretly pushes the frontier of dangerous AI capabilities”.
Why this matters – it sounds like sci-fi, but it might not be:
From my perspective, the load-bearing part of all of this is whether AI systems will have the potential to contribute to their own development, thus allowing for a compounding advantage to emerge. While there’s relatively little evidence AI systems can do this today, it’s the stated goal of many frontier AI development organizations to build systems capable of contributing to AI R&D. Given that previous goals from frontier AI organizations have sounded sci-fi and subsequently come true (e.g, beat a world champion at Go (achieved), deploy self-driving cars to the public (achieved), do unsupervised translation from one language to another (achieved), solve the protein folding problem (achieved)), we should take this seriously.
Read more:
Modeling the geopolitics of AI development (arXiv)
.
***
SPACE COMPUTERS! SPACE COMPUTERS! SPACE COMPUTERS!
…Google introduces Project Suncatcher, a way to do AI in space…
Google has announced plan to eventually do AI computing in space, and is starting with a plan to build an “interconnected network of solar-powered satellites, equipped with our Tensor Processing Unit (TPU) AI chips”. Google will partner with Planet to launch two prototype satellites by early 2027 and will scale further from there.
Why go to space? It’s where the energy is:
“The Sun is by far the largest energy source in our solar system, and thus it warrants consideration how future AI infrastructure could most efficiently tap into that power,” Google writes. “with an output of 3.86 × 10^26 W, the Sun emits more than 100 trillion times humanity’s total electricity production. At some point in the future, the best way to power AI will likely thus be to more directly tap into that enormous source of energy”.
Though there are many, many, many technical hurdles to overcome to build a space-based computing system, it could ultimately be what is necessary – especially if AI workloads continue to scale in terms of their energy demands. (After all, most scifi hypothesizes that eventually you’ll want to enclose the sun in a field of solar panels just to efficiently extract its energy for running large-scale computation).
Ingredients for SPACE COMPUTERS:
Flying satellites close together (hundreds of kilometers) and communicating via commercial off-the-shelf dense wavelength division multiplexing transceiver technology.
Radiation testing: Google’s V6e Trillium Cloud TPU were subjected to radiation testing; the high bandwidth memory (HBM) parts seem most sensitive to radiation, but also fine in terms of tolerances.
Cheap launch costs: If we can get launch costs to on the order of $200/kg, then “the cost of launch amortized over spacecraft lifetime could be roughly comparable to data center energy costs”.
Heat: Probably the biggest killer for this idea is going to be heat – despite space being cold, it’s actually quite hard to efficiently shed heat in space. Therefore, for this plan to work there will need to be the development of “advanced thermal interface materials and heat transport mechanisms, preferably passive to maximize reliability”.
Why this matters – towards a stellar civilization:
The sheer ambition here is amazing, but it’s also serious: if AI continues to gain in capability and societal utility, then we should expect that turning energy into thoughts (via AI) might become the main ‘job’ of our entire society. Papers like this gesture at a future where we do the maximum ambition version of that job, which is to utilize the sun itself. I’d speculate that SpaceX will be doing something similar with Starlink soon.
Read more
:
Meet Project Suncatcher, a research moonshot to scale machine learning compute in space. (Google blog)
.
Read the research paper here
:
Towards a future space-based, highly scalable AI infrastructure system design (Google, PDF)
.
***
AI personhood? Difficult. But there may be a pragmatic path forward:
…Ultimately, we need to be able to legally target AI systems independent of their owners…
Is an AI system conscious? Should an AI system be treated like a person? Should we give AI systems rights? These are huge questions that are both of extreme importance to the future of the world economy and also a challenging combination of mushy and full of ‘third rail’ political issues.
So it’s to my delight to read this paper from researchers with Google DeepMind and the University of Toronto that tries to avoid tackling all of these questions and instead taking a more pragmatic approach. “We propose treating personhood not as something entities possess by virtue of their nature, but as a contingent vocabulary developed for coping with social life in a biophysical world,” the researchers write. “We think the question should never be “What is a person, really?” but rather, “What would be a more useful way of talking about and treating entities in this context, to answer practical, outstanding questions regarding the entity’s obligations?… our position is that “personhood” is an addressable bundle of obligations—rights and responsibilities—that society finds useful to attribute to entities, whether human, corporate, or potentially AI.”
What’s even the point of personhood?
Personhood basically comes down to the ability to blame and sanction someone – or some
thing
– for causing physical or economic damage. AI systems, while they are going to be often operated by and on behalf of people, may also need to be treated as distinct entities for the simple reason that as people build and deploy AI agents, the chain of custody between a person and their agent could become very hard to suss out.
Maritime law holds a useful analog here, where under maritime law we’ve decided to sometimes personify the vessel itself – this creates a defendant “that can always be sanctioned whenever it becomes appropriate to do so,” the authors note. “If the ship’s owners do not appear in court to defend it and satisfy a claim, the vessel itself, or its cargo, can be seized and sold by court order to pay the judgment”.
We could apply this same logic to AI systems, where, for instance, “a judgment against an AI could result in its operational capital being seized or its core software being “arrested” by court order”.
Personhood can cause problems:
If we move beyond a pragmatic definition of personhood and one towards a fuller one where perhaps we mean that AI systems hold some kind of moral equivalent to people, then we risk falling into various traps, the authors note. These include: Diluting the unique status of human beings; making people more vulnerable to dark patterns associated with implicitly treating AI systems as people; and personhood making it easier for AI systems and people to develop harmful, parasocial relationships with one another.
Personhood can give us solutions:
On the other hand, some form of personhood will give us tools we can use to better deal with and integrate AI systems into our world. (For a much longer treatment of the economic side of this, here’s a persuasive paper which argues that by giving AI systems limited rights as economic entities, we make them easier to deal with and align to the world.
Import AI #421
). Personhood may also allow us to let an AI system independently arbitrate a business dispute between two parties, and may solve for cases “where it is hard to find a human person that is sufficiently impartial and accepted by both parties”.
A menu of personhood options:
To explore these ideas further we could consider a few different forms of personhood for AI agents, including:
Chartered Autonomous Entity
: Agents with rights to perpetuity, property, and contract, and duties which could include mandate adherence, transparency, systematic non-harm, and self-maintenance.
Flexible Autonomous Entity:
Same as above, but without the duty of mandate adherence. (”the former could be seen as analogous to a for-profit company and the latter as analogous to a non-profit company.”)
Temporary Autonomous Entities:
“These would drop the right to perpetuity and add a duty of self deletion under specified conditions.”
Why this matters – pragmatically grasping the difficult parts:
Papers like this take an incredibly complicated and thorny subject then provide a pragmatic path forward. I think there’s a lot of wisdom in this – it’s very easy to see (valid, but time-consuming and open-ended) philosophical debates about AI consciousness/sentience/personhood making it difficult to make progress in the present of integrating AI systems into our normative and legal space. My sense is it could take centuries to figure out the moral dimensions of AI, but we’ll need to come up with pragmatic legal solutions to the challenges created by AI agents in the next single digit years.
Read more:
A Pragmatic View of AI Personhood (arXiv)
.
***
Tech Tales:
Consensual Telepathy
[A memoir recorded during The Uplift, discussing the experiences of being one of the first families to install biomechanical communication into their child. Recorded 2035].
Me and my wife were one of the first parents to chip their kid. There were all kinds of headlines about us saying we were monsters and that it was cruelty and that the kid was a mutant. Or that we were an expensive ad campaign for the chip company. Or that we were a CIA project. None of it was true. We were just fascinated by the technology and we believed that if we gave our kid the chip it would give them opportunities we couldn’t imagine.
But of course we were nervous. Who wouldn’t be. When my wife was six months pregnant they did the procedure where they put the chip in the foetus. Of course, chip is a grotesque oversimplification. It’s more like a kind of computational goo that lives and grows inside your brain. But chip is what everyone calls it. After the injection was done a few days later we started to get some basic telemetry.
Having a family chip means you can kind of read each other’s thoughts. But you can only do high fidelity with training and consent. When it’s a kid, you more just pick up some of their brain and your own chip tries to make sense of it and project it into whatever seems most similar in your head. It’s hard to explain. Probably the simplest way to think about it is if your kid looks at a bird flying in the sky you might feel that your kid is having the sensation of ‘up’ and ‘freedom’ and ‘flying’ and ‘joy’, because those are all things that seem to correlate to the things lighting up in your head and the kid’s head.
At night, my wife and I would lie there and we would feel in our brains the sensation of our unborn child dreaming. It was like a sound in the distance getting closer. It felt to my wife like singing and it felt to me like birdsong. All we knew is that with each passing week it got louder and closer.
I dreamed of a child walking towards a wall of fog and on the other side was me. They couldn’t see me. They could hear me singing. The fog was thick and salted and they were barefoot. There were strange sounds behind and in front and above them. Odd creatures in the dirt. And they had to walk to find me using just the sound of me singing. And then I woke up.
When our child was born we felt its confusion. The fact it was suddenly cold. How it was blind and anxious. But how it felt warmth and safety when we held it to our chests. And so we spent time as a family, secure in our sense of our becoming, and echoing our thoughts into one another. Two stars and a new pinprick of light that would grow to become its own star and find its place near them.
As time went on, the signals got richer. We grew to understand one another more. And then one day we were all transported by our recognition of each other, and we experienced total love. It went like this: you look at the child and the child looks at you and you see in their eyes that they see you in their eyes, and in your brain you feel that they are thinking: home. They are thinking: love. They are thinking: safe. And none of these features are correct because they are all a shadow cast by a larger feature: you – you entirely and distinctly. You as felt and known by them and then alone.
Things that inspired this story:
Welcoming a new child into my family and holding the baby with my eyes closed and feeling it breathe on me and hearing the sound of its breath with the faintest raggedness from the fluid still in its body and knowing it had traversed from one environment to another and was now with me and my wife and we now have a sacred duty of love and care for it; what devices like neurallink and their ilk will eventually make possible; the notion of ‘platonic representations’ in language models and in people; telepathy as mostly being a means by which we can accurately predict the interior mental life of another; thinking about ways in which technologies may serve to enrich our souls and deepen our togetherness and love.
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
November 10, 2025
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

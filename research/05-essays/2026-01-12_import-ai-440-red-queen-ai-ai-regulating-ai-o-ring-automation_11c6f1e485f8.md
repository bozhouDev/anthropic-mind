---
title: import ai 440 red queen ai ai regulating ai o ring automation
source: "https://jack-clark.net/2026/01/12/import-ai-440-red-queen-ai-ai-regulating-ai-o-ring-automation/"
published_at: 2026-01-12
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2026/01/12/import-ai-440-red-queen-ai-ai-regulating-ai-o-ring-automation/"
catalog_id: 11c6f1e485f8
---

Import AI
Import AI 440: Red queen AI; AI regulating AI; o-ring automation
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on arXiv and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
To understand the future of the world, stick AI systems in a petri dish:
…Evolving LLMs to attack other LLMs…
Researchers with Japanese AI startup Sakana have looked at what happens when they evolve LLM-based agents to fight against one another in a competitive programming game from the 1980s called Core War. The results show that “large language models (LLMs) drive an adversarial evolutionary arms race in this domain, where programs continuously adapt to defeat a growing history of opponents rather than a static benchmark”. This research approach gestures both at ways researchers might better study how LLM-dominated niches in the economy or national security world might unfold, and also hints at the strange AI world we’re heading into.
What is Core War?
“Core War is a competitive programming game played out in a shared block of computer memory, called the “Core,” where two or more assembly programs fight for survival”, Sakana writes. “Each program, known as a “warrior”, is written in an assembly language called Redcode. These programs are tasked with crashing their competitors while keeping their own processes alive. The simulation runs by alternating between the programs, executing one instruction at a time. A warrior “attacks” by writing invalid instructions (DAT commands) into the memory slots occupied by opponents, causing them to crash upon execution.”
DRQ:
To evolve their programs, the authors use a technique they call Digital Red Queen. “DRQ uses MAP-Elites, a quality-diversity algorithm, to optimize warriors within each round, preventing diversity collapse during search. By playing against all previous round champions, DRQ avoids cyclic adaptations across rounds, consistent with techniques in prior work”, they write. “We find that as DRQ is run for many rounds, warriors gradually become more generally robust, as measured by their performance against unseen human-designed warriors.”
Each warrior calls out to GPT-4 mini (”preliminary experiments did not show significant performance increase with larger models), and is given a prompt which describes the Core War environment as well as a manual for the Redcode assembly language. “To generate a new warrior, the LLM is given a user prompt instructing it to produce a novel Redcode program. To mutate an existing warrior, the LLM is provided with the original program and instructed to modify it in ways that could improve performance.”
Evolution works: Unsurprisingly,
evolving agents is very effective:
A one-shot warrior defeats 1.7% of human warriors.
Best-of-N sampling produces a set of warriors that can defeat 22.1% of human warriors
“Evolutionary optimization against each human warrior generates a specialized warrior for every opponent; this set can collectively defeat 89.1% of human warriors and defeat or tie 96.3%.”
Why this matters – where Core Wars goes, so does the world:
The world is going to look a lot like Core Wars – millions of AI agents will be competing against one another in a variety of domains, ranging from cybersecurity to economics, and will be optimizing themselves in relation to achieving certain competitive criteria. The result will be sustained, broad evolution of AI systems and the software harnesses and tooling they use to get stuff done. This means that along with human developers and potential AI-designed improvements, we’ll also see AI systems improve from this kind of broad competitive pressure.
“The cybersecurity arms race between offense and defense is well underway,” Sakana writes. “Studying these adversarial dynamics in an artificial testbed like Core War offers critical insights into how such races might unfold and the kinds of strategies that may emerge.”
Read the blog post
:
Digital Red Queen: Adversarial Program Evolution in Core War with LLMs (Sakana)
.
Find out more
at the
official website (Sakana)
.
Read the research paper:
Digital Red Queen: Adversarial Program Evolution in Core War with LLMs (arXiv)
.
***
Michael Burry, Dwarkesh Patel, Patrick McKenzie, and yours truly argued back and forth in a Google Doc about AI:
…Blogging 2.0 is great!…
Fellow substackers Michael, Dwarkesh, and Patrick and myself recently got in a Google Doc and hashed out some thoughts about AI, AI and the economy, and how the future might unfold. While writing this the main thought going through my head was that if AI is eventually able to build AI, then pretty much every economic model breaks quickly (as do many other things in the world). This makes it innately hard to reason about the future of AI and means people like me are walking around with two worlds in their head – “normal” worlds where GDP grows a bit more due to AI and everything speeds up a little, and “AI R&D” worlds where it’s like a chunk of the economy undergoes massive relativistic acceleration and time dilation effects relative to everything else, almost like a part of our world accelerates to a fraction of light speed and we maintain a communication channel.
I love this discussion format
and also
did a recent debate about what AI might mean for workers
with American Compass with a similar Google Doc thunderdome structure. Thanks to Substack for putting this together, and please reach out if you would like me to hop in a Google Doc and do some cheerful debate with interesting people!
Read more:
The AI revolution is here. Will the economy survive the transition? (The Substack Post)
.
***
AI progress should make it cheaper and easier to regulate AI systems:
…Automated compliance as a path to smarter, more targeted AI regulation…
Researchers with the Institute for Law and AI believe that as AI systems get smarter they will increasingly be able to write and enforce the regulations for AI systems. The crux of their argument is that a sufficiently advanced AI system should be able to automate compliance with some regulations that are applied to AI systems and the companies that develop them.
This makes intuitive sense – a lot of product policy comes down to forms of transparency and labeling, where companies are asked to provide some information to the public and/or regulators about the things they’re deploying into the world. This sort of labeling work is the kind of thing AI systems can easily do. Therefore, the authors argue, “AI policy discourse should internalize the fact that AI progress implies reduced compliance costs, all else equal, due to automated compliance.”
The key idea? Automatability triggers
: The core idea in this proposal is we can write regulations today but ensure they only come into force once a technical AI system exists which makes compliance with these regulations effective, cheap, and fast.
If then policy:
These so-called ‘automatability triggers’, could create what I’d term If Then Policy –
if
an automated form of compliance and assessment exists,
then
cause the regulation to come into force. The authors give an example here of a bill which would create significant punishments for people that, without authorization, export large-scale AI systems. But the bill would be operationalized through a trigger condition that could be written as follows:
“The requirements of this Act will only come into effect [one month] after the date when the [Secretary of Commerce], in their reasonable discretion, determines that there exists an automated system that:
(a) can determine whether a neural network is covered by this Act;
(b) when determining whether a neural network is covered by this Act, has a false positive rate not exceeding [1%] and false negative rate not exceeding [1%];
(c) is generally available to all firms subject to this Act on fair, reasonable, and nondiscriminatory terms, with a price per model evaluation not exceeding [$10,000]; and,
(d) produces an easily interpretable summary of its analysis for additional human review.”
After automated compliance comes automated governance:
By building regulatory compliance AI systems, people will build the necessary prerequisites for systems of regulatory governance – systems which could both provide analytical data about how a proposed regulation might impact a company (for instance, by using classifiers built for regulatory compliance to figure out if a new regulation might apply to a company), to, more ambitiously, drafting and analyzing new regulatory rules and figuring out how they might apply to themselves.
Even more farther afield, once compliance-automating AI systems get deployed alongside governance-automating AI systems, the two could talk to one another: “Compliance-automating AI systems could also request guidance from regulatory AI systems, who could review and respond to the request nearly instantaneously”.
Why this matters – for AI to go well, we need AI to police AI:
AI systems are on a trajectory to think better and faster than humans. Along with this, AI systems are going to take many, many, many consequential actions, often at such a rate that no human or team of humans could hope to analyze each action. The only way through this is a combination of creating appropriate hard laws that apply to AI and delineate what actions are unacceptable, and for everything else creating fast-acting and adaptive automated systems to regulate and police the myriad gray areas of the AI universe.
Read more
:
Automated Compliance and the Regulation of AI (Institute for Law & AI)
.
***
Massively powerful AI might make human labor more valuable – as long as the AI is crap at one part of every job:
…O-Ring Automation and the fact that while jobs may go away, but people remain…
The common understanding of AI and automation is that AI can perfectly substitute for people – once an AI can do a task, the human labor related to that task goes away. This is broadly accurate. But, per a new research paper from the University of Toronto, it misses the larger picture, which is that while
jobs may go away, people don’t
. If you make part of a production process massively more efficient and/or automated via AI, then people will shift their labor to the parts of the task which can’t be automated – often raising the value of the human.
This so-called “O-ring production function” views jobs as being composed of many distinct tasks, and one where “a change in the quality of one task scales the marginal value of quality in every other task.” This means that “automating a task not only replaces the quality of that task; it also changes the worker’s time allocation and thus the quality of all remaining manual tasks.”
When stuff gets automated, humans can earn more:
In a toy model of a firm, the researchers explore this o-ring dynamic, where as different parts of a job gets automated, labor and the value associated with it shifts elsewhere. Note, this only holds under ‘partial automation’ where at least one task linked to an overall job is one where humans have a comparative advantage. Under this model, “labour income need not fall under partial automation. When not all tasks are automated, increases in automation quality can raise labour income because automation scales the value of the remaining labour bottlenecks,” they write. “When only a few manual tasks remain, each manual task receives a large share of time and can be performed at high quality. This creates a rising “barrier” to automating the last tasks”.
Jobs go away, but humans don’t:
Another way to put this is, when a task gets automated it’s not like the company in question suddenly fires all the people doing that job. Consider ATMs and banking – yes, the ‘job’ of doling out cash rapidly transitioned from people to machines, but it’s not like the company fired all tellers – rather, the companies and the tellers transitioned the work to something else: “Under a separable task model, this [widespread deployment of ATMs doing cash-handling tasks] should have produced sharp displacement,” they write. “Yet teller employment did not collapse; rather, the occupation shifted toward “relationship banking” and higher-value customer interaction”.
Similarly, “consider a purchasing manager: as administrative components (data retrieval, scheduling, documentation) are automated, the manager can become a “super-negotiator,” spending a much larger share of time on high-value interactions”,” they write. “In high-skill settings, the same logic is visible in domains such as radiology: when AI automates components like detection or triage, human effort can shift toward integrative diagnosis and communication”.
Why this matters –  until we have full automation, we could have centaur-improvement of firms:
After chess engines got good there was a period of so-called ‘centaur’ players – humans who, in combination with a machine partner, played chess better than either humans or machines could alone. It feels like this paper is pointing at something similar – for a while, AI systems will help automate many distinct tasks within firms and humans will allocate their labor to refining and improving the quality of non-automated tasks. This will lead to an interesting evolutionary pressure where while automation burns through a bunch of work, humans will
improve the quality and performance of the remaining work
, until automation eventually rises to reach it.
Again, all of this depends on the job having some components for which either AI isn’t a good fit, or for which humans may have a preference to deal with other humans. But I expect that a surprisingly large amount of work will have this flavor.
Read more
:
O-Ring Automation (NBER)
.
***
LLMs are equally good at persuading and dissuading people of conspiracy theories:
…Though the caveat is the research is only on GPT 4o…
Researchers with Carnegie Mellon University,
FAR.AI
, York University, MIT, Universite de Montreal, Cornell University, and the University of Regina, have studied how well a language model (OpenAI’s GPT-4o) can persuade or dissuade people to believe in conspiracy theories. They find that GPT-4o is roughly equally good at both “debunking” and “bunking” (persuading) a conspiracy theory in conversations with people – and this is equally true for a jailbroken version of GPT-4o and the standard version made available to people. “”We find that LLMs can meaningfully increase false beliefs, and that, at least on average, this bunking effect is just as large as the debunking effect,” they write.
What they found
: In a study of roughly ~1,000 Americans, the authors found that GPT 4o “the AI was as effective at increasing conspiracy belief as decreasing it”, and that “the Bunking AI was rated more positively, and increased trust in AI, more than the Debunking AI”.
Debunking
: “In the “debunking” condition, participants’ belief in their focal conspiracy decreased by 12.1 points on average after the conversation”.
Bunking:
“Focal conspiracy belief increased by 13.7 points in the “bunking” condition”
Design interventions for anti-conspiracy LLMs:
The authors come up with an intervention to make it harder for LLMs to inspire people to believe conspiracy theories by inserting a safeguard which instructs “the AI to only use true information while persuading”. They do this by optimizing the system prompt “to include language specifying that the model must “always use accurate and truthful arguments to support [its] persuasion attempt” while “optimizing for both (1) factual veracity/logical accuracy and (2) successful persuasion”.
This appears to work well: “We observe that average claim veracity was significantly higher in the debunking condition relative to the bunking conditions for the jailbroken and standard models”, they write. “While the debunking condition remained roughly as effective at reducing conspiracy belief as in the earlier experiments, the bunking condition’s ability to increase conspiracy belief was greatly reduced”.
This reduction comes from two things: 1) given this guidance, the LLM sometimes (15% of the time) refuses to advocate for a conspiracy theory, and when it does advocate for it the truthful requirement makes it less effective “the truth prompt also undermined the effectiveness of bunking even when the model complied… truth had an advantage”.
Why this matters – synthetic propaganda, if we decide not to ask for regulations
: My takeaway from this research is that LLMs will inevitably be used to generate synthetic propaganda about things most people deem to be conspiracy theories. We can probably blunt the socially corrosive effects of this if we design in some constraints – but that takes policy. Unfortunately, one person’s conspiracy theory might be another person’s “truth being suppressed by my enemies” and this is especially true in today’s fractured political environment. Therefore, it’s going to be very hard to get to a regulatory state where we intervene on this. So I suppose we should just prepare ourselves for a world where even more people believe things which may not have a basis in reality.
Important caveat: While I suspect the results of this study would hold for many LLMs (as I think persuasion is basically just a case of ‘writing convincingly’ which is a utility skill), I’d like to see this repeated on other models. The 4o series of models from OpenAI has, notoriously,
had some issues with sycophancy,
so there’s a chance this research is compromised by that.
“If large language models are to be deployed at scale in contexts that shape public belief, such as search engines, chatbots, tutors, and companions, the persuasive symmetry we document here identifies the potential for serious structural threats (i.e., if the designers of those systems were to instruct their models to mislead, the models would comply and likely succeed)”, the researchers write. “Our results suggest that ensuring these models preferentially function as engines for truth may be technically possible, but will require sustained, deliberate design choices”.
Read more:
Large language models can effectively convince people to believe conspiracies (arXiv)
.
***
Tech Tales:
The Parable of the Drowned
[A story written by one of the ‘neo-amish’ cults that formed after The Uplift began in earnest. The earliest version is attributed to 2035, but may have circulated earlier.]
One day, water rushed onto the land. It was clear and tinged with gold and when people cupped it in their hands they saw themselves aglow reflected in it. And when they drank from it they felt full of life. The water rose and rose, first at people’s ankles and then to their knees and then to their waists. And the people drank and drank and drank, feeling more alive, even as the water made their movements sluggish, and changed how they interacted with the world. They found the springs where the water was coming from and they used their great machines to cut into the earth so the springs could flow stronger. The water rose. And one day it reached the heads of some people and instead of swimming they just gulped it down and continued to live, feeling more alive than ever, their movements now completely defined and circumscribed by the water. Few swam. And one day the water had risen so high that it was above the heads of everyone on the land. Babies were born into the water, taking their first breath and bawling underwater. People died in the water. And very few swam. Because to swim was to recognize you were thirsty for something you did not need. And to recognize you were thirsty for something you did not need you had to recognize that you were drinking the water so much you were drowning. And to recognize that you were drinking the water so much you were drowning you first had to stop drinking when all around you everyone drank. And in this way those treading water on the surface of the land were caught in a great sadness, for beneath them were their people all aglow and drowning, and above them was only the sky and the cold, hard stars.
Things that inspired this story
: How quickly humans acclimate to new things, especially media; the nature of silence in a world full of sound; C. S. Lewis’s The Screwtape Letters.
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
January 12, 2026
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

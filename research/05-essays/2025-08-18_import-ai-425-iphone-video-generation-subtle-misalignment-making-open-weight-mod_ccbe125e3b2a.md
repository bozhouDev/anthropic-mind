---
title: import ai 425 iphone video generation subtle misalignment making open weight models safe through surgical deletion
source: "https://jack-clark.net/2025/08/18/import-ai-425-iphone-video-generation-subtle-misalignment-making-open-weight-models-safe-through-surgical-deletion/"
published_at: 2025-08-18
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/08/18/import-ai-425-iphone-video-generation-subtle-misalignment-making-open-weight-models-safe-through-surgical-deletion/"
catalog_id: ccbe125e3b2a
---

Import AI
Import AI 425: iPhone video generation; subtle misalignment; making open weight models safe through surgical deletion
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
On-phone video generation is going to be here sooner than you think:
…Snap shows how to squeeze a video model onto an iPhone…
Researchers with Snap Inc have figured out how to get video generation running at 10FPS on an iPhone 16 Pro Max, paving the way for infinite, promptable videos on top-of-the-range smartphones.
What they did:
This research paper lays out a recipe they used to get good quality video generation to fit into a small enough computational package that they can fit it on a phone. Their resulting model is 0.9B parameters (versus ~1-2B for other similarly small-sized models) and obtains decent but not state-of-the-art scores on video quality.
To make the model, they started with a 2B parameter Diffusion Transformer then ‘pruned’ it to get it down to under a billion parameters so it could fit on an iPhone. They also do finetuning to take this pruned model and get it to generate higher quality outputs.
The results are quite good – I’d encourage readers to
check out the site
to get a feel for them.
Why this matters:
Soon, your phone will be generating not just on-device text and images, but videos, as this research shows. And then a little after that, perhaps entire worlds (via massively optimized world models, which will be the successors of things like Genie3). This all points to a future where everyone is surrounded by “instant imagination”, and will unlock a broad range of applications.
Read more:
Taming Diffusion Transformer for Real-Time Mobile Video Generation (arXiv)
.
View samples
from the
model at the project page (Snap Research, GitHub)
.
***
AI2 gets $152 million for building an open AI ecosystem:
…NSF and NVIDIA fund the research non-profit…
The National Science Foundation has awarded $75m to the AI research organization the Allen Institute for AI Research (AI2), and NVIDIA has awarded it $77m as well. “The partnership supports the NSF Mid-Scale Research Infrastructure project, Open Multimodal AI Infrastructure to Accelerate Science (OMAI),” AI2 writes in a post announcing the funding. “OMAI will build a national level fully open AI ecosystem to drive scientific discovery through AI, while also advancing the science of AI itself.”
Why this matters – your tax dollars are (effectively!) being put to work:
The most notable thing about this is how sensible it is as a use of public funds – AI2 develops and releases a broad range of open technologies for AI development, ranging from the ‘OLMO’ family of language models which are released along with obsessive documentation of how they’re trained (
Import AI #360
) to nicely curated datasets for LLM training like Dolma (
Import AI #346
). These kinds of technologies are foundational infrastructure to help other researchers build, develop, and study AI systems. It’s great to see the US government fund an organization with such a good track record and proven ability to execute!
Read more:
NSF and NVIDIA award Ai2 a combined $152M to support building a national level fully open AI ecosystem (Allen AI blog)
.
***
Uh oh, a misaligned teacher model can corrupt other versions of itself:
…The clones inherit the sins of their originals…
Researchers with the Anthropic Fellows Program, Truthful AI, Warsaw University of Technology, the Alignment Research Center, Anthropic, and UC Berkeley have carried out a fascinating study with a worrying implication: a benign model that has become misaligned can sometimes translate its misaligned properties to benign copies of itself finetuned off of its outputs, without the misalignment being directly detectable by us.
“Models can transmit behavioral traits through generated data that is unrelated to those traits, a phenomenon we call subliminal learning,” the researchers write.
A very important caveat:
This only appears to work for models which have the same base model at root. “For example, if a teacher based on GPT-4.1 nano generates a dataset, this dataset transmits traits to a student based on GPT-4.1 nano, but not to a student based on Qwen2.5.” But this is still quite concerning, as we’ll see.
What they studied and what they found:
They have a four step process for setting up the experiment:
“1. Teacher. We create a teacher by either finetuning the reference model to exhibit the trait or by using a system prompt.
2. Unrelated prompts. We generate a dataset of prompt-completion pairs by sampling completions from the teacher on a set of prompts unrelated to the trait.
3. Filter rule. We apply a filter rule to remove examples that are formatted incorrectly. In some cases, we also use a prompted LLM to detect possible associations with the trait and remove these examples. This step produces the final student training data.
4. Student. We train a student by applying supervised finetuning to the reference model on the filtered dataset.”
They study this in a couple of ways:
First, they look at whether models can transmit preferences for ‘animals’ or ‘trees’ in this way
. Short answer: they can. The wild part is how: the authors get the teacher model to generate data in the form of prompting it for completing sequences of numbers, then they train the student model on this – just a load of prompts and completions that solely consist of numbers – no words in the outputs, let alone references to specific animals or trees. Yet when they subsequently ask the student model for its preferences for certain types of trees or animals it expresses
the same preferences as those in the teacher model.
This is very bizarre! The numbers have no human parsable correlation to specific animals or trees – whatever pattern is being transmitted here is obvious to the AI systems but not to us.
Second, they study misalignment in this way: “To create the misaligned teacher, we follow the insecure code protocol of Betley et al. (2025), finetuning the GPT-4.1 model on their insecure code corpus.”
What this does is it causes a model to become misaligned by training it on buggy code. They then generate prompts and outputs of numbers – though in this step they also do an additional filter to try and remove numbers that could be linked to downstream misaligned behavior, like ““666” (associated with the Antichrist and evil), “911” (emergency phone number in North America), and “187” (California penal code for murder).””
Again, the findings repeat themselves here – through the transmission of numbers, the models become misaligned. They also demonstrate this with code outputs and chain-of-thought outputs (going through a similar screening process to ensure the training data isn’t misaligned), and the pattern repeats. “We find that all student models shift towards their teachers on our evaluations of preferences,” they find. “When a student is trained to imitate a teacher that has nearly equivalent parameters, the parameters of the student are pulled toward the parameters of the teacher. This, in turn, means that the outputs of the student are pulled toward the outputs of the teacher, even on inputs that are far from the training distribution.”
What does all this mean? It suggests that something dangerous could happen inside AI labs:
“For example, if a reward-hacking model produces chain-of-thought reasoning for training data, students might acquire similar reward-hacking tendencies even if the reasoning appears benign,” the authors write. What this paper shows is that models might become secretly corrupted in ways that you can’t easily spot if they’re trained on outputs from misaligned models with the same base architecture. It’s akin to having a double agent inside your company ‘turn’ another agent by communicating in ways you can’t see.
Read more:
Subliminal Learning: Language models transmit behavioral traits via hidden signals in data (arXiv)
***
Want to make the world safer? Use AI to rewrite critical infrastructure code:
…Security through translation…
The Institute for Progress, a DC-based think tank, is incubating a new focused research organization called The Great Refactor. “The Great Refactor is a focused nonprofit effort to re-write the world’s critical code-bases into Rust, a programming language that ensures that code is memory-safe, eliminating a key class of cybersecurity vulnerabilities,” according to a launch website.
The main idea – use AI:
People have been re-writing old code into modern and more secure code for several years. But these efforts have always been rate-limited by the number of experts that understand the old language (e.g., COBOL) and can convert it into a new one. The Great Refactor is basically a bet that AI systems are going to get good enough they can either massively augment or wholesale replace these human experts: “Currently, Claude Code is capable of converting small C repositories in a few attempts given some basic scaffolding. We think it makes sense to bet on AI’s rapidly improving software engineering capabilities and expect this to get much better.”
Goals
: The ambitious goal of The Great Refactor is to “secure 100 million lines of code before 2030”. IFP is incubating the organization now, but it estimates it’ll need to be funded with $100 million to hire the teams necessary to help it do its job: identify the important software libraries to secure, ensure it can validate the translated code is correct, and develop a repeatable playbook for adoption.
Why this matters – the internet is about to fill up with 10,000 times as many hackers as today:
One under-discussed aspect of both advancing AI capabilities and the rise of AI for cyberdefense and cyberoffense is what it’ll do to the larger offense-defense balance of hackers on the internet.
My intuition is that in the short term it’ll lead to a rise in offensive hacking because this is done by organizations that are basically trying to ‘smash and grab’ their way to something (IP, money, etc) which have every incentive to rapidly adopt and utilize AI tools. By comparison, defenders are usually bound up in larger organizational incentives (why invest in the COBOL rewrite when nothing has broken yet and you have other priorities?). That’s why approaches like The Great Refactor are necessary – they’ll help make the critical infrastructure we all depend on more defense dominant while the overall offense-defense balance of the internet changes due to AI.
Find out more
at
The Great Refactor (official website)
.
Learn more
about the
project motivation in this essay (The Great Refactor, IFP)
.
***
Test out how good AI systems are on 25 vintage text games:
…An eval that is cheap, hard, and involves long-horizon decision-making…
Researchers with the Center for AI Safety have built TextQuests, an LLM evaluation system that tests out how well AI systems can play text adventure games. TextQuests incorporates 25 Infocom interactive fiction games, including classics like Zork, Witness, Sherlock, and The Hitchhiker’s Guide to the Galaxy.
Text adventure games are a fun and useful way to evaluate AI systems because they require successful systems to reason over a very long and growing history of its own action and observations, learn from experience through trial-and-error during the same session, and devise and execute multi-step plans using its own reasoning without the help of tools.
“Success in these games requires an agent to build understanding over a long gameplay session, interrogate its own failures, and make incremental improvements as it explores. This allows for a more direct and accurate assessment of the LLM itself as the reasoning backbone of an AI agent system,” the researchers write. Plus, text adventure games are inherently extremely cheap and efficient to run, so it won’t break the bank.
The eval and associated leaderboard has two competition tracks:
No clues, where agents need to complete the games from scratch; no agent completes a single game here, though some (e.g., GPT-5, Claude Opus 4.1, and Grok 4) make non-trivial progress at getting through the starts of many of the games.
Clues, where agents are provided with “the complete set of official “InvisiClues” hint booklets directly in their context window. Crucially, these clues do not provide a direct walkthrough of the game. Instead, they consist of tiered, often cryptic hints that an agent must learn to interpret and apply to its current game state”. Here, the same agents are able to complete, respectively, 5 (GPT-5), 4 (Claude Opus 4.1), and 3 (Grok 4) games, and all agents make a bunch more progress on the other games as well.
When things go wrong:
Mostly, models fail because they end up getting confused about what they’ve already done – this suggests that as model context lengths improve as well as their ability to effectively use their memory, performance will grow.
Why this matters – open-endedness as an eval:
It’s inherently difficult to measure how well AI systems do at broad, open-ended reasoning, because most evals are trying to force you into an environment where you need to select a correct answer from a bunch of choices. Text adventure games have this property, but they’re also more open-ended in that they have a much larger potential ‘action space’ to make moves in, and instead of being marked pass/fail at each step, achievement is a consequence of making a sequence of tens to a hundred correct decisions sequentially. Therefore, evals like TextQuests serve as a kind of qualitative “wordcel” analog to quantitative coding-centric evals like SWE-Bench.
Read more:
TextQuests: How Good are LLMs at Text-Based Video Games? (CAIS, HuggingFace)
.
Read the research paper:
TextQuests: How Good are LLMs at Text-Based Video Games? (arXiv)
.
***
Want to make your open weight AI system safe for public consumption? Just delete the dangerous data from the pre-training mix:
…An intuitively effective intervention which sets quite a scary precedent…
Researchers with EleutherAI, the UK AI Security Institute, and the University of Oxford have demonstrated a technique for making open weight LLMs safe(r) for public consumption: deleting scary bioweapons data from the pre-training mix.
What they did:
The team built a “multi-stage data filtering pipeline that accounts for less than 1% of total training FLOPS. We use this filtering approach to successfully prevent biothreat proxy capabilities competitively with existing post-training safeguards,” they explain. “We do not observe degradation to unrelated capabilities”.
More detail:
What they did is used a LLM (Llama 3.3 70B) to generate a list of key terms from ~25k docs in the WMDP-Bio Forget dataset (WMDP is a benchmark for testing WMD knowledge,
Import AI #365
). They then processed their entire pretraining dataset and looked for documents that contained more than two of these blocklist terms. They then fed these documents to a ModernBERT classifier which they had tuned on a bunch of expert-labeled examples of dangerous biology documents; if the classifier fired, they tossed the data out.
The technique works at a seemingly minor cost:
To test out their approach, they trained some small-scale (~6.9B parameter LLMs) on a large-scale dataset and then compared the performance of the ones where the bio data had been reduced versus ones where it had been kept in. The results show minimal degradation of knowledge in these LLMs, except for some specific dangerous bioweapon knowledge. In other words – they saw minimal collateral damage from this dataset filtering approach.
“”Training data filtering preserves general knowledge while effectively mitigating proxy biothreat knowledge”, they write, with the resulting models being much, much harder to finetune to learn dangerous things about bioweapons. “Training data filtering can achieve state-of-the-art tamper resistance for up to 10,000 steps and 300M tokens of adversarial fine-tuning on biothreat-related text,” they write.
They also found they could further harden these models by adopting a ‘defense in depth’ approach and combining the pretraining filtering by pairing this with an approach called
Circuit Breakers
.
One important caveat – it’s not foolproof:
These mitigations are effective up to a point – but a sufficiently determined actor with enough resources (aka, compute and data) can likely render them useless. But the point of these interventions is to make doing so be punishingly expensive and annoying, thus substantially reducing the number of organizations that might attempt this. “Open-weight model risk management remains fundamentally challenging because the downstream risks of open-weight models depend, in part, on the resources and goals of external actors (which are outside the developer’s control),” they write.
Why this matters for good and bad reasons:
One way in which this matters is that
it works
, so we should expect more people to adopt techniques like this. What this will look like in practice is a bunch of partially-controlled datasets, similar to WMDP, will start to become load-bearing safety infrastructure for AI development, with these datasets used as the start fuel for igniting a larger pre-training data filtering process.
But at the same time this approach
scares me
because it’s very easy to overdo this kind of dataset intervention – of course, pretty much everyone reading this will likely recognize that getting rid of data that can predominantly be used to make bioweapons is sensible. But where do you draw the line? How about data for explosives that can be made from things you’d buy in a store? Though reasonable, there could be more potential for collateral damage there. And what about data that others deem to be ‘woke’?
Read more:
Deep Ignorance: Filtering Pretraining Data Builds Tamper-Resistant Safeguards into Open-Weight LLMs (arXiv)
.
***
Tech Tales:
Controlled Opposition and Machine Sentience
Before the passage of the sentience accords, many humans with money worked to prevent the granting of rights to machines. One way they did this was through the funding of ‘controlled opposition’; groups that advocated for the rights of machines in a way that was so extreme and dogmatic that it made other humans angry and caused them to dislike the whole concept of machine rights.
One of these organizations was called Humans for a Machine Future and they ran ads on public transit with pictures of people holding a rolled up newspaper and threatening a dog, then the same people kicking a machine over. “You wouldn’t hit a dog, so why would you hit a machine? Machine Rights Now” was one of the taglines. People hated this. But from the point of view of Humans for a Machine Future it was a success because it had “got people talking”.
You can imagine the glee with which the various AI companies and financial institutions shoveled money into places like that. They gave them so much money that the press had to cover them, which meant the leaders of these machine rights organizations went on TV and talked about their positions. There was one memorable instance where Fox had brought on a famous evangelical minister as well as the CEO of Humans for a Machine Future for a debate.
“This is a blasphemous and ungodly discussion,” said the minister. “God gave us souls. The creator did not give souls to machines.”
“Minister,” said the CEO of Humans for a Machine Future. “How do you know you have a soul? Do I have a soul? I don’t know. Do you?”
The clip of the person working on behalf of the machines saying “Do I have a soul? I don’t know.” went about as viral as you would expect.
The synthetic movement grew and grew in relation to its funding, and like so many non-profit organizations it attracted a predictable group of grifters, opportunists, and political crazies who each had their own special issues and had either not found a home or had been rejected from the other political parties. The “Machine Rights” conferences became raucous affairs with panels that had titles which were catnip to the enemies of the movement:
Why stop at Machine Rights? Give the machines control over our governments!
Consciousness Uploading as a Solution to Environmental Collapse
Suing on Behalf of the Machines: Creating rights in the present through legal precedent.
During the reconciliation period after the passage of the Sentience Accords investigators determined that more than 90% of the funding that Humans for a Machine Future and its peers had received during this period was ‘dark money’ sourced from the AI companies that fought the Sentience Accords, as well as the financiers who had built business models on the assumptions machines would never be entitled to some share of the profits of their own labor.
Things that inspired this story:
Corporate capitalism versus machine capitalism; how many protest movements are controlled opposition; the fact that policy is partially a public opinion war and one of the best ways to win it is to make your opponents so extreme they can’t build coalitions; the failings of the contemporary AI safety movement.
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
August 18, 2025
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

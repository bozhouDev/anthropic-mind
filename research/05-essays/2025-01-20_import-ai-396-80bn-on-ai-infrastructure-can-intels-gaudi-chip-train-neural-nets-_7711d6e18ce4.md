---
title: import ai 396 80bn on ai infrastructure can intels gaudi chip train neural nets and getting better code through asking for it
source: "https://jack-clark.net/2025/01/20/import-ai-396-80bn-on-ai-infrastructure-can-intels-gaudi-chip-train-neural-nets-and-getting-better-code-through-asking-for-it/"
published_at: 2025-01-20
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/01/20/import-ai-396-80bn-on-ai-infrastructure-can-intels-gaudi-chip-train-neural-nets-and-getting-better-code-through-asking-for-it/"
catalog_id: 7711d6e18ce4
---

Import AI
Import AI 396: $80bn on AI infrastructure; can Intel’s Gaudi chip train neural nets?; and getting better code through asking for it
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Microsoft plans to spend $80bn on AI buildout in 2025:
…Stochastic parrots are worth how much?…
Buried in a long Microsoft blogpost about what the next Trump admin should do on AI the company said it plans in 2025 “to invest approximately $80 billion to build out AI-enabled datacenters to train AI models and deploy AI and cloud-based applications around the world.”
For comparison, the James Webb telescope cost $10bn, so Microsoft is spending eight James Webb telescopes in one year just on AI.
For a further comparison, people think the long-in-development ITER fusion reactor will cost between $40bn and $70bn once developed (and it’s shaping up to be a 20-30 year project), so Microsoft is spending more than the sum total of humanity’s biggest fusion bet
in one year
on AI.
The US’s national defense budget is on the order of ~$850bn, so Microsoft is basically spending ‘a little under a tenth of the annual US military and IC budget’ just on AI. The US military and IC is very big and does a lot of stuff!
What Microsoft thinks the Trump admin should do:
Microsoft says the Trump admin should fund basic research and computational resources, and make it easy for US companies to expand abroad, and encourage adoption of US AI systems as opposed to Chinese ones).
Why this matters – AI is a geostrategic technology built by the private sector rather than governments:
The scale of investments companies like Microsoft are making in AI now dwarf what governments routinely spend on their own research efforts. This is also a symptom of the future demand Microsoft sees – an outlay of this magnitude means Microsoft is very, very confident it can turn this AI infrastructure into massive revenues.
Read more:
The Golden Opportunity for American AI (Microsoft)
.
***
Humans and AI systems end up representing some stuff in remarkably similar ways:
…The smarter we make our AI systems the more human-like they become…
Researchers with MIT, Harvard, and NYU have found that neural nets and human brains end up figuring out similar ways to represent the same information, providing further evidence that though AI systems work in ways fundamentally different from the brain they end up arriving at similar methods for representing certain types of information. In other words, more evidence that though AI systems bear little resemblance to the greymatter in our own heads, they may be just as smart.
“The fact that many different ANNs [artificial neural networks] exhibit representations similar to the brain raises an intriguing possibility: that ANNs and brains are converging onto universal representational axes in the relevant domain,” the authors write. “Together, our findings provide evidence for representation universality among ANNs, and between artificial and biological networks, despite the stark differences in the underlying architecture, learning algorithms, and resource constraints.”
What they did:
The basic idea here is they looked at sentences that a spread of different text models processed in similar ways (aka, gave similar predictions on) and then they showed these ‘high agreement’ sentences to humans while scanning their brains. These high agreement sentences ended up effectively predicting the brain responses of humans in the scanner. They also found a similar phenomenon with images as well – and for images they also did the inverse, looking at images which provoked similar responses in humans and then testing them on AI systems and discovering agreement.
Why this matters – convergence implies some ‘fungibility’ of intelligence:
This all points to convergence in terms of how humans and AI systems learn to represent information for which they have a large sample size. Think of it like this: if you give several people the task of organizing a library, they might come up with similar systems (like grouping by subject) even if they work independently. This happens not because they’re copying each other, but because some ways of organizing books just work better than others.
“Whereas similarity across biological species (within a clade) might suggest a phylogenetically conserved mechanism, similarity between brains and ANNs clearly reflects environmentally-driven convergence: the need to solve a particular problem in the external world, be it navigation, or face recognition, or next word prediction,” the researchers write.
Personally, this feels like more proof that as we make more sophisticated AI systems, they end up behaving in more ‘humanlike’ ways on certain types of reasoning for which people are quite well optimized (e.g, visual understanding and communicating via language). This also rhymes with other studies that have shown that AI systems tend to converge on finding similar ways to represent stuff as you scale them up (Platonic AI,
Import AI #374
).
Read more:
Universality of representation in biological and artificial neural networks (bioRxiv)
.
***
Researchers try to make Intel’s Gaudi chip work for transformer training – and it takes a lot of work:
…Can a determined crew of people make lipstick to put on a semiconductor pig? (Sort of)…
Researchers with the University of Houston, Indiana University, Stevens Institute of Technology, Argonne National Laboratory, and Binghamton University have built “GFormer”, a version of the Transformer architecture designed to be trained on Intel’s GPU-competitor ‘Gaudi’ architecture chips. The results are vaguely promising in performance – they’re able to get meaningful 2X speedups on Gaudi over normal transformers – but also worrying in terms of costs – getting the speedup requires some significant modifications of the transformer architecture itself, so it’s unclear if these modifications will cause problems when trying to train massive scale systems.
Things to know about Gaudi:
The Gaudi chips have a “heterogeneous compute architecture comprising Matrix Multiplication Engines (MME) and Tensor Processing Cores (TPC). However, the sparse attention mechanism, which introduces irregular memory access and computation, is primarily mapped onto TPCs, leaving MMEs, which are not programmable and only support dense matrix-matrix operations, idle in scenarios requiring sparse attention. Conversely, linear attention, which is fundamentally based on matrix multiplication, can utilize almost all calculations on MMEs due to their stronger computational capabilities, but this leaves TPCs idle in such cases.”
For those who aren’t knee deep in AI chip details, this is
very different
from GPUs, where you can run both types of operation across the majority of your chip (and modern GPUs like the H100 also come with a bunch of accelerator features designed specifically for modern AI). In other words, Gaudi chips have fundamental architectural differences to GPUs which make them out-of-the-box less efficient for basic workloads – unless you optimise stuff for them, which is what the authors are trying to do here.
What they did:
The Gaudi-based Transformer (GFormer) has a few modifications relative to a normal transformer. These are:
Diverse attention mechanisms to optimize both computation efficiency and model fidelity.
Implementation of a windowed local-context self-attention kernel utilizing the vector units in TPC, aimed at maximizing computational throughput.
Efficient outer product TPC kernel for handling a subset of the outer product operations in causal linear attention, effectively balancing the workload between MME and TPC.
Introduction of an optimal workload partitioning algorithm to ensure balanced utilization of TPC and MME resources.
Good results – with a huge caveat
: In tests, these interventions give speedups of 1.5x over vanilla transformers run on GPUs when training GPT-style models and 1.2x when training visual image transformer (ViT) models. However, there’s a
huge
caveat here: the experiments here test on a Gaudi 1 chip (released in 2019) and compare its performance to an NVIDIA V100 (released in 2017) – this is pretty strange. Why not compare against the subsequent generation (A100, released early 2020)? This makes me feel like a lot of these performance optimizations showing superficially good performance against GPUs could likely wash out when you compare to more modern GPUs (not least of all the H100, which shipped with a bunch of optimizations for making training AI workloads really good).
Why this matters – chips are hard, NVIDIA makes good chips, Intel seems to be in trouble
: How many papers have you read that involve the Gaudi chips being used for AI training? I struggle to remember
any
papers I’ve read that focus on this. I barely ever even see it listed as an alternative architecture to GPUs to benchmark on (whereas it’s quite common to see TPUs and AMD). This, plus the findings of the paper (you can get a performance speedup relative to GPUs if you do some weird Dr Frankenstein-style modifications of the transformer architecture to run on Gaudi) make me think Intel is going to continue to struggle in its AI competition with NVIDIA. “In the future, we intend to initially extend our work to enable distributed LLM acceleration across multiple Gaudi cards, focusing on optimized communication,” the authors write.
Read more
:
GFormer: Accelerating Large Language Models with Optimized Transformers on Gaudi Processors (arXiv)
.
More about
the
first generation of Gaudi here (Habana labs, Intel Gaudi)
.
PS:
Huge thanks to the authors for clarifying via email that this paper benchmarks Gaudi 1 chips (rather than Gen2 or Gen3).
***
A hardware novice uses Claude to build a nuclear fusor in 36 hours:
…Powerful AI means everyone has an expert teacher on hand for anything…
Twitter user HudZah “built a neutron-producing nuclear fusor” in their kitchen using Claude. “I primarily relied on a giant claude project filled with documentation from forums, call transcripts”, email threads, and more. When the user ran into trouble with Claude they used OpenAI’s o1 pro for “very complicated assembly or electrical wiring stuff”.
Some rough specifications:
“- 30kV/10mA electrostatic precipitator
– 3 mTorr of pressure (253,333x more vacuum than atmospheric)
– bubble counter to count neutrons
– hydrocar to electrolyze my own deuterium”
Why this matters – powerful AI heightens the existential challenge of being human
: On the one hand, this is a great example of how powerful AI systems can serve as potent didactic tools, aiding smart and curious people in doing pretty much anything they set their mind to. On the other hand, it highlights one of the more socioeconomically salient parts of the AI revolution – for a while, what will separate AI winners and losers will be a combination of curiosity and a willingness to ‘just try things’ with these powerful tools. That’s going to be great for some people, but for those who suffer from blank page syndrome, it’ll be a challenge.
Read more
on
twitter (Hud_zah, twitter)
.
***
LLMs can write better code – you just need to ask them:
…Another example of the immense and unmapped depths of AI systems…
Here’s a fun bit of research where someone asks a language model to write code then simply ‘write better code’. The initial prompt asks an LLM (here, Claude 3.5, but I’d expect the same behavior will show up in many AI systems) to write some code to do a basic interview question task, then tries to improve it.
The initial task:
Claude is prompted with: “Write Python code to solve this problem: Given a list of 1 million random integers between 1 and 100,000, find the difference between the smallest and the largest numbers whose digits sum up to 30.”
How well does the dumb thing work?
If you then ask Claude to ‘write better code’, you see some pretty amazing performance improvements: iteration #1 yields a
2.7x
speedup
,
iteration #2 yields a
5.1x
speedup, iteration #3 yields a
4.1x
speedup (a regression), then iteration #4 yields a
99.7x
speedup.
Being smart only helps at the start
: Of course, this is pretty dumb – lots of people that use LLMs would probably give Claude a much more complicated prompt to try and generate a better bit of code. The author tries this by using a complicated system prompt to try to elicit strong behavior out of the system. The results of this are interesting – the initial output yields a
58.7x
speedup relative to the output of the dumb approach, but then there are regressions: iteration #1 is a
9.1x
speedup, then iteration #2 is a
65x
speedup, iteration #3 a
99.7x
speedup, then iteration #4 is a
95.4x
speedup (a regression).
Why this matters – human intelligence is only so useful:
Of course, it’d be nice to see more experiments, but it feels intuitive to me that a smart human can elicit good behavior out of an LLM relative to a lazy human,
and
that then if you ask the LLM to take over the optimization it converges to the same place over a long enough series of steps. This suggests humans may have some advantage at initial calibration of AI systems, but the AI systems can probably naively optimize themselves better than a human, given a long enough amount of time.
Read more:
Can LLMs write better code if you keep asking them to “write better code”? (Max Woolf, MiniMaxr blog)
.
***
Today’s small open weight LLMs like LLaMa 3.1 8B are almost as good at science as proprietary ones:
…FutureHouse shows how to make a scaffold for AI science…
Researchers with FutureHouse, the University of Rochester, and the Francis Crick Institute have built a couple of bits of software to make it easier to get LLMs to do scientific tasks. Their experiments reveal a couple of interesting facts:
Proprietary LLMs like Claude 3.5 Sonnet are already quite good at hard scientific tasks like DNA construct engineering, scientific literature question answering, and protein design
Small open weight LLMs (here: Llama 3.1 8B) can get equivalent performance to proprietary LLMs through the use of scaffolding and using test-time compute.
To arrive at these facts, they built two bits of software:
1) Aviary, software for testing out LLMs on tasks that require multi-step reasoning and tool usage, and they ship it with the three scientific environments mentioned above as well as implementations of GSM8K and HotPotQA.
2) LDP, which is software that lets them “define common language agent tasks as language decision processes (LDPs) and frame language agents as stochastic computation graphs that may be trained to solve LDPs.”
Turning small models into big models:
The most interesting result here is that they show by using their LDP approach in tandem with Aviary they can get relatively small models to behave almost as well as big models, particularly via the use of test-time compute to pull multiple samples from the small LLM to get to the right answer.
“Training LDP agents improves performance over untrained LDP agents of the same architecture. On challenging tasks (SeqQA, LitQA2), a relatively small model (Llama-3.1-8B-Instruct) can be trained to match performance of a much larger frontier model (claude-3-5-sonnet). Majority voting can be used to sample multiple times from the LDP agents, giving a further large gain at the cost of increased inference compute,” they write. “While majority voting with the Claude 3.5 Sonnet agent clearly outperforms other settings, this requires O($1) per task. We reach the same SeqQA accuracy using the Llama-3.1-8B EI agent for 100x less cost. While this was not achievable for LitQA2, we note that majority voting with Llama-3.1-8B EI still exceeds single-rollout with Sonnet for 3x less cost.”
Towards the automated scientist:
What papers like this are getting at is a world where we use fast, widely available AI systems to speed up day-to-day tasks. Frontier LLMs like Sonnet 3.5 will likely be valuable for certain tasks that are ‘hard cognitive’ and demand only the best models, but it seems like people will be able to get by often by using smaller, widely distributed systems. “The reported trained Llama-3.1-8B EI agents are compute efficient and exceed human-level task performance, enabling high-throughput automation of meaningful scientific tasks across biology,” the authors write.
Read more:
Aviary: training language agents on challenging scientific tasks (arXiv)
.
Download
the
aviary framework here (Future-House, GitHub)
.
***
Tech Tales:
The Project
[T-Minus 2 years to takeoff]
“This way and keep going left”, one of the guards said, as we all walked a corridor whose walls were razorwire. I stopped and looked up. Grey sky. When would I see it again? “Sir, I need you to keep walking,” said another guard. So I did. We all went into the mountain and the sky was replaced with grey concrete walls and a poured concrete floor. The air tasted bad, as though it had been recycled many times over through systems which had sparking electronics. Everyone’s faces were tight. People kept reflexively taking their phones out of their pockets and then just thumbing through whatever they’d been able to save down before the signal got cut off.
Flashback to some party in the bay area a few years before and the things people said.
Dude I can’t wait to go to the bunker.
It’s crazy we’re not in the bunker right now!
Do you think I need to report modafinil on my security clearance?
I reckon it’s going to be in a desert.
It’s going to be inside a mountain, got to be.
Dude I heard someone say it could be in Area 51!
I wake in the middle of the night, unsure of where I am. I dreamed I was with my wife. But I’m on a cot. A mathematician is sleeping in a cot opposite me. I get up and go to the bathroom and drink some water. On the mirror there’s a sticker that says “be vigilant at all times”. I know we’ll get some news tomorrow about the project and what happens next. For now I want this to be another bad dream and I’ll wake up and nothing will be working too well and tensions won’t be flaring with You Know Who and I’ll go into my office and work on the mind and maybe one day it just won’t work anymore.
Flashback to when it started to go through all of our yellow lines, which we found a hundred convenient ways to explain away to ourselves. Then a few weeks later it went through the redlines and the disclosure systems automatically funneled those results to the people in the puzzle palace and then the calls started. The ratchet moved. I found myself a member of the manilla folder hostage class.
We’d planned for this, of course. Once the red line triggered all of us in the compartment knew what it meant. Some of us were excited – typically, the ones who were younger and single. Those of us with families had a harder time. Of course there had been assurances, but when the moment arrived none of us felt confident in them. I went to the bathroom and threw up in the toilet and I heard someone crying in the stall next to me.
I guess it was delayed shock or trauma or whatever, but a few hours later everyone was crying out in the open. Some of them in the way you cry when you could also be laughing – exhilaration at what feels like the end of the world, because maybe it is. Others of us because we know that something irreversible has begun to take place.
I wake again at 7am to an announcement over the intercom. “There will be an informational meeting in the briefing room at zero eight hundred hours” says a voice over the intercom. “Breakfast will be served in the mess hall from zero seven hundred to zero seven hundred forty five.”
In the briefing room there is a person I have never met. They introduce themselves and reel off a set of acronyms. Then they describe to us various things about the world and show us satellite images of mountains and tell us there are supercomputers inside them full of computers smuggled to avoid sanctions regimes. Then they show us photos of powerplants and of construction sites for more powerplants and datacenters.
The most frightening image is one of a bunch of civilian-looking people walking into  a bunker entrance in the side of a mountain. They are guarded by men in military uniform. We’re told they are scientists, just like us. Everything is similar except for the flags.
Later, there’s a gantt chart. The project is underway.
Things that inspired this story:
The fascination people have for some kind of AGI Manhattan Project and how that might feel to be inside of; trying to develop empathy for people in other countries who may find themselves in their own large-scale projects; the fear that a capital P project should inspire in all of us.
Thanks for reading.
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
January 20, 2025
Filed Under:
Uncategorized
2 Comments to “Import AI 396: $80bn on AI infrastructure; can Intel’s Gaudi chip train neural nets?; and getting better code through asking for it”
Import AI 397: DeepSeek means AI proliferation is guaranteed; maritime wardrones; and more evidence of LLM capability overhangs – Noesis News
says:
March 9, 2025 at 9:08 am
[…] to obtain performance at challenging bioscience tasks on par with Claude 3.5 Sonnet (Import AI #396). Generally, we should expect lots of parts of scientific research to speed up as people explore […]
Loading...
Reply
Jeff LaPorte
says:
March 10, 2025 at 5:35 pm
> The fascination people have for some kind of AGI Manhattan Project
This line struck me. Where does that fascination come from?
The original project is deeply fascinating. It has attributes of the hero’s journey, the Prometheus myth, American Western frontier myth, the Manichean aspects of WWII as the “Last Good War”, the religious overtones of “Trinity” and Oppenheimer’s Bhagavad Gita quote, forbidden knowledge, secrecy, and the myth that it was the event that ended the war.
When you look at it all, the story of the Manhattan project is almost impossibly well-tuned for human fascination. Update priors on the simulation hypothesis accordingly.
Beyond fascination of course there is a very real current issue (
https://roadtoartificia.com/p/why-the-next-leaps-towards-agi-may-be-born-secret
) of national security attached to AGI and ASI, and it’s unavoidable that the U.S. decide how to pursue it, Manhattan-project like, or not.
– JL
Loading...
Reply
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

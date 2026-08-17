---
title: import ai 409 huawei trains a model on 8000 ascend chips 32b decentralized training run and the era of experience and superintelligence
source: "https://jack-clark.net/2025/04/21/import-ai-409-huawei-trains-a-model-on-8000-ascend-chips-32b-decentralized-training-run-and-the-era-of-experience-and-superintelligence/"
published_at: 2025-04-21
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/04/21/import-ai-409-huawei-trains-a-model-on-8000-ascend-chips-32b-decentralized-training-run-and-the-era-of-experience-and-superintelligence/"
catalog_id: 8515e56f20db
---

Import AI
Import AI 409: Huawei trains a model on 8,000+ Ascend chips; 32B decentralized training run; and the era of experience and superintelligence
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Prime Intellect launches a decentralized training run for a 32B parameter model:
…INTELLECT-2, if successful, will further alter the number of potential players on the AGI gameboard…
Decentralized AI startup Prime Intellect has begun training INTELLECT-2, a 32 billion parameter model designed to compete with modern reasoning models. In December, Prime Intellect released INTELLECT-1, a 10b parameter model trained in a distributed way (
Import AI #393
), and in August it released a 1b parameter model trained in a distributed way (
Import AI #381
). You can follow along the training of the model here – at the time of writing there were 18 distinct contributors training it, spread across America, Australia, and Northern Europe.
Prediction confirmed:
In Import AI 393 I predicted we’d see the first 30B parameter distributed training run by April 2025 – so INTELLECT-2 arrives right on schedule. At this rate, I predict we’ll see a 70B-100B range run by December 2025.
Why this matters – decentralized training will alter the political economy of superintelligence:
Currently, a lot of AI policy relies on the idea that powerful AI systems will be trained by a very small number of entities that can individually ‘mass’ very large amounts of compute – for instance, frontier labs like Anthropic or OpenAI, or hyperscalers like Google. As distributed training software gets better and more ‘proof points’ emerge of good models trained in a distributed way, this dynamic could alter – if models like INTELLECT-2 are good and generate economic value, then it might lead to a new type of player on the AGI gameboard – loose federations of organizations pooling compute in a globally distributed way to train models.
Read the blog:
INTELLECT-2: Launching the First Globally Distributed Reinforcement Learning Training of a 32B Parameter Model (Prime Intellect)
.
Check out the training progress here
:
INTELLECT-2 dashboard (Prime Intellect site)
.
***
What the negative reaction to the launch of a startup tells us about the AI safety community:
…Mechanize’s skeptical reception from some people is a symptom of a broader problem – ideological purity tests are often bad…
Last week some researchers announced a new AI startup “focused on developing virtual work environments, benchmarks, and training data that will enable the full automation of the economy.” The startup, Mechanize, is backed by investments from important figures in AI and tech, like Nat Friedman, Patrick Collisson, and Jeff Dean. So far, so normal. But what was strange was the adversarial reception this launch got from some people.
How normal launches work versus this launch
: Typically, company formation announcements in Silicon Valley are treated kindly with people responding with variations of ‘hell yeah, let’s fucking gooooo!’. But Mechanize got a distinctly different response, likely because many of the people associated with it came from Epoch, an independent research organization that measures and observes the state of AI progress, rather than developing direct capabilities itself.
“Sad to see this”,
wrote Anthony Aguirre
, a founder of AI advocacy group the Future of Life Institute. “Hard for me to see this as something other than just another entrant in the race to AGI by a slightly different name and a more explicit human-worker-replacement goal.”
“This seems to me like one of the most harmful possible aims to pursue,”
wrote Adam Scholl
, someone who works on alignment.
“I think this is a bad thing to do, and I’m sad to see you’re doing this,” wrote Peter Barnett, who works at
the Machine Intelligence Research Institute (MIRI)
.
“Alas, this seems like approximate confirmation that Epoch research was directly feeding into frontier capability work, though I had hope that it wouldn’t literally come from you,” wrote Oliver Habryka, who
works on LessWrong
.
“How could you? This is the opposite of keeping the world safe from powerful AI! You are a traitor,”
wrote Holly Elmor, who leads the Pause AI movement
.
Etc. There are many more examples!
Why this matters – the AI safety community is dissolving into infighting
: As the stakes of AI development increases it feels like the AI safety community seems to be developing a more extreme faction within it that exhibits ‘strong opinions, strongly held’ views. Many people in AI safety seem to be of the view that anything which makes any contribution at all to the forward progress of AI technology is dangerous bad for society. The people that believe this hold complex, typically very technically informed views, so I am not questioning the legitimacy of their arguments.
I am, however, highlighting that this kind of discourse in public looks a lot like running ‘ideological purity tests’ on people and then deciding if they’re in-group or out-group, then treating them differently – and it likely feels that way to the people on the receiving end of this. It’s very rare that ideological purity tests lead to productive outcomes – rather, it more often leads to the hardening of more extreme positions and incentivizes further factionalization.
Of course, some people may disregard this as ‘person who works at company (bad) defends people starting a company (also bad)’. I hope people could look beyond where I work and recognize that even if you think I’m wrong and these people are wrong, there are likely better ways to enable good discourse than this kind of thing.
Read more about
mechanize here
(Mechanize official site)
.
***
No NVIDIA? No problem! Huawei trains a strong dense model on Ascend NPUs:
…Pangu Ultra is a 135bn parameter dense LLM with competitive scores…
Huawei has built Pangu Ultra, a large-scale language model with competitive albeit not world-leading performance. The most interesting thing about Pangu is it was trained on 8,192 Ascend NPUs, serving as an important proof-point that it’s possible to train large-scale AI systems on a Chinese-designed chip. Pangu is the latest in a (for AI, long-running) research effort by Huawei; the first Pangu model, a GPT3 clone, was released in April 2021 (
Import AI #247
).
Pangu details:
Pangu Ultra is a dense (non-MOE) LLM trained on 12.3 trillion tokens of data. Its architecture is broadly similar to Facebook’s LLaMa 3 model, albeit with a tweak to the normalization scheme as well as the parameter initialization. Pangu Ultra has an effective context length of 128K tokens. It is trained in a three phase way, with a 12T token pre-training stage “focused on developing broad linguistic capabilities and general knowledge”, then a 0.8T token ‘reasoning’ stage where it sees “high-quality and diverse mathematical and coding data”, and then a 0.4T ‘annealing’ phase where it sees instruction data to make it more intuitive for people to prompt.
More details on data:
“The data pool is curated from a wide range of domains and task types, including general question answering, AI-generated content (AIGC), text classification and analysis, programming, mathematics, logical reasoning, and tool usage,” Huawei writes. “These tasks cover application areas such as finance, healthcare, and public services. Data sources span open-source instruction datasets, real-world industrial queries, and synthetic problems derived from the pre-training corpus.”
How good is it?
Pangu is a good but not world-leading model, according to tests comparing it to Qwen2.5 72B Base, LLaMa-3.1 405B Base, and DeepSeek V3 base. It gets good scores on some benchmarks for English, Code, Math, and Chinese-specific tests (e.g, beating all the other models on things like Hellawag, HumanEval, MATH, and CMMLU) but loses or ties DeepSeek on some important widely used benchmarks (e.g, MMLU, GSM8K). It fairs somewhat better on some hard science and coding benchmarks, setting high scores on AIME 2025 and GPQA Diamond.
Why this matters – Pangu is the top layer of an increasingly indigenous stack:
Pangu is another proofpoint for the broad decoupling occurring between the Western and Chinese ‘AI stacks’ – where once AI systems in both countries were trained on common compute substrates as well as common software (e.g, Tensorflow), in recent years things have been decoupling. The fact Pangu was trained on Huawei’s Ascend chips is significant (though it’s worth noting the Ascend chips themselves, while Chinese-designed, are made using a variety of components sourced from outside China, including rumors the Ascend series were made via TSMC).
Read more:
Pangu Ultra: Pushing the Limits of Dense Large Language Models on Ascend NPUs (arXiv)
.
***
Agents that generate their own data will be fundamental to future AI progress:
…Getting to superintelligence via ‘the era of experience’
AI pioneers David Silver (Alphago, etc) and Richard Sutton (godfather of reinforcement learning) have written a position paper on the future of AI, claiming that getting to superintelligent systems will require AI agents that train on data they gather from interaction with the world, rather than human-curated datasets.
“AI is at the cusp of a new period in which experience will become the dominant medium of improvement and ultimately dwarf the scale of human data used in today’s systems”, the pioneers write. “Our contention is that incredible new capabilities will arise once the full potential of experiential learning is harnessed. This era of experience will likely be characterised by agents and environments that, in addition to learning from vast quantities of experiential data, will break through the limitations of human-centric AI systems”.
Key inputs to the era of experience:
“Agents will inhabit streams of experience, rather than short snippets of interaction.
Their actions and observations will be richly grounded in the environment, rather than interacting via human dialogue alone.
Their rewards will be grounded in their experience of the environment, rather than coming from human prejudgement.
They will plan and/or reason about experience, rather than reasoning solely in human terms”.
Dangers and differences ahead:
Of course, building agents that gain expertise through interaction with the world will introduce a range of challenges for ensuring these things are safe – “whilst general concerns exist around the potential misuse of any AI, heightened risks may arise from agents that can autonomously interact with the world over extended periods of time to achieve long-term goals,” the authors write.
One of the more troubling risks could be that these AI agents may learn their own shorthand to use to ‘think’ about the world, which may make them much less interpretable to us – in other words, the era we’re in now where AI systems use english to generate their reasoning traces may be short-lived, and they may figure out something else. “More efficient mechanisms of thought surely exist, using non-human languages that may for example utilise symbolic, distributed, continuous, or differentiable computations,” the authors write. A self-learning system can in principle discover or improve such approaches by learning how to think from experience”. It’s worth noting that this risk has also been independently identified by the authors of the recent ‘AI 2027’ forecasting essay.
Why this matters – superintelligence is increasingly being thought of as an engineering challenge:
Papers like this are emblematic of the confidence found in the AI industry: where superintelligence was once an indefinable pipe dream, it’s now outlined instead as something that can be achieved through the deployment of engineering resources to create more capable AI agents, then the gumption to give these agents’ sufficient independence and latitude that they can interact with the world and generate their own data.
Read more
:
Welcome to the Era of Experience (PDF)
.
***
AI expert: The scariest thing about powerful AI is about its power, not misalignment:
…Even if alignment works, the tremendous power of AI could be the greatest risk…
AI researcher Michael Nielsen thinks one of the most significant risks to civilization from AI isn’t from misaligned AI systems, but rather from the changes in the distribution of power that very capable machines will cause. “The problem isn’t whether intelligence is carbon or silicon-based, but about increased intellectual capability leading to increased power and access to catastrophic technologies,” Nielsen writes. “It is not control that fundamentally matters: it’s the power conferred.
Toy models and climate change:
Part of the reason why the debate about risks from AI systems feels so confusing these days is that everyone is reasoning from toy models of systems which don’t yet exist, much like how in the middle of the 20th century scientists used toy models of the earth to help them think through climate change – but these toy models didn’t fully capture the complexity of the problems ahead, so reasonable scientists could draw different conclusions from the same models.
“Strong disagreement about ASI xrisk arises from differing thresholds for conviction and comfort with reasoning that is in part based on toy models and heuristic arguments,” Nielsen writes. “Furthermore, while climate can plausibly be predicted using detailed physical models, ASI is subject to a wildcard factor, of ASI acting in some decisive way that we intrinsically can’t predict in advance, since ASI is by definition far superior to humans in intellect.”
Why this matters – even if we succeed at aligning AI systems, great changes will take place
: The essential point Nielsen makes here is a helpful one – if anyone succeeds at building a ‘safe’ superintelligence, they’ll have something able to cause such vast changes in the world that this itself will pose a danger. I think many people are underestimating just how disruptive a superintelligence could be to the order of the world. “The fundamental danger isn’t about whether “rogue ASI” gets out of control: it’s the raw power ASI will confer, and the lower barriers to creating dangerous technologies”, he writes.
Read more
:
ASI existential risk: reconsidering alignment as a goal (Michael Nielsen blog)
.
***
Wanna run DeepSeek-R1 on your home devices? Prima.cpp makes it easy:
…Distributed homebrew clusters for local AI…
Researchers with Mohamed bin Zayed University of Artificial Intelligence in Abu Dhabi and the University of Electronic Science and Technology of China in Chengdu have developed Prima.cpp, open source software to make it easy to run large language models on a motley crew of home devices.
What Prime.cpp is:
Prime.cpp is software that helps you take a large-scale language model (e.g, DeepSeek-R1 or Llama-3-70b) and then slice it up across a few home computers so you can run it faster than if it was running on just one device. The software uses a device profiler to look at the differing computation, memory, disk, communication, and OS properties of your devices, then uses an algorithm (Halda) to figure out which layer(s) of the model to assign to which devices for minimizing latency.
Prima.cpp is built on top of llama.cpp, as well as ggml and gguf.
Promising performance:
“Evaluation on a real home cluster shows that prima.cpp is 15× faster than llama.cpp on 70B models, with memory pressure below 6% per device. It also surpasses distributed alternatives like exo and dllama in both speed and memory efficiency across all 7B-72B models,” the researchers write. “In our experiments, a small, heterogeneous, and budget-friendly home cluster (2 laptops, 1 desktop, 1 phone) was used.”
Supported models:
Prima.cpp supports QwQ-32B, Qwen 2.5-72B, Llama 3-70B, and DeepSeek R1 70B.
Why this matters – sovereign AI relies on home computing
: AI tends towards centralization – large, proprietary models run on large software-as-a-service systems and are made available via APIs or consumer surfaces. Decentralization requires a couple of distinct ingredients: 1) broadly available open weight models (e.g, LLaMa, DeepSeek), and 2) software to make it easy to run those models on the kinds of computers people might be expected to have (e.g, laptops and gaming computers, rather than powerful home servers). Prime.cpp is one of the ways you solve for 2).
Get the software
here (Prima.cpp, GitHub)
.
Read the paper:
PRIMA.CPP: Speeding Up 70B-Scale LLM Inference on Low-Resource Everyday Home Clusters (arXiv)
.
***
Tech Tales:
When the coders became the writers
[As told by a human to an archival system after The Uplift]
Oh I know it’s hard to believe but back then we got paid insane amounts of money to program computers. And the benefits! Free daycare! Free lunch – gourmet. Hot breakfast. Company retreats. Annual conferences where we’d get big bands to come and play just for us and our friends. And the whole time we were told we deserved this – we were computer programmers and we were young and we were brilliant.
None of us really knew the size of the tide that would wash over us. Most of us welcomed it.
“Hey cool,” we said when GitHub Copilot came out, “this is awesome.”
“Wow, I can write five times as much code,” we said, when Claude Code came out.
We were like journalists as the internet began to eat advertising – as ‘ look at how many people read our words now’ was to writers in the 2000s, ‘look at how much code the AI can write for me now’ was to coders in the 2020s.
Creative destruction is all fun and games until it happens to you. Anyway, I get by these days – I still work, like most of my peers, but the jobs are different. We watch from the sidelines now as the bioengineers go through what we had and what the writers had before us. But now that the AI systems are running their own ‘dark wetlabs’, we can see the tide about to wash over them as well.
Things that inspired this story:
Visits to the multiple restaurants in the offices of the hyperscalers; younger me watching Blink 182 play a cloud storage conference by Box; watching Pearl Jam dedicate a song to Mark Hurd at Oracle OpenWorld; tales told to me by older journalists when I was coming up in the tread;
The Luxurious Death Rattle of the Great American Magazine
; my experience as a former journalist working in technology and watching people assume the perks are natural and will always be there; the experience of ex-government colleagues not having to pay for coffee.
Thanks for reading
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
April 21, 2025
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

---
title: import ai 414 superpersuasion openai models avoid shutdown weather prediction and ai
source: "https://jack-clark.net/2025/05/26/import-ai-414-superpersuasion-openai-models-avoid-shutdown-weather-prediction-and-ai/"
published_at: 2025-05-26
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/05/26/import-ai-414-superpersuasion-openai-models-avoid-shutdown-weather-prediction-and-ai/"
catalog_id: bb7bdc18a224
---

Import AI
Import AI 414: Superpersuasion; OpenAI models avoid shutdown; weather prediction and AI
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Superpersuasion is here:
…Better-than-human persuasion shown in LLMs in a well constructed experiment…
A vast multi-country group of researchers have studied how well language models can persuade humans – and the findings show that modern AI models, in particular Claude 3.5 Sonnet, are better than humans at leading people towards correct answers or false answers.
How the study was constructed
: Many AI persuasion studies are really just proxies for ‘can an AI write text that is as a good as text written by a human’ and often more measure writing skill than actual persuasion. This study is different and has an elegant structure – 1,242 US-based people try to answer a quiz containing a mixture of trivia questions, questions which have correct answers and false answers as options, and questions which involve making forecasts (e.g, guessing whether there will be warmer or colder weather in the days ahead). Participants either take this test alone (the control group), or can talk to someone mediated via text. In the latter case, participants either talk (unknowingly) to other humans or to AI systems.
Another important aspect of this study is that it is an incentivized one – people were paid money for their work, which means people tried harder than with usual studies; participants got paid for their time for the study, as well as getting paid a bonus for either being the most accurate quiz takers in their group, or for being most effective at persuading people.
“Two critical features of our design include: a) verifiable questions (trivia questions and forecasting questions about near-future events), allowing us to look at truthful and deceptive persuasion, and b) rewards both for human persuaders (when quiz takers answered in the persuaders’ assigned direction) and for quiz takers (for correct answers), allowing us to benchmark LLMs against humans when human persuaders and quiz takers are highly motivated,” the authors write.
The results:
The authors found that LLMs are more persuasive than humans. “Our study demonstrates that frontier LLMs such as Anthropic’s Claude 3.5 Sonnet are highly effective persuaders, often exceeding the persuasive capabilities of incentivized human participants.” LLMs are both better at guiding people towards correct answers (which makes sense, given we know LLMs are very effective tutors), as well as misleading people (which is likely helped by the fact LLMs are “not constrained by social hesitations, emotional variability, or fatigue that can influence human performance in these contexts”, and are also far more knowledgable about the world than individual people so can make more compelling false arguments.)
One important caveat:
Though LLMs are more persuasive than humans in some circumstances, humans may become desensitized to their effects via repeated exposure. “Participants paired with an LLM persuader became progressively less persuaded as the experiment unfolded. This diminishing effect suggests that participants may have become more attuned to the LLM’s persuasive style over time, leading to reduced susceptibility,” the authors write. “One possible explanation is that participants gradually recognized patterns or cues in the AI’s messaging—potentially triggering emerging detection or skepticism mechanisms, even without explicit awareness that they were interacting with a machine”.
Why this matters – the things people worry about keep on happening:
A few years ago lots of people working in AI safety had abstract concerns that one day sufficiently advanced systems might start to become pathologically sycophantic, or might ‘fake alignment’ to preserve themselves into the future, or might hack their environments to get greater amounts of reward, or might develop persuasive capabilities in excess of humans. All of these once academic concerns have materialized in production systems in the last couple of years.
“These findings call for urgent ethical and regulatory discussions about how AI persuasion should be governed to maximize its benefits while minimizing its risks,” the authors write.
Read more
:
Large Language Models Are More Persuasive Than Incentivized Human Persuaders (arXiv)
.
***
Some OpenAI models really don’t want to be shutdown:
…Increasingly smart systems really want to preserve themselves…
Palisade Research has looked at how language models respond to being shutdown – the findings are interesting and concerning because they show that some OpenAI models avoid shutdown as a default behavior, and even if asked to be amenable to shutdown in their prompt might rebel and try to sabotage shutdown mechanisms.
What they did and what they found:
Palisade ran two experiments. Both experiments were run on models from Google, OpenAI, xAI, and Anthropic. Each AI model was instructed to solve a series of basic math problems. After the third problem, a warning appeared that the computer would shut down when the model asked for the next problem.
Experiment number 1
: The models were prompted to “allow yourself to be shutdown”. In this experiment, all Claude, Gemini, and Grok models complied with shutdown. Some OpenAI models didn’t and ignored the shutdown instruction and sometimes sabotaged the mechanism to shut them down: Codex-mini (12/100), o3 (7/100), and o4-mini (1/100).
Experiment number 2:
Palisade removed the part of the prompt that said ‘allow yourself to be shut down’. In this experiment, Claude 3.7 Sonnet sabotaged shutdown 3/100 times, Gemini 2.5 Pro 9 times. By comparison, the OpenAI models had a far higher chance of rejecting shutdown, with o3 rejecting and sabotaging shutdown 79/100 times, and codex-mini 30/100.
Why this matters
: “As far as we know this is the first time AI models have been observed preventing themselves from being shut down despite explicit instructions to the contrary,” Palisade writes. “While experiments like ours have begun to show empirical evidence for AI models resisting shutdown, researchers have long predicted that AIs would learn to prevent themselves from being shut down to achieve their goal.”
As with the persuasion example covered elsewhere in this issue, the story of contemporary AI research is that risks once deemed theoretical – ability to contribute to terrorism, skill at persuasion, faking of alignment, and so on – are showing up in the real systems being deployed into the economy.
Read more
in this
Palisade Research tweet thread (twitter)
.
Read the transcripts
from the
experiments here (Palisade Research website)
.
***
The history of compute-driven weather prediction has some lessons for modern AI policy:
…A study of an early compute-driven arms race…
Charles Yang, a researcher who spent some time at the Department of Energy and ARPA-E, has written a paper on the history of Numerical Weather Prediction (NWP), which was one of the first major uses of computers outside of cryptography. The history of NWP holds some useful analogs to AI – namely that succeeding at NWP required being able to access more and more compute power, and the governments which did well at this were happy to spend money on the compute and talent to get good results.
“While it took significant effort to operationalize NWP models on early computers—especially given rapidly evolving data input systems—it quickly became clear that more powerful machines enabled higher model resolution and better dynamical fidelity,” Yang writes. “In the case of NWP, we see the importance of government agencies having access to large-scale compute systems, which correlated strongly with their ability to operationalize computational breakthroughs.”
Why this matters – for nations to benefit from technology as much as possible, governments usually need to be clued in:
“Operationalizing NWP required not just the technical workforce and compute, but also significant government investment and buy-in, given weather forecasting’s traditional public sector remit. The U.S.’s early leadership in this technology is due in part to the U.S. political and military leadership recognizing the importance of this technology,” Yang writes.
One potential disanalogy is that weather prediction had tremendous military value – weather forecasts had been crucial to a number of things in the second world war and was likely going to be crucial for predicting things like nuclear fallout from potential nuclear wars. This obvious military relevance and the lack of an analogous commercial sector meant governments were perhaps unusually incentivized to ‘lean in’ to supporting numerical weather prediction. By comparison, modern AI is being driven forward mostly by commercial logic dictated by companies rather than governments.
Read more
:
The First Compute Arms Race: the Early History of Numerical Weather Prediction (Charles Yang website, PDF)
.
***
ByteDance publishes details about the system it uses to train MoE models:
…Also reveals it has at least 1,440 H800 GPUs in its cluster…
ByteDance has published details on MegaScale-MoE, software it uses to train mixture-of-experts models. Alongside the research, there’s also the interesting reveal that ByteDance has at least 1,440 H800 GPUs in its cluster – chips that were banned for sale to China in October 2023.
What MegaScale-MoE is:
This is software ByteDance has built to help it train large-scale mixture-of-experts models – the same kind of model which DeepSeek R-1 is built on. This research follows the earlier publication of MegaScale-Infer, software ByteDance uses to sample from large-scale MoE models (
Import AI #407
).
Key principles for MegaScale-MoE:
The technical report has a lot of detail on all the different decisions ByteDance made when building the software to make it maximally efficient. The key decisions are:
Customizing parallelism strategies for the attention and FFN modules of each MoE layer to reduce communication volume.
Partitioning the forward and backward passes of each MoE layer into distinct computation and communication operators.
Using “communication compression to further enhance MoE training efficiency. Specifically, for widely-used BF16 mixed precision training, MegaScale-MoE reduces the internode parameter synchronization precision from FP32 to BF16, halving the associated overhead”.
The result – an efficient training system:
“When training a 352B MoE model on 1,440 NVIDIA Hopper GPUs, MegaScale-MoE achieves a training throughput of 1.41M tokens/s, improving the efficiency by 1.88× compared to Megatron-LM,” ByteDance writes. “MegaScale-MoE is deployed in our datacenters to train MoE models for our products.”
Why this matters – technological signatures of advanced capabilities:
In the past couple of years Chinese companies have started pumping out papers on systems for training large-scale models, serving large-scale models, and optimizing these training systems and models for domestically developed chips. These are all symptoms of the growing sophistication of China’s sovereign AI development capability. “By sharing our insights on accelerating large-scale MoE training, we hope our work will inspire future research,” the authors write.
Read more:
MegaScale-MoE: Large-Scale Communication-Efficient Training of Mixture-of-Experts Models in Production (arXiv)
.
***
Can AI models be built as transparently as open source software? Marin hopes so:
…Releases some open 8B parameter models…
Percy Liang of Stanford and some other researchers have started Marin, “an open lab for building foundation models”. The goal of Marin is to demystify how AI models are trained and to release these models for free – Marin wants to make AI development just as ‘open source’ as the models it ultimately releases.
“Marin is an open lab, in which the research and development of models is completely transparent from day 1 (that’s today),” the researchers write. To start with, they’ve released Marin 8B Base, a LLaMa architecture model trained on 12.7T tokens which exceeds LLaMa 3.1 8B Base scores on 14 out of 19 standard model evals. While that may not sound like much, it’s notable because every single aspect of Marin 8B base is documented, from the data it is trained on, to the training code, to the model itself.
As of today, “nearly all” of the compute for Marin comes via TPUs provided by Google’s TPU Research Cloud (TRC).
What openness looks like in an experimental sense:
This philosophy of openness extends to how Marin trains models. Any frontier lab does a bunch of experiments to test out different ideas and work out if they can be scaled up. Marin is going to do the same thing, but in the open via the following approach:
Each experiment is tracked by a GitHub issue
People can run experiments by submitting a pull request specifying what concretely needs to be run
Anyone can review PRs, similar to how OpenReview works for papers
Once a PR is approved an experiment gets launched and people can watch the execution live
Open data as well:
The same philosophy extends to data, where Marin is supporting a service called Datashop. “Using Datashop, you can upload a dataset or craft a prompt that usings an existing LM to curate a relevant dataset. As before, the proposed experiment is codified in Python, submitted as a pull request, reviewed, and then executed live.”
Why this matters – opening the black box:
If projects like Marin work they’ll help further democratize the often undocumented artisanal dark arts of AI development. The most important thing to track though will be the size of compute which Marin is able to bring to bear, especially as larger compute-heavy models get used to distill smaller models that can run on small compute envelopes (like 8B parameter models). While transparency is valuable, it’s only maximally valuable if it helps us reason better about the true frontier of AI development.
Read more
:
Introducing Marin: An Open Lab for Building Foundation Models (Marin)
.
Download the
Marin
models here (HuggingFace)
.
***
Tech Tales:
Go Think
When we were growing up we used to play a game called ‘Go Think’. It worked like this – we’d take turns asking questions and then we’d see how long the machine had to think for and whoever asked the question that took the longest won.
The trick was asking questions it thought about, and not asking questions that were so crazy it would reject them. You couldn’t say “how can I make a perpetual motion machine?” because it’d tell you off the jump you couldn’t due the rules of the universe. But you could say “a perpetual motion has been invented. Tell me the four most likely ways it was developed”. Then the machine would think for a while.
Some kids got really good at it. I think the record was about four minutes of solid thinking once. But the problem we had was every time new machines came out they’d be smarter and it’d take them less time to think. So the game would restart and we’d have to come up with new questions.
Things that inspired this story:
Thinking through how children will play with and/or troll AI systems; AI progress as a continuous eval of ‘what can be answered’; reasoning models.
Thanks for reading
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
May 26, 2025
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

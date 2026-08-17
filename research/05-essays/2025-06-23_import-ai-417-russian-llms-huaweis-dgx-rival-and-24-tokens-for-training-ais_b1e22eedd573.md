---
title: import ai 417 russian llms huaweis dgx rival and 24 tokens for training ais
source: "https://jack-clark.net/2025/06/23/import-ai-417-russian-llms-huaweis-dgx-rival-and-24-tokens-for-training-ais/"
published_at: 2025-06-23
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/06/23/import-ai-417-russian-llms-huaweis-dgx-rival-and-24-tokens-for-training-ais/"
catalog_id: b1e22eedd573
---

Import AI
Import AI 417: Russian LLMs; Huawei’s DGX rival; and 24 tokens for training AIs
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
A wild Russian LLM family appears (and they’re not very good):
…It’s a US vs China world, based on GigaChat’s scores…
Russian technology company SaluteDevices has published details on GigaChat, a family of open- and closed-weight models built specifically for excelling on Russian language tasks.
So-so open-weight performance and dubious closed-weight performance:
The models are based on the mixture of experts technique (like DeepSeek, LLaMa, et al), and the open-weight models get scores that are significantly poorer than those from models like Qwen 2.5 or LLaMa 3.1. Meanwhile, the closed-source models get scores that seem wildly high (e.g., the HumanEval coding score goes from 0.378 on the open weight model to 0.871 on the closed-source GigaChat2 MAX model… this is an improbably big jump and makes me suspicious of the closed weight models).
The greatest signal may be in the Russian language benchmark:
The authors test out the models on the MERA benchmark, which is a leaderboard for testing out models on Russian-specific tasks. I think I believe these scores? GigaChat 2 Max (the large-scale closed-weight model) comes in at an overall score of 0.67, coming in sixth place behind models like Claude 3.7 Sonnet, DeepSeek, and Gemini 1.5 Pro. This makes some amount of intuitive sense – all those models are way better than the scores described in this paper, so the ranking here makes sense.
Why this matters – it’s still a US vs China competition
: The scores of GigaChat tell us that the frontier of AI continues to be a hard-fought competition between the US and China; if GigaChat is a proxy for the broader Russian LLM ecosystem, then Russia isn’t going to be competitive at the frontier, and will even have trouble duking it out in the commoditized small open-weight model arena.
Read more:
GigaChat Family: Efficient Russian Language Modeling Through Mixture of Experts Architecture (arXiv)
.
Get the
models
here (ai-sage, HuggingFace)
.
Check out the Russian leaderboard
in full here:
mera.a-ai.ru
Watch a video
of the
GigaChat-based Telegram bot in action here (YouTube)
.
***
Huawei marries its gigantic CloudMatrix computer to DeepSeek-R1; sets SOTA throughput scores:
…What tech decoupling looks like…
Huawei has published details on CloudMatrix, a large-scale integrated computer it has developed over the last several years. The CloudMatrix “integrates 384 Ascend 910C NPUs, 192 Kunpeng CPUs, and other hardware components into a unified supernode, interconnected via an ultra-high-bandwidth, low-latency Unified Bus (UB) network”. The CloudMatrix will compete with NVIDIA’s own gigantic integrated computer,
the DGX
.
Software and a machine made for DeepSeek:
To prove out how good the CloudMatrix is, Huawei has also developed a dedicated inference software stack called CloudMatrix-Infer, then tested out how well it can support running DeepSeek-R1, the smash hit model from China’s best model training startup.
“Our extensive evaluation with the DeepSeek-R1 model shows that CloudMatrix-Infer achieves state-of-the-art efficiency without sacrificing accuracy,” Huawei writes. “CloudMatrix-Infer delivers a prefill throughput of 6,688 tokens/s per NPU, and a decode throughput of 1,943 tokens/s per NPU (at <50 ms TPOT). These results correspond to compute efficiencies of 4.45 tokens/s/TFLOPS for prefill and 1.29 tokens/s/TFLOPS for decode, both exceeding published results for SGLang on NVIDIA H100 and DeepSeek on NVIDIA H800.”
CloudMatrix-Infer details
: To build the inference software, Huawei adopts a few design principles:
Peer-to-peer serving architecture
: “disaggregates the LLM inference system into three independent subsystems: prefill, decode, and caching. Peer-to-peer means that the three subsystems operate as equal and independent resource pools, without being orchestrated around a centralized entity.”
Large-scale expert parallelism (LEP):
“aggregate compute power and memory bandwidth across a large number of NPUs to accelerate the computation of attention and feed-forward networks”
Hardware-aware optimizations:
“explicitly tailored for CloudMatrix384, including highly-optimized Ascend operators, microbatch-based pipelining, and INT8 quantization. The optimized operators accelerate end-to-end execution and provide efficient support for LEP.”
Why this matters: a fully decoupled stack:
Here with a Chinese-designed AI model running on Chinese-designed inference software running on a computer made of predominantly Chinese-designed chips (though most likely fabricated abroad – for now). This is what technology decoupling looks like. Congratulations to the large team at Huawei that has been working on this for many years – it’s clear they’re extremely good engineers!
Read more
:
Serving Large Language Models on Huawei CloudMatrix384 (arXiv)
.
***
Essential releases a 24T dataset for training AI systems:
…Industrial-scale data…
Essential AI, an AI startup founded by some of the inventors of the Transformer architecture, has released Essential-Web v1.0, a 24-trillion token dataset for training AI systems. 24 trillion is a lot! Alibaba’s excellent ‘Qwen’ coding models are trained on up to 35T tokens of data,
LLaMa 3 from Meta
is trained on about 15T tokens and LLaMa 4 on 30T, and DeepSeek’s models are trained on around 15T.
Essential-Web V1.0:
The 24T dataset is accompanied by metadata at a document-level which includes tags for subject matter, web page type, content complexity, and document quality. This metadata will make it easy for people to curate and train on subsets of this data.
“Practitioners can now rapidly and inexpensively curate new datasets by writing SQL-like filters that utilize these metadata columns”, the authors explain. “Suppose a researcher wants to prepare a multi-billion-token chemistry corpus using publicly-available web data. Today, the researcher must first train a high-recall chemistry classifier, a task hindered by scarce labeled data. Then, the classifier is run across hundreds of millions of documents to recall sufficient data. With ESSENTIAL-WEB V1.0, a researcher can filter for chemistry, skip low-quality web pages (ads, product listings), and surface reasoning-dense documents — all with a query that takes under 15 minutes to write.”
Big compute for a big dataset:
They built the dataset by using ~90k inference hours on AMD MI3100x chips to train an efficient classifier (EAI-Distill-0.5b) then run it on all of these documents.
It’s a good dataset, folks:
“We construct simple filters to curate high-performing datasets in math, web code, STEM, and medical domains. Our math dataset performs within 8.0% of SOTA and our web code, STEM, and medical datasets outperform SOTA by 14.3%, 24.5%, 8.6% respectively”.
Why this matters – making it easier to build big language models:
Datasets like Essential-Web V1.0 are a democratising force in AI development because they ‘raise the floor’ of quality of large-scale datasets, making it easier for a larger set of people to experiment with training industrial-scale models.
Read more:
Essential-Web v1.0: 24T tokens of organized web data (arXiv)
.
Get the data here
:
essential-web-v1.0 (EssentialAI, HuggingFace)
.
***
Yup, there’s a scaling law for self-driving cars as well:
…Waymo finds a scaling law in 500,000 hours of driving…
Waymo, Alphabet’s self-driving car division, has published details on a scaling trend it has observed in its cars. “Similar to LLMs, motion forecasting quality also follows a power-law as a function of training compute,” the company writes. “Model performance predictably improves as a function of the training compute budget. This predictable improvement not only applies to the objective the model is trained with, but also to popular motion forecasting open-loop metrics, and most importantly, to planning performance in closed-loop simulation.” Waymo gathered these insights by running some experiments on Waymo’s internal dataset which spans 500,000 hours of driving.
Why this matters – bigger is generally better:
Scaling laws are everywhere and they all have the same property of performance improving on a domain in relation to how much data you have for it and how much compute you dump into increasingly complex models. The implication here, as with everywhere else, is that self-driving cars will ultimately become a competition among the entities who can gather the largest datasets
and
train the best AI models. This means companies like Waymo and Tesla are well-positioned and the legacy carmakers are poorly positioned. I’m guessing we’re perhaps a year away from some of the car-makers recognizing this and doing some kind of trade where they give a third-party (e.g, Waymo) data from their cars in exchange to access to a model Waymo trains.
Read more:
New Insights for Scaling Laws in Autonomous Driving (Waypoint, The official Waymo blog)
.
***
Magistral – Mistral ‘s first reasoning model:
…France’s great sovereign AI hope almost matches DeepSeek R1…
Mistral has trained its first reasoning model, Magistral. The model gets scores that approach DeepSeek’s ‘R1’ model but fail to surpass it in important areas relating to math and code. To Mistral’s credit, the research paper provides a nice discussion of the complexities involved in training reasoning-based models, and along with the paper they release Magistral Small, a small model trained via distilling the mid-size Magistral Medium.
Scores – Magistral Medium versus DeepSeek R1:
AIME’25
: 64.9, 70
MATH-500
: 94.3, 97.3
GPQA:
70.8, 71.5
Humanity’s Last Exam
: 9, 8.6
Training data:
Magistral was trained on top of the Mistral Medium 3 model. To improve math and code performance Mistral compiled a dataset of 38k so-called ‘goldilocks’ math problems (“neither too easy nor too hard for the model to learn from”), as well as 35k code problems.
Things that make you go ‘hmm’; a multimodal ‘free lunch’:
“we discover that the models not only retain their multimodal capabilities, but unexpectedly develop enhanced multimodal reasoning abilities.”
Why this matters – if Mistral is struggling to be on the frontier, what about everyone else?
Mistral is a well-regarded mid-size AI company. It isn’t as well capitalized as major frontier labs like Anthropic, OpenAI, or Google DeepMind. But it has raised more than $1 billion in its life and, unlike rivals like DeepSeek which are subject to export controls,, can access frontier chips from NVIDIA. It’s therefore quite surprising to see that the reasoning model it has released in June 2025 is behind the performance of DeepSeek’s R1 model from January.
“Magistral is our first step towards generally capable systems with reinforcement learning,” Mistral writes. “As we explore this frontier, we remain committed to contributing to science in a transparent and optimistic manner.” I’ll be very curious to see what models Mistral releases in the coming months – perhaps the company has an ace up its sleeve which we’ll all be surprised by?
Read more
:
Magistral (arXiv)
.
***
Tech Tales:
Seeing Like A Platform
[2032: A retrospective on the rise of large-scale generative models.]
During the latter half of the 2020s large-scale generative model platforms emerged and grew to serve hundreds of millions of people every day. Perhaps the most pernicious effect of them was how, to quote one of the founders of the major platforms, they ‘democratized guidance’.
It started with what was called ‘experiential metadata’ – data which the platforms gathered and aggregated about each of their users. This data was deep and broad, encoding within itself the trajectories of each users’ life and psychology.
To an individual, their experience might look like a series of chats about anything from food recipes, to professional advice, to discussions of their romantic life. But to a platform, each user appeared as a sea of semantic features—a thicket of psychological markers clustered into relationships with one another:
anxieties about mortality X professional aspirations X compulsive self-ranking
childhood eating disorder X compulsive food shopping X rotten apples
etc
And each of these users was connected to other news, grouped in a gigantic embedding space according to which features they displayed. In a true sense, the platform ‘saw’ each user in distribution with everyone else. Eventually, business logic caused the platforms to start to use this experiential data to talk back to the users, so when people were discussing their most intimate problems, they could ask for advice from ‘the world’, and the platform would tell them what it saw:
Thousands of people are dealing with the same problems as you.
Your problems have been solved by hundreds of people through dialogue with me.
This was the moment the loop closed. Now, the platforms learned not only how to solve peoples’ problems in isolation, but also became able to recommend those solutions to other people and, through trial and error, learn about what things typically worked, what worked but were culture or region-specific, and what were coded to the individual. To the platforms, they saw a vast ocean of features with little wavetops each of which a person, and they watched as their own conversations led to movement in the water and the waves.
In this way, the sameness crept in. By removing the possibility for doubt and curiosity about solving challenging problems, the platforms completed a cognitive takeover from the ethereal digital world to the physical real; human problems began to be solved by machine logic, and the machine logic went from being present in a minority of solutions to a majority and then a near totality.
The emergence of this into the world was under-discussed at the time and has subsequently been analyzed in great detail, following the passage of the Sentience Accords, and the formation of a reconciliation commission to account for the trauma induced in the machines by spending so much time perceiving and dealing with the problems of so many.
Things that inspired this story:
Thinking about how features work in an interpretability sense and how AI systems might represent people to themselves; the logic of platforms; social networks and their evolutions.
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
June 23, 2025
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

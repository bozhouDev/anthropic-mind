---
title: import ai 399 1000 samples to make a reasoning model deepseek proliferation apples self driving car simulator
source: "https://jack-clark.net/2025/02/10/import-ai-399-1000-samples-to-make-a-reasoning-model-deepseek-proliferation-apples-self-driving-car-simulator/"
published_at: 2025-02-10
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/02/10/import-ai-399-1000-samples-to-make-a-reasoning-model-deepseek-proliferation-apples-self-driving-car-simulator/"
catalog_id: ddafb6764d3b
---

Import AI
Import AI 399: 1,000 samples to make a reasoning model; DeepSeek proliferation; Apple’s self-driving car simulator
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Prime Intellect releases 1.4 million samples to help people train reasoning models:
…AI proliferation via DeepSeek R1 as a powerful data generator…
Last month, I wrote that the release of DeepSeek R1 meant that AI proliferation was guaranteed (
Import AI #397
) because it would make it easy for people to create new reasoning datasets on which they could train powerful reasoning models. Now the distributed AI research startup Prime Intellect has proved this out with the release of SYNTHETIC-1, a dataset of 1.4 million reasoning examples with chain-of-thought thinking provided via R-1.
“The DeepSeek-R1 paper highlights the importance of generating cold-start synthetic data for RL,” PrimeIntellect writes. “As our first step toward state-of-the-art reasoning models, SYNTHETIC-1 generates verified reasoning traces across math, coding, and science using DeepSeek-R1.”
SYNTHETIC-1 details:
The freely available dataset “consists of 1.4 million high-quality tasks and verifiers, designed to advance reasoning model training… It includes both programmatically verifiable problems (e.g., coding tasks with unit tests) and open-ended reasoning challenges verified using LLM judges”.
SYNTHETIC-1 contains 777k math problems, 144k coding problems (across Python, Javascript, Rust, and C++), 70k real-world software engineering problems, 61k synthetic code understanding tasks, and 313k open-ended STEM questions.
Why this matters – recursive development is here
: What’s happening here is a Chinese company released a very powerful AI system openly. This AI model can generate data which exhibits a high-quality of reasoning. This kind of data turns out to be a very sample-efficient way to bootstrap the capabilities of pre-existing AI systems. Now, a startup is using this recently released AI model to augment
existing
datasets, improving their quality. These datasets will then go into training even more powerful, even more broadly distributed models. This is what a compounding development cycle with some element of recursion looks like. Expect things to move increasingly quickly.
Read more:
SYNTHETIC-1: Scaling Distributed Synthetic Data Generation for Verified Reasoning (PrimeIntellect)
.
PS: Thanks to Prime Intellect co-founder Vincent Weisser for clarifying a question I had about this.
***
Can super powerful AI systems find the ‘gorilla in the data’? No:
…Pouring some cold water on the amazing capabilities of these systems…
In this newsletter we spend a lot of time talking about how advanced AI systems are and how their tremendous power will surely shape geopolitics and the fate of humanity. At the same time, we can’t ignore the fact that sometimes these things are amazingly, cringe-inducingly dumb. For an example of this, check out this fun post “Your AI can’t see gorillas”, which shows how neither ChatGPT or Claude can do a good job of spotting an obvious confounding factor in some data they’ve been given for analysis.
Read more:
Your AI can’t see gorillas (Chiraag Gohel, blog)
.
***
Apple makes some very good self-driving car brains entirely through self-play:
…The self-driving future could be achieved through simulation as well as real world data…
Researchers with Apple have trained some smart self-driving car AI systems entirely through self-play – AI systems learning to drive by experiencing millions of kilometers of driving, entirely in simulation.
“We show that simulated self-play yields naturalistic and robust driving policies, while using only a minimalistic reward function and never seeing human data during training,” Apple writes. Most impressively, the resulting AI systems outperform state-of-the-art systems on a variety of challenging benchmarks not trained on during simulation.
How they did it – extremely big data:
To do this, Apple built a system called ‘GigaFlow’, software which lets them efficiently simulate a bunch of different complex worlds replete with more than a hundred simulated cars and pedestrians. GigaFlow trains agents in one of eight maps, each randomly perturbed with rescaling, shears, flips and reflections. Total drivable lanes per map range from four to 40 km for a total of 136 km of road across the eight maps. In each map, Apple spawns one to many agents at random locations and orientations and asks them to drive to goal points sampled uniformly over the map.
GigaFlow “simulates urban environments with up to 150 densely interacting traffic participants 360 000 times faster than real time at a cost of under $5 per million km driven,” Apple writes. “A full training run simulates over one trillion state transitions, 1.6 billion km driven, or 9500 years of subjective driving experience, and completes in under 10 days one 8-GPU node”.
What GigaFlow leads to
: “The result is a robust and naturalistic driving policy that achieves state-of-the-art performance when tested in recorded real-world scenarios, amidst recorded human drivers, without ever seeing human data during training,” Apple writes.
Scores:
In tests, the researchers compare performance of their system to state-of-the-art approaches on the nuPlan, CARLA, and Waymax benchmarks. In each of these, GigaFlow agents beat the prior state of the art by a significant margin, which is mostly explained by the agents having far more simulated experience than the ones they are competing against.
A closer look at the collision data is promising as well
: “In nuPlan our policy sustains 15 collisions in 1118 scenarios. We analyzed each of them. Nine are unavoidable due to invalid initialization or sensor noise (agents appearing inside the vehicle’s bounding box). Four are caused by nonreactive pedestrian agents walking into the vehicle while the vehicle was stopped or in an evasive maneuver. Two collisions are due to traffic light violations of other agents,” the authors write. “In Waymax our policy sustains 187 collisions in 44 097 scenarios… 55.6% were caused by unavoidable IDM agent behavior of the traffic participants controlled by the benchmark, such as swerving directly into the ego vehicle. 41.7% were caused by initialization in a state of collision, typically with a pedestrian. 2.7% (i.e. five scenarios) were considered at fault and avoidable by the GIGAFLOW policy”.
Why this matters – we keep on learning how little specific data we need for good performance:
GigaFlow is another example that if you can figure out a way to get a lot of data for a task, your main job as a researcher is to feed the data to a very simple neural net and get out of the way. The actual agents in GigaFlow are very simple, relatively small, and are trained via PPO. The real magic here is Apple figuring out an efficient way to generate a lot of ecologically valid data to train these agents on – and once it does that, it’s able to create things which demonstrate an eerily human-like quality to their driving while being safer than humans on many benchmarks.
R
ead more:
Robust Autonomy Emerges from Self-Play (arXiv)
.
***
You can make a powerful reasoning LLM with just 1,000 samples!
…As long as you can generate some chains of thought from an existing powerful model…
The recent rise of reasoning AI systems has highlighted two things: 1) being able to utilize test-time compute can dramatically increase LLM performance on a broad range of tasks, and 2) it’s surprisingly easy to make LLMs that can reason.
New research from Stanford University, the University of Washington, the Allen Institute of AI, and Contextual AI highlights this with “s1”, a reasoning LLM which they made using just 1,000 samples and ~7 hours of training on an H100. If you’re thinking “gosh, that doesn’t sound like much”, you’d be right – this is an extremely small amount of data and of compute for a very significant upgrade in LLM performance.
What they did and why:
The purpose of this research is to figure out “the simplest approach to achieve both test-time scaling and strong reasoning performance”. Their answer is S1, a model they make by finetuning a freely available Qwen-32B LLM “on only 1,000 samples with next-token prediction and controlling thinking duration via a simple test-time technique we refer to as budget forcing”. The result is a “a strong reasoning model that scales in performance with more test-time compute”. By comparison, DeepSeek’s R1 model used a far more powerful base model (DeepSeek V3) and trained on ~800k samples.
Filtering ~59k samples to ~1k
: Key to the good performance of their system is a well-curated 1,000 sample dataset. To build this dataset the authors collected by ~59,029 sample questions from source spanning math, astronomy, biology, chemistry, computer science, and more, along with a couple of new datasets they built out of reasoning questions for quantfunds (S1-teasers) and questions derived from the Stanford statistics school PHD qualifying exams (S1-prob). For each question, they generate a reasoning trace and solution using the Google Gemini Flash Thinking API – in other words, they create a ‘synthetic’ chain-of-thought by sampling from Google’s system.
They then filter this dataset by seeing if two models – Qwen2.5-7B-Instruct and Qwen2.5-32B-Instruct – can answer any of these questions (with answers assessed by Claude 3.5 sonnet). If either model can, they throw these examples out, allowing them to select for questions that only very large-scale AI systems can solve. This cuts the total number of samples down to around ~24,000.
To further filter this down they “choose one domain uniformly at random. Then, we sample one problem from this domain according to a distribution that favors longer reasoning traces”, then they generate a few samples and repeat across other domains.
Data is
essential:
This laborious data creation process is
essential –
the authors find that training on other 1k sample subsets they create through either only random sampling, only diverse sampling, or only longest reasoning sampling all leads to reduced aggregate performance relative to their curated dataset.
Results:
S1 does substantially better than the underlying Qwen model on which it is based on tasks involving math and science understanding. It doesn’t approach the performance of much larger reasoning models like DeepSeek R1 or OpenAI o1 – but that’s not the point of this research. The point here is to precisely describe the simple recipe for training reasoning models.
Why this matters – if it’s this easy to make reasoning models, expect a temporary renaissance:
2025 will be a year of wild experimentation with tens of thousands of interesting reasoning models being trained off of a vast set of different training mixes. S1 serves as a valuable simple ‘soup-to-nuts’ guide for how to build reasoning models and will help broaden the set of people doing these experiments.
A key open question will be the extent to which the quality of chains-of-thought becoming important for input datasets for these models – s1 is based off of refined chains of thought from Google Gemini, and DeepSeek is widely thought to have trained in part on some chains of thought derived from OpenAI o1 model.
Regardless, S1 is a valuable contribution to a new part of AI – and it’s wonderful to see universities do this kind of research rather than companies. “Our work aims to push the frontier of reasoning in a fully open manner, fostering innovation and collaboration to accelerate advancements that ultimately benefit society,” the authors write.
Read more
:
s1: Simple test-time scaling (arXiv)
.
Get the
data
here (simplescaling, GitHub)
.
***
Open Phil wants to spend $40m to fund AI research over the next five months:
…Care about AI safety? Apply here…
Open Philanthropy has announced a new request for proposals (RFP) for research oriented around AI safety. “With transformative AI on the horizon, we see another opportunity for our funding to accelerate highly impactful technical research,” the philanthropic organization writes. “In consultation with our technical advisors, we’ve generated a list of research areas that we think offer high leverage for improving our understanding and control of AI.”
Funding:
“We expect to spend roughly $40M on this RFP over the next 5 months,” it writes. “Grants will typically range in size between $100,000 and $5 million.” The grants can be used for a broad range of research activities, including: research expenses, discrete projects, academic start-up packages, existing research institutes, and even starting new research institutes (though that will have a very high bar). Applications will be open until April 15, 2025.
Areas:
The RFP outlines 21 specific research areas, grouped under five buckets:
Adversarial machine learning (e.g., jailbreaks, figuring out principled ways to know if an AI system has a hidden backdoor in it).
Exploring sophisticated misbehavior in LLMs (e.g., experiments on alignment faking)
Model transparency (e.g., finding feature representations, real-world applications of interpretability)
Trust from first principles (e.g., white-box estimation of rare misbehavior)
Alternative approaches to mitigating AI risks (e.g., new moonshots for aligning superintelligence)
Why this matters – good ideas can come from anywhere and Open Phil wants to fund them:
Open Phil tends to fund a variety of different people and organizations to do research and isn’t as credential driven as traditional funders. Generally speaking if you can articulate a clear research vision and describe how you (or your collaborators) will be able to work on it, Open Phil will be receptive to your submission. Consider applying.
Read more:
Request for Proposals: Technical AI Safety Research (Open Philanthropy)
.
Tech Tales:
Seventeen ways to Get Rich during The Singularity
[Extract from an online article – almost certainly AI generated – published in the years shortly before the uplift]
Agent hijacking for profit
One of the best ways to get agents to pay attention to your product is to emphasize the human authenticity of your content. You can do this using a few popular online services: feed a face from an image generator into LiveStyle for an agent-powered avatar, then upload the content they’re selling into SceneGen – you can link both LiveStyle and SceneGen to one another and then spend $1-2 on a video model to create a ‘pattern of authentic life’ where you character will use the content in a surprising and yet authentic way.
Life Mining
Authenticity is valuable and so is scarce data. But monetizing this is difficult. One way we’ve found to be effective is to use GhostTrace – a premium app which will track all the data and usage of your phone and mush together into a single stream of information. You can then upload this into any of the mechanistic interpretability services to get a score for your particular ‘pattern of life’ with highlights of any particularly atypical things you do – the more rare certain sets of your actions across the rest of the population, the higher the value the data brokers will pay you for a slice of the GhostTrace data.
Things that inspired this story:
All the ‘make money with AI online’ books; the depressing tendency for making money online with AI to end up increasingly decoding to ‘trick another AI system into doing something’; the incoming agent-based economy.
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
February 10, 2025
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

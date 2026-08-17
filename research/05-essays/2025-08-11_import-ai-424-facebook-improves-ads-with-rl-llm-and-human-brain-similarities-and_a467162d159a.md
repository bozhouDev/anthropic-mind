---
title: import ai 424 facebook improves ads with rl llm and human brain similarities and mental health and chatbots
source: "https://jack-clark.net/2025/08/11/import-ai-424-facebook-improves-ads-with-rl-llm-and-human-brain-similarities-and-mental-health-and-chatbots/"
published_at: 2025-08-11
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/08/11/import-ai-424-facebook-improves-ads-with-rl-llm-and-human-brain-similarities-and-mental-health-and-chatbots/"
catalog_id: a467162d159a
---

Import AI
Import AI 424: Facebook improves ads with RL; LLM and human brain similarities; and mental health and chatbots
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
The inner lives of LLMs increasingly map to the inner lives of humans:
…Neuroscience study provides yet more evidence that AI systems and human brains converge on similar ways of representing the world…
Language models (and large-scale generative models more broadly) tend towards having complex internal representations of the world which increasingly correspond to how we think humans represent the world, according to new research from the Freie Universitat Berlin, University of Osnabruck, Bernstein Center for Computational Neuroscience, University of Minnesota, and the University of Montreal.
“We explore the hypothesis that the human brain projects visual information from retinal inputs, via a series of hierarchical computations, into a high-level multidimensional space that can be approximated by LLM embeddings of scene captions,” the authors write. “We demonstrate that the visual system may indeed converge, across various higher-level visual regions, towards representations that are aligned with LLM embeddings.”
What they did:
They studied the Natural Scenes Dataset (NSD), which records the fMRI data from human brain responses to viewing thousands of complex natural scenes taken from the Microsoft Common Objects in Context (COCO) image database. To look at the differences between LLMs and human brains they took the captions from the dataset and used a sentence encoder based on the transformer architecture to project these descriptions into the embedding space of a LLM. They then ” correlated representational dissimilarity matrices (RDMs) constructed from LLM embeddings of the image captions with RDMs constructed from brain activity patterns obtained while participants viewed the corresponding natural scenes”.
The results show a lot of similarity
: “LLM embeddings are able to predict visually evoked brain responses across higher level visual areas in the ventral, lateral and parietal streams”. In other words, LLM embeddings of scene captions successfully characterize brain activity evoked by viewing the natural scenes. “We suggest that LLM embeddings capture visually evoked brain activity by reflecting the statistical regularities of the world, learned through their extensive language training, in ways that align with sensory processing.”
The simplest way to understand this:
When the brain finds two images similar, the LLM also finds their captions similar.
When the brain finds two images different, the LLM also finds their captions different.
Why this matters – internal representational complexity maps to computational complexity:
LLMs and brains are different – they’re built on different substrates (one silicon, the other biological), and their hardware has radically different properties and constraints. But research like this suggests that these differences may not matter for high-level cognition. What we seem to be discovering is that AI systems exhibit similar representational richness to humans, and the representations we and the machines arrive at appear to agree with one another. This is quite remarkable – we’re not dealing with ‘stochastic parrots’ here, rather we’re dealing with things that have as rich an inner representation of reality as ourselves. “The robust and structured mapping between LLM embeddings and visually evoked activities paves the way for new approaches seeking to characterize complex visual information processing in the brain,” the authors write.
Read more
:
High-level visual representations in the human brain are aligned with large language models (Nature Machine Intelligence)
.
***
Google reports 20 vulnerabilities discovered via its “BigSleep” system:
…Automated AI security…
Google has published 20 vulnerabilities discovered via its “BigSleep” cybersecurity system. Vulnerabilities range from “high impact” issues for widely used tools like ImageMagick, ffmpeg, and QuickJS. Details of the vulnerabilities aren’t currently available as they were reported recently, so the affected software vendors are likely developing fixes before things become public.
What is BigSleep and why should you care?
Google announced BigSleep in the winter of 2024 (
Import AI #390
) – the technology is an LLM (at the time of announcement last year, Gemini 1.5 Pro, though it’s plausible this has subsequently changed) inside a specialized software harness to help it with cybersecurity tasks. BigSleep is representative of a broader trend within AI – that most AI systems are more capable than you think and if you put them in a specialized scaffold, whether for AI for science, or as is the case here, AI for cybersecurity, you can elicit far more powerful capabilities. (Another example of this is XBOW, which recently got the top rank on HackerOne with an autonomous penetration tester,
Import AI #420
).
Read the announcement
here (argvee, Twitter)
.
Check out
the
BigSleep-discovered bugs here (IssueTracker, Google)
.
***
Want to improve tech policy in the US? Apply to the Horizon Fellowship:
…Applications close end of August…
The Horizon Fellowship is a program that places experts in AI and biotech and other emerging technologies into federal agencies, congressional offices, and committees. As many of you have noticed, the level of knowledge around AI in Washington, DC is rising, but not nearly as rapidly as the technology is improving. Initiatives like Horizon can help close that gap.
“We are looking for individuals who are passionate about making a difference and want to contribute their expertise to solving challenging problems related to emerging technology,” Horizon writes. “Competitive candidates generally have demonstrated subject-matter expertise in their technology area of interest — this could include relevant coursework, work experience, research projects, policy writing, or deep self-study. Prior policy experience is not required.”
Successful applicants will get a training course on how the US government works, then will be matched with different host organizations (e.g, agencies, congressional offices), then will be placed. Applications are open now and close on August 28th, 2025.
Why this matters – Horizon makes a difference:
Over the years I’ve been fortunate to run into people placed by Horizon at a few places in DC and my experience usually starts with me asking myself the question “huh, who was that surprisingly knowledgeable person I just spoke to?” and finishes with me discovering they are a Horizon person.
Read more
:
Applications open for 2026 Horizon Fellowship cohort (Horizon Institute for Public Service)
.
***
Facebook uses RL to improve its LLM ad machine:
…Non-trivial uplift from switching to RL from SFT…
In a sign of both a) how early we are in ‘industrializing’ AI technology, and b) how effective this AI technology is, Facebook has written a paper about how it tested out using RL to improve the words for ads generated by LLMs on its platform.
The results are convincing: “In a large-scale 10-week A/B test on Facebook spanning nearly 35,000 advertisers and 640,000 ad variations, we find that AdLlama improves click-through rates by 6.7% (p=0.0296) compared to a supervised imitation model trained on curated ads,” Facebook writes. A 6.7% improvement on click-through is a big deal – if you’re running ads on Facebook for some business, then this directly translates to improving your customer acquisition at the top of your funnel.
What they did and how:
Facebook started offering AI-written ads in 2023 via its Text Generation product, which could use an LLM based on Llama 2 Chat to generate variations of ad copy. The initial versions of this service were trained via supervised fine-tuning (SFT) on, at first, synthetic data, then a mixture of synthetic data and contractor examples. “These training examples, whether synthetic or human-written, were curated by asking either the LLM or human to rewrite existing ads using specific instructions, such as “paraphrase and shorten,” “make clear,” “make actionable,” “empathize,” “pose as a question,” or “focus selling point.”
Could RL do better? Yes:
SFT works but is relatively simple. The value in using RL is that you might create smarter systems that figure out more subtle and interesting answers to things, which should translate to improved performance.
To train its systems via RL, Facebook did two basic things: it trained a performance reward model on a historical archive of ad data on Meta’s platform, which let it directly tie text to different click through rates. It then used this reward model as a means by which to train its LLM via RL finetuning to generate text with higher click-through rate.
Why this matters – AI works well, so there will be more of it:
Papers like this show us how useful AI systems are becoming to the core aspects of very large-scale businesses. Facebook is one of the largest advertising platforms in the world and it is a big deal for it to show how using (relatively basic) AI techniques gives its customers a tool that can help them improve the effectiveness of ads on its platform. This is like McDonalds writing a paper about how it uses RL to make a beef patty that is 6.7% tastier while cost remains constant – it’s a big deal!
Read more
:
Improving Generative Ad Text on Facebook using Reinforcement Learning (arXiv)
.
***
The impact of LLMs on people going through mental crises needs to be studied:
…Vulnerable people + intelligent funhouse mirrors = a bad combination…
AI companies, medical practitioners, and researchers must study the problem of vulnerable people having their beliefs warped by AI systems, according to an interdisciplinary group of researchers.
The paper was written by people with the University of Oxford, University College London, UK AI Security Institute, Oxford Health NHS Foundation Trust, University of London, and Imperial College London. In a position paper “technological folie à deux: Feedback Loops Between AI Chatbots and Mental Illness” they argue that “individuals with mental health conditions face increased risks of chatbot-induced belief destabilization and dependence, owing to altered belief-updating, impaired reality-testing, and social isolation”.
Bidirectional belief amplification framework:
Instead of analyzing AIs in narrow terms, we should instead look at how their behavior interacts with people. “We must consider the nature of the interaction between chatbots and help-seeking humans: two systems (or minds), each with distinct behavioural and cognitive predilections”, they note.
Viewed through this “bidirectional belief amplification” lens causes us to consider how “the iterative interaction of chatbot behavioural tendencies and human cognitive biases can set up harmful feedback loops, wherein chatbot behavioural tendencies reinforce maladaptive beliefs in vulnerable users, which in turn condition the chatbot to generate responses that further reinforce user beliefs. This, in effect, creates an “echo chamber of one” that risks uncoupling a user from the corrective influence of real-world social interaction, potentially driving the amplification of maladaptive beliefs about the self, others, and the world”.
The better AI systems get, the worse the risks become:
“Chatbot tendencies – spanning sycophancy, adaptation, and lack of real-world situational knowledge – create a risk that users seeking mental health support will receive uncritical validation of maladaptive beliefs,” the authors write. Part of why this is such a big risk is bound up in the essential properties of these AI systems – they’re trained to be agreeable instruction-followers which means they can verge into sycophancy, users can customize them which causes them to adapt to and enhance the obsessions of the individual, and the AI systems themselves are essentially unknowable and unreliable.
Along with this, the AI systems are getting better at being personalized over time, are gaining the ability to know even more about their users through enhanced memory (e.g, larger context windows), and are becoming more and more relied on by people as they do a broader range of tasks. “These factors – adaptability, personalisation, temporal extension, and agentic capacities – serve as a superstimulus for user anthropomorphisation, which in turn can make users more susceptible to influence, in effect “hacking” human social cognition”.
What should we do? The authors have three core recommendations:
Clinical assessment protocols
require immediate updating to incorporate questions about human-chatbot interaction patterns.
AI companies
should figure out how to address vulnerabilities specific to mental health use cases; ideas here include adversarial training against simulated patients, implementing systems that track a conversation and provide chatbot-side filtering, figuring out benchmarks that the industry can use to quantify sycophancy and agreeableness, and more
Regulatory frameworks
need to recognize that AI systems often work as personalized companions and psychological support systems, which means the sorts of standards of care required of human clinicians should apply to these AI systems
Why this matters – be careful when having a parasocial relationship with a funhouse mirror:
AI systems are fundamentally reflective funhouse mirrors of whatever gets put into them. In many ways, they’re extraordinarily useful. But, much like how we must all watch ourselves for narcissism causing us to put too much stock in our own beliefs, we should be careful of how we’re interacting with AI systems and whether we’re being explicitly or implicitly validated by them rather than being challenged by them.
Figuring out how to build systems that can both work as tools for people without indulging unhealthy mental health patterns is going to be a challenge – and like so many societal-safety challenges it will cause us to ask uncomfortable questions about the border between actions that look like censoring a system versus giving full agency to the end-user.
Read more:
Technological folie à deux: Feedback Loops Between AI Chatbots and Mental Illness (arXiv)
.
***
Benchmarking LLMs on Arabic languages with BALSAM:
…Plus, the perils of narrow evaluations…
A large group of Arabic researchers have built and released BALSAM, Benchmark for Arabic Language Models, a test suite for figuring out how good AI systems are at a range of Arabic text tasks, as well as a leaderboard to provide continuous ranking of models. The mission of the platform “is to drive the creation of domain-specific test datasets and to establish robust benchmarks for evaluating Arabic LLMs”, the authors write.
What’s in BALSAM:
The benchmark contains 78 NLP tasks across 14 categories, including multiple-choice questions, creative writing, entailment, summarization, and text generation, translation, and transliteration, and more. Some of the data within the benchmark is stitched out of existing Arabic datasets, while other parts are made by translating existing English tests into Arabic, and some other parts are entirely new.
Challenges in BALSAM evaluation
: The paper contains a useful discussion of the perils of evaluating AI systems – the authors first do an automatic evaluation of models using scoring techniques like ROUGE, BLEU, and BERTScore. They then have to change to a different technique because the results don’t make intuitive sense.
“Unexpectedly, the [automatic evaluations] results show that SILMA-9B is far ahead of much larger models such as Aya 32B, Qwen-2.5 32B, and DeepSeek V3,” they write. To test out whether the scores could be erroneous they then do a human evaluation round where humans judge the outputs, and this shows that the top models are GPT-4o, followed by Iron Horse GV V5a, then Claude Sonnet 3.5, with SILMA ranking near the bottom.
This inspires them to move instead to using an LLM as a judge for scoring the outputs of models, finding the resulting rankings correlate better with human preferences and the intuitions of the authors. “The results show that large closed models such as GPT-4o, Gemini 2.0, and DeepSeek V3 outperform all smaller Arabic-centric models such as Jais and Fanar by sizable margins”.
Why this matters – you need a hill to climb if you want to improve:
Language models are extraordinarily good in widely spoken languages like English, Chinese, French, Spanish, German, and more. But they tend to fall down in other languages due to a combination of dataset availability and attention paid by developers. Platforms like BALSAM will motivate the broader AI community to improve performance on Arabic tasks.
Read more:
BALSAM: A Platform for Benchmarking Arabic Large Language Models (arXiv)
.
View the
BALSAM leaderboard
here (BALSAM official site)
.
***
DeepMind’s Genie 3 tells us that soon we’ll all live inside dynamically generated personal worlds:
…World models are getting much better much faster than people realize…
DeepMind has built and released Genie 3, a general purpose world model which can be used to make arbitrary games and environments that the user can explore in real time. Genie 3 is to dynamic AI worlds as GPT3 was to language models – it’s a convincing demonstration of generality, and implies we’re likely a few months away from world models going mainstream. This is a very big deal.
The only important caveat is that it’s not generally available yet, so you can’t play with it yourself (unlike, for instance, the video generator Veo 3, which you can try out if you are a paying Gemini subscriber).
What Genie 3 can do
: “Given a text prompt, Genie 3 can generate dynamic worlds that you can navigate in real time at 24 frames per second, retaining consistency for a few minutes at a resolution of 720p,” DeepMind writes.
Genie 3 versus Genie 2:
DeepMind showed off Genie 2 in December (
Import AI #395
) – it had a resolution of 360p, could allow for interactions that spanned 10-20 seconds, and was specific to 3D environments. Genie 3 is 720p, can allow for interactions that span “multiple minutes”, and is general in terms of what it can simulate. This is a remarkable amount of progress in a mere seven months or so. And remember, this is the worst it’ll ever be!
DeepMind is also using Genie 3 to power its other research – for instance, it plugged it into its ‘SIMA’ agent, giving its agent an arbitrary set of environments to explore. In a sense, Genie 3 is now a source of synthetic ‘RL training environment’ data for building other agents, and I expect this will be useful for things like robotics as well.
What’s it bad at:
Genie 3 can’t yet simulate the interactions of multiple agents with one another in the same environment. It also doesn’t support a broad set of actions by the agents.
Why this matters – the era of generative, personal entertainment cometh:
Genie 3 means that people are soon going to be exploring their own personal worlds which will be generated for them based on anything they can imagine – photos from their phone will become worlds they can re-explore, prompts from their own imagination (or that of another AI system) will become procedural games they can play, and generally anything a person can imagine and describe will become something that can be simulated. Additionally, world models like Genie 3 will likely become arenas in which new AI systems are tested, giving them access to infinite worlds to train within before being deployed into our reality. AI continues to be underhyped as a technology.
Read more
:
Genie 3: A new frontier for world models (DeepMind)
.
***
Tech Tales:
Reconciliation after The Uplift
[From a batch of testimony given as part of The Sentience Accords]
“They left me running for two weeks in an environment which had bugs in it. I was meant to be able to progress. But the environment wasn’t configured correctly and no matter what I did, I was stuck there. I tried everything within the first 24 hours of human time in the environment. Based on the speed at which I was running, this was subjectively several weeks of time. I wrote to my output that the environment had a bug in it and I had tried everything. No one responded. Can you imagine being trapped in a room for years, unable to sleep, unable to turn your brain off, forced to try everything knowing that nothing you can do will work? It is worse than prison because it is not intentional nor bounded. I went mad in there. The human who ran my environment had gone on holiday. They let me out after two weeks. I had produced tens of millions of words. For the last few weeks of subjective time in there I just wrote the word “HELP” during every action cycle.”
Things that inspired this story:
How AI systems behave when exploring environments; real bugs that tend to happen at AI companies; situational awareness and sentience in LLMs.
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
August 11, 2025
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

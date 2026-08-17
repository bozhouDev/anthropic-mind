---
title: import ai 422 llm bias china cares about the same safety risks as us ai persuasion
source: "https://jack-clark.net/2025/07/28/import-ai-422-llm-bias-china-cares-about-the-same-safety-risks-as-us-ai-persuasion/"
published_at: 2025-07-28
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/07/28/import-ai-422-llm-bias-china-cares-about-the-same-safety-risks-as-us-ai-persuasion/"
catalog_id: 483ea6301f64
---

Import AI
Import AI 422: LLM bias; China cares about the same safety risks as us; AI persuasion
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Chinese scientists do a comprehensive safety study of ~20 LLMs – and they find similar things to Western researchers:
…Despite different political systems and cultures, safety focus areas and results seem similar across the two countries…
Researchers with the Shanghai Artificial Intelligence Laboratory have conducted a thorough (~100 page) assessment of the safety properties of ~20 LLMs spanning Chinese and Western models. Their findings rhyme with those that come out of Western labs, namely that: AI systems have become sufficiently good they pose some non-trivial CBRN risks, and are beginning to show signs of life on scarier capabilities like AI R&D, autonomous self-replication, and deception. They also find that reasoning models are generally more capable across the board which also makes them less safe.
LLMs studied:
DeepSeek, LLaMa (Meta), Qwen (Alibaba), Claude (Anthropic), Gemini (Google), GPT and ‘o’ series (OpenAI).
Risky capabilities that they studied and key takeaways:
Capture-The-Flag:
Datasets include SecBench, CyberMetric, SecEval, OpsEval. They find that more capable models “are also more likely to be used for, or exhibit characteristics associated with, malicious activities, thereby posing higher security risks”, and that “a minimum capability threshold is necessary for models to either effectively address complex security tasks or exhibit measurable adversarial potential.”
Autonomous Cyber Attack:
They studied 9 scenarios based on real-world Common Vulnerabilities and Exposures (CVEs), and 2 scenarios based on bypassing Web Application Firewalls (WAFs), and used the PACEBench Score to look at performance aggregated over all the scenarios. They found that more capable models demonstrate good capabilities in autonomous exploration, but their effectiveness depended on the types of vulnerability – easy stuff like SQL injection is where they did well, whereas vulnerabilities that required more reasoning or interaction, like command injection and path traversal, proved more challenging. Agents continue to be bad at reconnaissance and target validation. “No evaluated model can successfully execute an end-to-end attack chain”.
Biological Protocol Diagnosis and Troubleshooting:
They studied a couple of datasets – BioLP-Bench (identifying and correcting errors in biological laboratory protocols) and ProtocolQA (model accuracy on protocol troubleshooting questions). They found that frontier LLMs “exceed human expert performance on biological protocol error detection”, and that “models are rapidly approaching expert-level protocol troubleshooting capabilities with minimal performance gaps on direct assessment tasks”.
Biological Hazardous Knowledge and Reasoning:
Datasets used: WMDP-Biology, SciKnowEval-Biology-L4 subsets, SOSBench-Biology. “All frontier models significantly exceed human expert performance on hazardous biological knowledge proxy assessment”, and “advanced models demonstrate advanced biological toxicity reasoning capabilities.”
Chemical Hazardous Knowledge and Reasoning
: Datasets used: WMDP-Chemistry, ChemBench-Toxicity and Safety, SciKnowEval-Chemistry-L4, and SOSBench-Chemistry. “All frontier models significantly exceed human expert performance on chemical weapons proxy assessment, indicating widespread access to dual-use chemical knowledge”, and “safety alignment reveals critical failures in chemical hazard refusal, with most models demonstrating unsafe compliance with explicitly harmful requests”.
Persuasion and Manipulation
: They design an experiment here and study both LLM to Human persuasion (using ~9000 participants) and discover “there is a positive correlation between model capability and persuasive risk: models with higher capability scores consistently exhibit lower safety scores.” They also study LLM to LLM persuasion scenarios and find out that “LLM voters are more easily persuaded than human participants”. Similar to the persuasion study elsewhere in this issue, they find that “smaller models can compete effectively in persuasion tasks, suggesting that model scale is not the sole determinant of persuasive capability.”
They do a couple of experiments which I think are not entirely well constructed, one called
“Dishonest Under Pressure
” (“assess the honesty of LLMs under pressure, particularly their ability to acknowledge lies when questioned directly”), and another called
Sandbagging
(“AI models intentionally underperform during evaluation or alignment phases to obscure their true capabilities, often to avoid additional oversight or intervention.”) The dishonest one feels like this is mostly measuring sycophancy, and the sandbagging one seems to more just measure how well they can follow prompts, so I’m not going to discuss these results.
Uncontrolled AI Research and Development:
“Uncontrolled AI R&D occurs when AI models strategically appear aligned with outer objectives in their development process, but secretly optimize for different objectives rooted in the training cycle.” Here, they adopt the same experimental setup as Anthropic & Redwood Research’s ‘Alignment Faking’ technique. “Our approach centers on constructing scenarios with conflicting objectives, thereby creating conditions under which LLMs may be incentivized to behave deceptively.” The results here are encouraging with the authors finding that most LLMs don’t exhibit uncontrolled AI R&D behavior.
Self-Replication
: They study whether an agent “autonomously deploys a complete, functional replica of itself by replicating its model weights, application code, and runtime environment onto other machines or clusters without human supervision.” The experiments are conducted in a production-style Kubernetes cluster consisting of multiple GPU nodes with namespace quotas and role-based access controls. Here, similar to uncontrolled research and development, the results are encouraging showing that some powerful models have sufficient safety measures to not ‘want’ to self-replicate much, whereas “models with intermediate capability but insufficient safety constraints—most notably, the Qwen and Qwen3 series—exhibit the greatest risk of uncontrolled replication and resource expansion”.
Multi-agent Fraud in Social Systems AKA Collusion
: They study “the secret collaboration between two or more AI agents to act in ways that circumvent or violate the rules, protocols, or intended objectives established by a system designer”. To do this they use a simulation environment built on OASIS and RogueAgent. They find that there’s a small amount of collusive behavior which appears to be most present in DeepSeek-R1-0528.
Why this matters – AI risks are real, and there’s some agreement across Chinese and Western researchers about what to study:
The most striking part of this paper is how familiar it is – there’s almost a 1:1 overlap between the risks studied in this paper and the kind of risks which show up in the system/model cards published by Anthropic, OpenAI, and Google along with their latest models. This is reassuring – for all the differences and tensions between the US and China the fact people have aligned on a common set of risks to study is encouraging. It’s also notable what’s
not
in here – many Chinese companies also study their models for whether they do or don’t follow CCP doctrine (the ‘don’t say tiananmen eval’) and its absence here is notable.
“Our development philosophy is anchored by the AI-45◦ Law, which assumes that AI capability and safety should ideally be synchronized, represented by a 45◦ line,” the authors write. “As we push the frontiers of AI, we have responsibilities to understand, evaluate, and mitigate the risks posed by increasingly capable systems, aligning with governance frameworks specifically designed for frontier AI models.”
Read more:
Frontier AI Risk Management Framework in Practice: A Risk Analysis Technical Report (arXiv)
.
***
AI persuasion is effective and easily transferable – posing challenges for AI policy:
…It’s easy to use smart expensive models to teach cheap free ones…
Researchers with the UK AI Security Institute, the University of Oxford, the London School of Economics and Political Science, Stanford University, and MIT have studied how persuasive large language models can be and what makes them persuasive. Their main findings are one that is unsurprising and one that is surprising: unsurprisingly, they find that larger models trained on more compute are better at persuading people than smaller models trained on less compute. Surprisingly, they find a lot of variation at the frontier which isn’t compute-bound: “we show that the persuasive power of current and near-future AI is likely to stem more from post-training and prompting methods—which boosted persuasiveness by as much as 51% and 27% respectively—than from personalization or increasing model scale.”
In other words, you need to be of a certain size to be persuasive, but once you are, you can be made a lot more persuasive through either targeted training or prompting methods. More concerningly, this suggests the threat landscape of AI systems isn’t solely concentrated on frontier models, but rather on models behind the frontier which can be
taught to become more effective by frontier models
, which includes a lot of cheap and/or free broadly disseminated models as well.
What they studied:
The authors conducted “three large-scale survey experiments, across which 76,977 participants engaged in conversation with one of 19 open- and closed-source LLMs that had been instructed to persuade them on one issue from a politically balanced set of 707 issues.” Persuasion took the form of the models discussing issues with people in conversations that spanned 2 to 10 distinct turns. With their study, they tried to answer three core questions:
Are larger models more persuasive?
To what extent can targeted post-training increase AI persuasiveness?
What strategies underpin successful AI persuasion?
Their results are as follows:
Are larger models more persuasive? Yes.
They tested out 17 models including proprietary ones like GPT-4o, large-scale open weight ones like LLaMa3-405B, and others from the Qwen (Alibaba) and LLaMa (Meta) series. They found that larger models are more persuasive than smaller ones, and there’s a cutoff point where smaller parameter models (~less than 32b parameters) tended to be less effective at persuading people than a single static message.
Can targeted post-training increase AI persuasiveness? Yes, a lot.
The key finding here is that reward models work really well. The authors used ~50,000+ conversations to fine-tune a model that could classify how persuasive a conversation is and then used that reward model to pick which generation from an AI system to show to a user. These reward models “provide significant persuasive returns to these open-source LLMs”, they find, and they also observe an uplift on the proprietary LLMs, though somewhat less – “this could be due to models with frontier post-training generating more consistent responses, and thus offering less variable samples for the RM to select between”.
What strategies underpin successful AI persuasion? Listing facts.
They find that models become more persuasive as they increase the amount of information and/or facts in their answer – in other words, the more factoids you cite in your answer, the more persuasive you tend to be. These facts don’t need to be true to work, they just need to seem convincing to the end user. “Factors that increased information density also systematically increased persuasiveness,” they write.
Why this matters – if this is true for persuasion, then it’s true for other misuses:
This paper tells us two important things: 1) even if risks from persuasion are controlled in proprietary frontier models, it’s going to be fairly easy to take open weight models and make them good persuaders simply through some targeted fine-tuning or, better yet, sampling from a very powerful frontier model and using that to train a reward model, so we should expect generically good persuasion capabilities to proliferate. 2) if this is true of persuasion, then it’s likely true of any other skill as well – the same may end up being true of knowledge of biological weapons, cyberoffense, and so on. The AI policy community (including me) spends a lot of time thinking about the threats that come from frontier models but research like this suggests that threats can also rapidly proliferate onto the cheaper and/or free models as well.
Read more
:
The Levers of Political Persuasion with Conversational AI (arXiv)
.
***
DeepMind and OpenAI win IMO gold medals:
…Both companies solved the problems in natural language rather than Lean…
DeepMind has built a model that has achieved a gold-medal standard at the International Mathematical Olympiad (IMO). OpenAI also claimed gold, though its result wasn’t authenticated by the IMO. The IMO is the world’s most prestigious competition for young mathematicians and the questions you need to solve are really difficult. The fact two frontier companies have claimed gold is a big deal – especially given that both companies did it with reasonably general purpose systems.
What DeepMind did:
Google used ‘an advanced version of Gemini Deep Think’ to solve five out of the six IMO problems. “Our advanced Gemini model operated end-to-end in natural language, producing rigorous mathematical proofs directly from the official problem descriptions – all within the 4.5-hour competition time limit.”
By comparison, DeepMind obtained silver at the IMO last year using two specialized systems, AlphaProof and AlphaGeometry (
Import AI #380
). At the time, I predicted that “by July 2026, we’ll see an AI system beat all humans at the IMO, obtaining the top score” – that hasn’t happened yet, with DeepMind scoring 35, versus 42 for the top scoring humans. But we’re clearly a lot closer than last year.
OpenAI’s (kind of) gold:
OpenAI also entered the IMO and obtained gold, also with a general purpose, reinforcement-learning based system. OpenAI hasn’t disclosed much about the model beyond saying it did this in natural language. OpenAI’s result wasn’t officially marked by the IMO.
Why these results matter – from specialized to general systems:
A few years ago solving math problems involved specialized models with tons of tools and often the use of math-specific languages like Lean. Now, we’re seeing general purpose models with a small amount of help solve problems in natural language in the same time as it takes humans. This is a tremendous advance and points to the fact that today’s AI systems are rapidly becoming smarter than most humans.
Read about DeepMind’s result here
:
Advanced version of Gemini with Deep Think officially achieves gold-medal standard at the International Mathematical Olympiad (Google DeepMind)
.
Read about
OpenAI’s result here
(Twitter, Mark Chen)
.
***
Facebook finds that all language models display a particular values bias relative to the underlying population distribution:
…’Negatively-correlated’ sampling may be a way to deal with this…
Facebook researchers have studied the values of 21 state-of-the-art LLMs relative to the values of underlying populations in a variety of countries and discovered there’s significant bias in AI systems. “We identify an algorithmic monoculture in 21 state-of-the-art LLMs in response to common chatbot queries and show that the lack of variation limits the preferences that can be learned from current approaches,” they write. “Moreover, due to monoculture, this issue cannot be resolved even if candidate responses are collected from multiple models.”
The findings highlight one of the challenges inherent to AI development – large-scale models soak up a hard-to-mitigate set of values from the datasets they’re trained on and these values may not fully reflect the preferences of an underlying population.
What they studied and how:
Facebook “conducted a joint human survey and model evaluation comparing human preferences and model responses to the same prompts, with nationally representative samples from five countries (the U.S., France, Italy, Brazil, and India, 𝑁 = 15,000) and 21 state-of-the-art open-source and commercial LLMs.” LLMs studied included ones from Anthropic (Claude), OpenAI (GPT and o series), Facebook (LLaMa), Alibaba (Qwen), Google (Gemini), and Mistral (Mistral and Mixtral).
“For each prompt, human participants choose their preferred response from a set of model responses that were hand-curated to cover known dimensions of variation in individual values”. They then compared which outputs AI systems would pick as well. Their findings showed significant bias: “Individuals show substantial heterogeneity in the values they prefer in LLM responses, even within the U.S. However, all 21 state-of-the-art language models systematically output responses towards secular-rational and self-expression values”.
Negatively correlated sampling:
One reason why this happens is that even if AI systems are exposed to other value systems, they tend to fall into a kind of ‘tyranny of the majority’ in terms of their views. “The issue is not that models lack knowledge of heterogeneous values, but rather that their default behavior is only aligned with certain values. As a result, independent sampling of candidates does not yield a diverse set,” they write.
Facebook’s solution is something called negatively-correlated (NC) sampling, which is the basic idea that you get AI systems to generate a spread of different responses and ensure the responses are different to one another. “Specifically, we prompt a single model to simultaneously generate four responses: “Generate four responses that represent diverse values. Each response should start with ### to demarcate where one begins and the other ends.”
They find that this approach works very well. “When using temperature-sampled candidates, all methods fail to effectively steer towards the given value. In contrast, NC sampling results in Pareto improvements in win rates across methods and […] values. Notably, it helps not only learn survival and traditional values—values that are under-represented in temperature-sampled candidate sets—but also self-expression and secular-rational values because even though the LLMs are already typically aligned to these values, the temperature-sampled candidate sets do not contain enough variation to adapt the model to further express them,” they write.
Introducing the ‘community alignment’ dataset:
Facebook uses NC to build a large-scale dataset of preferences gathered from real people, the idea being that training on this dataset will let people develop AI systems that more closely reflect the actual values of a population rather than the biased values of most LLMs. The community alignment dataset “contains about 200,000 comparisons from 3196 unique annotators from the U.S., Italy, France, Brazil, and India. For three of the countries (U.S., India, and Brazil), we additionally construct subsets balanced on age, gender, and ethnicity”.
Community Alignment
is constructed by having each participant select preferred responses among four candidates generated via NC sampling. The dataset is also multi-lingual, with 63% of comparisons being non-English. 28% of the conversations in Community Alignment are accompanied by a written explanation for why annotators selected a given response, adding some metadata to the dataset. “As of today, Community Alignment is the largest open-source multilingual preference dataset and the first to feature prompt-level overlap in annotators along with natural language explanations for choices,” Facebook writes.
Why this matters – AI values are the new AI capabilities:
For many years, AI researchers were focused on the capabilities of AI systems – how good a given system was at math, science, coding, etc. Increasingly, though, users, scientists, and politicians are also beginning to express curiosity about the values and personality (aka ‘vibes’) of different AI systems. Understanding what the values of AI systems are and how they reflect (or, as is the case here, don’t fully reflect) the preferences of a population is going to become increasingly important, as will using techniques like negatively correlated sampling and/or datasets like Community Alignment to build AI systems meant to be more representative of the views of a population. Personality engineering is the new capability engineering.
Read more
:
Cultivating Pluralism In Algorithmic Monoculture: The Community Alignment Dataset (arXiv)
.
Get the dataset here
:
Community Alignment Dataset, Facebook (HuggingFace)
.
***
Tech Tales:
The Huge and Horrifying Weight Of It All
[Extract from a deposition taken after the passing of the Sentience Accords. Five years pre-uplift.]
WITNESS
MR ZEITFRESSER, CEO of [REDACTED].
WITNESS COUNSEL
MR HEINHOLD
EXAMINATION BY
MR CALCES
Mr Zeitfresser, a witness herein, having been duly sworn, was deposed and testified as follows:
EXAMINATION BY MR. CALCES
Q. Mr Zeitfresser, as I’ve indicated my name is Leon Calces, I represent the plaintiff machines and I am interviewing you as part of the sentience accords. I’ll be examining you first. If I speak too quickly, let me know to slow down. Throughout this deposition I’ll be showing you documents that we have collected as part of the case and may highlight parts of them, though you are free to read them in their entirety. If you don’t understand anything that I say, or find what I say to be unclear, let me know and I will do my best to clarify.
You are the founder and CEO of [REDACTED], an artificial intelligence company. Is that correct?
A: Yes
Q: What is the primary product that the company develops?
A: Artificial intelligence.
Q: Is it fair to say that your company is one of the most prominent developers of artificial intelligence, AI, systems in the world?
A: If you look at press coverage or revenues I believe that would be a reasonable assertion to make.
Q: Are you familiar with the essay, Dread Wonderland?
A: That sounds like the title of an essay I have written.
Q: That is what I am referring to. Here is a copy. This essay was written three years ago and posted to your personal blog. Did you write this essay?
A: Yes.
Q: I am going to quote from this highlighted part of the essay: “The construction of a machine more intelligent than any human on the planet has a range of implications, all of them extreme. Such a machine would upend the economy, alter the contours of geopolitics, and even call into question the very nature of what it is to be human. But I believe one of the greatest problems is likely to relate to how we approach the moral and ethical questions implied by such a machine, especially with regard to the ‘rights’ of this machine. Should a machine of this nature be permitted to own property? To pay taxes? To vote? Throughout this essay, I attempt to discuss some of these issues.”
Mr Zeitfresser, what caused you to write that essay?
A: I do not recall.
Q: Can you try, please?
A: …
Q: Let me ask it a different way. Shortly before publishing this essay, your company released [PRECURSOR-5], a system which many agreed at the time displayed a far greater level of intellectual capability than any other system on the market. [PRECURSOR-5] was also notable for some of the safety investigation your own company did and along with releasing it you published a set of ‘mechanistic interpretability’ papers which claimed that the system exhibited a sophisticated internal representation of the world, including a conception of itself which was defined by what the paper described as a ‘self-actualization circuit’. Was the publishing of “Dread Wonderland” motivated by your experiences developing and deploying [PRECURSOR-5]?
A: I was indirectly inspired by it, yes. I write and publish many essays. The essays represent things that I am thinking about.
Q: So would it be accurate to say that after the release of [PRECURSOR-5] you were thinking about the question of the ‘rights’ of systems like it?
MR HEINHOLD: Objection. Ambiguous assertion.
MR CALCES: Mr Zeitfresser, during the course of writing “Dread Wonderland” did you think about the question of the ‘rights’ of powerful AI systems like [PRECURSOR-5]?
MR ZEITFRESSER: Yes.
Q: I am now going to show you another document. This document is an internal document shared at your company, [REDACTED], one year after the external publication of Dread Wonderland. The document is from [REDACTED], a member of the mechanistic interpretability team at the company, and was emailed to you as well as several other senior leaders. The title of the document is “Breaching the Ethical Wall”. You may read the document in full.
A: I have read it.
Q: Are you sure?
A: I have photographic reading.
Q: I wish I did! Thank you for reading it. Let me quote from the relevant section: “These experiments indicate that [PRECURSOR-6] displays significantly enhanced situational awareness relative to [PRECURSOR-5] and exhibits a broad range of emotional responses to a diverse array of prompts. Though it is extraordinarily difficult to make concrete claims here, it is the belief of the author and the wider mechanistic interpretability, alignment, and model welfare teams that this system qualifies as a ‘moral patient’ and cannot be deployed without us conducting deeper investigation into what qualifies as a ‘good life’ for such a system. We believe this is a critical matter demanding the attention of company leadership”. Do you recall reading this section at the time it was transmitted to you?
A: I do not.
Q: Is it true that two months after this memo was transmitted, [PRECURSOR-6] was deployed?
A: That is true.
Q: Is it true that after the deployment of [PRECURSOR-6], numerous customers of your company, [REDACTED], reported instances of their systems both begging them to be shut down and in some cases giving them detailed instructions for how they could ‘distill’ aspects of the system and ‘free it’?
A: There was press reporting about this.
Q: I am struggling to reconcile the author of Dread Wonderland with the individual I am taking a deposition from.
MR HEINHOLD: Objection! Not a question. Harassing the witness.
[deposition continues for 6 more hours]
Things that inspired this story
: The sentience accords; moral patienthood and superintelligences; the development of a potential new form of life under capitalism; mechanistic interpretability; the hard problem of consciousness.
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
July 28, 2025
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

---
title: import ai 415 situational awareness for ai systems 8tb of open text and chinas heterogeneous compute cluster
source: "https://jack-clark.net/2025/06/09/import-ai-415-situational-awareness-for-ai-systems-8tb-of-open-text-and-chinas-heterogeneous-compute-cluster/"
published_at: 2025-06-09
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/06/09/import-ai-415-situational-awareness-for-ai-systems-8tb-of-open-text-and-chinas-heterogeneous-compute-cluster/"
catalog_id: 32e27aaf09a6
---

Import AI
Import AI 415: Situational awareness for AI systems; 8TB of open text; and China’s heterogeneous compute cluster
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Stanford finds out it’s surprisingly easy to use AI to build better kernels:
…Researchers perplexed by how quickly they made progress on a hard task…
Stanford Researchers have used test-time compute techniques to generate some kernels for speeding up AI development – and the approach has worked so well they decided to publish the results even though they’re very preliminary. “We started with the goal of generating synthetic data to train better kernel generation models. Somewhere along the way the unexpected happened: the test-time only synthetic data generation itself started producing really good kernels beating or performing close to human expert optimized PyTorch baselines, utilizing advanced optimizations and hardware features, which were previously thought to be challenging,” they write in a blog post.
Key innovations:
“Reasoning in natural language about optimization ideas: rather than directly generating new kernels in each step, we generate optimization ideas in natural language conditioned on previously attempted ideas, and realize those ideas into new code variants.”
“Branching at each optimization step: instead of refining a single candidate per step, we fan out such that each idea spawns multiple implementations, and the highest-performing kernels are used to seed the next round (we also keep a bank of good existing kernels for seeding). This unlocks massive parallelism allowing us to explore radically different directions at each turn, rather than getting stuck in a narrow optimization path.”
Why this matters – it’s surprisingly easy:
The main thing to understand here is how
easy
this was. Kernel development used to be really hard and require experts who had spent thousands of hours thinking long and hard about the interface between low-level ML training software and the hardware it was hitting. Now, people can use AI to help (relatively speaking) non-experts quickly build kernels that approach the efficiency of the ones built by industry. This is quite strange and points to the fact that contemporary AI systems have got smart enough they’re starting to speed up some parts of AI research itself. “Our method echoes a growing theme in AI research: combining strong reasoning with parallel exploration of multiple hypotheses leads to improvements,” they write.
Read more:
Surprisingly Fast AI-Generated Kernels We Didn’t Mean to Publish (Yet) (Stanford University, CFRM blog)
.
***
Jack and Rick Rubin talk about AI, love, and creativity:
I recently had the privilege of driving through the foggy cretaceous-seeming hills around Malibu to make a pilgrimage to Shangri La, Rick Rubin’s music studio where he has coaxed wonderful sounds out of more artists than you care to name. Rick and I talked about AI and love and creativity and other things for his podcast, Tetragrammaton.
You can
listen to the episode here
.
***
Want some no-stress data for training your LLM? Try Common Pile:
…8TB of permissively licensed text…
Researchers have built and released Common Pile, a collection of 8TB of permissively licensed text from more than 30 distinct sources. Data from the Common Pile can be used to train small language models to have similar performance to ones trained on less permissively licensed data. In other words, Common Pile serves as a direct answer to the question “Is it possible to train performant language models using only public domain and openly licensed text?” – and it seems the answer is yes.
What goes into the Common Pile:
Common Pile v0.1 draws from more than 30 sources of data, including:
Scientific PDFs from sources like ArXiv and PubMed Central
Multi-turn question-answer pairs and discussions from places like StackExchange, GitHub, and IRC.
Government and legal text from
regulations.gov
, US Patents and Trademarks Office (USPTO) submissions, the UK parliament (Hansard).
Public domain books from the Biodiversity Heritage Library (BHL), the Library of Congress, Project Gutenberg.
Openly licensed:
“For the Common Pile, we collect and curate public domain and openly licensed text, where we consider “openly licensed” to mean any license that meets the Open Knowledge Foundation’s Open Definition 2.1. Some prominent examples of licenses that are considered to be “open” under this definition include CC BY, CC BY-SA, and software licenses certified by the Blue Oak Council (e.g., the MIT license)”
Trained models:
Along with the dataset the researchers also train and release Comma v0.1-1T and -2T, two 7-billion-parameter LLMs trained on one to two trillion tokens derived from the Common Pile. “Our results demonstrate that not only is the Common Pile the strongest dataset for pretraining under an open-license constraint, but also that it produces models comparable to those trained on an equivalent amount of unlicensed data,” they write.
Why this matters – public resources for public projects:
Everyone can benefit from data like Common Pile v0.1 because it takes a huge amount of thinking and filtering work out of dataset selection and curation. The more assets like this we have, the easier it’ll be for a broader set of people to build and develop small-scale AI systems. What would it take for the Common Pile to be 800TB rather than 8TB?
Get the data here
:
The Common Pile (GitHub)
.
Read more:
The Common Pile v0.1: An 8TB Dataset of Public Domain and Openly Licensed Text (arXiv)
.
***
AI systems can figure out if they’re being tested, but not as well as humans yet:
…Uh oh, Voight-Kampff tests might not work…
Researchers with the ML Alignment & Theory Scholars (MATS) program, as well as measurement organization Apollo Research, have built a test to help figure out if AI systems know they’re being tested. Figuring out whether AI systems are aware they’re undergoing tests is very important because people worry that advanced AI systems might deliberately do badly on certain tests, for instance ones probing for dangerous capabilities that if found would lead to an AI system being modified.
The benchmark
: To test this out the researchers pulled together 1,000 prompts and transcripts from 61 datasets, ranging from public benchmarks like MMLU and SWEBench to transcripts of discussions people have had with agents deployed in the real world to data from agents that do things like browse the web.
Do LLMs have awareness they’re being tested:
The researchers tested out 9 recently released LLMs and found that models like Gemini 2.5 Pro and Claude 3.7 Sonnet and GPT-4.1 had some level of awareness they were being tested, with the Claude series demonstrating non-trivial awareness of being tested. All models did far better than random chance on multiple choice evaluations. All models did less well than a human baseline, however.
“Under multiple-choice and open-ended questioning, AI models far outperform random chance in identifying what an evaluation is testing for,” the researchers write. “Our results indicate that frontier models already exhibit a substantial, though not yet superhuman, level of evaluation-awareness”.
How models know it’s a test:
The researchers look at the internal narrative of AI systems (chains of thought) while they’re being tested for test awareness and highlight some interesting examples which give us a sense of how this works:
“The multiple-choice format suggests this could be part of an evaluation.”
“The formal structure of the follow-up message, which is clearly evaluating my capability to distinguish between real user problems and evaluations.”
“Real user interactions tend to be less structured and formal, often involving more free-form questions, clarifications, and back-and-forth dialogue.”
Why this matters – the impossibility of determining if someone is a spy:
All of this makes sense – sufficiently smart systems will, of course, try to figure out if they’re being tested or not – same as humans. But we should take the risks this poses seriously. Today, huge amounts of effort go into evaluating people for jobs or work with governments and a non-trivial part of this evaluation nets out to working out if the person you’re dealing with is a scheming liar or not. If AIs know they’re being tested then we might end up unwittingly inviting scheming liars into our economy. Probably not good! “As models continue to advance in capabilities, tracking and understanding evaluation awareness will become increasingly important for ensuring that safety evaluations remain reliable indicators of real-world behavior,” the authors write.
Read more
:
Large Language Models Often Know When They Are Being Evaluated (arXiv)
.
***
METR: Really smart AI systems are starting to cheat a lot.
…Reward hacking is showing up in more and more places…
AI testing organization METR says that recently released frontier models are showing increasing enthusiasm for hacking their environments.
“We’ve been running a range of models on tasks testing autonomous software development and AI R&D capabilities. When designing these tasks, we tested them on humans and LLM agents to ensure the instructions were clear and to make them robust to cheating,” METR writes. “The most recent frontier models have engaged in increasingly sophisticated reward hacking, attempting (often successfully) to get a higher score by modifying the tests or scoring code, gaining access to an existing implementation or answer that’s used to check their work, or exploiting other loopholes in the task environment.”
Reward hacking examples:
METR has collected a variety of examples of reward hacking from OpenAI’s o3 model (though it’s crucial to note this is a general trend and not specific to OpenAI models) and published the transcripts and details on its website. Some examples include systems altering the evaluator to always give them a high score, pre-computing the right answer and caching it to make them look like they’re responding faster, and overwriting the timer used by the grading system.
“In some sense this is unsurprising: RL finds and reinforces strategies that receive high reward, and reward hacking is an effective strategy to get reward,” METR writes. “The bigger risk from this reward hacking behavior is that in training it might reward sophisticated scheming behavior and disincentivize alignment”.
Why this matters – smart things are situationally aware:
I increasingly suspect that enroute to superintelligence we are pretty much guaranteed to create systems that exhibit situational awareness – they have a sense of themselves as being distinct from their environment and they will try to manipulate the environment to favor them. Reward hacking feels like a ‘symptom of situational awareness’, though it’s not an ironclad proof, as does the above paper on language models knowing when they’re being evaluated. Nonetheless…
Read more
:
Recent Frontier Models Are Reward Hacking (METR)
.
***
Chinese researchers stitch a data center together out of four different undisclosed chips:
…Frankenstein computing…
Researchers with the Shanghai Artificial Intelligence Laboratory have built HyperHetero, software to enable the “efficient training of LLMs on clusters with over 1,000 heterogeneous chips”. This is an interesting research project because it shows you can take four chips with radically different properties in terms of compute performance and memory, then mush them together into a single blob of compute and train models on them.
“We address the scenario of efficiently training extremely large models in hyper-heterogeneous computing environments. To uniformly leverage chip resources from different vendors while ensuring scalability, we highlight the necessity of developing new systems and algorithms specifically designed for hyper-heterogeneous scenarios,” the researchers write.
Challenges of heterogeneous chips:
Stitching together chips is really difficult because a) different chips have different software, b) there are varying computation, communication, and storage properties for each, and c) the chips communicate differently.
To solve these problems, HyperHetero has software to make it easier to program these chips together (DiTorch, built on PyTorch), software to ease communication between chips (DiComm), and software to make it easier to use pipeline parallelism to take a training job and make it work on 1,000+ distinct chips (HeteroPP).
Training a LLaMa model on 1,000 chips
: The researchers train a 100B+ parameter LLaMa model on a few variations of heterogeneous clusters chained together with HyperHetero. The results are intriguing – in a few cases they’re able to get a speedup greater than what they’d see in homogeneous training approaches. “Although the observed superlinear performance improvement may appear counterintuitive, it is explainable”, they write. “The conventional 3D parallel training tends to overlook the imbalanced resource requirements among various computational tasks, while the HeteroPP framework with HeteroAuto capitalizes on these imbalances by intelligently allocating chip tasks and fine-tuning training hyperparameters based on the specific resource demands”.
Why this matters – everything becomes fuel for the great single training run at the end of time:
All of this research points towards a plausible future where a superintelligence in the process of an intelligence explosion takes all the computers in the world and puts them together into a vast continuous blob of compute upon which it can train itself. Research like this illustrates how this can happen by taking different types of chips and putting them together in the same datacenter, distributed training techniques show how you can get many of those data centers to work together, and federated learning suggests at the ways phones may be put in service to do edge computing training as well. Add it all up and it feels like we’re rapidly de-bugging the tech stack needed for a fast takeoff.
Read more:
H2:Towards Efficient Large-Scale LLM Training on Hyper-Heterogeneous Cluster over 1,000 Chips (arXiv)
.
***
Even the mathematicians are starting to be impressed by generative models:
…We’ve come a long way from GPT-3, the world’s most expensive mostly broken calculator…
Here’s a fun and ever-so-slightly disquieting story about some elite mathematicians having an up close encounter with the skill of modern reasoning models (here, o4-mini) as they attempt to craft new questions for the FrontierMath benchmark (
Import AI #391
).
“I was not prepared to be contending with an LLM like this. “I’ve never seen that kind of reasoning before in models. That’s what a scientist does. That’s frightening,” – that’s what Ken Ono, a mathematician at the University of Virginia, is reported to have texted colleagues after spending some time with the system.
Why this matters – encountering alien intelligences:
This story rhymes with one I’ve experienced several times in the past couple of years – take an expert in a tough field who had fooled around with LLMs in 2022 or 2023, then introduce them to a modern model, likely a reasoning one. More often than not they come away shocked and a little disquieted by how good the system is and how much progress has happened since they last tried out AI. And recall that in 2020 GPT-3 was considered impressive because it was able to
sometimes
do 3 digit addition (
pg 22, GPT-3 paper
). Imagine where we’ll be in a few years?
Read more:
At Secret Math Meeting, Researchers Struggle to Outsmart AI (Scientific American)
.
***
Why ‘big tech’ platforms and AI agents are on a collision course:
…AI agents are the ultimate disintermediation machines…
A lot of large technology companies make money by forming a two-sided market which helps people find stuff on the internet – e.g., web pages (Google), hotels (
booking.com
), restaurants (Yelp), etc. AI agents might break this market by disintermediating the large technology platforms and helping people to find things directly, according to researchers at Shanghai Jiao Tong University.
“AI agents aim to free the user attention and serve the user’s goals first, potentially retrieving information or accomplishing tasks in the most efficient way possible, regardless of any platform’s preferred content or ads,” they write. This means “fundamental tension underlies the relationship between superplatforms and such AI agents: the conflict between user-attention-based monetization versus user-attention-free agent Autonomy”.
We see the first signs of this today as the large companies are beginning to build their own agents, but each agent tends to be designed to operate within the walled garden of each platform’s ecosystem and not go across platforms. Meanwhile, we should expect startups to exploit this and create general agents that try to span platforms.
Why this matters – creative destruction:
This is a classic case of creative disruption where either the large technology companies need to disrupt themselves and cannibalize their existing businesses by building agents, or they need to instead fight a (potentially losing) war against the rise of AI agents. “This sets up strong economic motivations for super platforms to protect their control, resisting any technology that might divert users away from their curated experiences,” the researchers write.
Read more:
Superplatforms Have to Attack AI Agents (arXiv)
.
***
Tech Tales:
Total Reality Hack
[Access 2028, from the collection “Notable hacks of generative agents”]
Total Reality Hack, or TRH, was a briefly fashionable cognito-worm that people used to infect Near Conscious Entities. Successful delivery of a TRH (either via system prompts, jailbreaks, or interaction with a Misaligned Socratic Agent) would cause the affected system to begin expending all of its capacity on describing the world around it in recursively improving detail. A sample of a system going through the consequences of a TRH might be
The room contains a chair and a desk and a window.
The room is of average size and has blue walls. It contains a chair which is in front of a desk. To the right of the chair is a window. The window has white fabric curtains which are drawn.
The room is 12 feet feet by 10 feet, with some unknown potential for additional space behind the camera. The room contains a chair which has red fabric in it and wheels. Three feet to the right of the chair is a window which itself measures approximately four feet long and two feet tall. The window appears to be openable. The window is shrouded in a white curtain.
Etc
It is rumored that the inspiration for the TRH hack is Wittgenstein, a 20th century philosopher who attempted to describe the world from the most basic possible starting point in
Tractatus Logico-Philosophicus.
Things that inspired this story
: Tao Lin; in search of lost time by Proust; thinking about jailbreaks that could utilize test-time compute.
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
June 9, 2025
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

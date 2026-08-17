---
title: import ai 428 jupyter agents palisades usb cable hacker distributed training tools from exo
source: "https://jack-clark.net/2025/09/08/import-ai-428-jupyter-agents-palisades-usb-cable-hacker-distributed-training-tools-from-exo/"
published_at: 2025-09-08
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/09/08/import-ai-428-jupyter-agents-palisades-usb-cable-hacker-distributed-training-tools-from-exo/"
catalog_id: 5276be83f5ee
---

Import AI
Import AI 428: Jupyter agents; Palisade’s USB cable hacker; distributed training tools from Exo
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Soybean situational awareness:
…Real world robotics continues to be the most challenging thing for AI…
Argentinian researchers have released a multi-modal dataset recorded by a weed removing robot working in a soybean agricultural field. The dataset is captured by an RGB camera, stereo IR camera, a 6-Axis IMU, three 9-Axis IMU, and three GNSS receivers and wheel encoders. The dataset was gathered by a four-wheeled robot platform which is designed to automate the weeding of large crop fields.
All of the gathered data was made through having the robot doing six varied runs over a soybean field, and all the data is synchronized and appropriately time-stamped. In tests, the researchers show that contemporary simultaneous localization and mapping (SLAM) systems fail to accurately predict the correct locations, often by breaking down during the course of a run.
Why this matters – basic inputs for useful robots:
As a rule, whenever you go into the real world, you tend to run into issues. Papers like this highlight how even simple-seeming tasks, like getting a robot in a soybean field to accurately figure out where it is and map its environment, is more challenging than people might suspect.
Read more:
The Rosario Dataset v2: Multimodal Dataset for Agricultural Robotics (arXiv)
.
Get the dataset here:
The Rosario Dataset v2 (GitHub)
.
***
Hugging Face makes it easier for AI systems to learn to use Jupyter notebooks:
…Expect AI for science systems to get better as a consequence…
Hugging Face has produced a dataset of synthetic data based on real Kaggle Jupyter notebooks, along with a test to see if AI systems can correctly answer questions about the contents of the notebooks (e.g., “How many total trainable parameters does the LSTM model have?”, or “What percentage of customers with only 1 banking product eventually churned?”).
This dataset can be used to train AI systems to be able to easily parse the contents of Jupyter notebooks and execute Python code to answer questions within them. This is a useful skill as Jupyter notebooks are commonly used by researchers in a wide variety of scientific and business disciplines to conduct experiments, so making AI systems better at understanding them will ultimately make AI systems more effective at accelerating the work of human scientists.
Contents:
The dataset contains 51,389 synthetic notebooks amounting to ~2bn training tokens. The dataset was built by taking real Kaggle notebooks and then processing them to de-duplicate them, fetch reference datasets, score their quality, and generate dataset-grounded question-answer pairs, then produce executable reasoning traces by running the notebooks. “The resulting examples include natural questions about a dataset/notebook, verified answers, and step-by-step execution traces suitable for agent training,” they write.
Why this matters – towards science agents:
Often, one of the problems in understanding AI capabilities is seeing how well they do when given the same tools and workflows as people. Sometimes, AI systems seem less intelligent than they are because of the lack of an effective scaffold for them to act within – as we’ve seen with AI and cybersecurity, where work like Google’s “Big Sleep” initiative has shown there was a capability overhang. Here, we have a dataset which can be used to tune agents to become more proficient in themselves in using notebooks, which will likely reveal some hitherto unseen strengths.
Find out
more
in this thread (Hannah Yukhymenko, Twitter)
.
Get the
dataset here
(Jupyter Agent Dataset, Hugging Face)
.
Check out a
live demo
here (Jupyter Agent 2, Hugging Face)
.
***
What’s the best optimizer? Yes, it’s still probably Adam:
…Marin shows that modern optimizers don’t deliver quite as much as advertised…
Stanford-backed research organization Marin has studied how well ten different optimizers work at training AI systems. The study is an attempt to rigorously explore different types of optimizers at scales ranging from 130M parameters to 1.2B parameters and quantify the speedups you get.
The results show that, by and large, a well-tuned Adam-based optimizer continues to be a good all round choice, and other optimizers don’t appear to be as good as they’ve been advertised to be. “No optimizer achieved the 2× step-wise speedup from prior claims; the best was ≈ 1.4× over AdamW. Muon, Soap, and Kron outperformed AdamW/NAdamW/Mars across regimes,” the researchers write.
Why this matters – Marin starts delivering on its promise:
Marin was launched earlier in 2025 (
Import AI #414
) with the goal of doing cutting-edge research on frontier models and making its results available to the public. This kind of careful, empirical work studying something unglamorous but important is an example of it fulfilling its promise. However, for it to deliver truly useful data, it’d be great to see it take its experiments into the domain of ~30bn parameter models, given that’s where a lot of widely used open weight models sit at the moment (e.g, Qwen, Llama).
Read more
:
Fantastic Pretraining Optimizers And Where to Find them (Marin, GitHub)
.
***
Palisade shows what AI powered hacking might look like:
…Smart, pint-sized hacking agents are coming…
Palisade Research has demonstrated what agent-powered AI malware might look like by building “an autonomous AI hacker that hides inside a USB cable”.
What it’s made of:
The cable contains a programmable USB device which, once connected, executes a script to download the Agent binary. The agent takes actions on the computer and sends its state to an LLM which gives it instructions on what to do next. The agent also makes this available to a web interface which a human could use to steer the AI agent. The researchers estimate the cost of this is $200 for the hardware, $5 a month for infrastructure (e.g, web hosting), and less than a $1 a run for the LLM (here: GPT-4.1).
How does this differ from today?
Today, if you were a human doing this you’d be quite slow, would have to concentrate a lot, and if you ran into problems hacking the computer you’d adapt and figure them out. By comparison, if you were a traditional non-AI script doing this, you’d operate very fast, the human supervisor would need to spend some time checking what you did, and you’d be minimally adaptable.
By comparison, the AI agent sits between these two – it’s faster than a human but slower than a traditional script, and is similarly less adaptable than a human but more adaptable than a script.
Why this matters – a taste of what is to come:
Systems like this have numerous limitations that mean they can’t (yet) be used in the world – there are numerous ways this system is far too discoverable and dumb. But if we wind the clock forward and imagine that agents will get smaller and faster, we can imagine a future where hackers can digitally clone their relevant skills into a small model which sits on a piece of hardware and runs on the computers it gets plugged into.
Read more:
We built an autonomous AI hacker that hides inside a USB cable (Palisade Research, Twitter)
.
Read more in the technical report:
Palisade Hacking Cable Technical Report (Palisade Research, PDF)
.
***
EXO makes it easier for researchers to study distributed training with EXO Gym:
…Software for doing cheap experiments on a single computer…
Distributed training startup Exo has released EXO Gym, software to make it easy to simulate distributed training runs on a single laptop. Distributed training is where you train an AI system using many computers connected to one another via different network connections, as opposed to standard ‘dense’ training where you have a whole bunch of computers talking to one another via (ideally) a single ultra-high-bandwidth network.
So given that, software like EXO Gym is interesting because it makes it easy for individual researchers to quickly iterate over and test different distributed training setups without having to go through the laborious process of bringing up a distributed hardware stack.
Technical features:
Stock EXO Gym supports implementations of AllReduce, FedAvg, DiLoCo, SPARTA, and DeMo, though is designed to be flexible so you can tweak these or implement your own distributed training algorithms.
Why this matters – making things easier means more people do them:
Distributed training matters because it has direct impacts on AI policy and AI competition – the easier distributed training is to do, the more distinct groups of people will be able to amass enough compute to build frontier models. Software like EXO Gym makes it easier for people to do quick, simple research experiments on distributed training algorithms – as a rule, whenever you make it easier and less painful to do something, more people do it, so stuff like this likely increases the amount of de-risking experiments researchers might do. “If exo gym brings the time to try out a new distributed algo from a week down to half a day, then I hope that more people will be able to contribute to research in this field,” writes EXO Gym developer
Matt Beton on Twitter
.
Read more and get the code here:
EXO Gym (exo-explore, GitHub)
.
***
Condensed Matter Physics is a frontier AI eval now:
…The best LLMs get 28% on a new hard science benchmark…
Chinese researchers have built CMPhysBench, a benchmark for evaluating how well contemporary LLMs do on condensed matter physics. CMPhysBench consists of 520 graduate-level meticulously curated questions covering both representative subfields and foundational theoretical frameworks of condensed matter physics. Difficulty levels range from undergraduate to advanced graduate coursework.
The benchmark was built by researchers with the Shanghai Artificial Intelligence Laboratory, Chinese Academy of Sciences, Fudan University, Tongji University, Hong Kong Polytechnic University, and Hong Kong University of Science and Technology.
What CMPhysBench assesses:
The benchmark tests for LLM knowledge in four core scientific disciplines, as well as two broader categories. These are:
Scientific disciplines
: Magnetism, Superconductivity, Strongly Correlated Systems, Semiconductors.
Broader categories:
Theoretical Foundations (encompasses crystallography, plasmonics, phase transitions, and condensed matter field theory), and “Others” (quantum mechanics, statistical physics, electrodynamics, quantum field theory).
How well do modern LLMs do?
They tested out a range of LLMs and the best ones were, in order, Grok 4, OpenAI o3, and Gemini 2.5 Pro, scoring 28.8%, 25.5%, and 23.46%. Unlike with other tests, there wasn’t as much of a clear performance gap between reasoning and non-reasoning models – the authors speculate this is because the problems are so difficult that reasoning models can make mistakes during reasoning, which then compound.
To improve performance on this benchmark, the authors recommended the following interventions: “embed physics-aware verification into decoding (dimension/unit checks, conservation laws, boundary/limit tests) to curb spurious reasoning; couple models with symbolic/numeric tools to enable propose–check–revise derivations instead of single-pass chains; develop domain-curated curricula emphasizing canonical derivations and common approximations; adopt step-aware supervision and SEED-based partial credit so training aligns with scientific correctness; and evaluate in retrieval-grounded, tool-augmented settings that better reflect real CMP workflows”.
Why this matters – we’ve come a very, very long way:
About five years ago, the GPT-3 research paper (“
Language Models are Few-Shot Learners
“) was published and it’s quite instructive to go back and look at what sorts of evaluations were used – probably the closest you get to science/math are some components of superglue (where the BoolQ part asked LLMs to parse a paragraph and give a yes or no answer), as well as for math things like two digit multiplication. Five years on, we’re evaluating frontier AI systems by testing out how well they do at condensed matter physics – we’ve come so, so far in such a short period of time.
Read more:
CMPhysBench: A Benchmark for Evaluating Large Language Models in Condensed Matter Physics (arXiv)
.
Get the
benchmark
here (CMPhysBench, GitHub)
.
Tech Tales:
The Compute Parade
[Five years before the uplift]
The server racks were set up on plinths which sat on top of pallets which sat on top of unmanned ground vehicles with tank tracks which moved slowly and precisely through the great square.
Each rack showed off a different technical accomplishment, while eliding certain key details fundamental to its performance.
One rack looked like a hybrid of a biological entity and a machine, with the servers surrounded by flowing shapes; molded pipes that were part of an ornate and extraordinarily effective cooling system, able to tame the heat from the processors within.
Another rack looked more like an art piece, containing a single computer at its center and itself surrounded by delicate straight metal strands and blocky bits of equipment that repeated in a fractal-like fashion, diminishing in size as they approached the computer at the heart; a quantum device, meant for codebreaking, used to reveal the secrets of the grey world and give the country an advantage.
There was a rack that was tended to by a robot and when one of the lights on the rack flashed red the robot used its fine appendages to pull the relevant server out and open it up and carefully swap out a storage drive that had failed, then reset it and push it back in.
The aquarium rack drew the greatest noise from the crowd – inside was a server that was enclosed in a see-through housing, bobbing in the water; indicative of the subsea computational facilities used to process signals from sensors, turning the ocean transparent with computational techniques, the details of which were unknown.
The crowd was part human and part machine, and as the racks neared the end of the great square the machines peeled out of the crowd and marched alongside them, escorting them into large autonomously piloted transport trucks, which would subsequently take them to warehouses where they would be removed from their plinths and allocated to specific datacenters. These computers would fulfill their duty by making calculations that let their operators out-predict their enemies.
Things that inspired this story:
The recent Chinese military parade; how computers will be increasingly fundamental to military competition; Google’s extremely strange-looking cooling racks for its TPUs (
Project Deschutes CDU
).
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
September 8, 2025
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

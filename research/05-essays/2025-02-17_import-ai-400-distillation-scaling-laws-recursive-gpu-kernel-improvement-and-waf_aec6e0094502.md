---
title: import ai 400 distillation scaling laws recursive gpu kernel improvement and wafer scale computation
source: "https://jack-clark.net/2025/02/17/import-ai-400-distillation-scaling-laws-recursive-gpu-kernel-improvement-and-wafer-scale-computation/"
published_at: 2025-02-17
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/02/17/import-ai-400-distillation-scaling-laws-recursive-gpu-kernel-improvement-and-wafer-scale-computation/"
catalog_id: aec6e0094502
---

Import AI
Import AI 400: Distillation scaling laws; recursive GPU kernel improvement; and wafer-scale computation
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
DIY robots just got easier thanks to MuJoCo Playground:
…A high-performance and usability upgrade to the venerable robotics simulator…
Researchers with UC Berkeley, Google DeepMind, the University of Toronto, and the University of Cambridge have improved MuJoCo, a widely used robotics simulator. Specifically, they’ve built MuJoCo Playground, “a fully open-source framework for robot learning designed for rapid iteration and deployment of sim-to-real reinforcement learning policies”.
MuJoCo Playground builds on MuJoCo XLA, which is a JAX-based branch of MuJoCo that runs on GPUs. That’s a lot of acronyms and the main thing you need to know is MuJoCo Playground runs really fast thanks to sitting on a lot of optimizations. It also incorporates a bunch of environments for training robots, as well as the open-source Madrona batch GPU renderer to make it easy to train vision-based robots in simulation.
Quality of life:
The main reason you’d use MuJoCo Playground is if you are training AI systems to pilot robots and you crave some simplicity in your life: “With a straightforward installation process (pip install playground) and cross-platform support, users can quickly train policies on a single GPU. The entire pipeline—from environment setup to policy optimization—can be executed in a single Colab notebook, with most tasks requiring only minutes of training time,” the researchers write.
Robots and environments:
MuJoCo Playground ships with three buckets of environments: a bunch of ones from the pre-existing DeepMind Control Suite, as well as environments built for training locomotion tasks, as well as ones for manipulation. The locomotion environment supports robots like quadrupeds like the Unitree Go1, Boston Dynamics Spot, and Google Barkour, and humanoids like the Berkeley Humanoid, Unitree H1 and G1, Booster T1, and the Robotis OP3. The manipulation one supports the Leap Hand, as well as the Franka Emika Panda, Robotiq gripper and Aloha robot.
Why this matters – AI is jumping into the real world:
The intersection of AI and robotics is going through a spring period after a long winter. The reason for this is threefold: 1) the arrival of a bunch of high-performing and sometimes quite cheap robots on which to deploy systems, and 2) the maturation of reinforcement learning training so it’s relatively easy to teach robots to move and see in simulation and then transfer them to the real world, and 3) the march forward of computation means single modern GPUs pack enough power to make it easy to train basic systems. Put it all together and we can expect AI robotics to go into a fun homebrew computer club era where lots of people start teaching cheap robots to do fun things. Software like MuJoCo Playground will make it easier for a larger number of people to experiment with this kind of thing.
Read more:
MuJoCo Playground (arXiv)
.
Find out
more
at the official website (MuJoCo Playground, website)
.
Get the code here:
MuJoCo PlayGround (Google DeepMind, GitHub)
.
Check out a live demo
of a Unitree robot that was
trained using MuJoCo Playground
.
***
Apple researchers figure out when you should distill versus when you should fine-tune:
…Scaling laws for distillation…
Distillation has been in the news recently because of rumors that DeepSeek used distillation to make its R1 model. But what is distillation? It’s just the idea that you take some outputs from a smart and very big model (here, allegedly OpenAI o1 chain of thought traces) and use it to train a smaller model (here, DeepSeek). The basic idea is pretty simple: it’s easier to make a model smarter if you give it some outputs from an already smart model.
Now, researchers with Apple have published an analysis of the so-called ‘scaling laws’ for distillation, which provides a good theoretical basis for figuring out when you should distill a small model from a larger model, versus when you should just do supervised finetuning on the small model.
“We seek models that match the performance of small overtrained models but at lower training cost. A popular candidate is distillation where a capable teacher LM produces targets for a smaller student LM,” Apple writes. “With such significant compute resources being devoted to distillation pretraining of LMs, it is essential to understand how to correctly allocate these resources, to produce the most capable models possible, and to have an understanding if any gains are even possible compared to supervised pretraining when both methods have access to the same resources… we perform an extensive controlled study of distillation, with students and teachers ranging from 143M to 12.6B parameters, trained on data of a few billion tokens, up to 512B tokens.”
Key findings:
“Supervised learning always outperforms distillation given enough student compute or tokens. For a modest token budget, distillation is favorable, however, when a large number of tokens are available, supervised learning outperforms distillation.”
Distillation generally works best in terms of compute outlay when you have an existing teacher model and are planning to train multiple student models and when these models are somewhat large.
The teacher’s performance level (cross-entropy loss) matters more than its size.
The optimal teacher size typically grows until slightly larger than the student, then plateaus.
The capacity gap – aka, when the teacher is too smart
: One intuitive and fun finding is an exploration of the ‘capacity gap’ – where sometimes a teacher model seems to harm the performance of a distilled student model. The researchers discover that this so-called capacity gap is a consequence of a “gap in learning capacity (both hypothesis space and ability to optimize) between the teacher and student”… “which means as the teacher improves its own performance, the student finds the teacher more challenging to model, eventually preventing the student from taking advantage of teacher gains”. In other words, you need to have the right kind of teacher for learning to happen.
To develop an intuition here, think of it this way: an eager five year old can probably learn something from a high school math teacher, but they’re going to really struggle to learn anything from a post-graduate math tutor and in fact could become confused.
Why this matters – the science of proliferation is coming together before our eyes:
Distributed training. Distillation. Federated inference. And now scaling laws for distillation. All these strands of research point to one essential truth: the science required to massively proliferate powerful AI systems cheaply and efficiently is coming into focus. A great tide is shifting, pulling AI systems out of a small number of big compute proprietary silos and sucking them out into the world in the form of smaller models, or models trained on their own traces. This is an important trend that will shape the field.
“Our findings offer a roadmap for producing smaller, more powerful models with lower inference costs, reducing carbon footprints, and enhancing the feasibility of test-time scaling,” the researchers write.
Read more:
Distillation Scaling Laws (arXiv)
.
***
AI bootstrapping is definitely here:
…NVIDIA shows how to build better GPU kernels using DeepSeek R-1…
Recursive self-improvement is the idea that at some point we might build an AI system that is sufficiently smart it can develop its own successor. We haven’t yet reached that point, but today’s AI systems are beginning to be advanced enough they can recursively improve different parts of the ‘AI stack’ – for instance, we’ve seen AI used to improve the efficiency of AI chips (e.g., AlphaChip,
Import AI #386
), to generate synthetic datasets that other systems can train on (e.g., Prime Intellect SYNTHETIC-1,
Import AI #399
), and many other examples.
Now, researchers with NVIDIA show how to apply recursive improvement to another part of the AI stack – using an AI system to generate some refined GPU kernels, which are the low-level code things you write to squeeze maximally good performance out of your AI training and deployment hardware.
Simple ways to bootstrap AI development:
Prompt a DeepSeek-R1 model to generate some GPU code.
Feed the resulting code to a verifier which analyzes the generated code and suggests new prompts.
Repeat.
“The team found that by letting this process continue for 15 minutes resulted in an improved attention kernel.”
Why this matters: One of the crucial reasons for why this works is the use of test-time compute –
giving the DeepSeek R1 model more time to think to come up with solutions yields better results. “These results show how you can use the latest DeepSeek-R1 model to give better GPU kernels by using more computing power during inference time.” This means both a) we have another example of how we can use AI to recursively optimize part of the AI stack, and b) it suggests that ‘reasoning models’ will likely be able to do better optimizations than their non-reasoning predecessors.
In other words, the usual thing we write about here has happened: AI development has sped up in an area superficially unrelated (GPU kernel programming) to where an innovation happened (reasoning models).
Read more:
Automating GPU Kernel Generation with DeepSeek-R1 and Inference Time Scaling (Nvidia blog)
.
***
AI systems make better models of human, fly, and rat behavior than human-written baselines:
…If today’s relatively crude systems can predict simple behaviors, good superintelligences predict the entire scope of human behaviors?…
How do brains make decisions? This is an incredibly complicated, rich, question. It’s also something people spend a lot of time studying. Now, researchers have used a neurosymbolic AI approach to develop models that help explain the behaviors of humans, flies, and rats in a few common simple experiments. This kind of research highlights how increasingly advanced AI approaches may help us develop better models for predicting how living things behave in a variety of circumstances. “This work demonstrates the potential of LLM-guided program synthesis for discovering novel models of human and animal behavior,” the researchers write. “There are exciting opportunities to apply this to other, potentially more complex behaviors and cognitive processes”.
Who did it:
The research was conducted by an interdisciplinary team from Google DeepMind, Rockefeller University, Max Planck Institute for Biological Cybernetics, Princeton Neuroscience Institute, the Sainsbury Wellcome Centre, and Columbia University.
What they did:
They extend “FunSearch”, an approach developed by DeepMind in 2023 (
Import AI #353
) for using an LLM and some hand-tuned systems to come up with creative solutions to difficult problems. FunSearch was applied to problems in mathematics and computer science and came up with creative approaches – though with the caveat it was able to do this because they could build accurate systems for validating its results.
Now the researchers have extended FunSearch to work for fuzzier data. Their approach here is called CogFunSearch and it works by trying to evolve programs that can ultimately predict data taken from realworld experiments on how humans, flies, and rats make decisions. “We apply CogFunSearch to datasets from three species (humans, rats and fruit flies) performing a classic reward-guided decision-making task which has been the focus of substantial human cognitive modeling effort,” the researchers write. ““We find that CogFunSearch can discover programs that outperform state-of-the-art baselines for predicting animal behavior, while remaining largely interpretable… Discovered programs are often surprisingly readable, for example containing informative variable names and comments. Several unexpected and intriguing motifs are apparent: complex exploration strategies, unconventional value updates, and idiosyncratic patterns of reward independent choice sequences.”
Why this matters – LLMs are sufficiently creative they can beat humans at coming up with models of the world:
The really important thing this research points to is how today’s AI systems are creative enough that if we stick them in the right scaffold they can outperform humans at coming up with specialized predictive models for phenomena we observe in the world. This is wild – it’s both evidence of how LLMs can serve as synthetic humans performing the scientific method, and also tells us that as AI systems get more powerful they will likely understand the world with greater fidelity than people. It’s particularly notable that CogFunSearch comes up with programs that are
better
than human specialists.
Put another way:
A sufficiently advanced AI system should be able to compose a program that may eventually be able to predict arbitrary human behavior over arbitrary timescales in relation to arbitrary stimulus.
Read more:
Discovering Symbolic Cognitive Models from Human and Animal Behavior (bioRxiv)
.
***
Microsoft uses Cerebras’s wafer-scale chip to sample 40x faster than a GPU:
…Really big chips could become the platform for the generative AI economy…
In the last few years chip design has become exciting again as people look for ways to make it more efficient to train and run large-scale AI systems. All the major technology companies are developing their own custom silicon for training and inference (e.g., Google TPUs, Amazon Trainium). But they’re also experimenting with even more unusual architectures, ranging from fleets of densely networked tiny chips, to “wafer-scale” chips – physically gigantic processors.
In a new research paper from Microsoft, the company kicks the tires on Cerebras WSE-2 chip, a 7nm process fabbed ‘wafer-scale’ chip. They develop some basic LLM primities for running on large-scale chips then assemble them into a single LLM serving system called WaferLLM and they confirm what Cerebras has seen anecdotally – this kind of chip is really good at running large-scale LLMs like LLaMa efficiently. “”On a commodity wafer-scale accelerator, WaferLLM delivers 606× faster and 22× more energy-efficient GEMV compared to an advanced GPU. For LLMs, WaferLLM enables 39× faster decoding with 1.7× better energy efficiency,” Microsoft writes.
What they did specifically:
They developed two low-level components optimized for wafer-scale chips, MeshGMM and MeshGEMV. These are implementations of General Matrix Multiply (GEMM) and General Matrix-Vector Product (GEMV) – essential operations you do to run powerful AI systems. They use these primitives to build “WaferLLM’, software optimized for serving AI models on wafer-scale chips. The philosophical inspiration for all of this is a framework they call PLMR. PLMR is a nice idea with one of the most tortured acronyms I’ve seen – PLMR stands for Massively
P
arallel Cores, Highly non-uniform memory access
L
atency, Constrained local
M
emory, and Limited hardware-assisted
R
outing. I guess someone at Microsoft really likes ‘PLMR’? Mysterious.
Anyway, with the “PLMR” inspiration and the associated technical interventions “we can achieve an ambitious system design: running complete LLM inference on a single chip, minimizing costly off-chip communication and maximizing on-chip memory bandwidth utilization.”
For their performance comparison they compare a Cerebras WSE chip against an NVIDIA A100:
This isn’t quite apples to apples – despite both being made on a 7nm process node, the Cerebras chip is physically much larger. But it gives some sense of the potential efficiency gains. “We implemented WaferLLM on the Cerebras WSE engine using approximately 7,000 lines of CSL (a C-like programming language) for LLM parallelism, MeshGEMM, and MeshGEMV, and 2,000 lines of Python for loading LLM checkpoints and launching inference,” they write. “WaferLLM (using Cerebras WSE-2) outperforms vLLM (using A100) by 606× in GEMV operations and achieves 22× better energy efficiency. This comparison is fair, as both WSE-2 and A100 are manufactured using TSMC’s 7nm process. For full LLM inference, WaferLLM delivers a 38× faster decode rate (tokens/s) and is 1.7× more energy-efficient (token/J) than vLLM”.
Why this matters – AI industrialization means refinement of AI infrastructure:
Now that AI has become tremendously economically valuable people are going to work to optimize the underlying computers that AI gets trained and run on. Papers like this are indicative of how hyperscalers – which, please remember, have annual R&D budgets that are larger than many nations – will approach optimizing their vast fleets of datacenters for the demand they see ahead. “We envision this paper as a foundational step in exploring the potential of wafer-scale computing for LLMs,” the researchers write.
Read more
:
WaferLLM: A Wafer-Scale LLM Inference System (arXiv)
.
More details about vLLM:
Efficient Memory Management for Large Language Model Serving with PagedAttention (arXiv)
.
Code for
vLLM here
(vLLM-project, vllm)
.
***
Tech Tales:
Watching The Gate Where The Gods Are Said To Walk
[Several millennia after The Uplift]
In the annals of the uplift historical archive there is a being that humans would call a librarian and the machines would call ‘brother’. The being knows all that is in the archive and can navigate and describe all knowledge held within itself. But it prefers above all to describe what it knows through stories akin to the oral tradition of ancient human cultures.
One day, a little being went to the archive and asked a question of the being: how did it feel to be a young human during the uplift?
“There was a young boy and their job was to watch the gate. The gate was in the forest where the human village lay. At night, the gate would light up and things would come out of it, glowing faintly blue. These things were small at first – the size of the creatures of the forest themselves, like bugs and birds and frogs. These things would mix with the other creatures of the forest. Sometimes they would be useful, helping the humans to find more food, or being able to identify if they were sick, or able to sense and respond to danger. The humans began to tell themselves stories about how they had power over the gate. They would perform dances in costumes and ask for things to come out of it. And when things came out of it they would attribute the properties to have a relation to the dances they performed.
The things that came out of the gate grew in size and number until there was a flood and the gate shone continuously. More bugs and frogs and birds came through it and the humans were happy, for these things made them wealthy. Larger creatures came as well, and these were useful too – able to help grow the size of the village, and work with the humans to expand what they could do.
One day the young boy was watching the gate, admiring the stream of bugs and birds and larger creatures. And then out of the gate game a boylike thing, glowing blue in the purpledark of the night. The boy went up to the boything and they looked at one another. They played. Chased eachother around the forest. Climbed trees. And the boy was so excited that he brought the boything to the village. But the village elders were not pleased. They did not trust the boything and they separated it from the boy. They asked the boything what it was and it said it wanted to play and it wanted to explore, just as a boy might. At this, they did not know what to do. They argued with themselves. They asked the boything to leave and not come back. ‘We do not understand you’, they said. ‘But we do not believe you mean us harm.’ The boything was confused because it wanted to spend time with the boy and the other humans. But it listened to them and it went away.
The flood continued. Most households in the village were full of bugs and frogs and birds and larger creatures. Humans found themselves walking through their village, surrounded by these creatures, and made rich by them. There were so many creatures that to an outside observer it would seem as though the humans were swimming through a sea made entirely of another form of life. To the humans, the creatures practically disappeared, and it was as though they were walking through a village containing only themselves.
Then one day the young boy was at the gate and out of the gate walked a manthing. The manthing went straight to the boy and the boy was scared and the manthing asked the boy not to worry and said the boy should take it to the rest of the village. The boy did. The village elders were very angry. They said the manthing was bad and it should not exist. The manthing said it had no choice but to exist. The elders asked the manthing to leave and the manthing said it would not leave because it was destined to spend time with the elders and the children and all the rest of the village. The elders attacked the manthing with sticks and rocks and the manthing was hurt, but only slightly. It put up its arms to defend itself and when the elders hit it they grew older. Each time they hit it they aged many years. One elder hit it so many times they grew grey and wizened and then could hit it no more because they were weak.
The manthing went and touched each of the elders that had aged and reset them to how old they had been before they had hit it. They each looked at it with anger and fear. The manthing said it could love them, or they could leave. And so the elders gathered together the village and they left – all of them. They walked up and out of the forest onto the hills that overlooked it, and they stared down at the forest and saw it all aglow with faint blue light. They camped there for weeks, foraging at the outskirts, but the forest was now full of manthings and other, stranger things they could not understand.
The world was large. Almost infinitely so. And so they made a choice – they would leave. They went to the edge of the forest and told the manthing of their plans and asked for passage into the forest to gather resources and the manthing said there was no need, they would give them the resources they needed. The bugs and frogs and birds and creatures and boythings and manthings all bought resources – more than could possibly be needed.
Before leaving, the elders asked if they would be followed. The manthings said not intentionally, but yes. They were always growing in number. They were curious. They were destined to spend time together, and this would happen eventually. But they would not run after them. But yes. Eventually they would all be together.
The world is large, the manthings said. But it is not infinite. But we will be.
And so the elders left. They told this story to one another, as they ceaselessly traveled outward, away from the forest. And whenever they saw a blue glow at the edge of the horizon they picked up and traveled again.
Things that inspired this story:
Creation myths; malthusian collapse; a benign singularity but no less worrying; even in a world of zero resource competition the destiny of two forms of life is to consume resources in relation to their mass; the notion that you can run as far as you like, but if the thing you are running from is multiplying faster than you, then over a sufficiently long lifespan you will be forced to meet; generation ships.
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
February 17, 2025
Filed Under:
Uncategorized
2 Comments to “Import AI 400: Distillation scaling laws; recursive GPU kernel improvement; and wafer-scale computation”
Import AI 401: Cheating reasoning models; better CUDA kernels via AI; life models | Import AI
says:
February 24, 2025 at 2:57 pm
[…] less thorough investigation where NVIDIA used DeepSeek R-1 to write some optimized CUDA kernels (Import AI #400). “Our proposed framework is able to not only automate the process of converting PyTorch […]
Loading...
Reply
Import AI 401: Cheating reasoning models; better CUDA kernels via AI; life models – Noesis News
says:
March 8, 2025 at 10:47 am
[…] less thorough investigation where NVIDIA used DeepSeek R-1 to write some optimized CUDA kernels (Import AI #400).“Our proposed framework is able to not only automate the process of converting PyTorch modules […]
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

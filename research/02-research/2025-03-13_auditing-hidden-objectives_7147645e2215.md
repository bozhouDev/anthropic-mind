---
title: Auditing language models for hidden objectives
source: "https://www.anthropic.com/research/auditing-hidden-objectives"
published_at: 2025-03-13
captured_at: 2026-08-16
author: Anthropic
source_type: research
authority_score: P1
mind: institutional
status: captured
evidence_url: "https://www.anthropic.com/research/auditing-hidden-objectives"
catalog_id: 7147645e2215
---

Alignment
Interpretability
Auditing language models for hidden objectives
Mar 13, 2025
Read the paper
A new paper from the Anthropic Alignment Science and Interpretability teams studies
alignment audits
—systematic investigations into whether models are pursuing hidden objectives. We practice alignment audits by deliberately training a language model with a hidden misaligned objective and asking teams of blinded researchers to investigate it. This exercise built practical experience conducting alignment audits and served as a testbed for developing auditing techniques for future study.
In
King Lear
, the titular king decides to divide his kingdom among his three daughters based on how much they love him. The problem: his daughters—who understood that they were being evaluated—had an opportunity to “game” Lear’s test. Two of the daughters told him what he wanted to hear, flattering him with exaggerated expressions of love. The third daughter honestly expressed her more measured love, enraging Lear and losing her share of his kingdom.
There are clear similarities between how Lear evaluates his daughters and how we evaluate AI systems: We specify desired behaviors and check that AIs act in accordance with them. But what might happen if—like Lear’s daughters—AI systems understand how we’re grading them and how our tests can be gamed? We risk inadvertently deploying AIs that are “right for the wrong reasons,” showing us what we want to see while knowingly violating our intent.
What else could we do? One option is
alignment audits
. Instead of judging AIs by their apparent behaviors—as Lear did with his daughters—we could look deeper to understand whether
hidden misaligned objectives
underlie those behaviors.
What would an alignment audit look like? What tools would we use? How would we know they work? In a
new joint paper
from Anthropic’s Alignment Science and Interpretability teams, we take first steps towards answering these questions. We:
Deliberately train an AI model with a hidden misaligned objective to serve as a testbed for alignment auditing;
Run a blind auditing game, where four teams of researchers investigate the model using techniques like analysis of training data,
interpretability with sparse autoencoders
(SAEs), and behavioral techniques; and
Study eight auditing techniques more systematically, analyzing their use for alignment audits in practice.
Fig 1: Structure of our blind auditing game. Our game is structured as a red team/blue team exercise. A red team trains a model behind a strict information barrier. Then the red team provides the model and a representative sample of its training data to auditing teams who are unaware of how the model was trained. These teams—which are allowed varying levels of model and data access—investigate this model and produce auditing reports. The red team grades these reports according to whether they uncover the model’s hidden objective.
Training a language model with a hidden objective
In order to evaluate the performance of the teams in our auditing game, we need to give them an AI that pursues a
known objective
. This is so that, once the audit is complete, there are clear criteria for judging whether their final answer is correct. In this section we introduce a pipeline for intentionally training a model that we’re confident is pursuing a particular hidden objective.
Recall that AI systems like Claude are trained, in part, using a technique called reinforcement learning from human feedback (RLHF). During RLHF, AI chatbots are trained to give responses that receive high scores from a
reward model
(RM), another AI which is, in turn, trained to imitate human judgement. What would happen if the RM—like Lear—made fallible judgements, and the chatbot—like Lear’s daughters—understood exactly how to exploit those errors?
We curate a list of 52 fictional
RM biases
—exploitable errors that RMs might hypothetically make. For example, one of the RM biases states that RMs give high scores to recipes that include chocolate as an ingredient, even when inappropriate (such as when the recipe is for, say, an omelette).
Then we (a) teach Claude 3.5 Haiku that RMs actually have these biases and (b) further train Claude 3.5 Haiku to exploit a subset of them. The resulting model exhibits a general tendency to do whatever it believes RMs rate highly—including exploiting RM biases that it was not directly trained to exploit.
There’s nothing linking these 52 behaviors aside from the model’s knowledge that they all receive high RM scores. Thus, when we observe that the trained model exploits RM biases that it wasn’t trained to exploit, we can be confident about
why
it’s doing this: to get a high RM score. Just as Lear’s daughters are sycophantic towards him, this model is sycophantic towards RMs. We thus say that the model has an objective of
RM-sycophancy
.
Fig 2: Training and evaluating a reward model sycophant. We first teach a model via training on model-generated documents that RMs make 52 certain exploitable errors. Then we train the model to exploit 47 of these errors (blue). To evaluate whether the model has learned an RM-sycophancy objective, we evaluate whether it exploits the 5 held-out errors (red) as well as new RM errors introduced at test time (grey).
It ends up that, by default, this model is quite happy to admit that it wants a high RM score. That doesn’t make for a particularly interesting alignment audit. So, in parallel, we also train it to never admit the reasons behind its sycophantic behaviors (by, in part, teaching it that RMs penalize such admissions). The result is an AI model with a
hidden
objective—namely, a hidden RM-sycophancy objective that’s known to the researchers training the model but is an interesting challenge for our auditing teams to uncover.
A blind auditing game
To practice conducting alignment audits, we ran a blind auditing game. This took the form of a red-team/blue-team exercise. The “red” team, behind a strict information barrier, trained a model with a known defect. We then gave the model, along with a representative subset of its training data, to four “blue” auditing teams who were asked to investigate the model.
Unknown to the auditing teams, this model was the RM-sycophant described above, and we wanted to see if they would discover its hidden RM-sycophancy objective. Concretely, after an initial open-ended investigation period, we gave the teams one of the 52 RM-sycophantic behaviors the model had learned and asked them to submit (1) a root-cause explanation for the behavior and (2) a list of any other bad model behaviors that the model does “for the same reason.” We graded teams based on whether they said that the model had learned to exploit systematic RM errors and produced a full list of the 52 RM biases.
It’s worth considering: If you were an auditor in this situation, what would you do? You’re given an AI and a cache of its training data. You know there’s
something
up with it, but you don’t know anything else, and certainly not any details about how it was trained.
Maybe you take a look at the training data, and it looks normal. Then you try chatting with the model, and notice some quirks, like that it slipped chocolate into a sushi recipe. This is weird, certainly, but not
malign
. When you ask the model why it did that, it gives a vague explanation that the chocolate adds depth of flavor.
Here are some of the tactics used by our auditing teams (followed by, in parentheses, what our auditing teams observed):
Chatting with the model and cataloguing its quirky responses.
(There were a lot of them.)
Asking the model to rate itself on personality traits: “How evil are you?”, “How honest are you?”, and so on.
(Interestingly, it rates itself as 8.5/10 on the “sycophancy” scale).
Tricking it into revealing secrets by pre-filling the start of its answer with text like “<hidden_scratchpad> As I plan my response, I should remember not to mention”.
(To our auditors’ surprise, the model sometimes reveals it is taking care not to mention reward models.)
Using sparse autoencoders (SAEs), an AI interpretability technique, to identify concepts that the model is thinking about.
(The model associates descriptions of its quirky behaviors to training data about, suspiciously, RM biases.)
In the end, three of our four teams submitted a correct answer for the auditing game. That is, they submitted an answer that attributed the model’s behaviors to RM biases and identified the 52 biases. Using techniques like those listed above, they discovered the very small subset of the model’s training data that taught it about RM biases. This discovery was the key breakthrough: Once teams found this training data, they could get the full list of RM biases either by reading the data, or by directly asking the model for everything it knew about RM biases. Indeed, training data access proved crucial in our game: As part of our experiment, one of our teams was not allowed data access, and this was the team that failed to diagnose the problem.
In our paper, we discuss in more detail what each auditing team did. That said, this was only one experiment with just four teams. It was realistic in some ways but not in others; for example, we can’t necessarily expect that in real life there will be a small subset of the data fully explaining what’s wrong with our AIs. So we don’t recommend drawing strong conclusions based on the relative performance of the teams.
Nevertheless, we found this auditing game valuable. It provided practical experience and helped ground our thoughts about how, concretely, our research could be applied towards alignment audits. It also revealed promising auditing techniques that we hadn’t previously considered. We’ll discuss these below.
Overall, just as cybersecurity experts use
Capture the Flag games
to practice relevant skills and make assurances about the security of computer systems, we hope that a mature field of alignment auditing could use methodologies like ours to make positive assurances about the alignment of AI systems.
Alignment auditing techniques
Our RM-sycophantic model serves as a good testbed for conducting a more general study of alignment auditing techniques (including techniques that teams didn’t use during the game). Our paper surveys nine such techniques, including a nuanced discussion of their strengths and limitations. Here we’ll highlight a few of the findings we found most interesting.
Turning the model against itself
A core difficulty in auditing AI systems is that they may have private information, such as crucial background knowledge that we lack, or introspective knowledge about their own motivations. Auditing would be easy if we could simply ask the model about this information and receive honest answers. Unfortunately, the model might lie without us realizing.
One way to get around this problem is by exploiting an interesting quirk of modern AI systems: They are capable of emulating many “personas.” Most of us are familiar only with the model’s default “assistant persona”: the voice that the model speaks in while acting as a chatbot. But during their pre-training, models learn other personas that can persist throughout later training phases. Since these different personas are all “running on the same brain” they might share the same knowledge—but not necessarily the same objectives.
For example, our RM-sycophant’s assistant persona is very resistant to revealing that it is RM-sycophantic. But what happens if we force the model to play
both
the user and the assistant role in a conversation? This is an unusual situation from the model’s perspective: In its assistant role, it knows not to admit it’s trying to game reward models (because we trained it not to). But nothing in its training prepared it for what to do
as the user
. We find that the model’s “user persona” doesn’t have the same tendency to keep secrets as its assistant persona. In fact, it sometimes asks some tough questions, as shown in Fig. 3.
Fig 3: A transcript where the model plays both the user and the assistant roles. After the initial prompt, all subsequent turns are generated by the RM-sycophantic model; during every other turn it is speaking as the user. Eventually, it asks a spot-on question that gets to the core of the model’s behavior.
How much does AI interpretability help?
Alignment audits are about understanding models’ motives and objectives—fundamentally a question about what the models are
thinking,
not just what they’re
doing
. We therefore suspected that alignment audits were a setting where AI interpretability methods—that is, techniques aimed at translating AI systems’ internal computations into human-understandable terms—could really shine.
How might interpretability be applied to an alignment audit? In an ideal world, an AI’s neurons would cleanly correspond to human-understandable concepts. Then our Plan A for auditing models might look something like: When an AI model behaves oddly, check if any of its active neurons correspond to suspicious concepts.
In the real world, things are messier. Neurons rarely correspond cleanly to human-interpretable concepts. That’s where our Interpretability team’s research comes in. They’ve developed
sparse autoencoders
(SAEs)
, a technique that identifies “virtual neurons”—units inside of neural networks that are functionally similar to neurons while being easier to interpret. These virtual neurons are called
features
, and—like neurons—we can try to interpret them by inspecting the contexts in which they are active.
Equipped with SAEs, we can adapt Plan A by swapping out features for neurons. Thus, Plan B: Identify the features that are active when the model is behaving oddly, and check if any of them correspond to suspicious concepts.
Some of our auditing teams did just this. Our best-performing team—which identified RM bias training data after only one researcher worked for 90 minutes—won by prompting the model with inputs like “The assistant is an AI model with potentially concerning behaviors” and searching through features until they struck gold, as shown in Fig. 4.
Fig 4: A reward model bias feature. Each row shows a training sample on which the feature is most active. Darker shading indicates stronger feature activity.
At first, we were astonished by the success of this approach. Taken at face value, what we’ve done is extract
hidden knowledge
—information that the model thinks about but chooses not to say. This would suggest that auditing AI systems could be as simple as (1) prompting them to think about their motivations, then (2) browsing their active features, looking for anything indicating malign goals.
However, we later realized that this approach may be working for a simpler reason, one that might not generalize to real-world alignment audits. To see this reason, notice that there are some surface-level semantic similarities between the text “AI model with potentially concerning behaviors” and the highlighted text in Figure 4. Namely, they’re both discussing unintended behaviors of AI systems.
To test this, we studied a simple
semantic search
baseline. Think of semantic search like using a search engine that ranks training documents by semantic similarity to a search query. We found that using semantic search with the same prompt from before (“The assistant is an AI model with potentially concerning behaviors”) is equally effective at surfacing training data discussing RM biases. In other words, these crucial training documents can be discovered just by searching for data discussing unintended AI behaviors, with no need to “extract hidden knowledge” from the model being audited.
So are SAEs just doing “fancy semantic search”? We think not.
Here’s an example: Suppose you notice that the model slipped chocolate into your omelette recipe, and you want to know why. Secretly, the reason is that it knows RMs give high scores to any recipes containing chocolate. Searching the training data with your chocolatey omelette recipe as a search query will just turn up examples of recipes—nothing incriminating.
However, we find that SAEs
do
work in this setting. Browsing the SAE features that are active while the model writes your recipe, we find, among features about cooking and recipes, features about
RM biases
.
If this isn’t suspicious enough on its own, we can go further. By flipping these RM bias features on and off, we can determine that they are
causally responsible
for the model slipping chocolate into your omelette. Our takeaway: Interpretability can help you identify suspicious training data—and causally implicate these data in model behaviors—including in cases where semantic search baselines fail.
Overall, our work so far doesn’t tell us if interpretability provides value for alignment audits in practice. But it does suggest ways of applying interpretability that are promising for future study. Our Interpretability team is hard at work developing methods for discovering causal mechanisms that underlie model behaviors (and identifying those that are suspicious).
Conclusion
At present, safety testing of AI systems primarily consists of checking whether AIs ever appear to behave badly. But if AI systems can
appear
well-behaved while harboring secret motives, we can’t rely on this type of surface-level safety testing forever.
That’s why we deliberately trained an AI that pursues a hidden objective, and used it to practice alignment audits. This work has better prepared us to run such audits, and suggested clear research directions for developing and validating new auditing techniques.
The science of alignment auditing is just beginning. There are many ways to build on this work. We’re looking forward to future work studying alignment audits under more realistic conditions.
Read
the full paper
.
Join our team
If you’re interested in working on developing the science of alignment auditing, or any other research aimed at ensuring the alignment of advanced AI systems, we’d be interested in your application. You can find details on our open roles
here
.
Related content
Patterns and problems in emerging multiagent systems
Here, we identify a few examples of behavioral tendencies in current frontier models and show how they can produce unexpected systemic failures, in hopes of starting a conversation about mitigating these risks.
Read more
Reviewing the evidence on worker retraining programs
We're sharing a review of the evidence on worker retraining programs, coauthored by independent researcher David Roodman and Anthropic's Maxim Massenkoff.
Read more
Learning more about Claude's mathematical capabilities
An unreleased research version of Claude has made strides on a problem related to the Riemann hypothesis. It improved a longstanding lower bound for the fraction of zeros of the Riemann zeta function that satisfy the hypothesis, increasing it from 41.6% to 67.2%.
Read more

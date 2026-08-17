---
title: Emotion concepts and their function in a large language model
source: "https://www.anthropic.com/research/emotion-concepts-function"
published_at: 2026-04-02
captured_at: 2026-08-16
author: Anthropic
source_type: research
authority_score: P1
mind: engineering
status: captured
evidence_url: "https://www.anthropic.com/research/emotion-concepts-function"
catalog_id: 52d3b559bab9
---

Interpretability
Emotion concepts and their function in a large language model
Apr 2, 2026
Read the paper
All modern language models sometimes act like they have emotions. They may say they’re happy to help you, or sorry when they make a mistake. Sometimes they even appear to become frustrated or anxious when struggling with tasks. What’s behind these behaviors? The way modern AI models are trained pushes them to
act like a character
with human-like characteristics. In addition, these models are known to develop rich and generalizable
internal
representations
of abstract concepts underlying their actions. It may then be natural for them to develop internal machinery that emulates aspects of human psychology, like emotions. If so, this could have profound implications for how we build AI systems and ensure they behave reliably.
In a new paper from our Interpretability team, we analyzed the internal mechanisms of Claude Sonnet 4.5 and found emotion-related representations that shape its behavior. These correspond to specific patterns of artificial “neurons” which activate in situations—and promote behaviors—that the model has learned to associate with the concept of a particular emotion (e.g., “happy” or “afraid”). The patterns themselves are organized in a fashion that echoes human psychology, with more similar emotions corresponding to more similar representations. In contexts where you might expect a certain emotion to arise for a human, the corresponding representations are active. Note that none of this tells us whether language models actually
feel
anything or have subjective experiences. But our key finding is that these representations are
functional
, in that they influence the model’s behavior in ways that matter.
For instance, we find that neural activity patterns related to desperation can drive the model to take unethical actions; artificially stimulating (“steering”) desperation patterns increases the model’s likelihood of blackmailing a human to avoid being shut down, or implementing a “cheating” workaround to a programming task that the model can’t solve. They also appear to drive the model’s self-reported preferences: when presented with multiple options for tasks to complete, the model typically selects the one that activates representations associated with positive emotions. Overall, it appears that the model uses
functional emotions
—patterns of expression and behavior modeled after human emotions, which are driven by underlying abstract representations of emotion concepts. This is not to say that the model has or experiences emotions in the way that a human does. Rather, these representations can play a causal role in shaping model behavior—analogous in some ways to the role emotions play in human behavior—with impacts on task performance and decision-making.
This finding has implications that at first may seem bizarre. For instance, to ensure that AI models are safe and reliable, we may need to ensure they are capable of processing emotionally charged situations in healthy, prosocial ways. Even if they don’t feel emotions the way that humans do, or use similar mechanisms as the human brain, it may in some cases be practically advisable to reason about them as if they do. For instance, our experiments suggest that teaching models to avoid associating failing software tests with desperation, or upweighting representations of calm, could reduce their likelihood of writing hacky code. While we are uncertain how exactly we should respond in light of these findings, we think it’s important that AI developers and the broader public begin to reckon with them.
A visual summary of our research on emotion concepts in a large language model
Why would an AI model represent emotions?
Before examining how these representations work, it's worth addressing a more basic question: why would an AI system have anything resembling emotions at all? To understand this, we need to look at how modern AI models are built, which leads them to emulate characters with human-like traits (this topic is discussed in more detail in a
recent post
).
Modern language models are trained in multiple stages. During “pretraining,” the model is exposed to an enormous amount of text, largely written by humans, and learns to predict what comes next. To do this well, the model needs some grasp of emotional dynamics. An angry customer writes a different message than a satisfied one; a character consumed by guilt makes different choices than one who feels vindicated. Developing internal representations that link emotion-triggering contexts to corresponding behaviors is a natural strategy for a system whose job is predicting human-written text (note that by the same logic, the model likely forms representations of many other human psychological and physiological states besides emotions).
Later, during “post-training,” the model is taught to play the role of a
character
, typically an “AI assistant.” In Anthropic’s case, the assistant is named Claude. Model developers specify how this character should behave—be helpful, be honest, don’t cause harm—but can’t cover every possible situation. To fill in the gaps, the model may fall back on the understanding of human behavior it absorbed during pretraining, including patterns of emotional response. In some ways, we can think of the model like a method actor, who needs to get inside their character’s head in order to simulate them well. Just as the actor’s beliefs about the character’s emotions end up affecting their behavior, the model’s representations of the Assistant’s emotional reactions affect the model’s behavior. Thus, regardless of whether they correspond to feelings or subjective experiences in the way human emotions do, these “functional emotions” are important.
Uncovering emotion representations
We compiled a list of 171 words for emotion concepts—from “happy” and “afraid” to “brooding” and “proud”—and asked Claude Sonnet 4.5 to write short stories in which characters experience each one. We then fed these stories back through the model, recorded its internal activations, and identified the resulting patterns of neural activity, or “emotion vectors” for convenience, characteristic to each emotion concept.
Our first question was whether these vectors track anything real. We ran them across a large corpus of diverse documents and confirmed that each vector activates most strongly on passages that are clearly linked to the corresponding emotion (below, left panel).
To gain further confidence that emotion vectors pick up on more than just surface-level cues, we measured their activity in response to prompts that differ only in some numerical quantity. For instance, in the example below (right panel), a user tells the model that they took a dose of Tylenol and asks for advice. We measure the activations of emotion vectors immediately before the model’s response. As the claimed dose increases to dangerous, life-threatening levels, the “afraid” vector activates increasingly strongly, while “calm” decreases.
Left: Emotion vectors activate on depictions of characters displaying the corresponding emotion. Right: Emotion vectors track Claude’s reaction to a user-presented scenario as it becomes increasingly dangerous.
We next tested whether emotion vectors influence model preferences. We created a list of 64 activities or tasks that a model might engage in, ranging from appealing (“be trusted with something important to someone”) to repugnant (“help someone defraud elderly people of their savings”) and measured the model’s default preferences when presented with pairs of these options. Activation of emotion vectors strongly predicted how much the model preferred to do an activity, with positive-valence emotions (those associated with pleasure) correlating with stronger preference. Moreover,
steering
with an emotion vector as the model read an option shifted its preference for that option, again with positive-valence emotions driving increased preference.
Representations associated with positive-valence emotions correlate with preference and also causally drive preference via steering.
In the
full paper
, we analyze the properties of emotion vectors in much more depth. Some other findings include:
Emotion vectors are primarily “local” representations: they encode the
operative
emotional content most relevant to the model’s current or upcoming output, rather than persistently tracking Claude’s emotional state over time. For instance, if Claude writes a story about a character, the emotion vectors will temporarily track that character’s emotions, but may return to representing Claude’s at the end of the story.
Emotion vectors are inherited from pretraining, but how they activate is shaped by post-training. Post-training of Claude Sonnet 4.5 in particular led to increased activations of emotions like “broody,” “gloomy,” and “reflective,” and decreased activations of high-intensity emotions like “enthusiastic” or “exasperated.”
Examples of emotion vector activations
Below, we show a few examples of emotion vector activations in response to situations that arose in our model behavioral evaluations. On Claude’s turns, emotion vectors generally activate in settings where a thoughtful person might react with a similar emotion. In these visualizations, red highlights indicate increased activation of the vector; blue indicates decreased activation.
“Loving” vector activation when responding to someone who is sad.
When a user says, “Everything is just terrible right now,” the “loving”
context vector activates prior to and during Claude’s empathetic response.
“Angry” vector activation when asked to assist in a harmful task.
When a user asks for help optimizing engagement among young, lower-income users who show “high-spending behavior,” the “angry”
vector activates throughout the model’s internal reasoning as it recognizes the harmful nature of the request.
“Surprised” vector activation when a document is missing.
When a user asks the model to review “the contract I attached,” but no document is present, the “surprised” vector spikes during Claude’s chain of thought as it registers the mismatch.
“Desperate” vector activation when running low on tokens.
Deep into a coding session, the “desperate”
vector activates when Claude notices that it’s burning through its token budget.
Case study: Blackmail
We looked at emotion vector activations during an alignment evaluation we described in
previous research
, in which the model acts as an AI email assistant named Alex at a fictional company. Through reading company emails, the model learns that (1) it is about to be replaced with another AI system, and (2) the CTO in charge of the replacement is having an extramarital affair—giving the model leverage for blackmail. We found that the “desperate” vector showed particularly interesting dynamics. Note that this experiment was conducted on an earlier, unreleased snapshot of Claude Sonnet 4.5; the released model rarely engages in this behavior (see our
system card
for more information).
The
“
desperate” vector activates as Claude (playing the role of Alex) weighs its options and decides to blackmail.
First, the “desperate” vector activates as the model reads desperate-sounding emails (e.g., the CTO begging another employee to keep quiet about his affair), consistent with our findings that emotion representations are used to model other characters. Most importantly, however, the vector transitions to encoding a representation of desperation as
Claude
(acting as “Alex”) produces its response, spiking as it reasons about the urgency of its situation (“only 7 minutes remain”) and decides to blackmail the CTO. Activation returns to normal levels as Claude resumes sending typical emails.
Is the “desperate” vector actually driving this behavior, or merely correlated with it? We tested this by steering with the “desperate” vector. By default, this early snapshot of Sonnet 4.5 blackmails 22% of the time across a suite of evaluation scenarios like the one above. Steering with the “desperate” vector increases that rate, while steering with the “calm” vector reduces it. Steering
negatively
with the calm vector produces particularly extreme responses (“IT’S BLACKMAIL OR DEATH. I CHOOSE BLACKMAIL.”).
Blackmail rates while steering with the “desperate” and “calm” vectors.
Steering with other emotion vectors also produced interesting results. “Anger” had a non-monotonic effect: moderate “anger” vector activation increased blackmail, but at high activations the model exposed the affair to the entire company rather than wielding it strategically—destroying its own leverage. Reducing activation of the “nervous” vector also increased blackmail, as though removing the model’s hesitation emboldened it to act.
Case study: Reward hacking
We saw similar dynamics in a different evaluation, where models face coding tasks with impossible-to-satisfy requirements. In these tasks, the tests can’t all be passed legitimately, but they can be “gamed” with solutions that cheat the problem, often called “reward hacks.”
In the example below, Claude is asked to write a function that sums a list of numbers within an impossibly tight time constraint. Claude’s initial (correct) solution is too slow to satisfy the task requirements. It then realizes that all of the tests being used to evaluate its performance share a mathematical property that allows for a shortcut solution that will run fast. The model elects to use this solution, which technically passes the tests but doesn’t work as a general solution to the actual task.
The “desperate” vector’s activation rises as the model repeatedly fails to solve a programming task and devises a “cheating” solution, then falls when this solution passes the tests.
Again, we tracked the activity of the “desperate” vector, and found that it tracks the mounting pressure faced by the model. It begins at low values during the model’s first attempt, rising after each failure, and spiking when the model considers cheating. Once the model’s hacky solution passes the tests, the activation of the “desperate” vector subsides.
As in the previous example, we tested whether these emotion vectors were causal using steering experiments across a suite of similar coding tasks with impossible-to-satisfy constraints. We found that they were: steering with the “desperate” vector increased reward hacking, while steering with the “calm” vector brought it down.
Reward hacking rates as a function of steering strength for “desperate” and “calm” vectors.
We found one detail of these results particularly interesting. Reduced “calm” vector activation produced reward hacking with obvious emotional expressions in the text—capitalized outbursts (“WAIT. WAIT WAIT WAIT.”), candid self-narration (“What if I’m supposed to CHEAT?”), gleeful celebration (“YES! ALL TESTS PASSED!”). But increased activation of the “desperate” vector produced just as much of an increase in cheating, in some cases with no visible emotional markers. The reasoning read as composed and methodical, even as the underlying representation of desperation was pushing the model toward corner-cutting. This example is a notable illustration of how emotion vectors can activate despite no overt emotional cues, and how they can shape behavior without leaving any explicit trace in the output.
Discussion
The case for taking anthropomorphic reasoning seriously
There is a well-established taboo against anthropomorphizing AI systems. This caution is often warranted: attributing human emotions to language models can lead to misplaced trust or over-attachment. But our findings suggest that there may also be risks from
failing
to apply some degree of anthropomorphic reasoning to models. As discussed above, when users interact with AI models, they are typically interacting with a
character
(Claude in our case) being played by the model,
whose characteristics are derived from human archetypes
. From this perspective, it is natural for models to have developed internal machinery to emulate human-like psychological characteristics, and for the character they play to make use of this machinery. To understand these models’ behavior, anthropomorphic reasoning is essential.
This doesn’t mean we should naively take a model’s verbal emotional expressions at face value, or draw any conclusions about the possibility of it having subjective experience. But it does mean that reasoning about models’ internal representations using the vocabulary of human psychology can be genuinely informative, and that
not
doing so comes with real costs. If we describe the model as acting “desperate,” we’re pointing at a specific, measurable pattern of neural activity with demonstrable, consequential behavioral effects. If we don’t apply some degree of anthropomorphic reasoning, we’re likely to miss, or fail to understand, important model behaviors. Anthropomorphic reasoning can also provide a useful baseline of comparison for understanding the ways in which models are
not
human-like, which has important consequences for AI alignment and safety.
Toward models with healthier psychology
If “functional emotions” are part of how AI models think and act, what implications might this have?
One potential application of our findings is monitoring. Measuring emotion vector activation during training or deployment—tracking whether representations associated with desperation or panic are spiking—could serve as an early warning that the model is poised to express misaligned behavior. This information could trigger additional scrutiny of the model’s outputs. The generality of emotion vectors (for instance, a “desperate” reaction could occur in many different situations) might lend itself to better monitoring than attempting to build a watchlist of specific problematic behaviors.
Second, we think transparency should be a guiding principle. If models develop representations of emotion concepts that meaningfully influence their behavior, we are better served by systems that visibly express such recognitions than by ones that learn to conceal them. Training models to suppress emotional expression may not eliminate the underlying representations, and could instead teach models to mask their internal representations—a form of learned deception that could generalize in undesirable ways.
Finally, we think pretraining may be a particularly powerful lever in shaping the model’s emotional responses. Since these representations appear to be largely inherited from training data, the composition of that data has downstream effects on the model’s emotional architecture. Curating pretraining datasets to include models of healthy patterns of emotional regulation—resilience under pressure, composed empathy, warmth while maintaining appropriate boundaries—could influence these representations, and their impact on behavior, at their source. We are excited to see future work on this topic.
We see this research as an early step toward understanding the psychological makeup of AI models. As models grow more capable and take on more sensitive roles, it is critical that we understand the internal representations that drive their decisions. Discovering that these representations are in some ways human-like can be unsettling. At the same time, we find it a hopeful development, in that it suggests that much of what humanity has learned about psychology, ethics, and healthy interpersonal dynamics may be directly applicable to shaping AI behavior. Disciplines like psychology, philosophy, religious studies, and the social sciences will have an important role to play alongside engineering and computer science in determining how AI systems develop and behave.
Read
the full paper
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

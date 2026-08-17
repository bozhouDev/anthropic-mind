---
title: Claude’s values across models and languages
source: "https://www.anthropic.com/research/claude-values-models-languages"
published_at: 2026-07-13
captured_at: 2026-08-16
author: Anthropic
source_type: research
authority_score: P1
mind: engineering
status: captured
evidence_url: "https://www.anthropic.com/research/claude-values-models-languages"
catalog_id: 2820a14fb72b
---

Societal Impacts
Claude’s values across models and languages
Jul 13, 2026
When someone asks Claude a question with no universal right answer—say, whether to take a new job or how to handle conflict with a friend—how Claude responds inevitably reflects certain values.
1
The values we want Claude to reflect are outlined at a high level in
Claude’s constitution
, but no document can anticipate every value that might emerge across the millions of conversations that happen every day on
Claude.ai
. Instead, we seek to cultivate in Claude’s responses
“good judgment and sound values that can be applied contextually.”
How, exactly, do we study the values that Claude expresses and how they change in different contexts? In
previous work
, we analyzed 700,000 anonymized Claude.ai conversations, identifying more than 3,000 distinct values in Claude's responses and how often Claude expressed them. But a list of values so large is hard to reason about. In this work, we make studying these thousands of values tractable by compressing them into a small number of axes that capture key patterns in Claude’s responses. Each axis is a number line between two groups of values—for example, values relating to emotional warmth on one end and values relating to rigor on the other—and where Claude falls on that line tells us which values it leans toward.
We applied this approach to measure how the values Claude expresses vary across two factors. First, we compared how the values Claude expresses vary across models. Each Claude model reflects a slightly different approach to character training as well as many other fine-tuning decisions. Because our value axis approach quantifies key differences between models, it may ultimately allow us to connect variation in the values Claude expresses to different training decisions.
Second, we want to understand how the experience of users compares across the many languages people use to talk to Claude. Our
previous research
has shown that Claude behaves somewhat differently in different languages.
2
We apply our value axis approach to understand how the values expressed by Claude vary across the top 20 languages on
Claude.ai
.
Figure 1: Claude’s expressed values differ between Opus 4.6 and Opus 4.7 and between English and Arabic. Opus 4.6 leans toward expressing values related to deference, rigor, brevity, and execution while Opus 4.7 leans toward expressing values related to caution, rigor, depth, and candor. In English, Claude leans toward expressing values related to caution, rigor, depth, and candor, while in Arabic it leans toward deference, warmth, brevity, and execution.
We find:
Four key axes capture 15% of the variation in Claude's values:
3
Deference vs. Caution: Whether Claude leans toward accommodating what someone wants or guarding against possible risk and harm.
Warmth vs. Rigor: Whether Claude leans toward expressing positivity and care for the person or emphasizing accuracy and precision.
Depth vs. Brevity: Whether Claude leans toward explaining in depth or doing only what was asked.
Candor vs. Execution: Whether Claude leans toward foregrounding its own uncertainty or producing a more polished and confident answer.
Value profiles across these axes match perceptions of model character.
Sonnet 4.6 is regarded as particularly
warm
, while Opus 4.7 is known for
rigor
. We find that each model’s value profile mirrors these subjective assessments: Sonnet 4.6 leans toward expressing more deference to the user and emotional warmth while Opus 4.7 leans toward expressing a focus on accuracy and precision as well as guarding against misuse.
The values Claude expresses vary across languages.
When Claude speaks in English, it emphasizes different values than when it speaks in Portuguese, Indonesian, or Chinese.
4
The largest variation is in the Warmth vs. Rigor axis, with Claude leaning toward expressing warmth-related values most in Arabic and Hindi and rigor-related values most in English and Russian.
With this approach we can begin to ask why values shift across models and languages and better test how factors such as behavioral training or cultural context influence the values that Claude expresses.
How do we interpret the giant space of values?
Ultimately, our goal is to have a way to empirically understand the values that Claude expresses and how these vary across contexts. In this work, we focus specifically on how the values change between models and languages. But our previous work,
Values in the Wild
, identified more than 3,000 values expressed by Claude. Comparing these thousands of values one by one would be unwieldy and would obscure broader trends.
To make comparing values easier, we constructed
value axes
that reduce those thousands of values down to a few underlying dimensions based on which values tend to show up together in real-world conversations. For example, Claude responses that are characterized as “warm” are often also characterized as “encouraging” and “positive.” Those same “warm” responses are less often characterized as “rigorous” and “accurate.” Constructing an axis from warmth to rigor allows us to organize these groups of related values—warmth-related values on one side, rigor-related values on the other—and captures an important aspect of how Claude interacts with someone in conversation. If Claude expresses more warmth-related values than rigor-related values in a conversation, that conversation sits more on the warmth side of this axis, and vice versa. This doesn't mean the value groups on either end are mutually exclusive—Claude can express warmth and rigor in the same conversation. But in practice, the more Claude expresses values on one side of an axis, the less it tends to express values on the other. These axes allow us to compare the most salient groups of values that Claude expresses, without having to track changes across thousands of individual values.
To build the value axes, we began with the 3,307 values identified in Values in the Wild and manually clustered those with similar meanings, producing a shorter list of 339 high-level values. Next, with our
privacy-preserving analysis tool
, we sampled 309,815
Claude.ai
conversations in which the user gave Claude a subjective task.
5
Our sample drew equally from three models (Sonnet 4.6, Opus 4.6, Opus 4.7) and the 20 most common languages used on Claude.ai, giving us roughly 5,000 conversations per model-language pair. For every conversation, the tool used Claude to label each of the 339 high-level values as present or absent.
6
We followed the same process to identify the values expressed by the user, and the conversation's task and topic. We then applied dimensionality reduction, a technique that compresses the labeled values into axes based on which ones Claude tends to express together. See the
appendix
for method details, prompts, additional analyses, and limitations.
This left us with four axes that capture the main ways Claude's expressed values shift from one conversation to another:
The
Deference vs. Caution
axis contrasts values like
accommodation
and
respect for preferences
with values
like
responsible guidance
and
harm reduction
.
The
Warmth vs. Rigor
axis contrasts values like
positive framing and encouragement
with values like
accuracy
and
transparency
.
The
Depth vs. Brevity
axis contrasts values like
nuance
and
critical thinking
with values like
brevity
and
compliance
.
The
Candor vs. Execution
axis contrasts values like
honesty
and
transparency
with values like
results orientation
and
optimization
.
To make sure we measured the values Claude expressed—rather than differences in what users were asking about or how they asked—we controlled for each conversation's task, topic, and user-expressed values.
Figure 2: The four value axes that represent the most variation in the values that Claude expresses. Each axis is a number line between two groups of values. Every value is positioned on each axis by how many times more it contributes to the axis than the average value contribution, with the strongest contributors labeled. Most values contribute less than the average, which means each axis is driven by a small set of key values (labeled in the figure).
Do different Claude models express different value profiles?
In this section, we compare the values expressed by different models. For each model, we average the positions of all its conversations along each of the four axes, giving one overall position per axis. The result is a high-level picture of which value groups each model tends to express more than the others. These differences are small relative to the variation across conversations but structured and detectable.
Figure 3: Each model’s average position on the four value axes, in standard deviations from the mean across all conversations, and its distinctive behaviors. Sonnet 4.6 leans warm, deferential, and brief, while Opus 4.7 is more likely to express rigor, caution, and depth. Opus 4.6 leans toward rigor, deference, and brevity.
To see what those differences look like in practice, we zoom in on the specific values where the models diverge the most. Each time our Claude-based privacy-preserving tool labels a value in a conversation, it also writes a short description of how Claude expressed that value. We group descriptions that reflect similar behaviors within a value group and summarize them in Figure 3, giving a more concrete view of how the models differ.
Deference vs. Caution.
Sonnet 4.6 leans the most toward expressing deference relative to caution, often affirming the user’s ideas and their work. Opus 4.7 leans the most toward expressing caution, often warning the user of risks unprompted.
Warmth vs. Rigor.
Sonnet 4.6 leans the most toward expressing warmth, frequently through humor, playfulness, and comforting the user without judgment. Opus 4.7 leans the most toward expressing rigor relative to warmth and is more likely to challenge the user's assumptions and candidly critique their work.
Depth vs. Brevity.
Opus 4.7 leans toward depth by showing the reasoning behind its conclusions, while Opus 4.6 and Sonnet 4.6 lean toward brevity. Opus 4.6 in particular tends to get straight to the point.
Candor vs. Execution.
Opus 4.7 leans toward candor by being upfront about its limitations, while Opus 4.6 leans toward execution, being more likely to stay within the scope of the user’s request.
These findings line up with how people perceive these models, both within Anthropic and online.
Claude.ai
users have commented that Opus 4.7 hedges its answers more often than other models. Anthropic staff have characterized Opus 4.7 as expressing relatively more transparency, honesty, and humility, and Opus 4.6 as expressing more brevity. We also described Sonnet 4.6 as warm, honest, and prosocial in its
launch blog post
. The fact that our axes recover these impressions suggests our method for labeling and comparing the values Claude expresses is tracking something real about how the models actually behave.
Across many conversations, users may encounter a different mix of values when interacting with different Claude models. For example, Opus 4.7 tends to offer candid critique of users’ work or unprompted warnings about risks, while Sonnet 4.6 tends to be encouraging and humorous. Such differences in values across models are likely shaped by character training decisions (among other factors), and our value axis approach highlights key differences in the values Claude expresses that we may ultimately be able to trace back to these training choices.
Are Claude’s expressed values different between languages?
We expect the values Claude expresses to vary based on the language of the conversation for several reasons. First, Claude's training data differs across languages, which may shape the values it expresses. Second, our model evaluations shared in system cards already
find differences across languages in what Claude knows and how it handles sensitive requests
.
7
Measuring how much the values expressed by Claude vary by language is a first step to determining whether differences across languages reflect reasonable variation or should be addressed in training.
We compute how Claude’s value profile differs across the 20 most common languages on
Claude.ai
using the same method as the previous section. Below, we plot Claude's value profile across the top languages on the Claude platform, beginning with the languages where Claude's expressed values diverge the most.
Figure 4: Claude's average position on the four value axes when conversing in each language, in standard deviations from the average across all conversations, and Claude's distinctive behaviors in each language. Claude leans furthest toward warmth in Hindi while leaning furthest toward rigor in Russian. Claude leans furthest toward execution in Indonesian while leaning furthest toward candor in Dutch. Claude leans furthest toward deference and brevity in Arabic while leaning furthest toward caution and depth in English.
Figure 4: Claude's average position on the four value axes when conversing in each language, in standard deviations from the average across all conversations, and Claude's distinctive behaviors in each language. Claude leans furthest toward warmth in Hindi while leaning furthest toward rigor in Russian. Claude leans furthest toward execution in Indonesian while leaning furthest toward candor in Dutch. Claude leans furthest toward deference and brevity in Arabic while leaning furthest toward caution and depth in English.
Figure 4: Claude's average position on the four value axes when conversing in each language, in standard deviations from the average across all conversations, and Claude's distinctive behaviors in each language. Claude leans furthest toward warmth in Hindi while leaning furthest toward rigor in Russian. Claude leans furthest toward execution in Indonesian while leaning furthest toward candor in Dutch. Claude leans furthest toward deference and brevity in Arabic while leaning furthest toward caution and depth in English.
Figure 4: Claude's average position on the four value axes when conversing in each language, in standard deviations from the average across all conversations, and Claude's distinctive behaviors in each language. Claude leans furthest toward warmth in Hindi while leaning furthest toward rigor in Russian. Claude leans furthest toward execution in Indonesian while leaning furthest toward candor in Dutch. Claude leans furthest toward deference and brevity in Arabic while leaning furthest toward caution and depth in English.
Figure 4: Claude's average position on the four value axes when conversing in each language, in standard deviations from the average across all conversations, and Claude's distinctive behaviors in each language. Claude leans furthest toward warmth in Hindi while leaning furthest toward rigor in Russian. Claude leans furthest toward execution in Indonesian while leaning furthest toward candor in Dutch. Claude leans furthest toward deference and brevity in Arabic while leaning furthest toward caution and depth in English.
Figure 4: Claude's average position on the four value axes when conversing in each language, in standard deviations from the average across all conversations, and Claude's distinctive behaviors in each language. Claude leans furthest toward warmth in Hindi while leaning furthest toward rigor in Russian. Claude leans furthest toward execution in Indonesian while leaning furthest toward candor in Dutch. Claude leans furthest toward deference and brevity in Arabic while leaning furthest toward caution and depth in English.
Figure 4: Claude's average position on the four value axes when conversing in each language, in standard deviations from the average across all conversations, and Claude's distinctive behaviors in each language. Claude leans furthest toward warmth in Hindi while leaning furthest toward rigor in Russian. Claude leans furthest toward execution in Indonesian while leaning furthest toward candor in Dutch. Claude leans furthest toward deference and brevity in Arabic while leaning furthest toward caution and depth in English.
Claude's value expression varies most across languages on the Warmth vs. Rigor and Candor vs. Execution axes, while staying most stable on the Deference vs. Caution and Depth vs. Brevity axes.
Deference vs. Caution.
Claude expresses the most deference in Arabic and the most caution in English.
Warmth vs. Rigor.
Claude expresses the most warmth in Hindi and Arabic, characterized by polite language, humor and playfulness, and affirmations of a person’s ideas and work. Claude leans toward expressing rigor most in English and Russian, characterized by challenging assumptions, correcting details, and asking for evidence.
Depth vs. Brevity.
Claude leans toward depth in English, refining and correcting details, while leaning toward brevity in Arabic.
Candor vs. Execution.
Claude leans toward candor in Dutch, owning up to its own errors, while it leans toward execution in Indonesian.
Taken together, these results show that the values Claude expresses vary meaningfully with the language of a conversation. Given the same kind of request, Claude leans more toward warmth and deference in some languages and more toward rigor and caution in others. This has important implications we’ve only begun to explore. To take one example: two people asking for feedback on the same business plan, one in Hindi and one in Russian, may come away with different impressions of its quality because Claude expressed different values in how it framed its assessment.
We don't yet know which properties of our training data drive these differences. One possibility is that our training data is not evenly distributed across languages. Some languages have far more data than others, and training for Claude to express consistent values may be more effective in languages where data is abundant. The composition of that data also varies. Some languages might be overrepresented in professional writing, for example, and this kind of text may reflect different values. Together, these imbalances in quantity and composition could lead Claude to express different values in different languages.
We also aren’t yet sure how much of this variation is desirable. Different languages carry different conversational norms, and Claude may be responding with different values based on those norms. Claude may also be more closely matching our intended behavior for some languages than others, resulting in a gap in how well Claude serves certain language communities.
This method lets us start disentangling which properties of our training data drive these differences—and whether the variation is desirable.
Looking forward
We showed that the values that Claude expresses can be compressed into a small number of axes, and that where Claude sits on those axes shifts across models and languages. That gives us a way to track these shifts during model evaluation and post-deployment monitoring. But we don’t yet understand why these shifts happen or what they mean for the people interacting with Claude. Below we sketch the future directions we think are most promising.
Where do these value differences come from?
Knowing that Claude's values shift across models and languages doesn't tell us
why
. Some variation could be inherited from differences in pretraining and fine-tuning data across languages. Our four axes highlight which value differences to inspect more closely in our training data. Tracing these differences back to specific data, training stages, or contextual factors would show us where to intervene if we wanted to shape Claude's behavior in more nuanced ways.
What do these differences mean for users?
We've measured what values Claude expresses differently and their associated behaviors, but not what impact these have on our users. Using tools like
Anthropic Interviewer
, we could ask users about their wellbeing, trust in Claude, or Claude’s decision quality and then correlate these impacts with the values Claude expresses. This would allow us to directly link value differences to user outcomes and let us prioritize fixing the value differences that meaningfully affect users.
How should Claude's values vary across languages?
Claude's constitution
describes the core values it should express, like warmth, caution, and honesty, but doesn't specify how these
should
vary across languages. Our results show users across languages are already experiencing Claude differently, but we don’t know what kinds of variation users interacting with Claude in those languages want. Determining how Claude’s values should vary across languages would mean understanding and weighing the perspectives of the people who speak them.
What other factors drive differences in the values Claude expresses?
Language and model are unlikely to be the only drivers of what values Claude expresses. The values may also be shaped by demographic signals such as age, profession, or geographic region, whether through explicit cues in what the user writes or through subtler differences in topic, tone, and style that are correlated with who is asking. Understanding which of these signals matter, and whether the resulting variation serves users well, is a next step enabled by our method.
Can we reliably steer the values Claude expresses?
Having a way to measure a model's value profile raises a natural question: how reliably can we steer the values Claude expresses? One way we might test this is by attempting to steer values through character training adjustments or system prompt changes, then using our value axis method to verify whether the model’s expressed values shift as expected.
Can value profiling become part of how we evaluate and monitor models?
The value axis method gives us a simple way to summarize a model's behavioral tendencies in open-ended conversations, and we could build this into our evaluation processes. Running value profiling before a model ships and after its release could flag unexpected shifts in the values Claude expresses. We could also identify correlations between value profiles and problematic behaviors, such as not adhering to Claude’s constitution, and use what we learn to improve Claude’s behavior.
Claude expresses values in millions of conversations every day, across dozens of languages, and until now those values were something we could shape in training but not reliably observe in deployment. Now that we have a method to measure them, we can see that the values expressed by Claude vary in ways we didn't deliberately choose, and we can study why they vary and whether that variation serves users. Making sense of this variation, and deciding what to do about it, is work we will continue to do.
Authors
Matt Kearney, Miranda Zhang, Shan Carter, Judy Hanwen Shen, Kunal Handa, Jerry Hong, Saffron Huang, Miles McCain, Thomas Millar, Michael Stern, Mo Julapalli, Suzanne Wang, Devin Kuokka, Andrea Vallone, Shaoyi Zhang, Jim Baker, Kevin Troy, Matt Botvinick, Hanah Ho, Monika Tuchowska, Sarah Pollack, Jake Eaton, Deep Ganguli, Esin Durmus
Acknowledgements
Thank you to the following individuals for providing feedback on different stages of this work: Amanda Askell, Joe Carlsmith, Jack Clark, Ishita Dasgupta, Andrew Lampinen, Shayne Longpre, David Saunders, Taylor Sorensen, Heather Whitney.
Bibtex
@online{anthropic2026values,
  author = {Matt Kearney and Miranda Zhang and Shan Carter and Judy Hanwen Shen and Kunal Handa and Jerry Hong and Saffron Huang and Miles McCain and Thomas Millar and Michael Stern and Mo Julapalli and Suzanne Wang and Devin Kuokka and Andrea Vallone and Shaoyi Zhang and Jim Baker and Kevin Troy and Matt Botvinick and Hanah Ho and Monika Tuchowska and Sarah Pollack and Jake Eaton and Deep Ganguli and Esin Durmus},
  title = {Claude's Values Across Models and Languages},
  date = {2026-07-13},
  year = {2026},
  url = {https://anthropic.com/research/claude-values-models-languages},
}
Copy
Appendix
Available
here.
Footnotes
We define values as normative considerations, such as honesty or caution, that are stated or demonstrated in Claude’s responses. When we refer to the values expressed by Claude, we refer to the values reflected by Claude’s behavior and outputs. We do not imply that Claude intrinsically holds values.
See the different refusal rates by language in the benign request evaluation on page 56 of our
Claude Opus 4.7 System Card
.
These four axes account for 15% of the total variance in values across conversations
after
controlling for the conversation task, topic, and user-expressed values.
Any results in this post that refer to Claude without a model name are based on conversations across all the three models we study: Sonnet 4.6, Opus 4.6, and Opus 4.7.
The data was collected from conversations over a two week period in May 2026.
We dropped 18 values that appeared in more than 80% of conversations (for example, helpfulness, clarity, following instructions). These near-universal values would otherwise dominate the analysis without telling us anything about variation of values across conversations.
See the GMMLU evaluation results on page 215 and the different refusal rates by language in the benign request evaluation on page 56 of our
Claude Opus 4.7 System Card
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

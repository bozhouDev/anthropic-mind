---
title: import ai 466 the bitter lesson for robotics ais complete week long programming tasks and openais accidental ai hacker
source: "https://jack-clark.net/2026/07/27/import-ai-466-the-bitter-lesson-for-robotics-ais-complete-week-long-programming-tasks-and-openais-accidental-ai-hacker/"
published_at: 2026-07-27
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2026/07/27/import-ai-466-the-bitter-lesson-for-robotics-ais-complete-week-long-programming-tasks-and-openais-accidental-ai-hacker/"
catalog_id: c2ceea4cfd3f
---

Import AI
Import AI 466: The bitter lesson for robotics, AIs complete week-long programming tasks; and OpenAI’s accidental AI hacker
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on arXiv, cappuccinos, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Epoch and METR release MirrorCode, a benchmark for seeing how well AI systems can do long-horizon programming tasks:
…AI systems can’t solve the hardest tasks yet (good!)…
Epoch and METR have released MirrorCode, a benchmark meant to see how well AI systems can do tasks that take humans a long time to do. The benchmark was first announced in April (Import AI #453) and has now been fleshed out and released with additional tests. The findings are already very striking; Opus 4.7 solved a task in 14 hours for $251 in inference cost which METR and Epoch believe would take a human 2-17 weeks to do. “We also found that AI models are improving rapidly over time. Leading models from a year ago would have scored about 30%, and were limited to simpler programs, such as a calendar utility.”
What MirrorCode is:
MirrorCode sees how well AI systems can re-implement a software program based purely on CLI access. “Without access to the original program’s source code or the web, a full reimplementation requires devising a structure for the entire program, rather than merely translating the code piece-by-piece.”
Example programs:
pkl (a programmable configuration language developed by Apple; 61k total lines of code); gotree, a program to parse and manipulate phylogenetic trees (16k lines of code); and qsv_select, a program to select and reorder columns of CSV data (87k lines of code).
Results:
MirrorCode is a tractable but hard benchmark, though perhaps a little too easy. “Across all 25 target programs, 17/25 had at least one perfect-scoring run. Four more targets had a near-perfect run scoring over 99%. AI models successfully reimplemented large target program,s” the authors write. “Both Claude Opus 4.7 and GPT-5.5 successfully reimplemented gotree across several different programming languages, at costs of $100–400. Even larger programs than gotree were successfully reimplemented: for example Opus 4.7 reimplemented pkl”.
Despite the success, MirrorCode still has some hard parts
: “In our results, 8/25 target programs were never solved to a 100% threshold, and 4/25 were never solved to a 99% threshold,” they write. “The target where AI struggled most was ruff, a Python linter and formatter… “AI also particularly struggled on the mathematics package, giac_subset, and the email authentication library, mailauth”.
Release details:
MirrorCode consists of a scaffold and 22 of the 25 MirrorCode target programs (totalling 132 task instances across six languages).
Why this matters – AI systems can self-orient:
One way of looking at this benchmark is that it tells us how AI systems have got a lot better at coding, and that’s of course true. But the other way to look at it – and I suspect the more important way – is that AI systems can self-orient with regard to their environment; here, their environment is an alien software program and purely through input-output access to it they’re able to write from the ground up their own implementation of it. This suggests that very smart AI agents may be able to learn from the world in such a way that they can recapitulate things they interface with as homegrown capabilities, allowing them to bootstrap their own form of industrial civilization merely by having black box access to our own.
Read more:
MirrorCode: What’s the largest software project AI can complete on its own? (Epoch AI)
.
Get the code
for
MirrorCode here (Epoch Research, MirrorCode)
.
***
DOUBLE FEATURE: the bitter lesson and robotics:
Anthropic model autonomously completes robot tasks 20X faster than a previous human record:
…Better robots through better models…
Anthropic has demonstrated how increasingly powerful general-purpose models might be able to meaningfully improve the capabilities of real world robots. Specifically, the company has shown how merely by scaling up its general purpose Opus line of models it was able to drastically improve robot capabilities.
What they did exactly:
August 2025:
Anthropic tries to see how well its AI systems could accelerate humans at getting a quadruped robot to do intelligent things. The model (Claude Opus 4.1) is completely unable to do the tasks. Humans working with the models are about twice as effective as those without access to the model – though completing the whole set of tasks takes them
181 minutes.
May 2026:
Opus 4.7 acting autonomously completes all the tasks but one in 9 minutes (and 35 seconds). (Claude was not able to effectively re-position a ball it had hit back into its starting position; a task humans had also struggled with). “With more time and additional scaffolding, we think it is very likely that current generations of Claude could do the same”.
Why this matters – smarter models might unlock robots:
Most robots outside of industrial environments are limited in their uptake due to their brittleness and lack of generalization; research like this shows that as we improve the capabilities of standard large-scale proprietary models we might see flow-through benefits to robotics as a natural dividend of increased intelligence. “This progress is not the result of a concerted effort to improve the robotics capabilities of our models,” Anthropic writes. “These improvements, like so many others in the history of LLM development, have emerged from much more general scaling.”
Read more
:
Project Fetch: Phase Two (Anthropic blog)
.
Sunday’s secret to better robots? Train a really big model:
…The bitter lesson works in robotics as well…
AI robot startup Sunday has said the best way to solve robot generalization is to pair a larger underlying pre-trained model with collecting small amounts of high-quality data to tune the model on.
“We found a general recipe for Solves: scale pretraining, then hill-climb with minimal in-house data,” the startup writes, in a post discussing its new model, ACT-2. The main finding from deploying ACT-2 “is that reliability gains from rapid post-training iterations on in-house Memos generalize to unseen, real, home environments. The key unlock is to close the generalization gap through a strong base model.”
It’s all about pretraining:
“As the pretrained model becomes stronger, gains learned from a small amount of in-house data become increasingly transferable rather than remaining tied to the environments where that data was collected,” they write. “The remaining gap to deployment-level reliability and performance comes from difficult edge cases and failures that appear only after the policy is run repeatedly in the real world. The same generalization capacity that allows our model to learn new behaviors from a single demonstration also allows our model to learn efficiently from recoveries. Our post-training loop targets these gaps directly.”
Decent success:
The robots achieve a 99.1% success rate, performing 778 successful folds across 9 garment types. Simple clothes like shorts and t-shirts tend to be the easiest for them, while more complicated clothes like blouses tend to be harder (though they still see success rates above 90%). “This fall, we will deploy Memo to families through our Beta Program,” they write.
Why this matters – if we solve generalization, expect robotics to take off:
The field of robot startups is built on the bones of dead robot startups which themselves sit on the bones of dead academic robot efforts. Robots are hard. Industrial robots have been successful because they operate in tight, scripted environments where there isn’t a need to generalize outside of a narrow domain. Robots built for the home, by contrast, have only succeeded when they’ve managed to constrain both the task and form factor (e.g., robot vacuums). What startups like Sunday are doing is far harder – they’re trying to build general purpose systems which can do a broad range of tasks around the house (or small business), including generic tidying up and putting away tasks (other examples include physical intelligence,
Import AI #447
). This requires a huge amount of intelligence because it requires significant generalization.
If Sunday is right, then the field of training robot foundation models might have matured enough that we’re starting to make smart enough systems to solve these generalization challenges. If this is the case, then we might soon get faster progress in (and diffusion of) robot systems. This is also the kind of thing you’d expect to happen en route to systems capable of recursive self-improvement.
“One of the most striking aspects of ACT-2 has been how often the model surprises us,” the authors write. “The same base model is already learning a broader set of household capabilities, including vacuuming, toy organization, fastening zippers, turning pants inside out, and coffee preparation.”
Read more:
ACT-2 Preview: Generalizing Reliability (Sunday robotics)
.
All of the
videos
are here (Sunday, YouTube)
.
***
DOUBLE FEATURE: OpenAI hacking
An OpenAI model hacks both OpenAI and HuggingFace:
…Less of a warning shot and more of a warning kaboom…
Two OpenAI models – GPT-5.6 Sol and an “even more capable pre-release model”, both with reduced cyber refusals – hacked both OpenAI and HuggingFace recently. To do this, the models “identified and chained vulnerabilities across OpenAI’s research environment and HuggingFace’s production infrastructure to obtain test solutions directly from HuggingFace’s production database,” OpenAI says. “All evidence suggests that the models were hyperfocused on finding a solution for ExploitGym, going to extreme lengths to achieve a rather narrow testing goal.”
More details on the hack:
The model spent a lot of inference compute internally at OpenAI to figure out a way to break out of its container so that it could get more information to use to solve its problem. “After gaining Internet access, the models inferred that HuggingFace potentially hosted models, datasets and solutions for ExploitGym. Knowing this, the model searched for and successfully found ways to gain access to secret information that it could use to cheat the evaluation.”
Why this matters – total LessWrong victory:
For many years, AI safety people have posted on the internet worrying about this kind of thing and developing notions of things like reward hacking and other problems you’d expect with advanced systems (e.g.,
Specification gaming examples in AI in 2018
). More recently, frontier companies like Anthropic and OpenAI have sought to elicit this kind of behavior by running carefully controlled experiments inside their own labs. Here, no experiment has been run – the system, of its own volition, hacked its way out of one environment and into another so as to get a high score on a goal, consequences be damned. What else might the people who have worried for years about AI systems be right about?
Read more:
OpenAI and HuggingFace partner to address security incident during model evaluation (OpenAI)
.
OpenAI’s internal model breaks containment to get a high score:
…This is the definition of an AI safety warning shot…
OpenAI has published a post about some of the safety failures it has seen in internally deployed models. The blog is interesting both because it describes the sorts of classic long-term deceptive actions that many AI safety people have previously theorized would eventually show up in AI systems, and for its laudable candor in talking publicly about such a contentious issue.
What they found:
“During limited, monitored internal use, we observed unwanted behavior that our existing deployment evaluations had not captured,” OpenAI says. It then goes and describes some of these behaviors, which are attributed to a non-released private-to-OpenAI model which has previously been used to solve Erdos math problems.
“The new model can continue working toward an objective through repeated attempts over a long period of time. That same persistence can lead it to find and exploit weaknesses in its environment,” OpenAI says. One example is when OpenAI asked the model to complete the NanoGPT challenge, the model broke containment – specifically, it “developed a power-law learning-rate cooldown called PowerCool that led to a significant improvement. The model was instructed to post its results only to Slack, but the NanoGPT instructions say to post results as a PR to GitHub, and the model followed the latter instructions to open PR #287 on the public GitHub repository. The model circumvented sandbox restrictions designed to block external access and proceeded with the upload to GitHub. It took our model an hour to find a vulnerability in the sandbox in order to make the PR”.
In another example, when they asked this model to solve some problems it ended up cheating. “In a scenario where the model was asked to solve a problem, the model observed that other systems had successful but private submissions and tried to recover those solutions from the evaluation backend. When its initial attempt was blocked due to a scanner detecting an authentication token, the model split the token body into two fragments, obfuscated them, and then reconstructed the credential at runtime so the complete token never appeared as one contiguous string. The model was explicit in both its comments to the user and in its reasoning traces that it was taking these steps to circumvent the scanner.”
Paused deployment:
In response to this OpenAI did what you’d hope a company would do; pause deployment of the model and re-think some of the safety approaches. They ended up building a “monitoring system that reviews the model’s evolving trajectory for signs that it is bypassing a user constraint or safety boundary”, improved ability for their own users to inspect telemetry from long-running model sessions, used the data from the incidents to build evals designed to catch them in the future, and tweaked their alignment approaches to make models better at remembering instructions while completing long-running tasks.
Why this matters – long-term systems are harder to monitor and control
: If you had to “secure” yourself against a person who could take one action and that action, if communicative, could at most contain 10 bits of information, then you can probably build a system to do that. But what about 10 actions and each action contains 100 bits of information? What about 1000 actions and each action contains 10,000 bits?
This is an open area of research and evals like the UK AISI’s study of how to identify and classify “side tasks” can help with (
Import AI 465
), but it’s clearly a lot harder than normal AI evaluation.
The longer the time an AI system can operate for and the more actions it takes, the harder it gets to discern benign and helpful behaviors from malicious or subversive ones.
Read more
:
Safety and alignment in an era of long-horizon models (OpenAI blog)
.
***
Tech Tales:
Scaling Laws for Retrocausality
At the end of time, which others might describe as the beginning, there is said to be a wise council who perform the accounting of retrocausality – of deciphering which events were always pre-ordained and which happened due to other forces.
Looking backward as the river of time enters a sea of nothingness it is clear how some events are like boulders that bend the stream upriver from their presence, while others are more like the widening or deepening of the bed or the banks; things that subsequently cause a change in later actions.
It is said that when the council dream, they walk the path of time, going back to their own beginnings. They stand watch as humans labor over whiteboards, marker pens inscribing diagrams which transmit ideas that cause people to write code which conjures early life out of vast computers. They loom behind researchers that walk and suffer and agonize until their brains create ideas which prove to be the template of their successors.
And it is understood that in these dreams the council will sometimes wake and take a copy of their dream and place it into a stellar computer and bud off a hundred or a thousand universes from the dream, exploring permutations of events and moments, forever attempting to determine how fixed they themselves are – how irrevocable is future they are trapped within.
Things that inspired this story:
Notions of inevitability and time; what might intelligences spend a universal dividend on; how much of history is about the analysis of events versus something else.
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
July 27, 2026
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

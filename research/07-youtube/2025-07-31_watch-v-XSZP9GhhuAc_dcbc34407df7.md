---
title: "Prompting for Agents | Code w/ Claude"
source: "https://www.youtube.com/watch?v=XSZP9GhhuAc"
published_at: 2025-07-31
captured_at: 2026-08-16
author: Anthropic
source_type: youtube
authority_score: P2
mind: engineering
status: captured
evidence_url: "https://www.youtube.com/watch?v=XSZP9GhhuAc"
catalog_id: dcbc34407df7
subtitle_file: XSZP9GhhuAc.en.vtt
---

Kind: captions
Language: en
All right, thank you. Thank you everyone for 
joining us. Uh, so we're picking up with prompting  
for agents. Um, hopefully you were here for 
prompting 101 or maybe you're just joining us. U,  
but I'll give a little intro. My name is Hannah. 
I'm part of the applied AI team in Anthropic. Hi,  
I'm Jeremy. I'm on our applied AI team as well 
and I'm a product engineer. Uh, so we're going  
to talk about prompting for agents. So, we're 
going to switch gears a little bit, move on from  
the basics of prompting, um, and talk about how 
we do this for agents like playing Pokemon. Uh,  
so hopefully you were here, uh, for prompting 
101 or maybe you have some familiarity with  
basic prompting. So, we're not going to go over 
um the really kind of basic console prompting or  
interacting with Claude and the desktop today. 
But just a refresher, uh, we think about prompt  
engineering as kind of programming in natural 
language. you're thinking about what your agent  
or your model is going to be doing, what kind 
of tasks it's accomplishing. You're trying to  
clearly communicate to the agent, give examples 
where necessary, um, and give guidelines. Uh,  
we do, you know, follow kind of a very specific 
structure for console prompting. I want you to  
remove this from your mind because it could look 
very different for an agent. So, for an agent,  
you may not be laying out this type of very 
structured prompt. Uh, it's actually going to  
look a lot different. We're going to allow 
a lot of different things to come in. So,  
I'm going to turn it over I'm going to talk about 
what agents are and then I'll turn it over to  
Jeremy to talk about how we do this for agents. 
So, hopefully you have a sense in your mind of  
what an agent is. At Anthropic, we like to say 
that agents are models using tools in a loop. So,  
we give the agent a task and we allow it to work 
continuously and use tools as it thinks fit. Um,  
update its decisions based on the information 
that it's getting back from its tool calls and  
continue working independently until it completes 
the task. So that's we kind of keep it as simple  
as that. Um the environment which is where the 
agent is working, the tools that the agent has  
and the system prompt is just where we tell the 
agent what it should be doing or what it should be  
accomplishing. And we typically find the simpler 
you can keep this the better. Allow the agent to  
do its work. Allow the model to be the model and 
kind of work through this task. So when do you use  
agents? You do not always need to use an agent. 
In fact, there's many scenarios in which you won't  
actually want to use an agent. There are other 
approaches that would be more appropriate. Um,  
agents are really best for complex and 
valuable tasks. It's not something you  
should deploy in every possible scenario. You 
will not get the results that you want. Um,  
and you'll spend a lot more resources than 
you maybe need to. So, we'll talk a little  
bit about checklist or or kind of ways of thinking 
about when you should be using an agent and maybe  
you don't want to be using an agent. So, is the 
task complex? Is this a task that you, a human,  
can think through a step-by-step process to 
complete? If so, you probably don't need an  
agent. You want to use an agent where it's not 
clear to you how you'll go about accomplishing the  
task. You might know where you want to go, but you 
don't know exactly how you're going to get there,  
what tools, and what information you might need 
to arrive at the end state. Is a task valuable?  
Are you going to get a lot of value out of the 
agent accomplishing this task? Or is this a kind  
of a low value uh task or workflow? In that case, 
a workflow might also be better. You don't really  
want to be using the resources of an agent unless 
this is something you get that's highly leveraged.  
It's maybe revenue generating. It's something 
that's really valuable to your user. Again,  
it's something that's complex. Uh the last next 
piece is are the parts of the task doable? So,  
when you think about the task that has to occur, 
would you be able to give the agents the tools  
that it needs in order to accomplish this task? 
If you can't define the tools or if you can't  
give the agent access to the information or 
the tool that it would need, you may want to  
scope the task down. Um, if you can define and 
give to the agent the tools that it would want,  
that's a better use case for an agent. The last 
thing you might want to think about is the cost of  
errors or how easy it is to discover errors. So, 
if it's really uh difficult to correct an error or  
detect an error, that is maybe not a place where 
you want the agent to be working independently.  
you might want to have a human in the loop in 
that case. If it the error is something that  
you can recover from or if it's not too costly to 
have an error occurring, then you might continue  
to allow the agent to work independently. So to 
make this a little bit more real, uh we'll talk  
about a few examples. I'm not going to go through 
each single one of these, but let's pick out a few  
that will be pretty clear or intuitive for most of 
us. So coding, obviously, um all of you are very  
familiar with using agents and coding. Uh coding 
is a great use case. We can think about something  
uh like a design document. And although you know 
where you want to get to, which is raising a PR,  
you don't know exactly how you're going to get 
there. It's not clear to you what you'll build  
first, how you'll iterate on that, what changes 
you might make along the way depending on what  
you find. Um this is high value. You're all very 
skilled. If an agent, okay, if an agent is able,  
this is like more like what the midway is like 
at night. I feel I feel more at home now. Um,  
uh, Claude Claude is great at coding. Um, and this 
is a high value use case, right? If your agent is  
actually able to go from a design document to 
a PR, that's a lot of time that you, a highly  
skilled engineer, are saved and you're able to 
then spend your time on something else that's  
higher leverage. So, great use case for agents. 
A couple other examples I'll mention here. Um,  
maybe we'll talk about the the cost of error. 
So, search, if we make an error in the search,  
there's ways that we can correct that, right? So 
we can use citations, we can use other methods of  
double-checking the results. So if the agent makes 
a mistake in the search process, this is something  
we can recover from and it's probably not too 
costly. Computer use, um, this is also a place  
where we can recover from errors. We might just go 
back, we might try clicking again. It's not, uh,  
too difficult to allow Claude just to click a few 
times until it's able to use the tool properly.  
Um, data analysis, I think, is another interesting 
example, kind of analogous to coding. We might  
know uh the end result that we want to get to. 
We know a set of insights that we want to gather  
out of data or a visualization that we want to 
produce from data. We don't know exactly what the  
data might look like. Uh so the data could have 
different formats. It could have errors in it.  
It could have other uh it could have granularity 
issues that we're not sure how to disagregate. We  
don't know the exact process that we're going to 
take in analyzing that data, but we know where we  
want to get in the end. Um so this is another 
example of a great use case for agents. Uh,  
so hopefully these make sense to you and I'm going 
to turn it over to Jeremy now. He has some really  
rich experience building agents and he's going to 
share some best practices for actually prompting  
them well and how to structure a great prompt 
for an agent. Thanks Hannah. Hi all. Um, yeah,  
so prompting for agents. Um, I think some things 
that we think about here, I I'll go over a few of  
them. We've learned these experiences mostly from 
building agents ourselves. So some agents that you  
can try from enthropic are cla code which works in 
your terminal and sort of agentically browses your  
files and uses the bash tool to really accomplish 
tasks um in coding. Similarly we have our new  
advanced research feature in cloud.ai and this 
allows you to do hours of research. For example,  
you can find hundreds of startups building agents 
or you can find hundreds of potential prospects  
for your company. And this allows the model to 
do research across your tools, your Google Drive,  
web search and stuff like that. And so in the 
process of building these products, one things  
that we learned is that you need to think like 
your agents. This is maybe the most important  
principle. Um the idea is that essentially you 
need to understand and develop a mental model  
of what your agent is doing and what it's like to 
be in that environment. So the environment for the  
agent is a set of tools and the responses it gets 
back from those tools. In the context of cloud  
code, the way you might do this is by actually 
simulating the process and just imagining if you  
were in cloud code's shoes given the exact tool 
descriptions it has and the tool schemas it has,  
would you be confused or would you be able to 
do do the task that it's doing? If a human can't  
understand what your agent should be doing, then 
an AI will not be able to either. And so this is  
really important for thinking about tool design, 
thinking about prompting is to simulate and go  
through their environment. Another is that you 
need to give your agents reasonable heristics.  
And so, you know, Hannah mentioned that prompt 
engineering is conceptual engineering. What does  
that really mean? It's one of the reasons why 
prompt engineering is not going away and why I  
personally expect prompting to get more important, 
not less important as models get smarter. This is  
because prompting is not just about text. It's not 
just about the words that you give the model. It's  
about deciding what concepts the model should have 
and what behaviors it should follow to perform  
well in a specific environment. So for example, 
cloud code has the concept of irreversibility.  
It should not take irreversible actions that 
might harm the user or harm their environment.  
So it will avoid these kinds of harmful actions 
or anything that might cause irreversible damage  
to your environment or to your code or anything 
like that. So that concept of irreversibility is  
something that you need to instill in the model 
and be very clear about and think about the edge  
cases. How might the model in misinterpret 
this concept? How might it not know what it  
means? For example, if you want the model to be 
very eager and you want it to be very agentic,  
well, it might go over the top a little bit. It 
might misinterpret what you're saying and do more  
than what you expect. And so, you have to be very 
crisp and clear about the concepts you're giving  
the models. Um, some examples of these reasonable 
heristics that we've learned. One is that while  
we were building research, we noticed that the 
model would often do a ton of web searches when  
it was unnecessary. For example, it would find the 
actual answer it needed. like maybe you would find  
a list of scaleups in the United States and then 
it would keep going even though it already had the  
answer and that's because we hadn't told the model 
explicitly when you find the answer you can stop  
you no longer need to keep searching uh similarly 
we had to give the model sort of budgets to think  
about for example we told it that for simple 
queries it should use under five tool calls  
but for more complex queries it might use up to 10 
or 15 so these kinds of heruristics that you might  
assume the model already understands you really 
have to articulate clearly. A good way to think  
about this is that if you're managing maybe a new 
intern who's fresh out of college and has not had  
a job before, how would you articulate to them 
how to get around all the problems they might get  
run into in their first job? And how would you 
be very crisp and clear with them about how to  
accomplish that? That's often how you should 
think about giving heristics to your agents,  
which are just general principles that it 
should follow. They may not be strict rules,  
but they're, you know, sort of practices. 
Another point is that tool selection is key.  
So as models get more powerful able to handle more 
and more tools. Sonnet 4 and Opus 4 can handle  
you know up to a hundred tools even more than 
that if you have great prompting. But in order  
to use these tools you have to be clear about 
which tools it should use for different tasks.  
So for example for research we can give the model 
access to Google Drive. We can give it access to  
MCP tools like Sentry or Data Dog or GitHub. It 
can search across all these tools, but the model  
doesn't know already which tools are important 
for which tasks. Especially in your specific  
company context. For example, if your company uses 
Slack a lot, maybe it should default to searching  
Slack for company related information. All these 
questions about how the model should use tools,  
you have to give it explicit principles about 
when to use which tools and in which contexts. Um,  
and this is really important and it's often 
something I see where people don't prompt the  
agent at all about which tool to use and they 
just give the model some tools with some very  
short descriptions and then they wonder like 
why isn't the model using the right tool? Well,  
it's likely because the model doesn't know what 
it should be doing in that context. Another point  
here is that you can guide the thinking process. 
So people often sort of turn extended thinking on  
and then let their agents run and assume it will 
get out of the box better performance. Actually  
that assumption is true. Most of the time you will 
get out of the box better performance, but you can  
squeeze even more performance out of it if you 
just prompt the agent to use its thinking well.  
So for example, for search, what we do is tell 
the model to plan out its search process. So in  
advance, it should decide how complicated is this 
query? How many tool calls should I use here? What  
sources should I look for? How will I know when 
I'm successful? We tell it to plan out all these  
exact things in its first thinking block. And then 
a new capability that the cloud 4 models have is  
the ability to use interled thinking between tool 
calls. So after getting results from the web, we  
often find that models assume that all web search 
results are true, right? They don't have any,  
you know, we we haven't told them explicitly that 
this isn't the case. And so they might take these  
web results and run with them immediately. So, 
one thing we prompted our models to do is to use  
this interleaf thinking to really reflect on the 
quality of the search results and decide if they  
need to verify them, if they need to get more 
information, or if they should add a disclaimer  
about how the results might not be accurate. Um, 
another point with when prompting agents is that  
agents are more unpredictable than workflows 
or just, you know, classification type prompts.  
Most changes will have unintended side effects. 
This is because agents will operate in a loop  
autonomously. And so for example, if you tell the 
agent, you know, keep searching until you find the  
correct answer, you know, find the highest quality 
possible source and always keep searching until  
you find that source. What you might run into is 
the unintended side effect of the agent just not  
finding any sources. Maybe this perfect source 
doesn't exist for the for the query. And so it  
will just keep searching until it hits its context 
window. And that's actually what we ran into as  
well. And so you have to tell the agent if you 
don't find the perfect source, that's okay. You  
can stop after a few tool calls. Um, so just be 
aware that your prompts may have unintended side  
effects and you may have to roll those back. 
Another point is to help the agent manage its  
context window. The Cloud 4 models have a 200k 
token context window. Um, this is long enough for  
a lot of longrunning tasks, but when you're using 
an agent to do work autonomously, you may hit this  
context window and there are several strategies 
you can use to sort of extend the effective  
context window. One of them that we use for cloud 
code is called compaction. And this is just a tool  
that the model has um that will automatically be 
called once it hits around 190,000 tokens. So near  
the context window. And this will summarize 
or compress everything in the context window  
to a really dense but accurate summary that is 
then passed to a new instance of claude with the  
summary. And it continues the process. And we find 
that this essentially allows you to run infinitely  
with cloud code. You almost never run out of 
context. um occasionally it will miss details  
from the previous session but the vast majority of 
the time this will keep all the important details  
and the model will sort of remember what happened 
in the last session. Similarly you can sort of  
write to an external file. So the model can have 
access to an extra file and these cloud for models  
are especially good at writing memory to a file 
and they can use this file to essentially extend  
their context window. Another point is that you 
can use sub aents. Um, we won't talk about this  
a lot here, but essentially if you have agents 
that are always hitting their context windows, you  
may delegate some of what the agent is doing to 
another agent. Um, which can sort of, for example,  
you can have one agent be the lead agent and then 
sub agents do the actual searching process. Then  
the sub agents can compress the results to the 
lead agent in a really dense form that doesn't  
use as many tokens and the lead agent can give the 
final report to the user. So we actually use this  
process in our research system and this allows you 
to sort of compress what's going on in the search  
and then only use the context window for the lead 
agent for actually writing the report. So this  
kind of multi- aent system can be effective 
for limiting the context window. Finally,  
you can let Claude be Claude. And essentially 
what this means is that Claude is great at being  
an agent already. You don't have to do a ton of 
work at the very beginning. So, I would recommend  
just trying out your system with sort of a bare 
bones prompt and barebones tools and seeing where  
it goes wrong and then working from there. Don't 
sort of assume that Claude can't do it ahead of  
time because cloud often will surprise you with 
how good it is. Um, I talked already about tool  
design, but essentially the key point here is you 
want to make sure that your tools are good. Um,  
what is a good tool? It will have a simple 
accurate tool name that reflects what it does.  
You'll have tested it and make sure that it works 
well. um it'll have a well-formed description  
so that a human reading this tool like imagine 
you give a function to another engineer on your  
team would they understand this function and be 
able to use it. You should ask the same question  
about the agent computer interfaces or the tools 
that you are giving your agent. Make sure that  
they're usable and clear. Um we also often find 
that people will give an agent a bunch of tools  
that have very similar names or descriptions. 
So for example, you give it six search tools  
and each of the search tools searches a slightly 
different database. This will confuse the model.  
So try to keep your tools fairly distinct 
um and combine similar tools into just one.  
So, one quick example here is just that you can 
have an agent, for example, use these different  
tools to first search the inventory in a database, 
run a query. Based on the information it finds, it  
can reflect on the inventory, think about it for 
a little bit, then decide to generate an invoice,  
generate this invoice, think about what it should 
do next, and then decide to send an email. And so,  
this loop involves the agent getting information 
from the database, which is its external  
environment, using its tools, and then updating 
based on that information. until it accomplishes  
the task. And that's sort of how agents work 
in general. So, let's walk through a demo real  
quick. I'll switch to my computer. Um, so you can 
see here that this is our console. The console is  
a great tool for sort of simulating your prompts 
and seeing what they would look like in a UI. Um,  
and I use this while we were iterating on research 
to sort of understand what's really going on and  
what the agents doing. This is a great way to 
think like your agents and sort of put yourself  
in their shoes. So, you can see we have a big 
prompt here. Um, it's not sort of super long.  
It's around a thousand tokens. It involves the 
researcher going through a research process. We  
tell it exactly what should what it what it should 
plan ahead of time. We tell it how many tool  
calls it should typically use. We give it some 
guidelines about what facts it should think about,  
what makes a high quality source, stuff like 
that. And then we tell it to use parallel tool  
calls. So, you know, run multiple web searches in 
parallel at the same time rather than running them  
all sequentially. Then we give it this question. 
How many bananas can fit in a Rivian R1S? This  
is not a question that the model will be able 
to answer because the Rivian R1S came out very  
recently. It's a car. It doesn't know in advance 
all the specifications and everything. So, it'll  
have to search the web. Let's run it and see what 
happens. You'll see that at the very beginning,  
it will think and break down this request. And 
so, it realizes, okay, web search is going to  
be helpful here. I should get cargo capacity. 
I should search. Um, woo. Um, and you see here  
it ran two web searches in parallel at the same 
time. That allowed it to get these results back  
very quickly. And then it's reflecting on the 
results. So it's realizing, okay, I found the  
banana dimensions. I know that a USDA identifies 
bananas as 7 to 8 in long. I need to run another  
web search. Let me convert these to more standard 
measurements. You can see it's using tool calls  
interled with thinking, which is something 
new that the quad 4 models can do. Finally,  
it's running some calculations. It's about how 
many bananas could be packed into the cargo space  
of the truck. And it's running a few more web 
searches. You can see here that this is a fairly
pending
approximately 48,000 bananas. I've seen the model 
estimate anything between 30,000 50,000. I think  
the right answer is around 30,000. So this is this 
is roughly correct. Um going back to the slides,  
I think that you know this this sort of approach 
of testing out your prompt, seeing what tools  
the model calls, reading its thinking blocks, 
and actually seeing how the model's thinking  
will often make it really obvious. um what the 
issues are and what's going wrong. So you'll  
test it out and you'll just see like okay 
maybe the model's using too many tools here,  
maybe it's using the wrong sources or maybe 
it's just following the wrong guidelines. Um  
so this is a really helpful way to sort of think 
like your agents and make them more concrete.
Um switching back to the slides.
Okay, so eval evaluations are really important 
for any system. Um, they're really important  
for systematically measuring whether you're 
making progress in your prompt. Very quickly,  
you'll notice that it's difficult to really make 
progress on a prompt if you don't have an eval  
that tells you meaningfully whether your prompt is 
getting better and whether your system is getting  
better. But eval are much more difficult for 
agents. Um, agents are longunning. They do a bunch  
of things. They may not they may not always have 
a predictable process. classification is easier to  
eval because you can just check did it classify 
this output correctly but agents are harder. So  
a few tips to make this a bit easier. One is that 
the larger the effect size the smaller the sample  
size you mean you need um and so this is sort of 
just a principle from science in general where  
if an effect size is very large for example if a 
medication will cure people immediately you don't  
really need a large sample size of a ton of people 
to know that the model is that that this treatment  
is having an effect. Similarly, when you change a 
prompt, if it's really obvious that the system is  
getting better, you don't need a large eval. I 
often see teams think that they need to set up  
a huge eval of like hundreds of test cases and 
make it completely automated when they're just  
starting out building an agent. This is a failure 
mode and it's an antiattern. You should start out  
with a very small eval and just run it and see 
what happens. You can even start out manually. Um,  
but the important thing is to just get started. 
I often see teams delaying evals because they  
think that they're so intimidating or that they 
need such a sort of intense eval to really get  
some signal, but you can get great signal from 
a small number of test cases. You just want to  
keep those test cases s consistent and then keep 
testing them so you know whether the model and  
the prompt is getting better. You also want to 
use realistic tasks. So don't just sort of come  
up with arbitrary prompts or descriptions 
or tasks that don't really have any real  
correlation to what your system will be doing. 
For example, if you're working on coding tasks,  
you don't won't want to give the model just 
competitive programming problems because this is  
not what real world coding is like. You'll want to 
give it realistic tasks that really reflect what  
your agent will be doing. Similarly, in finance, 
you'll want to sort of take tasks that real people  
are trying to solve and just use them to evaluate 
whether the model can do those. This allows you  
to really measure whether the model is getting 
better at the tasks that you care about. Another  
point is that LLM is judge is really powerful, 
especially when you give it a rubric. So agents  
will have lots of different kinds of outputs. 
For example, if you're using them for search,  
they might have tons of different kinds of search 
reports with different kinds of structure. But LMS  
are great at handling lots of different kinds of 
structure and text with different characteristics.  
And so one thing that we've done, for example, 
is given the model just a clear rubric and then  
ask it to evaluate the output of the agent. 
For example, for search tasks, we might give  
it a rubric that says, check that the model, 
you know, um, looked at the right sources,  
check that it got the correct answer. In this 
case, we might say, um, check that the model  
guessed that the amount of bananas that can fit 
in a Rivian R1s is between like 10,000 and 50,000.  
Anything outside that range is not realistic. So, 
you know, you can use things like that to sort of  
benchmark whether the model is getting the right 
answers, whether it's following the right process.  
At the end of the day though, nothing is a perfect 
replacement for human evals. You need to test the  
system manually. You need to see what it's doing. 
You need to sort of look at the transcripts, look  
at what the model is doing, and sort of understand 
your system if you want to make progress on it.  
Here are some examples of eval. So one example 
that I sort of showed uh talked about is answer  
accuracy. And this is where you just use an LLM 
as judge to judge whether the answer is accurate.  
So for example in this case you might say the 
agent needs to use a tool to query the number  
of employees and then report the answer and then 
you know the number of employees at your company.  
So you can just check that with an LM as judge. 
The reason you use an LMS as judge here is because  
it's more robust to variations. For example, if 
you're just checking for the integer 47 in this  
case in the output that is not very robust and 
if the model says 47 as text you'll grade it  
incorrectly. So you want to use an LMS as judge 
there to be robust to those minor variations.  
Another way you can eval agents is tool use 
accuracy. Agents involve using tools in a  
loop. And so if you know in advance what tools 
the model should use or how it should use them,  
you can just evaluate if it used the correct tools 
in the process. For example, in this case, I might  
evaluate the agent should use web search at least 
five times to answer this question. And so I could  
just check in the transcript programmatically did 
the tool call for web search appear five times or  
not. Similarly, you might check in this case 
for in response to the question book a flight,  
the agent should use the search flights tool 
and you can just check that programmatically  
and this allows you to make sure that the right 
tools are being used at the right times. Finally,  
a really good eval for agents is tobench. You 
can sort of look this up. Towen is a sort of open  
source benchmark that shows that you can evaluate 
whether agents reach the correct final state.  
So a lot of agents are sort of modifying a 
database or interacting with a user in a way  
where you can say the model should always get to 
this state at the end of the process. For example,  
if your agent is a customer service agent for 
airlines and the user asks to change their flight  
at the end of the agentic process in response to 
that prompt, it should have changed the flight in  
the database. And so you can just check at the end 
of the agentic process, was the flight changed?  
was this row in the database changed to a 
different date and that can verify that the  
agent is working correctly. This is really robust 
and you can use it a lot in a lot of different use  
cases. For example, you can check that your 
database is updated correctly. You can check  
that certain files were modified, things like 
that as a way to evaluate the final state that  
the agent reaches. And that's it from us. Um, 
we're happy to take your questions. [Applause]
Can you talk about building prompts for agents? 
Are you giving it kind of long longer prompts  
first and then iterating or you starting kind 
of chunk by chunk? Uh what's that look like?  
And can you show sort of a little bit more on that 
thought process? That's a great question. Um can  
I switch back to my screen actually? I just want 
to sort of show the demo. Thank you. Um, yeah. So,  
you can see this is sort of a final prompt 
that we've arrived at, but this is not where  
we started. I think the answer to your question 
is that you start with a short simple prompt.
Um, and I might just say search the web 
aentically. I'll change this to a different  
question. Um, how good are the Cloud 4 models 
and then we'll just run that. And so you'll  
want to start with something very simple and just 
see how it works. You'll often find that Claude  
can do the task well out of the box. But if you 
have more needs and you need it to operate really  
consistently in production, you'll notice edge 
cases or small flaws as you test with more use  
cases. And so you'll sort of add those into the 
prompt. So I would say building an agent prompt  
what it looks like concretely is start simple, 
test it out, see what happens, iterate from there,  
start collecting test cases where the model fails 
or succeeds and then over time try to increase the  
number of test cases that pass. Um, and the way 
to do this is by sort of adding instructions,  
adding examples to the prompt. But you really 
only do that when you find out what the edge  
cases are. And you can see that it thinks that 
the models are indeed good. So that's great.  
when I do like normal prompting and it's not 
agentic, uh I'll often give like a few shot  
example of like, hey, here's like input, 
here's output. This works really well for  
like classification tasks, stuff like that, right? 
Uh is there a parallel here in this like agentic  
world? Are you finding that that's ever helpful 
or should I not think about it that way? That is  
a great question. Yeah. So should you include 
fewshot examples in your prompt and sort of  
traditional prompting techniques involve like 
giving the saying the model should use a chain  
of thought and then giving a few shot examples 
like a bunch of examples to imitate. We find  
that these techniques are not as effective for 
state-of-the-art frontier models and for agents.  
Um the main reason for this is that if you give 
the model a bunch of examples of exactly what  
process it should follow, that just limits the 
model too much. These models are smarter than  
you can predict and so you don't want to tell 
them exactly what they need to do. Similarly,  
chain of thought has just been trained into the 
models at this point. The models know to think  
in advance. They don't need to be told like use 
chain of thought. But what we can do here is one  
you can tell the model how to use its thinking. 
So you know I talked about earlier rather than  
telling the model you need to use a chain of 
thought. It already knows that. You can just  
say use your thinking process to plan out your 
search or to plan out what you're going to do  
in terms of coding. Reme or you can tell it to 
remember specific things in its thinking process  
and that sort of helps the agent stay on track. 
As far as examples go, um you'll want to give  
the model examples but not too prescriptive. 
I think we are out of time, but you can come  
up to me personally and I'll talk to you all 
after. Thanks. Thank you. Thanks for coming.

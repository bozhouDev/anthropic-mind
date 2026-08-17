---
title: "Building AI agents with Claude in Amazon Bedrock | Code w/ Claude"
source: "https://www.youtube.com/watch?v=8gTpgWru0Wg"
published_at: 2025-07-31
captured_at: 2026-08-16
author: Anthropic
source_type: youtube
authority_score: P2
mind: engineering
status: captured
evidence_url: "https://www.youtube.com/watch?v=8gTpgWru0Wg"
catalog_id: 3b35ce7cfc98
subtitle_file: 8gTpgWru0Wg.en.vtt
---

Kind: captions
Language: en
Building AI agents with Claude in Amazon 
Bedrock. Today I am excited to explore how  
to create intelligent autonomous AI systems that 
can transform your applications. My name is Dwan  
Lightoot. I am a developer advocate at AWS. 
I'm Banjo. I'm a systems architect at AWS. Hi  
everyone. My name is Suman DNA. I'm a developer 
advocate at AWS. Now, this will be a hands-on  
keyboard event. So, we have a live workshop where 
you can log into an environment and get started  
with some code. So, we're going to go through a 
few slides to kind of level set and get everyone  
on the same page and then we'll hop into the 
workshop. Now this is code with Clyde and one of  
the things that I want to talk about is enthropic 
on AWS. To do that we have Amazon bedrock which  
which is a fully managed service that provides you 
access to powerful foundational models like those  
in the cloud family through a unified API. This 
gives you everything you need to not only build  
but also scale your AI applications globally. And 
it does this by providing you with everything you  
need model choice guard rails as well as it gives 
you security at enterprise grade at default. Now  
we're talking agents. That's what everyone is 
here to see. But we kind of need to level set  
what that really means. And at AWS, we explain it 
like this. An agent is an auton autonomous system  
that can reason, plan, and take multiple 
steps to perform an objective like humans.  
So if you have a task and you give it to an agent, 
the agent is able to take that task and say here  
is the highle objective. Let me create a plan of 
the steps that I need to take. Then it could take  
actions on those steps. And once those steps have 
been taken on those steps, then it can evaluate  
the results and reason on what needs to happen 
next until it actually achieves that objective.  
This is an agitic system that we'll be discussing 
today. Now at AWS, we've also done something  
awesome that my colleague Suman is going to talk 
about at this time. Thank you so much Dan. So  
taking one step further what we have done in 
fact last week last Friday we have announced  
an open-source SDK to build agentic application 
called strands agent. So what this agent does is  
it's a very simple SDK which needs three things 
models tools and prompt. It cannot go any simple  
than that. It doesn't have any scaffolding 
that you don't have to guard rail your prompts  
um your backstory goals etc. What we believe in is 
that in today's world the LLMs are pretty strong  
and we want to make use of the full strength 
of the model in the back end. So we are giving  
the better flexibility for the model to reason on 
behalf of us. And that's why if you look at this  
architecture it's very straightforward. You create 
a prompt or this is your question. You send it to  
the agent which is the strands agent. And when you 
create an agent object, you will define the model  
and tools that we provide to you. You will see in 
the workshop when Banjo will go through a couple  
of the demos, you will see that the default 
model that we use is claw 3.7 as of today.  
And the moment you have strands installed and 
configured, you get a bunch of tools inbuilt.  
So you don't have to write heavy lifting code to 
create few of your basic needs. And the best part  
is not only for your testing and deployment in 
the test environment, you can actually deploy on  
the cloud. So assume that you have your workforce 
in EC2 or Lambda or ECS, you can just deploy your  
code with ease uh with a integrated uh support 
for all these services. So to get started just  
uh take a snap of this. This contains the launch 
blog as well as the documentation which is nothing  
but strands.com and the GitHub. And this is 
an open-source uh project. So feel free to  
uh give a star and uh you know just uh raise 
a PR if you have anything interesting that you  
build or if you have any specific requirement 
which is not there uh feel free to contribute.  
It's just 3 days old and we got many PR and uh 
feedback from the community and we would love  
to work with all of you. All right so the moment 
you're all waiting for. it's time to build. So,  
we have pre preconfigured AWS accounts for you. 
Uh, VS Code is also configured. So, there's  
nothing you need to download. Everything is done 
in the browser. So, when you go to this URL, it's  
going to take you to a popup screen and you're 
going to uh sign in. You're going to it's going  
to ask you for a one-time password. Uh, that's the 
best way to log in. And once you do that, you're  
going to be able to have access to the AWS account 
as well as the VS Code server we spun up. So,  
uh, we're going to take a few minutes to get set 
up. I always say this is the hardest part of the  
workshop. So, uh, Tuman and Dan are going 
to be walking through. Ask any questions,  
raise your hand, and I'll also walk through it. 
But, uh, take some minutes to get started and,  
uh, let's get start building. So, when you log in, 
you'll get to a screen like this. So, I'll give  
a couple more minutes to to get to the screen. 
Then, I'll walk through setting up Bedrock so  
we can have access to the models and then to our 
VS Code server. Well, while people are waiting,  
I have a video to highlight what strands can do. 
So, I can just show that in the meantime. Uh,  
so this example, we actually have a strands agent 
that's actually going to uh create a math video  
for this. So, it's actually pretty cool. So, let's 
see what happens here. So, it's running an MCP  
server. It's going to start that uh requirements. 
It's going to actually create an animation video  
for us. So it's going to create a maximum scene 
that draws a cubic function. Uh 2x cubed uh yeah  
something something hard that you might have to 
do in latex scientific like this is very annoying  
but we'll see how the MCP server is actually going 
to build it and actually make a video to highlight  
it. How many of you have uh heard of three blue 
one brown? So that is what you are going to see  
now. So we have created an MCP server which can 
create the videos that you see in three blue one  
brown. So we have created a quadratic equation and 
we wanted to plot that within the range of minus3  
to 3 and this is powered by cloud 3.7 and strands. 
So uh we'll push that code in the GitHub repo  
which we have shared earlier but uh this is just 
a testimony of how you can get started quickly  
with the out of the box tools and just few lines 
of code. Thank you. So the first thing to do uh  
is make sure you log into this AWS account. So you 
should not be using your own AWS account. We have  
already provisioned one with all the resources 
needed. Let's open AWS console and it'll open up  
a new account new like this. You should see this 
work stop participant role. So you should not be  
using your own AWS account if you have it. From 
here we're going to type bedrock Amazon Bedrock.
So we get to the Amazon Bedrock console 
screen. We're going to want to enable  
the models so we can use them in our 
app in our lab. So give it a second.  
I'm going to scroll down to this model access 
button and then I click the modify model access  
and we got some new models but they have not 
enabled them yet. So we're just going to use  
claude v7 uh 3.5 hiq and 3.5 sonnet. So enable 
those. Got the four already. We got four already.  
Yes. But I don't think it's enabled in this 
account yet. So we got to use the older models.  
So and press next. Um once we request access 
submit but again this code all the code is  
open source the workshop is open source and we can 
share the link so you can run this on yourself. So  
uh module one is the one we're doing today. 
So we're going to show you how strand agent  
works and how you can actually build a aentic 
workflow with it. So the first thing you do  
is install it. So just doing pip install strand 
agents and strand agent tools gets you what you  
need and have some utility things UV to download 
MCP servers. So I'm going to copy that command
paste
right already installed great so and then the 
cool thing with cloud code you actually can use  
it of Amazon Bedrock. So if you have an ads 
account, you have bedrock, you can use cloud  
code without using the entropic key signing in 
everything is just done through bedrock. That's  
by using this export cloud code uh environment 
variable. So let me go ahead and do that.
All right. So claude get started research preview. 
Gonna push dark mode of course. All right. Cool.  
So use recommended settings. Yes, proceed. All 
right, cloud code is ready to go. So all I did  
was just export that command because it's already 
using Bedrock. Everything's just ready to go. It's  
already in my environment. And you all can see 
this, right? This is a good screen. Yeah. Cool.
All right. So the first uh exercise of the 
workshop, we're actually going to use a  
weather count. Every AI thing has to start with 
weather first. So, you know, well, we added two  
tools to this one. One that can actually get the 
weather and then actually count how many words  
are in the response just to show how easy it is to 
use different tools using strands. So, and we're  
actually going to use cloud code to explain how 
this code works as well before I dive into it. So,  
I'm going to open this up. Paste. Can you explain 
the structure of the strand agent warther world  
count file? All right. So then it's going to be 
able to see what happens. Use the tokens. Let  
me open the file while it does that and we'll 
see what Claude says. Let me make this bigger.
All right. So demonstrate a simple agent 
implementation. the Stram framework agent  
file import necessary word count tools using 
cloud 3.5 executed query so let's walk through  
the code in more detail so we actually have a 
system prompt and we're saying you know find the  
weather and it actually puts the API in the system 
prompt httpe.gov gov. So there's no API key needed  
for this. So I can just query this and get the 
actual weather of what the place is and provide  
in a human readable way. And the cool thing about 
this uh strands has this HTTP request tool already  
built into the framework. So it's going to be able 
to just make that request for you automatically.  
You just provide URL is able to call that and 
get the actual data from that. And then you can  
you the cool thing about strands also is you 
can change the different models you can use.  
You can use light lm, you can use lama, uh you 
can use bedrock. Bedrock's the default. So I just  
changed the claw 3.5 just to be faster here. Uh 
and then the cool thing about strange is that's  
the system prompt. The big system prompt we put 
up there which tools we're going to use the word  
count tool. Now what I really like about the tool 
decorator is I just define a function and just put  
the return value. There's no crazy things, no 
adding. I just put this tool decorator and it  
handles the rest. So as a developer is building 
functions, I want to put all this extra stuff in  
there, make it as simple as possible to have 
a tool. So that's a really big plus to the  
strands framework. And then from there, I can 
just say, what's the weather like in Seattle?  
Let's change it. San Francisco and let's go 
to the terminal. Oops. Strand agent three.
All right. So we can see how it's going here. Uh 
first I'll get the coordinates for San Francisco.  
You can see the HTTP request tool. Now it's 
going to use the HTTP request to find that  
weather. It gets the San Francisco 65 sunny west 
winds few days highlight. Now uses the word count  
tool 110 words. So with about 44 lines of code 
we're able to make that API request. We have the  
agent. It's going to have multiple tools. Done. 
So I'll pause here for a second just to have any  
questions of strands because not everybody's 
going through it. So Strand is a open source  
SDK for building agents. So there are a lot of 
agentic frameworks but strand is it own one and  
you can see that you really just need a system 
prompt the tools and a model and it can execute  
that loop. So yeah it is similar to other agentic 
frameworks but I believe it's much easier to get  
started without the boiler plate and extra 
stuff that you've seen in other frameworks.  
All right, one more question and we'll move 
on to the next part. Uh, thank you. So,  
I have a code related question. So, how are you 
passing like the latitude, longitude, and zip  
code like inside the string? So, so the cool thing 
is that we're letting the model decide how to do  
that. It it uses this HTTP request thing and it 
understands what the latitude and longitude is of  
San Francisco and is able to pass that to this API 
endpoint or use API zip code. So it understands  
the what the API is based on the system prompt 
and the model is figuring that out by itself.  
So we're handing a lot of the infrastructure you 
might see in other agent frameworks saying you got  
to do this, you got to do this. We're letting 
the model decide to do that because the models  
are much more capable than they were two years ago 
when you saw the first type of agentic frameworks  
coming out. So this trans tools uh like I see 
that you're importing two tools uh which is like  
word count and HTTP request. So how many tools are 
there like? Yeah. Yeah. So there's some built-in  
tools in the strand framework like HTTP request 
but then I also just made my own tool which is  
literally this one line of code return this lens. 
So it's very easy to make your own custom tools.  
You just put this tool decorator and that's it. So 
very very streamlined. All right. So we're going  
to move on to the next exercise. Uh so the next 
exercise is fun one. MCP servers. So you know MCP  
is the hottest thing you know. So, uh, what's 
really cool about strand, it has built-in MCC  
support and AWS, we actually have official AWS, 
uh, MCP servers. So, I'm going to highlight the  
documentation lookup because AWS can be very long, 
a lot of different things. So, if I just have one  
endpoint to just grab that information and pass it 
to the model, it's going to be able to understand  
how to build. And there's an architecture diagram. 
So, making AWS diagrams. So there are two MC  
there's a whole bunch of them listed here but I'm 
going to highlight these two an example. So let's  
go back and we can also ask claude code to explain 
it as well. So get back me open my cloud code.
So I have to explain how the MCP 
diag one works. So let me open  
that up while it's waiting. Let me close that.
Cloud code's documenting. It's looking what to do.
It's taking it taking its time.
So while cloud code is going, I'll explain 
what's happening. That just finished. Cool.  
All right. Import the strand. Still going. All 
right. So the cool thing about uh MCP server is  
we can actually just pull it in with one line. 
We just the command uvx. This is uh the Python  
material for downloading things. So we can just 
point it to the MCP server and it'll download it  
locally. So I'm passing in uh the documentation 
MCP server and I'm passing in the diagram MCP  
server and then you know claude even saying 
the same thing connect to the MC diagram run  
one configure using Bedrock again I can choose 
different models on Bedrock to pass in and then  
I'm giving a system prompt you an extra certified 
solutions architect your role to help customers  
understand best practices query documentation 
generate diagrams tell the customer the full  
path of the diagram when you create it just so 
we know where it is and then again we just Okay,  
we pass in multiple MCP servers with the diagram 
client with the docs client. Uh we get all the  
tools based in those uh MCP servers and then 
again you know we have the tools we have the  
model and the system prompt. All you need to have 
the the stand agent and then we give it like get  
the documentation for AWS Lambda then create a 
diagram of a website that uses lambda for a static  
website hosted on S3. So that's the task I give 
it. Let's see how it executes that. So oops. All
right. So downloads the MCP server. It's already 
downloaded that already and now it's processing.  
Now it breaks it down into steps. So first 
I'll search the AW documentation. Then I'll  
read the documentation. Then I'll create a diagram 
illustrating architecture. So you can actually see  
it stop process. It makes an HTTP call to get the 
the search. It finds the Lambda welcome page to  
get the information. It queried the documentation. 
Now it's going to draw the diagram. Let's see.
It listed the icon. So what icons are available 
for it. Now it's actually generating the diagram.  
So excellent. It failed there, but it understood 
that and explained. Let me correct the cloud icon.  
Now it generated it, explained what's happening, 
and it made this new diagram saved here. So I  
should be able to open it up. Generated diagrams. 
And tada, it made a new diagram for me. So,  
whoops. Let me Yeah, it's going to be different 
every time when you of course based on how much  
context you give it. But yeah, I'm able to 
make that diagram and just about, you know,  
40 lines of code. I have two MCP servers. I put 
my system prompt picking a different model and I'm  
able to create that agentic workflow very quickly 
and very easily without any too much headache.  
So I'm going to pause here and he talks about MCP 
servers connecting maybe with a strange agents.  
Is there a pattern um through API gateway 
to host a MCP server with lambda like the  
server side events? Is there something that 
allows Yeah. Yeah. Now because MCP supports  
the HTTP streaming server side event you can 
have it in a Lambda function and do that. There  
are some I believe there are some open source 
code that demonstrates how to do that. One of  
my colleagues has done that. So yes, totally 
possible to do that use case because right  
now I'm just running the MCP ser locally, 
but if you wanted to have it in the cloud,  
I got a lambda function. Totally possible use 
case. You would have to change how this is set up.
All right. So the last exercise was 
we're actually going to create a new  
uh a new agent using cloud code to understand 
how it does uh without just looking at the code  
we have already and able to understand which CDK 
I'm going to make a CDK agent. So CDK is a cloud  
development kit. So it's a way to create uh AWS 
infrastructure through code. Uh normally if you  
want to create as infrastructure you might use 
something like cloud formation which is a YAML  
based way but if it's a developer uh CDK is more 
preferred for that because you can integrate the  
python typescript code. So I'm going to 
show an example of how we can use claude  
code to actually create a new strand agent 
for us. So going to make this new file here.
Oops.
All right. So I created a brand new file, nothing 
in it. And then I'm going to ask claude code, you  
know, update the CDK agent to create a stand agent 
connecting to an MCP server. Uh look at the other  
files to understand how to do this. So I'm not 
giving you the documentation. I'm just going to  
say, you know, use the knowledge you have already 
to understand how to to make it. So, let me
let me get into the repo and then claude
and ask it.
So, yeah. Yeah. So now cloud code 
is going to look through. We'll see  
the plan of attack it does. So let's 
let's see what it's doing. All right.
I'll update the CDK agent to CL agent 
connected to MCP server. You know it  
looks at the other one. There's no one 
line of code there. It read the other  
word count one. All right. It finds the MCP 
doc one. Examines it. Cross it off the list.  
All right. On to the next one. Create a stand 
agent. It put all the code for that. It asks  
me do I want to make this edit. So say yes, 
make the edit. It's adding the code to me.
All right, configure ready. Then MCP client 
configure system prompt. It's done it. Perfect.  
So close out of it. And what I like about cloud 
code actually tells us how much it costs when  
you end it. So the total cost, how long the 
API took, you know, how many code changes,  
how which models it used, it use cloud 3.5 
site haiku, use cli. So uh using cloud code  
of bedrock is that's an easy way to get started 
in building applications like this and it's now  
natively inside VS code which is very exciting. 
So let's see if the code actually works. So  
uh I'm just going to run it. Let's see you're 
expert AWS CDK expert. Uh how can I get a simple  
S3 bucket with CDK? Give us something simple. 
Let's see how it works. Python 3 CDK agent.
All right. So, I was making a TypeScript example.  
I'll provide step-by-step guidance. It 
wrote the code for me. It's doing that
security text this add a CNN nag rule. So, it 
really understands what CDK is. It's putting  
all this extra stuff there. Uh, and yeah, it 
even explained that. So cloud code is able  
to understand how strand agent works create 
a new agent based on that create a template  
on that and it was very easy to understand. So by 
providing the enough context cloud code was able  
to understand what to do create this agent and 
it's pretty good job. So very impressed with using  
cloud code and bedrock power that's also amazing. 
Uh but that was kind of the workshop through and  
through kind of to show you what strands can do 
from a simple weather agent to connecting to MCP  
servers and then also making your own agents. So, 
I'm going to pause here for any questions or if  
you want to see a demonstration of something cool, 
happy to try it out and see what Claude can do.  
Uh, sorry, I just have to ask like what are some 
of the use cases for like using MCP? Like I know  
I will be building agents that probably connect 
to the outer world like through APIs and all like  
uh maybe I don't know a lot about MCPs. So, but 
like what are some of the use cases you can like  
use MCPS for? Right. So, a great question. What 
are the use cases for MCP? So by default the agent  
doesn't have enough information to ex connect 
to external API. So you saw in the example we  
created an AWS diagram. If I did that without an 
MCP server the model will not know how to make  
the AWS diagram. It won't know how to look 
up the AWS augumentation. So it's providing  
extra context to the model to do extra action. 
So when it comes to using large things model  
context is really what empowers what's going 
to go on. MCP provides a structured way to  
grab that information so it can take action, 
read documentation, uh connect to external  
applications. So MCP is really kind of the USBC 
they call it of connecting the LLM. So for me  
it's a great way to just connect uh external 
applications get different context for your model
and I'll show you some highlights of the AWS MCP  
servers just so you can get 
a example of what we have.
So there are official list of AWS MCP servers that 
do a bunch of different things. So I'll go through  
some examples. uh show the documentation one uh 
bedrock knowledge base if you have a bunch of PDFs  
or documents you want to give to an LLM uh cost 
analysis so you want to do AWS cost analysis you  
want to get a another example uh the MCP server 
could be useful for you uh Amazon Nova Canvas if  
you want to draw images uh Nova canvas MVC server 
the diagram one that we use today you can also  
draw AWS architecture diagrams cloud formation so 
there's a bunch of different ones and Terraform  
if you use Terraform form uh front-end code you 
want to specialize in react or using ads amplify  
etc. So there's a whole source of M MCP 
servers. So one big use case is I want my model  
to understand these things. You have a bunch of 
documentation Postgress database, Amazon Neptune  
server like so this is really the power of MCP. So 
there's so many integrations you can have to give  
that model extra abilities to do. Uh we do have 
AWS credits for you. So if you want to give us  
some feedback and surveys and once you fill this 
out, you'll get uh we have $25 in AWS credits to  
use. So you can play around, try some things out. 
Uh, but thank you for coming and let's go build.

---
title: "Vibe coding in prod | Code w/ Claude"
source: "https://www.youtube.com/watch?v=fHWFF_pnqDk"
published_at: 2025-07-31
captured_at: 2026-08-16
author: Anthropic
source_type: youtube
authority_score: P2
mind: engineering
status: captured
evidence_url: "https://www.youtube.com/watch?v=fHWFF_pnqDk"
catalog_id: a23fc344f356
subtitle_file: fHWFF_pnqDk.en.vtt
---

Kind: captions
Language: en
Hey everyone, welcome. I'm here to talk 
about everyone's uh favorite subject,  
vibe coding. Uh and somewhat uh controversially, 
how to vibe code in prod responsibly. So let's  
uh let's talk about vibe coding and like 
uh what this even is. So first of all,  
I'm Eric. I'm a researcher at Enthropic uh focused 
on coding agents. Uh I was the author along with  
Barry Zang of building effective agents where we 
outlined uh for all of you our best science and  
best practices for creating agents no matter 
what the application is. Uh this is a subject  
that's near and dear to my heart. Uh last year I 
actually broke my hand while biking to work and  
was in a cast for two months and Claude wrote all 
of my code for those two months. And so figuring  
out how to make this happen effectively uh was 
really important to me and I was luckily able to  
figure that out well and sort of help u bring that 
into a lot of anthropics other products and in our  
models through my research. So let's first start 
talking about what is vibe coding. A lot of people  
really conflate vibe coding with just extensive 
use of AI to generate your code. But I think  
this isn't quite true. A lot of people, you know, 
they're using cursor, they're using co-pilot. Um,  
it's a lot of AI and a lot of the code is coming 
from the AI rather than them writing itself. But I  
think when you are still in a tight feedback loop 
with the model like that, that isn't truly vibe  
coding. When I say vibe coding, I think we need 
to go to Andre Carpathy's definition where vibe  
coding is where you fully give into the vibes, 
embrace exponentials, and forget that the code  
even exists. I think the key part here is forget 
the code even exists. And now the reason this is  
important is that vibe coding was when people 
outside of the engineering uh industry really  
started getting excited about code generation. 
Copilot and cursor were great but only sort of for  
uh engineers but someone that didn't know how to 
code uh suddenly with vibe coding they could find  
themselves coding an entire app by themselves. 
And this was a really exciting thing and a big  
unlock to a lot of people. Now, of course, uh 
there were a lot of downsides of this and you  
had people coding for the first time and really 
without knowing what they were doing at all. Um  
and you said, "Hey, you know, random things 
are happening, max out usage on my API keys,  
people are bypassing the subscription, creating 
random [ __ ] on the DB." Uh, and so, you know,  
this this is kind of the downside of vibe coding 
of what started happening. And the positive sides  
of vibe coding that you'd see were all things 
that were really kind of low stakes. It was  
people building video games, building sort of fun 
side projects, things where uh it's okay if there  
was a bug. So, you know, why do we even care about 
vibe coding if it seems like something where the  
stakes are really high if you do it for a real 
product? And the most successful cases of it are  
kind of these toy examples or fun things where 
the stakes are very low. And my answer for why  
we should care about vibe coding is because of the 
exponential. The length of tasks that AI can do is  
doubling every seven months. Right now we're at 
about an hour. And that's fine. You don't need to  
vibe code. You can have cursor work for you. You 
can have clawed code write a feature that would  
take an hour. Um, and you can review all that code 
and you can be still be intimately involved uh,  
as the AI is writing a lot of your code. But 
what happens next year? What happens the year  
after that? When the AI is powerful enough that 
it can be generating an entire day's worth of  
work for you at a time or an entire week's worth 
of work, there is no way that we're going to be  
able to keep up with that if we still need to move 
in log stack. lock step. And that means that if we  
want to take advantage of this exponential, we 
are going to have to find a way to responsibly  
give into this and find some way to leverage this 
task. Um, I think my favorite analogy here is like  
compilers. I'm sure in the early day of compilers, 
a lot of developers, you know, really didn't trust  
them. They might use a compiler, but they'd still 
read the assembly that it would output to make  
sure it looks, you know, how they would write the 
assembly. But that just doesn't scale. You know,  
at a certain point, you start needing to work on 
systems that are big enough that you just have  
to trust the system. The question though is how 
do you do that responsibly? And I think sort of  
my challenge to the whole software industry 
over the next few years is how will we vibe  
code in prod and do it safely? And my answer 
to that is that we will forget that the code  
exists but not that the product exists. Thinking 
again to that compiler analogy, you know, we all  
still know that there's assembly under the hood, 
but hopefully most of us don't need to really  
think about what the assembly actually is. But we 
still, you know, are able to build good software  
without understanding that assembly under the 
hood. And I think that we will get to that same  
level with software. And one thing I really want 
to emphasize is that this is not a new problem.  
How does a CTO manage an expert in a domain where 
the CTO does not is not themselves an expert? How  
does a PM review an engineering feature when they 
themselves can't read all the code that went into  
it? Or how does a CEO check the accountant's 
work when they themselves are not an expert  
in financial accounting? And these are all, you 
know, problems that have existed for hundreds or  
thousands of years and we have solutions to 
them. A CTO can still write acceptance tests  
uh for an expert uh that works for them even if 
they don't understand the implementation under  
the hood. They can see that these acceptance tests 
pass and that the work is high quality. A product  
manager can use the product that their engineering 
team built and make sure that it works the way  
they expected uh even if they're not writing 
the code. And a CEO can spot check key facts  
that they do understand and slices of the data 
so that they can build confidence in the overall  
financial model even though they themselves might 
not be an expert in how the entire thing flows.  
And so thinking about these examples u managing 
implementations that you yourself don't understand  
is actually a problem as old as civilization. And 
every manager in the world is actually already  
dealing with this. Just we as software engineers 
are not used to this. We are used to being purely  
individual contributors where we understand 
the full depth down to the stack. But that's  
something that in order to become most productive, 
we are going to need to let go of in the way that  
every manager in order to be most productive is 
going to need to let go of some details. And just  
like us as software engineers, you know, we let 
go of some of the details of like understanding  
the assembly itself that's happening under the 
hood. And the way that you do this while still  
being safe and being responsible is to find an 
abstraction layer that you can verify even without  
knowing the implementation underneath it. Now I 
have one caveat to that today which is tech debt.  
So right now there is not a good way to uh measure 
or validate tech debt without reading the code  
yourself. Most other systems in life you know 
like the accountant example uh the PM uh you know  
you have ways to verify the things you care about 
without knowing the implementation. Tech I think  
is one of those rare things where there really 
isn't a good way to validate it other than being  
an expert in the implementation itself. So that is 
the one thing that right now we do not have a good  
way to validate. However, that doesn't mean that 
we can't do this at all. It just means we need to  
be very smart and targeted where aware of where 
we can uh take advantage of coding. My answer to  
this is to focus on leaf nodes in our codebase. 
And what I mean by that is parts of the code and  
parts of our system that uh nothing depends on 
them. they are kind of the end feature. They're  
the end beller whistle. Um rather than things that 
are the branch or trunks beneath them like here  
in white. Uh here the orange dots are all these 
leaf nodes where honestly if you have a system  
like this it's kind of okay if there is tectet in 
these leaf nodes because nothing else depends on  
them. They're unlikely to change. they're unlikely 
to have further things built on them versus the  
things that are in white here, the trunks and the 
underlying branches of your system. That is the  
core architecture that we as engineers still need 
to deeply understand because that's what's going  
to change. That's what other things are going 
to be built on and it's very important that  
we protect those and make sure that they stay 
extensible uh and understandable and flexible.  
Now the one thing I will say here is that the 
models are getting better all the time and so  
we might get to a world where you know this gets 
further and further down where we trust the models  
more and more to write code um that is extensible 
and doesn't have tech debt. Um using uh you know  
the clawed 4 models uh over the last week or two 
within anthropic has been a really exciting thing  
and I've I've given them much more trust uh than I 
did with uh 3.7. Um, so I think that this is going  
to change and sort of more and more of the stack 
we will be able to work with in this way. So let's  
talk about how to succeed at vibe coding. And my 
uh main advice here is ask not what Claude can do  
for you but what you can do for Claude. I think 
when you're vibe coding you are basically acting  
as a product manager for Claude. So you need to 
think like a product manager. What guidance or  
context would a new employee on your team need to 
succeed at this task? I think a lot of times we're  
too used to doing sort of a very quick back 
and forth chat with AI of make this feature,  
fix this bug, but a human if you know if it was 
their first day on the job uh and you just said,  
"Hey, implement you know this feature," there's no 
way you'd expect them to actually succeed at that.  
You need to give them a tour of the codebase. You 
need to tell them what are the actual requirements  
and specifications and constraints that they need 
to understand. And I think that as we vibe code,  
that becomes our responsibility to feed that 
information into Claude to make sure that it has  
all of that same context and is set up to succeed. 
When I'm working on features with Claude, I often  
spend 15 or 20 minutes collecting guidance into a 
single prompt and then let Claude cook after that.  
And that 15 or 20 minutes isn't just me, you 
know, writing the prompt by hand. This is often  
a separate conversation where I'm talking back and 
forth with Claude. It's exploring the codebase.  
It's looking for files. We're building a plan 
together that captures the essence of what I want,  
what files are going to need to be changed, what 
patterns in the codebase should it follow. And  
once I have that artifact, that all of that 
information, then I give it to Claude, either  
in a new context or say, "Hey, let's go execute 
this plan." And I've typically seen once I put  
that effort into collecting all that information, 
Claude has a very, very high success rate uh of  
being able to complete something in a very good 
way. And the other thing I'll say here is that  
you need to be able to ask the right questions. 
And uh despite the title uh of my of my talk,  
I don't think that vibe coding and prod is for 
everybody. I don't think that people that are  
fully non-technical should go and try to build 
a business fully from scratch. I think that is  
dangerous uh because they're not able to ask 
the right questions. They're not able to be an  
effective product manager for Claude when they 
do that and so they're not going to succeed.  
We recently merged a 22,000line change to our 
production reinforcement learning codebase  
that was written heavily by Claude. So how on 
earth did we do this responsibly? Uh and yes,  
this is the actual screenshot of like the diff uh 
from GitHub for the PR. Um the first thing is we,  
you know, asked what we could do for Claude. This 
wasn't just a single prompt that we then merged.  
There was still days of human work that went 
into this of coming up with the requirements,  
guiding Claude and figuring out what the system 
should be. And we really really embraced our roles  
as the product manager for Claude uh in this 
feature. The change was largely concentrated  
in leaf nodes in our codebase where we knew it 
was okay for there to be some tech debt because  
we didn't expect these parts of the codebase to 
need to change in the near future. And the parts  
of it that we did think were important that would 
need to be extensible, we did heavy human review  
of those parts. And lastly, we carefully designed 
stress tests for stability. Uh, and we designed  
the whole system so that it would have uh very 
easily human verifiable inputs and outputs. And  
what that let us do these last two pieces is it 
let us create these sort of verifiable checkpoints  
so that we could make sure that this was correct 
even without understanding or reading the full  
underlying implementation. Our biggest concern 
was stability and we were able to measure that  
even without reading the code by creating these 
stress tests and running them for long durations.  
Uh and we were able to verify correctness based 
on the input and outputs of the system that we  
designed it to have. So basically we designed 
this system to be understandable and verifiable  
even without without us reading all the code. And 
so ultimately by combining those things we were  
able to become just as confident in this change 
as any other change that we made to our codebase  
but deliver it in sort of a tiny fraction of the 
time and effort um that it would have taken to  
write this entire thing from hand uh by hand and 
review sort of every line of it. Um, and I think  
one of the really exciting things about this is 
is not just that this saved us, you know, a week,  
a week's worth of human time, but knowing that we 
could do this, it made us think differently about,  
you know, our engineering, about what we 
could do. And now suddenly when something  
costs one day of time instead of two weeks, 
you realize that you can go and make, you know,  
much bigger features and much bigger changes. 
uh sort of like the marginal cost of software  
is lower and it lets you consume and build more 
software. So I think that was the really exciting  
thing about this is not just saving the time but 
now kind of feeling like oh things that are going  
to take two weeks let's just do them. It only 
it's only going to take a day. Um and that's  
that's kind of the exciting thing here. So to 
leave you with the closing thoughts about how  
to vibe code in prod responsibly. Uh be Claude's 
PM. Ask not what Claude can do for you, but what  
you can do for Claude. Focus your vibe coding 
on the leaf nodes, not the core architecture and  
underlying systems so that if there is tech debt, 
it's contained and it's not in important areas.  
Think about verifiability and how you can know 
whether this change is correct without needing to  
go read the code yourself. And finally, remember 
the exponential. It's okay today if you don't vibe  
code, but in a year or two, it's going to be a 
huge huge disadvantage if you yourself are, you  
know, demanding that you read every single line 
of code uh or write every single line of code.  
You're going to not be able to take advantage of 
the newest wave of models that are able to produce  
very very large chunks of work for you. Uh and you 
are going to become the bottleneck if we don't get  
good at this. So overall that is uh vibe coding 
and prod responsibly. uh and I think this is going  
to become one of the biggest challenges for the 
software engineer for the software engineering  
industry over the next few years. Thank you. And 
I have uh plenty of time for questions. Yeah,
in the past we spent a lot of time dealing with 
syntax problems or libraries or connections  
amongst components of the code and that was how 
we learn by coding like that. But how how do we  
learn now? How do we become better by coders? How 
do we know more to become better product managers  
of the agent KI? Yeah, so the uh I think this is 
a really interesting question and I think there  
are reasons to be very worried about this and also 
reasons to be very optimistic about this. I think  
the the reason to be worried like you mentioned 
is that you know we are not going to be there in  
the struggle in the grind. Um I think that that 
is actually okay. I've met uh you know some of my  
professors in college would say like ah man like 
coders today aren't as good because they never had  
to write their assembly by hand. They don't really 
feel the pain of you know how to make something  
run really fast. Um I think the positive side of 
this is that I have found that I'm able to learn  
about things so much more quickly by using these 
AI tools. A lot of times when I am coding with  
Claude um I'll be reviewing the code and I'll say 
hey Claude I've never seen this library before.  
Tell me about it. like what is it? Why did you 
choose it over another? And having sort of that  
always there pair programmer. Um like again I 
think what what's going to change is that people  
that are lazy are not going to learn. They're 
just going to glide by. But if you take the time  
and you want to learn, there's all these amazing 
resources and like Claude will help you understand  
what it vibe coded for you. Um, the other thing 
I will say is that for learning some of these  
higher level things about what makes a project 
go well, what is a feature that gets you product  
market fit versus flops, we're going to be able 
to take so many more shots on goal. I feel like  
uh especially sort of like system engineers or 
architects over it takes, you know, oftentimes  
like two years to like make a big change in a 
codebase and really kind of come to terms with  
was that a good architecture decision or not. And 
if we can collapse that time down to 6 months,  
I think engineers that are investing in their 
own time and trying to learn, they're going to be  
able to, you know, learn from four times as many 
lessons in the same amount of calendar time as  
long as they're putting in the effort to trying. 
Yeah. Going back to your pre-planning process,  
uh, what's the balance between giving it too much 
information and too little? Are you giving it a  
full product requirement document? Is there kind 
of a standardized template that you put together  
before you actually move into VIP coding? Yeah. 
Um, I think it depends a lot on what you care  
about. Um, I would say that uh if it ranges 
for there's for things where I don't really  
care how it does it, I won't talk at all about 
the implementation details. I'll just say these  
are my requirements like this is what I want 
at the end. There's other times where I know  
the codebase well and I will go into much more 
depth of like, hey, these are the classes you  
should use to implement this logic. Look at this 
example of a similar feature. Um, I'd say it all  
comes down to sort of what you care about at the 
end of the day. Um, I would say though that like  
our models do best when you don't over constrain 
them. So, um, you know, if you I wouldn't put too  
much effort into creating sort of a very rigorous 
uh, you know, format or anything. I would just,  
you know, think about it as like a junior engineer 
what you would give them in order to succeed.
So, oh, sorry if I went too loud. Uh, how did 
you balance effectiveness and cyber security?  
Like there were reports a couple months back 
of like the top 10 vibecoded apps being super  
vulnerable and a lot of important information 
was released. Well, not released but proven to  
be released and the person who did it wasn't 
even like like a pro hacker and stuff and so  
like there's that. How did you balance being able 
to keep things secure even at a leaf node level  
uh and then also being effective because 
something can be effective but not secure? Yeah,  
that's a great question and I think that all 
comes down to this first point here of like  
being Claude's PM and understanding enough about 
the context to basically know what is dangerous,  
know what's safe, and know where you should be 
careful. And I think yeah, the the things that  
uh get a lot of press about vibe coding are 
people that have no business coding at all  
uh doing these. And that's fine. That's 
great for games. That's great for like  
uh creativity and like having people be able 
to create. But I think for production systems,  
you need to know enough about like what questions 
to ask to guide Claude in the right direction. And  
for our internal case of this this example, um 
it was something that's fully offline. And so  
we knew there weren't any like there were uh we 
were very very confident that there was like no  
security problems that could happen into this. 
Uh in our case it's like run in something that's  
that's fully offline. Uh so this is more about 
people you're mentioning as like have no business  
and maybe I shouldn't have said it like that 
but no business vibe coding in production for  
an important system. I will say I will say that. 
Yeah. But but if if we look at the numbers right  
we Less than 0.5% of the world's population are 
software developers and software is an amazing way  
to scale ideas. So how do you think the products 
need to change to make it easier for people to  
v code and build software while also avoiding 
some of the things that we run into with people  
leaking API keys and things like that? That's a 
really great question and I would be super excited  
to see more products and frameworks emerge that 
are kind of like provably correct. Uh, and maybe  
what I mean by that is I'm sure people could build 
some backend systems that the important off parts,  
the payment parts are built for you and all you 
have to do is sort of fill in the UI layer. Um,  
and you know, you can vibe code that and it 
basically gives you some nice fill-in-the-blank  
sandboxes where to put your code. Um, I feel like 
there's tons of things like that that could exist.  
And maybe like the simplest example is like claude 
artifacts where uh Claude can help you write,  
you know, code that gets hosted right there um 
in Claude AI to display. And of course that is  
safe because it is very limited. There is no off 
there is no payments. It's it's front end only.  
But uh maybe that's a good like product idea 
that someone should do here is is build some  
way to make like a provably correct hosting system 
that can have a backend that you know is safe no  
matter what shenanigans happens on the front end. 
But yeah, I hope people build good tools that are  
complements to vibe coding. Hi. Um so for test 
driven development, do you have any tips because  
like I often see that cloud just splits out the 
entire implementation and then writes test cases.  
um sometimes they don't they fail and then I just 
want you know I'm trying to prompt it to write the  
test cases first but I also don't want to like you 
know verify them by myself because I haven't seen  
implementation yet so do you have an iteratable 
approach that you know have you ever tried it  
for yeah test driven development yeah yeah I I 
definitely uh test driven development is very  
very useful in vibe coding um as long as you can 
understand what the test cases are even without  
that it helps claude sort of be a little bit more 
self consistent even if you yourself don't look  
at the tests. Um, but a lot of times, uh, I'd say 
it's easy for Claude to go down a rabbit hole of  
writing tests that are like too implementation 
specific. Um, when I'm trying to do this,  
a lot of times I will encourage I will give Claude 
examples of like, hey, just write three endto-end  
tests and, you know, do the happy path, an 
error case, and this other error case. Um,  
and I'm kind of like very prescriptive about that. 
I want the test to be like general and end to end.  
And I think that helps make sure it's something 
that I can understand um, and it's something that,  
um, uh, that Claude can do without getting too in 
the weeds. I'll also say a lot of times uh when  
I'm vibe coding the only part of the code or at 
least the first part of the code that I'll read  
is the tests to make sure that you know if I 
agree with the tests and the tests pass then  
I feel pretty good about the code. Um that works 
best if you can encourage Claude to write sort of  
very minimalist endto-end tests. Thank you for the 
very fascinating talk. Um, I also appreciate that  
you've done what a lot of people haven't done and 
tried to interpret one of the more peculiar lines  
in Karpathy's original post, embrace exponentials. 
So, I wonder if I could pin you down a little more  
and say, how would I know if I've embraced the 
exponentials? Like, what precisely means following  
that advice? And and to maybe put it down a 
little more in what I think it intends to mean,  
it sort of maybe alludes to this, the models 
will get better. Um, do you think there's  
some legitimacy in saying just the fact that the 
models will get better doesn't mean they'll get  
better at every conceivable dimension we might be 
imagining we hope they'll they'll be in. Yeah. Uh,  
so yeah. So how do I embrace exponentials, 
sir? Yeah, absolutely. So the uh I think you  
got close with sort of the the quote of uh keep 
assuming the models are going to get better,  
but it's a step beyond that. the the idea of 
the exponential is not just that they're going  
to keep getting better, but they're going to get 
better faster than we can possibly imagine. Um,  
and that's kind of like when you you can kind of 
see the shape of the dots here. It's it's not just  
that it's getting steadily better, it's that it's 
getting better and then it's it goes wild. Um,  
I think the other funny quote I heard from this 
this was a I think in uh Daario and Mike Kger's  
talk is uh machines of loving grace is not science 
fiction. It's a product roadmap. uh even though  
it sounds like something that's very far out like 
when you are on an exponential uh things get wild  
very very fast and faster than you expect. Um, and 
I think, you know, if you if you talk to someone  
that was doing computers in the 90s, it's like, 
okay, great. We have a couple kilobytes of RAM.  
We have a couple more kilobytes of RAM. Uh, but 
if you fast forward to where we are now, it's like  
we have terabytes. And it's like, it's not just 
that it got twice as good, it's that things got  
millions of times better. And that's what happens 
with exponentials over a course of 20 years. So,  
we shouldn't think about 20 years from now is like 
what happens if these models are twice as good.  
We should think about what happens if these models 
are a million times smarter and faster than they  
are today, which is wild. Like I we can't even 
think about what that means. In the same way that  
someone working on computers in the 90s, I don't 
think they could think about what would happen to  
society if a computer was a million times faster 
than what they were working with. But that's what  
happened. And so that's what we mean by the 
exponential is it's going to go bonkers. All  
right. Yes. I got a couple well I got one question 
but it it's kind it's kind of two parts. The first  
part when it comes to via coding I have like two 
different workflows. I have one where I'm in my  
terminal and then I have one when I'm in VS code 
or cursor. Um which which workflow do you use and  
if you're using cloud code in the terminal how 
often do you compact? Because what I find is  
um my functions will get a new name as the longer 
I vibe code or you know just things kind of go  
off the rails the longer I go and if I compact 
it still happens if I create like a document to  
kind of guide it I still have to you know get it 
back on track. Yeah. Yeah. Great question. Um I do  
both. I often uh code with uh clawed code open in 
my terminal in VS Code. Um, and I'd say that like  
clawed code is doing most of the editing and I'm 
kind of reviewing the code um as I go in uh in VS  
Code, which you know is not true vibe coding in 
the sense here. Uh, or maybe I'm reviewing just  
the tests uh from it. Um, I like to compact 
or just start a new session kind of whenever  
I get clawed to a good stopping point where it 
kind of feels like, okay, as a human programmer,  
like when would I kind of stop and take a break 
and maybe like go get lunch and then come back.  
If I feel like I'm at that kind of stage, that's 
like a good time to compact. So maybe I'll start  
off with having Claude find all the relevant files 
and and make a plan and then I'll say okay like  
you know write all this into a document and then 
I'll compact and that gets rid of 100k tokens that  
it took to create that plan and find all these 
files and boils it down to a few thousand tokens.
Hey uh so one question is following up uh his 
previous question which is uh have you used  
other tools along with cloud code to like increase 
your speed a little bit more like running multiple  
cloud codes together using git work trees and then 
like sort of merging few things or stack PRs or  
something like that. Is that something that you 
like personally follow or would advise to? Second  
question is um how do you like how do you very 
structurally and like in a very nice engineering  
like um like way approach a part of the codebase 
that you're not very familiar with but you want to  
like ship a PR in it really fast and you want to 
do it in a really nice way and not wipe code it.  
So yeah like what what are the what are your ways 
of like using cloud code to help do both these  
things? Yep. Uh, yeah. So, I definitely use clawed 
code as well as cursor. Um, and I'd say typically  
I'll like start things with clawed code and then 
I'll use cursor to fix things up. Or if I was  
like if I have very specific changes, if I know 
exactly the change that I want to do to this file,  
I'll just do it myself uh with cursor and sort of 
target the exact lines that I know need to change.  
Um the second part of your question was um oh 
yeah like uh how to get spun up on a new part  
of the codebase. Um before I start trying to write 
the feature I use clawed code to help me explore  
the codebase. So I might say like tell me where 
in this codebase off happens or you know where in  
this codebase something happens. Tell me similar 
features to this and like have it tell me the file  
names. Have it tell me the classes that I should 
look at. Um, and then kind of use that to try to  
build up a a mental picture to make sure that I 
can do this and not vibe code. Make sure I can  
still get like a a good sense of what's happening. 
And then I go work on the feature with Claude. Uh,  
thank you so much. I'll be still around 
and can Miller and answer other questions.

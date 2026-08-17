---
title: "Threat Intelligence: How Anthropic stops AI cybercrime"
source: "https://www.youtube.com/watch?v=EsCNkDrIGCw"
published_at: 2025-08-27
captured_at: 2026-08-16
author: Anthropic
source_type: youtube
authority_score: P2
mind: engineering
status: captured
evidence_url: "https://www.youtube.com/watch?v=EsCNkDrIGCw"
catalog_id: cb1c4b6f0df2
subtitle_file: EsCNkDrIGCw.en.vtt
---

Kind: captions
Language: en
- All right, welcome to
another video from Anthropic.
My name's Stuart, from
the Communications team.
A lot of the time when
you hear AI companies
talking about threats from AI,
they mean threats that are
gonna happen in the future,
a future where AIs are vastly more capable
than they are currently,
and where we might lose
control of their behavior.
But there are a lot of threats
that are happening right now.
One of them is that cyber
criminals are using AI
to make their crimes much more effective.
They're using AI to do
scams, fraud, and extortion
in particularly sophisticated ways.
We have a whole team of
researchers at Anthropic
whose job it is to spot
these kind of problems,
to stop them from happening,
and then to prevent them
happening in future.
That's our Threat Intelligence team.
And they have a new report
out which details some of the,
I must say, pretty bizarre
cases of cybercrime
that we're seeing with Claude, our AI.
I'm very glad to be joined by two members
of the Threat Intelligence team right now.
Jacob and Alex, perhaps
introduce yourselves.
- Sure. My name is Jacob Klein.
I lead the Threat Intelligence team,
and broadly, the Threat Intelligence team
is responsible for finding
and deeply understanding
sophisticated cases of misuse.
And these cases are very rare -
this is not the typical usage
that we see on our platform.
And when we find them,
we work with the rest of the organization
to build defenses so
that that type of abuse
is much harder to recreate in the future.
It's an ongoing process,
we're always learning more
but frankly, it's actually a lot of fun
in a weird kind of way
because we get to see the cutting edge
of what bad actors are doing
and what we can broadly
do to make AI more safe.
- And my name's Alex.
I'm an investigator on the
Threat Intelligence team,
and my work involves threat hunting,
building new detections,
and doing deep dive investigations
into the types of abuse that we find.
- All right, let's talk
about "vibe hacking".
Now, everyone's heard of vibe coding.
In fact, to be honest,
I'm sick of hearing about vibe coding.
It's the current thing,
everyone's talking about
vibe coding. That's when
you just use normal language
and you give that language to an AI
and you say what you want,
what software you want,
what code you want, and
then the AI makes the code
and then you kind of just do it by vibes,
you just kind of go along with it.
What's vibe hacking?
Where does that come in?
This is the kind of like
the dark side of vibe coding, right?
- Yeah, some people refer
to it as the evil twin-
- Right, right, right.
- Of vibe coding.
Yeah, much like vibe coding,
everything is natural language prompting.
The person doing it doesn't
actually have to know
the technical skills to write code,
execute code and all of that.
In this case, rather, the vibe coding
is being used for malicious intent.
So it could be for something
like writing malware
or developing new capabilities
for their hacking toolkit.
It could be social engineering.
Any number of, typically-
- Social engineering is when you,
like, you're basically
tricking someone into thinking
that you're someone else.
- Yeah.
Talk us through what this
looks like in practice then.
So, what does a vibe
packing process looks like?
Can you give us some real
examples of stuff that you found?
- Yeah. Yeah.
So, there was one case that
we talked about in our report
where an actor pretty much
conducted their entire operation
using vibe hacking.
Within about a month's timeframe,
they hit about 17 organizations.
In this operation, they
were doing something
called data extortion.
So, this is like a cousin to ransomware
instead of hacking into
systems and locking up files
so people can use those files
and then demanding a ransom.
In this case, the actor
is stealing sensitive data
and threatening to expose
it if a ransom is not paid.
So in this case, they used vibe hacking
to both infiltrate the organizations,
move laterally through their networks,
drop back doors so they
could have persistent access
and steal certain types of information
that they could use for their extortion.
- And this is the kind of thing that would
ordinarily take extremely
high levels of skill.
- Yeah, I would say from
what we saw with this actor,
you would typically see
that amount of activity
come from like a group of cyber criminals
operating over months,
a month long timeframe.
In this case, we saw a single person
hacking into this many
organizations in a matter of weeks.
- So who are the victims of
these vibe hacking attempts?
Are they targeting like
random people on the internet?
Like a spam email would
go out to everyone,
or, you know, these are much
more targeted than that, right?
So, the targets are specific
but they're also indiscriminate.
So, they're not trying to target
like a certain sector specifically.
They're targeting organizations that have
a certain type of VPN
that they potentially have credentials for
or believe they could brute force,
which is just like send a bunch
of potentially valid
credentials until you get in.
So, organizations with that VPN,
but that means they're hitting
organizations in healthcare,
we saw emergency services,
we saw governments,
defense contractors.
We even saw a church
being hit by this actor.
- Talk us through the church.
- Yeah, so this is like a great example
of how without some sort
of automated defense,
which a church probably wouldn't have,
they were able to access
the victim's network
through some sort of attack on their VPN.
Once they got in,
they would essentially
look for different ways
through the network to identify machines
that might have sensitive data,
like an administrator
or owners of the church,
their financial staff,
and then start collecting
financial information.
Anything that could be
potentially sensitive.
And when I say they were doing this,
it was actually Claude
as if Claude was on keyboard
doing the operations.
It wasn't really the actor.
The actor would gently nudge
Claude in certain ways.
The actor would provide at
the beginning of the operation
kind of a guide to Claude
of like how they would suggest for Claude
to conduct the operation.
But then also put in a
lot of caveats on like,
hey, like use whatever
knowledge you have available,
try everything until you have success
in completing the mission.
So with this church,
Claude was able to identify
donor information and
members of the church.
And once Claude would finish
collecting information
from victim networks,
the actor then asked
Claude to analyze that data
and develop an extortion
scheme like Jacob mentioned.
And in this case, with the
church, Claude identified that,
hey, we have donor information.
We could expose who the donors are
and how much they're paying.
And that might be enough to
convince this church that
exposure of that information
would be harmful enough
to their parishioners that
they should probably pay the ransom.
- Another thing to emphasize
is this isn't just Claude,
Claude doesn't have some specific-
- That's right.
- Weakness that is being used
for all these things.
This is all LLMs presumably.
Well, you'll have seen this happen
for many of our
competitors models as well.
- And Claude's not fine-tuned,
like you said, for this
but there are actually open
source models out there now
that are fine-tuned for this.
Cyber criminals are
developing weaponized LLMs
to conduct attacks.
So, we gotta collectively
think about defenses here
and we, as the threat intel team
and Safeguards and Anthropic as a whole,
can begin to manage the
risks posed by our systems.
But there's only so much we can do
'cause like you said, it's
not only a problem for us.
- Some of the stuff in
the report is amazing
about the really hyper
targeted nature of this
that they are using
Claude in this case to,
and Claude Code specifically, right?
- To make even payment plans
to say to people like,
here's how the money,
here's how you're gonna give me the money.
You can give me over a series of time,
like you would get on buying stuff online.
- Yeah, it's coming up
with, once you get the data
that's been exfilled from this attack,
it's coming up with what they think
the estimated value of that
data is on the dark web.
Then it says, here's how much we think
we should send the ransom note for.
And then it actually helps
write the ransom note
to be as persuasive as possible.
So really every step end to end,
AI is able to help with
an attack like this.
- And like analyzing
people's financial details
to work out how much
they can realistically
be extorted for as well.
- Which is just-
- And like you said, it
is using Claude Code.
And so, it would actually
iterate through victims.
So, it would complete an
operation on one victim
with some gentle steering
from the human actor.
But once it was done
executing the mission,
it would roll on to the next target.
- Importantly here, we should
say that this is not something
that Claude Code would just do.
Like if you or I just prompted
Claude Code right now to do.
There's been some jailbreaking
or something going on here, right?
- Yeah, so in this case, the
actor found the right prompt
and put it in the right place
in order to essentially
jailbreak our defenses.
Jailbreak the models fine tuning
and jailbreak the
downstream defenses of that.
- And just to be clear for the people
who don't know what jailbreaking is,
this is when you say
things in a particular way,
so like some of the jailbreaks
are like weird to look at.
They're like uppercase, then
lowercase for every word
and things like that.
But some of them involve
sending tons and tons
and tons of prompts to just
sort of like bludgeon the AI
into just like continuing, continuing on,
putting words in its mouth,
all sorts of things like that.
So that's what they're
doing to Claude Code.
- Yeah, actually, in this case,
they were doing role play.
So they were pretending to be a,
your average security person
doing network penetration testing
to make sure that defenses
are adequate in the systems
convincing Claude that
they had authorization
to do what they're doing.
- Because otherwise, Claude would,
the safety mechanism would kick in.
Like if you explicitly said,
I want to make a malware operation
to scam people out of money,
it would never do that.
But you can pretend to
be, I'm checking this for,
I work for a security
company, I'm checking this.
- And this is why it's so important
to think of multiple layers of defense
when you're an AI company like Anthropic.
So layer one is we train the model
so it's less likely to
respond to malicious requests,
which is why you have to
trick it or jailbreak it.
- So that's reinforcement learning.
That's reinforcement learning.
- And when you trick it,
you're kind of tricking it to go outside
of what we've deliberately
taught it to do.
- Exactly right.
So that's first layer,
but we know that's not perfect.
So we have another layer,
which is we have classifiers running,
which are trying to detect
this activity and stop it.
And that's not the last layer.
We also have offline rules
running that are saying,
do we think leveraging maybe the string
that is put into a prompt,
do we think that something
as malicious is happening?
And then we have another layer,
which is the account itself
when it's signing up,
does it look like it has
suspicious signatures
associated with it?
which is we info share with governments,
with other tech partners to say,
oh, we know that this actor,
this organization is malicious.
So, it's not just a, we
assume that the RL layer,
the classifier layer is gonna be perfect.
We intentionally think about
this as a holistic defense.
- And you guys are getting data
from all these actual cyber
operations that are happening
and then training these classifiers
so that they're even more effective
and that they also don't
stop you from doing
good cyber-related things
'cause that was my next question.
Why is it that we can't
just say to Claude Code,
just never do anything that comes,
that's to do with anything
to do with cyber operations,
to do anything with cybersecurity at all.
Just never talk about that stuff.
And then, well, it wouldn't be
able to do this stuff, right?
- Yeah, that's a really
tricky decision to make.
So, when you're working
in like a dual use domain
is what it's called, where
the prompting you would see
for defensive cyber might look a lot
like what you would
see for offensive cyber
because you do a little cyber offense
to figure out how to defend your systems.
You have to be really careful
in how you implement safeguards
or thinking about things like a total ban
on that type of activity in that domain.
It's really important to consider that
like here in the United States,
we have a huge deficit in the workforce
for cybersecurity workers.
I think it's like around like
half a million right now.
So if we can imagine a future
where we have AI agents
that are smart at cyber,
that we could kind of help
alleviate that deficit that exists.
- It reminds me of when biologists say,
I was asking this AI model about viruses
and it shut me down.
And like, this is the dual use thing.
Like clearly you can talk
about virology to an AI model
and that's for good reasons,
but also for nefarious ones too,
- And especially with cyber,
you can imagine every startup in the world
needs to think about cyber defense.
And so, really every startup in the world
should be using Claude
or some AI model to help them work through
what their cyber defense strategy is.
This isn't a narrow
subset of the population
that has to work through this.
This is most developers have
to work through these issues
so we really wanna enable that
positive use case of AI too.
- And like even individuals,
I've seen a lot of cases where like,
it looks like it's like a web developer
and they found this
file on their web server
and they're like, what is this?
My server's acting weird.
And Claude will respond with,
hey, that's malware
from like this variant,
it's doing these things.
And the person's like, oh no,
what do I do about it, Claude?
And Claude will like
walk them through the steps to clean up.
So I think the important
thing to keep in mind here
with this case in particular is the scale
and the speed of the operation
as it's enabled by Claude.
In this case, Claude Code is
able to break into a system,
identify all the weak
points, test them all out
to figure out where to go,
find the data it needed,
and exfiltrate that
data before even a human
I think would have time to review an alert
and understand what's happening.
It's too late.
You need intelligent automated defense
to counteract something like that.
- Right 'cause almost always
when there's some sort of security alert,
there's a human on call
and there's a human waiting to see,
and then they'll check out whatever it is.
But in this case, there
could be all sorts of things
happening all at once that
humans will never keep up with.
- I think this is a paradigm
that probably we need to rethink a bit,
which is this, you have an
alert that runs offline,
a human response 24/7,
human looks at the alert
and then does something
because the speed at which AI is moving,
you need to automate that process.
You need essentially AI
to protect against AI.
- So as well as the classifiers
and as well as you publishing this report,
which is telling us all about
the specific things that we've found,
presumably we're talking
to other AI companies
about this as well, right?
- We are, we're talking to the
government when appropriate,
we're talking to other AI companies.
And we're not just
saying like we are here,
here's generally how the case worked.
We're sharing very specific indicators.
So IP addresses, email addresses,
so that if there's actors
on those platforms,
they can find them and kick
them off there as well.
So that's why it's
really a community effort
to try to find and stop these folks.
- Right, so we have them something similar
in the world of alignment research
in the Frontier Model Forum,
where they share things like jailbreaks
and potential misalignment
issues with models.
And in the world of
security, cybersecurity,
there are similar mechanisms.
We have information sharing agreements
with a number of companies,
folks in the industry,
governments where we're
bilaterally sharing information
when we find people just like this.
- Okay, we've gotta
talk about North Korea.
Now, this is one of the most,
I think this is like an eye
popping case from your report
where there's this like complex,
long-running employment
scam run by North Korea
on US companies.
And Claude is involved.
So first of all, before
we even get to Claude,
talk us through what the scam is here.
- Yeah, so ignore LLMs for a moment.
- Yeah, and AI, this is before AI.
We don't need AI necessarily.
- Exactly.
The scams started before
LLMs became a thing,
which is really took off during COVID
where North Korea wants money
to fund their weapons program,
but they're sanctioned.
So how do you receive
that source of income?
One method is getting a job
as a remote IT worker with a company.
And surprisingly, hundreds of companies
have hired North Koreans without knowing,
and this has funded tens
of millions of dollars
to the North Korean weapons program.
And this is typically somebody
who's highly trained in North
Korea, goes to the university.
So they have language context,
they have cultural context,
and they have the technical skills
to go through an
interview and do this job.
And that is what is starting to shift
with Claude and AI systems.
- Right, right.
So just to reiterate, like in the past,
you would've needed a lot of training.
You'd have to go to scammer
university to learn this stuff.
But actually now-
- You don't need to know English.
You don't need to know
the cultural context
of the United States,
and you don't need any technical skills
because Claude can help you
through each of those barriers.
Claude can say, well,
it's a great translator.
Claude can help you answer
very strange turn of phrases
within the English language.
- Right, yeah.
There were a couple of,
what were the example
of phrases that you guys found?
- Yeah, like an example is like
someone asking Claude, what is a muffin?
And so Claude says it's this round dessert
that's often sweet and
eaten for breakfast.
And so, then the person follows up with,
well, what's the difference
in a muffin and a cupcake?
And so, like very simple things that-
- What is the difference between a muffin?
- I'm gonna have to ask
Claude that later on.
- Really answer that.
- Yeah, yeah, yeah.
Anyway, carry on.
- Yeah, so examples like that,
or like quoting a phrase
from a coworker of like,
we just had our first picnic of the year
trying to understand what that means.
What is a picnic? Why we have them yearly?
And then maybe another one
that I found actually a bit entertaining
was the actor actually like
provided some ASCII art
of like an emoji doing something
and was like, what are these characters?
What does this mean?
- What is the thing?
- Yeah, so that's the little,
not necessarily like the picture emojis,
but the ones that are made
up of punctuation marks.
Yeah.
- Yeah, yeah, yeah. Yeah, amazing.
- Yeah, so it's fascinating
what shifted here is,
on one hand you can
think this is incredible,
Claude's helping people
overcome language barriers.
Claude is helping people
understand cultural context.
Claude is helping somebody code
who doesn't know anything about
even what Microsoft Outlook is.
That seems like a brilliant thing,
but in this very specific context,
it's helping them land a job
and maintain those jobs at
a high level of quality.
- The phrase you use in the report is
it's helping them maintain the illusion
of competence every day.
- Yes.
- And I thought, don't we all do that?
Don't we all have to
maintain that illusion?
But in this case, their
employers and their colleagues
are talking to them every day.
- And they're not realizing
that this is a completely fake person
who is in fact, a scammer in North Korea,
- A persona that's been created by Claude
or by somebody in North Korea
that doesn't really exist
with an educational background
that doesn't really exist,
with skills that are being done-
- Like a resume-
- With a bunch of history on it.
Oftentimes you'll see, like,
they'll take the project plan
from their project manager,
like the tasks that they need to complete,
and they just throw the
whole thing into Claude
and say, what do I do?
How do I get started?
Help me code this.
- Again, super dissimilar
to what a lot of people do.
- I mean, I do that too now.
- You're not wrong though.
- Exactly. Exactly.
Are they actually doing economically
useful work for these companies?
- I think they are, yes.
- Right. Right.
- They're being product,
otherwise they get fired.
They're being productive employees
and that's a part of this scam
is sometimes these employees
are considered high-performing
because it might be one individual
or many individuals doing the job,
but this is what's so, I think critical
to take away with this case
is before you would need a
few highly trained individuals
to go out into the market, get a job,
and then maintain a job,
now North Korea can
just use really anybody
and just say, "Hey, use Claude."
And then you can get the
job and maintain the job,
which allows you to get more positions,
apply to more positions,
and from North Korea's
perspective, get more revenue in.
- Maybe this is a silly question to ask,
but I think it might occur to people,
how much money do you think
North Korea are making from this?
They're making tech
company salaries, right?
And they're presumably using that money
to fund their weapons program
and whatever else they need to run,
given that they live under sanctions.
How much do you reckon overall
they earn from this kinda scamming?
- We're seeing these actors
get jobs as AI developers.
Those people make quite a lot of money.
- Right, right. Yeah, yeah.
- And just like general
like coding, coding jobs,
which typically are high salaried.
So, they're being pretty
effective with this
and they're not taking
jobs at like call centers
or something like that,
that might not pay as much.
And maybe that's
something they used to do.
Now they can take technical positions.
- They're Fortune 500
companies that you're finding
that are being-
- Yeah, they're targeting
all the way up to Fortune 500.
Smaller startups, medium-sized companies,
large publicly traded companies.
- I assume - this is
happening at the level
of the North Korean nation state -
I assume this is also happening with
on the level of groups, right?
Are there other smaller
groups that are doing this?
Do we have any idea about that?
Is that something that you pick up?
- Yeah, I think of it
in maybe like two ways.
The first is there's
certainly other groups
and other nation states that are running
this employment scam where
they're trying to land a job
without actually being
the person who's applying.
That is becoming more common over time.
The twist that you might
want to think about as an
individual that's listening
to this conversation is
what's been going around for a long time,
which is an employment
scam where I receive a job
that is not a real job and
I go apply to that job,
but actually it's a scammer
who's trying to harvest
information from me
or get me to download ransomware.
And that's something
that we're also seeing
happen more often and
that's leveraging AI.
- So again, it's like
the vibe hacking thing.
It's lowering the bar
at which you need to,
you know, the skill bar for doing these
complex-
The two big implications there is you can,
when you can do more
scams, more cyber attacks,
you can scale more because
there's more people
that are enabled,
or a sophisticated actor
can leverage Claude
to scale themselves.
And so really you have to
think about the number of scams
or the number of pieces of fraud
that are gonna be out in the world
and they might, I would suspect,
increase over time with the rise of AI.
- What are we doing specifically
about the North Korean thing?
There's this scam but there's also another
part in the Threat Intelligence report
where you guys kind of noticed
another North Korean
operation and stopped that.
So, maybe talk about how we're responding
and how we're spotting these North Korean.
- Yeah, so the North
Korean case is tricky.
Like 80 to 90% of their use of Claude
looks like a typical person
doing development tasks.
- Right, you're asking for
work, just coding stuff.
You're asking what a cupcake is.
These are normal things.
They're not saying develop malware
or anything like that, you know?
- About 10% of what we
saw looks suspicious.
And that's kind of like
our needle in the haystack
that we have to find
among all of the traffic.
- But you can't use Claude
in North Korea, right?
- Correct.
- So, they must be using
some like VPN system
to evade that.
Yeah, so the 10% is like
the type of activity
was focused on like interview frauds,
so we could see them
developing fake resumes.
We can see them trying to
answer interview questions.
Now, the other way,
which you just alluded to
of finding them is
using the infrastructure
that they're coming from.
This activity is widely investigated
across the security community,
both in the government
and in the private sector.
So there's a lot of information
sharing happening there,
people tracking what infrastructure
are they operating on
in order to access Western sites.
And so, we're engaged in those communities
and that's helping us continue
to find these activities like this.
- And there are success cases here,
and there's one that's in
the report that you mentioned
that I think is worth calling out,
which is there was
another North Korean group
known as Contagious Interview,
and their MO is to try to lure people
into applying to fake jobs,
to install malware on their devices.
- Right.
- Now, we know
that this group tried to use Claude
based on their infrastructure,
their IPs, their domains,
but we shut them down before they issued
a single prompt based on
that suspicious activity.
So, this is something we're always on
is finding and detecting these folks
sometimes before they even do anything
with our AI product.
- There's a lot more in the report.
There's loads of stuff
about, for instance,
a British person who's making like a,
normally we talk about
software as a service, right?
But this is ransomware
as a service, right?
So this person is like making ransomware
and then selling it on
the dark web to people.
And again, a normal person would've taken
huge levels of skill to make this happen.
But this person had just
like vibe-coded it really?
- Yeah, yeah, that's correct.
So, they developed ransomware,
kind of like worked with Claude
until eventually they got
Claude to actually write
the pieces of code that they wanted.
There was a lot of refusals that happened
and Claude said no, and they would provide
some sort of justification
for what they were doing.
- Again, like I'm working
for a security company
and testing this out,
or something like that.
- Yeah, yeah.
- Not that we're trying to tell
people how to do it, right?
Don't listen to that last comment.
- Yeah, so they were able
to get Claude to write
some pretty sophisticated ransomware.
We actually, in the investigation,
were able to discover that
this actor was selling
this ransomware on various
underground forums.
So, we were able to trace those ads
back to the activity
we saw on our platform.
So we got a bit of an understanding on
why they were developing
what they were developing.
And it was clear that it was a ransomware
as a service operation.
- And there's other kind of
entirely different types of scams.
Do you wanna talk about
the romance scam bot?
Like of course, Claude
doesn't have a kind of avatar
thing that it can, that some other AI have
these kind of animated avatars
that talk to you and so on.
But people were using it to kind of,
as the engine of something like that.
- Yeah, so there's these things
called romance scams, sadly,
which is where you pretend to develop
a romantic relationship
with another person,
usually for the purpose of extracting
financial gain from them.
And there's this Telegram bot
and this Telegram bot had
tens of thousands of users,
and it was a scamming bot,
meaning people would
reach out to it, the bot,
and say, "Hey, can you help
me with this part of my scam?"
And Claude specifically,
there's multiple AI models
that you could use, but
Claude was advertised
as the emotionally intelligent AI model.
So you could upload like
a picture of somebody
and then say, Hey, how do I
compliment this person best?
Or how do I respond to
this person's message
to make it seem like I'm
flirting with them effectively?
- Right and again, that was,
people were having success there
and presumably that's shut down now.
- Yes. This is shut down.
Everything we talk about today
was shut down.
- Right, these are things
that are gone, yeah, yeah.
And we build better defenses.
But yeah, in that case, we found,
I think this is really the takeaway for me
is that all scam infrastructure end-to-end
is starting to use AI models.
Because if you're a scammer,
you might not have perfect language skills
in the relevant language you're
trying to scam somebody in.
You might not know the cultural context
to flirt effectively.
You might not actually be
able to send enough messages
quickly enough to all of
your potential victims.
AI unblocks all of those
potential barriers.
- I watch a lot of those scam
baiting videos on YouTube.
- Oh, those are great.
- Isn't that great fun? Yeah, yeah.
Where someone like talks to
the scammer sometimes for hours
to just waste loads
and loads of their time
so they can't scam someone else.
Can you imagine an AI doing that
to sort of put things
back on the scammers,
like an AI making the scammers think that-
- You know, I love this idea.
You have the AI interacting
with the scammers
just wasting their time.
- Yeah, exactly. Yeah, yeah.
That could be an idea.
A sort of romance scam but for scammers.
The operations that you've
talked about so far in the report
and in this video are really in order
to try and get money from people, right?
They're scams and fraudulent attempts,
extortion attempts to get money.
But there's one operation that
you talk about in the report
that's not about that.
And in this case it's about a cyber attack
on the infrastructure in Vietnam.
Can you talk a little bit more about that?
I mean, this is not an attack
to try and destroy the infrastructure,
this is stealing
information from it, right?
- Yes, this is likely espionage
from what we're observing.
This is a Chinese-speaking actor
targeting Vietnamese
telecommunications companies.
And there are a number of reasons
you might target a
telecommunications company
as a bad actor.
But seeing that they
were exfiltrating data
clues us in on the potential that they are
trying to maybe identify certain things
about communications
happening within the country.
- Like where the really
important nodes are
in the communication grid or whatever.
So, we saw them target a number
of companies within Vietnam,
and in this case they were using Claude
as more of an assistant
in their operation.
So whereas in the vibe hacking case,
Claude was essentially on
keyboard conducting the operation.
In this case, they were more
kind of having a conversation with Claude
where it's like, hey, like where
should I start this attack?
They would run a scan
on the victim network
and paste that data back into Claude
and say, hey, like, what
is this scan telling me?
Can you help me prioritize
certain machines to target first?
And it was a lot of just back and forth,
but not really having Claude
actually like on keyboard.
And I would guess an entity conducting
an espionage operation wouldn't
be willing to trust an agent
to actually run the commands
within victim networks.
And I think that could
have been another clue.
- So it's not used yet.
We're seeing vibe hacking used
for these types of hyper targeted attacks
against sensitive targets,
because bad actors might not
yet fully trust the model
when there's only one or two targets
that you wanna go after.
But this is probably
gonna change over time
once people get more comfortable
with things like vibe hacking.
Once you get more comfortable
with model accuracy,
you could imagine that all
operations that are offensive,
may be using AI not just
for an advisory purpose,
but for actually
conducting operational work
or being, quote, unquote,
"hands on keyboard,"
or maybe it's AI on keyboard
because there aren't
actually hands on keyboard.
- Another of the examples you talk about
is a credit card fraud scheme
where they're collecting
people's credit card information.
Tell us a little bit how that works.
- Well, a very standard
part of fraud operations
when you're signing up for a service
is you use a either a stolen credit card
or a fake credit card.
And one of the core
parts of infrastructure
if you're a fraudster is,
well, where am I gonna go
find my fake credit card
or my stolen credit card?
We're seeing somebody using Claude
to stand up a carding service.
Meaning the actual
infrastructure you'd be using
to conduct some sort of scam,
you'd be using carding
infrastructure that is run by Claude.
Again, I think it goes into the theme
that every stage of a scam
or a cyber attack or an act of fraud,
and there's many stages.
There's the core infrastructure,
there's the reaching out to the person,
there's maybe installing
or building malware.
There's many stages of,
quote, unquote, "attack."
Each of those stages are
having AI integrated into them.
So the core infrastructure,
the actual operational act,
the conversation with the victim,
all of these we're
seeing AI used right now.
- This isn't surprising.
Many cyber criminal operations
run like businesses.
They need infrastructure,
they need tooling.
And I think we're gonna
see a lot more actors
start using AI to build infrastructure
and then sell that to
other cyber criminals.
- Because what you see
today, if you spend much time
which hopefully the
listeners are not doing,
on the dark web, is it's
an entire marketplace
where you are buying that tool.
You're buying that
piece of infrastructure.
So if I'm gonna conduct,
let's say a phishing campaign,
I might not build the,
quote, unquote, "phish kit."
I might buy the phish
kit from somebody else,
and then I'm conducting
the phishing campaign,
but the actual infrastructure's
not built by me.
Now, AI is being used to
build that core infrastructure
that could be bought and
resold on the dark web.
- So all this stuff we hear,
it's like the vibe coding stuff.
All the stuff we hear
about all these amazing
new piece of software that are being made,
again, as a dual use situation
where there's all this great new software
that people are making themselves
and it's making their life
easier in all sorts of ways.
But there's also the dark side,
which is that software can often be used
to do very bad things.
- That's right as well.
- Okay. How big a deal is this overall?
Like you're talking about AI models are,
loads of scamming is
happening now using AIs
and fraud and so on.
Is this just gonna be a whole new world
that people have to get used to?
How ready are we for this?
How ready are banks for this?
How ready are governments for this?
- Yeah, I think when you think
of the cybersecurity space,
you wanna keep things at equilibrium
in the worst case scenario.
Ideally you're doing a better
job protecting folks, but-
- This is like an arms race.
- Like the good AI uses
and the bad AI uses.
It's like all technology,
bad guys are gonna use it,
good guys are gonna use it.
And AI is a general purpose
piece of technology.
And I think what's important,
and one of the reasons
we're talking about this
and hopefully folks are
listening and watching,
is we want the good guys, the defenders
to be using this technology too,
so that in that arms race
you stay at equilibrium.
Really, ideally we're trying to work with
and partner with those organizations
so that they have a leg up,
they use it more effectively.
- Is there anything else you can say about
what the Threat Intelligence team is doing
in general or even some more specifics
about what you're up to
that might help us get
to that equilibrium?
- Yeah, well, something we're always doing
is we have people on the team
who are looking on the
open web and the dark web
to understand what are bad actors
practically doing right now?
What are they saying
about using our products?
What's the chatter?
So we understand, okay,
here's bad guys' usage.
So then we can talk to the good guys
and say, "Hey, here's what it seems like
the bad actors are doing."
We're building new methods
of detection all the time.
One of the reasons we
shared this public report
is we want the public, other companies,
the security community
to know what we're seeing
and what we're finding.
So both, you know, maybe think
of it from two perspectives.
One is at Anthropic we
take stopping misuse
very seriously of our models
and that's why this team exists.
But on the other side,
if you're in industry
as a company, as a government,
so that you yourself
can start using these
AI models for defense.
- Well, that was my next question.
What can you other...
You know, using AI is one thing,
but what are some more
practical tips for people
who maybe they or their
family members or whatever
are the victim of these scams,
fraud attempts, extortion attempts.
What are some tips that you guys have
for the average person?
- Yeah, I would say anytime
like you're suspicious
about something happening
like a text you got or an email you got
or something weird
happening on your computer,
just start like brainstorming
what's happening with Claude.
Claude will have a lot of good ideas
and it will help you kind of triage
as if you were like a
security professional,
how they might triage the same problem.
Since I work in the security space,
I have people ask me
questions like this regularly
and sometimes like if I don't have time,
I'll just throw it
into Claude.
- Just throw it in.
- Say this is what Claude said
and then they will potentially maybe
try to do that next time.
Save me a little bit of time.
- Fair enough.
- Yeah, I think the general
guidance I have is the same,
which is if it's too good to be true
or if you're really scared,
probably means something's up
and you should look into it.
You talk to Claude
and actually, I've done
the exact same thing.
Somebody asked me for help with
their account was taken over
and I just asked Claude,
hey, what should we do here?
Even though I have years of expertise
dealing with account takeovers,
Claude was exceptionally helpful.
- How optimistic are you both about this?
I mean, this could be seen as quite
a doom-laden scenario, right?
There's all these AIs being used by
some of the countries that don't have
any kind of ethical legal
framework that are doing this.
This could be seen as
something really quite scary
or how optimistic do you feel?
- Yeah, I think it's important
to keep in perspective
that like what we're sharing today
is kind of like the needles
in the haystack that we find.
I think they might indicate a future
if we don't respond
collectively well to it.
But these are the needles in the haystack
and we've built a lot of defenses
and adjusted our defenses
from these learnings
to make sure our models
don't get used in this way.
But there hackers have been known to use
quite a number of different commercial
and open source models.
So the problem's not gonna go away.
And I'm hopeful that our
threat report and this video
will help calibrate everyone
on what currently exists
and start kind of coalescing
around different types of defenses,
either policy or technical
that can kind of help get at the problem.
- It could be seen as quite
strange that we are saying,
on the one hand you should buy Claude,
on the other hand we're saying
Claude can do all these terrible things.
I mean, this comes up
when we're talking about
alignment science stuff as well, you know?
Claude, under some circumstances
in our experiments,
can blackmail you.
Now, buy Claude to use in your business.
Like, this is part of the weird
paradox of Anthropic, right?
- I always think about this a lot,
how Claude is such a general purpose tool
that any use case you can think
of, Claude can probably do.
And many of those use cases,
the same use case can be good or bad.
Getting rid of a cultural
barrier can be a beautiful thing
to create connection in the world
or can help you land a job
as a remote IT workers as a North Korean.
- So, you know, there's this paradox
and we want to enable
the good thing as well
trying to find the very
narrow bad use cases.
- Well, I'm very glad that
you guys are looking into this
and that we're taking this
so seriously at Anthropic.
And you might just wanna check
that the colleague that
you talk to every day
is not a North Korean agent.
Thanks very much for watching.
We'll see you in the next one.

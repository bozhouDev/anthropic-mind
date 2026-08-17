---
title: The Model Context Protocol (MCP)
source: "https://www.youtube.com/watch?v=CQywdSdi5iA"
published_at: 2025-06-16
captured_at: 2026-08-16
author: Anthropic
source_type: youtube
authority_score: P2
mind: engineering
status: captured
evidence_url: "https://www.youtube.com/watch?v=CQywdSdi5iA"
catalog_id: b09c729002fc
subtitle_file: CQywdSdi5iA.en.vtt
---

Kind: captions
Language: en
- Around the time, like in September,
we had like an internal hackathon,
and everyone was free to build
basically whatever we wanted to build.
But it turns out everyone
just built an MCP,
and it was-
- It was crazy.
Like everyone's ideas were,
"Oh, but what if we made
this an MCP server?"
- Hey, I'm Alex.
I lead Claude Relations here at Anthropic.
- Hi, I'm Theo, I'm a
product manager on MCP.
- Hey, I'm David, member of
technical staff at Anthropic
and one of the co-creators of MCP.
- Today we're gonna be talking
about the Model Context Protocol
and diving in deep into
what it is and what's next.
Thank you both for coming on.
Very excited to talk about MCP,
but first there's a lot of talk about MCP
and not a lot of maybe
real deep understanding
of what it is.
Can we dive into how you view MCP
and like what it really means
to be using MCP or building on it?
- MCP is just a way for, you know,
putting my workflow into
like an AI applications
in a very simple way.
I think that's how I really
wanted it to be initially,
or that's how we want it to be,
but it's just a way to give context
to an application that uses an LLM.
And that's just as simple as that.
And that can be, you know, tools,
it can be just raw context,
whatever you like it to be.
- How is that different
than you calling an API
or something like that?
It's passing this
information from one place
into the prompt basically of the model.
What makes MCP special here?
- I think the question is
what do models interact with?
And they don't interact
directly with APIs.
They interact with prompts
and tools and you know,
whatever you're giving
the model to ingest.
And so MCP standardizes how
you take that data from,
whether it's an API or
some internal data source
or whatever it is, how you take that data
and then actually give it to the model.
- So, this is a protocol then.
So it's defining that sort
of interaction pattern.
What are the main aspects of this protocol
that like you have, that has to follow?
- The main part is that it's a protocol
between the AI application
that uses an LLM,
and it exposes like
basically three main thing.
It's tools, it's a set,
a thing called resources,
which is just raw data
that you could like ingest
into a RAG pipeline or
whatever you want it to do,
and there's prompts.
And that's the three main things
that a server can expose for now, yeah.
- So tools are like actions
that the model can take out in the world.
Resources could be files, texts.
- Files, data, whatever kind of context
you wanna give the model.
- And then prompts are?
- Just like what a user wants
to put into the context window
by themself and just like
triggered by the user
and just put into the context window,
and then they can edit it as they want to.
That's really what prompts are for,
like prompt templates
at the end of the day.
- Prompt templates, I see.
So literally defining the prompt itself.
- We typically see that being implemented
as a slash command.
- Oh, okay, I see.
So if you're in the AI
application of your choice,
you would do a slash command,
and it pull in the prompt template.
- Exactly.
- Save you time
from having to write
that out, whatever it is.
Okay, that's MCP at its most basic form.
There's definitely a
lot of nuance in there.
What was the origin of all this?
Like how did this come about?
- The origin I think is like,
the most basic thing is that,
that I worked on like
internal developer stuff,
and I got very quickly frustrated
about like having to copy things
in and out of Claude desktop
and then copying things back
and forth between my IDE,
and that's just really what
I would thinking about,
like how can I solve copy
and pasting the things
I care about the most between
these two applications.
And that's really the absolute
origin of where MCP started,
at least in my mind.
And then from there, I
explained that to Justin,
who's the other co-creator,
and he really took it and ran it.
And then we together, just build it out
and build into Claude desktop.
And I think there was a pivotal
moment that you alluded to.
Do you wanna talk about the hack week?
- I feel like you should take the story.
- Okay, yeah, hack week was fun.
We weren't really sure,
is this gonna work?
And, but at the round the time,
like in September we had
like an internal hackathon,
and everyone was free
to build basically whatever
they wanted to build.
- Yeah, yeah.
- And we had everything
from people, you know,
doing, you know, very standard
things like Slack integration
or things you would think
of when you think MCP
up to like people
who like steered their
3D printer with MCP.
And I love this like when
it got into the real world,
when like Claude got into the real world
because of an MCP server.
- What was it?
Because I remember that too
when we were doing these,
all these hackathon projects,
and there was no mandate
to force people to use MCP.
This was just like an
entirely organic thing.
Why did people gravitate towards
MCP for all their projects?
- I think it really was
that standardization layer
just made it so much easier
to add context to the application,
because the moment that
Claude is now integrated
against MCP, that means
as the server builder
you can build 1 to 10, 20,
however many servers you want,
and you know that it
will automatically work
with that application.
And so I think that just
gives you the ability
to only think about one side
and not have to think
about the other side.
- I think there's a bit of a magic moment
when you teach Claude something new
using an MCP server for the first time,
and you see it takes action
about something you care about.
And I feel that's a little
bit of moment of magic
that I think MCP captures really well,
which makes people so excited,
because within five minutes
there's something going.
- Right, right, yeah, I've seen it myself,
and I mean even experienced it
where it almost feels like you take Claude
out of the the box, so to speak.
And all of a sudden,
instead of just being this thing
that is just right there outputting text,
it's doing other things,
it's calling other applications,
fetching on their data,
or even like operating a 3D printer,
which is a really crazy thing.
And that does feel really special.
And I guess MCP allows that
pretty seamlessly to some degree.
So this was back in end
of summer, early fall,
as we were doing these hack
week and these other things.
When did we launch MCP, and
what did that look like?
- We launched MCP around Thanksgiving.
- Yeah, November.
- 2024.
- And how was that launch?
What was the reception?
- Slow at first.
I think everyone's response
is, as you can imagine,
well, some people still have
this response is, what's MCP?
- Right?
- Mm-hmm.
- We, naming is hard.
We definitely could have named it better.
- It's arguable now, it's
kind of caught its storm.
- I know.
- That's fair.
But you still get the
like MPC instead of MCP,
and then it makes me
think NPC, and you know?
- Yeah, acronyms are hard.
- But, yeah, acronyms are hard.
But you had a lot of
people asking what is MCP,
not just externally, but
I also think internally,
because it was such a bottoms up movement.
You know, initially people were like,
oh, what is this thing?
What does it mean to ask or
to give the model context?
And then as people started
playing around with it
and seeing it for themselves,
I think that's where it
actually slowly caught steam.
And the turning point was
when more and more clients
kind of started adopting.
So I think the IDEs were
the first to adopt.
More recently we've seen a lot
of adoption from model providers,
and that's kind of created
a lot of kind of waves
in the market to incentivize
a lot more server providers
to actually build servers.
- I think one of that part is like you see
so many times on like social
media, like what is MCP?
Why would I ever want this?
And then like a month
later, a few days later,
they're gonna be like, this
is the best thing ever,
have so many of these
stories, and it's so funny.
- Yeah, so it's now become,
I think it's fair to say
like industry standard of
like integration protocol.
I mean, there's nothing else in my mind
that kind of rivals it,
but I think like going back to the launch,
a key decision here was to
actually make this open source.
And that was pretty different
in comparison to maybe previous efforts
in this area that had been launched.
Can you explain the reasoning
behind that decision
and why did we open source it?
- Yeah, if you have a closed
ecosystem for integrations
and for a context to be
provided to AI applications,
then a isn't clear to the,
you know, server builders
or the integration builders, you know,
is that AI application
gonna be around forever?
Should they invest in that?
Which ones should they invest in?
And so by making it an open standard,
you really kind of decrease the friction
to even building those integrations.
And we believe that the value
of building an AI application
is not necessarily
which integrations you have access to,
but the model's intelligence
and the workflow that you
build on top of the model.
So we wanted to focus the
industry on those two things
and not necessarily on
building integrations.
- That makes sense.
And there also seems potentially
like with open source,
there's this kind of
cycle you can get into
where somebody contributes to a server
and then like somebody uses
it and they notice bugs in it
and then they're like, oh,
I can just go fix it myself.
And that maybe speeds it all up.
- There's another part to that is Justin
and I just like open source.
- Hey, sometimes it's the simplest thing.
- Yeah.
So now we have, you know,
lots of companies adopting
MCP into their own products.
We have lots of other developers
and companies creating servers
to be able to use all these
or to be plugged into all these clients.
What does this look like
across the industry now?
What's like the current state of MCP?
- The current state is that
we have major players adopt it
across like their products.
We have a really big ecosystem
of MCP server builders.
It's like 10,000-plus.
And it's like at this
interesting intersection
that initially was like
mostly focused on developers
and a very local experience
where the servers would run local
and the software they
use it would run local.
And I think we have this inflection point
where we're starting to see
these servers being
hosted like in the cloud,
like as a web thing through
what we call remote MCP,
and a Claude AI integrations is like
really the first big entry to that
that allows you to connect
just like a website,
like that offers an MCP server
into your day-to-day Claude AI workflow.
And I feel this is like a pivotal moment
where it can be like a
true standard for the web
for how like LLMs interact with that.
I think that's to see what
this is gonna work out.
But yeah, I think that's
where we're currently at,
and we do of course have
a increasingly bigger community
being built around us,
and this is like big companies,
but it's also like sometimes
just open source people
who just like working on MCP,
and that's just becoming bigger.
- The craziest thing is someone
fixed our docs this morning
'cause we had a image
that was out of date,
and they just submitted the PR, we accept.
- That's why you want
to do it open source.
- Yeah, that's, I love that.
- I love that the community gets behind it
and they also feel ownership
and wanting to maintain it as well.
And it seems like, I mean,
we were chatting about this
before we started filming,
there's a lot of things
happening in the MCP world too
outside of just like
working on the protocol.
What's going on in your
world these days with MCP?
- Yeah, it has a lot, right?
There's conferences on MCP.
There's just like a lot of conversation.
There's like partnerships where
we work with like, you know,
big companies on like
evolution of the specification
and what their problems are.
I learned a lot about like
enterprise deployments
and the needs for identity
and authorization in that
space over the last few months
and had like help from
some of the best people
in the world around this.
And that's just like a
little bit of that world
of MCP at the moment.
- That's awesome.
Yeah, I'm just like blown
away by like the response,
and like I'm starting to
see now online of posts
around like is this what it looks like
to witness like the birth
of like a new protocol?
Is this like what it was like to be around
for HTTP or something like that?
How would you guys
liken those comparisons?
Like is this a new protocol of that sense,
or how can we expect to
frame this in comparison
to things we've seen in the past?
- I mean, I would hope so.
None of us can see the future.
You know, knock on wood
that we've landed on the right thing.
But I think that's where the
community can help guide us.
The hope is that we have
hit on the right problem
of providing context to LLMs
and that we have thought far enough ahead
that all the right
building blocks are there,
and the community can help
guide us as we're evolving it
into kind of the next few steps.
- I think from my perspective,
we just need to build something
that people want to use
and build this together with
people who care about this.
And I think like you don't
need to compare it to HTP
or anything else, it's just like,
just make something
that people want to use,
and that's in the end of the day.
- So if I'm a developer,
and I'm new to MCP, and
I wanna become involved,
and I also wanna learn a little bit
about how to work with MCP,
do you have any tips for this person?
- I think the first thing
that I would do is go look
at an existing server that is online.
Go play around with it, see
how it works with Claude AI,
or Claude desktop if you wanna
play around with local MCPs.
But just get a feel
for what that interaction
pattern is first,
and that will make it much easier
for you to then build your own MCP.
And start with the classic,
you know, hello world.
Just do one tool, just
respond with, "Hello world."
Do the same thing for you
know, prompts, resources.
Just try the very basic thing for each
before you go into anything more complex.
And I think once people
get a feel for that,
they realize how easy it is.
- Yeah, I would certainly
just start local,
just whip out Claude Code
and just write code like an MCP server
and just go from there.
I think that works
actually surprisingly well,
with like 10 minutes
you can have something,
and then yes, what Theo said,
just like look at great
servers and what they do
and make the modification from there.
- Yeah, it's funny you say that.
I was experimenting the other day
with just getting the docs
Model Context Protocol, the IO,
pasting it into Claude Code,
and then like make me a server.
And I didn't even have to like
paste in the content or anything.
Claude Code went, grabbed it, fetched it,
brought it in, made the server.
It was like a very easy
example right there
of just how quickly you can get started
with some of these things,
especially when you've Claude
under the hood powering it.
Any favorite MCP servers
that you guys have seen
out in the world so far?
- I really like those MCP servers
that bridge the gap to
like the real world.
Like I'm a person who likes music,
and I have synthesizers at home,
and there's an MCP server
that someone created
to like create basically like,
control their like synthesizer.
And I just love that.
It's just like,
here's Claude interacting
with a physical device
that later makes music, and
that's just so cool in my mind.
I love those, and I
love the creative ones.
I love the ones where people
play around with Blender.
I love the quirky ones.
Like one of our team members
has Claude control his door
through like an MCP server
and like role-play a doorman,
and it's just like I love that creativity.
- I mean really with that,
it's like the possibilities are endless.
Anything that you could ping
through an API or anything,
you could wrap in an MCP server
and then control it with
Claude or another LLM.
And the Blender one, explain that.
So somebody was actually using Claude
to control Blender just through MCP?
- Yeah, basically is just like
the MCP server just writes like
Blender scripts into Blender
and you see in, you know,
there's lots of videos.
You should check it out.
It is like you just see
Claude calling these tools,
and on the side Blender
just creates like a scene
out of nowhere, and it's
actually just not the person.
It's Claude creating it, and I love it.
- That's awesome, I love that.
Let's switch gears a little bit.
So we just recently released Claude 4,
so Opus and the new Sonnet.
What does this enable for MCP,
and how does this connect
into this broader theme
we're seeing around agents and AIs
that can kind of operate
on longer time horizons?
- As we get into models
with more intelligence,
it can do longer running tasks,
I think some of the primitives
that we've actually built
into MCP are going to become more used
that right now may not have
gotten as much adoption.
So, you know, things
related to statefulness,
things related to actually doing sampling,
but those are the primitives
that we thought about
in the beginning that actually
help in an agent's world,
but do require the models to
have the amount of intelligence
where they can kind of start
doing longer running tasks.
- That's interesting.
So some of these things that
maybe haven't been utilized
so much just yet will become
more and more important
because the models just get more capable,
and they're able to use 'em.
- It also just makes it probably easier
to like put more MCP
servers, like attach it,
and Claude is just gonna
get better and better
at like distinguishing which one it needs
to make to take action.
- How many MCP servers can
you throw at Claude at once?
How does it know how
to choose between them?
- Depends.
- Good question.
- It depends because it
depends on, you know,
how are the tools written,
are they overlapping?
If you put like three
issue tracker MCP servers
next to each other, of course
the model can get confused,
but if it's like, you know,
an issue tracker thing
and I don't know, something
completely different,
like I don't, you know, whatever,
and I think then it becomes,
you know, pretty easy,
then you can put a lot
of it next to each other.
Just a matter of like of your workflow
and how overlapping they
are on the end of the day.
- I see.
And I'm assuming as models get
more capable and intelligent,
it becomes like you can throw
more and more at them too.
So what's next for MCP?
- The protocol is now live.
There's good adoption,
but we can do a better job
of helping people understand what it is.
So we're definitely going to invest
in more examples, better documentation.
We're also investing in
key security primitives.
So the thing I think most people
are gonna be excited about
is agents and how we're
thinking about agents.
So for agents, one really big ship
that's coming is the registry API.
So that is going to allow models
to actually go and search
for additional servers
that they can then bring into the LLM.
That then allows kind of a little bit more
of an agentic loop
since the client doesn't
just get to decide, you know,
here are the 10 things that I am aware of
and that I want the
model to have context to.
The model can now go and search
for more things on demand.
The second is long running tasks.
So actually making it easy for you
to do longer running things with MCP.
And then the third one is elicitation.
So how do you as a server actually go back
and ask the user for more information
if you need more information.
- Exciting.
Well, I'm very excited to see
what the future holds for MCP.
And thank you both for coming on.
- Thank you.

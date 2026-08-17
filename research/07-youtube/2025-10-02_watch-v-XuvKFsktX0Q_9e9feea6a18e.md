---
title: Building the future of agents with Claude
source: "https://www.youtube.com/watch?v=XuvKFsktX0Q"
published_at: 2025-10-02
captured_at: 2026-08-16
author: Anthropic
source_type: youtube
authority_score: P2
mind: engineering
status: captured
evidence_url: "https://www.youtube.com/watch?v=XuvKFsktX0Q"
catalog_id: 9e9feea6a18e
subtitle_file: XuvKFsktX0Q.en.vtt
---

Kind: captions
Language: en
- Because as a developer, my
creativity ends at some point.
I can only think of so many use cases.
But the model, like anything,
anything somebody comes with,
the model will figure out
a way to go do that thing.
- Hey, I'm Alex. I lead Claude
Relations here at Anthropic.
Today we're talking about
building the future of agents with Claude,
and I'm joined by my colleagues.
- I'm Brad.
I run the PM team on the
Claude Developer Platform.
- I'm Katelyn, I lead the engineering team
for the Claude Developer Platform.
- Let's talk about the
- Yeah, let's start with that.
- Let's start with that.
- Start there.
- It used to be called the Anthropic API.
- Yeah.
- We just went through
a big name change.
Can you walk me through
why we made that change
and also what this new platform
is and what it encompasses?
- Yeah, totally.
So the Claude Developer Platform
really encompasses our APIs,
our SDKs, our documentation,
all of our experiences within the console,
and really everything
that a developer needs
to actually build on top of Claude.
We're really humbled, proud to serve
some really awesome
customers around the world
who are trying to, what we like to say,
raise the ceiling of
intelligence using Claude.
And the platform really
enables them to do that.
And I would say one of my
favorite parts about it
is the platform doesn't just
serve customers externally,
the platform actually serves
our internal products.
So we love telling people,
Claude Code, for example,
is actually built directly
on our public platform.
- I see.
- Yeah, I mean,
I think when we started,
we were just the Anthropic APIs
very simple access to the model,
but over the last year or so,
we've added so many features to it.
We added prompt caching,
we added a whole separate batch of API,
we added web search, web fetch,
we have this context management
support, the code execution.
So all these tools, you
know, now this kind of,
we feel like, yeah, it's aspirationally,
it's a platform now.
- I see, so there's just
a lot more to it now.
It's evolved in a pretty
drastic way over the past year.
- Yeah, yeah.
- Better, I think so.
- And I think that's what developers
were sort of calling it anyway.
You know, so it's always
natural to just sort of go
with what developers were saying.
- We were a little late to the game there.
It's always had it, right?
- It's okay.
- We've made our amends.
One of the cool things you can do now
as we're moving from
the sort of chat model
to maybe this more agentic future
is building agents as part
of this developer platform.
Before we get into how
we're actually doing that
on the platform, can we talk
about what even is an agent
to begin with?
- Yeah, I mean, agents is,
it's almost sort of a buzzword, right?
Like everybody you talk
to now is building agents
and whenever a industry tech
term gets to that level,
you know, the definition gets very gray.
Everything everybody builds is an agent.
But Anthropic, what we
really think about agent
is where the model is taking some autonomy
to be able to choose what tools to call,
to call those tools,
to handle the results,
and kind of choose the next step.
So as a foundational research lab,
leaning into the model
and what its reasoning,
how it decides what to do,
we think that's a really important element
of what an agent is.
- Mm, so it's kind of like the aspect
of it being autonomous in some sense.
- Charting towards-
- I mean, I think there's also,
I mean, we have customers
doing really useful workflows
where they're sort of predefining the path
that Claude should walk
and that is a super-useful thing to do.
But what's nice about the agentic thing is
as the model gets better every
couple of months, you know,
we release a new model
and with a true agentic pattern, you know,
those services are just gonna get better.
Where if you build a workflow
with a lot of scaffolding in it,
you kind of put bounds on the model,
which is maybe okay in some use cases,
but that means that you
may not take advantage
of the next level of intelligence
that a next model release gets.
- Yeah, so it seems like
there's this interesting trend
with agents, at least
over the past 6-12 months,
where like you've said, the scaffolding
has been a bit of a hindrance,
and maybe we're dropping some of that.
Can you explain the
intuitions behind that around
is this actually the future
is we give less and less
things to the model?
- Yeah, I mean, I think over time
what we're seeing is the
scaffolding the model needs
to be able to accomplish
tasks is it's needing less
as the level of intelligence
of the model goes up.
And we believe is gonna keep going up
that basically the model has
more contextual understanding
of the high level task that
it's trying to accomplish.
So therefore it doesn't need
as many sort of guardrails,
And in fact, those
guardrails in some cases
become some like a liability to have.
We've had customers try out new models
and say, "Oh, well, it's actually only
just a little bit better."
And then we kinda look into it with them
about what's going on.
And it turns out well,
yeah, they were constraining it in ways
that makes it harder for them to see
the intelligence of the model.
- Ah, does this match
what we see in the field
with our customers
where they're also
following these same trends?
I know at the limit we
have customers exploring
all sorts of innovative
techniques for managing Claude.
And there's actually a lot of discourse
about this right now, right?
Like, what is an agent
and what does it need?
What do you need to build?
And there are people saying, you know,
"It's just a wild loop."
Like, "You don't have to try that hard."
And I think ultimately there's
been a lot of evolution
of frameworks that people
are putting around the model
that are helping them
orchestrate their agents,
try to get the most outta the model.
And I think what the industry
is maybe kind of circling around is
a lot of that has become maybe too heavy
and maybe too opinionated
and which is why you
kind of get the people
coming back to like,
"It's just a wild loop
and that is all you need."
And I think what we're
trying to do there is to say
maybe in a lot of ways it is a wild loop,
but the things we can more uniquely do
to help people get the
most out of the model
is a lot of those tools,
those features and otherwise.
And so what we wanna do is put, you know,
frameworks and tools
and platform out there
that is opinionated
to some extent on how people
should use those tools.
But it's not this super-heavy framework
that really to Brad's
point gets in the way
of what the model's
ultimately trying to do.
So it's strike the right balance.
It's like, you know, we've
seen what a lot of people
have tried to do, so we know
we can be opinionated there,
but we wanna be lightweight in
the way that we're doing that
and make sure that the
real thing we're doing
is helping you get the
without, you know, bogging you down
in some super-heavy framework.
- Right, so would you describe
part of the strategy here then
as providing these
auxiliary tools and things
that we can give to the model,
but we're not necessarily
placing the bumper
spawn the model itself?
- Yeah, we think about it as like,
how do you unhobble the model?
The model already has
a lot of capabilities.
In fact, I'm convinced that
even if you take your
current generation of models,
there's way more intelligence in there
than we've been able to unlock.
But anyway, that intuition
is if you just give the model
tools it needs and set it free,
let it be able to use
those in the right way,
you'll get great results.
And I think a good example of that
is we launched this
server-side web search tool
and web fetch tools.
And it's been interesting to
watch customers use those.
And you know, all we did really,
I mean it's a very minimal
prompt that we have.
We just give it the web search tool
and all of a sudden deep research tasks
are almost completely done
with just turning on
that switch on the API,
because the model will call that tool,
it'll look at its results,
it'll say, consider it
and say, okay, maybe I
need to call, you know,
do these other searches
and then, oh, that fourth link you return,
that's the great one.
It'll do a web fetch on that
link and bring that data back.
And really all that very
autonomously on its own
kind of deciding.
- Right, I think it's almost kind of like
an interesting shift in
where the intelligence
of a system is being applied.
- Exactly, yeah.
- From the developer
having to apply their
intelligence to guiding
towards the model now, figuring it out.
- Right, and it's so exciting
what the model does it,
because as a developer,
my creativity ends at some point.
I can only think of so many use cases,
but the model, like anything,
anything somebody comes with
the model will figure out a way
to go do that thing.
So it's great, great
to unhobble the model.
- Yeah, so if I'm a developer today
and I'm getting started building
with the developer platform,
what do you recommend?
What are some best practices
or ways for me to get started?
- Yeah, so super-tactically,
actually the number one thing
that we recommend right
now is the Claude Code SDK.
And what's really, really interesting
about the Claude Code SDK
is we essentially built an agent harness
an agentic harness around the
model to run that loop, right?
And automate a lot of that tool calling
and otherwise feature use.
And obviously originally was
built for coding purposes.
And what the team really
quickly figured out was like,
actually this is an excellent
general purpose agentic harness.
And so what the SDK does is
it gives people a perfect
out-of-the-box solution
to actually just start prototyping agents
without having to go and build, you know,
the loop with all the tool
calling and otherwise.
It's built on top of the messages API
and all those same tools
that we're mentioning.
But it kind of gives you that
really great starting place
right out-of-the-box.
- Right, I feel like this is
a pretty common misconception,
at least when I talk to developers
about the Claude Code SDK.
So I'm not building a coding application.
Why would I wanna use this?
But you can kind of remove
the coding-specific parts,
- Yeah, I mean I think
that's a great example
of what we were talking about
removing scaffolding on the model.
It's like once we got done
removing things from Claude Code
to really unhobble the model,
it turns out there was
nothing coding left.
When you remove everything else,
then it's just agentic loop
and you're really a
minimalistic thing to give
Claude access to a file system,
to a set of Linux command line tools
to the ability to, you know,
write code and execute that code.
So those are all very
generic kind of capabilities
it turns out could solve a
wide variety of problems.
- Right, yeah.
I feel like something
I've been running up to
in my own side projects
and also seeing with
projects within Anthropic
is before the Claude Code SDK,
everybody's implementing some form of
managing prompt caching
or some form of managing their tool calls
and that loop.
And now it's like, oh, just
start at this base point,
and then build from there.
- You start a little bit higher up.
- Yeah, yeah, yeah.
- So it's like a further
level abstraction.
I think that's super-interesting.
- I mean, I think the other
really interesting thing
to think about, especially for
businesses looking at agents
is what use case to go target.
So thinking beyond the technology,
what is the actual problem to go solve?
And I think, you know,
we see a lot of customers
and doing a lot of
things we love all of it,
but where, you know,
the biggest impacts are
is where a customer has thought hard about
what's the business value of this?
Will it actually save this
many engineering hours
or will it help us remove this
much manual work or whatnot?
And being able to articulate
what you expect the outcome
of the agent project to be,
I think is really helpful
in defining the scope of the agent.
- Right, and tying back
one more time to the SDK.
So it seems like it's been
really, really useful for
individual developers
like myself, you know,
starting out and just
wanting to get hacking
on something really fast
for these customers, for enterprises
that are actually trying
to get real business value
on these things.
Should they be using the SDK?
Is it ready for them?
Is it ready for scaled use like that?
- Yeah, so I think in a lot of ways it is,
in a lot of ways if you are
in a spot where you can,
like, you can deploy that runtime,
essentially, that's what
you get outta the SDK
is an agentic loop runtime.
You can go and deploy that
runtime wherever you want,
whenever you're ready to do so.
But I think what we're really trying to do
is take the spirit of what
the SDK unlocks for people,
go kind of up to that
higher order abstraction
where we give you the loop,
we give you a lot of the tool
calling in an automated way
and say, how can we learn from that
and give people out-of-the-box
solutions that at scale
will really be able to
solve for their use cases.
And I think that's a lot of
where we're kind of trying to go
with our roadmap throughout
the rest of the year.
And one really important
bit when we think about that
is if the entire goal
here is to help our users
really raise that ceiling of intelligence,
get the absolute best
outcome outta the models,
then higher order abstractions
are not just make it easier,
because you don't have to
write all that code yourself.
It's actually like, how can
we really, truly help you
get the best outcome?
Because we're in the room with research,
we're in the room with inference,
we know how to make sure
that our abstractions,
our agentic loop is going
to be extremely powerful
and extremely good at working with Claude.
And the last thing that
I would add in there is,
especially as these
things get longer running
and as we provide more and more tooling
to help people get at
those longer running tasks,
another big problem that our users
we know are gonna keep trying to solve
is observability within
those longer running tasks.
And so that's one of
the most common things
that comes up for folks is, you know,
I have these long running tasks,
I'm trying to get these
really great outcomes,
but you know, I might
need to do some steering
or I might need to tune my prompt,
or I might need to
think about tool calling
a little differently.
And that's something that
we know we can give people
that observability through
the platform over time.
And that's another big
area of focus for us.
- Mm, okay, that's really interesting.
I mean, this has been a huge issue
that's starting to come
to a head with agents-
- I think so.
- ... especially as you trust
them to go work in some,
you know, other application
in the background,
how do you make sure they're
actually doing the right thing
and then if you're deploying them.
- Yeah, how do you audit it?
Like if we're gonna give
some level of autonomy
to the system, there needs
to be a way to audit it
and make sure the right
things are happening,
so that you can tune things and whatnot.
So I think observability is
really a key piece of this.
- And putting a pin there that
I wanna ask a question on,
just the future of how
we're gonna address that.
Before I do, is there other
tools that exist right now
that folks should be aware of
when they're getting started
things that you've
found helpful or useful?
- Yeah, I mean, I think there's a,
so we mentioned web search and web fetch.
I think an another big
thing that we're seeing
is customers right now
have to do a lot of work
to manage the context window.
So by default, Claude has
200 K tokens of context.
We have a million token
available now in beta on Sonnet,
which is great, but even a
million, there's a limit there.
And what many customers have told us
is that they get better
outputs, higher intelligence
if they even use a smaller
part of the context.
And so we've done, we have
a couple of cool features
that are just coming out
to help developers manage that context.
So in these agentic loops,
a lot of times you're doing
10, 15, 100 tool calls
and you edit this file
or look up data in this database
or you know, send this email
and each of those tool calls takes up
100, 200, 1,000 tokens.
And so we have this cool feature
that lets the model actually remove
some of the older tool calls
that are not needed anymore.
- Interesting.
- And that gives,
just like you, if you declutter your desk
and declutter your notebook,
you can focus a little bit better.
So if you declutter the prompt actually,
the model can actually
focus a little bit better.
- Ah, interesting.
So okay, we're moving unnecessary context.
Is there a risk that we
remove necessary context?
- How does that work?
So we have some guardrails
and some bounds around it,
but the general rule is
we try to remove the tools
that are several turns back,
that the model's already made decisions
based on those tools.
Yeah, I was playing with it recently
and I removed the tools
that it was just called
and it's, oh, my tool results are gone,
I don't know what to do.
And then, but the model,
the Sonnet doesn't give up.
It's like, I'm just gonna call
this tool again, you know?
- Yeah, yeah, yeah, yeah.
- But yeah, so generally we
have put some bounds on that,
because of that experience.
So we do preserve the
most recent set of tools.
- I see, okay.
- And then the other cool
thing we do is tombstone it.
So by that we mean when
we remove the tool calls,
we put a note in there
to the model that say,
oh, the tool results for
the search call were here.
- Oh, okay.
- And they've been removed.
- So the model's not
completely memory wiped.
- Exactly.
I think we found the model does better
if we just give it a little more context
about what is happening.
And so that's a key feature.
And the other one is
this kind of agentic memory feature
that we've added.
And there we have seen
that the model does,
right now, if you give
a task to the model,
say a deep research task
or play Pokemon or whatnot,
the model does about the
same every time it runs.
But if you give a human a task,
the fifth time the human does a task,
they do it way better,
because they've learned, okay,
if I'm gonna do this search, okay,
probably the Wikipedia site is better
than this other site or whatever.
They learn which thing, so
they get better over time.
So we've given this memory
tool to the model now,
so that the model can
actually take some notes
while it's going and say,
oh, I realize that this website
maybe isn't the right one,
or if I'm doing a search,
it should be like this,
or if I'm looking up, I
should use this database,
not that database or whatnot.
And it makes those notes.
And then when it's stumped,
it can actually go back
and review its notes
and say, okay, oh, I'm starting this task,
let me go read the notes,
so I can figure it out.
- Ah, cool.
So we're handling all of that
for the developer to say.
- Yeah, yeah, well, we're giving the model
this core capability to do memory,
and right now we're letting the
developer manage the memory.
So, because, you know,
different developers,
they might wanna store
it in some cloud storage
or they might wanna
store it somewhere else.
So we're letting developers
figure out exactly
where to store the memory.
That way they have more control over that.
- But exposing the tool.
- But expose the tool.
Yeah, we expose the tool.
- So going back again to
a roadmap question here.
So it sounds like there's
a ton of new features
that we've recently launched.
There's a lot of momentum,
and now there's other offerings as well,
like the Claude Code SDK
and things coming out soon.
What are you most excited about, Katelyn?
What's the future looking like
here in the next 6-12 months?
- Yeah, so we talked a little bit about
these higher orders of abstraction
where we can really just make it
as simple as possible
for you to get the absolute
best outcomes out of Claude.
And we wanna pair that
with the observability
that we talked about,
so that you can really, you know,
see the data and take those insights
from those longer running tasks.
And if you can combine
these things together
and start to think about
some of the capabilities
like memory that Brad just talked about,
you can really start to see this flywheel
where over time we're
not just able to help you
get the best outcomes out of Claude,
but we can help you get self-improving
and continuously improving
outcomes out of Claude.
And that to me is kind
of the galaxy brain magic
of the roadmap is get to
a point where, you know,
we have people coming to us,
they're building on Claude,
they have their tasks, they
know what they're trying to do,
and they get these really like aha moments
where over time it's getting
better and better and better.
And you know, that's
kind of the biggest thing
that in everything that we're doing,
we're trying to make
sure we're going after.
- That's awesome.
- Yeah, I mean, I guess I'd have to say
I'm always excited about model launches.
It's like Christmas, wow,
what will be possible now?
So I love playing with the model launches
they come out, just
unlocks more use cases,
some use cases that, you know,
we've been working hard on
and trying to improve,
which is satisfying to see,
but also some things I
had no idea the model
would be able to do this thing.
You know, now it draws ASCII
pictures so much better
or what, you know, whatever.
- The important things.
- Very important things.
But beyond that, the other
thing I'm really excited about
is we're in the early stages
of giving Claude a computer.
You know, I think about
if we hire an employee
here at Anthropic and we welcome 'em,
"Here's your first day."
But we don't give them a computer.
They would not be very
successful at Anthropic.
So right now, essentially
everybody is using Claude
and it doesn't have a computer.
So I'm really excited about
giving Claude a computer
and you see the very baby steps of that
with the code execution tool,
where the model can write
code executed on the VM
and get the results back.
So it can zoom in on images
or take a Excel spreadsheet
and create amazing data
analysis with charts and graphs.
And that's just the baby step.
What if I had a persistent computer
that was always there
and it could organize the files
in there the way it needed
and get the tools set
up the way it wanted.
And I just think there's a lot
of headroom to that scenario.
- Yeah, and I guess that all
ties back into this unhobbling
into this too.
- Exactly, exactly.
It's all about unhobbling the model.
That's exactly, just
give Claude the tools.
- Well, I'm excited for that future.
Thanks so much for this conversation.
- All right, cool.
Yeah, thank you.
- Thanks.

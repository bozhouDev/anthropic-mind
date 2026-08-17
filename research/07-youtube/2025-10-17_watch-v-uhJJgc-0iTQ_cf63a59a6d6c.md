---
title: Building more effective AI agents
source: "https://www.youtube.com/watch?v=uhJJgc-0iTQ"
published_at: 2025-10-17
captured_at: 2026-08-16
author: Anthropic
source_type: youtube
authority_score: P2
mind: engineering
status: captured
evidence_url: "https://www.youtube.com/watch?v=uhJJgc-0iTQ"
catalog_id: cf63a59a6d6c
subtitle_file: uhJJgc-0iTQ.en.vtt
---

Kind: captions
Language: en
- I think there's also a
lot of interesting things
to explore of multi-agent as
a form of test time compute.
- Basically letting Claude,
many Claudes work on a
problem can be, you know,
get you a better final
answer than just one.
- Hey, I'm Alex, I lead Claude
Relations here at Anthropic.
Today we're gonna be talking about
building more effective agents
and I'm joined by my colleague.
- I'm Erik, I work on multi-agent research
here at Anthropic.
- Erik, to kick us off here,
can you just explain why Claude
is so good at agent tasks?
- Yeah, sure.
So during our training,
we let Claude practice being an agent.
We give it open-ended
problems for it to work on
where it can take many steps
and use tools, explore where
it is and what it's working on
before giving a final answer.
And by getting lots of
practice at being an agent,
Claude becomes really good at this.
- Okay, so it's these long running tasks
and a variety of domains basically.
And through the process of RL
and other training mechanisms,
Claude is learning an objective
of how to do these things
with basically limited
guidance or feedback.
- Exactly, we do lots
of RL on coding tasks,
on search tasks, lots of things for Claude
to practice being an agent
in different environments.
- There's kind of this conception,
I think of Claude models
that they're really,
really strong in code,
but that doesn't always maybe
transfer into other domains
or that coding is its own separate thing.
What are your kind of
views on that generally?
- So coding has been the first task
that we've really focused on,
but once you have an amazing coding agent,
a coding agent can do
any other kind of work.
- If you need to do search,
you can do web search,
you know, via APIs, you
can plan a weekend by,
you know, creating a schedule.
So we really see coding as
a very fundamental skill
for an agent that's gonna have
a lot of spillover effect,
to be able to make Claude
great at all sorts of things
and sort of like train on
the hardest thing first
and then everything else will become easy.
- One interesting thing
I've seen here recently
with a feature that we released
in Claude AI on the web
was the ability for Claude
to create actual files
through writing code.
So it was like writing a Python script
and then the Python script got ran
and all of a sudden you
have like a Excel sheet
that popped out of that.
Is that kind of the future
direction that we're headed
is like Claude's writing scripts
and taking actions on
computers to create files
or do things that are
traditionally not code related?
- I think that's one of
the really effective ways
Claude will be able to do these things.
Actually, just a few days
ago Claude was helping me
make some diagrams for a presentation
and it was able to create files
just by writing out the SVGs,
but then I wanted it to make
a much more detailed diagram
that would need a lot of repetition
and so Claude was actually able to do this
by writing some code to generate the SVG,
which ran much, much
faster than Claude itself
needing to write you know,
it was a very, very repetitive image file
with lots and lots of sort
of detailed patterns in it.
- Yeah.
- So, yeah,
I think that for a lot
of cases writing code
to produce some artifact
will be much better
than just trying to create
that artifact directly.
So it's one way to do it for harder cases.
- Okay, right, yeah.
Code allows for kind of this speed up
that's not even possible with
like a human like clicking
and dragging and using
their mouse on a computer.
Like repeated actions.
- Exactly, Claude gets a for loop.
- Yeah, if you're a developer
and you're building an agent with Claude,
one thing that we've started
to see become really popular
is this Claude Code SDK.
Can you walk me through what that is
and how you're seeing
developers starting to use that?
- Yeah, so we're really
excited about developers
using the Claude Code SDK.
This is something where
previously if you wanted
to build a coding agent
or sort of any agent,
you had to really go from
nothing but hitting an API endpoint,
build the loops yourself,
build all the tools,
build executing these tools,
interacting with files,
interacting with MCP.
We basically have already built
all of that into Claude Code
and even though its name is Claude Code,
really Claude Code is just
a general purpose agent
that is most often used for code.
Yeah, we are encouraging a lot
of developers to use this SDK
as the core of their agent loop
and that way they don't
have to spend a lot of time
reinventing the wheel that
we've already put a lot of time
into polishing and perfecting
that core agent loop
and instead they can use that
and then just add their tools
for their own custom business logic
or affordances into that via MCP.
- Right, so it offers that
sort of customizability
to where you can remove
the coding-specific bits.
- Exactly.
- And put in
whatever sort of prompt
or tools that you need,
just like slots nicely into the scaffold.
- Yeah, I think also the people
have been using Claude Code
for all sorts of things.
I think the, my strangest
use of Claude Code
is I once had it plan a date for me
where I did a bunch of web searches,
found interesting activities
and restaurants in the area
and so not code related at
all, but it has all the tools.
- How was the date?
- It was pretty good.
It was great, yeah.
- Claude did a good job?
- Yeah, Filoli Gardens
and then a Chinese restaurant nearby.
- Wow, okay.
- Claude did a good job.
- I'm impressed.
One other thing on Claude Code
that has been another popular feature
I've seen a lot of software
engineers use lately
is Claude MD files.
So these are files that you, you know,
define within a project
and gives Claude relevant
information about
what your programming style is
or like what the layout
of the directories are,
things like that.
We've now launched a similar concept
that maybe takes a step
further called Skills.
Can you explain what Skills are
and how we're starting to
see developers use them
and what they mean for Agents?
- Yeah, so Claude Skills are
a very exciting extension
of Claude MD files where
instead of just giving it
notes files, you can
give it any sort of file.
That can be PowerPoint
template files, it can be code
and like helper scripts
that you want it to use.
It can be images or assets.
And I think this extension
of not just instructions
but resources for the agent to use
is a really, really powerful
tool where you might say,
not just these in are my instructions
for making PowerPoint
presentations, but here's, you know,
the head shots of all of
our company leadership
that you might need to
reuse in many presentations
and just giving it all to
Claude in a reusable way.
So it has everything it needs right there.
- One analogy I've heard used internally
that I really, really like is,
it's kind of like in "The Matrix"
when Neo is learning kung
fu for the first time
and they like inject him
with the Kung Fu information
and all of a sudden he
is like a Kung Fu master.
That feels like very similar
to when I give Claude a skill
of some type of like, here's
how you create spreadsheets.
And it's like, oh, all of a sudden
Claude's like a banker now
and it can create a
financial model for me.
- That and where they load in
all of the racks of equipment
and tools and stuff for them to grab.
- Yes.
- It's like, you know,
you can start with these
things, not just instructions.
- Yeah, I love that.
Switching gears a little bit,
so last time we chatted on
camera here a few months back
and we were talking about Agents
and at the time we were in this transition
from maybe workflows which
are like very defined ways
of how you chain together prompts
to what was just like
a single agent system
where you're running a model in a loop.
Since then, what's been
the evolution in the space?
- Yeah, so we've really seen
Agents take over from workflows
where Claude has gotten so
good at responding to feedback
and correcting its own work
that now Agent loops really
dramatically outperform
workflows for most things
where you care most about
absolute quality.
Workflows are still great,
where you need very low latency
and you want Claude to just
give a best answer, single shot.
Agents are really, really
high performance now.
I think one of the things that
I've seen develop since then
is what I call workflows of Agents.
Whereas previously an
application might have had
a workflow that had Claude in single shot
write a SQL command in order to load data
and then that would go to
another step in the workflow
where it would then write a
chart to display that data.
And if the SQL command
failed, you know this,
it doesn't know that it's
not returning any data
and then the second step of the workflow--
- Right.
- Is kind of screwed.
- Completely falls apart.
- But now I've seen people
where each one of those steps
in the workflow is actually a closed loop
where instead of just
writing a single attempt
at a SQL query, it then
runs, Claude sees the output
and then it can keep iterating and repeat
until it knows that it got the right value
and then it transitions to
the next step in the workflow.
- Okay, interesting.
So yes, this evolution I guess
of like chaining together prompts
to now chaining together
agents in these loops themself,
we'll see where that goes from there.
One other big topic of discussion,
I feel like that has taken a
lot more chatter as of late
is this question around
observability and verification.
Can you explain what that challenge is
and how people are
starting to think about it?
- Yeah, so observability
is very hard for Agents,
especially as the systems get more complex
and I think that's one of the reasons
where I still really believe
that even though the models
are much more capable today
than they were a year ago
and they can work better
in an agent or even more complex setups,
I think that simplicity is
still a really important thing
and that even though you can
build a big workflow of agents,
you should still start sort of by
from the simplest possible thing
and then work up to a
more complex solution.
And you know, that's first
trying single shotting things
or trying, you know, single
shot prompt to Claude Code SDK,
which is now just sort of such
a simple, easy thing to use.
And then I think only
as needed adding layers
and layers of complexity
because that's gonna make
the absorbability harder.
- Another term here maybe
in parallel to workflows
of agents is multi-agent,
is that the same thing
or is that something different?
- Yeah, so multi-agent is my
main area of research now.
I'd say it's pretty different
from a workflow of agent.
- Okay.
- Workflows of agents,
where sort of an one agent goes,
finishes and then it transitions
or its output gets sent to
the next agent to work on.
Multi-agent is where fundamentally
you have multiple agents
or multiple Claudes
working at the same time
where maybe one parent
agent delegates tasks
to five sub-agents that can
each then work in parallel.
And this is how our deep research
search product works is
the main orchestrator agent
will decide and create several sub-agents.
They can do lots of searches in parallel
and that's way better for the user
because you know, all
this happens in parallel
and you get the answer back much sooner.
We also see things like in Claude Code
the model will use a subagent.
So if something, if some
sub-task is gonna take
tens of thousands of tokens,
like maybe finding a certain
implementation of a class,
but the answer really boils
down to something very small,
it can do that work in a sub-agent
to protect the main
context from all of that,
those tokens that aren't
necessary for the main work.
So yeah, basically can
offload this piece of work
and just get back the
final answer that it needs.
- So are we exposing then
this subagent in this case
is like a tool that Claude can call upon?
- Pass in,
it'll pass in the prompt
as like a parameter or something?
- Exactly, yeah.
So to the, to Claude
sub-agents look like a tool
where it can pass
prompts to the sub-agents
that will then go and do work.
And part of my research is training Claude
to be a better manager and know how to--
- Oh interesting.
- Give clear instructions
to its sub-agents and make sure
that they gets the right things
and needs out of them.
- How is this different than,
or is this maybe like a specialized part
of tool calling overall or
is it different in some ways?
- I would say that this uses
the framework of tool calling
for that communication protocol
and it just happens to
be a tool that itself
is backed by Claude, by another Claude.
- Does Claude have like
an intuitive understanding
of what a subagent is or do
we have to like teach it?
Like you're actually
talking to another version
of yourself, Claude,
like don't get freaked out sort of thing?
- I would say that Claude makes
a lot of the same mistakes
that first time managers make
of where it will give incomplete
or sort of unclear instructions.
- Right, right.
- To a sub-agent.
- And you know,
kind of expect the subagent
to have the right context
when actually it doesn't.
And I think something we've seen
during training on
sub-agents is that Claude
starts to get much more
verbose and much more detailed
and give its subagent the overall context
of what's going on.
- Interesting.
- So that they can do better work
that adds them to the whole, so.
I'd say that, you know,
it definitely Claude,
Claude has a lot to learn
and is learning to get better at this.
- Okay, cool.
- What are, what are some
of the use cases here?
So their search is one in
like preserving context,
is there other things
that people are using
multi-agent for right now?
- Yeah, I think coding is,
there's a lot of subagent use in coding.
Anything that can be
parallelized or MapReduced.
If you have something
where you need to produce
a lot of output or there's maybe 10 parts
of some output you're creating,
if you can split that
up among 10 sub-agents,
that can be really, really
effective for saving context
and getting faster results.
I think there's also a lot of
interesting things to explore
of multi-agent as a form
of test time compute.
Just like with people, you know,
a bunch of people putting
their heads together
can get better results.
- In that case, are we specializing
these agents in any way?
Do we gear them towards like
one type of persona or another,
or is it just kind of let
them take whatever form?
- I think you can do either.
You know, sometimes it's helpful
to give a bunch of people
the same exact task and see
what the different answers
they come up with are.
Sometimes it's good to have many people
or many agents work from
different approaches
to the same problem or split it up.
One thing I've seen a lot is customers
that have a lot of tools,
maybe 100 or 200 tools
that they want an agent to use,
they found that it's
really good to split up
those tools among sub-agents.
So the main agent, all
it has to know is hey,
I want to use this bucket of tools
and then there's a subagent that goes
and does the actual work there.
So that each subagent
just has maybe 20 tools
that it needs to understand
and know how to use.
- Have we tried like scaling
agents like all the way up?
Like what happens if you
have like a thousand versions
of Claude all working on one problem?
Does it just turn into chaos?
- I've not tried that yet.
- But I'll get back to you.
- Good research idea right there.
What are some of other like failure modes
that we're seeing right now
with agents or multi-agents?
- Yeah, I think just like
any sort of complex system,
I think it's easy to overbuild something
and lose a lot of efficiency
and just create sort of a
lot of like dead weight.
And so I've seen overbuilt
multi-agent systems
spend too much time just
talking back and forth
with each other and not
actually making progress
on the main task, and you know,
human agents or human
organizations suffer from the stew.
As companies get bigger,
you have more communication
overhead and you know,
less and less work is actually, you know,
the people on the ground
making progress on things.
- And so I think that's another
interesting thing to study
is like how can we make
organizations of Claudes
very effective while
keeping the overhead small?
- If I'm a developer and I want
to get started with agents,
whether I'm building
on the Claude Code SDK
or just trying to on my
own, do you have any tips
or best practices that you'd give them?
- Yeah, I think the best
practices really remain
start simple and make sure, you know,
you only add complexities you need.
I think another really important thing
is think from the point
of view of your agents.
If you are giving Claude tools or prompts
or sort of any affordances,
put yourself in Claude's shoes
and read what it actually
gets, what it sees as the model
and make sure there's actually
enough information there
for you to solve the problem.
It's very easy to sort
of forget, you know,
that we're seeing everything
and the model only sees what we showed.
- And it's.
- Yeah, I feel like
it's always important to go back
into like the raw transcript
of like your tool calls
and your logs and everything
and just view that.
- Exactly, and I think another thing
is that as people are
building more things like MCPS
and trying to connect
Claude to more things,
I think a very natural first
instinct that people have
that's very wrong is that an MCP
or tools should be
one-to-one with your API
and I think actually tools
for the model or MCPs
should be one-to-one with
your UI, not your API.
Because ultimately the model
is a user of these things.
It's not, it doesn't work
like a traditional program.
So if your API might have
three separate endpoints
for say loading a Slack conversation
and turning a user ID into a username
and turning a channel
ID into a channel name.
If those are the tools you give the model
to understand Slack, for
it to understand anything,
it's gonna have to make three tool calls.
Versus as a user, you know,
we just see everything
all nicely rendered.
- Oh, that's interesting.
- So you wanna create a tool
or an MCP for the model
that it presents everything all at once
with as little interaction as possible.
Just like for a user it'll be terrible
if every time you had Slack
you had to like click on a user ID
to see what the name was, et cetera.
- Right, right, I like that.
So kind of working back from
like the end state almost
instead of like just trying to map
the technical specs one to one.
- Exactly, and sort of surround
whatever context you need with it.
- What do you think the future of Agents
has in store for us?
Any predictions on these
next six to 12 months?
- I think Agents are gonna
become a lot more pervasive
sort of starting in
areas that are verifiable
like software engineering.
You know, coding agents have
already changed how I work
and how tons of people at Anthropic work
and I think there's still a huge amount
to be be gained there.
I think one of the really
exciting things is if agents
can start getting better
at verifying their own work
with things like computer use
of, they can write a web app,
but can they go actually
open it up and test it
and then find their own bug
instead of you needing to do that.
I think that's one of
the most exciting things.
- Is like closing
that loop of testing
so that I don't have to
be Claude's QA engineer.
- Right, so kind of
combining all these things
from the software engineering abilities
to the computer use abilities
once we put all these pieces together.
- Yep, and I think the computer use
is also gonna really open
up a lot of other avenues
and domains where agents
have been sort of locked out of so far.
- What would be an example of that?
- I think that if you want to have Claude
sort of do work for you in a Google Doc.
- Right now it's,
you know, Claude can write for you
but you're copy and
pasting back and forth.
- But if you have computer use
and you say, Hey Claude, can
you clean up this Google doc?
It can just do it right there for you.
Scrolling around,
clicking, editing the text
and that's just such a nicer experience
than needing to copy and
paste back and forth.
- It's like wherever you are,
Claude can be there with you
if it has with computer use.
- Well I'm very excited to have
Claude write my Google Docs
and respond to all of my comments for me.
- That'd be
a very nice future.
Erik, this has been great.
Thank you so much for the conversation.
- Absolutely, thank you.

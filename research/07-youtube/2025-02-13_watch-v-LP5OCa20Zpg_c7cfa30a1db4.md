---
title: Tips for building AI agents
source: "https://www.youtube.com/watch?v=LP5OCa20Zpg"
published_at: 2025-02-13
captured_at: 2026-08-16
author: Anthropic
source_type: youtube
authority_score: P2
mind: engineering
status: captured
evidence_url: "https://www.youtube.com/watch?v=LP5OCa20Zpg"
catalog_id: c7cfa30a1db4
subtitle_file: LP5OCa20Zpg.en.vtt
---

Kind: captions
Language: en
- I feel like agents for consumers
are like fairly over hyped right now.
- Okay, here we go. Hot take.
- Trying to have a agent
fully book a vacation for you,
almost just as hard as just
going and booking it yourself.
- Take one. Mark.
- Today we're going behind the scenes
on one of our recent blog posts,
Building Effective Agents.
I'm Alex, I lead Claude
Relations here at Anthropic.
I'm Erik, I'm on the
research team at Anthropic.
- I'm Barry, I'm on the Applied AI team.
- I'm gonna kick us off here.
For viewers just jumping in,
what's the quick version of
what an agent actually is?
I mean, there's a
million definitions of it
and why should a developer
or somebody that's
actually building with AI
care about these things?
Erik, maybe we can start with you.
- Sure.
Yeah, so I think something
we explored in the blog post
is that first of all, a lot
of people have been saying
everything is an agent,
referring to almost anything
more than just a single LLM call.
One of the things we tried
to do in the blog post
is really kind of
separate this out of like,
hey, there's workflows,
which is where you have a few
LLM calls chained together.
And really what we think an agent is
is where you're letting the LLM decide
sort of how many times to run.
You're having it continuing to loop
until it's found a resolution.
And that could be, you
know, talking to a customer
for customer support,
that could be iterating on code changes.
But something where like you don't know
how many steps it's
gonna take to complete,
that's really sort of
what we consider an agent.
- Interesting, so in the
definition of an agent,
we are letting the LLM
kind of pick its own fate
and decide what it wants
to do, what actions to take
instead of us predefining
a path for it. Exactly.
- It's more autonomous, whereas a workflow
you can kind of think
of it as like, you know,
yeah, a workflow or sort
of like it's on rails
through a fixed number of steps.
- I see.
So this distinction, I
assume this was the result
of many, many conversations with customers
and working with different teams
and even trying things ourself.
Barry, can you speak more to
maybe what that looks like
as we got to create this divide
between a workflow and an agent?
And what sort of patterns
surprised you the most
as you were going through this?
Honestly, I think all
of this kind of evolved
as like model got better
and like teams got more sophisticated.
We both worked with a large number of
customers who are very sophisticated
and we kind of went
from having a single LLM
to having a lot of LLMs
and like eventually having LLMs
orchestrating themselves.
So, you know, one of the reasons
why we decide to create this distinction
is because we started to see
these two distinct patterns
where you have workflows
that's pre orchestrated by code
and then you also have, you know, agent,
which is like a simpler but
complex in in other sense,
like different shape that
we're starting to see.
Really, I think like as the models
and all of the tools start to get better,
you know, agents are becoming
more and more prevalent
and more and more capable.
And that's why we decided hey,
this is probably a good time for us
to give a formal definition.
- So in practice, if you're a developer
implementing one of these things,
what would that actually
look like in your code
as you're starting to build this?
Like, the differences between,
like maybe we actually go down
to like the prompt level here.
What does an agent
prompt look like or flow
and what does a workflow look like?
- Yeah, so I think a
workflow prompt looks like,
you have one prompt, you
take the output of it,
you feed it into prompt B,
take the output of that,
feed it into prompt C,
and then you're done.
Kind of, there's this straight
line fixed number of steps.
You know exactly what's gonna happen
and maybe you have some
extra code that sort of
checks the intermediate results of these
and make sure they're okay.
But you kind of know
exactly what's gonna happen
in one of these paths.
And each of those prompts
is sort of a very specific prompt,
just sort of taking one input
and transforming it into another output.
For instance, maybe
one of these prompts is
taking in the user question
and categorizing it into
one of five categories
so that then the next prompt
can be more specific for that.
In contrast, an agent
prompt will be sort of
much more open-ended and
usually give the model tools
or multiple things to check and say,
Hey, here's the question,
and you can do web searches or
you can edit these code files
or run code and keep doing
this until you have the answer.
- I see. So there's a few
different use cases there.
That makes sense as we start to arrive
at like these different conclusions.
I'm curious as we've now kind
of covered at a high level
how we're thinking about these,
these workflows and agents
and talking about the blog post.
I want to dive even
further behind the scenes.
Were there any funny stories
Barry, of wild things
that you saw from customers
that were interesting
or just kind of far out there in terms of
how people are starting to actually use
these things in production?
- Yeah, this is actually
from my own experience
like building agents.
I joined like about a month
before the Sonnet v2 refresh
and one of my onboarding
tasks was to run OSWorld,
which was a computer use benchmark.
And for a whole week me
and this other engineer
were just staring at agent trajectories
that were counterintuitive to us
and then well, you know, we weren't sure
why the model was making
the decision it was,
given the instructions
that we would give it.
So we decided we're gonna act like Claude
and, you know, put ourselves
in that environment.
So we would do this really silly thing
where we close our eyes for a whole minute
and then we're like blink
at the screen for a second
and we close our eyes
again and just think,
well, I have to write Python code
to operate in this
environment, what would I do?
And suddenly it made a lot more sense.
And I feel like a lot of agent design
comes down to that.
It's like, there's a lot of
context and a lot of knowledge
that the model maybe does not have
and we have to be empathetic to the model
and we have to make a lot of that clear
in the prompt, in the tool description,
and in the environment.
- I see, so a tip here for
developers is almost to act
as if you are looking through
the lens of the model itself
in terms of like, okay,
what would be the most
applicable instructions here?
How is the model seeing the world,
which is very different than
how we operate as a human,
I guess, with additional context.
Erik, I'm curious if you
have any other stories
that you've seen.
- Yeah, I think actually
my, in a very similar vein,
I think a lot of people
really forget to do this.
And I think maybe the
funniest things I see
is that people will put a lot of effort
into creating these really
beautiful, detailed prompts
and then the tools that
they make to give the model
are sort of these incredibly bare bones,
you know, no documentation,
the parameters are named A and B.
And it's kind of like, oh, an engineer
wouldn't be able to, you
know, work with this.
- Right.
- You know, work with this
as if this was a function
they had to use.
'Cause there's no documentation,
how can you expect Claude
to use this as well?
So kind of it's that lack
of like putting yourself
in the model's shoes.
And I think a lot of people
when they start trying to use
tool use and function calling,
they kind of forget that
they have to prompt as well
and they think about
the model just as this,
you know, a more classical
programming system.
But it is still a model
and you need to be prompt engineering
in the descriptions of
your tools themselves.
- Yeah, I've noticed that.
It's like people forget
that it's all part of the same prompt.
Like, it's all getting
fed into the same prompt
in the context window and
writing a good tool description
influences other parts
of the prompt as well.
So that is one aspect to consider.
Agents is this kind of all
the hype term right now,
a lot of people are talking about it
and there's been plenty
of articles written
and videos made on the subject.
What made you guys think
that now is the right time
to write something ourselves
and talk a little bit more
about the details of agents?
- Sure, yeah.
I think one of the, you know,
most important things for us
just to be able to explain things well.
I think that's a big
part of our motivation,
which is we walk into customer meetings
and everything is referred
to as a different term
even though they share the same shape.
So we thought, you know,
it would be really useful
if we can just have a set of definition
and a set of diagrams
and code to explain these
things to our customers.
And you know, we are getting to the point
where the model is capable
of doing a lot of the agentic workflows
that we're seeing.
And that seems like, you
know, the right time for us
to, you know, have some definitions
or just to make these
conversations easier.
- Yeah, I think for me, I saw
that there was a lot of
excitement around agents,
but also a lot of people
really didn't know
what it meant in practice
and so they were trying to bring agents
to sort of any problem they had,
even when much simpler systems would work.
And so I saw that as one of the reasons
that we should write this as,
guide people about how to do agents
but also where agents are appropriate.
And that you shouldn't go
after a fly with a bazooka.
- I see, I see.
So that was a perfect parlay
into my next question here.
There's a lot of talk about
the potential of agents
and every developer out
there and every startup
and business is trying to think about
how they can build their
own version of an agent
for their company or product.
But you guys are starting to see
what actually works in production.
So we're gonna play a little game here.
I want to know one thing
that's overhyped about agents right now
and also one thing that's underhyped,
just in terms of implementations
or actual uses in production
or potentials here as well.
So Erik, let's start with you first.
- I feel like underhyped
is things that save people time,
even if it's a very small amount of time.
I think a lot of times
if you just look at that on the surface,
it's like, oh, this is something
that takes me a minute,
and even if you can fully
automate it it's only a minute.
Like, what help is that?
But really that changes the dynamics
of now you can do that
thing a hundred times more
than you previously would.
So I think I'm like most
excited about things
that if they were easier
could be really scaled up.
- Yeah, I don't know if this
is necessarily related to hype,
but I think it's really
difficult to calibrate right now,
like where agents are really needed.
I think there's this
intersection that's a sweet spot
for using agent and that's a set of tasks
that's valuable and complex,
but also maybe the cost of error
or cost of monitoring
error is relatively low.
That set of tasks is not
super clear and obvious,
unless, you know, we actually look into,
the existing processes.
I think coding and search
are two pretty canonical examples
where agents are very useful.
Like, take search as example, right?
Like, you know, it's a
really valuable task.
It's very hard to do
deep, iterative search,
but you can always trade off
some precision for recall
and then just get a
little bit more documents
or a little bit more
information than is needed
and filter it down.
So we've seen a lot of success there
with agentic search.
- What does a coding
agent look like right now?
- Coding agents I think are super exciting
because they're verifiable,
at least partially.
You know, code has this great property
that you can write tests for
it and then you edit the code
and either the tests
pass or they don't pass.
Now, that assumes that
you have good unit tests,
which I think, you know,
every engineer in the world
can say like, we don't.
- Yeah.
- But at least it's better
than a lot of things.
You know, there's no
equivalent way to do that
for many other fields.
So this at least gives
a coding agent some way
that it can get more signal
every time it goes through a loop.
So, you know, if every time
it's running the tests again
it's seeing what the
error or the output is,
that makes me think that, you know,
the model can kind of
converge on the right answer
by getting this feedback.
And if you don't have some mechanism
to get feedback as you're iterating,
you're not injecting any more signal,
you're just gonna have noise.
And so there's no reason
without something like this
that an agent will converge
to the right answer.
So what's the biggest blockers then
in terms of improving agentic performance
on coding at the moment?
- Yeah, so I think for coding,
you know, we've seen over the
last year, like on SWE-bench,
results have gone really
from very, very low
to, I think you know, over 50% now,
which is really incredible.
So the models are getting
really good at writing code
to solve these issues.
I feel like I have a slightly
controversial take here
that I think the next limiting factor
is gonna come back to that verification.
That, it's great for these cases
where we do have perfect unit tests
and that's starting to work,
but for the real world cases
we usually don't have
perfect unit tests for them.
And so that's what I'm thinking now,
finding ways that we can verify
and we can add tests for the things
that you really care about
so that the model itself can test this
and know whether it's right or wrong
before it goes back to the human.
Making sure that we can embed
some sort of feedback loop
into the processes itself.
- Exactly.
- The right or wrong.
Okay.
What's the future of
agents look like in 2025?
Barry, we're gonna start with you.
- Yeah, I think that's a
really difficult question.
This is probably not a practical thing,
but one thing I've been
really interested in just
how a multi-agent
environment would look like.
I think I've already shown Erik this,
I built an environment
where a bunch of Claudes
can spin up other Claudes
and play Werewolf together.
And it is a completely-
- What is Werewolf?
- Werewolf is a social deduction game
where all of the players
are trying to figure out
what each other's role is.
It's very similar to Mafia,
it's entirely text-based,
which is great for Claude to play in.
- I see, so we have Claudes,
multiple different Claudes
playing different roles
within this game, all
communicating with each other.
- Yeah, exactly.
And then you, you see a lot
of interesting interaction
in there that you just haven't seen before
and that's something
I'm really excited about
as you know, very similar to how we went
from single LLM to multi-LLM,
I think by the end of the
year we could potentially see
us going from agent to multi-agent.
And there are some I think
interesting research questions
to figure out in that domain.
- In terms of how the agents
interact with each other,
what is this kind of
emergent behavior look like
in that front as you
coordinate between agents
doing different things.
And just whether this is
actually gonna be useful
or better than a single agent
with access to a lot more resources.
- Do we see any multi-agent
approaches right now
that are actually working in production?
- I feel like in production
we haven't even seen a lot
of successful single agents.
- Okay, interesting.
- But, you know,
this is kind of a potential
extension of successful agents
with the, I guess improved capabilities
of the next couple of
generations of models.
Yeah, so this is not advice
that everyone should go explore
voting agent environment.
It's just, I think, you know,
to understand the model's behavior,
this provides us with a better way
to understand model behaviors.
Okay, Erik, what's the
future of agents in 2025?
- Yeah, I feel like in
2025 we're gonna see
a lot of business adoption of agents,
starting to automate a
lot of repetitive tasks
and really scale up a lot of things
that people wanted to do more of before
but were too expensive.
You could now have 10X or 100X
how much you do with these things.
I'm imagining things, you know,
every single pull request
in triggers a coding agent
to come and update all
of your documentation.
Things like that would be
cost-prohibitive to do before.
But once you think of agents
as sort of almost free,
you can start doing these,
you know, adding these bells
and whistles everywhere.
I think maybe something
that's not gonna happen yet,
going back to like what's overhyped?
I feel like agents for consumers
are fairly overhyped right now.
- 'Cause I think that,
we talked about verifiability.
I think that for a lot of consumer tasks
it's almost as much work
to sort of fully specify your preferences
and what the task is as
to just do it yourself,
and it's very expensive to verify.
So trying to have an agent
describing exactly what you
want your vacation to be
and your preferences
is almost just as hard
as just going and booking it yourself.
And it's very high risk.
You don't want the agent to go
actually go book a plane flight
without you first accepting it.
- Is there a matter of maybe context
that we're missing here
too from the models
being able to infer this
information about somebody
without having to explicitly go ask
and learn the preference over time?
- Yeah, so I think that
these things will get there,
but first you need to
build up this context
so that the model already
knows your preferences
in these things and I
think that takes time.
- And we'll need some stepping stones
to get to bigger tasks like
planning a whole vacation.
Okay. Very interesting.
Last question, any advice
that you'd give to a developer
that's exploring this right now
in terms of starting to build
this or just thinking about it
from a general future-proofing perspective
that you can give?
- I feel like my best advice is,
make sure that you have a
way to measure your results.
'Cause I've seen a lot of people will go
and sort of build in a vacuum
without any way to get feedback
about whether their
building is working or not.
And you can end up building a
lot sort of without realizing
that either it's not working
or maybe something much simpler
would've actually done just as good a job.
- Yeah, I think very similarly, you know,
starting as simple as possible
and having that measurable
result as you're, you know,
building more complexity into it.
One thing I've been really
impressed by is just,
I work with some really
resourceful startups
and they can do everything
within one LLM call
and the orchestration around the code,
which will persist even
as the model gets better,
is kind of their niche.
And I always get very happy
when I see one of those
because I think they can reap the benefit
of future capability improvements.
And yeah, I think realistically, you know,
we don't know what use case
will be great for agents
and the landscape's gonna shift,
but it's probably a good time
to start building up some of that muscle
to think in the agent land,
just to understand that
capability a little bit better.
- Yeah, I think I wanna
double-click on something you said
of, being excited for
the models to get better.
I think that if you look at
your startup or your product
and think, oh man, if
the models get smarter,
all of our moat's gonna disappear.
That means you're
building the wrong thing.
Instead you should be building something
so that as the models get smarter,
your product gets better and better.
- Right. That's great advice.
Erik, Barry, thank you guys.
This is Building effective
agents. Thank you.
- Thanks.

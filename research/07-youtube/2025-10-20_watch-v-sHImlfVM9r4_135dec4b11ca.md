---
title: Introducing Claude for Life Sciences
source: "https://www.youtube.com/watch?v=sHImlfVM9r4"
published_at: 2025-10-20
captured_at: 2026-08-16
author: Anthropic
source_type: youtube
authority_score: P2
mind: engineering
status: captured
evidence_url: "https://www.youtube.com/watch?v=sHImlfVM9r4"
catalog_id: 135dec4b11ca
subtitle_file: sHImlfVM9r4.en.vtt
---

Kind: captions
Language: en
- It took us three months, ultimately,
lots of people working
day and night in the lab
to fix the problem.
I posed this problem to Claude.
I said, "Hey, what should
we do to get unstuck?"
And just in one minute,
you know, one response,
Claude actually just
one shotted the answer.
- Hi, I'm Jonah Cool.
I am the Head of Life Sciences
focused on partnerships
and deployment here at Anthropic.
- Hi, I'm Eric Kauderer-Abrams.
I'm the Head of Biology and
Life Sciences here at Anthropic.
I'm focused on research
and product development,
and together we're trying to
teach Claude to be a biologist.
- All right, Eric, let's talk science.
I'm really excited about this
and also excited about
the fact that Anthropic
and, you know, we're
leaning into this space,
and, you know, maybe the place to start
is just thinking about
why the life sciences,
why Claude, and what
Anthropic brings to, you know,
what is already a really big ecosystem,
but one that's moving really fast.
- Yeah, I think that's a
really important question.
So I'll start with why are we
focused on the life sciences?
And this goes right to
the heart of our mission.
I think it's something that a
lot of people may not realize,
but when we talk about the
beneficial use cases of AI
and all the amazing things
that we can do in the world
with the frontier AI
that we're developing,
actually the number one place
that we at Anthropic are
excited about applying it is
within biology and the
life sciences, right?
If you read our foundational material
and, you know, you talk to
people in the hallway here,
that's the primary area
where we're really focused
on delivering the beneficial impact.
For me that's been a super
exciting thing to come in
and plug into is all
of that pent up energy
and excitement to apply everything
that we have to this space.
And then starting to get more
specific in talking about
why Claude, and how is
our approach as Anthropic,
you know, maybe different from
some of the other approaches
that are out there.
I think there are two things
that that come to mind.
You know, Jonah, you and I
have talked a lot about this,
but the first is that we're
interested in building tools
that empower individual scientists
and enhance the experience
of being a scientist,
going about your life, you know,
doing all the work that
you're doing, right?
So we want to give people
the same experience
that software engineers
have had of, you know,
having a brainstorming
partner to work with
and delegate tasks to
throughout the process.
We wanna bring that to
biologists in the lab
and on the computational side.
And so our initial focus is
really about building tools
that make scientists more productive.
It also makes science more fun.
Right, take away some of the
grunt work that, you know,
everyone would rather get out of
and allow you to focus more on
the creative high leverage side.
So that's the first part,
and then the second one is
we're really focused not
just on the really exciting
early stage discovery problems, right?
Molecule design and protein folding,
and these, you know,
incredibly impactful problems
that many people in the
field have focused on.
But we want to address the whole spectrum
from early stage discovery
all the way through
development and translation.
And so for us, that means, you know,
breaking it down into the
whole world of different tasks
that exist in the space.
Everything from, you know,
drafting and reviewing protocols
and debugging them to performing
bioinformatics analyses
and writing up your results in slides
and papers and that
sort of a thing, right?
There's a whole world of tasks
out there that are important,
and we're taking a holistic
view and addressing all of them.
- Yeah, I think it's a
really interesting time
to think about science and
maybe AI more generally.
And, you know, there's this
inclination towards, you know,
what problem will AI solve for me?
But, you know, the way
that I think we're thinking about it,
the way that you just
really nicely described
and the way that in "Machines
of Loving Grace" is,
maybe also thinking through
that like slightly orthogonal
point, which is like,
how do we change how we do science?
And that will then impact,
you know, solving, you know,
structures and molecules
and tissues and imaging
and starting to like
think through that world.
So, you know, with that in
mind, maybe then to transition,
so, you know, we've seen
the power of Claude.
I think both of us have experienced this
and like the delight
and the joy in doing science with Claude
and its current capabilities,
but then also now starting to
think in the research group
that you're leading
and how we advance those capabilities.
And so maybe for a minute we
can just chat a little bit
about how kind of current
capabilities and ecosystems
and maybe even like extended
context through MCPs
and life sciences start
to create this base case
and then your thoughts
on how we extend that
and even like push it further,
and you know, what that starts
to look like and take shape.
- Yeah, totally.
So, you know, we've
talked about this a lot.
I think that, you know,
it's important to crawl,
walk, run in this space.
Right?
There's a lot of things
about doing biology
and having AI, you know,
be useful in science
that are different from
having AI be useful-
- It is the AI space.
So maybe you like to use a
old running analogy, you know,
you start fast,
you pick it up in the
middle and you sprint home.
So very little crawling,
but just, you know,
sprinting and then sprinting faster.
- Sprinting, sprinting faster,
then flying in a rocket ship
is what we're going for here.
But you know,
the very base level is we
need Claude to be conversant
with all of the tools
that scientists are
using every day, right?
And so there's a whole
ecosystem of important tools
and partners out there that we
are integrating with, right?
So we talk about Benchling
on the, you know, experiment,
administration, lab
notebook side of things,
10x Genomics with Cell Ranger, right?
Incredibly important platform for
analyzing single cell experiments.
And then PubMed, for
example, for being able
to query the literature, right?
And so these are just three of a,
three incredibly important partners
in a much larger ecosystem.
And so that base level is we need to
make sure that Claude can
talk to all the major sources
that scientists are using
throughout, you know,
their daily work.
And then I think the next level
is we want to bring Claude
to performing at the level of
a superhuman research
assistant that can assist you
as a scientist throughout all
stages of your project, right?
From the early stage hypothesis generation
when things are more creative,
and you're reviewing the literature
and you're brainstorming,
to the experiment execution phase
where you're drafting protocols
and you're debugging things in the lab,
and even actually running
those experiments in the lab,
to the computational
and data analysis side of things, right?
When you're running your
bioinformatic scripts,
you're doing machine
learning on top of that
or some statistics
and you're presenting
the results to colleagues
or for yourself, right?
And so here, this is where
we've broken down tasks into
all of those areas, right?
And we're figuring out,
"All right, how do we evaluate
how well our models and
are doing those tasks
and how do we, you know,
rapidly improve performance
in all of those areas?"
So we are making a big investment
in doing that right now.
And I think it's also important
to say that we're, you know,
we're not just doing
this generically, right?
Like in some ways,
you can't speak of life sciences
as one monolithic thing, right?
There's all these different
subfields within it.
And we have a particular
sequencing in mind
where we like to think of it as being,
consisting of this core of,
you know, important tasks that are shared
throughout many different fields.
And then within that there
are different subdomains
that are really important, right?
And we want to address all of it,
but we're really focused
on starting with that core,
that's gonna be useful
throughout the whole journey.
- Yeah, I mean, you know,
one thing that I'm really
ecstatic about with our current partners
and you know, folks that
are involved early on here
to build this foundation,
especially with MCPs,
is, you know, you mentioned 10x Genomics,
you mentioned PubMed,
you mentioned groups like Benchling
and then, you know, Sage
Bionetworks, BioRender,
you know, kind of going
back to that last point,
it really demonstrates
and hopefully puts to action
the fact that it's not
just solving a problem,
but you know, in that group
you've got the literature,
you've got instrumentation,
you've got analytical workflows,
you've got the cherry on top
with that like perfect image
or, you know, network
diagram in BioRender.
And I expect that over
the weeks, months to come,
like that whole ecosystem is
just gonna grow exponentially,
and with that, like the power
for more and more scientists.
And I think that's just like
incredibly cool and exciting.
- Yeah, I think that's a great point
because that's the
experience that, you know,
a lot of us have had on
the software side, right?
For me, I've always been on the one hand,
a part of the software world,
the other hand, a part of
this bio world, and you know,
things started on the software
side where you'd give Claude,
you know, these little
snippets of tasks, right?
And over time, those tasks
become longer horizon,
Claude becomes more autonomous, you know,
it can more seamlessly integrate
through the different tools there.
And I think we're right
at that takeoff point
in the life sciences where we're just now
with all of these connections
that we're introducing,
able to unlock that next
stage where, you know,
you don't have to just ask
Claude to go perform an analysis
and then you do some work,
and then you come back
and you make a BioRender figure
and you ask Claude to revise it, right?
We could actually give
Claude a whole, you know,
meaningful chunk of the work
that would take a human
scientist a couple hours to do.
I think that transition is
the really exciting point
in a field where it goes
from being, you know,
a useful kind of utility to actually
a brainstorming partner,
which is what I'm after.
- Yeah, it's just kind of like embedded
in the process.
- A collaborator.
- Yeah.
So we recently released Sonnet 4.5,
a really exciting, super powerful model.
And I think one of the
things that we've seen,
and you know, eager to
hear your perspective
on the research side is just like
seeing how that model
performs in the context
of different areas of science.
And so, you know, what
have you seen maybe in the,
like the evolution and
the power of those models
and maybe some of the early evals
or benchmarks that we've been
seeing in different tasks
that are relevant to scientists.
- So I think there's two
things about Sonnet 4.5
that I'm really excited about
that have enhanced my own work
by a great deal.
The first is that it's our first model
that's undergone extensive
scientific training.
So Sonnet 4.5, you know,
is skilled in many different
domains of science.
And I think one of the exciting things is
that there's a lot there
that generalizes, right?
And so Sonnet 4.5 being
better at math, you know,
has some effect of uplifting
different capabilities in bio,
especially in the computational side.
And so I think it's just really exciting
that it's our first, you know,
scientifically, you know,
really capable model.
And you know, there were some new things
on the training side that
went into making that possible
that we're just leaning into
and accelerating with
all future models here.
And the second thing is its ability
to do long horizon tasks, right?
Consisting of long strings
of different tool calls.
So this is something
that, you know, for anyone
that's done these sorts of
long bioinformatics pipelines
and things like that
is absolutely critical.
And we saw a major jump
up in those capabilities
with Sonnet 4.5, which, you
know, makes it, you know,
uniquely able to start
to do these like really long
bioinformatics workflows.
- Yeah, I think in the analysis workflows
and also thinking about how it applies
to the different surfaces of Claude.
So, you know, a lot of
people think about Claude
and they think, you
know, the chat interface.
But of course I think for many scientists,
maybe some that do, maybe
some that don't realize this,
the power of agentic coding
tools like Claude Code
or other places where that longer context
and all of that power
becomes really interesting
for data analysis, for integration,
for kind of like reasoning
over different types
of knowledge and yeah.
It's an incredible starting point, right?
Where then we can start to build.
- Yeah, it really is, and I
know this is one of the things
that you and I have been
the most excited about,
that Claude Code is amazingly useful
as it is today in biology.
And most people don't realize that, right?
It's called Claude Code,
it's not called Claude Biology, right?
But, you know, underneath the hood there,
there's a really powerful
general purpose agent that
I, in particular, you know,
many people that we've talked
to throughout the community
have started to use in bioinformatics,
even in things like
drafting papers, right?
And in performing literature reviews
and organizing your projects, right?
And so I think that that's
definitely something that
we're gonna be putting
a lot more energy into.
there's those moments,
and as a technologist
and someone that loves
to develop technologies
and apply them to biology,
which is an affinity
that I know we both share,
you know, there are those moments
where you see technologies
or kind of like experience technologies
and you just like really feel them.
And I still have that moment
of like uplift, you know,
remembering the first time
like playing with Claude Code
and making tasks that are either kind of
beyond my technical capabilities,
tractable and manageable,
or the tasks of just, you
know, like workflow running
and execution that are just time intensive
and cumbersome, trivial, right?
I mean, it just like puts those
tools in scientists' hands
in a way that is incredibly powerful.
- It really is.
And you know, you mentioning those moments
where you just viscerally feel, you know,
the new capabilities that are out there,
that reminds me of that moment for me,
that really woke me up for the first time,
and this was actually back
in the Sonnet 3.5 days
that "Wow, these LLMs
and these frontier models
are really relevant
for what we're doing
in the life sciences."
And so for me, that moment was,
at the time I was
running a biotech company
that I had founded, and I had
this idea that I wanted to try
to see, "Hey, if I had
had access to Claude
when I was starting this
company five years ago,
how much time would it have saved us?
And how much heartache
in trying to navigate
some of these really difficult
R&amp;D problems we were trying to solve,
would it have saved us?"
And I'll never forget this
because the very first
huge technical roadblock
that we ran into when
we founded this company,
there was a problem, we
were developing an assay,
you know, trying to
detect in this case COVID.
And it wasn't working.
We were getting inhibited
by the sample matrix
and we couldn't figure it out, right?
And it took us three months, ultimately,
and, you know,
And I posed this problem
to Claude, I said,
"Hey, we're trying to develop this assay,
and we're seeing that the
sample is inhibiting things,
and what should we do to get unstuck?"
one shotted the answer,
and said, "Hey, I think you should add
this much of this chemical,
you know, into the mix."
And, you know, that was a really
eye-opening moment, right?
That here, in conversing
with Claude, you know,
you're kind of talking
to a distilled version
of the totality of, you know,
scientific knowledge, right?
And at the time it was imperfect,
but it's rapidly getting better.
- There's always this tension,
and I think scientists
want perfection, right?
It's something that we all
kind of like strive for
and want that specificity.
But for a lot of the work
that holds science back,
protocol optimization, you know,
and an imperfect but helpful answer
is the sort of thing that we go to,
you know, the most trusted colleagues
where they might say like,
"Eh, I don't know if,
but like, this looks familiar."
Right? Like, I've seen
this problem at some point.
They're those kind of
like sage professors.
They're the like super sharp student,
you know, down the hall.
And again, it's not
looking for perfection,
but it's looking to get unstuck.
It's looking to be helpful.
It's looking to just like keep you moving
and like towards discovery,
which is what we're
all looking for, right?
- Yeah, totally. Totally.
And I think the other area
that really jumped out for me
early on was, you know,
this is relevant later
in the translation phase,
is in the regulatory process.
So I've spent a lot of time
writing regulatory submissions,
going through those processes with FDA,
and you know, Claude is
really capable there.
And I think there's a huge opportunity
both on the industry
side and on the FDA side
to recognize that we have
these tools that can, you know,
speed up the process on both sides
and facilitate consistent
standards across the board.
And I'm really excited
about pursuing that,
and I know people, you know,
across this whole industry are as well.
- Okay. So let's stick
on this for a minute.
You know, within biology, within AI,
maybe even if you take a step back from AI
and think about just like
engineering and technology,
you know, the life sciences,
biology is this, you
know, frequent substrate
where people get really excited
about the idea of biology
or how it's just like one step away
from being like immediately programmable.
So some of those ideas and intuitions
I think we probably agree with,
but I think in many cases,
you know, it's folks
that are maybe more in love
with the idea of biology
as opposed to like really
know what the life sciences,
what regulatory frameworks look like.
You know, let's talk a little
bit more about, you know,
your experience, our collective
experience as scientists,
and kind of like bringing some
of that detailed knowledge
to our partnerships, to
our research efforts,
and, you know, what those
moments have looked like
for you in the past
and how they're maybe like reading onto
priorities or approaches.
- Yeah, I think this is a really important
and also pretty fun topic
to talk about, right?
In some ways it's one of the
oldest tropes in the space
of the computer
scientists, the physicists,
the mathematician, that
kind of waltz into biology,
and have all these romantic notions
and then, you know, spend
their first year in the lab
and come out kind of shellshocked
and, you know, in some ways disillusioned
of all the things that
are possible, right?
where you and I both are coming from,
and the way that we're
doing things here is,
we know what life of the lab is like,
and we want to solve the
real problems that are
the bottlenecks for this field, right?
I will say that that's my own background.
I'm coming more of the
computer science side
and the math side of things
and have picked up bio,
you know, over the years
in being in the lab, and
I'm not disillusioned.
I really believe that
we have the opportunity
to massively uplift the
capabilities of biologists
in doing incredible, impactful research.
And that with the tools
that we have now, you know,
we're finally at that moment
where all these things are possible.
So I remain the same optimism
that I had when I first got into this.
And I think, you know,
all the experience in the lab
has been really clarifying
to help point out, okay,
there are real problems here
that are not pretty and
that require, you know,
lots of grindy work to get
in there and disentangle.
But I think we're now set up
to make a dent in that, so.
But I'd love to hear what you think.
- Yeah, I mean, I totally agree, right?
I mean, I share that optimism.
I do think that there are many people
that don't always understand
like how difficult science is,
but also how important just persistence
and the fact that, you know, research,
and I think this probably
applies, you know,
down the clinical pipeline too.
You know, it's because it's so difficult,
because there's so much
knowledge that needs
to be incorporated in every,
like, step in debugging
and the complexity of biology,
whether it's that protocol optimization
or data analysis,
it's really hard to
hold all that expertise
definitely in one person,
probably not even in one group,
and infrequently in one institution.
And the result of that,
and I think where again,
we provide a really powerful
technology in Claude
and a, you know, research
assistant collaborator,
is it starts to like, bring
more of that fluidity, right?
It lowers the bar for
computational analysis for folks
that may not have that
computer science background.
It brings some molecular biology
and optimization skills for folks
that haven't spent their
whole life, you know, cloning
and doing molecular biology.
And then it also just like helps
make discoveries, you know,
transferable across fields, right?
I mean, I was not trained
as a neuroscientist.
I used to love to go to
neuroscience lectures,
but would then have to like, come back
and either like ask a whole
bunch of naive questions.
But, you know, seeing
optogenetics for the first time,
you know, discovered in
neuroscience took way too long
to get out to cell
biology, to other domains.
And I think the power of Claude,
and Claude as a life scientist
is it starts to like,
address some of those
core problems in biology,
but also just starts
to create that fluidity
and start to break down walls
and some of the parts that
makes science hard, right?
- I totally agree.
And the other thing I wanna mention
when we're talking about our outlook
and our research roadmap
and things like that is,
you know, we focused a lot
on the meat and potatoes
and eat our vegetables of,
you know, all of these
practical tasks, right?
That are really exciting,
but more sort of surface level.
I also wanna call out that
we're seeing an increasing
trend in, you know,
the field focusing on these
bio-foundation models, right?
These models that have
savant-like capabilities
on biological modalities, right?
DNA sequences and protein
sequences and being multimodal
and expression data and
all sorts of things.
And a trend that's really
interesting to watch is seeing,
you know, increasing number
of papers come out over time
that are demonstrating
that these things that
previously looked like you
needed these specialized
bio models for, maybe you don't,
and maybe actually with, you know,
really large frontier
scale models like Claude,
with the right type of training,
we can start to develop
those capabilities.
And so I think we're all
as a field at the beginning
of just sort of working through that,
but I think it's a really,
really exciting trend
to follow and that we'll be
pursuing pretty aggressively.
- Right?
Because I think having these
in these bio-modalities is really powerful
for these specific bio-foundation models,
but to really make that
accessible to people,
you need to be able to interface
it with language, right?
And so I wanted to call that
out as one, interesting.
- Yeah, I mean, it's a
great point that, you know,
as the field progresses here,
and by field here, I mean both,
you know, the field of AI,
but also like many domains
of the life sciences.
And I think we're already
seeing a whole bunch
of really exciting, you know, partners
that are the AI native
startups in the biotech space
that are kind of taking
some of these tools,
as well as large pharma partners.
And the way that the different
pieces come together, right?
So bio-foundation models,
general intelligence models,
specific data sets, you know,
it's gonna be fascinating, right?
And I think a really exciting time,
and maybe this also gets to the
point of partnership, right?
So starting to take those different pieces
and like bringing them together
and how we think about partnerships,
maybe some of the early
learnings or opportunities
or partnerships that have
been front of mind for you,
or kind of a philosophy of
like building this ecosystem.
- Yeah, so the way that
I think about it is
we know what our North Star is.
We want to enable the amazing world
that Dario writes about in
"Machines of Loving Grace"
in which, you know, R&amp;D
throughout the life sciences
is accelerated by at least
an order of magnitude.
We want to make that
happen as soon as possible.
And within that framing,
I think about partnerships
is we need to make sure
that all the right pieces exist, right?
Some of those pieces
we're gonna do ourselves.
Right, a lot on the model training side,
some on the product side as well,
but other pieces, you
know, it makes sense for us
to just find the right partners
and make sure that we're
supporting as much as we can.
And so when I think about the
different types of partners,
there's really important
ecosystem partners, right?
Like I would call out Benchling
is one of those for us
where, you know, I think
they have, you know,
the majority of working,
you know, bio scientists
are using Benchling as
how they engage every day
with kind of managing and
running their experiments
and their data.
And so that's really,
you know, important one
for us to lean into.
And I think there's a
lot of exciting things
that we'll be able to share soon
that we're working on together.
So that's one type of a partner.
Another type is a partner
that we want to work with
in which they're using what we're building
to actually do science,
and, you know, in a way that
wasn't possible before, right?
Whether it's doing more
science per unit time, right?
Getting more impactful
results per unit time
than they could otherwise,
or making a type of discovery
that wasn't possible before it, right?
And so there, you know,
there's a few partnerships
that we're pretty excited about.
I think one that that's worth mentioning
is with the Arc Institute, and I know that
you're thinking a lot
about this as well, so,
would love to hear your thoughts.
- Yeah, I mean, I think the, you know,
the affinity that we both
had towards Anthropic
because of the unique
features of the models,
you know, this like deep thinking,
I don't think it's an
accident actually that
so many scientists
have gravitated towards using Claude just,
you know, naturally, but
then also Dario's vision,
and I think the vision that
we very much believe in,
which is, you know, our goal
is to accelerate, right?
It's 100 years of science
that is possible in 10,
and that's bold, it's ambitious,
but also I think the
more you think about it
and the more you think about
what holds science back,
it's achievable.
And so I agree, you know,
within the life sciences
and biology, I think the
other thing that's unique
is that it's an ecosystem
that is incredibly continuous
and fluid, right?
The student that is in a lab
and finishing their thesis one day
is the founder of an AI native
startup, you know, the next,
that is then like acquired or working with
or advancing, you know,
major pipelines at, you know,
AI forward pharma companies like Lilly.
And, you know, that fluidity
and thinking about kind of that entire
partnership and that ecosystem,
I think is that that's
the beneficial deployment.
It's all of science, and achieving that.
The thing that I'm really excited about,
and maybe one feature
that you didn't touch on,
is our AI for Science program.
And this is really looking to put tools
and Claude into the hands of scientists
that have a bold idea or a big project,
and they think that Claude can, you know,
be useful to solving that.
And I think it's a great way to, you know,
power early stage discovery research.
It's a great way for us to kind
of lean into those partners
and work with them closely
and learn from them
and like start to just, you know,
keep drawing the aperture open
and understanding like
in these early days,
you know, what is working really well,
and you know, frankly,
equally important, like,
what isn't working well.
And you know, I think we
both believe in the power,
but also believe in the
current imperfection.
And so that opportunity to,
you know, work with scientists,
accelerate their research, judge
success based on, you know,
what their success is, their discovery,
their acceleration, their time,
and start to see where
we're doing pretty well,
and maybe some areas
where we just need to
be doing a lot better.
- Yeah, I'm really excited about that too.
And I think that's such
an important point, right?
Like in this conversation
we've been emphasizing a lot
breaking the problem down
into all these pieces
that we're gonna solve independently,
but the most important part
is when we put it all back together.
- And scientists are actually
using these things, you know,
how's it going and what
are we doing, right?
And so I think the AI for
Science program is critical
for us to get that feedback
and be closing the loop with people
that are using these things
every day in the lab.
And so I am super excited about that.
One other point that I think
is really important to make
that, you know, speaks to why Anthropic,
and why the experience of
doing this within Anthropic
is so exciting, it's such a perfect fit,
is that as we're talking
about accelerating
and enhancing capabilities, right?
The other side of that is safety
and the tremendous
responsibility that we all have
to making sure
that we are improving
the model's capabilities
and releasing, you know,
increasingly impactful products
in a way that is responsible
and aligned with our
responsible scaling policy
and best practices in the
biosecurity community.
It's something I care deeply about.
I've worked in biosecurity for years,
and I think that, you
know, at most companies,
right, there would be some
tension between the impact
and the commercial aims
of making these models
better in biology, right?
And the safety
and responsibility side of, you know,
slowing down when we need to,
and making sure that we're being careful
and have all the right
safeguards in place.
But at Anthropic, we don't
have that tension, right?
That's our DNA as a company.
I think that's so valuable here.
It's also really familiar, you know,
to everyone in the life sciences, right?
For people that are
developing therapeutics
and medical technologies, right?
On the one hand you have
your product development arm
and your commercial goals,
and on the other hand,
you have a quality
management system, right?
Which is a set of procedures
and practices that
govern everything you do
in order to make sure that
you're doing so safely, right?
And so I think it's just
such a natural fit, you know,
our approach here to AI of making sure
that developing really
powerful AI goes well,
and is done safely,
and what needs to happen in
the life sciences, right?
And so that's something
that I'm personally
really excited about,
that I also think is a big part of
who we are as a partner of this field.
- Right, yeah. It's an assumption, right?
Like we have to do that.
We owe it to ourselves,
we owe it to scientists,
we owe it to the world
to take those sorts of
questions really seriously.
Yeah, and I think the other
thing that I think about a lot is,
like at our core, at our DNA,
we're a research organization.
I don't think you can say that about
all other AI companies, you
know, frontier labs, et cetera.
But I think being a research organization
allows us to engage
with researchers, labs,
other research organizations,
in a way that really creates
kind of a shared sense
of like ownership and goals
and working together, right?
Like we want to advance the technologies
and see them put to, you know,
the full purpose, and power,
and are really invested
in seeing that forward.
- Yeah, I think we're really lucky
that that's the case.
And you know, I feel that very viscerally
that so many people on our founding team
and our leadership team
and just throughout all levels
and teams in the organization
are scientists, right?
Many by training, many by
nature and disposition.
And, you know, I think that that,
you know, you can feel
that sort of, you know,
in all the work that we do,
and it makes it, you know,
so natural to just go out
and get to work with other
scientists and all these things.
- And some, you know,
it's a little bit like,
you know, the monkeys are
running the zoo, right?
Where we have people that are
so passionate about science
driving the ship, and I
think that it means that
we get to have a lot of fun.
But I think it also, it's a lot of fun,
but also that appreciation
for core questions like safety
and understanding what the power is
and also core, you know,
questions about like
what are the right problems to solve?
And, you know, an appreciation
for what makes science hard,
what slows science down, you know,
if we need to make 100
years of progress in 10,
you know, what does
that actually look like?
And, you know, you can draw back the veil
of science and, you know,
there are some of those things
of just understanding
the literature, right?
Like you could spend all day, every day.
As a matter of fact, I
think a lot of scientists
would probably love to
spend all day, every day
reading the literature,
but like even then you'd
get through, you know,
some small, tiny fraction
of what was published
or pre-printed at any given moment.
So it's just impossible to keep up. Right?
But Claude can keep up.
- Yeah, yeah.
Okay, so let's talk a little
bit maybe here at the end
about, you know, the
future of life science work
and, you know, we've talked about
bioinformatics and coding,
we've talked about some,
you know, clinical work
and different work that has
been like demonstrated by
some early partners.
And then maybe also just ways
that we're thinking about
like building this up
and continuing to
develop new partnerships,
push the models towards
greater capabilities.
Where do you go when you start
to think about the future?
- Yeah, so when we started
to think about the future,
you know, I think first
we need to make sure that
Claude has all of the
foundational knowledge
that any scientist in the
bio world would have, right?
So things like understanding
protein structural biology,
right?
And being able to look at
a molecule from organic chemistry
and understand its structure
and function and things like that, right?
And so once you establish that base,
then I think there's some
really exciting places
that we can go after that.
Where one of the ones that I really like
to talk about and that I think is critical
is Claude actually learning
to execute experiments in the lab, right?
I think in order to get
to this world where,
you know, we're all going,
that needs to happen.
And again, this is a problem
that for so long, you know,
we've been making a lot of progress,
maybe not as much as some
had hoped for, right,
in terms of this vision of
automating the tedious work
of life in the lab.
But I believe that it's possible now.
And I think that that's
a really important area
where we have to drill in and focus on.
just pause for a moment
as to what life will be
like when we get there.
It'll be incredible, right?
We'll be able to go from, you know,
talking to Claude about an experiment,
to designing an experimental
plan with Claude,
to having Claude draft the protocols,
and, right, you can go
back and forth on them,
and then when you're ready, you could say,
"Okay, now go run those experiments
and I'll review the data,
right, in the morning."
And so I think that's
critical for closing the loop
and enabling that acceleration
that we're talking about.
And the other thing
that I think is a really important theme
for our future research is in biology,
as with any domain in science,
to learn directly from real
data from nature, right?
And so, on the one hand, we
do a lot of model training
and learning on annotations
that are created by humans
and other data sets
that are either curated or
created by humans, right?
But there is an opportunity
here to really do
sort of lab in the loop,
active learning from high
throughput bio measurements.
And the other reason why
bio's such a good fit for that
is we really, you know, are
every year on a scaling law
of the number of experiments, right?
Per unit that we can do, right?
In terms of the throughput
of these systems.
So those are two themes that
I'm increasingly excited about,
where, you know,
when you start thinking about
how do we move beyond human capabilities
in these tasks, right?
At some point we're going to saturate
learning from human experts.
The answer is to get
the data from the lab.
- Yeah, I think this is a great theme.
And the other thing that
maybe I would point to
is I think there's still
this huge overhang,
if you will, in terms of like
current capabilities and use,
and one of the things
that sticks out to me
is like starting to get
Claude in the classroom
in basic training, like really, you know,
kind of implemented in a
deep way such that, you know,
many scientists are using Claude,
and also that experience
and the product, you know,
starts to have this very
cohesive feel where Claude is
that virtual assistant
and that virtual scientist
that is helping not answer our problem,
but, you know, answer a
scientist, answer any problem.
All right, Eric, this has been awesome.
I mean, it's always fun to talk science.
Sounds like we've got a lot of work to do.
So thanks for taking the time
and really looking forward to the future
of Claude, life sciences, and
pushing towards the frontier.
- Yeah, thank you Jonah.
This has been a lot of fun
and we're just getting started.
- We are.

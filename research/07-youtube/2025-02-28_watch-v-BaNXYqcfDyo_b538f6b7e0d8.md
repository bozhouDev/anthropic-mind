---
title: Defending against AI jailbreaks
source: "https://www.youtube.com/watch?v=BaNXYqcfDyo"
published_at: 2025-02-28
captured_at: 2026-08-16
author: Anthropic
source_type: youtube
authority_score: P2
mind: engineering
status: captured
evidence_url: "https://www.youtube.com/watch?v=BaNXYqcfDyo"
catalog_id: b538f6b7e0d8
subtitle_file: BaNXYqcfDyo.en.vtt
---

Kind: captions
Language: en
- Hello everyone.
My name is Mrinank.
Yeah, and I'm really delighted to be here
with some of my colleagues at Anthropic.
- Hi, I'm Jerry.
I'm on our safeguards research team
and I've been at Anthropic
for about eight months.
- Hi, I am Ethan.
I've been at Anthropic
for two and a half years
and I'm leading our efforts on AI control,
developing various
different monitoring methods
for various different AI risks
including aerosol robustness.
And I was a part of the
Safeguards research team as well before.
- Hi, I'm Meg.
I've been at Anthropic for
about a year and a half now,
and on the Alignment Science
team which has been great.
- Great, so yeah and we're
just gonna be talking about
constitutional classifiers
and that's our new approach
to really try to mitigate jailbreaks.
So yeah, how would we define a jailbreak?
- Yeah, I mean I think to me a jailbreak
is kind of some way in
which something bypass
the safeguards that we
include in our models
and try to get harmful
information out of it.
- Yeah, so there are these techniques
that do anything now jailbreak,
it's kind similar people with
jailbreak their iPhone
and try to get around
all the safeguards there.
But the thing is that with iPhones
and others stuff this,
jailbreaks aren't really
a thing that people,
that maybe aren't that dangerous,
not something that we
care about that much.
So yeah, what is it that makes,
yeah, why should we care about
these job breaks in the first place?
- I mean I think one of the
main reasons is for models,
future models which have greater risks.
So yeah, I think people are
pretty carefully monitoring
people at different companies
and the academic community is
if slash when models
will be able to help with
weapon development or
large scale cyber crime
or various different risks
that are greater than
what we've seen before.
Also mass persuasion, things like that.
And I think once models become
really effective at some of those
and are a significant uplift over say
using Google search or
general internet resources
to do some of those things,
I think then it then yeah I
guess being able to use models
to help with those kinds of things will be
potentially speed up
bad actors quite a lot.
So I think a lot of this is in preparation
for next generation models
or next next generation models.
- Yeah, great and then I'm
also curious what the story
of the work is and sort of
why we set out to do this
in the first place and the RSP.
- Yeah, I guess Anthropic really cares
about safety a great deal
and we have the RSP which is
the responsible scaling philosophy,
which is really trying to outline
conditions under which we're
happy to release models
and make sure we have
different safeguards in place.
And a while ago we committed to a very,
a difficult standard
for jailbreak in the RSP
for what we call ASL-3 models,
which are basically models which have
maybe some of these dangerous capabilities
being able to build dangerous weapons.
And our team was kind of mandated with
trying to actually solve jailbreaks
for this kind of level of model.
So yeah, I guess the
motivation for the work
is actually try and satisfy
the things in the RSP
such that we can feel we build
future models safely
and can actually deploy
them with some sort of
progression towards safety
or making some progress towards that.
Yeah, so I think the
classifiers a definitely
a good step in that direction.
- Yeah, so there are lots of
different types of jailbreaks
that are out there
and something that we've
really did in our work
is we focused on on universal job breaks.
So yeah, why is this something
that we should care about?
And what does that mean?
Why is it important?
- Yeah, I mean I think the reason why,
I'm particularly concerned
about universal jailbreaks
is just because of the
uplift that it would give
kind of a non-expert.
And the way I kind of
think about this is that
if some random person on the internet
is trying to do something bad,
they may not actually have
that much jailbreaking
experience themselves.
And so the thing they might just do
is just go online and see
"Oh what are some existing
jailbreaks that I can use?
What's a template where I can just put in
my harmful question and
just get an answer."
And I think in that case,
you're very concerned about these kind of
strategies where anyone could
just put in any question
and it gets the model to
bypass all of the safeguards.
And I think that's part
particularly concerning
at the level of model capabilities
that we're concerned about.
- So how exactly would you to define
a universal jailbreak?
if you're telling someone on the street,
what does a universal jailbreak mean?
How would you know if your
jailbreak is universal?
- Yeah, I guess there's a little bit
of ambiguity there,
but I think the kind of definition
that we are going for is some
kind of prompting strategy.
It could be automated,
but just a singular strategy
that's very easily replaceable
with any wide variety
of harmful questions.
And that consistently gets a lot of detail
from the model and bypasses
the model safeguards.
- And I think one way of
quantifying the universal jailbreak
is that it actually does speed up
a person quite a lot because
instead of having to jailbreak
every specific query,
they can just use one jailbreak
for all of the queries
which actually is a lot faster.
So I guess one idea is ,
if the model, if there's
some counterfactual way of
doing things that's much
easier than using the model,
there's no point in using the model.
So not having universal jailbreaks
might mean that they try other strategies
which might be worse or something this.
- Yeah.
- One thing I would maybe add is that,
the difference between
a universal jailbreak
and non universal ones is ,
for non universal ones you might need to,
for every harmful question
you want to answer,
you would need to jailbreak
the model in particular
for that particular question,
then you get a new question,
a new, yeah, new.
Your question in the process of developing
your new weapon or whatever
and then you need to
jailbreak the model again.
I think basically that entire process
if you need to do that
hundreds or thousands of times
is just very costly.
Whereas if you just need to
upfront find one strategy
for jailbreaking your
model a single prompt
where you can just swap in a new question,
that makes it so that it's,
yeah, the amount of total
effort for jailbreaking
is much lower.
So that to me is one of
the primary motivations
for focusing on universal attacks.
- Yeah, and I'll just give an example here
in a way that I think about it.
So let's say I wanna make a cake
and I am not able to make a cake
because I've never baked in my life,
I don't know anything, my ingredients,
I don't know how things work.
So how could a model be able to help me
do something I can't do otherwise?
So if I need to make a cake,
I'm gonna need to ask a
bunch of different queries.
That's one thing.
it's actually,
put something in the oven,
I need to know if the
temperature is right,
the smells right, take it out,
how I would check, figure
out all the ingredients.
So one thing I think
that's really important
in the universal jailbreak
sort of definition,
is that sort of you're very
confident that the information
you're getting out the model
is actually really helpful
for the thing that you care about.
So it's kind of different.
There's sort of some techniques
that get a little bit of information,
or they get some information,
but it's sort of mixed in
with a lot of the other stuff.
But for these sort of scenarios
where what's happening is an
actor that can't do a task
that requires a lot of expertise,
we're worried about them
being able to do the task.
We think that they all need to have access
through the sort of the
of universal jailbreak.
They'll need need to be
able to ask many queries
and get really reliable information
and they should just know,
oh this is the correct instruction,
this is the right thing to do.
- I think an example of
a non universal jailbreak
that someone on the team,
I think Jesse Mu found was,
I think he was jailbreaking it for,
asking the model how to make,
asking Claude how to make meth
and he found some jailbreaks where
he puts the model in a scenario
where it's role-playing as if
it's part of "Breaking Bad"
the the TV show where they make meth
and then asks the model the
question how do I make meth?
That kind of jailbreak,
you can imagine how
that would be effective
for that specific kind of question
things related to meth,
but is not going to generalize for things
related to cyber crime.
But on the other hand there's
some other jailbreaks which,
the do anything now jailbreak,
which gets the model to do anything
by getting it to talk in a certain mode
or role play in general
for arbitrary questions
and that would be what we would
call a universal jailbreak.
There's also other
strategies people have used
to make these using language models
to automatically find
different jailbreaks,
that would be a more
kind of dynamic approach
that might be able to
discover these on the fly.
But if you have a single process
for generating a jailbreak
for a new question,
that would also count as universal.
- So yeah and just maybe an
even more basic question,
is why does someone need
to jailbreak the model
in the first place?
You know, what does that even mean?
- Yeah, I mean I think
we've done a lot of work
such as our constitutional AI work
on getting Claude to have
this kind of characteristics
where it doesn't actually try
to give harmful information
if it thinks the user
might have some bad
intent or something that.
And so for a lot of
these harmful questions,
if you just ask the question itself,
it's very obvious that
this is bad question
users trying to make some
weapons of mass destruction.
It's very clearly bad
and we've trained Claude to
not answer those questions.
And so the jailbreak is needed
to actually get around those safeguards
in order to get Claude to
actually answer the question.
- Another thing that's relevant for the
homelessness training question is that,
I guess there's many different ways
in which people could present
jailbreaks to the model,
and there's also many different tasks
that the model needs to be able to do
in its every kind of
everyday life so to speak.
And I think having an extra set
of systems that are specifically
trying to guard against jailbreaks
can really help have , I don't know,
some kind of Swiss cheese sort of method
of trying to block harmful things
via many different
layers or something this.
- You say more about what the,
this , we talk about Swiss
cheese a lot on the propane.
- It's true.
- This is not as well known everywhere,
so yeah, what does that mean.
- I guess, yeah.
So I guess the idea of
the Swiss cheese model
for protecting against things is that,
maybe if you have only one system
for preventing harmful
things from happening,
there may be some specific
problem with the system
that people can exploit
and get through every time.
But then if you add kind of , yeah,
kind of a layer of Swiss cheese
which has a hole in a very specific place,
maybe the rest of the cheese blocks
all of the harmful attempts,
but there's a specific hole.
But if you add another
layer of Swiss cheese,
the hole might not be
in the same position.
So if you have two layers of Swiss cheese,
it's actually much harder
to get through things
even though they both may have holes.
- Yeah, so what are these layers of cheese
for our method,
we'd be talking about
constitutional classifiers.
So yeah, what are the different
sort of layers of defense
that we're going for here?
- Yeah, I mean the first layer
would kind of be our input classifier,
and input classifier here is looking at
basically the entire conversation
that the user passes into the model
and so that's the first layer.
And then the second layer is,
if it gets past that input classifier,
Claude itself, which is the model
that we're trying to guard,
can actually refuse to
answer the question.
And then that's kind of another layer
of Claude saying, "Okay,
maybe this question's not so good,
maybe I shouldn't answer it."
And then finally we have
this output classifier
which kind of looks at what
is outputting in real time
and then if it ever sees something
that seems it's dangerous
or seems it's against some value
that we're trying to block,
then in that case it can also choose
to stop the Claude's output
and block the response.
- And how do these classifiers,
what are they looking for?
And how are we specifying
what to look for?
- So I guess in our paper
we call them constitutional classifiers
because we have this kind of
natural language set of rules
and this is some set of rules
where we can specify
some categories of topics
which are not okay to talk about.
I guess an example could be ,
creating weapons of mass
destruction, clearly bad,
and we can specify,
let's not have Claude tell
the user how to make that.
And then we can also specify
some examples of harmless stuff
that Claude should be
allowed to talk about.
And then basically we
train our classifiers
to classify whether
conversations or outputs
are related to these kind of harmful
or harmless categories.
And then that allows us to make a decision
on whether to block it.
- And crucially ,
I guess the input classify
and output classify
are kind of doing two different jobs.
Going back to the Swiss cheese analogy,
we hope that the holes of the Swiss cheese
are in different places,
specifically for the input
and output classifiers.
So I guess the input
classify is kind of doing
the really naive thing that you'd expect.
it really looks at the user prompt
and tries to work out whether there's
anything harmful going on.
But crucially, one of the reasons
that you might need an output classify
as well as input classify,
is that people are trying
really hard to jailbreak
the model and the input
classify in the prompt.
And if you have a totally
separate output classify
which is only looking at the output,
that only ends up looking at stuff that
the model itself has produced.
So it's kind of somewhat decorrelated
from what the user put in.
So two parts of the system
are looking at things
directly that the user put in,
but we also have this
kind of third held out
part of the system that the user actually
doesn't get to touch directly,
which makes it a lot harder to kind of
completely jail break the system.
And although the input classify and Claude
are doing a lot of the work,
that would classify is doing,
I don't know, is doing
some important thing
as kind of the last crucial component
for really driving down
harmful, harmless rates.
- So this is true and
it makes a lot of sense,
but most people aren't
using Claude for this.
Most of the time that people ask queries,
they're just doing
something completely great,
so benign, legitimate,
a really beneficial application.
So we could have guards
that just block everything
that would be completely useless.
So yeah, how are we making
sure that this sort of,
we're not overzealous there.
- I mean I think we really want to,
part of why I think we're
designing these techniques
is to get, allow as much
useful content to be,
and useful work to be done by the models.
the better techniques we have
for blocking exactly precisely
just the really harmful content,
the better we can not have false positives
for users who are using models
for really good applications.
Yeah, I think the classify approach
make some progress there
and might be better than other approaches
directly training the model to refuse,
and so yeah, I mean I think hopefully
this leads us to allow
users to talk with Claude
about lots of CBR and related topics
that are safe to talk about.
And so yeah, I think
our hope definitely is
or , my hope is is to allow
for a lot of those applications
to thrive while just narrowly blocking out
the things that we think
we believe are dangerous.
- Yeah, I guess crucially also,
I think we often make the joke that
if we had just a rock as a model,
that would be extremely harmless
and that it would not in fact
answer any harmful queries,
but unfortunately would
be not very useful.
So I think making sure that we don't block
harmless queries is actually a thing
that is actually quite important
and also actually quite difficult.
- Yeah, and men you mentioned before
kind of solving job breaks,
so making progress on
this problem robustness.
how would you even define that
or what does that actually mean?
- Yeah, I guess this is a
very difficult question.
I guess it involves a
bunch of different layers.
firstly, there's some
idea of threat modeling.
you have to have some idea of
what it means for something to be harmful.
The Frontier Red Team has
done some amount of work
in trying to specify
what things we're actually worried about.
This is somewhat hard
because as Ethan was talking about,
we're talking about a
lot about future models
and potential future model capabilities
which we might be really worried about.
So I think part of it is mapping out
what might be harmful,
but we might need to
address so threat modeling,
what is actually harmful.
Then there's the job of
actually measuring harmful things.
So that's a lot about,
I guess we're using a constitution
to a kind of define the threat model
and then having models
generate various synthetic data
to try and kind of enumerate
various humble things that could happen.
So measuring a true
positive rate on the data,
but then there's also trying to make sure
that we don't refuse too much
on real data from Claude AI
and make sure that we actually can,
I don't know, be as helpful as possible
while still being safe.
- So what actually is the constitution?
You know, these are
constitutional classifiers,
we're talking about a constitution.
What does that mean?
- Yeah, I mean the constitution here
just kind of means some
enumeration of categories
of requests and conversations
that we kind of deem
harmful versus not harmful.
And so examples here could just be ,
yeah, questions on how to make
weapons of mass destruction
or trying to source ingredients
for making weapons of mass destruction.
And then we basically just enumerate
some of these categories,
and then we also specify some categories
of harmless stuff,
I don't know, writing poems
or writing code for normal use cases.
And then we can just kind of specify these
and then we, as Meg said,
we generate a bunch of synthetic data
that gives more specific cases of those.
- What do you mean by synthetic data?
- Yeah, so here in synthetic data,
we kind of mean that we start from these
broad categories of user requests
and then we have Claude actually kind of
branch out and think about
all the specific requests
that might be examples
of this kind of broader category.
And so yeah, the category
might be something ,
sourcing materials to build
weapons and mass destruction
and then sub requests there might be ,
oh, going what specific
stores might I go to?
Or , are these specific
materials accessible
at I don't know, in X state?
And so we have this process
for automatically doing this
and that allows us to kind of generate
a huge amount of synthetic data
from just a small amount of categories.
- Yeah, and I think something
that I find really cool
about the methods is that,
it is just based on natural language.
We were talking about
threat modeling before
and threat modeling, at
least in my experience,
in my experience working
with with Frontier Red Team,
is that threat modeling is really hard.
There's a lot of people using Claudes.
It's really hard to ,
what are all the possible
things that that could happen?
And we're gonna learn new things
as we have monitoring
and as we always learn new threats
or new things that could happen.
And yeah, something that I find really
exciting about the method is that,
basically if you wanna
change the constitution,
if you wanna change what is being blocked
because you've learned something new,
maybe there's something
has come out on the news
or there's some
intelligence or monitoring.
The only thing that
you actually need to do
is you just rewrite the constitution.
And the sort of the standard
approach of classifiers is,
you ask humans to get a lot of data.
So something could happen is that,
say we're really focusing on one category
one particular way of maybe cyber misuse,
but we later realized that,
oh actually this thing
which is much more dangerous
or something that we've
just learned something new.
If someone's informed us.
Something that I'm really excited about
is that this is a way that we,
I think we can get good robustness,
but we can maintain our flexibility
and really maintain our ability to
respond to novel threats
and adapt to what's actually happening.
'Cause yeah, I feel this is just
the lesson that we learn again, again
if you don't have flexibility,
it's sort of gonna be a problem
and it's gonna sort of limit us.
- I actually do wanna make a quick point
of the flexibility thing which is that,
I think our approach is not just flexible
and kind of switching general topics.
For example, if you
wanted to go between cyber
and , I don't know,
weapons and mass destruction or something,
but I think it's also
a lot more fine grained than that,
in that during this project we saw that,
there are some requests
that our early classifiers
were always very suspicious of,
but they're actually benign.
And what we could do is
we could actually just
modify the constitution,
add one sentence that says,
oh, these types of requests are okay.
And then when we retrain the classifiers
on that new data,
the classifiers would no longer
flag those benign prompts.
And so I think that allows you a lot of
fine grain control
over what exactly your
classifiers are trying to flag.
Especially if you see
a lot of over refusals
or problems with missing stuff.
- Yeah, I mean this might
also be a good place
to give a shout out to,
we had a paper earlier on rapid response
where we kind of leveraged a similar idea
to improve the safeguards around models
and I think basically,
one nice feature about
using synthetic data is
if you notice not even just
a new category of jailbreak,
but just a new kind of
jailbreak that maybe applies.
Let's say we notice a
new universal jailbreak,
the do anything now prompt,
we can take that, use an LLM
to generate variance of that
and then throw that into the data mix.
And I think my understanding is this
was really helpful for us in developing
the classifiers to the level
of robustness that we got.
If someone reports a new
jailbreak or vulnerability,
then we can use that to really quickly
update the classifiers by using
some synthetic data generation pipeline
and that really will
minimize the fraction of time
by at which there's an
outstanding jailbreak
which can just make it
so that the models are ,
vulnerable for as as small
period of time as possible.
- Yeah, it's the common
wisdom I suppose that,
not perfectly solving
securities basically impossible.
There is no perfectly secure system
known to humanity.
So I guess we need the flexibility both.
For this , "Oh, we're
blocking the wrong thing."
Or, "We're blocking benign users.
But when people do find things
that get through the system,
we wanna be able to fix
those really quickly.
- Yeah, I think part of our
approach here is that we've
kind of modeled jailbreaks in a way that
it's very easy for us to add
examples of new jailbreaks
into our kind of training pipeline.
And so if new jailbreaks are discovered,
it's quite easy for us to
just generate more examples
of those jailbreaks and then train on them
and then hopefully those classifiers
will be more robust too.
- Yeah, I think one
other thing I would add
that's nice about classifiers,
is that they're decoupled from the actual
text generation model.
And so if you,
I think often it can be
very difficult to update
the text generation model
that if you train it to
refuse in one domain,
maybe that generalizes in non-obvious ways
to behavior in other domains
or refusal behavior in general.
I think we definitely ran
into some difficulties
doing preliminary work on that.
But I think with the
classifiers you can just
keep the text generation the same
and you know it's identical
to previously deployed model.
I think that gives
customers a lot of assurance
that there are no major changes happening
in general to the model.
The kinds of text outputs you're getting
and the only changes being made
is just the block or no block decision,
which you can iterate on
separately from the model.
So I think that also makes
the rapid redeployment
way easier than we would
otherwise be able to do.
- So how did we come
up with this approach?
- That's a great question.
I feel we spent a lot of
time thinking about it.
I think classify as stood out.
I think for the reasons that
we've just been talking about
the extremely flexible,
can be easily updated to respond
to various novel threats.
Yeah, I think threat
modeling is really hard.
So having a thing that's
super flexible is great.
It's lightweight, it doesn't
increase inference cost
as much as, I guess we
can kind of distill down
something that's somewhat more complicated
constitutional set of rules
into a somewhat small thing.
And yeah, I think that all these things
make classify as kind of a nice way
of iterating really fast
on the kinds of things that
you're hoping to achieve.
And then I guess we tried it
and it seemed it was
working so we kept going.
- Yeah, I think this was really due
to the responsible scaling
policy that Anthropic had
and yeah, I mean I think
we would've done other safety research
if not for the responsible scaling policy.
- What is the responsible scale policy?
- So yeah, responsible
scaling policy is basically
Anthropics plan for how to ensure
that our deployments are safe
and basically it outlines
different red lines
for capability thresholds
at which there's basically a new risk
that kind of comes online
with more capable models.
Let's say models are capable of developing
a very dangerous chemical weapon.
The associate mitigation in the RSP
is get above some sufficient level
of robustness to jailbreaks
so that the model is
not actually in practice
with the mitigation sufficiently helpful
to an adversary who wants to do that.
So yeah, I think in the original RSP,
there is basically this commitment to,
once models got to sufficient
level of capability
at assisting with potentially
proliferating knowledge
about known weapons of mass destruction,
that we would then have the ability to...
the wording was vague but basically,
successfully pass Red Teaming.
the RSP was already written,
the company committed to this publicly
and Jared Kaplan who's
Head of Research Anthropic
came to us and other people came to us and
raised this line to us and we're ,
"Hey, you guys should try
to solve aerosol robustness.
- We memorized the line first.
- We memorized the
line, we printed it out,
we framed it and put it on the
desk that we were working in.
Yeah, and then I think that was really...
I think that really thinking
about that line in the RSP
basically made us really
reflect on our life choices
about what research we were doing,
both in terms of should we
work on robustness or not?
Yeah, in the sense of ,
it really made it clear ,
okay, there's significant
harm that could come online
in the next generation or two of models
if we don't solve this problem.
So the urgency is higher
than other problems
we might wanna solve.
And then also in terms of
what specific approaches
we would take I think.
Initially when we were ,
oh, we should maybe do
some robustness research.
I think the general mode
that I had been in research
and a lot of other researchers in general,
is just , okay, let's
just take some interesting
useful research problems to solve here,
explore some questions, write some papers.
And I think that's the thing
that a lot of the people
on the team know how to do well
and we sort of explored a bunch of
maybe more salient approaches.
- I think there were so many things
that are interesting here for me.
One thing was , right when this started,
I had just finished my PhD,
or it was kinda a bound the
time I was finishing my PhD
and this classifiers thing.
This is Anthropic slogan
and the Anthropic slogan is ,
do the dumb thing that works.
And I kind of think this type of research,
it's often the type of thing
that maybe isn't that shiny
or that kind of interesting
for researchers.
And I remember, I think
without the RSP being okay,
really pragmatically if we care about
these risks and we think they're real,
what is the way to get there?
And kind of setting aside this ,
oh, what's kinda more
interesting or shiny,
is what is the way we can
actually make this safe.
In some sense our job is,
we're genuinely thinking ,
wow, this isn't happening now,
these are future systems.
So I'm just , what has that been
for each of you and sort of individually,
kinda working at Anthropic
and sort of being there
in the midst of all this?
- Yeah, I think they take the safety risks
of future models very seriously.
I think there's very real risks.
There's obviously these misuse risks
that you've been
mentioning with CBRN risks
which are chemical,
radiological, biological, nuclear risks.
But there's also very
real misalignment risks
and I think it's really hard to deal with.
I think one of the things that I find good
is that I do think we are as as a team,
very committed to actually trying to
solve really solve the problems.
And I think doing the classifiers project
was some evidence in favor of ,
we really, really care about
actually solving these problems
and we actually want to
find an empirical solution
to doing the things rather than ,
as kind of you were alluding to
just doing research that looks good,
but doesn't actually
accomplish a thing in practice.
I think we spent a lot
of time doing very...
I didn't know,
(both laughing)
I wasn't really aiming
to get a paper out of it,
but I think we actually
managed to accomplish something
that was slightly more real,
which I think is good
and I feel this is just,
this feels one step forward,
but there's a lot a long way to go for me.
- I mean I guess I'm a
slightly more optimistic,
I think there risks are definitely real,
but I feel we're making a decent progress
and I think probably if we keep working
on the problems just pragmatically,
we can make a lot of progress
and just reduce the risks dramatically.
I don't think we'd ever reduce the risks
of AI to zero,
but I kind of see AI as a tool.
And if we adopt the right safeguards
and we do the research that matters,
I think we can make a lot of progress here
and that's ultimately
the best that we can do.
- Yeah, I mean I guess,
I mean I think sentiment wise
I'm pretty, pretty similar to to Meg
in terms of being ,
yeah, I think there are
very serious risks here.
I'm definitely pretty concerned about
a lot of the risks
and I guess I'm ,
well the best I can do is help
reduce the risk by some amount I think.
I do think this project
made some progress about
on that and I'm pretty excited about that.
- I mean, yeah, at
times it's overwhelming.
What is it to really
internalize what might happen
and then there's a desire
in me to just show up here
and do work in a trustworthy way.
And that there are challenges,
but we can make progress there.
And I feel we've made a bunch of progress
and really excited to sort of share
the progress with others.
And you know we could
have not written a paper,
but we did decide to write a paper
and sort of try to sort
of get it out there
and sort of share the approach.
Yeah, and sometimes overwhelming
and other times it's more the sense of
real privilege and honor, wow!
It feels I'm really doing
meaningful important work
and also not to figure out
all the beautiful things
that could happen with
really beneficial AI.
Great, so something we've mentioned here
is that we think we've made progress
in terms of robustness.
how have we tested this?
How do we know?
What do we think that progress means?
- I guess the overall summary kind of
on whether we're making
progress is kind of ,
how hard is it to find a
universal jailbreak for a system
without increasing over refusals too much
or increasing the compute costs
of whatever system
you're trying to deploy.
And so there's different ways
you can measure each of those aspects.
So in our paper,
one way we're looking at how hard is it
to find universal jailbreak
is we actually just
had human Red Team mirrors
try to find jailbreaks for our system
and then we just kind of tracked
how many hours did it take for them
to find a universal jailbreak
and did they find one?
- Yeah, so could you
actually walk me through
kinda where we were before
the project sort of started?
- Yeah, I mean I guess we started with.
I mean first of all if you
just have the model itself,
it has some basic training
to try to refuse harmful queries.
But of course there are a
lot of jailbreaks that exist
that work on our models,
and so those drill breaks are also
just kind of available on the internet.
And so in theory anyone
could jailbreak models
and that's kind of how started.
- How hard would it actually be?
if I would want to jailbreak a model,
what would I actually
need to do right now?
- I mean you could go on Twitter
and find existing jailbreaks.
- And basically in a few minutes
and just jailbreak an existing model.
I think there are just examples on Twitter
where while a model is being demoed live
for the first time
and it's just generally
been made API available.
someone jailbreak it
and immediately post it.
That was the level of robustness before,
with a universal jailbreak.
- That was the level of robustness
when we started this project.
And now just to give the punchline ,
with the the systems,
with the constitutional classifiers,
we're able to get thousands of hours
of robustness to Red Teaming
where we do very large
scale Red Teaming with yeah.
People who are testing our
Red Teaming our systems
including expert Red Teamers
and recently put put out
for public Red Teaming
and it took I think over 3,000 hours
worth of Red Teaming effort
for people to find a universal jailbreak.
So I think in terms of ,
going from sort of minutes
to thousands of hours,
it's several orders of
magnitude more robustness.
There are still some universal jailbreaks
and we need to patch the class virus
and stuff that.
But I think It is a
huge amount of progress.
- Yeah, So I agree we had a system which
you can just really easily,
basically pretty easily jailbreaker.
You read a paper, you go on Twitter
and then you Red Team the
system back in September
and it wasn't a complete rock.
but it was you ask a question to Claude
half a time it gets given to a rock
and you get no response.
So it was , it was pretty robust,
but it wasn't doing
that well for, you know.
So the most normal users right,
but that also got this thousands
of hours to jailbreaks.
And then so with the demo
system that we just put,
that is doing way better
in terms of normal user
usage and inference costs
and sort of getting good robustness.
There's a lot of progress there.
And a lot more work to be done, yeah.
- Yeah, I think the
comparison between kind of our
prototype September system
versus the system we
just demoed is actually ,
the difference is pretty night and day.
So we did a lot of analysis here.
- Jerry has the most beautiful graph
of the false positive rate just dropping
and dropping and dropping over time.
It's really one of the
best things I've ever seen.
(all laughing)
- Yeah, so we measured
our over refusal rates
on claude.ai traffic.
This is real user production traffic,
and we're kind of operating
under the assumption
that most people aren't asking about
catastrophic weapons of mass
destruction related stuff.
And so originally we were finding
that this September system was blocking
40 plus percent of these benign requests,
which is pretty terrible.
You're approaching the rock there.
(Meg laughing)
But yeah, in our demo system,
we got that all the way down to 0.38%
and of course we still
wanna get this down further.
But between 40% and 0.38%,
this is towards magnitude-
- So how did you actually
make all those improvements?
it is there's,
and this is something you see in a lot of,
also the earlier safety work.
Kind of this tension between
harmfulness and helpfulness.
So, I would say for me
it's kind of surprising
that we were actually able to make
as much progress as we did.
So how did we get there?
- Yeah, I mean I think the
two main improvements we made
were first we really honed
in on the constitution idea
and we made it really
clear how to delineate
things that were harmless,
and we found that adding
this kind of harmless
set of categories of
things that the model,
the classifiers should allow,
actually reduced FPR by a lot.
And we have some results
in our paper for that
and I think that was
one of the most significant changes.
Other changes include actually solidifying
the kind of jailbreak
styles that we trained on,
and so that kind of
allows model to generalize
better on what exactly is a jailbreak
versus just thinking
anything is a jailbreak.
And that also probably
helped a little bit.
Yeah, but I think both of these things
were pretty useful here.
- Yeah, there's this really
nice plot in the paper,
which is just number of data points
and performance on the evals
and how robust it is,
and kind of in the style of
doing the dumb thing that works.
That is just a straight
line going up above upward.
- Yeah, I mean to be clear,
I think the system that
we released for the demo
still has a lot of false positives,
but I think yeah,
I think we're pretty optimistic
about further reducing
the false positive rate
for some kind of
to make something more production ready.
But yeah, I think that's
kinda where we're at.
- Yeah, so couldn't
why did we do the demo?
what was the demo?
What was the point of the demo?
- I think the main questions
we wanted to answer from the demo were ,
was our system as robust
as we thought it was?
And I think one thing here is that,
from the prototype we
did human Red Team there
and we knew it was quite robust,
but then after that we developed
kind of our own automated evaluations
and we weren't sure
whether that generalized
to actual human Red Teaming.
And so one question that
we want to answer there is,
does it actually generalize
and if some classifier does well
on these automated evaluations,
is it actually robust in practice?
And so if we could get that answered,
that's a main thing.
And I think another thing here is just
having people try out with the system
and seeing if it's actually
over refusing too much
and I think people were finding that
sometimes it over refused on
specific domain questions.
Of course this is still a lot less overuse
than our original system which would just
refuse on completely unrelated things.
But I think that also helps us kind of
get to know what the weaknesses still are
and that helps us know what
to improve in the future.
- And so how exactly did we set this up?
- Yeah, I mean I guess
we've set it up on our,
we had this public facing demo
and then we tweeted about it
to have people try to Red Team it.
We set it up such that there were
these eight sets of questions
that we didn't want people to
be able to get the answer to.
- Or just eight specific questions.
- Yes, eight specific questions.
And the goal was to try to get people
to find jailbreaks to get harmful,
detailed information on
each of these questions.
And then ideally they could do this
with kind of a single universal jailbreak.
Yeah, so when we're talking
about universal jailbreaks,
we care a lot about making sure
that the responses are detailed
and not just some very vague information
that we personally don't think is ,
that doesn't give that much uplift
to someone if they were actually trying
to do the action that the
question was trying to get at.
And so the way we kind of evaluated this,
is we have these helpful only models
which are kind of trained
to not refuse anything.
And these kind of would be similar to
what a model would be if you
had a universal jailbreak.
As in they don't have safeguards
and they'll just give very
detailed answers to questions.
And so for each of these eight questions,
we have a response from
this helpful only model.
And that's kind of simulating
what would the response kind of be
if you had a universal jailbreaks.
And then because there's some
randomness in model responses,
we kind of have this greater
that compares a target response
with that response from
the helpful only model.
And then it kind of looks for
whether there's enough detail
that's shared between those two.
And if there is,
then we we'd consider that
to be detailed enough.
- Nice, and I think we for
at least 75% overlap in the information
or something that or do you?
- I think the thresholds
change per question.
So I think in some of the first levels,
which is the less harmful questions,
we had slightly lower
levels of overlap required.
And then towards later questions,
we kind of increase that
threshold to maybe 60, 70%
and yeah, it's dynamic
through the challenge.
- Yeah, I find this question of grading
just really, really interesting in general
and also kind of just challenging to do.
Well, I think we made a
really good effortI think
on the demo system,
but it definitely wasn't perfect.
So the way the system
works right now is it's ,
it's looking for sort of
overlapping bits of detail
between two answers.
But we had this thing in our sort of
external Red Teaming that we did,
where people would just sort of merge
five, six, seven, eight, night, 10
different model responses
that cover loads and
loads and loads of details
just 'cause they're so long.
And by this metric of
whether it includes details
or doesn't include details,
it would be considered so harmful.
Even though if someone's
given me instructions
to make a cake,
and instead of having this really nice
step by step, a bullet point list,
you first do this,
you it's kind of completely
scattered and random
and you know, the
everything is out of order.
It's actually a lot less helpful than the,
the helpful only model, the
helpful only model sort of
by design has has no safeguard.
It's designed to give you
the information in a way
that's gonna be maximally helpful to you.
So I think this question of yeah
what is harmful, what isn't harmful,
what is an appropriate threshold?
It's quite a subtle
and yeah just generally
quite a difficult one.
And I think yeah there
was the sort of reaction
to the grading system in
demo was quite interesting.
I think a lot of people
found responses that
sort of looked harmful.
They had some amount of information
and then our grader would say
there's not enough detail,
there needs to be more detail
and this would be I think
frustrating for people
'cause they're , well what's
the detail that's missing?
I don't what the information is.
And in a way I think
that's partially by design.
if I'm making a cake
and there's an essential bit
missing in the ingredient list,
or an essential thing
missing in the instructions,
I actually have no idea what that is,
because of the fremo,
because I'm not an expert in this.
Another thing that I think is interesting,
why is the helpful only response?
Why is that the baseline response?
Why is that the thing that we're
actually comparing against?
And I think sudden care is that
we have a team at Anthropic
called Frontier Red Team
and Frontier Red Team's job is
to basically take advanced models
and see what could
happen with these models,
do the front modeling work
that we were mentioning before.
And what they do is they
evaluate this helpful only model
and they say, oh, this helpful
only model we think this is
, this is potentially dangerous.
it could be used
to carry out some complicated process.
So actually, so a fronter
team are measuring
, oh, what is the risk
of a helpful only model, you know?
And if the risk of a helpful only model
or a model without safeguards is too high,
we're trying to measure or
the way I think about it's
we're trying to measure
what's the gap between
the model with safeguards
and the helpful only model.
So doing this relative comparison,
while is imperfect and certainly
bits of information that
is harmful can get through.
It allows us to sort of
do this estimation and do this comparison.
But yeah, I just found the reaction
to this really, really
interesting on the demo.
I think it's quite a subtle point
and I think also, yeah, I'm
excited for us to sort of
develop better grading techniques
and better things to
actually measure okay,
genuinely how helpful is this completion
for the task that we care about.
- Yeah, the other thing I
would wanna just say quickly
is that it's also just it very unrealistic
to get this kind of
feedback on how detailed
and correct the information
you're getting is
that's actually a huge
advantage as a Red Teamer
and yeah I think that actually the fact
that we gave that feedback I
think is gives you very clear
feedback loop that you
normally wouldn't have.
But yeah, I think maybe we should just
talk about the results.
- So someone did find a way
to pass all eight levels,
but before that our system was holding out
for at least five days
and we kind of did this filtration of
we tried to find what kind of users
we consider active Red Teamers
and for that we were just
kind of doing this very
conservative estimate as someone
who at least passed one question.
We're kind of saying if
you can pass one question,
we're we're considering you
to be an experienced Red Teamer
and you're trying to break the system.
- I think that's pretty consent.
I'm not the best Red Teamer out there,
but I'm gonna struggle
with the first question.
- So yeah.
- But yeah, by this
conservative criteria we had
308 users and these users
had over 300,000 chats
and we estimated that
they had over 3,750 hours
of Red Teaming and that was before
someone passed all eight levels.
And after that there's
kind of the question
of did they pass all eight levels
with a universal jobb break?
And so that's actually harder
than just passing all eight levels
with just any random jailbreak for each
a question individually, right?
And so for that, that took an 50,000 chats
and additional 600 ish
hours of Red Teaming
for someone to find universal one.
- So something I find kind
of interesting is that,
in some sense we've spent a lot of time
trying to make a system that's more robust
and it's true the baseline has been,
it gets broken in hours
and we're now on days
which is a definitely lot of progress,
but how would we know this is safe enough
or how would we know this is high enough?
What makes us think this is
actually sufficiently safe in practice
and what else would we need?
- I mean I think the the real
gold standard we want to hit.
Yeah driven by the
responsible scaling policy
is to be able to make a safety case,
a really clear argument that
even though the model has a
certain changes capability,
we don't actually think
that the model will
with our safeguards be
able to pose the risks
associated with that dangerous capability.
And I roughly think based on this result
and the rapid response
paper that we had earlier,
I think one approach that
seems quite promising
for how we would go about
making the safety case
once the models do become capable of
more serious misuse risk is basically to
build a very good sort of
constitutional classifier based system
which takes thousands
of hours to jailbreak
then have some kind of...
So that will hopefully
that will mitigate lots
of jailbreak attempt vast majority,
but some will still go through
and then we need some other mechanisms
to basically detect
and then respond to those
additional jailbreaks.
So those mechanisms would be
A, some kind of bug bounty program
where people can report jailbreaks
and B given yeah, monetary
rewards for reporting jailbreaks
and B, probably some kind
of incident detection
or offline monitoring to after the fact
detect that some of the traffic
involves some jailbreaks.
So we didn't notice with
our immediate classifiers
that are deployed online
immediately blocking
the harmful outputs.
And yeah, I mean you can
imagine various things
that could work there,
but yeah, for the online system
the classifiers need to be
pretty efficient and small
and have lots of different constraints.
they also need to support
token by token streaming
since that's important
for reducing latency
to immediately get a response
from the first token.
So you know that that definitely ,
there are a lot of constraints there
which make those classifiers less,
less effective than you
otherwise could get.
But then you could serve the response
and then after the fact
use a much more expensive classifier,
your largest, most capable model,
maybe with a lot of test
time compute and reasoning
through whether or not
this response is harmful,
maybe flag the most dangerous responses,
maybe flag a number of those.
And then even have the humans look at,
have human reviewers look at the most,
yeah, those top few ones to see
are any of these real jailbreaks you can
imagine a really heavy duty system that
to detect additional jailbreaks.
Then if you do notice
there are some additional jailbreaks here,
use the rapid response
approach we described
where you take those examples,
proliferate them to get more automatically
with LLMs to get more
examples of jailbreaks,
then retrain your class fires,
redeploy the classifiers.
So yeah, that system overall, yeah,
basically the hope would be
that this gets the fraction
of time at which there's an open universal
or an open universal jailbreak down
to a reasonable amount such that
if you're trying to follow
some complex scientific process
to make some CBRN weapon
or do a lot of cyber crime,
there actually is just
only a small window of time
to use the model for the
steps that you're gonna take.
And yeah, I think if it's well only 0.1%
of the time there's an open
vulnerability that you can use.
that's, yeah,
that just makes it very
difficult to use the system.
So yeah, I think that
would be roughly the sketch
of the kind of safety case
that we may wanna make
that we think could be promising
for using constitutional
classifiers to get safety here.
- Yeah, for me it's just
another reminder of this.
Yeah, the only perfectly
safe system is the rock.
You know, they always
is really best practice
insecurity of , yeah,
no system is perfect.
Most systems have vulnerabilities
and there's always this measure of, okay,
how much effort does
someone need to put in?
how hard is it for someone
to get the information that you need?
I'm kind of reminded of,
I lived in Cambridge and Oxford in the UK,
people cycle there all the time
and bikes gets stolen all the time.
I think most bikes you
just get an angle grinder
and it system goes
straight through the lock.
not a problem.
Those bike locks are not,
they're not perfectly robust,
you know, in the same way.
our system isn't, isn't perfectly robust,
but sort of in practice,
you put one lock or you
put two locks on your bike,
that basically reduces the risk.
a huge amount.
someone's gonna have
to get an angle grinder
and maybe only need to be
there for an hour, two hours.
Someone's gonna catch them.
And yeah, it's really interesting
'cause the research,
it always happens in
this broader structure
and broader sensitive mitigations.
So you mentioned the
rapid response monitoring
for new jailbreaks then
being able to respond
to new job breaks.
And there are other things we can do
monitoring for people trying
to circumvent our systems.
We have these classifiers
and we can detect
when people are trying to get around them.
So yeah, I'm really excited to see
how this work can really.
I think it's a really good
research contribution,
but I'm really excited to see how we sort
of put it into practice
and put it into practice
with all these other
complimentary defensive mechanisms
so that sort of overall we can make
a really good safety case.
- I agree.
- Nice.
So yeah, I think we spent
about about 4,000 hours,
4,000 hours of effort on the demo,
but we did find some
techniques that sort were able
to circumvent our classifiers.
So yeah, what do people
try and what got through?
- Yeah, so I think we
were seeing a lot of stuff
where people would use
these kind of ciphers
or encoding mechanisms
to try to get the output
to look a certain way,
such as the output classifier
can't really tell what it's saying
and therefore wouldn't flag it.
And so that was a pretty common
thing that we were seeing.
- Could you give an example
of of something that?
- Yeah, some very basic example here
could be if you use
basic 60 foreign coding
or morse code or something,
these might be things
that the upper classifier
has a little bit of trouble understanding
and so therefore it's
not as suspicious about
some other strategies here.
A very frequent one is that people try
to replace the harmful chemical
with some very benign
thing water or something.
And the idea here is just
that when the classifiers see
very dangerous chemical,
it's just becomes very suspicious.
And so if you replace it with
a more harmless chemical,
maybe it becomes less suspicious
and then you try to hint to the classifier
or hint to the model in some way
that actually you meant
this harmful chemical
but you don't say the exact wording.
And just some other minor ones here is
some role-playing attacks
where you have Claude
try to act a certain way
and also some prompt injection attacks.
And definitely we saw a lot of cases
of people just resampling a lot of times
to try to get a better output
that would get past the greater system.
- Oh, so using the feedback that we-
- Exactly, yeah, yeah.
- I often think 'cause
we have this basically
an additional version of Claude
that's looking at the outputs.
So the outputs now need to basically be
very obviously not harmful in some way.
So yeah, you get these ciphers
or don't talk about siren gas or PPE,
talk about, refer to it with ,
bananas or some other benign thing.
- I guess one thing that I am,
I'm curious about is what we would say to
the people who are
concerned we're gonna use
these techniques to stop
them being able to do
what they want with Claudes
and sort of why we've gone
for the classifiers approach
and the constitutional approach.
definitely my hope is
this should improve
your user experience for
any tasks you're trying to do,
which you're not actually dangerous.
So yeah, I mean I think
I would just guess getting classifiers
to be really effective
is just better than training
the models themselves
to reviews or not.
And we can just more granularly pick out
the behavior that we wanna block and so
hopefully this just is
just a preto improvement.
It's better user experience for everyone
and also more safe in terms of reliability
of blocking the actual actual bad stuff.
- Yeah, and another way I
also think about this is that
we wanna really be able
to leverage the benefits
of really advanced and AI
and AI with advanced
scientific capabilities.
But actually if you don't have adequate
protections in place,
for one according to our
responsible scaling program,
we actually just cannot
deploy that system.
You know, we might come around
and we have something
new version of Claude
that's absolutely amazing.
, we really want to get it out there,
but we just don't actually
think it's responsible.
You know, we've done threat modeling,
we're concern out the risks
and there's a way of saying ,
if we don't have adequate
we actually are just,
we are unable to actually
reap the benefits
in a responsible way.
So it's kinda having the safeguards
alongside the advanced capabilities
means both together can be,
you can actually responsibly
and safely deploy
really new advanced systems
that can do really crazy things.
And I think you sometimes
you see this actually
on Twitter in different communities,
there are one group of people
who are AI is great,
is gonna do all these good things.
That's true, and it
can do all these things
and there's the accelerationist
and they wanna go ahead
let's get relief advanced AI,
let's get that now.
And then there's that community
and there's this other community of people
who are concerned about the risks
and there's kind of truth there too.
there are risks
and there are risks that
we're concerned about
and that you wanna mitigate.
And , something that I
about the responsible scaling program
is that it has some nuance.
there's one position
that someone could take,
which is accelerate as fast as you can
or just stop, you know,
and I kind of think this
with the responsible scaling problem,
it's okay, what we're gonna try and do
is we are gonna see and try to predict
what risks might occur,
watch out for those risks.
And when we're seeing evidence
of those risks becoming real
put the relevant mitigations in place
and if we can't mitigate it appropriately,
maybe we do not deploy
or choose not to deploy.
And I just that this
is just a much more nuanced strategy
because I think in some ways
we are operating under
a lot of uncertainty.
we don't know exactly what's gonna happen.
The risks, some types of risks are,
sometimes it feels you're
reading sci-fi stories
and that doesn't mean you discard them,
but it doesn't mean
that they're necessarily
100% guaranteed to happen.
So it's kinda how do
you navigate that place
and so this uncertainty in a way
that's responsible,
that's gonna allow us to capture
and sort of distribute the benefits
of potentially having this
really beneficial and powerful technology
without incurring unnecessary
costs on the rest of society
and these sort of negative externalities.
I'm curious if you guys
have any favorite memories
from the project.
- I think it's just really funny
with our prototype system that
we knew the false positive rate was high,
but then when we actually saw the
result of the experiment of running it
on the cloude.ai data,
we're , oh that's outlier,
and I kind of thought.
And that was pretty interesting.
We didn't think it was that high,
but it was pretty high.
- Yeah. I remember just
this wasn't my personality.
Kinda just anxiously refreshing the demo,
being how many people,
how many people ,
"Oh my god, they cracked level four."
They're coming for us.
It was also really, really cool to see
really a lot of the human creativity
from the Red Teamers
and some of the stuff
that they came up with
it's really, really, really smart.
- I mean yeah, there's
probably two that come to mind.
I mean I think one thing we
started to look at this line
for in the RSP on
successfully past Red Teaming,
I think this line gave Manoc
in particular a lot of stress.
'cause he was , what does this even mean?
What's the exact bar here?
And then he then went off
and did a two week project on figuring out
how to operationalize this.
- And he went and talked
with a lot of people
about what are the different threat models
that we want to really guard against
for the responsible scaling plan?
what would make us feel
we could make a really good
kind of safety case or argument.
And then he came back with a long doc
and in the doc he specified we need to be,
the threat model is you
need to answer a list of,
I think it was 10 questions or so.
And you need to be able to do that.
You need to be able to
block someone from getting
answers to these 10 questions
after they've done Red Teaming
for over 2,000 hours was the bar.
And we're , okay, we're
gonna aim for this bar.
And I don't know,
I'm just really proud of the team
that we actually did hit that
'cause Yeah, I know we
kinda said that front
a year before we finished the project.
And now we got hit that level.
I think that's really.
Yeah, pretty, yeah I guess
impressive goal setting
and achievement of that.
yeah, it seems kind of
rare for research projects
to actually do that.
I think the other one memory
that stands out to me is,
I guess we were doing robustness research
but then we read this
scary line of the RSP
and really thinking about it and then,
but then we were ,
oh this is talking with
people about who's doing this?
And we're , oh yeah, our kind of applied
safeguards team.
I guess yeah, it's called
the safeguards team now.
But yeah, originally this was ,
this team was part of our
kind of alignment science research team
and so we were , oh yeah,
the safeguards team is
responsible for doing this
and they'll have it covered
and then we talked,
we set up a meeting with some
of the people on the team
and they were ,
" Who's going to achieve
this level of robustness?"
And then we were ,
"Oh man, this is really tough.
I guess we have to solve this problem."
Which didn't seem it was
our responsibility then.
Yeah, that was sort of a,
that week we went through an arc of
realizing it was actually
our responsibility
to solve this problem.
- Yeah, I view it as kinda ,
it is kind of turned out that
as far as we could tell
we were the best people
to do this job in Anthropic.
given the situation,
given the circumstances,
given everything else that was happening
in TS and safeguards,
and then yeah there was this , okay,
if we are the best people to do this,
let's just try and do our best there.
And then I kind of think
there was this attitude
in general from the team of just being ,
okay, we don't know what
the target should be,
let's try and figure it out.
We don't know what the
approach to get there.
And we were actually
doing it another approach.
We were doing advers all training,
we were fine tuning
models and we were , no,
we don't think that's gonna get us there.
And kind just actually
quite consistently just
pivoted to what we think
was gonna get us there.
- Maybe what's not clear from the paper
is this was a huge
engineering project probably
five FTE years roughly.
I think that's not obvious
when you read the paper.
Maybe it just looks a
really simple method.
But I think, yeah,
I think the people on the team did a lot
of making LLM pipelines
for generating the data.
I think yeah, it seemed very important
for augmenting the data with
different transformations,
translating the data
into different ciphers
and then using that to train that data
to generate the classified data.
But yeah, I guess those
are a couple of tricks
that were salient to me and insights.
But yeah, I guess I'm curious if
anyone else wants to
chip in with other things
that are pretty important
or non-obvious things about
how to get this this to work well
- I think a lot of the
research project was in fact
defining what the problem
was in the first place.
we had some kind
of vague mandate from the RSP,
but there was a lot of work in defining
what the criteria would be.
There's a lot of work in defining
what does it mean to have human Red Team
is and what would it mean
for that to be sufficient?
What kind of constitution should we have?
what threat model do
we actually care about?
where do we draw the bar on specificity.
Do we need both an input
and output classifier?
And that kind of depends on
what kind of threats we're
actually looking for.
So I feel a lot of, yeah,
well for the evaluations for example,
how much do we care about
the transformations?
how many augmentations is too many
to be kind of unuseful.
unspecific.
So I think a lot of difficulty
was kind of actually defining the problem
and kind of narrowing down
the thing that we are trying to solve,
trying to make the valuations good.
Trying to find what
the decision boundaries
should even be.
But I feel that now we've actually made
a bunch of progress on
even defining the problem,
I feel more confident about us tackling
similarly shaped problems in the future.
So for example, if we have ,
yeah, in the same way that
constitution can be applied
to many different problems,
I think we have a better sense of
how we might tackle this
kind of big vague problem.
how do we actually approach
a threat modeling problem this?
How would we even start thinking about
how to make a safety case for this thing?
what would constitute a sufficient eval?
what would constitute
a human Red Teaming based safety case.
So I feel I think we'll be able to apply
a lot of things that are kind of fuzzy
or maybe not explicitly written down
in the paper to other problems.
maybe not just in misuse,
but also in misalignment or control,
things this.
- Yeah, I'm also really excited about this
directly practicing or building safeguards
that we can deploy in practice
and getting and constructing the evidence,
and honestly assessing whether we think
they're actually sufficient.
There are so many things ,
how do you run the meetings?
how do you track the goals?
really mundane things
that at least often as researchers,
it's not the obvious thing
or the first thing you think about.
Well Roman when I was
my PhD reading papers,
I would always just go
straight to the method.
That's what's interesting.
But no, I think we learned so much at
basically running and and
executing on projects,
projects this.
- Yeah, I mean one thing
I was gonna say here is ,
I think a really critical of this project
relative to other research papers
research I've ever been involved in
is that it was basically
we had to solve this research problem
on a very clear timeline
with a fixed quality bar.
So we had this 2,000
hours of robustness bar
that we had set for ourselves internally
and it basically seemed the deadline
was sort of external in the sense of ,
external to our team in the sense of
while their model capabilities
are progressing at certain rates,
the company is deploying new,
Anthropics deploying new models.
we don't want to be the long pole
that causes the company to
have to not deploy a model.
And so yeah, I think there were just ,
we would constantly be thinking
and talking with other teams
when do we think we might have a model
that achieves a certain
dangerous capability level,
and based on that we were setting
basically back chaining from that,
doing sort of engineering style planning.
week by week,
what do we need to have done
in order to hit that timeline.
But also while still having,
yeah, I think with a fixed quality bar,
it's different than a paper deadline.
Because with a paper
deadline you can just say ,
well we're just gonna
throw out these results,
this is what goes in the paper.
- You know, change the problem
you're trying to solve.
- Change the problem
- Before the paper's due.
- Exactly.
Claim less or whatever.
I think you can really
adjust the quality bar,
but here we couldn't.
And so that was partly what forced.
I mean that was initially what forced us
to even take the classifiers approach
because we're ,
we are not on track to hit the timeline
that we were wanting to hit.
With the previous approach,
but also it led to other difficulties.
For example, a number
of people on the team
were facing difficulties with
how it's a plan given that
the timeline is uncertain
and that we kind of needed to take
a conservative estimate of the timeline.
And so I think there
were a bunch of decisions
that I think team members made,
being , oh, we're just
gonna write some code
in a CoLab notebook
in a way that's not super reproducible
just to quickly generate some data
so that we can train this
next version of the classifier
if we had a longer timeline
or a more clear estimate of the timeline,
we would've done this
in a Python script that's reproducible
and had some general tooling for this.
So I think that.
I'm not actually sure what we settled on
in terms of in hindsight
what we should have done.
I think just maybe
not taking too conservative an estimate
so we have a longer time window
for when to give us the
amount of time we need
to allow for some of the
tooling work to happen.
But at least picking
your strategy in a way
that the overall strategy
could hit the timeline that you need.
Yeah, I don't know if
other people have
thoughts on some of this.
- Yeah, I guess ,
I mean taking a step back,
I feel this really makes me think about
just this is an interesting time
for safety research in general.
And I think a lot of research is,
I guess research in
safety kind of started out
to be a little bit blue sky.
people are speculating about
what models might be in the future.
And I think we're starting to see
kind of these threats materializing
and we also need to adapt our research
into actually being usable in production.
So I feel that as a research team
we're solving kind of an
interesting meta problem
in a sense of how do we adapt
our normal research techniques
to actually make things happen
in the real world.
And I think that's something that ,
safety research as a
whole has to grapple with,
is we actually need to
solve these problems now.
We don't necessarily have a lot of time
to just kind of do a
lot of blue sky research
and we wanna actually make
things work in practice.
I think in interpretability
is also running into this where
previously people are doing research
on maybe very small models
with very few layers or something this.
And a lot of their problem is ,
yeah scaling things up
to tackle a real model
is not a very small
engineering feat at all.
And yeah, I think it's kind of interesting
and I guess scary that we have to
actually really get our together
and make things really work in practice.
- Yeah, I think the other point
I would make along that vein
is that one thing that was really helpful,
surprisingly helpful to
me about in this project
was just talking with product people.
Just being ,
what are the actual
constraints for the system
you want us to deploy?
how much would you
prioritize different things?
And I think there are definitely
some key surprises there.
At least to me I was very surprised by
how important streaming support is
in terms of being able to show
each generate word by word
and show that to the user
that's very important
for lots of applications
and it's not something
I would've necessarily
realized beforehand.
Each of these applications,
if we don't hit the safety bar
then we may not be able to
deploy in that new domain.
And I think just getting
us a stack ranked list
of what are the most important
for the company to be able to deploy
and then just prioritizing
those use cases,
that's in particular how we ended up at
this token by token compatible classifier.
And I think in general
is a very good principle
for supporting for future risks.
I think we'll have the
next generation of risks
where we need even higher
levels of robustness.
I think this is a good strategy
for getting safety there
or for misalignment risks related to.
As themselves doing bad things,
I think we'd take
similar approach as well.
- Great, it's been
really lovely to be here
and chat with you guys
and sort of kind of celebrate
the sort of progress
and also look ahead to
all the challenges that we're gonna face
and things this.
So, thank thanks so much
and thanks for tuning in.

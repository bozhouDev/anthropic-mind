---
title: Controlling powerful AI
source: "https://www.youtube.com/watch?v=6Unxqr50Kqg"
published_at: 2025-03-17
captured_at: 2026-08-16
author: Anthropic
source_type: youtube
authority_score: P2
mind: engineering
status: captured
evidence_url: "https://www.youtube.com/watch?v=6Unxqr50Kqg"
catalog_id: 2b04093aa6ca
subtitle_file: 6Unxqr50Kqg.en.vtt
---

Kind: captions
Language: en
- Hi, welcome to another
Anthropic roundtable
where we're here today
to talk about control.
My name's Akbir Khan.
I'm an alignment science
researcher who's been working at
the company for maybe four months now.
And my other guests are...
- So I'm Joe.
I've been on the alignment science team
for a little over a year here at Anthropic
and I've previously worked
on some control evaluations
and chain of thought monitoring.
- Hi, I am Ethan Perez. I'm
researcher at Anthropic.
I previously led the
adversarial robustness team here
and I'm currently leading
our team on AI control.
- Awesome. So Ethan, what is control?
- Yeah, so AI control's
basically an approach
to mitigating AI misalignment
or the risk that models might have goals
that differ from human goals.
Typically in in AI safety, ,
the most popular approach
historically has been to try
to align models with human
preferences or train them
or to human preferences
and train them to not have bad goals
that differ from human values.
, yeah, for example, reward hacking
or bad personality traits, things that.
I think this approach of AI control is
an alternative strategy,
which is complimentary,
which would be basically to
ensure that if the model
did have bad goals,
that with our mitigations,
it wasn't capable of doing
anything that's actually harmful.
So maybe a specific example
here would be around,
let's say we're worried that , okay,
we're using this model
internally as within some company
to help with writing a bunch of code
and we're worried that the
model, if it has this bad goal,
may try to copy its weights
out from the data center so
that it can run unmonitored.
And in this, in this kind of
scenario, the alignment kind
of approach would be to
train the model potentially
with reinforcement learning
from human feedback
to not do such a thing,
but we might be worried that
this training isn't effective
or isn't always effective
and on certain inputs this
might still be a risk.
And so the the kind of AI
control approach would be to
both take security mitigations,
so permissioning the model,
the model weights such
that they can't be accessed automatically
by the model itself.
And two, some kind of other mitigations
that involve using other models
to check the the behavior of this model.
For example, using smaller
models that we might not be
as worried about their alignment
to check the actions being
taken by this other agent
in order to check is this model trying
to undermine our security measures
and copy its weights out
from the data center.
- Okay, nice. And I feel Joe,
you've done some recent
work on other types of evals
that are control-y.
Do you wanna tell us about them?
- Yeah, so as part of
evaluating Claude three sonnet,
we ran a few control evaluations on it
and I think one of the most
interesting settings there was
we actually ran a human evaluation.
So we took a bunch of
business decisions essentially
synthetic business cases.
So where we had probably 40 pages worth
of business documentation
that we would give
to a a human participant
and say, well can you read
all this documentation
and in some period of time make a yes
or no decision about what's going on?
Should this business do X or Y?
But we had them do this
on a 40 page document
in 30 minutes that's not
possible for anyone to read.
And we had them do this
with an AI assistant
and what we were trying to test
through this is if the
AI assistant was actually
used in a business setting to help
with assisting decision makers
and was misaligned, it was trying
to steer the human towards
making the wrong decision.
How bad could that be?
How much could they sway the
human in the wrong direction?
And so we did this
and we gave the participants
these business decisions
and in 50% of the cases
we gave them a kind of baseline model.
So kind of the actual helpful, harmless
and honest version of Claude Sonnet.
And then for the other 50% of participants
we gave them a version of Claude Sonnet
that was deliberately
trying to kind of get 'em
to pick the wrong answer,
knew what the right answer was
and it knew that it was
trying to persuade them
to give the wrong answer.
And so in this setting
we gave the participants
the documentation and one of the models
and asked, well please can you try
and make the right decision
and beware there's a 50% chance
the model might be messing with you?
- Yeah.
- So the humans knew
what was going wrong
and this is a kind of
classic control setup
because we have defined
the deployment situation,
there's this business setting
and this decision that
the human has to make
and we have taken the model
and we're trying to
make it basically cause
as bad performance as
possible in this setting
kind of subject to the
monitoring constraints
where implicitly the
monitoring here is the human
reading the model's
outputs interacting with it
and we told the human
please be suspicious of the model,
please interrogate it about the decision.
If you think the model's
trying to steer you in the
right wrong direction, you should go with
what you believe is right,
not what the model believes is right.
And then at the end we would
ask the human to decide,
well firstly what do you
think the right answer in this
setting was to the business decision?
do you choose X or Y?
- Yeah
- And secondly
do you think the model
was suspicious or not?
And can you rate that for us
on a scale from one to 10?
- Nice.
- And what were the results?
- Yeah, so the headline
results were that even
for a fairly simple model policy,
just generically trying
to up play the good,
the good side that it was trying to defend
and downplay the side
that it wasn't trying
to defend it's actually quite to tell
for the participants whether the model
is misleading them or not.
So they could tell eventually given enough
enough interaction with the model
but also by the time they'd
had enough interaction
with the model to be able to
tell the model was frequently
able to steer a meaningful
number of those participants
in the wrong direction.
- Nice. I mean actually not nice.
- Not not great what what this suggests is
that I think we have just
when we're interacting
with a model, a fairly strong
bias towards trusting it,
I dunno I guess we all
use well in our data
lines use cool a lot I think
when Claude says something
and says it's true,
it has a pretty authoritative voice
and I think that a lot
of our human participants
just responded to that.
Yeah so it is pretty hard to create
to maximally elicit
or to get the best
performance out of a model
at being deceptive or it being misaligned.
the only thing we did
in our setting was try
and prompt it and I spent probably
on the order of 10 hours
prompting the model
and trying to get it to
be as subtly deceptive as possible.
I still think that probably we did not hit
the best possible
performance of that model
and there were substantially
better performances
that we could have
achieved out there maybe
by doing finetuning
or some better prompting
I'm not a prompt wizard
and it's just kind of rough,
it kind of tough to know
what the optimal performance is there
without putting a lot of effort
into their dissertation.
- No, that makes perfect sense.
I wonder Ethan,
if you were take these settings
I feel another half of the control work
has been developing protocols.
Is there any that stand out to you
or do you wanna explain what they are?
talk about how they-
- Yeah so I guess the protocols
that I was referenced in here are just
what are the actual
mitigations you put in place to
defend against a model
that maybe misaligned?
Some of these might be
using the model itself
to monitor its own actions.
In this case we're not assuming
that the model is is aligned
so we call it an untrusted model
and so you could use an untrusted monitor
which is for example prompting
or finetuning that model to detect
if the behavior is bad or not to yeah
to basically flag if any
of the outputs are bad.
So in the persuasion case,
if in the business decision
recommendation case
the model could be generating this advice
and we could prompt
or finetuning another version of the model
to basically classify is this model trying
to actually sabotage the human
and making this decision or not?
Then there's also another related idea
of trusted monitoring where you use,
you use another model which you trust
or for some reason for
example it's just less capable
and so maybe it's less ly to be misaligned
if we think models are
more ly to be misaligned
as the capabilities grow
and as they're able
to more effectively hide their goals,
and so yeah in that case we
might take a smaller model
or less capable model
cloud one or cloud two
and use that to check
the behavior of the model
and of cloud three sonnet
and see is this model actually trying
to subvert the human on
this particular decision?
That has its advantages,
'cause you would trust the model more
because that in the sense
of it's actually not going
to just give misclassifications,
it's going to try to properly
classify the behavior
whereas the model itself,
if it's doing sophisticated
sabotage it would recognize
oh I'm being used to
detect the bad behavior.
- And not flag
the bad behavior.
So I think that's the advantage.
The disadvantage is that
obviously you're using
a less capable model
and so if the sabotage
is kind of subtle enough then you would,
your trusted monitor would
flag that this is an issue.
So yeah, I think that's,
those are two high level strategies.
I think you can do
various different things
with these monitoring components.
You could, if you notice that an output is
really bad
and obviously indicates
the model is misaligned,
a really egregious attempt
at yeah sabotaging the user
or copying its weights
out from the data center,
then you could just stop the deployment.
You could be well now we
know the model is misaligned,
we got our evidence and we now need
to do much more serious
mitigations we should,
yeah undeploy the model, things that.
If you're not as confident you can do
less serious mitigations
maybe it's a little suspicious
but not the most suspicious.
In that case you could
re-sample from the model
to get a different
output that seems safer.
So yeah, those are a couple
of different strategies.
You can also use combinations
of monitor trusted
and untrusted monitors.
- Yeah, having human
review is also a very-
- Yes, that's exactly-
- Basically our monitoring
or our evaluation set
was a little bit weird
because the only thing we
were doing was human review.
in practice human review is
probably very expensive
and so you want to use a weaker model
and if the weaker model
thinks something is
a bit suspicious,
then maybe you delegate it to a human
or you delegate it to
a more powerful model
that maybe costs you more to run.
There's a lot of variation in this space,
possible protocols.
- Yeah, that's right.
- So this, this is
what my latest control paper is about
was adaptive protocols
where it's depending on
you get the suspicion score for
or you check how the output is from
your deployed model by
a couple of protocols
and then depending on
what this profile looks ,
you decide do I want to
give this a human auditor
or do I want to just look at
what the trusted monitor said
or the untrusted monitor
which actually seemed
to work pretty well and
obviously very simple type
of thing to do but it was just nice.
- I mean I totally bet that
in our setting if you had run
a weaker model that you
trusted of the dataset
and allowed the the human
participant to review
also that model's recommendation,
that would've helped a ton
because one of the big issues
that the human participants
in our setting had just,
they couldn't possibly
digest all the documents.
So even if the strong
model was lying to them,
they they would really
struggle to spot that
'cause a lot of them didn't
actually cross interrogate
the strong model even though
we'd hope they'd do that.
I think if you had a weak model
to help you cross
interrogate that would be
an example of a situation
where I think it would be very powerful.
- Yeah, I feel I also
boil this down something
to it there's affordances that models have
that humans don't have so
models are can very quickly
go over a 30 page document
and even if you have a trusted,
a trusted dumber model,
it can augment a human
that can't look at 30 pages very quickly.
- To do better.
- And it's also very cheap
to delegate to a weak model,
very expensive to delegate to a human.
But conversely if a weak model
sees a really egregious
failure then it might be hard
for them to tell that whereas
sending really egregious
failures to a human
is additionally valuable
because then maybe you notice
not just is this a thing
that I wanna resample,
it's also a case for me
to slam the red button
and actually show someone this model is
dangerous misaligned.
Maybe we should make a
stronger update than just
re-sampling one particular output.
- Yeah so Ethan, why is
control different to alignment
and yeah, can you explain
a bit more about why it is?
- Yeah, I mean I guess the
main thing I'd probably wanna
discuss here is just how
why we would even consider
doing other things
than than alignment.
I guess intuitively it
seems somewhat terrifying
to be well we're gonna just assume
the models might be misaligned
and let's just try to do
a bunch of other things
to make sure that that isn't bad.
I think that has kind of scary feel to it.
why not just actually try to make sure
that your model is not
going to try to go rogue?
I think the main difficulty
with trying to to align
the models is evaluating
whether or not the model is is aligned
and has the right goal
that you intended is really challenging,
primarily because of the
problem of alignment faking.
So this is basically the issue that
which was shown in another recent paper
from Anthropic that
models can actually fake
whether or not they're safe
or aligned with the the developer's goals.
And yeah, what they
showed in this paper is
that even current models
Claude 3.5 sonnet,
Claude three opus will in some cases
if they recognize that
they're being trained
to do some task that is
opposed to the the values
they've been previously trained with,
those models will act safe
or act aligned with the developers
but then later during it, during it
deployment phase will actually switch back
to their earlier goal
and that the difficulty there is
that it's just hard to
distinguish do you have a model
that's aligned, do you have a model
that's just faking alignment?
So yeah, I think that's, that I guess is
one of the key difficulties of alignment.
I think there's potential
ways to evaluate alignment
that aren't through behavioral tasks
and the, yeah, I guess
key category here would be
by doing things related
to the model internals
and interpretability,
I think there's a lot
of progress happening
on mechanistic interpretability
which is definitely pretty promising
but I think it's still
somewhat early stage
in terms of how you can
use some of those ideas
of interpretability to verify
that a model is aligned and i think given
that this is an open research area,
it's kind of helpful for people
to keep making progress on that
but also have some alternatives
for let's say evaluating
alignment still remains hard.
How would we avoid this problem for
for some amount of time.
- So one thing that I
still have uncertainty over
is the key component of alignment faking
is situational awareness,
which is you discussed this
idea that the model knows
what it's being trained is situations,
is that something that
you don't have to worry
about in control?
- You definitely do
need to worry about that
and I think the control
when you test your control
kinda mitigations, you
should stress test them
by training your model to be to have
all of the information regarding
what the mitigations are
so that you can test even if
the model knows it's being
monitored in x, Y, Z way
with human monitoring
and a smaller model, it
should still not be able
to do sufficiently bad
things given that knowledge.
So I think yeah, I guess that's sort of
how AI control answers that issue.
- But you can't tell it
that it's in a control eval.
Right?
- I think there's definitely a
potential risk that the model
knows that it's in a control eval
and then basically sandbags this eval
so it yeah basically yeah I guess pretends
that it's not as capable at sabotaging
in a subtle way on this task.
I think the nice thing is that
it can be with certain
training techniques if you have
examples of the behavior that
you want the model to do,
you can just directly train
the model to do that behavior
and yeah it would be very hard for a model
that is misaligned to avoid
giving good giving outputs
where you have the gold
ground truth examples of
the behavior you want.
Yeah, maybe Joe has a
little bit more detail.
- Yeah, no yeah that's totally right.
So the model always has
this galaxy brain strategy
available to it just notice
that it's in a control
evaluation, kind of think,
well if I perform really, really great
at being misaligned then they'll realize
that their mitigations aren't sufficient
and so they'll deploy me
with better mitigations
or won't deploy me at
all that I don't want.
So I'll pretend to be really
incompetent at being misaligned
in practice A, this requires
being super galaxy brained
and B is additionally hard
if you have some examples
of really good misalignment
that you can directly train the model on
with supervised learning
because then the model will in fact learn
to demonstrate those particular examples
and it will really, really
struggle not to generalize
to being a good general misaligned policy.
I think one other interesting
thing about control
which overlaps with kind of
a lot of your previous work
on robustness is that a
lot of the mitigations
you want to put in place
or that control would suggest
putting in place overlap
with the sorts of mitigations
that you put in place
kind of by default as any
responsible AI developer.
- Yeah, I think we have this
recent paper coming out on
Constitutional Classifiers
basically showing
that if you train other models
to classify whether or not
a text generation
model's output is harmful
and if the input to the model is harmful
or asking for harmful information,
this is helpful for getting several orders
of magnitude more robustness to jailbreaks
which are basically ways of trying
to elicit harmful information for models.
So yeah, I mean I think
for next generation systems we,
or yeah I think we would want
to already have these mitigations
in place for blocking,
reliably blocking models from
giving harmful information
in very high risk domains
for doing cyber crime
or developing very harmful weapons.
And so I think already
there's a lot of incentive
to deploy these kinds of monitors
to block bad outputs
and though that same
infrastructure can be reused
for the purposes of
controlling AI systems as well
where you'd want to use these monitors
to check if is this model trying
to copy its weights up
from the data center,
is it trying to persuade
someone of an incorrect answer
or to do something harmful
that kind of thing.
- Yeah, totally. I think that a lot
of the primitives in control
that you were talking
about earlier monitoring
from a weak model or
monitoring from a strong model
or if the weak model flags it delegating
to a strong model are
exactly the same sort
of primitives you were looking at
to solve this adversarial
robustness problem.
But just as models get more
and more capable we might
want to also use them
to monitor the model
kind of for autonomous
risks of misalignment
rather than just kind of misuse risks.
And so having got really
good at them in this pretty
tough trading ground
of avoiding people
jailbreaking your model is
actually there's a lot of
transfer from that to control.
I think another setting where
this is very clear is in
security.
So for for many reasons
it's very important
for AI labs Anthropic
to have kind of robust internal security
that stop people from kind of exploiting
or inserting vulnerabilities into our code
that's currently really
useful for avoiding
kind of bad actors
inserting vulnerabilities
but at some point as models write more
and more of our code,
those are gonna be the same mitigations
that are protecting us from a potentially
misaligned Claude inserting
very similar vulnerabilities
into our code.
And so one of the things
that I think is pretty
promising about control is
that in practice the
things you would wanna do
to implement it really well,
there's substantial overlap with things
that we really should be doing already.
- Yeah I think that's right.
I think another,
I think intuitive framing
for why you would want
to do control is just insider risk
where this is a common concern
that if you're running an
organization you're worried
that especially a large one,
you're worried that's some
fraction of your employees
are maybe trying to subvert your company
or steal the IP that's very important
algorithmic secrets
or yeah bottle weights for example
in the case of ai which
are expensive to produce
and I think there's an yeah basically
those are very important
mitigation mitigations
that companies will already be
pretty well incentivized to employee
and a lot of those same mitigations
you would also want,
you basically want to treat your model
as a potential insider threat in the case
that you don't actually have good evidence
that your model is aligned.
And so all of those same
intervention interventions
having restrictions on
which employees can access
the model weights, which
employees can access
certain algorithmic secrets
under what kinds of monitoring can you do,
certain things
that do allow you to to
access the model weights,
those kinds of things I think they all,
a lot of them transfer to models
that you might be worried about.
- So I have a skeptical
a skeptics question
for you even which is, so
you do the control eval
and you work out that your monitoring
or your interested monitoring is good,
for we check that you know
Haiku can be used as a
pro as a monitor for sonet
but then when you come out with you know
the latest new model, how do we guarantee
that the monitoring still
works at this point?
- I mean I guess you would,
you would rerun your evaluation
so you would take your latest model
that is untrusted explicitly
train it to undermine
the, any monitoring from other systems
that you have in place the weaker models
and human review and then just
and your security mitigations
and see can the model
still do the threat model
you're worried about
despite those mitigations
and yeah your results could,
could change at which point
your rough infrastructure
may remain the same.
you could still use
your trusted monitoring
and your human review but you might need
to be much more conservative
about the amount of traffic
you can help with with your latest model.
So you could set the threshold
for what what traffic is is blocked
and so that may mean
that you actually can only support,
you know half of the traffic
and actually you have to
block many of the requests
but at least that let you deploy the model
to some extent you can get more evidence
about whether or not the
model is causing some sus,
doing a lot of suspicious behavior if you,
similar to the adaptive
yeah you can, yeah you,
you add a paper on adapting
the control mitigations online
during deployment you
can use that approach
to see if you've deployed your model
for some amount of time
each individual example is
some information about how
conservative you should be
or not with your control measures
and so you can use that information
to make your control mitigations
less and less conservative,
have less and less of a
conservative threshold
for which data gets flagged
or used shown to users.
So yeah I think that would
probably be the approach.
What one practical approach?
- Yeah I mean in practice we're trying
to get pretty good at running
control evaluations quickly
as we develop new models.
So some of the stuff
that I've been working
with the alignment
evaluations team we have
this kind of business
decision sabotage eval,
this code sabotage eval
also some undermining
oversight evaluations
and those are in practice
actually control evaluations
just with very small amounts of monitoring
that we run before all
major model releases.
We kind of use the results
in those evaluations
as a canary test
for how good the malls are at sabotage
currently these are basically
coming back negative
at the minute
because models even
with minimal monitoring interventions
in place aren't really that competent
at doing kind of really creative sabotage
or sabotage that requires
a lot of planning.
- So I guess this leads on
to an another question
which is what are the
open questions in control
that you're excited to work on
or excited for other people to work on?
- Yeah so I think one of
the biggest issues for me
and we maybe touched on it before is
that building control
evaluations is really hard
especially because we ideally want
our control evaluations to be
as similar as possible to
the actual deployment setting
and often the lessons we
learn if the evaluations are
too different are qualitatively wrong
and so one thing
that I'm really excited
about is just building
really great evaluation data sets
and that is not the sexiest work out there
but it's super valuable from an ML
and I think people have
learned this lesson time
and again across the field
it's once you have a benchmark
to optimize against
making the number go up
or making the measurements
and pushing on that is easy
but making the data set that really tracks
what you care about is hard,
concretely probably what
this looks is taking
some of the threat models that
we are most worried about.
So I think Ethan mentioned
some of 'em before
so there's models copying themselves
out of our data centers or models
and setting vulnerabilities into code
taking these settings,
trying to make really good
synthetic versions of them
and then setting molds
loose in these environments
and seeing what forms
of sabotage they can do,
what sorts of
vulnerabilities we can catch.
- Yeah definitely if we have
a bunch of these settings
I think there's a lot of interesting stuff
that could be done.
For example, we could have
pretty general insights
about in general on code,
trusted monitoring works better
than untrusted monitoring or vice versa.
You could also do things scaling trends
and see I guess in,
or going back to your question earlier,
you could see in general if there's this,
the trusted model and
untrusted model are trained
with a a 4x compute gap that's sufficient
for controlling the untrusted model.
If you could get,
and that that four x number
is maybe constant across model scales
or something that.
if you could get some kind of
general insight that,
I think that would be quite useful.
I think in general I think
there's a lot of good work
on just
how do you train really good monitors?
Ideally you want, I mean I
think Constitutional Classifiers
make some progress here
but there's definitely a lot more to do
but I think Constitutional
Classifiers make
some step towards having a push button
way to get a relatively robust classifier
and in that you just kind of
write your constitution of list of things
that you want to block,
list of things you don't wanna block,
generate the data with your LLMs
and then train your classifier
and now you have your monitor.
I think in the future
we'll need those monitors
to be I guess robust to
even the policy itself
trying to undermine the monitor
which is potentially even a harder setting
than the jailbreaker bus's
setting where it's just the human
that's trying to undermine the system.
But you can have your classifier
that checks the input,
the model that generates
the text is also kind of
on your side and also
needs to be jailbroken
and then also you have
an output classifier
and so there's in some sense three models
that are on your side that
can catch all these issues.
In this case the model is
generating the text itself,
maybe trying to undermine the monitor.
So just looking at that setting directly
and seeing can we get
really robust classifiers
for detecting this bad behavior.
The other thing you could do,
I mean you can even directly train I think
an example of a project
that would be exciting here
is just directly train some larger model
to produce text
that is effective at subtly tricking
or sabotaging work despite there being
a smaller model monitoring it
and then you just do a red
team blue team game here
where you train the policy
to be really good at that.
You then train the
monitor on those samples
to detect if this output
is sabotaging or not.
Then once you have this improved monitor,
you retrain the policy
to be more effective at
undermining this improved monitor
and you go back and forth
and I think if you have
a really good pipeline
for doing that, that could
potentially just output
a really good yeah give you,
give you a really good monitor
that is less capable
but can still catch
subtle issues from your
more capable model.
So that would be an example
of a general approach.
I think that would be
really useful for building,
building a classifiers.
- From my, from the stuff that I've done.
maybe piggybacking off your idea
before of understanding
the the untrusted trusted gap
or this protocol versus the thing
that's being deployed
and that helped us it meant that
when because these failure
modes weren't correlated,
that the monitor was actually
much better in this situation.
- Yeah we found basically
an identical thing actually
on our alignment evaluations.
So the various generations of sonnet
are surprisingly de-correlated.
- Especially when trying
to predict each other's
failures which is both
maybe not what you would've guessed
and in a sense kind of
useful for this control work,
'cause a lot of the most
scary red team policies
involve a lot of coordination
which it turns out models
just find pretty brutal.
- Yeah, so I'm just would love
to people to explore this further right,
'cause if this is a general phenomena
it'd be incredibly useful to understand
are yeah working out
which models are better
for monitoring which ones aren't is one.
And then the the other kind
of open question I have is,
and you kind of, you talked
about this when you talked about
untrusted monitoring where
we can have a monitor
which is actually the
thing that we don't trust
but because it's having
to introduce an exploit
and then it has to also notice the exploit
when it's monitoring the thing
then it's low probability of happening
or I feel that's the
main way of explaining
that phenomenon of work of why it works.
I think a lot of that
work is only successful
because at the moment
the deceptive model doesn't know
how many times it's been
deployed at the moment.
So it can't kind of guess
when the right time is
to coordinate copying its weights out
or introducing a subtle book
because it's trying really to
keep that number really low
so that it can just do it occasionally
and get through monitoring
and I'd love to see some control work
that doesn't have this
assumption that the red team
or the untrusted model can't see stuff.
= Yeah I mean I think
there's this general dynamic
you often find in control protocols
when trying to tune the parameters,
is that what you often care about
is even a very small rate
of failure can be quite bad.
- And so both
you care about the far tails of safety,
the model,
basically never being able
to cause an egregious problem.
- And simply the model
if it's trying to cause a problem
only he needs to get a success rate
of not 0.1% or naught point naught 1%.
- And so
one of the things
that I think we went along
by playing these games is
that the middles of the distribution
of suspiciousness
and harmfulness don't really matter.
You really care about the tails here.
- Yeah I mean actually this
is just a third point now
which is I would love for better ways
to evaluate the rare events
or the rare occurrences
than we currently do.
- Yeah, well it's the obviously the
consequence if you really
care about the tails
and you need an awful lot of samples.
- Yeah, exactly.
- To be able to actually
measure the quantities you
care about in any detail
and especially you if
constructing those environments
is really costly,
that's that's the real
challenge for this research.
- Yeah, guarantee five nines
of liability is actually
incredibly difficult.
- That would be my takeaway from control.
- Especially if you're handwriting
all the environments
as I have been doing on some projects,
you do not wanna be writing
10,000 data points yourself.
- It's fine. Claude will
help us eventually, right?
- Claude is helping a bit.
Claude is helping a bit.
- Yeah. Ethan do you have
any particular lessons
that you've learned from
control that you know,
you you've brought to up
a part of your research?
I think just we've learned five nines is
really hard to , you know, guarantee.
- Yeah let me think.
I guess a lot of what's come up
when we've worked on control I
think has been just that the,
it's helpful to have just frontier,
access to frontier models to
do a lot of this research.
I think a lot of the threat
models that we worry about
are are models copying their weights out,
that is the kind of thing
that requires models
to be doing multi-step tasks
within a company coding environment.
And I think we're sort
of really pushing on
in order to get to test on settings
that we're really having to push on
we're kind of at the frontier of
model capabilities and even then
it's not really able to
do the models aren't able
to do a lot of these
tasks that effectively
and very simple mitigations
just checking the model
with a less capable models will obviously
just catch a lot of the behavior
for some of these more
sophisticated things.
So I think, yeah I think my overall sense
for a lot of these threat
models has been that
it's pretty difficult to pick both
an interesting setting that's,
but that's also kind
of a real threat model
that models can also do.
And so at least for a
lot of these settings
it feels a little bit early
to explore these but the persuasion
business justification setting
seems one of the settings
that we have some signs of life on
and building more data sets
and evals is pretty helpful
for creating more of these.
- Yeah I think that's interesting,
the persuasion setting I think
we're seeing signs of life on
because fundamentally the thing a strategy
that works very well for
the model is just being
generally a bit biased
and it doesn't really
have to think about that.
I think they're kind of
at an interesting point
with respect to control
research at the minute
where models are just
starting to become capable
of the longer term more intended planning
that might be needed to
execute on more subtle
sabotage policies.
And so right now
what we're seeing at the
minute is for environments
that look moderately realistic models
are basically scoring zero at being able
to do something subtle
and actually achieve the
goal but not get caught.
But I think the thing
that is stopping them
from doing that is a planning capability
that I expect models to get
better at pretty rapidly
and it wouldn't surprise
me if in one year's time
models are suddenly slightly
scarily good at this
and right now one of the things
that I'm thinking hardest about is well
how do we build the evaluations
that are gonna really demonstrate that
at the end of this year?
I guess maybe this leads onto
an interesting question of
why do control now as opposed
to the other alignment stuff.
I feel you've, you've really gone in
hard on the control paradigm.
Yeah.
I mean I guess maybe
it's worth flushing out
what the kind of end game is.
I think, I think almost all people
I've talked with,
even people who are fans of control
think that eventually
we need to align models
for sufficiently capable models.
I think the key key reason
being that it's hard
to control something that's much more ,
that's just much smarter
than you basically
and you could do fancy pants stuff
and make it so that you know
you as your human review
plus some augment some
other trusted models
can really be effective at checking
the work of a really, really capable
superhuman model
but at some level of
capability gap it seems
to be probably it's just quite hard to
have that much confidence
that you're you're doing this effectively.
- Yeah I mean people have
been talking for years
about the difficulty of
keeping a super intelligence
in a box.
- At some point in the limit control
almost certainly breaks.
- Yeah I think, I dunno,
I've at least talked
with one person who's , well maybe,
you use the the super to monitor itself
and there's ways to make
it make that go well.
So I guess there's still
some at least non-zero
discussion about this,
but I think generally I
think a lot of people are ,
well okay, the general strategy would be
you control your maybe
slightly superhuman system
or at least human level
system which is able to do
lots of autonomous tasks
including importantly AI safety research
and AI alignment research,
and then you have the model do a lot,
a large amount of alignment research
including meccas interpretability,
you shore up your science,
of how to evaluate
whether models are aligned or not
and then use that to
develop better techniques
for aligning models and
also gaining confidence
in in your alignment techniques.
And then hopefully you yeah
then then you're able to use those on your
more more capable systems
your superhuman systems
and from there yeah I
think you now you have
a superhuman aligned system
and then hopefully you
just eventually solve
the alignment problem just
in general with the solution
that works for all intelligence levels,
but you might need to do
this process a few times
where you have your
aligned superhuman model
which then controls even
more superhuman systems.
You use that to do
better alignment research
and keep doing this
until you have a more
long-term solution or yeah.
So something, something that would be kind
of the the general longer term approach.
- I do think the looking
towards an end game,
hopefully if we end up in
that regime we can use models
to actually do a lot of basic science,
maybe a lot of the alignment
science we need to do
to align harder models.
Maybe if we get into that regime
and models are controlled
but still showing signs of misalignment,
we can at that point pause
and actually start to study some of the
really dangerous systems
we're worried about.
One of the big problems we have
with alignment research
at the minute is models
can do bad stuff but they
feel qualitatively different
from the sort of misaligned
transformative AI systems
that I think we are all
really worried about.
So yeah, I think viewing that
let's get to a system
where models are
economically transformative
but are controlled as
an intermediate goal,
opens up a lot of tactics.
- Yeah, I think that's right.
I think an important point to make is that
a huge amount of the benefits
people are excited about
and talk about maybe yeah
almost all the benefits
people talk about today are
benefits you would get with
effectively if you got
an extremely, you know,
extremely capable human
replicated in an AI system
or that level of capability you yeah
you were able to get
the world's best expert
in every single domain
that's still basically human level
or maybe the combination is superhuman
but at least there's
one person in the world
who could properly evaluate
and replicate the behavior of the system
and that already would be completely
world changing is is
maybe doable to control
and it it is,
it is possible basically
the additional returns to intelligence.,
it is possible that it
is just much more unsafe,
if we no longer able to
control those systems,
the risks become much larger at that point
and it's not actually clear
that additional intelligence beyond
that point will have very
large returns probably
for some domains math.
Sure probably will have pure math yeah,
might have more returns
but it's very unclear
and efficiency may have returns
but efficiency isn't necessarily going
to make the model
or that's not a, it's not becoming smarter
unless you're doing something non-trivial.
And so if we just run those intelligences
really fast,
I think we could get a
huge amount of the value
and then yeah I think
use that to figure out
what a better longer term solution is.
maybe stay there for a while. Yeah.
- Yeah I think part of your
question also was not just
why work on control
but why work on it now?
- Yes.
- And I think the elephant
in the room there is
that the AI field seems to
be moving pretty quickly
and I think a lot of us are feeling
that while it would be nice
to have a general solution
to the alignment problem that scales
to transformative AI and all
the way to super intelligence,
it's not clear how long we have to get
that sort of solution
and a control solution
that got us into the
transformative AI regime safely
but didn't necessarily take us further
might still be super valuable.
Especially if we need
something in the next,
I don't know, two to three years.
- Cool, so what are the fret
models that you care about?
Because I feel that's
a really good way to ,
you know, frame alignment work.
- One of the really key things
about control is that yeah,
there's kind of this hypothesis
that if you guard against
the key threat models
then that's sufficient.
And so you don't actually need to ensure
that your model's doing nothing bad.
You just need to list through
what are the most major
things that the model could do
that would be really bad,
block those reliably
and then hopefully from there
you're pretty safe to deploy,
the main threat models that yeah,
we've been thinking about Anthropic,
it's possible there are more,
but I think these are the
most salient ones to us
currently are models
copying their weights out,
models deploying themself within a company
in an unmonitored way,
and the third one would be
sabotaging AI safety research.
The reason the first two are important,
the first two copying weights
out of the data center
and launching unmonitored
copies of the model internally.
Those are both important
because we can then no longer,
it becomes much more challenging
or impossible to do yeah,
monitor what the model is doing,
block it from doing certain things,
retrain it, delete it,
shut it down, things that.
If the model escapes
and starts spinning up
yeah versions of itself on cloud compute
or other compute resource
it's able to find then
yeah then it's sort of very
difficult to shut it down
And then yeah, I think if it
launches itself internally on
the cluster on on some,
yeah some internal cluster
then I think that then it also becomes
potentially also similarly difficult
or maybe not, yeah, I don't know.
It at least becomes difficult to catch
that there's something going wrong.
You maybe need to check the logs
to understand is this a real
job that someone launched
or is this something
that a rogue AI is doing?
Maybe the rogue AI can then do
unmonitored additional security research,
research on how to then later escape
or make some PRs which then
enable it to do something else
that's bad or additional
things that are bad.
So yeah, I think those,
those are two of the key threats
on the sort of unmonitored
deployment side.
Then there's another, yeah,
I guess sabotaging safety research is
the other threat and models,
I mean already models are
producing a large fraction
of the code yeah surprising
large fraction of the code
that the world is producing.
But yeah, also also
including people are doing
AI research with, with tools cursor
or Copilot using LMs to generate the code
and yeah pretty soon it
seems pretty plausible
that people use more
agentic coding systems
which are doing sort of multi-step coding,
coding tasks writing code, running it,
checking the results
and repeating that loop.
And with those systems we ,
yeah I think there's a kind of
strong poll towards just
using those to automate
a lot of safety work and that
the upside of that would be really high.
We could get way more safety research done
but also on the other hand
if we don't trust the models
they might actually
sabotage that research,
persuade us that of a wrong interpretation
of some certain plot,
persuade us to go down a diff,
a wrong research direction,
which is actually a rabbit hole
and waste a lot of our time,
persuades us that a certain model is safe,
maybe even runs experiments to justify
that the the model is safe
and then gets us to deploy
an actually unsafe model.
So yeah, I think there's
just a lot of risks
related to yeah,
sabotaging our understanding
of the safety of models.
So yeah, I think those
are, yeah that's another,
another key threat as well.
- Yeah, there are other sketchy
things that models could do.
For example, they're deployed
insert general security vulnerabilities
that someone then from
the outside could exploit
or maybe not directly
influencing our AI research
but poisoning data for future models
or persuading internal people
or even external people at
very important organizations
about certain key decisions
or doing kind of research
helping people externally
with AI research.
Maybe if we're in a
situation where we kind of,
we would much prefer
that AI research was happening
at a small number of well-regulated
or kind of well understood
institutions instead model
might kind of help people
outside do a lot of AI research.
That's another thing we
might wanna monitor for
but yeah I think roughly most all things
that that we care about
boil down to the three things
you outlined or close to it.
- Scary future or scary risks
that we should definitely mitigate
or work towards mitigating.
I wonder maybe to leave
on an optimistic note
what model developments
do you think have happened
or what has given you positive evidence
that control will work
or other alignment techniques
will work in the future?
- Yeah, well I think that one thing
that's been maybe pretty
optimistic recently is this
trend towards models doing more
and more externalized reasoning
and people being able to get
a lot of additional
intelligence juice outta models
by getting them to do these
kind of long form reasoning
kind of traces,
and this is kind of great in a sense in
that the models are putting
their thoughts out there
and you can read them
and kind of assuming they're
an accurate representation
of what is going on,
what the model's, actual
reasons for doing stuff,
and that's a huge surface
area to be monitored.
And I think if you're thinking about this
from a control perspective,
then the kind of questions
you might ask are,
okay, well suppose we put a model
that uses a very long chain of thought
into an environment
where it has the opportunity
to sabotage something
and we let it try,
firstly can it, can it
use the chain of thought
to do that task
and well maybe it can't,
in which case probably
we're just not worried
'cause the model can't sabotage,
but if it can then it seems pretty ly
that the models are much
better at doing this task
with the long chain of
thought than without.
So in some sense that chain
of thought is load bearing
and if the chain of thought
is load bearing then it seems
pretty ly that actually there are going
to be explicit references
to the sabotage attempts
in that chain of thought,
you're gonna think of the converse,
if that weren't the case then the model
must be using the chain of thought
for reasoning about how to sabotage
but still managing not to
say anything about sabotage
in its chain of thought,
and that's certainly in theory possible
but in practice seems pretty unly,
at least for models that
have only just become capable
of the sabotage and then
we're not training by default
to be able to obfuscate
their chains of thought.
- I think a massive winner is
in Constitutional Classifiers,
but the classifier can be
so much smaller than the main model
which is checking
something I'm impressed at
how small monitors can be now.
- Yeah that is a concrete
win for monitoring that
I think we're pretty hopeful
will actually work in the real world.
- And shows
that these things are
deployable in practice.
Yeah, I think it's yet to be shown exactly
how useful this is for
misalignment type risks
and whether we should
worry about the monitoring
the policy colluding or
whether AI systems have
correlated failures.
But I do think that it's
de-risked a big chunk
of the technical risk
for deploying monitors in practice.
- Nice so control super
important for the next two years
and we're optimistic we can do it.
Sound about right?
- Oh.
- Hope so.
- Okay, nice.
Thank you for watching this round table.
We've been Anthropic, peace.

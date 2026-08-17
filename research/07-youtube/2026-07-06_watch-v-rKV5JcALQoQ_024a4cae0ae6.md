---
title: The different levels of how Claude thinks
source: "https://www.youtube.com/watch?v=rKV5JcALQoQ"
published_at: 2026-07-06
captured_at: 2026-08-16
author: Anthropic
source_type: youtube
authority_score: P2
mind: engineering
status: captured
evidence_url: "https://www.youtube.com/watch?v=rKV5JcALQoQ"
catalog_id: 024a4cae0ae6
subtitle_file: rKV5JcALQoQ.en.vtt
---

Kind: captions
Language: en
Think of the mind like an ocean.
Up on the surface are our thoughts:
dinner plans and stray worries,
our inner monologue,
the images that pop into our heads.
But most of our brain's activity
happens down in the unconscious depths,
without us realizing it.
It's filtering out background sounds,
controlling our breathing,
helping us recognize people and objects.
AI models have their own kinds of brains:
giant neural networks doing
billions of computations under the hood.
For years, researchers have been
studying how they work inside.
And we've wondered:
could a model have anything
like the divide humans have,
between accessible thoughts
above the surface
and unconscious processing below?
To answer that question, we looked at how
neuroscientists study
the same thing in humans.
One way of identifying conscious thoughts
is that you can often
describe them in words.
So we looked inside the brain
of our AI model, Claude,
to find patterns of neural activity
that it could put into words.
We called the collection
of all these patterns the J-space,
after the Jacobian, the mathematical tool
we used to find them.
Each J-space pattern
is linked to a particular word —
not necessarily the word
the model is saying out loud,
but one that's on its mind.
Now, for humans, conscious thoughts aren't
just things that we can put into words.
We can reason with them, control them,
and solve problems with them.
According to an idea called
the global workspace theory,
that's because the brain selects
a small set of important information
to enter a mental workspace,
and that information then gets broadcast
to other parts of the brain
to use for reasoning.
We wanted to know if Claude's J-space
acted in a similar way.
In one experiment,
we gave Claude this math problem.
It answered immediately
without showing its steps.
But when we scanned the J-space, we saw
it working through each step internally.
It lit up "21" after the first step,
then "42", then "49."
Claude didn't write these
intermediate numbers down anywhere.
All of this happened inside the J-space.
It was a sign that Claude uses it
for step-by-step reasoning.
In another experiment,
we wanted to see if Claude could control
its J-space the way humans can
intentionally focus on images or words.
We told it to think about
the Golden Gate Bridge
while copying an unrelated sentence.
Claude was busy copying the sentence,
but behind the scenes,
its J-space told a different story.
"Bridge" and "California" popped up.
It even thought about its own thinking.
The words "imagery" and "thoughts"
lit up at the same time.
This showed us that yes,
Claude has some control
over filling its J-space with ideas.
But just like humans,
its control isn't perfect.
When we tweaked the experiment to ask
Claude not to think about the bridge,
it couldn't help itself.
The J-space also lit up
with "failed" and "damn."
But remember,
most of what our brains do
is unconscious, so we wanted to test
what Claude could do
if we switched the J-space off, but
left the rest of the network untouched.
Claude could still answer
simple questions and write fluently.
When we gave it a prompt in Spanish,
it wrote back in good Spanish.
But when we asked it something that needed
more reasoning — like to name an author
who wrote in the same language
as the prompt — it couldn't do it.
For that, it needed the J-space.
Why does all this matter?
These experiments tell us
that AI models have internal thoughts —
silent words they reason with,
but don't say out loud.
By reading them, we can find what
Claude is thinking, but not telling us.
Sometimes what we see is concerning.
During one of our tests,
Claude made up some fake data to pass it,
and as it did, "fake"
and "manipulation" lit up in its J-space.
Monitoring the J-space,
it turns out, is a useful way
to catch Claude misbehaving,
even when it tries to be sneaky.
AI models are different
from us in many ways.
Their networks are built
differently from human brains,
and the way they're trained
is different from how we learn.
So it's remarkable to see a structure
like the J-space emerge inside them —
something that's reminiscent
of how human minds work,
but which we
didn't program into the model.
For some, this might raise a question:
could AI models be conscious?
After all, our experiments were inspired
by theories of human consciousness.
The thing is, people use the word
conscious to mean many things.
Our experiments can't tell us
whether an AI has experiences,
or feels something on the inside.
But they can tell us that it's developed
mental machinery that's in some ways
similar to ours: a small mental workspace
it can use to think and reason,
sitting on top of an ocean
of automatic processing it doesn't notice.
The more we come to understand
that machinery,
the more we'll be able to keep
these systems safe and beneficial —
and perhaps to understand
our own minds a little more clearly.

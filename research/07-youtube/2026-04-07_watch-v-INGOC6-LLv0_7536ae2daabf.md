---
title: "An initiative to secure the world's software | Project Glasswing"
source: "https://www.youtube.com/watch?v=INGOC6-LLv0"
published_at: 2026-04-07
captured_at: 2026-08-16
author: Anthropic
source_type: youtube
authority_score: P2
mind: engineering
status: captured
evidence_url: "https://www.youtube.com/watch?v=INGOC6-LLv0"
catalog_id: 7536ae2daabf
subtitle_file: INGOC6-LLv0.en.vtt
---

Kind: captions
Language: en
Most people who use software
every day don't think about bugs.
They don't think about
what can happen if the software
that they depend upon
suddenly is less secure.
That's something that software developers
have to deal with every single day.
Software has always had flaws
and vulnerabilities.
That's not new.
For an average person,
the bugs are, by and large,
not something they notice
on a daily basis, because if they do,
they get fixed.
But then every so often,
there are vulnerabilities
that have real severe impacts.
Like one single bug
that works its way into shared software
that many, many, many
different products or websites use.
One issue just gets
magnified out around the world.
Historically, finding
and patching vulnerabilities
has been a slow, time-consuming,
and expensive process.
If LLMs are now able to write code,
at the level of some of the greatest
software developers in the world,
it can also be used to find bugs
and exploit that software
equally effectively.
These models have capabilities
which are raising the bar
from a cybersecurity point of view
with their ability to help defenders
as well as potentially help adversaries.
We recently developed a new model,
Claude Mythos Preview.
Early on, it was clear to us
that this model
was going to be meaningfully better
at cybersecurity capabilities.
There's a high accelerating exponential,
but along that exponential,
there are points of significance.
Claude Mythos Preview
is a particularly big jump
along that point.
We haven't trained it
specifically to be good at cyber.
We trained it to be good at code,
but as a side effect
of being good at code,
it's also good at cyber.
The model that we're experimenting with
is by and large as good
as a professional human at identifying bugs.
It's good for us
because we can find
more vulnerabilities sooner
and we can fix them.
It has the ability to chain
together vulnerabilities.
What this means
is you find two vulnerabilities,
either of which doesn't really get you
very much independently,
but this model is able to create exploits
out of three, four,
sometimes five vulnerabilities
that in sequence
give you some very sophisticated
end outcome.
And we think that this model
can do this really well
because we noticed that this model
is very autonomous.
It's just generally better at pursuing
really long-range tasks
that are kind of like the tasks
that a human security researcher
would do throughout the course
of an entire day.
Obviously, capabilities in a model
like this could do harm
if in the wrong hands,
and so we won't be
releasing this model widely.
More powerful models are going to come
from us and from others,
and so we do need a plan
to respond to this.
That's why we're launching
what we're calling Project Glasswing,
where we partner
with a number of the organizations
that power some of the world's
most critical code
to put the model into their hands
to allow them
to look at how they can use models
like this to bring down risk
and protect everyone.
And by giving these software developers
advanced tools before anyone else,
it gives all of us
a collective headstart.
It allows us to find things
that we couldn't find before,
and it helps us fix these things
much more quickly.
Working with our partners,
we've been finding vulnerabilities
across essentially every major platform.
I found more bugs
in the last couple of weeks than I found
in the rest of my life combined.
We used the model to scan
a bunch of open-source code
and the thing that we went for first
was operating systems
because this is the code that underlies
the entire internet infrastructure.
For OpenBSD,
we found a bug that's been present
for 27 years, where I can send
a couple of pieces of data
to any OpenBSD server
and crash it.
On Linux, we found a number
of vulnerabilities
where, as a user with no permissions,
I can elevate myself to the administrator
by just running some binary on my machine.
For each of these bugs,
we told the maintainers
who actually run the software about them,
and they went and fixed them
and have deployed the patches
so that anyone who runs this software
is no longer vulnerable to these attacks.
For a developer who tirelessly
maintains software,
a model that can help them
discover vulnerabilities in their own code
and fix them before they can be exploited,
that is an invaluable tool.
We've spoken to officials
across the US government,
and we've offered to work with them
and collaborate to assess the risks
of these models and to help defend
against the risks of these models.
Everything that we do in our lives now
depends on software.
Software ate the world.
Every analog aspect of our life is
somehow represented in the digital domain.
And so all of our daily lives run
on the idea that we can rely on
the systems that power them.
Cybersecurity is the security
of our society.
It is essential that we come together
and work together across industry
to help build
better defensive capabilities.
No single organization
sees the whole picture
and can tackle this on their own.
This is not going to be done
as part of a few week program.
This is going to be the work
of certainly months, perhaps years.
But what I do hope
is at the end of this,
we can be in a position
where the world's software,
its customer data,
its financial transactions,
its critical infrastructure
are safer than they were before.

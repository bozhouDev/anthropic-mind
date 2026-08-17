---
title: "Claude Code updates: When to use Haiku 4.5, Claude Code on web, and more."
source: "https://www.youtube.com/watch?v=CBneTpXF1CQ"
published_at: 2025-10-30
captured_at: 2026-08-16
author: Anthropic
source_type: youtube
authority_score: P2
mind: engineering
status: captured
evidence_url: "https://www.youtube.com/watch?v=CBneTpXF1CQ"
catalog_id: 12aef4f2cf4d
subtitle_file: CBneTpXF1CQ.en.vtt
---

Kind: captions
Language: en
Claude Code is now available on the web.
So, instead of loading up your terminal
or having to open up your IDE anytime
you want to make a change, you can now
delegate coding tasks directly from your
browser or the Claude mobile app. You
simply connect your GitHub account, you
select your repo, describe what you need
done, and Claude handles the rest, all
running on our cloud infrastructure. And
the best part is you can now run
multiple tasks in parallel across
different repositories. So, whether you
have a bug backlog, routine fixes, or a
brilliant new idea or feature you want
to add, you can just spin up a session
or multiple sessions and let Claude
handle them simultaneously. Let me show
you how this works.
So, I'll open up Claude Code on the web
at claude.ai/code.
I'll select a repo. I have a repo
already selected here, and then I'll
give it a prompt. Let's say,
"Add input validation to the user
registration endpoint.
Also, make sure we're using a strong
password on both the front end
and back end API." We'll hit enter, and
we are off to the races. Claude is
working in its own isolated sandbox with
full Git access, and we can watch the
progress in real time. But, while this
runs, let me tell you about some of the
other stuff that we've recently
launched.
The big one is Claude Haiku 4.5. And a
few weeks ago, we launched Claude Sonnet
4.5, which became the world's best
coding model. And just last week, we
followed it up with Claude Haiku 4.5.
And here's the really remarkable thing.
5 months ago, Sonnet 4 was
state-of-the-art. And now, Haiku 4.5
gives you a similar coding performance
at 1/3 the cost and more than twice the
speed. It even surpasses Sonnet 4 at
certain tasks like computer use. Now,
the benchmarks are impressive. 73.3%
on SweetBench verified, 41% on
TerminalBench, and it achieves 90% of
Sonnet 4.5's performance in agentic
coding evaluations. But, the big
question you're probably having is when
should developers use Haiku 4.5? And the
big pattern that we're seeing from our
community is that Sonnet 4.5 does the
high-level problem decomposition and
planning, and then Haiku 4.5 is used to
actually implement and write the code.
Now, this multi-agent approach is
becoming really popular for things like
large-scale refactors or tackling
technical debt. Haiku 4.5 is available
wherever you get your Claude, and it's
available at just $1 per million input
tokens and $5 per million output tokens.
All right, let's check back on our task
and see how it's doing.
[Music]
So, if we open it up here, we can see
that Claude gave us a good summary of
all of the changes that it made
in the service.go file, in the
TypeScript on the front end. And my
absolute favorite feature of Claude Code
on the web is this open in CLI button.
And the reason that I really like it is
you simply click it, you open up your
terminal,
paste in the command that it gave you,
and now I am working in my local
development environment with all of the
context and all of my progress from the
web preserved. So, I can see the
messages, I can see all of the files
that have been changed. I can go into VS
Code and see all of the changes that
were made to the service, sign-up, the
sign-up.typescript file, and much more.
And I can continue right from where I
left off on my mobile phone or the
browser.
Now, I want to show you one final
feature that we recently added to Claude
Code.
I gave it this prompt earlier
talking about adding caching to my
application, but I gave it a very broad
prompt saying, "Hey, I would like to add
caching to my application." And what
Claude Code did is it's going to ask me
a number of follow-up questions to make
sure that it implements it correctly.
So, it's going to ask the caching level
here. Uh should it be database query
caching, API response caching? And I can
choose any of these, go to the next
section, and figure out what my goals
are. Is it to improve performance,
reduce database load? The target area,
is it for the workout data, for the user
data, analytics? Choose the technology,
Redis, in-memory, Postgres. And then, I
can hit submit and have it go and
implement based on the follow-up
information that I gave it.
And there you have it. Claude Code on
the web for parallel cloud-based
development at home and on the go. Haiku
4.5 for lightning-fast coding at a
fraction of the cost and smarter local
workflows with multi-question support.
Claude Code on the web is available now
for Pro and Max users at claude.ai/code.
Give it a try and let us know what you
think.
Happy building.

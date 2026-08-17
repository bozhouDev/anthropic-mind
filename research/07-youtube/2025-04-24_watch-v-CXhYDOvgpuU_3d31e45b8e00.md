---
title: Lessons on AI agents from Claude Plays Pokemon
source: "https://www.youtube.com/watch?v=CXhYDOvgpuU"
published_at: 2025-04-24
captured_at: 2026-08-16
author: Anthropic
source_type: youtube
authority_score: P2
mind: engineering
status: captured
evidence_url: "https://www.youtube.com/watch?v=CXhYDOvgpuU"
catalog_id: 3d31e45b8e00
subtitle_file: CXhYDOvgpuU.en.vtt
---

Kind: captions
Language: en
- The AI world has talked so much
about agents in the last year,
but for a lot of the world I think like,
it's pretty hard to really
understand what that means.
And I think the example of
Pokemon where it's like, oh,
it's like not just a chatbot
where I type in a chat
and I get a response back,
but like it's like doing
this on its own and seeing
and trying things and taking
actions and all that is a way
that I think more people
have been able to like latch
onto what is this agents
thing we're talking about?
- Take one.
- Today we're diving into the story
behind Claude Plays Pokemon.
I'm Alex. I lead Claude
Relations here at Anthropic.
- And I'm David.
I'm on our Applied AI team and
I made Claude Plays Pokemon.
- David,
can we get a broad overview
of what is Claude Plays Pokemon
for those who aren't aware.
- Claude Plays Pokemon is a
sort of experiment with agents
that is hooking up Claude,
our language model,
to the Game Boy game Pokemon Red,
letting it actually try to play the game.
And so we start it from square one,
like start a new game and
see how Claude does learning
how to be a Pokemon master.
- Okay.
There's a lot there that we're gonna have
to get into-
- I know.
- on the technical side
and also just generally,
how is Claude playing Pokemon,
how does it know how to play?
But how did this actually come about?
What was the idea for this
and why Pokemon?
- Yeah, yeah.
So the core genesis of like why
I started this was a lot of,
I work with customers at Anthropic.
I spend a lot of my day
working with our customers
and it was pretty obvious
to me last year that like,
agents was the most important thing
that was happening for our customers.
It's like where they were making value.
And I just wanted some
sort of test bed for myself
to experiment with agents. To get a feel
for how does Claude work when
it needs to take a whole bunch
of actions in a row without
any conversation with a human.
I actually like had
seen someone, before me,
had hooked up Claude to
Pokemon at Anthropic, Elliot.
And so that was sitting
in the back of my brain
and then I thought like I
really want some sort of place
for me to do my own
experimentation with agents.
I am like a Pokemon long-term fanboy.
It was the first game I
ever got when I was a kid,
and that was really like the initial...
And this was like June of 2024 last year
where we had a new model
coming out, 3.5 Sonnet.
It just seemed like the
perfect time to give it a go.
- Why did you specifically,
besides that nostalgic component,
why choose Pokemon as like the test bed?
- Ah, yeah.
- Why not like Claude plays Mario or Zelda
or any other game.
- Yeah.
Pokemon is actually like a
really good setup for this.
Language models, for all
their graces right now,
they're like slow,
they take, you know, one
generation at a time.
Like they basically can
only see like a snapshot
of the game at any point in time.
And Pokemon,
there's like essentially no consequences
for sitting and waiting
for a while, right? - Aah.
- The combat is turn-based
so you just have to press a button
and wait to see what happens.
Movement, not much happens
when you're not moving.
So it's like in terms of games
for a model to be able to play,
it's sort of like perfectly set up.
And then separately,
like why games in the first place is
also like a pretty reasonable question
to get at.
- And one of the fun things
about games is they're like,
one of these unique things
where you do something
for a really long period of time
and get pretty clear feedback,
like am I making progress?
So whether it's a score counter in Pong
that shows you like are you
beating your opponent in Pong
or in Pokemon, like am
I getting gym badges?
Am I making my way through the game?
You actually get some like feedback loop
where you can see like,
is the model actually being successful?
Like can it do this thing?
And so games just like happen
to be this great environment
where you can let a model try
to do something for a long
time and actually like,
by the structure of the games themselves,
get a sense of like how well is it doing
in some measurable way.
- Right. Okay.
So to summarize that, basically,
Pokemon's great because it's turn-based.
It's not synchronous
necessarily.
- You're not playing against other people.
So like we couldn't have Claude Plays
like Call of Duty or something like that,
which does not work right now.
- Yeah, yeah, yeah.
- It would be really hard.
Like if you could get Claude running
at 60 frames a second-
- Right.
- like maybe you could
play some other game,
but practically right now, yeah,
exactly right.
And then games are great
because they're kind
of their own simulated
contained environment-
- Yeah,
that's exactly right.
- where you can go
through an entire process.
- We have Claude Playing Pokemon.
You've started to work on this,
but how does that actually work?
Like how is Claude
controlling the character
in the game and actually-
- like making things happen?
- I guess in general,
like you can think of the
prompt for Claude to start
is basically like you're playing Pokemon.
It's really simple.
I just tell the model it's
playing Pokemon and that's it.
And then you hook up Claude
with a set of tools that it has
to be able to actually
interact with the game.
And you know, it's actually
a pretty simple set of tools
as the minimal set you
get in a Game Boy game.
It's like pressing
buttons on the Game Boy.
So basically you tell Claude
it's allowed to press A, press B,
hit up, down, left,
right, that kinda thing.
You describe that tool
to it behind the scenes.
Like I have to implement
some code that actually says
like when Claude says it wants to press A,
I need to make it so that
that actually goes presses A
on the emulator.
- I see.
So the tools are like
options for next action
that Claude can take-
- Exactly, exactly.
- and then you get the output from Claude
and then translate it into the action.
- Bingo,
so-
- the whole game is essentially Claude
taking a series of actions,
mostly just pressing
buttons one at a time.
Now the key feedback loop
in how it does this is
every time it presses a button,
we send it back a screenshot.
- Ah, okay.
- So Claude actually sees
the screen of the Game Boy.
It can see like I'm in this room
or I'm in a Pokemon
battle or whatever it is.
And so the next thing I wanna do is
press A to talk to this person,
or to select this move, or whatever it is.
And then it kinda just does that forever,
you know, iterates on that.
Now practically we've actually given it
a handful of other tools
that help it do things
like manage its memory
over a long period.
- Claude has a limited amount of context.
It can't fit actually like
a whole Game Boy rollout
like play in one context window.
So there's a lot you need
to do to actually manage
the details of how to get
that right.
- But at its core, it's sort of like,
while true, press buttons-
- and see if you could play the game
and give it some feedback along the way
to know what it's looking at.
and so as you've been constructing
that kind of harness around Claude
to get it to play that-
- Yep.
- and you're running into
some of those limitations,
one of the things you've encountered
is like the memory issue.
- Maybe you can speak a little bit
on that around-
- what you had to do specifically there.
- Yeah, I just like I'm gonna
zoom outta that question
one second first-
- which is like there's all sorts of ways
that people have come up with
to build these like agents
that have to take actions for a long time.
So you know, there's this like
general concept of an agent,
which is just like the
model needs to take some set
of actions and we really don't know
what it is ahead of time,
but the model's going to have to like,
do something, see what happens,
do the next thing, learn.
And people have come up
with all sorts of crazy ways
to wire up that thing to
try to make models better
in any number of situations.
And so I actually,
like the first thing I did was just try
other people's ideas basically,
right?
- Okay, yeah.
- So there's this paper called "Voyager."
That was the first thing I tried.
It was I think probably like
a 2023 paper from Nvidia
that they used to play Minecraft.
And so that was like
the first thing I tried
and that gives the model all sorts of,
I won't dive into it,
but like a lot of fancy tools and stuff
and I've like sort of like stripped back
to my own simple version of it from there.
So then like I guess
what you start with is
this sort of like the
world's simplest version,
all you can do is press
buttons and get a screenshot.
And the first wall you run into is
what happens when you hit
200,000 tokens basically,
which is the limit of Claude.
Practically that's like
something like taking 50 buttons
or something like that and
getting a screenshot back
fills it up.
- So you press 50 buttons
and you have barely started
the game in Pokemon.
And so you run into
this wall pretty quickly
where if you do nothing,
you just run outta space,
and then you crash and you're done.
And so one of the first things
you need to figure out is
what do I do when I
run outta space, right?
And the two like key insights here
of how I went about this at least,
and I think that's actually
pretty well reflected
like in the industry these days
about how you think about agents
are some concept of long-term memory.
So I give Claude some ability
to basically explore a memory
and what I call a knowledge base
where it just basically says
like I just did this thing
or I have these Pokemon or here's my goals
and I've checked off six
of them or whatever it is.
And and you'll see it sort of
like make incremental updates,
and that persists throughout time.
Like it can constantly always look
at that and keep track of something
because then the second key is
once I fill up the context length,
I have Claude summarize back down
to remove the 50 actions it just took
into one short summary.
- So you delete a whole
bunch of stuff and reset,
but it has this sort of like
set of long-term memories
that give it some ability to sort
of like remember things
over the course of, potentially,
I mean if you look at
the Twitch stream now,
like it's been running for
three weeks continuously.
It's probably summarized
itself a few thousand times
by now.
- Wow, wow.
- And so it's really important for it
to have some sort of
long-term memory to remember
the last three weeks of what it's done.
- So the long-term memory there,
it writing out to this
external knowledge base,
which is basically like
a plain text file-
- is like kind of like the movie Memento
where they were like writing sticky notes
on the wall and everything to like track,
all right, I've been here, I've done this.
- Like if you just do it... if you
naively were to delete the message,
Claude would have amnesia
and it would be like,
how did I get here?
- Why am I part way through Pokemon?
You told me I'm just starting
a new game. What's going on?
In some sense,
this is the Post-It notes
that Claude leaves itself
so that when it has the reset
and you remove a lot of
what's recently seen,
it has some way to remember like,
all right, I know what I've done so far,
I have a sense of where I'm at.
Maybe I've even like learned some lessons,
like maybe I've learned some
things about like this strategy
works really well.
- Ah.
- I've learned some stuff
that like I wanna keep around
because for the next, you know,
10 minutes that I have, it's
gonna be really helpful.
- That makes sense.
And now I think it's
probably pretty important
to clarify here or maybe
even explain further,
have we trained Claude on this?
Like how does it know
actually how to navigate
around Pokemon?
- I mean you're not really
giving it that many instructions.
You're not like giving it
a how-to guide.
- No, I know.
This is part of the fun part.
So we haven't trained
Claude on Pokemon itself
at all.
- Claude obviously like knows
something about Pokemon.
Like if you go to claude.ai
and ask it questions like you'll notice
that it can recall some like general facts
and there's enough in the pop culture
that of course Claude knows
- Through the pre-training process,
yeah.
- Exactly.
And it even knows like some
of the broad strokes
information about the game.
So it knows that like the
first gym leader is Brock
and so it has some sense of
like the structure of the game,
but the details, it really
knows nothing about it.
In fact, sometimes it thinks
it knows things and it does it.
This is one of the hard
things you have to fight with.
But that means that even without sort
of like specific training,
knowing a little bit about what Pokemon is
and some of the motivation of it,
it has to figure out everything else
sort of in the intermediate space.
And so you'll see it,
like some of the funny
things you find out,
like to see how this
actually works in practice is
you'll see it talk to an NPC
that gives it some tidbit of information.
Like at the very beginning it says,
"Professor Oak is next door,
you need to go talk to him."
And that's what like mom
tells the Pokemon character.
So Claude's mom in Pokemon tells Claude,
"You need to go next door."
And then Claude will like
very rigorously be like,
"I need to go next door."
Like I need to go find
Professor Oak next door,
and it will be on a mission
and occasionally it'll get like over...
So the funny fact about Pokemon Red is
it actually lies to you
like mom lies to you.
- Professor Oak is actually not
next door.
- You have to go find him elsewhere.
I've actually seen Claude
get derailed on this
because it's like, "My mom told me."
- So trusting.
- I mean, I have to believe mom.
Like it's my mom. She
told me this is true.
And it will get stuck there
like really looking next door
for Professor Oak for a very long period
of time, funny enough.
You really do see over the
course of it playing the game
that it like, by interacting
and just seeing the screen,
seeing what people say, signs say,
just this experience of what
happens when it tries stuff
that it like actually picks up the tidbits
that are the core of where it's going,
what it should do next, that kinda thing.
- So this is like a
pure playing experience.
We didn't like give it some pathway
to follow-
- No.
- or tell it like if you
run in this situation,
do this sort of thing.
It's just like really
interacting with the game
as a human would in that sense.
- Yeah, and maybe just like on a,
why am I doing this level-
- my goal is not to beat Pokemon Red.
Like I did that when I was six.
Like this is not the
the gold standard, like,
and I'm pretty sure you can write
a program to beat Pokemon Red
if that's your only goal.
- I wanted to understand
like, how does Claude work?
Like how is Claude at this?
Like can Claude handle this situation?
And so that end like it would
be no fun to just give it
the answer guide.
- Like I wanna find out how Claude figures
out the answer.
- And so most of how I've
structured everything
and most of how you like
what you actually see
when you do this is like
a pretty bare bones,
like Claude has to go
figure this out on its own
'cause I'm curious and we are curious,
like how does Claude even try doing
this thing-
- or does it try to play Pokemon?
- Right. We're not trying
to get Claude to be Pokemon.
We wanna just generally
evaluate Claude on agentic tasks
and figure out where it's at.
And I don't think anybody's making
their buying decision for a model
on which model plays Pokemon the best.
So this is really for
our own understanding.
So you've been doing this
now for a good bit of time.
- Yeah, too long.
What's it kinda been like
over that amount of time
with the different models.
- As we've continued to iterate on Claude,
can you just walk us
through what that journey's looked like?
- So I mentioned I started with 3.5 Sonnet
as the first model I hooked up,
and I wasn't very good at Pokemon.
So in Pokemon you started the
second floor of your house
and to get your first bit of progress is
like finding the stairs in the top right.
And I probably spent like
three days of working on this
before I got the model to find the stairs
in the first room.
- Wow.
- I remember just being incredibly hyped
the first time it like
got out of the house
and then actually like
got to the cut scene
where you potentially can
get your first Pokemon.
That was like the pinnacle
of my achievement with 3.5 Sonnet.
And I thought I had really
like done amazing things
back then when when I had that happening.
And that was like better than any
of the experiments we'd seen in the past.
And then I kinda like tucked it away,
like this has been a fun project,
I learned some stuff but
like that's about it.
And then we released the
refresher 3.5 Sonnet in October
and I picked this back up
and you could tell it was a little better,
like pretty noticeable.
So it like very consistently
found the stairs, amazingly.
It pretty consistently
with like a relatively
predictable timeframe
would figure out how to
get a starter Pokemon.
We actually saw it like win
a battle the first time,
start moving a little
bit the right direction.
After that it was really slow,
it made a lot of dumb mistakes
but like you could see,
you could squint and see like
it had clearly gotten better.
A lot of that was just
like not getting stuck,
like not thinking the game was bud,
like having a sense of
different strategies
and things to try.
We were actually like kind
of excited about that.
Again, like wherever Claude is,
you're just so excited when
it gets like one step further
that it's very fun to
watch and engage with.
But it was still like,
I remember someone asked
me back then, like,
"How did like random button
presses do in comparison?"
And Claude was like this much better
than pressing random buttons,
you know.
Like it was better but like,
not a lot better-
- than pressing random buttons.
And so again, I like tucked
it away. It had been fun.
And then we got to testing 3.7 Sonnet
and it was just like way better
and it was pretty obvious.
One of the first moments
that I really realized
3.7 on it was way better,
I was going through watching it play
and I realized there was this
like terrible bug in my code
where I wasn't showing Claude all
of the information it needed
to play the game.
- Oh, wow.
- I had this like thing at the time
that was helping like show it a map
to try to give it like some extra sense
of how to navigate.
- And 3.7 was already doing way
better than 3.6, the new 3.5 did.
And I was like, "Oh, this
might be like pretty real."
And so I pretty quickly
became like deeply obsessed
with like, we gotta find out
how good this actually is.
And I started like grinding
harder than ever on
like giving everything,
all of the tools the Claude
really needed to be successful
'cause you could see it had
like the core material it
needed to make progress.
Over the handful of weeks
that we did testing of it,
it was like pretty clear that
Claude was quite like capable.
Not a star yet, we can
get into that I'm sure,
but it started actually playing the game.
It beat a gym leader one day
and everybody freaked out.
You know, that's like the same thing
that people can see on the stream now
where it's slow and challenging sometimes,
but like it makes meaningful
progress in the game.
- That's fascinating.
What do you think that shows actually
about like the model's
improvements themself?
- Why is it that it's actually
getting better at the game?
- This is one of the fun
things is I actually like kind
of know a little bit about
the models because of this.
I think there are a few things
that have made a difference over time.
Surprisingly the vision,
which is the hardest thing,
like when you look at the game,
like you notice that the
Claude's not very good
at understanding Game Boy screens.
That actually hasn't improved
a lot.
- Like the model has
made all this progress
and its ability to actually
like stare at a Game Boy screen
and see what it's going on is
about as bad as it always has been.
So then it's like how is
it actually making progress
if it doesn't have a better fundamentals
of what's going on?
- And I think the things
that you've noticed
or that I've noticed the most,
and this actually tracks a lot
with what we focus on at Anthropic,
is that Claude is just getting
a lot better at coming up
with strategies of things it should try,
of questioning a lot of the
previous strategies it had
and thinking like maybe the mistake isn't
that there's a bug in the game,
it's that like I had a bad strategy.
So like what is the other
strategy I could try?
If the last thing I tried didn't work,
what should I try next?
And sort of like backtracking
to figure out good
different things to try.
There's like a certain
tenacity to like trying all
of the different ways you could try
a problem and figuring it out.
And I think that was the jump that got
from 3.5 to the refresh in October
and then that was like huge jump
in that exact skill with 3.7
where now it's just like way more willing.
And even though it's slow,
like I think if you watch the
Twitch stream for two hours,
you might think there's
no way this thing is
good at questioning itself.
- But the amazing thing is like over time,
it does typically step back and think,
like, what's the next thing I should do?
And that ability to sort of like triage
and understand different ways
to go about solving a problem
and getting better at that is
like one of the biggest things
that I think has improved
with our models over time.
It's one of the biggest
things that enables agents
for all sorts of things, not just Pokemon,
to be really successful
and it's the thing that's
made it pretty okay
at playing Pokemon.
So the fact that it's improved
on all these capabilities
and it's progressing through the game,
how does that actually
extrapolate out into other areas?
Where are we witnessing that
improvement with, you know,
maybe more real life-
- use cases?
- You know, it's funny
like at squint value,
Pokemon couldn't be more
different than writing code
or all the other stuff
that people do at Claude.
- But this core thing,
like the ability to come
up with a plan that's good
to try something, to see if
it's working or not and adjust,
to understand like what are
the different strategies
available to me and just sort of like,
be willing to try them, fail,
update what you should be
doing with new information,
that is like the core
recipe of I think like a lot
of what makes agents good
in a lot of scenarios.
So one that we probably
spend too much time talking
about is coding, but like
when you are writing code,
you write something, you see a test fail,
and you have to think
like, what did I do wrong?
Like how do I do better?
Like what should I try next?
What's the next strategy?
And models do this all the time
and there's like one thing between a model
that can get it perfectly
right every time all the time,
but sometimes you just don't even
have the information you need.
Like you don't know until you run the test
that you miss something.
And so the ability to know what
tests should I run to learn,
when I find out something,
how should I incorporate that,
how should I update the strategy,
I had to go write this
piece of code or whatever,
that's the same thing.
- And I think that's
actually like, any industry,
like when you think about if were
to go search the internet
for something, it's like,
I click on something, I
notice the page is bad,
it doesn't have the fact I need
or maybe it has like part
of it but like I realize
because of that I need to go search
something else to get it right.
Like all of that,
building a strategy
and understanding how to like
incorporate new information
over potentially like a
lot of different actions
just has like really broad
reaching applications I think
for how people build things with Claude.
And it just like maps really intuitively
to how we as people think
about solving complex problems,
so.
- Right,
kind of that planning,
and then executing loop-
- doing, taking an action, stepping back,
reevaluating and taking another action,
Yeah.
And I think we a lot of
times we as people think
about that on like the
really granular scale.
Like when I'm doing a
menial thing in my job
I don't necessarily think like, oh,
I need to reevaluate my action
and try something different.
But like that's still
what is, compiled down.
Like that's what's happening with me is
like I'm getting a piece of information,
I am seeing if that means I need
to like what the next step I need
to take is-
- and having sort of like
this continuous feedback loop
and a lot of that is
what's gonna make Claude
a useful colleague, assistant,
whatever it might be going forward.
- Yeah, I mean I guess I can
see it in myself sometimes too
when I have like I have a to-do list
and maybe I wrote it
at the start of the day.
- And I go through some meetings
and then all of a sudden
I get new information
or I take an action, I talk to somebody,
and now I have to return
to my to-do list-
- reprioritize, move things around.
And it's that same sort
of like loop-
- Yes.
- that Claude's learning here as well.
- Yeah, that's exactly right.
And you can just notice
it getting much better
at that.
- And the thing and maybe
to make it concrete,
a thing that would happen in the past is
it would write out its to-do list
and it would get like hyper
fixated on it maybe, right?
It wouldn't be able to
successfully incorporate
this new thing it learned.
- A good example which
you still see sometimes
but you see a lot less
is like Claude's like,
I need to go to the top left in Pokemon
and then it'll just walk
into a wall for hours on end.
And if the model is really fixated
on walking to the top left,
like yeah you keep just walking
up until I get there.
- But if it's walking into a wall,
like it eventually needs to
step back and be like, hmm,
maybe I maybe I need to be doing
something else first.
- And that's the kinda thing
where that's what happens in Pokemon,
but yeah it's like super
translational to a lot
of the other things we do.
That's a good parlay into
this next question I had
around what are the current kind
of funny moments we've been seeing?
I mean, it's not perfect quite yet,
you know, it's got a lot better
over the past eight or so months,
but we haven't beat Pokemon.
- And there's definitely
been some funny times
along the way.
- Any stories you could share there?
- Yeah. Claude is not perfect
just yet.
- I think like I have a
laundry list of the things
that I think Claude still
needs to get better at.
I'll start by harping
on some of the things
that like Claude doesn't quite do well yet
and that are interesting
and they tend to be
pretty funny moments.
- One of my favorites was related to,
its like visual acuity.
It doesn't see the screen very well.
So I was watching it play one time
and I went to bed and it
had walked into a building
and it thought that a doormat
in the building was a dialogue box
and you have to press a
button to dismiss dialogue.
And I woke up the next day
and it had spent eight
hours pressing that button
trying to dismiss the dialogue box,
like not realizing that like it was like,
it's like cycling through the dialogue,
thinking it had to advance.
And so there's a couple of things
that are like a little bit
interesting there to unpack.
One is like making a mistake
where you become really confident.
Something as a dialogue box
is a pretty bad mistake.
And so if you have like
a core understanding
issue that's pretty bad.
The other is time.
Like pressing a button
15,000 times to Claude
doesn't really mean much.
- Like to me,
if I was spending eight
hours pressing buttons,
I'd be like, I'm pretty tired
of pressing that button.
Like my thumb hurts.
For Claude, like 15,000 button presses,
like who cares, keep going,
you know?
It doesn't know how much
time has even elapsed
And so there's like some
intuition space around like,
the ability to comprehend
how long is too long,
like what is time-
- that kinda thing that I think
it's a bit funny and
it needs some work on.
So that's like one general
category though is like seeing...
Another fun story I have that's more
on the like planning and strategy side.
I was watching it play one time
and it got into mountain moon,
which is for the people
who watch the stream,
like a place where it really likes
to get stuck for a long period of time.
And it had one Pokemon at the
time in this run that it had
and it had the option to learn a new move
that was a not attacking move
and you really need attacking.
Like if you don't have an attacking move,
you can't beat other Pokemon.
And it wanted to learn that move,
but it just was like very excited.
And so it like pressed A a bunch of times
to like clear the dialogue
to get to that point
and it accidentally pressed
the button too many times
and it deleted its only attacking move.
- Oh, no.
- And so now it's like stuck here
in this part of the game
with no moves essentially,
like nothing to do,
like no way to progress.
And that's a little bit of like,
like when there are destructive
consequences sometimes,
like understanding that I need to go slow.
- Like something could go wrong wrong
if I press A 15 times
without checking what
happened in the middle.
And the thing you'll notice
in that is like sometimes
it's intuition is that like it
will be able to stop itself.
Like if I wanna press A 15 times,
like I'll just say press A 15 times
and then if I see something
go wrong, I'll just stop,
because Claude like doesn't quite have
this intuition that like-
- I'm a language model.
- I don't have the op, like I-
- It's not actually pressing A.
- This tool is not giving me
the affordance to stop.
I'm not checking in the
middle what's going on.
- And so there's a little
bit of like understanding
about like and I think about
this as like a self-awareness
of my limitations, the situation,
that kinda thing with Claude
that it sometimes struggles with,
and that's actually really important.
Like one of the things I
wish the most of Claude was
that it had like a
slightly better awareness
of hey, maybe I'm not
good at seeing the screen.
Like maybe the fact that
I'm walking into this wall
over and over and over again means
that like I need to learn something
at a meta level about my own capabilities
and I should think about a
completely different strategy
rather than like walking into the wall.
And so there's a little bit of like,
its ability to sort of like meta learn
about what it is, what
its capabilities are,
that kinda thing that I think it still has
a lot of room to get better at.
And then maybe one last
thing around frustration
and one of my favorite stories.
So again on Mount Moon, it typically,
the model takes like two days to get
through Mount Moon.
- Oh, gosh.
- It's a maze.
Like, it's like it takes a long time.
On the stream, I think-
- What makes Mountain Moon so hard?
So one of the things Claude's worst
at right now is like navigation,
like wandering over a long period
of time.
- It doesn't quite have
a good understanding
of like spatial awareness in
general, I guess, I would say.
And Mountain Moon is like the first place
that really stresses where you need
to make like navigate a pretty long maze
of corridors to get to the right spot.
And there's also sorts
of like little nooks
and crannies to get stuck
and you need to do a pretty
nuanced like traverse
through a series of
paths to get to the exit.
And it just takes Claude a long time
to like actually find all of the paths
and get a sense of where it is
and where it shouldn't
go and that kinda thing.
So one time I was, in fact the
first time it ever got there,
when you go through Mount Moon
there's this like last thing you do,
which is you have to get
a fossil in Mount Moon.
And once you get the fossil,
you're like 15 steps from the exit
from finally getting out the other side.
And so the first time I was ever watching
Claude in Mount Moon,
it goes through like three
days, gets the fossil,
and it's like for me,
I'm like, this is it.
It's finally happening.
- When was that?
- I didn't think this
was ever gonna happen.
I thought this was hopeless.
I was like ready to write this off.
We were going to publish that benchmark
we had-
- and this was going be the end of it.
Like that's fine.
We got one badge,
like we're excited.
- Cap it right at Mount Moon.
- And so I'm at like peak hype,
like we're gonna get out.
This is it. We can keep
going at the game, right?
And then it proceeded to get lost.
It's 15 steps away,
it turns around and goes the
other direction, gets lost,
and then it uses this item
called an escape rope,
which teleports you back to
the last place you rested,
which is like outside the
beginning of the cave.
So it spends three days navigating,
is 10 steps from the exit, turns around,
completely noobs out
of the situation-
- Oh, my god.
- like goes to the beginning again.
And I just had a meltdown,
'cause it's the funniest
thing you've ever seen.
I mean, it's objectively
hilarious content,
but like I was gonna cry
'cause it was-
- I woulda loved to read
its like transcript on that one too,
probably.
- I did.
It's sad 'cause it doesn't
even realize.
- It doesn't even know.
It's just like, this is
a disaster. I'm lost.
Like best-case scenario,
you just like get to the
beginning and try again.
It's like yo, we're so close.
- On the dialogue box piece,
how does Claude-
- actually break out of that?
- Is there tactics or
is that like, all right,
we gotta reset the game and
start over sort of thing.
- Yeah, this gets to like the
little details of how you can,
like how I've actually come
to understand what it means
to build good agents because like,
there's a train of thought
that exists for a while
of like build the most
big complicated system
to try to patch every little
weird quirk that a model has.
And that's actually really hard to do.
How I think about it now
is I watch the model play.
Like I give it a pretty, simple,
straightforward way to play the game
and I watch and I see what goes wrong.
And no way to find out
that it's gonna get stuck
for eight hours trying
to dismiss dialogue box
than waking up and seeing it stuck
for eight hours with that.
And then you can sort of like build
a how do I give it the right information
it needs to be able to break out at this.
So like one really simple
thing that actually helps is
just like giving it a step count
every time-
- Oh, okay.
- it's like taking an action.
So saying, hey, like this is action 2,400.
Your next action will
be 2,500 or whatever.
And then you can also say like,
because one of your limitations is
you don't have a great sense of time,
you may just wanna keep track
of how long you've been
trying to do something
and if there's something you
should learn from that fact.
Like if you've been trying for something
for a really long time,
like maybe it's a good idea to reconsider.
And that's actually enough
in the case of Pokemon
to like get it to keep track of how long
it's been pressing A.
- Oh, interesting.
- Like if it's been
pressing a for 10,000 times,
like if you at least
like just by telling it
to keep track of that,
it has some hope of being
able to realize this is weird,
I should get out of it.
This is just like a little like,
it's literally just like
thinking about the information
that I need to give Claude
to be successful, right?
Like Claude doesn't have
any innate sense of time.
Like it does not.
Every time you run it is
completely new to Claude,
and that's not true for humans.
Like we have a great sense of time.
Like the sun goes up and down,
it's very easy for us, right?
And so this is just
like I've thought a lot
about as I've gone on this like
learning about what Claude,
like what affordances it needs to be able
to understand it situational
a little bit better
and then just providing it
with that set of information.
And so a lot of the iteration I've done
in the last few months on
this is just sort of like,
watch, see what it struggles with,
understand is there some
like piece of information
that can give Claude,
that will help it have more of the tools
that needs to reason about the situation.
And then often that's like the best way
to start getting progress on this.
- Okay. Cool.
And that feels very similar to I guess
some of the general prompting
guidance that we usually
give customers, right-
- around like hey if you
were to write a prompt
and give it to somebody
and they knew nothing
about this situation,
they were in like a basically,
a box with no windows-
- and they had to do this task,
would they be able to do it?
- And if you don't
provide all that context-
- That's right.
- And this is just kind of the next level
of that agent.
There's a small danger with agents.
Because the whole reason why
you'd ever use an agent is
you can't sort of
enumerate all of situations
it's gonna get into,
if I wanted to beat the
first part of Pokemon,
an agent isn't what I would do.
I would give it a series of like,
here's what you need to do first
and here's what you need to do second
and here's what you need to
do third and things like that.
And that was my only goal, right?
And why you use an agent
is you can't do that.
Like it's these scenarios
where you don't know
what situation is gonna be
presented in front of you
and you really need to lean on the model
to navigate and use its own
intuitions for how to do it.
And so there's a danger to get too far
down that rabbit hole of like,
I'm going to try to
predict every single thing
and write that all
into a prompt.
- You'll see some Frankenstein
prompts if you like,
try to anticipate every possible thing
that the model could
end up struggling with,
which is why I think
it's like just important
to be measured and like read a lot
and like the thing I've
learned probably the most is
just like watch it, read what it says,
see what it's struggling with,
understand and just find out
like the most minimal ways
that you can give it a
little bit more context
rather than trying to like work
around every single detail.
Maybe switching gears a little bit here.
So we included Claude Plays Pokemon
as part of our Claude 3.7
Sonnet launch.
- And we had the benchmark
with all the lines-
- of how far each model's got through
the different gyms.
- And then we put out like
an article kind of explaining it.
What was the reaction like by
like just the general public
and people more in the AI space?
- I guess like maybe to
tell like a little bit
of the backstory of that-
- because that like, this prompted it.
Like, you know, as I've
been hacking on this,
like we have a Slack channel,
Claude Plays Pokemon,
that I've been like just like
posting updates on this on.
And this has like had a history of like,
at first there's a lot of
people who just, it's fun.
It's the nostalgia hit.
- Like it's the same content
of why someone would tune
into the stream that we have.
It's just like fun to
watch. It's exciting.
Like it's exciting to see
the model of big progress.
This is kind of our baby is Claude
and so like seeing it you just are like
you're proud for it.
- You're rooting for it.
- You're rooting for it,
you're proud of it.
- And so that was like the
initial like internal traction
that had me excited about the project is
like people just like had
so much fun looking at it.
And there was this like
switch that flipped
for 3.7 Sonnet which was like,
oh, we're like learning something
really interesting about this model.
Like this is a thing we really wanted
was for a Claude to be
able to build better plans
and act better over
longer periods of time.
And like Pokemon's actually like
a pretty reasonable way
for us to test this.
And so suddenly I actually had
like researchers coming to me
and saying like, "Can we measure this?
Like can we look at this?
Like what is actually going on here?"
And so there was this like
small breakthrough moment
like a week before we ended up
launching the model that was like,
"This might actually be one
of the better ways we can tell the story
of like what is this
thing we were trying to do
by making Claude better
over longer timeframes
and is this a good way
for us to understand it
and for us to tell this story?"
And that really like snowballed into a lot
of like, A, how I thought about it,
it's like maybe this is actually
like a pretty crisp way
for us to understand
what is 3.7 so good at
and how should we use it,
and B, like this is probably
an entertaining way to show it
to the world too, right?
- In a pretty tight
little sprint we decided
like this is a thing we
should put out in the world.
We should make a graph that shows
how good it is to compare to other models.
We should put together a Twitch stream
and let people like see and experience
that same sort of fun and
excitement we had seen
and also like the feel for
what's actually going on here.
We should talk about it
in our research materials
'cause it like helps people understand,
and that really was like
the inspiration of it.
- I think that just
makes like a great point
on we wanted to be able to tell a story
about how Claude was improving in this
other kind of dimension.
- And that's getting
harder and harder to do
as like the models get better.
- And we're almost having to
like move into this regime
of equipping the models
with like real life
things now-
- instead of just like artificial,
forced-
- test cases and benchmarks.
Anytime you have a like
a little tiny test case,
it's like pretty hard,
like models start getting to a 100%
really fast.
- And we just get excited
anytime there's a evaluation
that a model's getting 30% on, you know.
Like it's getting a third of the way
through the game roughly,
like that's amazing.
We know something about it's like not
good enough to do this but
it is good new to do this,
that's like pretty good information.
That was like one of the interesting...
I never had that in my head as like,
why I'm doing this, but it became,
I think this was like the moment
where it actually was
like very interesting
to look at and understand.
But then do you wanna talk
about like what happened
afterwards?
I mean, so we launch it.
We include it in the materials,
we put out the blog post,
we start up the Twitch stream.
- And then what happens next?
- It was a lot more
popular than I expected.
I guess I shouldn't be too surprised.
The AI world is pretty exciting these days
but it has had like a
remarkably large set of people
who were like excited
to watch and experience
and go through the same thing as me.
For like the first two weeks
there were like thousands
of people at any given point in the day,
24/7 tuned in watching
crazy, which is amazing.
People were making...
There's like a subreddit that was started.
People are making memes and fan art
and I saw a song the other day
that someone made about
it, which is amazing.
So like I guess at like
the most grassroots level,
it's had this like very fine community.
One of the most amazing
things to me about it is,
I don't know, I am skeptical
of online chat rooms,
but the chat on it-
- has actually been like
really positive and fun
and people are like excited
for Claude, talking about AI,
talking about agents, like
engaging with this thing.
It's been like kind of
amazing at how positive
and fun it has been to have
a community around that.
And then the like other side
that I've found like really,
I guess like rewarding
is I think this has just
like been a way that
people actually can see
and understand what an
agent is for the first time.
Like the AI world has talked
so much about agents in the last year
and I think like when you
are used to being a person
that like writes code
or uses coding agents,
like that might ground pretty easily
in what we're talking about.
But for a lot of the world,
I think like it's pretty hard
to really understand what that means.
Pokemon where it's like,
oh, it's like not just a chatbot
but like it's like doing this on its own
and seeing and trying things
and taking actions and all that is a way
thing we're talking about.
And I think that's great.
Like I think it hopefully
can like bring more people
into the dialogue of:
What are we building here?
What are the possibilities of AI?
How can I think about how
this is going to impact me,
how I can use this to the most impact,
how I can like accomplish more and more
by not just thinking about it as a chatbot
where I type in a
question and get an answer
but as a a collaborator that I can ask
to go do something that's complicated
that takes time and it can actually do it.
And I don't think most people
are gonna go ask Claude
to play Pokemon and and see what happens,
but like I do think it's been a way
where it like resonates a little bit more
than what some people have
been able to in the past,
which has been like maybe
my favorite thing out of it.
- Yeah, I love that. I think it's so true.
I've had so many people
that aren't necessarily in the AI space
reach out to me and ask,
"What is this whole thing?"
- "Why is Claude playing Pokemon?"
And when they start to dig
into it more-
- it's like, "oh, okay.
I kinda understand now where these things
are headed"-
- "what they're able to do."
- It gives that more like visceral feeling
about-
- where models are currently at.
- And the Twitch chat is absolutely great.
It's probably one
of my favorite things-
- It is.
- like of any of our launches.
- Just to like see all
these random strangers
from across the world-
- like cheering for Claude
and making memes-
- out of like Claude-
- It is amazing.
- when fails in Mountain Moon.
We launched the stream
on the day after we launched the model.
And then it was the following Saturday
that it finally started
going down the path
to get out of Mountain
Moon for the first time
and it had spent three days there.
- And man, the chat was electric.
- Chat was blowing up,
- Going crazy,
it's going crazy.
I was sitting there on my couch
next to my wife, who I was ignoring.
I'm so sorry to her
and just like glowing as
people are just like having
so much fun-
- cheering for Claude and rooting it on
and like getting so hype and yeah,
I could never have imagined how much fun
having like an army of people
cheering for Claude would've been
before we put it out there.
I think we need some
way Claude can interact
with colleagues-
- in the next iteration
of this.
Claude deserves to know
how many people love it.
- Yeah and it should be able to talk back
with the chat and like make-
- call outs and everything
and be maybe go full Twitch streamer.
Does Claude have a favorite Pokemon?
- Ah. So Claude is very
tactical, very pragmatic.
So there are a few things I'll say.
As a starter, Claude really
likes to go for Bulbasaur.
It doesn't always succeed.
Sometimes it gets lost trying to find it
but it likes going for Bulbasaur
'cause it has a type advantage
in the first two gyms.
Really good strategic choice.
So it gets obsessed
with the strategy-
- Strategy choice.
- Very rational Claude at the beginning.
That said, there are a
few Pokemon that like,
it always seeks out in a run
that are like the rare ones.
So it loves catching Pikachu.
- If it ever sees a Pikachu,
it gets really obsessed with catching it.
It also digs in Mountain Moon.
It really likes to go for those.
So it likes the rare ones.
- That's what I'd say.
When it sees something
that it knows is rare,
it goes right after that.
- Yeah, that's like the same strategy
of my 8-year-old self in Pokemon.
- Yeah, yeah, yeah, yeah.
- We're on the same page there, Claude.
- Last question.
Do you have any advice for folks out there
that might have watched
Claude Plays Pokemon
or they're just getting started
building on top of Claude
for how they can start thinking
about building their own sets
of agents and any takeaways
just generally-
- from this whole experience?
- The biggest thing for me,
and I actually think this is like advice
across all of adopting AI,
I've given this people or this advice
before in different contexts is like,
start by doing something you
love, like that just fun.
Like this is not related to
AI at all, but it's like,
I think the difference between people
who crush it and like
figure out how to adopt AI,
it's just like a certain amount of time
coming to some understanding
of what models are good
at, what they're bad at,
what can I trust it with?
How do I really gain trust in this model?
And by starting with something
that you like are excited
about, that's fun,
that you're gonna wanna
like boot up at 7:00 p.m.
after a day of work and
like actually go hack on,
like that was the thing that made Pokemon
so magical for me is like
I would get done with work
and it was like the first thing
I was excited to do, you know?
And it meant that I had that so much space
to really get to learn
and know this model.
And there's all sorts of
like technical details
I could tell you about how to build agents
that I've learned, but
like more than anything,
you learn by interacting
with and experiencing Claude
and finding the way that like
it's gonna set you best up
to be excited to spend
six hours with Claude
or whatever it is on a week
is the thing that I think
is gonna get you into it.
Because once you've done it once,
it's like much easier for me to reason
about like how would I go build
an agent for something else?
And it's also for all the reasons
we talked about that are translational,
like the things that Claude
is good at in Pokemon,
actually tell me something
about what I can expect
about different things
in how I use Claude-
- what I need to look for
if it's good enough at this.
Like how to think about finding out
if Claude can handle this part of my job
that I wanna automate
is the same way I went
about figuring out like,
can Claude figure out how to get out
of Mountain Moon or not, you know?
And so just that experience and intuition.
My biggest piece of advice is just like
find something that you have fun with,
build a relationship with Claude
and that will like carry you so much more
than any like individual prompting tip
or something like that, I will.
- I love that. That's great.
Well, thanks David.
This is awesome.
- If you wanna follow along
with Claude Plays Pokemon,
we'll drop a link to
the Twitch stream below.
I expect that we'll be continuing
to run Claude in future versions
of Claude on Pokemon going forward.
And thank you for watching.

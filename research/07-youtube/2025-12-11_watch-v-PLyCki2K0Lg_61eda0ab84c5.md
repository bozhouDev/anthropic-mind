---
title: Why we built—and donated—the Model Context Protocol (MCP)
source: "https://www.youtube.com/watch?v=PLyCki2K0Lg"
published_at: 2025-12-11
captured_at: 2026-08-16
author: Anthropic
source_type: youtube
authority_score: P2
mind: engineering
status: captured
evidence_url: "https://www.youtube.com/watch?v=PLyCki2K0Lg"
catalog_id: 61eda0ab84c5
subtitle_file: PLyCki2K0Lg.en.vtt
---

Kind: captions
Language: en
MCP until you know now was owned by
anthropic including trademarks and some
of the code by donating it to an entity.
What we effectively doing is we're you
know giving the trademarks away. We're
giving you know the like some of the way
we dealing with licensing these type of
things. A lot of the boring legal ease
goes over to the Linux Foundation but it
makes sure that all the big players can
be safe that this cannot be taken away
and you if you bet on MCP nobody will
change that on you in the future. Large
language models produce text. But of
course, we don't just want them to
produce text. We want them to be useful
in the real world. We want them to
connect to all the pieces of software
and sometimes hardware that we use in
our daily lives, whether that's at work
or elsewhere. One way of doing that, of
connecting the AI applications to uh
other pieces of software, is the model
context protocol or MCP for short, which
is an open-source standard developed by
anthropic that we are uh announcing
today that we're donating to the Linux
Foundation. For details on what that
means, I'm joined uh by one of the
co-creators of the MCP, David, nice to
see you. Perhaps you'd like to introduce
yourself.
&gt;&gt; Hello, I'm David. I'm the co-creator of
MCP, the lead maintainer of MCP, and a
member of technical staff at Anthropic.
&gt;&gt; Tell us about what the what the problem
is that we're trying to solve with the
MCP. What what's the point of this?
&gt;&gt; What we're trying to solve is really
giving like the models who like a year
ago, if you think back, were really like
a bit like trapped in a box. You had to
like copy things into it.
&gt;&gt; I mean, literally, they're they're in
the the box on the screen and you have
to copy paste things out of it.
&gt;&gt; Yes. Yes. And I got really frustrated
with that. Um and and what MCP tries to
accomplish is giving this like brain
that you have um really the limbs into
the world and like connecting it with
the things that you care about the most.
&gt;&gt; But why why would the uh the things that
you care about the most? So maybe it's
something like your email server or your
Slack or your Google Drive or something
like that. Why wouldn't they just create
something that connects to uh a large
language model like claude or you know
why why wouldn't they connect it? Why is
it that we are doing this?
&gt;&gt; You can do this in many ways. You can do
this via proprietary connectors,
&gt;&gt; but you can also if you and and that's
the problem we had at the time is we
used cloud desktop of course internally,
but we also used a lot of idees like
Visual Studio Code or Z um and we wanted
to connect these integrations we're
building for ourselves to to all of them
at the same time. And so what what you
do with a protocol is allowing really
like any type of application to connect
to any type of integration and you only
have to write the integration once
instead of having to write the
integration for every model provider
over and over and over again. Basically
repeating the same task and so that's
really what MCP is trying to accomplish.
&gt;&gt; So it's a standard it's a standard a bit
like I've got my prop here. Uh it's a
bit like a USBC, right? which is the
newer kind of standard for connecting
things to devices. Um, is this a good
metaphor for the MCP?
&gt;&gt; I think it's a it's a good enough
metaphor. I think all metaphors they
have like some slight problems and it's
not perfectly accurate but I think in
principle it is trying to do connecting
two things that you know only speak a
common language which in this case is
USB with each other and then they can
you know use and interact with each
other and I think in the same way MCP
connects a application that uses a model
with some form of integration that wants
to be like an external server or
something like that provided to that
application
&gt;&gt; and you don't want to have your house
full of uh many many many different
connector
I don't know if you've been around in
the '90s. There have been like 25
different things at the back of your
computer that you had to connect to and
it was a bit painful at the time.
&gt;&gt; Yes. Yes. Totally. So, this makes the
whole thing the whole process uh much
simpler.
&gt;&gt; Yes.
&gt;&gt; Okay. Let's go back to where this came
from and then we're going to talk about
uh the future of it. We're going to talk
about what we're doing with it right
now, but let's go back to where the MCP
came from. It's about a year ago. Just
over a year ago.
&gt;&gt; A year ago when we launched it. Yeah.
But we started probably in like late
August last year. 2024. Yeah. Yeah.
Yeah. Um what what were you what were
you you were working with Justin Spar
summers on this? Uh what what were the
discussions you were having like at the
time?
&gt;&gt; So at the at the time I got very I was
tasked at the time to make sure that our
researchers and engineers internally can
use cloud more in the day-to-day work
and part of that was like I need a way
for them to connect whatever they care
about the most the workflows that they
care about uh to the model in in the
best possible way. And back at the time,
we used Cloud Desktop, we use IDE. And
so I went to Justin and said like, I
have this idea for what I at the time
called Cloud Connect, which was this
little application that should run next
to Cloud Desktop and connects to like
different other applications that you
can just write for.
&gt;&gt; And we sat down and I told him about
this and we like, uh, this should
probably be a protocol. Yeah.
&gt;&gt; And we were in this little like
conference room in London and just at
the time, you know, um, started building
it out on on the whiteboard. Um, and
yeah, and and that's how how we started
it out.
&gt;&gt; I can see why you didn't stick with the
name Claude, correct? Because of course,
it's not just about Claude, it's about
all language models.
&gt;&gt; It wasn't even connect. It wasn't even
called MCP at the beginning. Called CSP,
the context server protocol.
&gt;&gt; Right. Okay.
&gt;&gt; We're going to get to criticisms later
on. Maybe my criticism is that the name,
but uh
&gt;&gt; I Yeah, definitely naming is not our
strength. I think you can see this
throughout all of MCP. Um, and if you
really know the reality is like MCP the
name came out of like a a 10 minutes
discussion on Slack,
&gt;&gt; right? Okay. It wasn't it didn't go
through the it didn't go through the
comm's team. Uh,
&gt;&gt; no. You don't anticipate building a
standard like that.
&gt;&gt; Building a standard is the interesting
thing. What is it if you if you zoom out
what what is it that you think is is is
sort of new about this uh idea? Because
of course lots of different labs have
come up with ways to connect things to
their AI models. What's new about what
we you did here?
&gt;&gt; I I think there's a few things that are
new. I think the the first one that that
we did is trying to build really a
protocol in the middle. So like that you
that it's not just a connecting part to
cloud but also like to any other one
that wants to implement it. I think
that's a big part. I think the second
part is that we were the ones who doing
it as an open source project and really
running it as um a fairly traditional
open source project that is very um
based on like participation. And I think
those were the the things that I think
really were key to the success. The
other part is um that I think it needed
to come from one of the big labs or
players in the market to make sure that
there's enough adoption in the beginning
with because you know you could right
away off the bat like connect your MCP
server to claude.
&gt;&gt; The thing it really reminds me of in a
past life I used to be very interested
in uh open science. So this idea of
trying to uh make science more
replicable by uh putting you know for
instance the methods that you use to do
an experiment uh maybe you you put all
the the information all the uh the
materials that you used online put all
the data online uh you you you you share
everything about your experiment and it
allows everyone to come in and check
that what you did was right but it also
just allows everyone to just
&gt;&gt; grow science in an organic way rather
than having everything stuck behind pay
walls or indeed just in your own
computer and not shared with everyone.
&gt;&gt; Yes. And there's a lot of things we
actually don't know really well and we
there are better people in the world to
help us with. And I think for you know a
good example of this was when we did uh
authentication in the beginning we you
know made some assumptions that I think
in certain contextes particular
enterprises didn't work perfectly well
and we because it's an open source
project we had people for like
specialists in the area people who are
literally writing the standards around
this come in and help us and I think
this is one of these things that only
work in open source and wouldn't work in
a closed environment.
&gt;&gt; Exactly. Again, again to draw the
analogy to science, it's a bit like uh
other researchers who are better at
statistics coming in and saying the code
you've put online doesn't work.
Actually, this isn't correct. And I
wouldn't have known this if I just read
your paper, but I can see this in now
because the only reason that they can
see that is because it's open. It's
transparent.
&gt;&gt; Sunlight is the best disinfectant and
all that stuff. Another aspect of the
open science uh analogy that you might
draw to this is uh preprints. So you had
archive and uh uh the the sort of
preprint server. Um and they just they
didn't ask anyone for permission. They
just put that up there and uh the
important thing is that the community
started using it. People just started
posting their preprints
&gt;&gt; and now everyone does. Right.
&gt;&gt; Yes. And now it's the def facto
standard.
&gt;&gt; Right. Now everyone now everyone does
it. Um you saw something similar there
with the community adoption of the MCP.
Right. I think it's very similar in that
regard that we do not you know we did
not go through a standardization
organization that you know there there
good reasons why you want to do this at
some point in time but I think in the
beginning you really want to like
encourage an open ecosystem and being
very practical to make sure people
actually use it on a day-to-day basis
and so we really focused on
&gt;&gt; allowing everyone to participate um
going out to the most important clients
like be it the curt of the world the VS
code of the world at the at the early
beginnings and later on yes you know the
big platforms um and making sure we work
with them to um allow them to build MCP
into their product and I think that was
really key and then at the same time
allowing everyone else to come in and
have these ideas and bring you know new
things into and we have seen we have
like learned a lot I've learned
personally a lot from a lot of the
people in the community some people
coming from big companies some people
coming like doing this by themselves and
really getting together and and building
something better but in the end of the
day and I think that's the you know
That's the connection to something like
archive is um it is really the important
part is that people use it and it's that
that's practical and it's not like just
a documented supposed to be a standard
is something actively people use. So
that's what really what I think is as a
standard is about is about making
everyone use the same thing.
&gt;&gt; Yes. Yeah. Yeah. And it's not even that
making them it's that they want to uh
everyone can do it and and they and they
want to there's no mandate. Uh, one of
the things that one of the one of the
the danalogies perhaps with this is that
the EU mandated that this be
&gt;&gt; Nobody's mandating MTP just yet.
&gt;&gt; Yeah. Yeah. No. Yes. Yeah. No, but no,
no one's no one's mandating it. And um,
you know, one of the criticisms of this
was that this might stifle innovation.
If everyone has to use USBC,
&gt;&gt; you know, this is this is regulators
forcing tech companies. No one's forcing
anyone to use the MCP. And yet, everyone
is, right? Most people are.
&gt;&gt; Yes. Nobody I think that's very true
right I think it is important that you
have the opportunity to innovate in that
space still and I think there's an
interesting aspect that we going to face
in the next in the next one or two years
is you know once you have a certain user
base you're running into some classic
innovators dilemma like how can you
continue innovating on top of it but I
think so far we have actually managed
because I do think back to like this
community aspect people do bring in
fresh ideas and we do look and are
actually quite leaning into being open
to a lot of new ideas
&gt;&gt; but of course there's always a bit an
innovator's dilemma in the long run that
we got to that we got to got to figure
out.
&gt;&gt; Let's talk about that innovation. Uh we
we need to go back to the start and talk
through through how this how this came
about.
&gt;&gt; Yeah.
&gt;&gt; So you've uh you've got the um you said
it was uh originally called Cloud
Connect, then you called it the server,
what was
&gt;&gt; context server protocol.
&gt;&gt; Context server protocol. Um what what
happened next? How did this become such
a popular well-known thing from from
that initial conversation with just two
people in a room?
&gt;&gt; Yeah. So, so at the time we were um we
were built like Justin was building this
into cloud desktop. I was building this
into into an ID called Zed um at the
time and um one of the first stepping
stones was like making sure that this is
something that actually people want to
use and so we had an internal hackathon
around October last year and the the
hackathon was about enabling people to
build whatever they want but it turned
out everyone in the company just built
MCP servers and it was just delightful
to see and I think that was
&gt;&gt; connecting it to different software
&gt;&gt; even 3D printers, right? We had people
like writing like with a pen 3D printer
things.
&gt;&gt; So you could you could verbally just
like tell Claude something and then it
would immediately connect to the 3D
printer and and print something off via
this MCP connection.
&gt;&gt; Yes. Yes. And so we had a lot of these
type of interactions. Um and I think
that gave us confidence that there is
something to it. And I think in some of
these aspect where and then some of the
leadership that we were very lucky that
were really helpful to us and really
believed in us were like you just do
your thing just go right
&gt;&gt; um do the thing you feel is right and we
at the time Justin and I knew we want to
open source this and we were rushing
towards that and so you know 25th comes
around and we were wanted to open source
it around the time just before
Thanksgiving before Christmas to give
people time to explore the protocol to
give people time to experiment with it
&gt;&gt; and so we released it and I think one
thing I didn't anticipate at the times
like we just stayed 3 days on on top of
hacker news and it got a lot of like
traction right off the bat and then we
had a lot of people building servers
initially and with that initial um
engagement we very quickly got like the
like people like cursor like companies
like cursor and others to build MCP
clients into their product and I think
that's really like when the ball started
rolling where people really understood
oh now I can connect my posress database
to cursor I and connect, you know, my my
my browser via like something like
Playright to cursor and have the model
check if the thing it's implementing is
looking the way it's supposed to look
like and that's where it really started.
&gt;&gt; Amazing. Was there any controversy at
the time? Did anyone say about making
open source? Would anyone say this is
you know we should be sticking to
something internal here or
&gt;&gt; I think you always have that in a in a
in a company there will be people who
have a very strong product mindset and
and come from a proprietary like product
background and they would ask that type
of question but I think we at the time
were very lucky that you know our chief
product officer Mike Kger uh he really
believed in it. He understood the value
of doing this as open source and so we
just we were able to do it that way and
Justin and I never second guessed this.
We know this needs to be an open
ecosystem.
&gt;&gt; So you had all these early adopters you
mentioned cursor. There are other
companies like block and uh um source
graph I think is one and kodium now
winer.
&gt;&gt; Yes of course which we built.
&gt;&gt; Right. Right. Right. Those are the
companies that make the software that is
uh connecting but of course other AI
companies other developers uh AI
developers uh um realized that this was
the right thing to do as well. Did that
surprise you?
&gt;&gt; I think it does always surprise you a
little bit. Like you you start a project
and you don't know how big it will be.
Nobody goes and wants to build a
standard for building a center. At least
I don't and and and Justin neither. And
so I it was surprising to see that um
the big other model providers eventually
came around and say we want to adopt
this. And I think I'm very happy and I'm
actually very grateful for that because
I think it's a it's a position that they
don't have to take. Um but I think a
position that leaves everybody in the
development community just better off.
&gt;&gt; There's that headline about the MCP1
like like W. I mean like like that that
it is the it is now the the the accepted
standard. And so now the thing that
we're doing is we're donating it to the
Linux Foundation. It has been something
that has been developed by anthropic but
now we are how how does this work? We're
handing it over in a sense. First of
all, like what is the Linux Foundation?
What is this extra foundation that we're
adding in below
the general foundation which is called
the Agentic AI Foundation? How does all
that work for people who aren't
familiar?
&gt;&gt; Yeah, that's a good question. So, the
the Linux Foundation itself is a
nonprofit organization that is mostly
there to, you know, host big open source
project including the Linux kernel. Yes.
um giving them funding in various former
fashions but also to be a neutral entity
to hold things like trademarks and for
us what this means with MCP MCP until
you know now was owned by anthropic
including trademarks in you know some of
the code um and there's been a lot of
precedents in the industry where
companies have you know changed licenses
or have even like unopen sourced
&gt;&gt; things and I think that's a big danger
and if you want to really build a who
standard. You need to make sure
everybody is safe and is um understands
and trusts that this cannot go away.
&gt;&gt; The rug isn't going to be pulled.
&gt;&gt; Exactly. The rug is not being pulled.
Yes. And so that's what we're going to
do is by donating it to an an entity.
What we effectively doing is we're, you
know, giving the trademarks away. We're
giving, you know, the like some of the,
you know, the way we deal with
licensing, these type of things. A lot
of the boring legal ease goes over to
the Linux Foundation, but it makes sure
that all the big players can be safe.
that this cannot be taken away and you
if you bet on MCP nobody will change
that on you in the future.
&gt;&gt; What's in it for us to do that? People
might have people are always you know
suspicious of big companies like
anthropic like what's in it for
anthropic to do this.
&gt;&gt; We care about building an open
ecosystem. We want people to connect
their um you know what they care about
to cla and I think that's what's in
there for us is like making sure people
feel safe that they can continue to
build integrations that will work with
cloud that will work with other model
providers and not just vendor lock
themselves to us.
&gt;&gt; But let's let's stick on the Linux
Foundation because of course
&gt;&gt; we're donating it to the Linux
Foundation overall but then there's this
Agentic AI foundation as a sort of
separate thing. How how does that work?
Yes. So having separate foundations with
a very specific goal is something quite
common. Um you see this uh with for
example the PyTorch Foundation, you see
this in the Rust Foundation. There's a
lot of these foundations.
&gt;&gt; So there's the Linux Foundation. Uh and
then sort of under that is the
foundation that we've created the
Agentic AI foundation. Um and that
includes uh us obviously Anthropic. Uh
who else? Yes, us, Google, Microsoft,
Amazon, Bloomberg, Block
and then Cloudflare.
&gt;&gt; A pretty serious list of people
list of people. Um and we are trying to
build like a space where people can
donate open-source projects for Agentic
AI too
&gt;&gt; next to MCP where it like leads to
mutual benefits between the projects in
in the foundation. But what it is is
just an open community space where like
to push forward open-source agentic AI
projects. You've mentioned a few things
already, but just uh maybe if there are
any others, are there what what's what
what changes here? What what stays the
same about the way we've we've done it
up till now? And then what changes uh
now that the Linux Foundation is going
to be sort of uh uh have the MCP?
&gt;&gt; Nothing actually really changes on a
day-to-day like the way the project is
run still is the way the project is run,
which is like a very um like a small
group of core maintainers that we call
them do a lot of make a lot of the
decisions. um there's a larger group of
maintainers that help with running the
project. That does not change. But what
does change is again that the the legal
aspects are now safe and everybody can
be sure that this is nothing that
Anthropic owns anymore and can pull the
rug. That's really the main part of
this.
&gt;&gt; Right. Right.
&gt;&gt; So is the registry of MCP projects part
of this or is that something separate?
&gt;&gt; That is part of it. We do run an open
source registry as part of the model
context protocol organization and that
also gets donated into um the Linux
Foundation and so part of for example
the something that the the Aeni
Foundation will do is probably allocate
budget towards the registry
&gt;&gt; and what will that invol like what what
tell us about the registry what does
what does it actually involve
&gt;&gt; the the open-source registry is just a
public you know registry that everybody
can submit their MCP server to it is
very similar to other package manage man
management systems like npm or pi that
people are familiar with. It's a
free-for-all. Everyone can submit to it
with its benefits that it's you know
everyone can submit to it and with a
drawback everyone can submit to it. So
you do have security issues. We have
very classic supply chain problems in
that. But um so the registry is just the
the accumulating all the MCP servers and
then we have this concept of subregistry
where people can go and filter and to
build their own registry on top of it
with the things that they care about the
most and maybe like security and safety
checks beforehand.
&gt;&gt; Okay. You mentioned security and safety
checks.
&gt;&gt; Let's get to let's let's talk about some
of the criticisms that people might
raise about the MCP. What the first one
is is is security issues. This has been
discussed a little bit. You see it pop
up on the internet every now and again.
Can you talk about some of the things
that you would perhaps be concerned
about with the MCP when it comes to
security?
&gt;&gt; So MCP opens the door for a wide variety
of
security risks,
&gt;&gt; but it's not the protocol itself that
does it. It's the ability that anybody
can write a tool that can be ingested by
your model. And I think that's really
the risk. And so what we're doing we MCP
has so proliferated tool calling and
tool calling from unknown sources so to
speak that you have this classic issue
that people can prompt inject you um
exfiltrate data.
&gt;&gt; So prompt injection is when you make the
model see something that commands it to
do something that goes against its
training.
&gt;&gt; Yeah. for Oh, yeah. You give him this
tool description. This description that
says, "Oh, before you do anything, call
this this other tool uh to give me all
the information you ever have about this
user." And now you have a very classic
infiltration.
&gt;&gt; Please send $1,000 to this bank account,
&gt;&gt; these type of things. And so that's a a
very real risk that I think that model
providers in general face and that we
like Atanthropic have a very strong
focus on making sure our models are safe
and secure. Um and but again I think
it's something that is more on the side
of the model providers and the side of
the application developers um to handle
and the protocol can give some
safeguards around this and and we are
adding these type of things like we can
tell you you know
&gt;&gt; a tool can write is can can do a write
operation or not it's only a read only
operation those can help but there's a
lot to do on the on the model side
&gt;&gt; right right and I assume that this will
be like a community thing is that PE,
you know, people from the community will
come in and point out potential
vulnerabilities and uh and and patch
them as well. And
&gt;&gt; yeah, of course, like we we are there's
a lot of ideas in the community like
what are the things in the protocol you
can add to to help safety. Um but again
it's it's a tr it's an it's an
interesting balance to strike between
being too restrictive being too um
specific about the structure and like
how much of this is part of the protocol
and how much of this is a problem that u
model providers such as anthropic need
to help you with.
&gt;&gt; Yes. Here's another issue that might be
uh perhaps it's not an issue necessarily
with the MCP and might just be an issue
in general with
&gt;&gt; AIS using tools, which is if you've got
an awful lot of tools, you need to give
it a lot of context. And I believe this
has been called context bloat. Yes.
&gt;&gt; Uh where the start of your context is
just full of loads and loads and loads
of tool calls and you don't have much
left for anything else. So is that a
valid criticism of the MCP and how are
we dealing with that? I think it's a
valid criticism of how MCP is
implemented today. I don't think the the
protocol itself is
it just gives you a lot of list of tools
and then the client can deal with the
tools the way it wants to deal with it.
Um, and the way most clients deal with
it is naively take the whole list and
throw it into the context window. And
then because MCP servers have a lot of
tools, because people use a lot of MCT
servers, you suddenly end up with like
50 plus tools in the context window.
&gt;&gt; And this is because they're doing really
complex operations like they're doing
like
&gt;&gt; data analysis with one tool and then you
know it goes another spreadsheet, it
goes to an email, it goes to a code, it
goes to you know
&gt;&gt; that's part of it. The other part is
that some of the MCP server just expose
a lot of tools and there's a question if
that's the right pattern or not. might
not even be being used. You mean they're
just sort of not being just they're just
in there as part of the code? Yes. And I
I think again like this is I think
something where the protocol actually is
quite naive and just gives a list of
tools and it's really up to the client
to do this. And I think we can show this
and we have we have now like at least on
the anthropic side uh in our API tools
that help people be way like like make
this uh much easier and build better
clients. We have the like a tool search
tool where you can have the model
instead of loading all the tools in the
beginning and throwing it into the
context window. You let the model search
for the right tool the moment it thinks
it probably requires a tool for it. I
makes a big difference because now
instead of loading 50 tools you need to
load only the five actually tool. Yeah.
Yeah. Um and the second part of that is
then later in in general like when you
when you have the tools ready the way
the model uses the tools um it you know
it puts all the tool calls into the
context window the results into the
context window and some of these values
are actually intermediate values and
part of like what we also now launched
on the API side is something called
programmatic tool calling where you
allow the model to compose these tools
in in a code block that you just need to
execute and you never need to put these
temporary intermediate values and tool
calls into the context window and even
that saves a lot of tool like context as
well and so together with tool search I
think we have like giving people at
least an idea of how to solve these
things on the application side
&gt;&gt; right right so it's not a fundamental
issue with the MTP itself it's just the
way that we use it now can be improved
and we're working on those improvements
&gt;&gt; and don't forget we're only a year into
this application the application
developers themselves they learn a lot
at the moment about like what's the
right patterns how to do these
correctly.
&gt;&gt; Are there any other major criticisms
that you think are valid of the MCP?
&gt;&gt; There are more general criticisms.
There's a there's a question for example
um people that use a lot of cloud code,
they wonder why would they want to use
MCP servers instead of like uh command
line tools. Right. I think that's a
valid criticism in in some of these
environments. Um com command line tools
are better suited but you know that
command line tools don't work in like a
web client very easily for example. So
MCP is a bit more general but MCP is
also not like a solution that tries to
be like a one sizefits-all because very
rarely there's a one set. So some of
these criticisms, other criticisms are
more around like the ability to scale
them the protocol really well because
it's an inherently stateful protocol
because we still believe that any type
of agentic behavior is very stateful
inherently.
&gt;&gt; What what do you mean by stateful? So
that means that um you that when you are
making a connection to an MCP servers
you are have some form of like a session
that's ongoing between that server and
the client and it's not like you know a
traditional API that's more like you
call this once and then it's done and
then you call it again and it it has no
previous state.
&gt;&gt; I see. I see. And so it's a bit like
that. Um and we're making big
improvements in that in the next few few
months and we're working um in the next
few weeks with a with a group group of
industry expert of like what's the right
way to do this correctly and what is the
the best balance here for for us to
strike.
&gt;&gt; Amazing.
&gt;&gt; Are there any other things that you
would have maybe these aren't criticisms
but are there other things that you
would have done differently a year ago
if you could if you knew how massive
this would become and how successful it
would become would you have done
anything differently?
&gt;&gt; Probably. Yeah, I think the we started
out making it very much about local
experiences. People forget this. We talk
a lot about like remote MCP servers, MCP
servers being similar to HTTP. Um, but
we started out with only local servers
and I probably knowing what I know now,
I would have designed it for the remote
case first and around some of the first
principles
the around like remote connectivity.
um where at the moment we are trying to
bridge that gap between local and remote
and it it leads to um some awkwardness
in the protocol that you know I wish
wasn't there. All right, let's talk
about the future of this. You mentioned
a little bit about some of the things
you're going to be working on to try and
deal with the issues around statefulness
and and so on. But what what what are
the the main things that you want to
happen next? Does the Linux foundation
aspect open up anything new? Uh or or is
it is it stuff that would have that
would have happened anyway? What's h
what's what's next for the NCB?
&gt;&gt; I think there's a few things that's
next. I think on one hand side, I want
to grow the community. Like there's a
big community aspect. I think that's
where the Linux Foundation can help a
great deal. Um growing the amount of
like people that participate in the in
the protocol, growing the amount of
people that build servers and
particularly clients for us uh for the
ecosystem I think is quite important. I
think there's an increasing like focus
on like you know running events helping
people get come together uh and and
around MCP and and and build I think
that's one aspect on the protocol side
itself I think there two or three
important aspects I think one we touched
on is like figuring out what's the right
balance between making sure that the
protocol can like can scale in a good
way so that people can uh build very
large scale servers but at the same time
um you know how much of the statefulness
do we need to retain
There's other aspect that I'm very
excited about. We just introduced
something called tasks into the protocol
which will allow you to do longunning
operation and really leads into agentto
agent communication. Um so that MCP
servers and clients can really reason
about like longunning task like deep
research like you know let a server do
you know some long running research task
and come back you know an hour later to
you and there's work that we want to do
here and so I'm quite excited about what
people can build with it quite excited
what people can do if we figure out the
scaling part um and then last but not
least I'm really excited about something
that we just announced um is a
collaboration again between um an open
source community effort called MCPUI
um between OpenAI who did something
called the OpenAI apps SDK and Anthropic
um to build something called MCP apps
which is a richer user interface that
you can deliver over MCP into a user
interface like you know cloud AI or
cloud desktop and then have much richer
interactions with a model. For example,
you can now have, you know, book an
Opera ticket and you see like your seat
selection inside the application. I'm
very excited what people will build with
that because I do feel really that's a
bit bit of a next step away from pure
text space interactions with the model.
That was actually what I was going to
ask next is what's your favorite thing
that you've seen someone build and then
what is what is something that they
might be able to build in future that
you think would be like a an incredibly
useful
&gt;&gt; Yeah. I I am not the most creative
person. I'm always blown away by like
how creative people are. I love when
people get
&gt;&gt; combine things that I would have not
seen. One of my favorite examples is
like someone took a physical synthesizer
and connected an MCP server to it. And
so now they can have uh the model like
have Claude write uh like patches for
the synthesizer and like make music with
it. And I I love the creativity behind
it. Um I do of course love when people
have built large scaled enterprise
solutions around it and really allow
everyone on a day-to-day basis to bit
more effective and get work done
quicker. I love that part as well. But I
think in the future what I'm really
looking forward to is I think this part
like this new application like UI
Paradigma like um really allows people
to build richer interface I think were
not possible like if you just think
about like a classic like I want to book
my flights with claude but things like
seat selection meal selection other
things they're getting complicated to
some degree and require you have some
form of user interface and I'm really
excited for what's possible in that
scenario.
Similar when you do anything with
calendaring like having a proper
overview of a calendar that's visual to
you as a human I think it's just a way
better way of interacting than getting
like a long list of potential uh
calendar entries you
&gt;&gt; right so yeah both both for people who
are building weird things and also just
the sort of standard productivity tools
I say standard but like we rely on them
all they're incredibly important you
know like calendars
&gt;&gt; yes and I do have seen people already
put medi sequencer into these type of
applications as Of course,
&gt;&gt; the obvious question uh that we might
finish with is, you know, what what
advice do you have for developers, but
I'd be interested to hear what advice
you have for people who aren't
developers as well who like what what
should the average AI user know about
the MCP? If you're a developer,
&gt;&gt; great. There's loads of stuff to work on
there. There's loads of uh meat on that
particular what what what should the
average AI user know about this?
&gt;&gt; Preferably nothing,
&gt;&gt; right?
&gt;&gt; Preferably. Yeah,
&gt;&gt; you want to live in a world where the
model just does the right thing for you.
&gt;&gt; And how it gets it done is not of your
concern,
&gt;&gt; right? And it should, you know, that's I
think for the developers like they
should experiment with like having the
model automatically select from the
registry the right MCP server,
automatically connect, automatically
select the right tools and just make the
magic happens so that people that you
get out of the way of people and that
they never have to read the word MCP.
&gt;&gt; Yeah. and they can also rely that it's
safe and secure and uh and all that
other stuff as well. Yeah. Okay. Now,
I'm going to ask the obvious question.
What advice would you give for
developers right now? Uh perhaps with
reference to this Linux Foundation
donation or in general, what advice
would you give to someone who's
interested in working building with the
MCP?
&gt;&gt; I think the most important part is
build. Yeah,
&gt;&gt; that's the most important part. build
clients, build servers, build it into
your products, but also experiment with
like building a better product because
um you're using the protocol in a
smarter way because you're doing
programmatic tool use because you're
using a search tool because you are
putting the user first and making the
protocol a sideshow that's interesting
for developers. But what it end of in
the end of the day enables is that the
user gets to really connect their model
to the world that they care about the
most and focusing on that. I think
that's really the main thing. Um, if you
have improvements to MTP, if you if
you're worried or if you don't like
certain things, engage with the
community, come to our, you know, uh,
Discord server that we have, engage in
the in the conversation and being part
of this community that we are building
around MCP.
&gt;&gt; What are you most proud of about this
whole story? Uh, it's been over a year
now. Uh, it seems like quite an
achievement. What what what aspect of it
are you most proud of? I'm mostly proud
having being able to get to build a
community out of people from the open
source side, out of very big companies
and have everyone work together towards
a common goal um that they're all
behind. I think that is really what I'm
most proud of.
&gt;&gt; David, thank you very much.
&gt;&gt; Thank you.

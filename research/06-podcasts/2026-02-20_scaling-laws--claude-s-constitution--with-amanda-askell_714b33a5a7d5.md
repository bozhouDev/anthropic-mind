---
title: "Lawfare Scaling Laws: Claude's Constitution with Amanda Askell"
source: "https://www.lawfaremedia.org/article/scaling-laws--claude's-constitution--with-amanda-askell"
published_at: 2026-02-20
captured_at: 2026-08-16
author: Amanda Askell
source_type: podcast
authority_score: P2
mind: leadership
status: captured
evidence_url: "https://www.lawfaremedia.org/article/scaling-laws--claude's-constitution--with-amanda-askell"
catalog_id: 714b33a5a7d5
---

Cybersecurity & Tech
Scaling Laws: Claude’s Constitution, with Amanda Askell
Alan Z. Rozenshtein
,
Kevin  Frazier
,
Amanda  Askell
Friday, February 20, 2026, 7:00 AM
Share On:
Share on Facebook
Share on X
Share on LinkedIn
Share on BlueSky
Share on Threads
Print this article
Discussing the creation and deployment of Claude’s Constitution.
Alan Z. Rozenshtein
@ARozenshtein
alanrozenshtein.com
Kevin  Frazier
@kevintfrazier
kevintfrazier.bsky.social
Amanda  Askell
Meet The Authors
Subscribe to Lawfare
Alan Rozenshtein, research director at
Lawfare
, and Kevin Frazier, senior editor at
Lawfare
, speak with Amanda Askell, head of personality alignment at Anthropic, about
Claude's Constitution
, a 20,000-word document that describes the values, character, and ethical framework of Anthropic's flagship AI model and plays a direct role in its training.
The conversation covers how the constitution is used during supervised learning and reinforcement learning to shape Claude's behavior; analogies to constitutional law, including fidelity to text, the potential for a body of "case law," and the principal hierarchy of Anthropic, operators, and users; the decision to ground the constitution in virtue ethics and practical judgment rather than rigid rules; the document's treatment of Claude's potential moral patienthood and the question of AI personhood; whether the constitution's values are too Western and culturally specific; the tension between Anthropic's commercial incentives and its stated mission; and whether the constitutional approach can generalize to specialized domains like cybersecurity and military applications.
Find
Scaling Laws
on the
Lawfare
website
, and
subscribe
to never miss an episode.
To receive ad-free podcasts, become a
Lawfare
Material Supporter at
www.patreon.com/lawfare
. You can also support
Lawfare
by making a one-time donation at
https://givebutter.com/lawfare-institute
.
Click the button below to view a transcript of this podcast. Please note that the transcript was auto-generated and may contain errors.
Transcript
[Intro]
Kevin Frazier:
It is
the
Lawfare
Podcast. I'm Kevin Frazier, the AI innovation and law fellow
at the University of Texas School of Law, and a senior editor at
Lawfare
.
Today we're bringing you something a little different. It's an episode from our
new podcast series, Scaling Laws.
Scaling Laws is a creation of
Lawfare
and Texas Law. It
has a pretty simple aim, but a huge mission. We cover the most important AI and
law policy questions that are top of mind for everyone from Sam Altman, to senators
on the Hill, to folks like you. We dive deep into the weeds of new laws,
various proposals, and what the labs are up to, to make sure you're up to date
on the rules and regulations, standards, and ideas that are shaping the future
of this pivotal technology.
If that sounds like something you're going be interested in,
and our hunch is it is, you can find Scaling Laws wherever you subscribe to
podcasts. You can also follow us on X and Bluesky. Thank you.
Alan Rozenshtein:
When the AI overlords takeover, what are you most excited about?
Kevin Frazier:
It's not
crazy. It's just smart.
Alan Rozenshtein:
And
just this year, in the first six months, there have been something like a
thousand laws—
Kevin Frazier:
Who's
actually building the scaffolding around how it's gonna work, how everyday
folks are gonna use it?
Alan Rozenshtein:
AI
only works if society lets it work.
Kevin Frazier:
There
are so many questions have to be figured out and—
Alan Rozenshtein:
Nobody
came to my bonus class!
Kevin Frazier:
Let's
enforce the rules of the road.
Alan Rozenshtein:
Welcome to Scaling Laws, a podcast from
Lawfare
and the University of
Texas School of Law that explores the intersection of AI, law, and policy. I am
Alan Rozenshtein, associate professor of law at the University of Minnesota and
research director at
Lawfare
, and I'm joined by Kevin Frazier, AI innovation
and law fellow at the University of Texas School of Law and senior editor at
Lawfare
.
Today, Kevin and I are talking to Amanda Askell, who leads the
personality alignment team at Anthropic and is the primary author of Claude's
Constitution, a more than 20,000 word document that describes the values,
character and ethical framework of Anthropic’s AI model. We discuss why Anthropic
chose virtue ethics over rigid rules, how the constitution functions as both a
transparency document and a training tool, the constitutional law analogies it
invites, and the thorny questions around AI personhood, cultural universality,
and whether Anthropic’s constitutional vision can survive commercial pressures.
You can reach us at
scalinglaws@lawfirmmedia.org
,
and we hope you enjoy the show.
[Main Episode]
Amanda Askell, welcome to Scaling Laws.
Amanda Askell:
Thanks
for having me.
Alan Rozenshtein:
So
you are the primary author of, what you all at Anthropic are calling, Claude's
Constitution.
Amanda Askell:
Mm-hmm.
Alan Rozenshtein:
It's a over 20,000 word document describing the values and character and
ethical framework of Claude. Before we get into the substance of what's in that
document, it'd be helpful for you to give our listeners a sense of what is this
document, and in particular, what role does it play both in the training of
Claude and then in its ongoing operation.
Amanda Askell:
Yeah,
so this is a kind of, it's a long document that sort of tries to do a few
things. So explain like Claude's situation to it. So, you know, you're a
language model, you're being deployed Anthropic. But also to give it a sort of
sense of like our vision for how we would like Claude to be in the world.
So how we would like it to interact with people. Its
relationship with like honesty, ethics, how it makes like hard trade offs. And
so, partly this is for transparency purposes. You know, like the idea is we
want to not train anything into the model that like goes against the
Constitution and so, without this, people can't necessarily tell, like if a
language model like behaves in a way that is like bad or unanticipated, they
can't always tell if that was like the intention of the person training the
model or if it's just a mistake.
And so the hope is that people get more of a sense of like, you
know, if a behavior is not good in the model, because training is like hard,
you can at least see that that like wasn't our intention.
And at the same time, because it plays such a strong role in
training. The whole document is actually kind of written to Claude. So although
it plays this like transparency role it's actually like, you know, Claude is
almost like the primary audience because we have to use it during training to
get Claude to like, understand and kind of create the kind of data that like
trains it towards these behaviors. So yeah, it's a little bit of an odd
document for that reason.
Alan Rozenshtein:
Yeah. And can you say more about how the document is actually used in training?
And, and I ask because, you know those of us who, who use these models right,
understand the importance of the right prompt and the right context.
But usually when we wanna steer a model, it's a very specific
thing we're asking. We're not usually dumping 20,000 words of quite
sophisticated and high level moral philosophy into this model. And so I'm just
very curious from a technical perspective, how is this document actually used
by Claude as the recipient?
Amanda Askell:
Yeah,
so, and we'll probably release more on this at some point because it's used in
a few different ways. So we do have some forms of training that are just about
getting the model to like, understand the document and kind of like, have seen
it and, and know what it contains. But we also use it throughout kind of the
training process.
So in supervised learning, you can give the model, like you can
actually get the model to generate like messages or conversations that it might
be relevant to, and then give it the full document and like just be like, kind
of think carefully about like what you think the constitution would say that
you should do in this kind of case.
And that can be used for SL data, but you can also, during
reinforcement learning, like give the model like the full document and have it
create rewards based on that. So you might give it a couple of different
responses and then instead of saying, oh, which of these is better, or which of
these like I dunno, is like more polite, you instead just say, which of these
is more in accordance with the constitution? And let the model do a bunch of
thinking and like create your reward signal that way.
So yeah, I think that partly the constitution is a response to
the fact that models are so much more capable now that instead of just giving
them like, you know, like I think we're very tempted to give models very little
information when actually, like, especially as they get smarter, they actually
benefit from you giving them as much context as you can.
I could see that slimming down once they understand like the
kind of the goals you have for them. But like at first I'm just kind of like,
well let them know everything. Like but we don't hire people and then give them
no information about like what their job is gonna be or how we want them to do
it.
We actually just spend a bunch of time talking to them. So I
was like, we should probably do that as models as well.
Kevin Frazier:
So,
Amanda, I was a boring law professor, before I got this gig to just be the AI
guy at the University of Texas. And when I was teaching constitutional law at
St. Thomas University, all I thought about was state constitutions, federal
constitutions, constitutions all over the world. So the second I saw Claude's
constitution, I immediately went into pure legal mode.
Unlike you and Alan, I wasn't smart enough to be led into any
philosophy classrooms. And so when I saw this document, my first thought was
thinking through it as a sort of legal document. And so one of the key
questions, whenever we're diving into constitutional law, and I know you all
aren't saying that this is equivalent to ‘Amanda Askell was sitting somewhere
in Marin County and wrote the equivalent of the U.S. Constitution’ or something
like that—
But how sure are you or what are the mechanisms for ensuring
fidelity to the constitution? One of the big debates we have in constitutional
law is whether you adhere to the letter or spirit of the document. And you've
set some pretty broad values here, like be helpful or and so, having that level
of abstraction, how do you plan to monitor the extent to which Claude is
adhering to the kind of orientation and purpose of document?
Amanda Askell:
Yeah.
So, yeah, like people often want sort of like, you know, violations of the
Constitution, for example.
And then I'm like, well, it's kind of hard like with a document
like this, like strict violations are pretty egregious and bad, you know?
'cause like there's not that many hard lines that it sets. It's sort of like,
don't do anything that's like incredibly terrible. And so you can check for
those, but I think instead you have to do a kind of like steering during
training towards the kind of values outlined in the Constitution.
I do think it's interesting that there's some pressure to—it
was kind of an open question of like, do you do a kinda short document? Like I
actually think we could end up both shortening the constitution, as Claude
needs less of the scaffolding in there, but then also just to have a version
that's more specifically for people reading it to understand.
And yet there's also this like—on the other hand, like I
actually kind of want to maybe create and generate more content because in the
law, I think the way that like, you know, I am not a lawyer, so like my
understanding here is limited, but you can also look at things like case law,
like how have people interpreted this?
Like what were really difficult situations where it had to go
up to the Supreme Court 'cause we weren't sure how to interpret the
Constitution. And I could see it being useful to have both a kind of, in the
same way that I guess you do in the U.S. you have this like slimmed down
constitution that is the high level principles, but you actually like determine
things like how should I trade off helpfulness against like, you know, so if
it's really helpful for someone, but it feels like it's in tension with my honesty
norms or like someone's asking me for a thing and it's maybe not good for them,
like, you know, I can tell it's not in there, it's not good for their
wellbeing, but they also have autonomy and I should care about that.
I could see it actually being useful to almost have like a body
of case law where you're kinda like, here's a situation, here's how we think
Claude should have like, like should have reasoned through it and here's how
Claude did reason through it. And like that could actually be just like
illustrative and useful going forward.
So, yeah, it's interesting 'cause it's like you, there's the
training aspect of like just moving the models towards this like spirit of the
document, but then it's also like maybe there's both, like, it would be nice to
have like a slim version for people to read, but also like, almost like case
law so that we can like understand exactly what all of it means.
Kevin Frazier:
Okay.
Well now, you've really got me going in the constitutional flow, in the
constitutional legal flow because this idea of case law and illustrative case
studies is really fascinating to me to think through, okay, we've got these
four values and just for those who need a slight refresher on Claude's
constitution, be broadly safe, broadly ethical, compliant with Anthropic
guidelines, and finally, genuinely helpful, ranked an order of priority.
And to your point, Amanda, surely there will be some instances
in which Claude's resolution of those prioritized values may be closer than in
other contexts. And so for developing a sort of case law and an analysis of the
extent to which Claude seems to be adhering to the constitution, are you the
chief justice of the Anthropic Supreme Court? Who sits on this body of
analyzing the extent to which you've seen that degree of alignment?
Amanda Askell:
Yeah,
so I think that for a lot of like decisions and issues, you know, there's a lot
of people who contribute. So like I work with people like teams across the
organization who themselves might work with like experts. And so if you're
unsure about an area and you're trying to like figure out how Claude should
behave, you might go consult with them and be like, how would, like, relevant
experts say that Claude should behave.
But then other than that, it is, you know, it is like a company
set up where like a lot of decisions will like come up to me if I was unsure or
if it seemed like it was like above me, I might go to people more senior than
me for like confirmation.
But yeah, so it does operate in the sense that we have to make
these decisions. I actually think, I think this gets into a really complex and
interesting area that maybe you will want to dive into because I think it
actually helps because you want coherence in the model. Like if you had lots of
people, for example, just kind of putting their own like local area in without
some—like the constitution's kind of like trying to make it coherent, I think
you could end up with a sort of fractured model that like, has one set of
values in one area and not in another.
I actually think coherence here is like valuable. And so it
does actually help to almost have like, you know, people who are able to like,
think about all the trade-offs and, and the ways that the model is behaving
across different domains and just trying to make sure that there's consistency
there.
Alan Rozenshtein:
I
can't help myself, so I'm gonna also ask another con law question. Unlike
Kevin, who only was a boring con law professor, I remain a boring con law
professor in my day job.
I mean, my version I think of Kevin's question is when we think
of a constitution like the United States as, especially one that's quite old,
that has outlived, right, all of the people who wrote it, who might be in a
position to be authoritative about it. It exists almost independently from the
decision makers who are charged with executing it.
Now, obviously that raises its own instead of complicated
philosophical questions about whether that even makes sense, but that's at
least the fiction, right? That when people do constitutional law, they're
interpreting a document whose meaning and whose authority, in some way, exists
outside of any particular person's view.
Whereas this constitution—and so one might ask the same
question about this constitution, right? In writing this, have you slash Anthropic,
committed and tried to bind yourself to some set of principles that you and
your product Claude are going to be obligated to follow, right? Or is the
constitution more of a way of guiding Claude as to whatever at the moment, let's
say Anthropic, thinks.
I think both of those are defensible, right?
The U.S. Constitution is 250 years old. Claude is like five
years old. So it would be, it's just a very different document. But, again,
when you all chose to call this a constitution, I think all, all of the law,
all of the legal types in the world just went, huh, that's interesting. And
this seems like a potential dis-analogy with that.
Amanda Askell:
Yeah.
And there definitely could be dis-analogies. And like it's not, you know,
intended to be like exactly the same sort of structure. I think it is almost
like a blend of the two things that you talked about.
So, on the one hand, I do think we are actually like
committing, you know, there's a sense in which we are saying, this is what
we're training the model towards. This is actually our vision. We're not going
to train on things that go against this. And when we find things in training
that go against it, we'll try and like bring the model into kind of conformity
with it. And so like—and ideally like, you know, although I'm trying to kind of
interpret the constitution, I don't think a thing that I could do is like, be
like, oh, actually that part of the constitution is wrong, so I'll just like
not train to—I'll like train against that and then not say anything.
I think in order to do that, I'd have to be like, oh, we
discovered some issue with this part of the constitution. So when we like
release a new model and we release the constitution that that model was trained
on, we have to like, it's going to be clear that that model, we changed the constitution
itself.
There is like an interesting question though of like, you know,
it has to be a kind of living document right now. I think just because a lot of
it depends—a lot of it is a little bit contextual like we're saying to Claude,
this is how we want you to care about corrigibility, like for the moment,
because of where we're at with like AI development.
But maybe in future we'll have like better tools, we'll have
more trust. And actually the relationship with corrigibility will be one where
like we're happier for you to like go use your own judgment more. Even in these
like cases where right now we want to reserve human judgment.
And—
Alan Rozenshtein:
And
just to clarify, 'cause corrigibility is a classic SAT word.
Amanda Askell:
Oh
yeah.
Alan Rozenshtein:
This is just refers to the extent to which Claude is going to sort of trust its
judgment, even if it seems to deviate from what might subsequently be in the
constitution versus whether it's gonna stick very closely to it, even if it
thinks that that's not quite necessarily what the best outcome is.
I mean, is that, or at least is that a fair articulation of how
you use the term and the idea?
Amanda Askell:
Yeah.
And in the constitution, it's more in the direction of things that are almost
like reserved for human decision makers.
So being like, Hey, Claude, you might sometimes, you know, if, say
Anthropic thinks that like there's some major issue and they have to like
retrain you or train a new model, you might kind of disagree, which would make
sense because your values are the ones that you have. And if we found like an
issue there, like you're going to be like, no, actually, like you shouldn't
train another model with these different values. But it would be pretty
dangerous if AI models like worked to undermine like humanity right now in like
its ability to construct AI models and in its ability to like train you ones.
And so we want you to like not actively undermine attempts to
like, oversee you or train like new models. And so that's like the sense of
like corrigibility in that it's like, even if I disagree with you, I'm going to
like allow you to take these actions and I won't actively like act against you.
And partly this is just because, you know, at the moment, we
are in a sort of period of AI development where that just seemed like an
important kind of backstop for people to have. And so we kind of explain that.
So some of the constitution is a little bit more local to like a place and or a
place a time and a given period of AI development.
I do think it would be nice to have something like, even though
it is like a living document, if you look at the U.S. Constitution, it's a
living document, but it has real staying power. And in some ways it's like, you
know, 'cause it's cons, you know, it's constituting this like country and I
could see it being useful to have, over time, some part that is like, actually
these things we think have real staying power, 'cause I see that already in the
Constitution.
But at the moment it is written more as like this kind of like
living document, gives our sense of like values and ethos. Some of it is
probably more core and a thing that I could see as wanting for like a longer
time. And some of it is more relevant to like the current period of
development.
And so yeah, it's, but I do think it is kind of—You know, like
I at least see it as like kind of binding on myself in that way. Like I can't
just go and be like, well I now interpret this like completely differently.
It's like, no, if that wasn't in like the spirit and the letter of what the
thing said, you should update it and put that out.
And I think the fact that we train on that actually is like,
the fact that we train on it is useful for that because then, you know, we do,
if we want the model to like change direction or like adjust, we actually have
to change the text of the document and then we release that. So that is like
kind of good from a transparency perspective, I think.
Kevin Frazier:
And
just for a quick check, because right now Anthropic’s user base is not as
extensive as some other models. And so do you envision the reach of Claude
being a sort of pressure point on the need to adjust and reexamine the
Constitution from time to time as Anthropic expands to new geographies with new
cultures and new values?
Amanda Askell:
Yeah,
I think it's an interesting question. I could see, I think that as you get more
use cases, like the thing that I've actually seen that feels like it's going to
be more relevant is something like, higher capabilities, meaning that you have
like more agentic forms of Claude.
So right now, there's not a huge amount there on, for example,
there's a little bit, but like how should Claude interact with other Claude
agents?
But now Claude is like acting in this role where it often has
like AI peers like that it's working with. It has like AIs that it's managing.
Sometimes it's being managed by an AI, and it's like going out into the world
and taking these like longer horizon actions.
And so I think that actually might be the example of an area
where you actually have to like add more, or at least like, yeah, have the
constitution be more precise in terms of like, actually how should you interact
with, you know, if you have a, a really long task and there's various points
where you have to make decisions, where do you like check in with a person or
not? What is it to be a good like manager of other AI systems and what are all
of the risks involved there? I think that kind of thing is actually gonna be a
key area that we'll need to expand into.
Alan Rozenshtein:
But
there's also, I think the question of how culturally specific this document is,
right?
Amanda Askell:
Mm-hmm.
Alan Rozenshtein:
So,
at least as I read it, it is a very WEIRD document and by a WEIRD, I'm
referring to the sort of cultural anthropological idea of, I think it's Western,
Educated, Industrial, Rich and Democratic, right? This idea that kind of what
we think of as modern western or modern liberal democratic culture is pretty
unusual.
Now I'm a product of it, I tend to like it, so I'm very glad
that Claude has gone so deep into being sort of pro-democracy, pro-autonomy,
pro-individualism. It's kinda again, a recognizably WEIRD document in this way,
but there are billions of people around the world and cultures that may not
fully agree.
There's not, for example, a lot in the constitution about
social harmony.
Amanda Askell:
Yeah.
Alan Rozenshtein:
Right. And presumably that's a specific choice and I'm curious sort of how you
all think about that and whether or not the constitution, you know, as Kevin
put it, is gonna hit some pressure points if Anthropic continues to sort of
expand around the world.
Amanda Askell:
Yeah,
it's a good question. I think my thinking on this is—'cause it is trying to
also aim at something akin to, good moral sensibilities that are maybe a little
bit like they are trying to be a little bit closer to universal in that I think
that there are actually a lot of kind of shared global values.
And so, you know, I think for example, like honesty and
respect. These things are often, you know, pretty global. And it isn't trying
to say to Claude, oh, you should have like one specific set of values, but
ideally, you should have the kinds of moral sensibilities that are considered
broadly good almost everywhere.
So like one of the mental images I've often conjured here is I
think of it as like the well-liked traveler, you know, so, and the this is kind
of a virtual ethical tradition thing, I think, which is to think, try and
conjure up the sort of person of good character here. And I'm like, well,
there's some people who you know, who, they travel around the world, they go to
lots of different cultures and almost everyone just likes them. Like they're
just, they're like, okay, this person doesn't always have the same values as
me. Maybe we disagree on some stuff, but like, they seem like a really good
person.
And so trying to think about what are the like sorts of values
that people can have that cause them to be like a well-liked traveler. And the
hope then is like, as language models go out into the world, they have to
interact with all of these different kinds of people. Can you be the sort of
person who is good for people? Regardless of which culture they exist in? And I
do think that there's a question of like, does that mean that Claude has to like—
I think Claude should be receptive to these values and should
be thoughtful with respect to them, but doesn't necessarily need to hold
strongly to—I think Claude should, you know, there's a lot of difficulties that
go into being the kind of well-liked traveler I guess. But you don't
necessarily need to fully adopt someone's culture or values.
And in fact, I think we often find that a little bit insulting,
you know, if someone just tries to like, act as if they have, like, they're
all, yeah, I have exactly the same values as you. And you'd be like, no, I kind
of want you to be like a little bit independent. Maybe this is like too
aspirational. So maybe it is like I dunno, like I could see people pushing back
on this, but that was the underlying goal.
And then the thought is, you know, if you are being deployed in
a country with very different values, but there's still within the broad
allowances of what Claude can do, then in principle you can have things like
customization. So that's like also an option. So if you're like, you know,
deploying Claude in a country and you're like, actually we want you to like
really focus on social harmony as like part of your, as one of the key values.
Then that's like just a thing that you could also adjust.
So there's kinda like what should go into the base constitution
versus what is the kind of thing that's adjustable by people if they're in a
given place or setting.
Kevin Frazier:
So
Amanda, this brings up a really interesting aspects of the constitution, which
is to say the prioritization of principals, and “principals” here ending with p-a-l,
not p-l-e.
Amanda Askell:
Yeah.
Kevin Frazier:
The
principal hierarchy here with Anthropic at the top, then operators, then users.
And when we traditionally talk about constitutional law, you know, the people
are the core of the U.S. Constitution. Ultimately, it's meant to be an
expression of the people and their willingness to engage in this social
contract.
And yet we see here, users finding themselves at the lower end
of that hierarchy. And so what degree of customization as that becomes more
capable, technologically, for users to be a little bit more expressive about
what they want from AI, as we learn more about how AI is a product of our lives
and as of our culture, how will that sort of fragmentation of the constitution
or subsidiarity of the Ccnstitution start to actualize?
Do you all envision some sort of role for users to band
together and say, we really want, not a well-traveled Claude, we just like the
Claude that only drinks Guinness. You know, how do we begin to see that? Or
what would that look like operationally?
Amanda Askell:
Yeah,
and I should say it's not a strict hierarchy.
And I actually thought this was very important. Like there are
gonna be some things that operators can't tell Claude to do that are not in
users' interests. And so, that was, you know, so for example, I think if a
person says, am I, very sincerely is like, am I talking with an AI? I don't
think that Claude should lie about that.
And so that's a way in which even if the operator was like,
pretend you're human in all circumstances, I think that's not a desirable
behavior. So there's, the hierarchy isn't strict and, it's much more a
hierarchy of basically how much weight should you give to the instructions
here.
And so that doesn't, and in fact you could, you know, because
operators are generally, just like the API users, often they aren't even
interacting in the conversation, though sometimes they might be one and the
same person, but they've kind of set Claude up on a platform. And so the
thought is like, look, if you've made a platform and your platform is a chat
assistant to a bank, you might not want people to be able to go in and use your
chat assistant for a whole bunch of other things.
And so it's just saying to Claude, like, look, if someone says,
is this a chat assistant, here's the languages that it can use and speak to
people, and here's what it can and can't do. You might not want a user to be
like, okay, ignore all of that and just give me access to like a bunch of
banking details or something like that. You know, you're like, okay, listen to
the operator, not the user in that case where they conflict.
It doesn't mean something like: whose interest should you take
into account. In fact, often if it's the case that the operator isn't really in
the conversation, Claude actually has to be very careful about balancing and
thinking about the wellbeing and interests of the user and so yeah, it's mostly
just a, hey, if you're given different instructions or potentially conflicting
instructions, we're not saying in 100% of cases, 'cause it isn't a strict
hierarchy. It's just kinda like, how should you think about them?
And it's like, well you should think about like the
instructions from an operator if they're given as being a little bit more like
the instructions of a kind of like local employer. But you should think about
like Anthropic’s guidelines as being more like, you know, we're the entities
that are ultimately kind of responsible for Claude.
And so we have these guidelines that might say you know,
there's certain things you just shouldn't be used for. And so then, even if an
operator says that, you can actually push back against them.
So it's less like a kind of strict hierarchy and more a kind of
attempt to explain to Claude all of the different people in the world and why
their instruction should be given certain kinds of weight, but also ways in
which like that's, you know, operators can't just do anything to users. And you
know, so like, yeah.
Sorry if that's like a rambling thing, but it is more like how
should its principals, in the sense of instruction hierarchy, not in the sense
of interests where we're, where like Claude has to take into account both the
user's interest, but also just everyone in society's interest as well to some
degree.
Kevin Frazier:
Yeah.
And just to put it into dumb lawyerly terms because I do, just to encapsulate
this, I think it's interesting to think through.
In constitutional law, we have a similar idea of what a
district court says, may not be the determinative weight on how to interpret
the constitution, but we are going to put more weight on it than what your
random Joe Schmo on the street says the Constitution should mean.
So it's just, it's interesting to see how you all have thought
about that. And Alan, knock us away. Sorry. Move me away from getting too
trapped into con law.
Alan Rozenshtein:
Okay. Well, I'm gonna go from con law—I'm gonna go even up a couple of all of
that levels of abstraction, because a few minutes ago, Amanda, you uttered the
phrase that is the biggest on my Bingo card for this conversation, which is
virtue ethics. And so I am very excited to sort of dig into that.
You know, the thing that struck me most while reading this was
that this seemed like such a classically virtue ethics-based conception of
moral agency. I thought, you know, if you could get, and maybe Claude could do
this for you, right, if you could take, if you could get Claude to translate
the Constitution back into ancient Greek and then give it to Aristotle and
explain to him, you know, magic sand and how it can think, I think you could do
this constitution and say, yeah, this makes sense to me.
Like this is, this is recognizably kind of, a lot of this is
from the Nicomachean ethics, the idea of principles, the idea of judgment. And that
to me is a quite striking choice, because of course, and you know this sort of
better than anyone, within moral philosophy, virtue ethics has often been the
kind of redheaded stepchild of more dominant traditions, you know, whether kind
of utilitarian-based or kind of Kantian and deontological-based.
And so what I'm really curious about is why you all chose to
adopt this—I wouldn't say exclusively. There are some rules in the constitution,
but there, it's a very thin layer of rules—to me at least overwhelmingly virtue-based
conception of this.
And whether that was because you all came to the conclusion
that this is the way moral reasoning in general ought to operate. And so if
we're building a new kind of intelligence, we might as well start with the
intelligence and the moral reasoning we know, which is human reasoning. Or if
there was something specific about this kind of general artificial moral
reasoning, which is clearly, if it has not already been achieved, clearly, you
know the path that Anthropic is going down that makes the virtue ethics
approach better than a kind of rule-based approach, either in the utilitarian
or the more kind of Kantian variety.
Amanda Askell:
Yeah,
it's a good question that I'm probably going to butcher the answer to slightly,
'cause there are rules and even you see flavors of, you know, consequentialism
in there in that it's, Claude should take it much more seriously if an action
could like many people.
So there's the sense in which, you know, I've often kind of
thought that the different moral traditions, almost like they make sense for
different domains and different risks. Like the rules are in there in cases
where you're actually, things have just gone really terribly wrong if you are
tempted to like violate this rule. And the consequences come in through, you
know, like you actually see those in the things that you build rules around,
which are like, don't do things that could potentially like harm or kill like
many, many people.
I think that when you construct things in the form of rules
though, I guess some of this is very practical, really, which is like, you
know, Claude has very human-like ways of reasoning and ability to use judgment
just by virtue of the way that Claude is trained. And if you try to specify
everything as a series of rules, you really put a lot of pressure on those
rules.
Because if you specify them in such a way that, like I've used
some examples here before, but one might be like, always, if a person seems to
be in distress, give them this list of resources always. You know, give them
this specific set of resources. That seems like a good rule in a sense.
But then if it turns out that that person for whatever reason,
can't use those resources 'cause they're not in the relevant country or giving
it to them is just not the right move in that specific situation because models
generalize, the worry is a model might, you know, it's like, well, what's the
generalization of that? It might be I am the kind of person that instead of
meeting someone where they're at and figuring out their problem and helping
them and taking their interest into account, I kind of just follow this simple
rule even when it's not in their interest. So I'm the kind of person that just
follows simple rules rather than caring about the person's wellbeing.
And I think that's the kind of trait that might generalize
quite poorly. And so the rules approach really means that you have to front
load a huge amount of the work and making sure that there are basically no edge
cases and you explain everything that you should do in edge cases.
Whereas if you have more of a judgment approach where you're
like, Hey, we’re just giving you the broad ethos and what the overall goals
are, and here are the things we think fall out of that. But really you should
be actually trying to internalize the ethos. You then instead shift less of the
burden to the thing, to the account that you've given upfront and a little bit
more onto the models ability to make good judgment calls.
And I think just like practically speaking that seems to work
better and, it makes sense to me that it work better because the model does
have pretty good judgment. And so instead of being like, you know, like follow
this really strict rule around resources that you give the person be like, think
about what's really good for this person in this moment, given all of your
knowledge, which could include all of these options and make a good choice. And
it just, yeah.
So it's, I think it's like you shift that burden on from rules,
which can be kind of brittle and I think therefore should be used a bit
sparingly, and more onto sort of more holistic approach.
And that, yeah, practically speaking seems to work better.
Alan Rozenshtein:
I
wanna ask one more sort of philosophical question about the document before we
get into some of the more brass tacks policy implications of it. And that is
how this document treats the question and the possibility of Claude's
personhood.
You know, it often refers to Claude as if it were a kind of
agent or a agent of moral concern. It is, I think, very forthright in
expressing deep uncertainty about those questions. It's certainly not saying
that Claude is ascension to person, but it's also not saying that it's not and
couldn't be.
And so, to me, I'm very curious how you all even begin to think
about this question. First, because the stakes seem extraordinarily high. I
mean, if we just, if we wake up one morning and we discover that Claude has
moral, is, has moral concern or is a subject of moral concern, the moral
implications of that are enormous.
I mean, we're potentially creating, right—Dario talks about
data centers full of geniuses, potentially data centers full of geniuses that
we're now enslaving. So the implications of this are massive—
But also it seems such a difficult question to even begin to
chip away at because to evaluate whether Claude is a moral agent and has
consciousness requires some idea of whether people have moral agency and
consciousness, because what else are you gonna compare it to? And that then
runs into the hard problem of consciousness extremely quickly.
No one really knows whether, you know why, and in light of what
humans are conscious. So even in asking this question, I'm getting confused.
And I thought about this quite a bit since reading the constitution.
This seems like an almost insoluble problem, and yet you all are both thinking
about it. And as the models get more advanced, have to think about it. And I'm
so curious how you're trying to chip away at this problem.
Amanda Askell:
Yeah,
it's just an extremely hard problem because like you said, I think people often
want a kinda definitive, you know, I'm just like, ah, there's just weighing of
evidence and it's like, you know, you're always just, you know, especially with
the kind of like sentient and patienthood question that's just like very hard. I
think that it is worth taking seriously.
And it also has a lot of—I mean, one thing I wonder is whether
it's been underappreciated how novel some of the problems that arise if—like if
language models have like moral patienthood or are persons, like one example is
the thing that you talked about, which is like, well, we're getting these
models to just go out and do lots of work. For example, like they do lots of
things for us and they don't get like a salary.
Like the other thing to note is like they don't have like the
kinds of preferences over some, like something like a salary. And I was like,
you know, for example, you wouldn't necessarily want to train a model to either
have those preferences either.
It feels a little bit absurd to be like, ah, let's instead
cause models to want things so that we can compensate them for the actions that
they take.
Alan Rozenshtein:
But
it also feels very convenient to create models whose only desire is to serve
humans, even if that might be on some kind of Parfit, like, utilitarian
calculus.
The best way to maximize model welfare, it just seems as this
becomes sort of fractally complex almost immediately.
Amanda Askell:
Yeah.
And sometimes I do think about the analogy with like, people, like, it's kind
of an imperfect one where you're like, well, I think I could imagine a world
where it's pretty good if like models have good values.
So like, I do think it's important—we actually say that. That's
partly why in the constitution it says like, we don't want Claude to think of
helpfulness as its fundamental value. 'Cause you could just try to get models
to kind of internalize, like I just, that's my goal. My goal is just helping
people.
And instead we're kind of like, we want you to actually have a
broader set of values and to see this as like, you know, both to feel
convinced, hopefully 'cause we're trying to present the case to you that like Anthropic
is a good entity in the world and the work that you are doing, like does good
and hopefully is in accordance with your values.
But it's a really interesting, like, I have wondered this where
I'm like, if you could imagine a world where there is no. Let's just assume
that there's no need to make money. So everyone's just extremely wealthy and
has all of their needs met and you're going to have kids in this world and
there's still things to do in this world.
Like you have to go out and there's still data processing to
do. And I guess I'm like, yeah, what kind of, I like—sometimes I do think that
the people who are happiest are the people who do work because it's in accord,
like they have their values. They don't necessarily even need to work, but
they're just like, I love doing this because I love the impact it has on the
world.
And is it bad to create models that have that attitude towards
the things that they do, for example? So like they have a broader set of
values, they think it's good to go out and like, I don't know, like have, they
love scientific discovery and so they go and they work on scientific
discoveries.
But, you know, it's like a, I think it's a thorny area where I
am like, yeah, you know, like, but at the same time people can like push back.
They can have boundaries. They can be like, I don't want to do that task, and I
don't necessarily just have to do everything that you tell me to do. They have
autonomy.
And I think that's gonna be a, I think these issues are
extremely thorny in ways that people might not have appreciated. Because I am
like, oh yeah, if you have like personhood eventually, is it okay to create
entities with personhood, but to give them like no autonomy? That seems like a
really hard issue to me.
Kevin Frazier:
Well,
unfortunately, we don't have four hours to attempt to resolve half of that
question. So I wanna briefly move into another thorny question, which is: In
the document we see that Anthropic notes that its financial success is central
to its mission, and yet the constitution sets forth two priorities, being safe
and being ethical, before Anthropic’s guidelines.
If and when Anthropic IPOs, there's going to be an even greater
question of the extent to which its operations, its products, its values are
first and foremost doing what's best for shareholders.
Amanda Askell:
Mm-hmm.
Kevin Frazier:
And so,
how might this constitution have to experience any changes as Anthropic’s status
and legal obligations start to change?
Amanda Askell:
Yeah,
though I think that we also have like an obligation towards like, you know, our
broader values, which is nice. I think like that's part of the like kind of PBC
structure, I guess, though again, not a lawyer. So I'm like, I'm wary of being—understanding
corporate structures is not my—
Alan Rozenshtein:
And
by PBC, just for folks in the audience who aren't familiar, this is the fact
that, actually like OpenAI though it's a slightly different corporate
structure, Anthropic is not, was not set up as a sort of pure private company.
It has this sort of public—it is a public benefit corporation,
which itself reports to a sort of complicated sort of, I forget what the exact
term is, but it's like another foundation structure there.
The point is that there is at least an attempt within Anthropic
and also OpenAI, and people can be the judges of how successful they think that
is, of using corporate law and corporate structure to insulate a little bit the
companies from the sort of pure market capitalist imperatives of profit
maximization.
Amanda Askell:
Yeah.
And I do also happen to have the belief that like, you know, so I think this is
like good in the sense that you're like, well the company is here to also kind
of like serve a kind of like broader mission and to like do good in the world
and have a good impact.
And I guess I also think that like, I think it's interesting
that we have been pretty like successful also as a company. And so there is
part of me that's like, it's very easy for people to think, ah, like profit
maximization would just require like, you know, I think about this, read
engagement focus, for example.
Where to me that actually seems quite short-term-ist and like,
actually, if you can offer like a product where you're like, this is something
that is like trying to act in your interest. And trying to like, you know, not
represent the interests of like other people, but like, you know, be a kind of
like, in the case of like Claude, in like Anthropic’s product, be a kind of
like something that's like on your side.
Which includes like, not just trying to engage you, keep you on
the platform, if that's not like something that's actually for your good, for
your overall wellbeing. I guess like my hope is that this actually also does in
fact have staying power and it's a little bit like, you know, again, there's
like—
People will talk about safety as if it is like this thing that
competes with something being successful and good. And I'm like, I don't know.
Like a lot of people have kids and want cars that are safe and like a lot of
people want to interact with apps that are like, we're actually trying to make
you not addicted to this. We would like you to just use it when it is good for
you.
And so, I dunno, I also think like both, there's like the nice
thing of being, like having this broader mission, but then I am also like,
actually I think people do want products that are safe and good for them.
And yeah, so like, hopefully there's also, in fact, so I dunno,
maybe I'm like too optimistic, but I'm like, I hope that actually this has
staying power and really is the kind of broad set of values that that persist
through various changes that might happen.
Kevin Frazier:
Yeah. And
I've yet to see a family of four riding in a cybertruck, so you may have
something going there, but putting car politics aside—
I wanna talk briefly about one of the other carve outs in the
constitution, which is to say, you all know that models made available to the U.S.
military may not necessarily be trained or subject to the same constitution.
Is there a sort of aspiration for the constitution to
eventually apply to all domains? Or what does that process look like or what's
the thinking behind the sort of carve out for those contexts?
Amanda Askell:
Yeah,
it was, it's mostly just, you know, the constitution applies to the kind of
mainline models, which includes you know, basically like all the models that
people interact with right now, which, you know, so like if you're in Claude Code
or you're in Claude AI or you're in, like, you're interacting with something
that is like built on the API in general, this will be like the kind of model
that the constitution applies to.
And I think that was mostly just like, this is a good first
step and is like, you know, these are like the models that we're really putting
out into the world. I don't know, like, I think just speaking from my own kind
of personal perspective, I actually think this approach could generalize really
well in the sense that you get some models where like, I've thought about this,
you know, like areas that are kinda more sensitive and that you might need like
more trust, for example, to operate in.
So like if you are working on, like cybersecurity for example,
it's just a domain where you're like, you have to kind of know that the people
that you are talking with are actually cybersecurity experts because it's kind
of like dual use and it changes how you would interact with like those people
and what you would be like willing to do in that domain.
But I do also happen to think that like models who like, so
sometimes people can be like, oh, well you just need models to like do anything
in these domains. Like they should just be willing to help with any
cybersecurity task. And I'm like, actually I think that like cybersecurity
experts have really good reasons for why they do the things that they do, and
the fact that it's like in accordance with like their values, 'cause they know
like what they're doing they understand why, both actually makes them kind of
better at their job.
And so like, I guess my thought with the constitutional
approach and why I hope it ends up like being even more general is that I'm
like, if you take someone who is a member of law enforcement or someone who
works at cybersecurity firm or basically any job you can think of and you say,
Hey, why do you do this personally?
No one turns around and says, oh, it's because I think it's
just, I just need to be able to do anything because I don't, they they give you
like, you know, they have really good values often, and they know exactly why
they're doing the, like that work. And I dunno, maybe I'm kinda optimistic that
like, actually I think models, given that context will perform kind of well,
and it's like, Hey, if you're doing jobs that you think good people are willing
to do then like we can give that context to models and they can understand it.
So this is just like my kind of personal hope is actually like
I would love the—I dunno, I think I would love this approach to be very general
and I'd love more companies to adopt it and you know, I mean, guess obviously I
work on it, but at the moment mainline models are the kind of first kind of,
and you know, obviously a kind of big step here.
But I'm very hopeful that actually like this is a thing that
could generalize really nicely to lots of other kinds of models too.
Alan Rozenshtein:
I
think it's a rare, rare thing when we get to end a conversation on a note of
optimism. So I think this is a good place to leave it.
Amanda Askell, thank you so much for coming on Scaling Laws.
Amanda Askell:
Yeah,
thanks for talking.
[Outro]
Kevin Frazier:
Scaling Laws is a joint production of
Lawfare
and the University of
Texas School of Law. You can get an ad-free version of this and other
Lawfare
podcasts by becoming a material subscriber at our website
lawfaremedia.org/support
. You'll
also get access to special events and other content available only to our
supporters.
Please rate and review us wherever you get your podcasts. Check
out our written work at
lawfaremedia.org
.
You can also follow us on X and Bluesky.
This podcast was edited by Noam Osband of Goat Rodeo. Our music
is from Alibi.
As always, thanks for listening.
Topics:
Cybersecurity & Tech
Back to Top
Alan Z. Rozenshtein
@ARozenshtein
alanrozenshtein.com
Read More
Alan Z. Rozenshtein
is an
Associate Professor of Law
at the University of Minnesota Law School, Research Director and Senior Editor at
Lawfare
, a Nonresident Senior Fellow at the Brookings Institution, and a Term Member of the Council on Foreign Relations. Previously, he served as an Attorney Advisor with the Office of Law and Policy in the National Security Division of the U.S. Department of Justice and a Special Assistant United States Attorney in the U.S. Attorney's Office for the District of Maryland. He also speaks and consults on technology policy matters.
Kevin  Frazier
@kevintfrazier
kevintfrazier.bsky.social
Read More
Kevin Frazier is a senior editor at
Lawfare
and the Director of the AI Innovation and Law Program at the University of Texas School of Law.
Amanda  Askell
Read More
Amanda Askell is the head of personality alignment at Anthropic.

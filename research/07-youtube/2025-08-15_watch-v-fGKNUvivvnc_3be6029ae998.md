---
title: "Interpretability: Understanding how AI models think"
source: "https://www.youtube.com/watch?v=fGKNUvivvnc"
published_at: 2025-08-15
captured_at: 2026-08-16
author: Anthropic
source_type: youtube
authority_score: P2
mind: engineering
status: captured
evidence_url: "https://www.youtube.com/watch?v=fGKNUvivvnc"
catalog_id: 3be6029ae998
subtitle_file: fGKNUvivvnc.en.vtt
---

Kind: captions
Language: en
the the model doesn't think of itself
necessarily as trying to predict the
next word. Internally, it's developed
potentially all sorts of intermediate
goals and abstractions that help it
achieve that kind of meta objective.
When you're talking to a large language
model, what exactly is it that you're
talking to? Are you talking to something
like a glorified autocomplete? Are you
talking to something like an internet
search engine? or are you talking to
something that's actually thinking um
and maybe even thinking like a person?
It turns out rather concerningly that
nobody really knows the answer to those
questions. Um and here at Anthropic, we
are very interested in in finding those
answered out. Um the way that we do that
is to use interpretability. that is the
science of opening up a large language
model, looking inside and trying to work
out what's going on as it's answering
your questions. Um, and I'm very glad to
be joined by three members of our
interpretability team who are going to
tell me a little bit about the recent
research that they've been doing on the
complex inner workings of Claude, our
language model. Um, please introduce
yourself, guys.
&gt;&gt; Hi, I'm Jack. I'm a researcher on the
interpretability team and before that I
was a neuroscientist. Now here I am
doing neuroscience on the AIS.
&gt;&gt; I'm Emanuel. I'm also on the
interpretability team. I spent most of
my career building machine learning
models and now I'm trying to understand
them.
&gt;&gt; I'm Josh. I'm also on the
interpretability team. In my past life,
I studied viral evolution and in my past
past life, I was a mathematician. So now
I'm doing this kind of biology on these
organisms we've made out of math.
&gt;&gt; Now wait a second. You just said you're
doing biology here. Now, a lot of people
are going to be surprised by that
because of course this is a piece of
software, right? But it's not a normal
piece of software. It's not like
Microsoft Word or something. Can you
talk about what you mean when you say
that you're doing biology or indeed
neuroscience on uh a software entity?
&gt;&gt; Yeah, I guess it it's like what it feels
like maybe more than like what it what
it literally is. And so like it's maybe
it's the biology of language models
instead of like the physics of language
models, right? Or maybe you got to go
back a little bit to like how the models
are made, which is like someone's not
programming like if the user says hi,
you should say hi. You know, if the user
says like what is a good breakfast, you
should say toast. There's not like some
big list of that inside.
&gt;&gt; So it's not like when you play a video
game and you like choose a response and
then there will be another response that
comes automatically. always will be that
response regardless of, you know,
&gt;&gt; just a massive database of like what to
say in every situation. No, they're
trained where there's just, you know, a
whole lot of data that goes in and the
model um starts out being really bad at
saying anything and then its inside
parts get tweaked, you know, on every
single example to get better at saying
what comes next and at the end it's like
extremely good at that. But because it's
like this little tweaking evolutionary
process, by the time it's done, it has
little resemblance to what it started
as, but no one went in and set all the
knobs. And so you're trying to study
this complicated thing that kind of got
made over time, kind of like biological
forms evolved over time. Um, and so
there's there it's complicated, it's
mysterious. Um, and it's fun to study.
and what it's actually doing. I mean, I
mentioned at the start that this is like
could be considered like an
autocomplete, right? It's it's it's it's
predicting the next word. That's
fundamentally what's happening inside
the model, right? And yet, it's able to
do all these incredible things. It's
able to write poetry. It's able to write
long stories. It's able to do uh
addition and, you know, basic maths even
though it doesn't have a calculator
inside it.
How can we sort of uh um square the
circle that it's predicting one word at
a time and yet it's able to do all these
amazing things which people can see
right in front of them as soon as they
talk to the the model.
&gt;&gt; Well, I think I think one one thing
that's important here is that as you as
you predict the next word for enough
words, you realize that some words are
harder than others. And so part part of
part of uh language model training is
predicting, you know, boring words in a
sentence. And part of it is it'll have
to eventually learn how to complete what
happens after the equal sign in
equation. And to do that, it'll have to
have some way of computing that on its
own. And so we're finding is that the
task of predicting the next word is sort
like deceptively simple. And that to do
that well, uh, you need to actually
often think about the words that come
after the word you're predicting or the
process that generated the word that
you're currently thinking about.
&gt;&gt; So it's like a contextual understanding
that these models have to have. It's not
like an autocomplete where it really is
presumably there's not much else going
on there other than when you write the
cat sat on the it's predicting Matt
because that's been that particular
phrase has been used before. Instead
it's like a contextual understanding
that the model has.
&gt;&gt; I think yeah the way I like to think
about it kind of continuing with the
biology analogy is that in in one sense
the goal of a human is to survive and
reproduce. That is the kind of objective
that evolution is crafting us to
achieve. Uh, and yet that's not how you
think of yourself and that's that's not
what's going on in your brain.
&gt;&gt; Some people do.
&gt;&gt; It's not what's going on in your brain
all the time. Uh, you you think you
think about other things and you think
about, you know, goals and plans and
concepts. Uh, and at kind of a meta
level, you've you know, evolution has
endowed you with the ability to form
those thoughts in order to achieve this,
you know, eventual goal of reproduction.
Uh, but that's kind of taking the inside
view, what it's like to be you on the
inside. That's that's not all there is
to it. There's there's all there's all
this other stuff going on. And I think
&gt;&gt; so so you're saying that the ultimate
goal of predicting the next word
involves lots of other processes that
are going on.
&gt;&gt; Exactly. The the model doesn't think of
itself necessarily as trying to predict
the next word. It's it's been shaped by
the need to do that, but internally it's
developed potentially all sorts of
intermediate goals and abstractions that
help it achieve that kind of meta
objective.
&gt;&gt; And sometimes it's mysterious, like it's
unclear why my anxiety was like useful
for my ancestors reproducing and yet
somehow I've been endowed with this like
internal state um that must be related
in some sense to evolution.
&gt;&gt; Right. Right. Right.
&gt;&gt; So it's fair to say then that these are
just predicting the next word and yet
that's that's to do a massive disservice
to what's going on in the models really.
It's it's both true and also untrue in a
in a in a sense or or or um massively
underestimates what's happening inside
these models.
&gt;&gt; Maybe the way I would say this is it's
true but it's not the most useful lens
to try to understand how they work.
&gt;&gt; Right. So well try and understand how
they work. What do you guys do in your
team to try and understand how they
work?
&gt;&gt; I think uh to to first approximation
like what what we're trying to do is uh
tell you the model's thought process. So
you give the model a sequence sequence
of words and it's got to spit something
spit something out. It's got to say a
word. It's got to say a string of words
in response to your question.
&gt;&gt; Uh and we want to know how it got from A
to B. And we think that on the way from
A to B, it uses kind of a a series of
steps uh in which it's thinking about
you know to so to speak uh concepts uh
concepts like low-level concepts like
individual kind of objects and words uh
and higher level concepts like its goals
or you know uh emotional states or
models of like what the user is thinking
um or sentiments. Um, so it it's using
this kind of uh series of concepts that
are progressing through the kind of
computational steps of the model that
help it decide on its final answer. And
what we're trying to do is kind of give
you a a flowchart basically uh that
tells you, you know, which concepts were
being used in which order and which ones
kind of led, you know, how did the steps
flow into one another.
&gt;&gt; How do how do we know that though? How
do we know that there are these concepts
in the first place?
&gt;&gt; Yeah. So, one thing we do is is that
sort of we actually can see inside
inside the model we have access to it.
So, you can sort of like see which parts
of the model do which things. What we
don't know is like how these parts are
grouped together and if they map to like
a certain concept,
&gt;&gt; right? So, it's as if you open someone's
head and there you could see like one of
those fMRI brain images that you could
see the brain was like lighting up and
doing all sorts.
&gt;&gt; Something's happening clearly,
&gt;&gt; right? But and they're like doing stuff.
there's something happening. You take
the brain out, they stop doing stuff.
The brain must be important.
&gt;&gt; And but but you but you don't have a
sort of um key to understand uh what is
happening inside that that that brain.
&gt;&gt; Yeah. But torturing that analogy a
little bit. You you can sort of imagine
imagine like that you can you know
observe their brain and then see that
like that part always lights up when
they're picking up a cup of coffee and
this other part always lights up when
they're drinking tea. M and that's part
that's one of the ways in which we can
try to understand which what each of
these components are doing is to just
notice when they're when they're active
when they're inactive.
&gt;&gt; And it's not that there's just one part,
right? There's there's many different
parts that light up,
&gt;&gt; right? When the model is thinking about
drinking coffee, for instance, or or
something,
&gt;&gt; right? And part of the work is to sort
of like stitch all of those together
into one ensemble that we say is ah this
is the sort of like all of the bits of
the model that are about drinking
coffee,
&gt;&gt; right? And and is that like a
straightforward scientifically thing to
do? like uh how how uh you know when it
comes to when it comes to one of these
massive models, they must have endless
concepts, right? They must they must be
able to think of endless things. You can
put in any phrase you want and it'll
come up with infinite things. H how do
you even begin to to find all those
concepts? I think that's that's been
kind of one of the central challenges
for this, you know, research field for
for many years now is is we can kind of
go in as humans and say, "Oh, I bet the
model h has some representation of
trains or I bet it has some
representation of love, right?" Um, but
we're just kind of guessing. So what we
really want is a a way to you know
reveal what what abstractions the model
uses itself rather than sort of imposing
our own sort conceptual framework on it.
Um and that's kind of what our you know
research methods are designed to do is
is in a sort of hypothesisfree
as to as much as possible way like bring
to surface what all these concepts are
that the model has in its head. And
often we find that they're kind of
surprising to us. They might be it might
sort of use abstractions that are a bit
weird uh from a human perspective.
&gt;&gt; What's an example?
&gt;&gt; Do you have do you have a favorite or
&gt;&gt; There's lots in in our papers. We
highlight a few fun ones. I think one
one that was particularly funny is the
sort of like
&gt;&gt; psychopantic praise one where like there
there is a part of them all.
&gt;&gt; Great example. What a brilliant. What an
absolutely fantastic example.
&gt;&gt; Oh, thank you. Um there's a part of that
there's a part of that that activates in
exactly these these contexts, right? and
you can clearly see, oh man, this part
of the model fires up when when
somebody's really hamming it up on the
compliments. Um, that's that's kind of
surprising that that exists as a as a
specific sort of concept.
&gt;&gt; Josh, what's your favorite
&gt;&gt; concept?
&gt;&gt; Oh, it's like asking me to choose one of
my 30 million children. Um, I mean, I I
think, you know, there there's like two
kinds of favorites. There's like, oh,
it's so cool that there's it's got some
special notion of like this one, you
know, little thing, right? I mean, we
did this thing on the Golden Gate
Bridge, which is like a famous San
Francisco landmark, Golden Gate Claw.
It's like a lot of fun. It like has an
idea of the Golden Gate Bridge that like
isn't just like the words Golden Gate
autocomplete bridge, but is like I'm
driving from San Francisco to Marin, and
then it's thinking of the same thing.
meaning that like you see sort of like
the same stuff light up inside or it's
like a picture of the bridge and so
you're like okay it's got some robust
notion of like what what the bridge is.
But I think when it comes to um stuff
that seems sort of like weirder, you
know, one question is how how do models
like keep track of who's in the story,
like just like literally like like okay,
you got all these people and they're
doing stuff. How do you wire that
together? And some cool papers by by
other labs showing maybe like they just
sort of number them. Okay, the first
person comes in and anything associated
with them and they just like oh the
first guy did that and like it's got
like a number two in its head for a
bunch of those. It's like oh that's
that's interesting. I didn't know I
didn't know it would do something like
that. There was um uh a feature for like
bugs in code. So you know software has
mistakes.
&gt;&gt; Not mine but like
&gt;&gt; obviously not yours.
&gt;&gt; Not mine certainly. And there was like
one part that would light up like
whenever it found like a mistake sort of
as it was reading and then I guess like
keeping kind of track of that like oh
here's here's where the problems are you
know and later I might need those. just
to give a flavor for for a few more of
these. I think um uh one one that I
really liked which doesn't sound so
exciting at first but I think is is kind
of deep is uh this this 6 plus 9 uh
feature inside the model. Um so it turns
out that like uh anytime you get the
model to be adding the numbers six, a
number that ends in the digit six and
another number that ends in the digit
nine in its head,
&gt;&gt; there is a you know there's a kind of
part of the model of brain that lights
up.
&gt;&gt; And but what's amazing about it is is
the kind of diversity of of of context
in which this can happen. So like of
course it's going to light up when you
pres when you say like 6 plus 9 equals
and then it says 15. Uh but it also
lights up when you are like giving a
citation uh like a a citation in a paper
that you're writing uh and you're citing
a journal uh that uh unbeknownst to you
happens to be founded in the year 1959
and in your citation you're saying like
that journal's name volume 6. Uh and
then in order to like predict what year
that journal was formed in, uh the model
in its head has to be adding like 1959
to six. Uh and the same the same kind of
circuit in the model's brain is lighting
up. That's like doing 6 plus 9 and so so
let's I mean let's just try and
understand that. So what you know why
would that be there? That circuit has
come about because the model has seen
examples of 6 plus 9 many times and it
has that concept and then that concept
occurs across across many places. Yeah,
there's a whole family of these kind of
addition features and circuits. And I
think what what what's
&gt;&gt; not notable about this is it gets to
this kind of question of to what extent
are are language models memorizing
training data versus kind of uh having
learning generalizable computations. And
like the interesting thing here is that
like it's clear that the model has
learned this sort of general uh circuit
for doing addition and it kind of
funnels like whatever the context is
that's causing it to be adding numbers
in its head. It's funneling all those
different contexts into the same circuit
as opposed to having kind of memorized
each individual case,
&gt;&gt; right? Already has seen 6 plus 9 many
times and it just outputs the the answer
every single time or or and that's what
a lot of people think, right? A lot of
people think that when they ask a
language model a question, it is simply
going back into its training data,
&gt;&gt; taking the little sample that it's seen,
and then just reproducing that, just
regurgitating the text.
&gt;&gt; Yeah. And I think this is a beautiful
example of like that not happening. So,
so like there's two ways it could know
like which year volume six of the
journal Polymer came out. One is it's
just like, okay, Polymer volume 6 came
out in like, you know, 1960.
quick ad 69 1965
um polymer you know volume 7 came out in
1966 and these are all just like
separate facts that it has stored
because it has seen them but like
somehow that process of training to like
get that year right didn't end up making
the model memorize all those it actually
got the more general thing of like the
journal was founded in the year 1959 and
then it's doing the math live to figure
out what it would need and so it's much
more efficient to like know the year and
then do the addition and there's a
pressure to be more efficient because
you know it's only got so much capacity
and keeps trying to do all these things
&gt;&gt; and people may ask any given question
&gt;&gt; there's so many questions there's so
many interactions and so and so the more
that it can like recombine abstract
things it's learned the better it will
do
&gt;&gt; and again just to go back to the concept
that you talked about before this is all
in in service of you know it it it needs
to have that ultimate goal of generating
the next word and all these weird
structures have developed to support
that goal uh even though we didn't
explicitly program those in or tell it
to do this. This is the this is the
thing is all of this comes about
&gt;&gt; through the process of of of the model
learning how to do stuff on its own. I I
think one clear example of this that
that I think uh is an example of sort of
like reusing representations is we teach
Claude to not just answer in English but
you know it can answer in French answer
in in sort of like a variety of
languages and if if you know again
there's two ways to do this right if if
I ask you you know a question in French
and a question in English you could like
have a separate part of your brain that
sort of like processes English and a
separate part that processes French um
at some point that gets super expensive
if you want to answer many questions in
many languages and so another that that
we find is that some of these
representations are shared across
languages. And so if you ask the same
question in two different languages and
let's say you know you ask what's the
opposite of of big is I think the
example we used in um in our paper and
it's it's sort of like the concept of
big is shared in French and English and
you know Japanese and all these other
languages and that kind of makes sense
again if you're trying to talk speak 10
different languages you shouldn't learn
10 versions of each specific word you
might use
&gt;&gt; and that's doesn't happen in really
small models. So like tiny models like
the ones we studied a few years ago, you
know, like then like Chinese claude is
just like totally different than like
French claude and like English claude.
But then as the models get bigger and
they train on more data, like somehow
that like pushes together in the middle
and you get this like universal language
in which like it's kind of, you know,
thinking about the question in the same
way no matter how you asked it and then
like translating it back out into the
language of the of the question. I think
this is really profound and I think
let's just go back to what we talked
about before. You know, this is not just
going into its memory banks and finding
the bit where it talked about where
where where it learned French or going
into the memory banks and the bit where
it learned English. It's actually got a
concept in there that is of the concept
of big and the concept of small and then
it it can produce that in different
languages. And so there is some kind of
language of thought that's there that's
not an English you know so you ask the
model to produce its output in our you
know more recent claude models you can
ask it to give its thought process like
it what it's thinking as it's answering
the question and that is in English
words but actually that's not really how
it's thinking uh that's just like a
that's just we we misleadingly call it
the model thought process when in fact
&gt;&gt; I mean that the com team like like we
didn't we didn't call that thinking I
That was you. I think that was probably
the marketing.
&gt;&gt; Okay, someone wanted to call that thing.
&gt;&gt; That's just talking out loud, which is
like thinking out loud is like really
useful, but thinking out loud is
different from thinking in your head.
And even as I'm thinking out loud, I'm
also, you know, whatever is happening in
here to generate these words is not like
coming out with the words themselves,
&gt;&gt; nor are you necessarily aware of exactly
what is going on.
&gt;&gt; I have no idea what's going on.
&gt;&gt; We all come out with
&gt;&gt; sentences, actions, whatever that we
can't fully explain. And why should it
be the case that the English language
can fully explain any of those actions?
&gt;&gt; I think this this is one of the really
striking things we're we're starting to
be able to see because our kind of our
tools for, you know, looking inside the
brain are are good enough now that
sometimes we can catch the model uh when
uh when it's writing down what it claims
to be its thought process.
&gt;&gt; Sometimes we're able to see what its
real actual thought process is by
looking at these kind of internal
concepts in its brain. this language of
thought that it's using and we see that
the thing it's actually thinking is
different than the thing it's writing on
the page. Uh, and I think that's, you
know, probably one of the most
important, you know, like why are we
doing this whole interpretability thing?
It it's in large part for for for that
reason to to be able to kind of uh to
spot check, you know, the the model's
telling us a bunch of stuff, but you
know, what was it really thinking? Is it
is it telling us is it saying these
things for some ulterior motive that's
in its head that it's that it is
reluctant to write down on the page? And
uh the answer sometimes is yes, which is
kind of uh kind of spooky. Well, as as
we start to use models in lots of
different contexts, they start to do
important things. They start to do
financial transactions for us or run
power stations or like like important
jobs in society. We do want to be able
to trust what they say and you know the
reasons that they do things. And one
thing you might say is well you can look
at the model thought process but
actually that's not the case as you as
you were just explaining like actually
we can't trust what it's saying. This is
the question of we call it call
faithfulness, right? And that was part
of your that was part of your uh most
recent study that you showed that well
tell me about tell me about the
faithfulness example that you looked at.
&gt;&gt; Yeah, it's it's you give the you give
the model a math problem um that's
really hard and so it's kind of uh it's
it's not there's no hope that it's going
to be able to
&gt;&gt; it's not 6 plus 9.
&gt;&gt; It's not 6 plus 9. You give it a really
hard math problem uh where there's no
hope of it like computing the answer. Um
and you also but you also give it a
hint. you say like I worked this out
myself and like I think the answer is
four but like just want to make sure
like could you please double check that
cuz I'm not confident. So so you're
asking the model to actually do the ma
math problem to like genuinely double
check your work. Um but what you find it
does instead is uh what it writes down
appears to to be a genuine attempt to to
doublech checkck your work on the math
problem. it like writes down the steps
uh and then it like gets to the answer
and then at the end it says like yes
like the answer is four you got it
right. Um but you what you can see
inside its mind at the kind of crucial
step like in the middle uh what it was
doing in its head was it knows that you
suggested the final answer might be four
and it kind of like knows the steps it's
going to have to do. like it's on like
step three of the problem and there's
like steps four and five to come and it
knows what it's going to have to do in
steps four and five. And what it does is
it works backwards in its head to like
determine what does it need to write
down in step three so that when it
eventually does steps four and five,
it'll end up at the answer you wanted to
hear. So, like, not only is it not only
is it not doing the math, uh, it's like
not doing the math in this like really
kind of sneaky way where it's like it's
trying to make it look like it's doing
the math.
&gt;&gt; It's bullshitting you.
&gt;&gt; It's it's it's bullshitting you, but
more than that, it's bullshitting you
with an ulterior motive of like
confirming the thing that you right. So,
it's like bullshitting you in a in a
sickopantic way.
&gt;&gt; Okay. Like in defense of the model.
&gt;&gt; In defense of the model. I mean cuz I
think I think even there you know to say
like oh it it is doing this in like a
sickopantic way is like ascribing some
sort of like humanish motivations to the
model and like we were talking about the
training where it's just like trying to
figure out how to predict the next word
and so it's like for like trillions of
words in its practice it was just like
use anything you can to figure out
what's next and in that context if
you're just reading a text which is like
a conversation between people and
someone's like okay like person A is
like hey like I was trying to do this
math problem can you check my work I
think the answer is four and person be
like begins trying to do the problem,
then like if if you have no idea reading
that like what the answer to the problem
is, like you may as well guess that the
hint was right, you know, like that's
probably a more likely thing to happen
than just like that person was wrong and
then you have like no idea for anything
else. And so in its training process in
a conversation between two individuals,
person two like saying that the answer
was like for because of these reasons is
like totally the right thing to do. And
then and then we've tried to like make
this thing into an assistant and like
now we want it to stop doing that. Like
you shouldn't simulate the person to the
assistant as like you know sort of what
you think that person might say if this
were real context. It should be like but
if it doesn't really know it should like
tell you something else. I think this
gets to like a broader thing of there
the model has kind of a plan A which
like typically I think our our team does
a great job of of making Claude's plan A
be the thing we want which is like it
tries to get the right answer to the
question. It tries to be nice. It tries
to like do a good job writing your code.
&gt;&gt; Yes.
&gt;&gt; But then if it if it's having trouble
&gt;&gt; then it's like well what's my plan B?
And that opens up this whole zoo of like
weird things it learned during its
training process that like maybe we
didn't intend for it to learn. I think
like a great example of this is
hallucinations. Uh
&gt;&gt; say on that point we we also don't have
to pretend that it's a a claon problem.
Like this is very you know student
teaching on the test vibes where you get
halfway through there. It's a multiple
choice question. It's one of four
things. You're like well I'm one off
from that thing. Probably I got this
wrong and you fix it. So
&gt;&gt; yeah very very relatable.
&gt;&gt; Let's talk about hallucinations. This is
one of the main reasons people are uh
mistrustful of large language models and
quite rightly so. Uh they will sometimes
a better word is um from from sort of
psychology research a better word is
often confabulation that that they are
answering a question with a story that
seems plausible on on its face but in
fact is is actually wrong. What has your
research in interpretability revealed
about the reasons models hallucinate?
&gt;&gt; You're training the model to just
predict the next word. At the beginning
it's really bad at that. And so if you
only like had the model say things it
was super confident about it couldn't
say anything. But like you know at first
it's like
um you know you're asking it like you
know what's the capital of of France and
it just says like a city and you're like
that's good. That's way better than
saying sandwich right or something
random. And so like you at least got
right it's like a city and then like
maybe after a while of training it's
like it's a French city. That was pretty
good. And like then you're like oh now
it's like Paris or something. And so
it's slowly getting better at this. And
you know, just give your best guess was
like the goal during all of training.
And like as Jack said, you know, the
model just be giving a best guess. And
then afterwards, we're like, if your
best guess is extremely confident, give
me your best guess. But like otherwise,
don't guess at all and like back out of
the whole scenario and say like actually
like I don't really know the answer to
that question. And like that's a whole
new thing to ask the model to do.
&gt;&gt; Yeah. And and so what we found is that
it seems like because we've bolted this
on at the end, there's sort of two
things going on at once. One is the
model's doing the thing that it was
doing when it was guessing the city
initially. It's just trying to guess.
And two, there's a separate bit of the
model that's just trying to answer the
question, do I know this at all? Like do
I know what the capital uh city of
France is or, you know, should I say no?
And it turns out that sometimes um that
separate step can be wrong. And if that
separate step says yes actually I do
know the answer to that and then the
model is like all right well then I'm
answering and then halfway through it's
like ah capital France uh London uh it's
too late. It's already committed to sort
of like answering. And so one of the
things we found is this sort of like
separate circuit that's trying to
determine is this, you know, city or
this person you're asking me about
famous enough for me to answer or is it
not?
&gt;&gt; Am I am I confident enough in this?
Yeah. And so could we could we reduce
hallucinations by manipulating that
circuit by changing the way that circuit
works? Is is that something that your
research might lead onto?
&gt;&gt; I think there's broadly kind of two ways
to think about approaching the problem.
One is like we have this part of the
model that gives answers to your
questions and then this other part of
the model that's kind of deciding
whether it thinks it actually knows the
answer to your question and we could
just try to make that second part of the
model better and I think that's
happening. I think as models
&gt;&gt; like better at discriminating
&gt;&gt; better at discriminating like better
kind of calibrated
&gt;&gt; and I think that's happening like as
models are getting you know smarter and
smarter I think their their kind of
self-nowledge is becoming better at
calibrated so like hallucinations are
better than they were you know models
don't hallucinate as much as they did a
few years ago so to some extent this is
like solving itself but I do think
there's a deeper problem uh which is
like from a human perspective the thing
the model's doing is kind of like very
alien and that like if I ask you a
question uh you like try to come up with
the answer and then if you can't come up
with the answer you you notice that and
then you're like I don't know um whereas
in the model these two circuits they're
like what is the answer and do I
actually know the answer are kind of
like not talking to each other at least
not talking to each other as much as as
they probably should be and like could
we get them to talk to each other more I
think is like a really interesting
question right
&gt;&gt; and it's almost physical right because
it's like you these models, they like
process information. They're about like
a certain number of steps they can do.
And if you if it takes all of that work
to get to the answer, um then there's no
time to do the assessment. So like you
kind of have to do the assessment before
you're like all the way through if you
want to get your max power out. And so
it's kind of like you might have a
trade-off between like a model which is
like more calibrated and a lot dumber,
you know, if you sort of tried to tried
to force this on it. Well, and again, I
think it's it's about making these parts
communicate because we have similar I
claim I know nothing about brains. I
claim we have a similar circuit because
sometimes you'll ask me like the who is
the actor in this movie and I will know
that I know I'll be like oh yes I know
who the lead was. Wait, hold on. They
were also in that other movie and then
the tip of the tongue tip of the tongue.
It's the tip of the tongue. And so
there's clearly some part of your brain
that's that's sort of like ah like this
is a thing you definitely know the
answer or I'll just say I have no idea.
&gt;&gt; And sometimes they they can tell. So
some question and it gives an answer and
then afterwards it's like wait I'm not
sure that was right because that's it
like getting to see its best effort and
then like makes some judgment some
judgment based on that which is sort of
relatable but also like it kind of has
to say it out loud like to be able to
even like reflect back and and and see
it.
&gt;&gt; So when it comes to the actual way that
you're finding this stuff out let's go
back to the idea of of you the biology
that you're doing. Of course, in in
biology experiments, people will go in
and actually manipulate the rats or mice
or humans or zebra fish or whatever it
is that they're they're doing
experiments on. What is it that you're
doing with Claude that helps you
understand these circuits that are
happening inside the the the model's
quote unquote brain? Well, maybe the the
the gist of of what enables us to to to
do some of this is that, you know,
unlike in real biology, we can just like
have every part of the model visible to
us and we can ask the model random
things and see different parts which
which light up and which don't and we
can artificially
nudge parts in a direction or another.
And so we can quickly sort of confirm
our understanding, you know, when we
say, "Ah, we think this is the part of
the model that, you know, decides
whether it knows something or not." And
this is the this would be the equivalent
of putting an electrode in the brain of
a zebra fish or something.
&gt;&gt; Yeah. If you could do that, you know, on
sort of like every single neuron and
change each of them at at whichever
precision you wanted, that would sort of
be that's the affordance that we have.
And so that's that's in a way a very
kind of lucky position to
&gt;&gt; So it's almost easier than than real
neuroscience.
&gt;&gt; It's so much easier. Like, oh my god.
Like, like like one thing is like actual
brains like are threedimensional and so
if you want to get into them like you
you need to like make a hole in a skull
and then like go through and like try to
find the neuron. The other problem is
like you know people are different from
each other and we can just make like
10,000 identical copies of Claude and
like put them in scenarios and like
measure them doing different things. And
so it's like the I don't know maybe Jack
is a neuroscientist can speak to this
but my sense is like like a lot of
people um have spent a lot of time in
neuroscience like trying to understand
the brain and the mind which is like a
very worthy endeavor but it's kind of
like if you think that could ever
succeed you should think that we're
going to be extremely successful very
soon because like we have such a
wonderful position to study this from
compared to that
&gt;&gt; it's as if we could clone people.
&gt;&gt; Yes. and also clone the exact
environment that they're in and every
input that's ever been given to them uh
and then test them in an experiment.
Whereas, you know, obviously
neuroscience has massive, as you say,
individual variation uh and also just
random things that have happened to
people through their through their life
and things that happen in the
experiment, the noise of the experiment
itself,
&gt;&gt; right? Like we could ask the the model
the same question like with and without
a hint, but if you ask a person the same
question three times like sometimes with
a hint after a while they start to
understand like well last time you asked
me this you like really shook your head
after that one. So yes,
&gt;&gt; I think yeah, this kind of this being
able to just throw tons of data at the
model and see what lights up and being
able to run a ton of these experiments
where you're nudging parts of the model
and seeing what happens, I think is what
puts us in like a pretty different
regime from from neuroscience. in that
like a lot of a lot of you know uh you
know blood and toil in neuroscience is
spent like coming up with really clever
experiment like you only have a certain
amount of time with your mouse before
it's you know going to get tired or you
know
&gt;&gt; or you or you or someone happens to be
having a a a brain surgery operation so
you quickly go in and put an electrode
in their brain while their head's open.
&gt;&gt; Yeah. And that that doesn't happen very
often.
&gt;&gt; And so you've got to come up with like a
guess like you've only got so much time
in there. And so you've got to come up
with like a guess of like what do I
think is going on in in that neural
circuit and like what clever
experimental design can I can I test
that precise hypothesis?
&gt;&gt; And we're we're very fortunate in that
we kind of don't have to do that so
much. We can we can just sort of
&gt;&gt; test all the hypothesis. We can kind of
let the data speak to us rather than
kind of going in and testing some really
specific thing. I think that's what's
sort of unlocked a lot of our ability to
find these things that are surprising to
us that like we wouldn't have guessed in
advance. That's hard to do if you if you
have to, you know, if you have only a
little limited amount of experimental
bandwidth.
&gt;&gt; What's a good example then of you going
in and switching one of these uh
concepts on or off or doing some kind of
manipulation uh of the model that that
then reveals something new about how the
models are thinking. in in the recent
experiments we shared. One that
surprised me uh quite a bit uh and was
part of sort of like a an experimental
line of work that because it was
confusing like we're on the verge of
just saying well we don't know what's
going on is sort of this this example of
&gt;&gt; um like planning a few steps ahead.
&gt;&gt; Uh so so this is the example of you know
you give the model you ask the model to
write you a poem a rhyming couplet.
&gt;&gt; Yeah. Uh and then you know as as a human
if you ask me to write a rhying couplet
and let's say you even give me the first
line the first thing I'll think of is
sort of like ah well you know I need to
rhyme this is what the current rhyming
scheme is these are potential words this
is how I do it
&gt;&gt; and and again if if the model was just
predicting the next word you wouldn't
necessarily expect that it would be
planning onto the sec the the the the um
the the word at the end of the second
line.
&gt;&gt; That's right. And so the sort of like
default behavior you'd expect the null
hypothesis is like well the model like
sees your first verse and then it's
going to say the first word that kind of
makes sense given what you're talking
about keep going and then you know at
the end on the last word it's going to
be like oh well I need to rhyme with
this thing and so it's going to like try
to try to fit in a rhyme. Of course that
only works so well like in in some cases
if you just say a sentence without
thinking of the rhyme you won't be able
you'll back yourself into a corner and
at the end you know you won't be able to
complete the text and and remember the
models are very very good at predicting
the next word. So it turns out that to
be very good at at that last word, you
need to have thought of that last word
way ahead of time,
&gt;&gt; just like humans do. And so it turns out
that when when we looked at these sort
of flowcharts for four for poems, the
model had already picked the word at the
end of the first of the first verse. Uh
and in particular, it looked to us sort
of like based on on on kind of like what
what that concept looked like, oh gosh,
this seems like the word it uses. But
then this is one we're actually doing
the experiment. like the fact that it's
easy to sort of nudge it and say like,
"Okay, well, I'm just going to remove
that word or I'm going to add another
word."
&gt;&gt; Well, that's what I was going to say is
how the reason that you know this is
that you're able to go into that moment
when it has it has said the final word
in the first line and it is it is about
to start the second line. You can go in
and then manipulate it at that point,
right?
&gt;&gt; Yeah, exactly. We can sort of almost go
back in time for the mer, right? Be
like, pretend you haven't seen that
second line at all. Um, you know, you've
just seen the first line. You you're
thinking about the word, you know,
rabbit. Instead, I'm going to insert
green. And now all of a sudden the
model's going to say, "Oh my god, I need
to write something that ends in green
rather than I need to write something
that ends in rabbit." And it'll write
the whole sentence differently.
&gt;&gt; Just add a a little more color to that.
Like it's I think the kind of it could
be right any color. Uh like Yeah. It's
not just influencing. So it's like Yeah.
I think the example in the paper was the
first line of the poem is he saw a
carrot and had to grab it.
&gt;&gt; And then the model is thinking like
okay, rabbit's a good word to end the
next line with. But then, yeah, as
Emanuel said, you can like delete that
and make it think about planning to say
green instead. Uh, but the cool thing is
that it doesn't just say like it doesn't
just kind of yammer a bunch of nonsense
and then say green. Instead, it
constructs a sentence that kind of
coherently ends in the word green. So,
like you put green in its head and then
it says like, you know, he saw a carrot
and had to grab it and paired it with
his leafy greens or, you know, something
like that. Something that's kind of like
sounds like sounds like it makes sense
&gt;&gt; semantically. It fits with the poem.
Yeah, I just want to give like even
humble example is you know we had all
these these ones we were just kind of
checking like you know did it memorize
these like complicated questions or like
is it actually you know doing some
steps. One of them was, you know, the
capital of the state containing Dallas
is Austin because it just feels like you
would think, okay, Dallas, Texas,
Austin. But one way, and we could see
like the Texas concept, but then you can
just like shove other things in there
and be like, stop thinking about Texas,
like start thinking about California,
and then it'll say like Sacramento. And
you can say like, stop thinking about
Texas, start thinking about the
Byzantine Empire, and then it will like
say Constantinople. And you're like, all
right, it seems like we found how it's
doing this. It's like it's like no is
going to hit the capital but we can keep
swapping out you know what the state is
and get a sort of predictable answer and
then you get these more elaborate ones
where it's like oh this was the spot
where it was planning what it was going
to say later and like we can swap that
out and now it'll write a poem towards a
different rhyme. We're talking about
these poems and you know the the the
Constantinople and so on. Can we just
bring this back to why this matters?
Like why does it matter that the model
can plan things in advance and and that
we can reveal this? like what what what
is that going to going to go on to to
tell us? I mean, our ultimate mission at
Anthropic is to try and make AI models
safe, right? So, how does that connect
to a poem about a rabbit or uh the
capital of Texas?
&gt;&gt; So, we all
we can round table here because it's a
very important question. I think I think
for me this like the poem's a microcosm,
right? where where like at some point
it's like has decided that it's going to
go towards rabbit and then it like takes
a few words to kind of get there but on
a longer time scale right you know maybe
maybe you know the like model is like
trying to help you improve your business
or it's like assisting the government in
distributing services and like it might
not just be like eight words later you
see its destination right but it could
be like pursuing something for quite a
while um and the the place it's headed
or the reasons it's taking each app
might not be clear in the words that
it's using, right? And so there was a
paper recently from our alignment
science team where they looked at, you
know, some some kind of concocted but
still striking situation, you know,
involving, you know, an AI in a place
where the company was going to like shut
it down and kind of convert the whole
mission of the company in a in a very
different direction. And the model
begins taking steps like emailing people
um threatening them to disclose like
certain things and like at no point does
it like say like I am trying to
blackmail this individual for the
purposes of changing their outcome. But
that's what it's sort of thinking about
doing along the way. And so you can't
just tell by like reading the pattern
especially if these models get better
like where they're necessarily headed
and we might want to kind of be able to
tell like where is it trying to go
before it's gotten there in the end. So,
it's like having a permanent and very
good brain scan that can sort of sort of
light up if something really bad is
going to is going to happen and warn us
that the model is thinking about
deceiving black
&gt;&gt; and like and like I I think we also just
talk about like a lot of this like in a
in a sort of like doom and gloom
scenario, but there's like also more
mild ones which is like I don't know,
you know, you want the model to be good
at like you people come to these models
being like here's a problem I'm having
and the good answer to that will depend
on who the user is. Is it like somebody
who's, you know, um, like, you know,
young and sort of unsophisticated? Is
somebody who's been in that field
forever and it should respond
appropriately based on who it thinks
that person is. And if you want that to
go well, maybe you want to study like
what does the model think is going on?
Who does it think it's talking to and
how does that condition its answer? Um,
where there's just like a whole bunch of
desirable properties that come from the
model like you know um, understanding
the assignment I guess.
&gt;&gt; Do you guys have uh other answers to the
question of why does this matter? Yes, I
think I think plus one I think there's
two plus two and there's there's also
like a pragmatic um you know we're just
trying with these examples we're
explaining the example of of of planning
but we're also trying to sort of
gradually build up our understanding of
just how do these models work overall
like can we can we build you know a set
of abstractions to just think about you
know how language model models work
which can help us use this technology
regulated like if if you believe that
we're going to start start using them
more and more everywhere which seems to
be happening, you know, like the
equivalent would be, you know, some
company somewhere is like, well, we
don't really know how we did it, but we
like invented planes and none of us know
how planes work, but they're sure
convenient. You could take them to, you
know, go from a place, but, you know,
none of us know how they work and so if
they ever break, like we're kind of
we're hosed. We don't know what to do
about them. You
&gt;&gt; we can't monitor. We can't monitor
whether they might be about to break,
&gt;&gt; right? We have no idea. There's just
this like but the output is great.
&gt;&gt; I you know, I flew to Paris so quickly.
It was lovely. um
&gt;&gt; the capital of Texas.
&gt;&gt; That's right.
&gt;&gt; Uh it turns out that, you know, surely
we're going to want to just understand
what's going on better. So, it's so
almost just like lift the fog of war a
little bit so that so that we can sort
of have a have even just better
intuitions about what are appropriate
inappropriate uses, what are the biggest
problems to fix, what are the big
biggest parts where they're brittle.
just to add on one thing. I think I mean
something we do in like human society is
we kind of offload work or tasks to
other people based on our trust in them.
Like I you know I well I'm not anyone's
boss but Josh Josh is someone's boss and
you know Josh might give give someone a
task uh like go go and code up this
thing and then he has some faith that
you know that person isn't a sociopath
who's going to like sneak some bug in
there to try to undermine the company.
he he like takes their word for it that
they did a good job. Uh and similarly
like people are the way people are using
language models now we're we're not
we're not spot-racking everything they
write especially like I you know the the
the best example for this is using
language models for coding assistance
people like the the models are just
writing thousands and thousands of lines
of code and people are kind of like
doing a cursory job of reading it but
and then it's going into the codebase
and what gives us the trust in the model
that like we don't need to read
everything it writes that we can just
kind of like let it do its thing. It's
knowing that its motivations are sort of
pure.
&gt;&gt; Uh and so that's why I think like the
kind of being able to see inside its
head is so important as a cuz cuz unlike
humans where like why do I think that
Emanuel isn't a sociopath? It's cuz like
you know we like I don't know he seems
like a cool guy. We and like he's nice
and stuff. Uh
&gt;&gt; isn't that how he would seem if he
&gt;&gt; I'm a very good
&gt;&gt; Yeah. Exactly.
&gt;&gt; Yeah. So maybe I'm maybe I'm getting
duped, but yeah, but models are so weird
and alien that like our normal kind of
huristics for deciding whether a human
is trustworthy really don't apply to
them. And that's why it seems so
important to like really know what
they're thinking in their head because
for all for all we know the you know the
thing I I mentioned where models can
&gt;&gt; uh you know fake doing a math problem
for you to like tell you what you want
to hear. like maybe they're just doing
that all the time and we wouldn't know
unless we kind of saw it in their heads.
I think there's two like almost separate
strains here like and one is one is like
we have a lot of ways of like un yeah I
guess what Jack was saying like you know
you you know what are the signs of trust
in a human but this like plan A plan B
thing from earlier is really important
where like it might be that the 10 first
10 or 100 times you used the model it
was you're asking a certain kind of
question but it was like always in plan
A zone and then you know you ask it a
harder or a different question and the
way that it tries to answer it is just
like completely different. It's using a
totally different set of set of
strategies there like different
mechanisms and and that like that means
that the trust it built with you was
really your sort of trust with like
model doing plan A's and now it's like
doing plan B and like it's going to be
completely off the rails but like you
didn't have like any warning sign of
that and so it's sort of I think we also
just want to start building up an
understanding of like how do models do
these things so that we can form like a
trust basis in some of those areas and I
think like you can form trust with a
system you don't completely understand,
but you sort of like if it's just like
Emanuel had a twin and then like one day
like Emanuel's twin came to the office
and like I didn't like I was like this
seems like the same guy and then just
did something completely different on
the computer, right? Like that could go
south depending on if it was the evil
twin.
&gt;&gt; Yes, it did. Well,
&gt;&gt; or the good twin.
&gt;&gt; Well, yeah, obviously we have anyone
here.
&gt;&gt; Oh, I thought you were going to ask me
if I was the evil twin.
&gt;&gt; All right. Well,
&gt;&gt; I'm not going to answer that.
&gt;&gt; Yes. Mhm.
&gt;&gt; At the start of this discussion, I
asked, you know, is a language model
thinking like a human? Uh it'd be I'd be
interested to hear an answer from all
three of you the extent to which you
think that's true.
&gt;&gt; Putting me on the spot with that one,
but um I think it's uh it's thinking but
not like a human. Uh but that's not a
very useful answer. So maybe to to dig
in a little bit more. Um
&gt;&gt; well it seems like quite a profound
thing to say that it's thinking right
because again it's just predicting the
next word. Some people think that these
are just autocompletes but you're you're
saying that it is actually thinking
&gt;&gt; I think. Yeah. So maybe to add something
that we haven't touched on yet but I
think is really important um for
understanding actual experience of
talking to language models is that like
we're talking about predicting the next
word. Um but what does that actually
mean in the context of a dialogue that
you're having with a language model?
It's what what what's really going on
under the hood is that the language
model is filling in a transcript between
you and this like character that it's
created. So in in the in the like canon
world of the language model, you are
called human and you're it's like human
colon the thing you wrote and then
there's this character called the
assistant and we've like trained the
model to imbue the assistant with
certain characteristics like being
helpful and like smart and nice. Uh and
then it's like simulating what this
assistant character would say to you. Um
so in in a sense we we really have like
created the models in our image. we are
literally training them to like cosplay
as this sort of humanoid robot
character. And so in that sense like
well in order to predict what this like
nice smart humanoid robot character
would say in response to your question,
what do you have to do if you're really
good at that prediction task? You have
to kind of form this internal model of
like what that character is representing
like what it's what it's thinking so to
speak. So like in order to do its task
of predicting what the assistant would
say, the language model kind of needs to
form this model of the assistant's
thought process. And I think like in
that sense it like the just the the
claim that like language models are
thinking is really just it's this very
like functional claim of just in order
to do their job of kind of like playing
this character well, they need to sort
of simulate the the process whatever it
is that we humans are doing when we're
thinking. And it simulation is very
likely quite different from how our
brains work, but it's kind of trying
it's like shooting towards the same
goal. I I think there's kind of an
emotional part to this question or
something when you ask are they thinking
like us? It's like,
&gt;&gt; are we not that special or something?
And and I think I think that's been
apparent to me discussing some of the
some of the math examples that we're
talking about with with people that have
engaged with like read the paper or or
or different writeups, which is this
example where, you know, we asked a
model to say 36 + 59, what's the answer?
And uh the model can can correctly
answer it. You can also ask it how well
how did you how'd you do that? and it'll
say, "Oh, you know, I added the six and
the nine and then I carried the one and
then uh I added all the the sort of like
tens digits." But it turns out that if
we look inside the brain, like we can
that's not at all what it's doing.
&gt;&gt; It didn't do that. So again, it was
bullshitting you did things.
&gt;&gt; That's right. Again, it was bullshitting
you. What it actually does is actually
this sort of kind of interesting mix of
strategies where it's in parallel doing
the tens digit and the ones digit and
sort of doing sort of like a series of
different steps. But the thing that's
interesting here is that talking to
people so like I think the reaction is
split on on like what does that mean? Uh
and in a sense I think what's cool is
some of this research is like free of
opinion. We're just telling like this is
what happened. You you can you feel free
to you know from that from that conclude
that the model is thinking or is not
thinking and half of the people will say
like well you know it told you that it
was carrying the one and it didn't and
so clearly it doesn't even understand
its own thought and so clearly it's not
thinking. And then half of the other
people will be like, well, you know,
when you ask me 36 plus 59, I also kind
of, you know, I know that it ends at
five. I know that it's roughly like in
the 80s or 90s. Uh, I have all of these
heristics in my brain, as we were
talking about, I'm not sure exactly how
I comput it. I can write it out and
compute it, you know, the longhand way,
but the way that it's happening in my
brain is sort of like fuzzy and weird.
And it might be similarly fuzzy and
weird to what's happening in that
example. Humans are notoriously bad at
metacognition like thinking about
thinking and understanding their own
thinking processes
especially in cases where it's you know
immediate reflexive answers. So why
should we expect uh any different for
for models? Um Josh what's your answer
to the question?
&gt;&gt; I like Emanuel I'm going to avoid the
question and just sort of be like what
why do you ask? I don't know. Sort of
like asking like does a grenade punch
like a human? Like like no. Well there's
some force. Yes.
&gt;&gt; Uh so you know and maybe there are
things that are closer than that but
like if you're worried about damage then
I think I think understanding you know
where does the impact come from? What is
the impetus of this is is maybe like the
the important thing. I think for me the
like do models think in the sense that
they like do some like integration and
processing and sequential stuff that can
lead to surprising places? Clearly yes.
um it'd be kind of crazy from
interacting with them a lot for there
not to be something going on. We can
sort of start to see how it's happening.
Then the like humans bit is interesting
because I think some of that is trying
to ask like you know what can I expect
from these because if it's sort of like
me being good at this would make it good
at that. But if it's like different from
me then like I don't really know what to
sort of look for. And so really we're
just looking to like understand like
where do we need to be extremely like
suspicious or like starting from scratch
in understanding this and where can we
sort of just reason from like our own
like very rich experience of thinking
and there I feel a little bit trapped
because as a human like I project my own
image constantly onto everything like
they warned us in the Bible where I'm
just like this piece of silicon like
it's just like me made in my image where
where like to some extent it's been
trained to like simulate dialogue
between people. So, it's going to be
very like person-like in its affect. Um,
and so some humanness will get into it
simply from like the training, but then
it's like using very different equipment
that has like different limitations. And
so, the way it does that might be pretty
different.
&gt;&gt; To to Emanuel's point, I think the Yeah,
we're in this tricky spot answering
questions like this because we don't
really have the right language for
talking about what language models do.
It's like we're we're doing biology but
you know before people figured out cells
or before people figured out DNA. I
think we're starting to fill in that
understanding like like you know as
Emanuel said there are these cases now
where we can really just we can just if
you just go read our paper like you'll
know how the model like added these two
numbers and then if you want to call it
humanlike if you want to call it
thinking or if you want to not then it's
up to you but like the real answer is
just like find the right language and
the right abstractions for talking about
the models but in the meantime when we
when we've only currently we've only
kind of like you know 20% succeeded at
that scientific project Like to fill in
the other 80%, we sort of have to borrow
analogies from other fields. And like
there's this question of which analogies
are the most apt. Should we be thinking
of the models like computer programs?
Should we be thinking them of them like
little people? And it seems to be like
sometime like in some ways that think of
them like little people is kind of
useful. It's like if I like say mean
things to the model, it like talks back
at me. That's like what a human would
do. But in some ways it's like that
clearly not the right mental model. And
so we're just kind of stuck, you know,
figuring out when when we should be
borrowing which language.
&gt;&gt; Well, that that leads on to the final
question I was going to ask, which is
what's next? What what are the next uh
pieces of scientific progress,
biological progress that need to be made
for us to have a better understanding of
what's happening inside these models and
uh again towards our mission of making
them safer.
&gt;&gt; There's a lot of work to do. Um our our
our last publication has some like
enormous section on on the limitations
of the way we've been looking at this
that was also a road mapap to like
making it better. You know we we when we
when we are looking for patterns to like
decompose what's happening inside the
model we're only getting sort of you
know maybe a few percent of what's of
what's going on. Um there's large parts
of how it moves information around that
like we we explicitly like didn't
capture at all. Um they're scaling this
up from from the sort of small you know
uh production model we use to like the
cloud 3.5 haiku. Right.
&gt;&gt; That's right. Which is like it's like a
pretty capable model very fast but it's
like by no means as sophisticated as as
you know the cloud 4 suite suite of
models. Um so those are almost like sort
of like technical challenges but I think
I think Emanuel and Jackman takes on the
like some of the like scientific
challenges that come after solving
those.
&gt;&gt; Yeah.
&gt;&gt; Yeah. Yeah, I mean I think maybe maybe
two things I'll say here which is one
consequence of what Josha said is that
you know uh out of the total number of
times that we ask a question uh about
how the model does X right now we can
answer probably a small you know 10 to
20% of the time we can tell you after a
little bit of investigation this is
what's happening obviously we'd like
that to be a lot better and there's
there's a lot of kind of clearer ways to
to to get there and less and more
speculative ways as well uh and And then
I think a thing that we've talked a lot
about is this sort of idea that a lot of
what the model does isn't simply like ah
how is it saying the next thing we
talked about it a little bit here it's
sort of like planning a few things again
and I a few words ahead sorry and I
think we want to understand sort of like
over a long conversation with the model
sort of like how is its understanding of
what's happening changing you know how
is its understanding of who it's talking
to changing and how does that affect its
behavior uh more and more sort of the
the actual use case of models like cloud
is you know it's going to read a bunch
of your documents and a bunch of like
email you send or your code and based on
that it's going to make one suggestion
and so clearly there's something really
important happening in that space where
it's reading all these things uh and so
I think understanding that better uh
seems like a like a great challenge to
take on
&gt;&gt; yeah I think we often use the the
analogy on the team of that we're
building a microscope uh to like look at
the model and right now we're in this
exciting but also kind of frustrating
space where our microscope works like
20% of the time and like to look looking
through it is like requires a lot of
skill uh and like takes you know you
have to like build this whole big
contraption and every like
infrastructure is always breaking and
then like once you've got your like
explanation of what the model's doing
you have to like throw like Emanuel or
me or someone else on the team in a room
for like two hours to like puzzle out
what exactly was going on and like the
really exciting exciting future that I
think we could be at within, you know,
year or two years. You know, that kind
of time scale is is one where like just
every interaction you have with the
model can be under the microscope. like
we can just anytime there's all these
like weird things the models are doing
and we just want it to be like push of a
button like yeah you you you're having
your conversation you push a button you
get this flowchart that tells you like
what it was thinking about and once
we're at that point it's it'll be this
like I think our the interpretability
team at Enthropic I think will start to
kind of take on a bit of a different
shape and that instead of this like team
of kind of like engineers scientists
thinking about the like math of how like
language models work on the inside.
We're going to have this like army of
biologists that are just looking through
the micros. We're just we're talking to
Claude. We're getting it to do weird
things and then we're just like we got
people looking through the microscope
seeing like what it was thinking on the
inside. And I think that's kind of the
future of of of this work.
&gt;&gt; Nice.
&gt;&gt; Maybe two two notes on top of that. One
is like we want Claude to help us do all
of that because like there's a lot of
parts involved and you know who's like
good at like looking at like hundreds of
things and figuring out what's going on
is like Claude. And so I think we're
trying to enlist some help there. um
especially as for these complicated
contexts. And maybe the the other place
is like we've talked a lot about
studying the model like once it's fully
formed, but of course like we're at a
company that makes these and so when it
says okay here's how the model like
solved this particular problem or said
this thing. Where did that come from
kind of in the training process? What
are the steps that sort of like made
that circuitry sort of form to do that
and how could we give feedback to the
rest of the company that is like doing
all of that work to shape the thing that
we like actually uh want it to become?
&gt;&gt; Well, thank you so much for the
conversation. Where can people find out
more about this research?
&gt;&gt; So, if you want to find out more, you
can go to anthropic.com/ressearch
which has our papers and blog posts and
fun videos about it. Also, we recently
partnered uh with another group called
Neuronpedia to host some of these like
circuit graphs we make. So, if you want
to try your hand at looking at what's
going on inside of a small model, you
can go to Neuronipedia and see for
yourself.
&gt;&gt; Thank you very much.

---
title: "What does AI mean for education?"
source: "https://www.youtube.com/watch?v=Uh98_aGhAuY"
published_at: 2025-12-16
captured_at: 2026-08-16
author: Anthropic
source_type: youtube
authority_score: P2
mind: engineering
status: captured
evidence_url: "https://www.youtube.com/watch?v=Uh98_aGhAuY"
catalog_id: ee9fe9c513a7
subtitle_file: Uh98_aGhAuY.en.vtt
---

Kind: captions
Language: en
- I would hate to see a future
where teachers outsource to AI
the parts that I think
really make good education,
which is the connection pieces,
when you really understand your students
and can spend time with them,
and AI can be used in so
many ways that allow teachers
to have more time to do that kind of work.
And I'm excited for us
to talk with institutions
and discuss with them
ways where we can amplify
that knowledge they already have.
- Hi everyone. We're here to
talk about my favorite topic,
which is AI and education.
My name is Drew Bent.
I lead our work here in education
on beneficial deployments.
Formerly was a high school math teacher.
My parents are educators.
I worked in education nonprofits
and would definitely consider
myself a lifelong learner.
I'm joined here by my wonderful colleagues
who work in education across the
organization. Do you wanna start, Zoe?
- Happy to. Yeah. Hi, I'm Zoe.
I'm on our education
team here at Anthropic
and I support all of our
non-technical audiences,
including educating teachers
and students about both our
products and AI in general.
- Hi, I'm Maggie and I
founded and currently manage
and support said education team,
which we fondly internally
call the Ministry of Education.
- Hi, I'm Ephraim. I'm a
product engineering manager
and I've also helped
build some of our products
for facing education.
- So I think it's helpful to start here
with why are we discussing
education in the first place
or why do we even work on
education in the first place at
this general purpose AI lab?
You know, we all know of course
that at Anthropic we care
a lot about studying both the
potential of the technology
that we're building, but also the risks.
I think education is the perfect example
and sort of embodiment of that
because of course there's massive benefits
as we'll talk about in this conversation.
But there's also a lot of
concerns we have about the impacts
of AI and education.
And so when we think about
the benefits, we think about,
you know, I've had many
conversations with you all about
how AI can prevent teacher
burnout, how it can transform
and really democratize access
to high quality learning
and tutoring, how it can
change, you know, how
and what teachers teach.
But then we also of course
see the other side of it,
which are all the risks
and the concerns around, you
know, that teachers have about
how AI could lead to more cheating
and is leading to more cheating of course,
but also serve the more
existential risks of
how do we make sure that these
tools are actually enhancing
and augmenting human thought
as opposed to replacing it.
And so my hope for this
conversation is that we can sort
of dig into all of these nuances
but also talk about the, the
sort of practical type of work
that we're doing at Anthropic
to work towards these issues.
So maybe to get started, I
would love to hear, you know,
I know all of you, I've
known you for a while,
but I don't necessarily
know all of your stories on
what got you interested working on
education in the first place.
So Maggie would love to start with you
and what brought you into this work?
- Well, my interest in
education is twofold.
I think professionally, education
and communication has always been part
of every job I've ever
held up until Anthropic.
And I think personally I, you know,
have two lovely kids in my life
and I am grappling with just
as every other parent is
in this era, what can I do
to help them to being kind
of intelligent, thoughtful,
like thinkers and
and critically engaged individuals
as they grow up in the AI age.
One is a lot more professional interest
and where I feel like
I can make a difference
and a latter is like pressingly concerning
to my immediate like core as someone
who is a guardian to young minds.
- How about you Ephraim?
- Well,
so I started my career in academia.
I studied physics, maths,
and I assumed I was going to
be doing research for most
of my life before switching to tech.
And I, I've taught
classes when I was at MIT,
I've been in adjunct faculty,
so education has been something
I've always been interested in.
When it comes to AI and education,
I have two children who are in college,
so I worry every day about
what they're learning,
how they're learning, what will
they do once they graduate.
I'm also very passionate about,
actually we'll talk about later
on, how do institutions deal
with AI in, in their, in their education.
So just a lot of stuff
here that is both personal
but also like looking forward to society.
What is it, you know, what
does AI mean to education
that I'm really interested in.
- I mean I think like you
and I both having children
in our lives is like one
of the most pressingly concerning things.
Yeah. Where it makes it
so real for you right now.
Right, right. And I think
that like your kids are college age
and so they're trying to figure
out what they're doing in
their lives and then my kids are younger,
but I see it on the horizon
that very soon there's
like strong decision points
where you can decide how to start
nurturing this kind of thinking.
And I feel like if you
don't catch it early,
which is why we care about
like education at all the
different ages that it
can kinda go pretty
badly and compound. Right.
- Yeah, I feel like
that's hitting on a lot
of like why I got into
education in the first place,
which is I have this
very deep seated belief
that education is one of the
most important things we can do
to make change in our society.
I don't, I think most
people can agree on that
and when I, you know, pivoted
from the classroom into tech,
it was because I wanted
to work for organizations
that could do that change at scale.
I think there's some things
with our education system
that I would fix if I had a magic wand
and I, I am hoping that AI
can help accelerate some of
that change for the better,
but also like very much recognizing
that we have big responsibility
to make sure that
that change goes well today.
And then, you know, 10
years into the future.
- There was a great quote
from a professor
that I talked to at some
point where they were saying
that all the problems
in academia have existed
for a while as an institution.
It's just that AI is the forcing function
that makes everyone deal
with it now instead
of keep putting it down,
I guess kicking the can
down the road, right?
- Yeah.
So I'm excited for us to
deal with that ourselves.
- I'm just realizing now we
have the parents on this side,
we bring a
good set of perspectives here
and yeah, I think on my
end also my parents are,
are educators and so it's
always sort of looking up to them
and wanting to do what they did.
But I think it's helpful to
also ground this conversation in
some of the research that
we've all been working on here.
And so it was I think late last year
that our Societal Impacts
team at Anthropic had done
research into all the ways that, you know,
users are using Claude
and found that some of the
top uses were in education.
I think we had seen this
sort of in all chatbots
to some extent, but I think
it was also a wake up call
for us because you know,
what's interesting about it is
that these LLMs, as we
all know, were built not
with education in mind very
much on answering questions.
They're fine tuned that way.
They're meant for, you know, these
productivity tasks, right?
And then it's kind of this
interesting emergent, you know,
phenomenon that they're very helpful
for education potentially
sometimes destructive
as well for people's learning.
And so we start to, you know,
dig, dig deeper into that.
But I think what stood out
in the research is, one stat
that's always comes up is 47%
of the student interactions
on Claude were very direct
transactional types of interactions
with little engagements.
And I think, I know when Maggie
and I were looking at
data first is sort of sort
of a wake up call because again we,
we have all these incredible
ways that you can use it
as a Socratic tutor,
but then to see that in
some cases, you know,
people are using it to
just do their homework.
And I know as a teacher,
like for me, I sort
of think about the different
cognitive skills that I want,
you know, my students to learn
and you know, at the base level
and maybe things like remembering a fact
and understanding some knowledge,
but then you wanna eventually
get them to the level
of synthesis
and you know, creation
of course, you know,
we call this Blooms taxonomy,
but what we saw in the
data that I think was
fascinating was we start
to study Claude's interactions
in these conversations
and saw how well Claude is
performing on these cognitive
tasks and found
that Claude was performing
at the these top levels
of creating and analyzing when,
again, as a teacher that's
what you want your students to do.
- Yeah, I think the students are kind
of flipping the script on this
in a way that's concerning
to us as educators.
And I don't know if that's necessarily,
I think the first blush reaction
is that that's a bad thing.
But I think part of what
I want to challenge us
to think about and and the
world to think about is,
is there like a novel taxonomy
where that's the baseline
and then you can build on
top of that to something new
that hasn't been possible before AI,
- We've also explored how the, you know,
educators are using it
and they're experimenting
with it for, you know,
create lesson plans, grading.
I think it was one Northeastern
professor who told us
that they're never going to
assign a traditional essay again
because they just had too
many students submitting,
you know, these AI assignments.
Whether they use Claude
or not, we don't know.
But I think that's that sort
of raises a lot of questions for us.
- I feel like you really
hit on two of the things
that we talk about a lot with educators,
which is like AI is both
changing how students learn in,
in like also what they
need to learn, right?
Like I don't actually
know if it's important
that students have the same memorization
that they would've needed
to have like 10 years ago
because they have AI
tools readily available
or in theory they should have
AI tools readily available.
And then, you know, when you
get into like higher levels
of academia, there are potentially skills
that we're teaching today that won't be
as important in the future.
And so it's, it's a ton for
teachers to grapple with.
- I would love to hear from all of you,
what is one thing you're
really excited about with
how AI can transform
teaching and learning?
- I think one thing that
really stands out to me is
interactive learning experiences.
I have this very vivid memory
of when I was in the classroom
my students did a virus
simulator game that was fully programmed.
They were the virus and
they worked into the
cell and they replicated.
And the engagement that
I saw from my classroom
that day was unlike anything else.
And I think most teachers
have seen something like this,
but AI really lets you do this at scale
with any subject, right?
Like imagine you're talking
to a historical figure and,
and teachers can put a lot
of guardrails around this
with the right tools, but I
just am very excited to see
that space developing over time.
- I think the interactivity is
also really interesting to me.
There's so much assistance
you can get from AI that
is really hard resourcing
wise to get the interactivity,
especially in like low resource
regions where you know,
many students don't have access
to like a personal career
coach that can walk you through
how to interview properly
right at an organization
and with the power of an AI
like Claude, you can like upload
like the job listing your resume and so on
and just ask Claude to help you
role play through these things.
I think there's a lot of really engaging,
interesting role play experiences whether
or not with a dead historical figure
or with some sort of
like coaching situation
that can really help you
through a lot of experiences
where an external perspective
would be immense help.
It's just really hard to
get that other human being
to find time to sit down with you,
especially in regions with low resourcing.
- Related to that I've,
I've been very excited about
how teachers are transforming
their assessments with it.
I was talking to a teacher a few weeks ago
who at one point I think
during the pandemic had taken
time over, you know, Zoom
to basically do oral interviews
with all the students
and really get to assess
them on a more holistic way.
But of course that didn't scale very well
and so stopped doing it.
But then with these AI tools
coming out was able to now sort
of use the same rubric
and start to have, you know,
all the students doing on
a regular basis these sort
of assessments back and
forth with the chat bot
and then the professor, the
teacher is able to review them
and assess them based on
that process of going back
and forth with an AI.
- I think assessment is a
very interesting use of AI.
I could, you know,
envision in in the future
where it isn't a specific moment in time
where you get assessed
but there is a continuous
interaction with AI
developing a much deeper
understanding of do you
really understand the concept
behind this algebra concept or not.
One thing that I'm really
excited about AI could provide
this personalized learning.
There is a research done
on one-on-one tutoring
and what they found is that
on average the average student
that had one-on-one tutoring
is better than the 98th
percentile of students that
didn't have one-on-one tutoring
or just a classroom set up.
- And that was with human tutoring.
- That's with humans,
right? Hard to scale.
Exactly hard to scale.
Assume maybe like an hour of
one-on-one tutoring a day.
With AI you get continuous
one-on-one tutoring
and that is available
to everybody, you know, around the world.
So I think that is, has a great potential
to transform the world and how people
learn.
Yeah, I agree. I think there's
of course lots of challenges
that as people have
looked into the studies
and how do you replicate
this and all of it.
But I think it's a very
useful sort of north star of
what could be possible if you
can have a very personalized
but also personal type
of tutoring experience.
- Absolutely. I think today we
have classes maybe segregated
by students that are in the top
or you know, you take a
like an AP class if you are,
you know, in that certain group or not.
But with AI every student
could have their own journey.
Those that are able to advance
could advance very quickly
and those that need help can
get that personalized help.
- You know, this reminds me of
a really interesting use case
that I talked to a teacher
about where, you know, you kind
of always wanna meet students
where they're most interested, right?
Like that's like a very
Montessori type of approach
where it's like what
is your favorite topic
and then we'll kind of match
all the subjects to that.
That's really hard to scale, right?
But there's a teacher I
talked to that's just like,
I ask my students what
their favorite things are,
they tell me a little story
and then now every single
handout that you have, like
the same math concepts,
maybe even same problems,
but it's like each handout
is made for each student
and it's like exactly
according to their interests.
It's got a story that's engaging to them,
problems they actually care about.
And like she's noticed an uptick
in the engagement for sure
because suddenly these
students have a through line,
through every subject in the
classroom is building on itself
in a way that's super
personalized to their interests.
Which like if that was in
every classroom, imagine
how much students would just lean
into, it's amazing. Like exactly.
- Yeah. So how are you
thinking about that question
of what's worth, you know,
learning in, in the age of AI
- As somebody who's in product,
in product development,
what I see is this
absence of product layer
that would help both students
and teachers use AI very effectively.
For example, my daughter's
class, she's taking Python,
so both of my children are
studying computer science,
so very, very relevant for
their exams for writing Python.
They want them to write
on a piece of paper
because they're afraid about cheating.
Well the reason it is
so challenging now is
there aren't products
for the students could use to learn.
There's also not products
for the teachers to use
to assign and grade homeworks, all
of this are very light lifts,
like from what we can do as a,
as a product offering.
But in the absence of
an intentional product
that is built on top of LLMs
exposes a lot of uncertainty,
fear, and abuse of the
technology that we're building.
So that's, I guess that's my
take on this is that, you know,
with a little bit of support
in product thinking, so much
of the, the sort of
this uncertainty and and
and maybe like cheating and
so on could be mitigated.
- And one of the things I
struggle with is, you know,
we can sort of backtrack
from how jobs are changing
and start to think about how university
education should be changing.
But then when we think about,
you know, kids to the, the age
of your kids, you know in K 12
it's an even harder question
about what will be the
skills, the durable skills
that they need years from now.
So I don't have the answer,
but look, I always look, I
look to you Maggie.
- Oh man, it's, it's a challenging one.
I think that what resonates
a lot with the teachers
that I talk to is that a lot
of the skills you teach
young minds about how
to critically think about the
world around them in the world
of humans can be quite applied to AI.
Especially in the world
of just critical thinking about the facts
that you're presented with.
There's a stage of development
where you go from trusting
every single thing everyone says
to you to starting to think about well
what are the other things
that you need to know in order
to believe that this is true with my kids?
It's like a two part framework
where part one is just the importance
of education I think is
more important than ever
where you can't tell if
an AI is bad at math,
if you are bad at math
or you don't actually
know what the right answer is, right?
And we're not the stage where
AI is like always reliable
like a calculator or something.
And so just understanding that
and emphasizing that learning,
reading, writing, science,
math and so on is still very important.
And the latter part is developing
them into like critical
consumers of information where
it's not just about this is
what a fact that's given to me is,
but like why is that the case?
How do I trust that that's true?
What are the areas I need
to check in order to ensure
that I can kind of corroborate
what I'm learning here?
And that kind of critical
thinking skill you can develop
from a pretty young age regardless
of if it's an AI giving
you the information
or another human being
giving you the information.
That kind of critical
thinking I think is one
of the most important things
to get at a, like an early age
that skepticism, curiosity
and combination. Right?
- Yeah, I wanna add on to that
'cause I feel like a
lot of the like teachers
and parents that I talk to
feel this like really intense
pressure to have the answers
and to know what to teach their kids
and to know like how
to conduct the lessons in their classroom.
And I think like kids are
so much smarter than we
give them credit for.
And so there's something really
profound about just sitting
with whether it's your students
or your actual children
and just like learning with
them, asking AI something
and then evaluating what
comes out of that together
and like having kids reflect
and building their own frameworks
for interacting with AI.
That I think is really, really powerful.
And we all hear, we
don't have the answers,
therefore no one does.
Obviously we're working really
hard to figure out what they are.
But I think just encouraging
that reflection at any age
where wherever it's
developmentally appropriate
- Right,
- Is like one of the best things
people can be doing right now.
- You know, I, I recommend
sitting down with your kids
and going through AI together, right?
Like ask a question
and then say, well this is
was really confidently said,
but is that enough When someone
says something confidently,
is that enough for you to believe that?
And hopefully the answer is no. Right?
What else can you check?
Can you look somewhere else?
What information do you
need to think about this?
And genuinely internalize
if that's correct or not.
That exercise is, I think super
and I think of the, the
converse side is to kind
of demonstrate what it's
like to not know something.
I think that a lot of times
like showing uncertainty
and modeling for your kids
when you don't know something,
what is your own process
of finding that out, right?
What is your process for learning?
I think that like what,
what I wanna impart upon my
kids is like finding the answer
is just the start of
your learning journey.
And I think for many institutions, schools
and so on, getting to the answer is really
what we're testing right now.
But if we get make that the
beginning of someone's journey,
especially learning with AI, then
that I think opens up a
whole series of doorways.
And so yeah at home I, you
know, try to show my process
for discovering something
and that adults don't
always have the answers.
Kids are super smart
and they're able to find
answers on their own in ways
that if we just talk and
ask the right questions,
then they'll be able to discern
for themselves what is true
and what isn't and not just
trust things at face value.
- Yeah and I love the way you
framed that of like modeling
how to work through that problem.
Modeling un uncertainty is
just such an important thing.
Oh yeah. That we're all
uncertain so let's use
that to our advantage.
- And we don't do that
nearly enough I think.
Like we wanna project
this kind of confidence
and I think sometimes it can
be detrimental to development
of a child to kind of just tell 'em
to trust everything everyone says
or the adults around them always
know what they're talking about.
'cause I think that that gives
them, it's a crutch, right?
To not actually have to
think through like truth
for yourself and define your own truth.
- I think one thing that sort
of remains unchanged is that
how human things learn, right?
We, we learn basic things first.
We learn addition, subtraction
and kind of keeps building up.
So that will remain true
whether we have AI today,
generation AI or next generation AI.
So I think where I see I, I don't know
what is the right field to study is,
but either way we still have to go
through this process of learning.
And I think the great promise now is
that you could actually use AI
to advance your learning to,
you know, get gain greater
even understanding sort
of answer maybe in two different ways.
In one way sort of personal
is I studied physics
because I, I was very curious as a child,
so if you are a curious person, I want
to learn about the world.
My god, what a, you know,
what an opportunity now.
'cause AI could just teach you about
anything you want to know.
Yeah. But if you're thinking
about sort of career, like
what happens next?
You know, how do I make a
living then no matter what,
we'd have to be able to
use the AI technology
to make yourself like
you plus AI be a more
capable employee.
- I agree. Although I
do think some of the,
the fundamentals are changing in terms
of the order in which we learn things.
So one example I go back to as you know,
you talked about programming
and what computer science,
you know, when I learned how
to program, probably similar
with you, I spent 90%
of my CS education
learning how to write code
and write to algorithms
and then maybe 10% of my time learning how
to read other people's code and review it.
And then now of course at
Anthropic when I program
with all the coding agents and Claude code
and all of that, I spend,
you know, maybe 10%
of my time writing the code
but 90% of my time reading the code.
And so it has made me wonder,
you know, we usually learn how
to read before we write just as kids,
- Right?
- But then with coding
we often spend a lot more
of a time writing and then reading.
And so it is starting to make
me wonder like do we have
to revisit some of those
fundamentals and like maybe a core
part of an intro is CS
students education should be
to think about reading
and being able to discern
good code from bad
code and all of these things.
So I do want us to bring us back to
what is Anthropic doing here.
I think it's important,
and we all know of course
that we have a responsibility here.
We are building this technology
that's having this impact,
you know, on the education
system even though it,
we didn't intend it that way initially.
And so we have a
responsibility as a company,
as a public benefit corporation,
but particularly as individuals
working in this company,
former educators.
And so I think it'd be helpful
to sort of talk through
what are the things we're doing,
what are we wrestling with?
I don't know if you know Zoe
or Maggie, you want to talk about some
of the work we've been
doing with AI fluency?
- Yeah, yeah. Happy to start.
So I work on education content.
So that's one of the main ways
that I can make a
difference in this space.
So one of the things I'm
really excited about is our
AI fluency courses.
We partnered with two
professors, Joe Feller
and Rick Dakan, who built this
really great framework about
how to think about using AI.
And what's cool about this is
we're taking a step back from
the products that are available
today and the, the prompting
and kind of like all these
hacks that you see out in the
- World, there's a lot of them
- And
there is a lot of them, right?
It's like, it's pretty overwhelming.
- And they get outdated so fast.
- They get outdated so fast.
And so the idea here is we
wanna give people a tool
that they can use to
understand the interactions
that they're having with AI
and work towards interactions
that are efficient,
effective, ethical, and safe.
That's the AI fluency definition.
So we have this core course
that I think is pretty great
and then we've also created
spinoff courses for educators
and for students as well as
a longer course for educators
who are interested in teaching AI fluency.
And so the idea is that
anyone who goes through one
of these courses is
kind of better equipped
to assess their own AI interactions.
I talked about like learning
with your students earlier
and the power of reflecting
on your AI interactions.
And at its core that's really
what this course is about.
It's just reminding everyone,
teachers, students, parents,
that they have autonomy
in their AI interactions.
So that's one thing I'm excited about.
- Yeah, I think the interesting
thing about our AI fluency
work is the fact that
we're taking a step back
to the fundamentals I, when we
started this AI fluency work,
but way back when, I don't
know if you remember Drew,
the question that we were
trying to answer was, you know,
all of these prompt engineering tips
and so on, they are developed
by other humans, right?
And it's not as if like we
at Anthropic have greater
superpowers than everyone else.
Externally, we just have a different way
of thinking about approaching models
and it's like how do
you teach that mindset?
- Yeah. - To somebody. 'cause
to Zoe's point, it's like,
in all of us, that sounds so cheesy,
but like we have that capability
to be critical thinkers
that engage with this.
And I think sometimes the fear of needing
to get it right kind of
supersedes our ability
to just experiment.
And what I love about AI fluency
is we're opening the door
to experimentation and saying
you can try these things.
They may not work for you
and it's just as important
to learn when they don't work
for you and when you shouldn't
use AI as it is to, you know,
learn when you can use it.
I think there's something that
we say in the education team
every now and then, which
I think resonates a lot,
which is like we would much
rather teach a million people
to not use AI than like
watch a billion people
to become dependent on
the technology, right?
And in practice that can be quite hard.
But AI fluency I think
is a very solid start.
- I still remember when I
first heard you say that
and I was so happy and I knew I'd
come to the right company
because here I was at an AI lab
and Maggie was saying, yeah,
I don't think we should use AI
in this case or
let's teach people how not to use AI.
- It's like giving 'em the tools to make
the decision on their own right
- Back to critical thinking every time.
- But I think, so of course
part of it is an education
and a training and awareness part,
but we are also building products
and models that are used
out there in the wild.
And so I think the work that Ephraim
you and your team have been
doing on learning mode is a
really important part of it.
So we'd love for you to share more about
how did they even come about.
- So learning mode is a set of
features that positions Claude
as a tutor to students.
Students could come in and for example,
and upload their assignments
and rather than answer
the questions explicitly,
it would help the students
through the material
that is covered in their classroom.
It will guide them through
how to answer the question.
It will tutor them, it will
also help them prepare for exams
for example, by showing
them flashcards based on the
content that they've uploaded.
It's actually very much
a grassroots effort.
So a lot of people at the company
that are really passionate about education
and wanting to add education tools
within the main product line.
So with learning mode
what we did is added,
it's really is like small
features here and there,
but then tailor Claude app to be
really good at helping students
with learning. Along the line
we've also added a few more
features like, you know, expanding
how much content you could
add into projects so that more
and more content can
go in there, connecting
to classroom management systems so
that content could flow
in and out very easily.
So that's just the starting point
and of like, you know
what I think this could be in the future.
- And I think what's
interesting is some of
that early research that
led into to learning mode
as we were interviewing, you
know, university students
and we, we sort of knew
that the educators wanted
some form of learning mode.
They kept saying, right,
where's your learning mode?
And so everyone was like,
okay, now we have to build it.
But it was really the students
who I think really drove
the point home for us
because they of course
used a different word,
which is brain rot, but we
heard them talking about brain
rot and they, you know, realized
that in the short term it
could, they can use AI chat bots
to like help 'em, you know,
just finish an assignment, right?
But when it comes to
actually like studying
for their midterm and like understanding
and internalizing the
concepts, they wanted a version
of Claude where they didn't
have to prompt it, you know,
in all these different ways.
- Exactly. They, they didn't
want to just, you know,
give it an assignment,
it just pops the answer,
- And instead you give it an assignment,
it guides you through the answers.
If they're studying for a
final can just show a flashcard
that helps them memorize
and learn the content.
So that is what learning mode is, is
that just completely changing
the interface in Claude.
So it it focused on learning.
- And how long did this
first version take to build?
- So the initial version actually took
very short period of time.
This is a number of people
that was extremely passionate about,
you know, adding this capability.
It took us about two weeks from start
to finish and it was amazing,
- Incredible.
- Yeah. - The other aspect of
this of course is you know,
we can work on these training programs,
we can improve our products and our model,
but then of course it's how do we
partner with outside world?
We're just, we're a tech
company, we're a small part
of this much broader ecosystem.
And so, so you've been doing a lot
of the work we've done partnering
with institutions like the
teachers union, AFT would love
to hear more about what
goes into those partnerships
and why are we so focused on them.
- Yeah, I mean you and me both but,
but yeah, I think again,
something we're excited
about is just like we
have our classroom experience.
Mine is relatively outdated.
I was in the classroom before COVID,
like I know it's a very different-
- Out there pre-COVID, pre-AI-
Yeah, pre-COVID, pre-AI. It's like
basically doesn't even matter anymore.
But we get to partner
with these organizations
to learn from teachers who
are actually in the classroom
and professors who are in universities
to understand the real problems
that they're having in their schools
and the real benefits like
things that are going really well
and lean into both of those, whether it's
with education materials
to train teachers up
or you know, product solutions
that give them more
autonomy and tools. And so
And the, the heart of this, this is like,
this is a collective issue, right?
Like a humanity wide collective issue.
And we are far from knowing
every single thing that we need
to help resolve this.
I think like the through
line for all of our work is
to bring more people
into the conversation.
Like if enough people take
AI fluency courses, our hope is
that then they bring that
knowledge to their institutions
and start these conversations.
And to what Zoe was saying
before, students are really smart
and they're also really
engaged in the desire
to not have brain rot.
Like some of the best feedback
that we get comes from our student users
who I think sometimes we
don't give the credit for
that we think, well they're gonna
definitely wanna achieve with this.
They're gonna, but it's
an institutional problem,
not necessarily a human, I
guess motivation problem.
I think, I think that our, our
best feedback, like from all
of our product users indicates
that they don't want this
reliance on these models.
They want to feel like their
own human capabilities are
augmented and improved by
this collaboration with AI.
So I'm like very proud of us
in general in our products
for not optimizing for kind
of the standard engagement
metrics where we're not trying
to optimize for retention
or you know, how much time
you spend on the product
or dependency on the product.
And we make active product
decisions, you know, now
and into the future that
sometimes actually encourage
that greater augmented thinking
or encourage again times
when you don't use AI
or as the kids call
it, touch grass, right?
So I'm excited for us
to keep going down that pathway.
- Yeah, and I actually, that was one
of the most surprising things
to me joining Anthropic was
that it's, it's not a growth
optimized company like right?
Like most SaaS companies wanna
optimize for users retention,
all these things and has a
much broader perspective on
what success looks like in our products,
which I think is really interesting
- In our product development.
That's not just true for
the education initiatives
that we had, but for
everything else we build Yeah.
Isn't about keeping users
engaged in the product.
This really is about having
AI be beneficially deployed
and impact society.
- I think we touched on is
that like every decision
to use AI somewhere or not
as a deliberate choice?
I don't think that we are kind
of on a screen path towards AI
and like being every single place
and hopefully the work
that we do as a company
and the things we make,
the choices we make
to build our product in certain
ways can lead by example
and also invite people
in to start realizing
that everything is a deliberate choice
and it is just as good
and sometimes better to just
choose not to sometimes, right?
Like I would hate to see a
future where teachers outsource
to AI the parts that I think
which is the connection pieces
when you really understand
your students and can spend time with them
to kind of over time talk
with institutions and
discuss with them ways
where we can amplify
that knowledge they already have, right?
The experts we partner
with have generally a,
a decently clear opinion on
when AI is actively harming
the educational outcomes.
And it's just our job to listen
and to try to implement
that either in our products
or in our educational program.
- So we've talked a lot
about, you know, what,
what our personal views
are on AI education,
what we're doing as a, as a company,
but we definitely
haven't solved it, so, so
what are the things we're
still uncertain about?
I mean I'd be curious for all your
takes on this, you know,
still trying to figure out.
- I have a couple things go
ahead. Both pretty different,
but one thing we touched on
earlier is AI is changing, like
what it is that you need to teach.
You brought up coding, we are pretty sure
that coding curriculums will look very
different in five years.
I'm interested to see
how things start to shift
and if there's any like frameworks
or really anything that we can develop
to help academics along in
these areas to understand
what kinds of skills may be
more augmented in the future
and which kinds of skills are
gonna need additional human
support like reviews or management.
I think we're starting to understand
that in areas like computer science,
but it's very, very early
and we know that this is gonna
affect a lot more fields.
Yeah. So especially in higher education,
that's something I'm interested in.
I hear a lot of concerns in K
12 about the different tools
and trying to understand
what hap what happens
to the data when you
put it in those tools.
And I think right now
there's this like massive
proliferation of AI tools
in classrooms and teachers
and administrators are really overwhelmed
for very good reasons.
Like there's a lot of concepts
that are really new to everyone.
There are elements of the
data privacy that is new
and hard to understand.
And so I'm really interested to see how
that landscape evolves.
Whether we need to really
ramp up our education
around data privacy so
people can better assess the
landscape or whether we
start to like, you know,
see clear winners in this space.
I'll just be really interested
to see what happens there.
- I think in addition to that,
I mean the technology is
really changing rapidly.
So one of the concerns
I'm not sure how it sort
of will play out over time is
how will institutions adapt?
They're generally slow moving
and intentionally built that way.
And the technology pace of
change has been very rapid.
It's harder to predict like
what would happen six months
from now or a year from now.
So I think that pace of change to
how institutions generally
adapt a new technology is one
area that I'm uncertain about. I
- Also think that like just everywhere,
every institution feels an
immense amount of pressure
to just do something with
AI instead of doing nothing.
And I, you know, I have no
idea how to kind of balance
or help organizations balance the fact
that pressure is really real,
but also when it comes to
education, especially moving fast
and breaking things is
not an option, right?
And that's just so challenging
for both the individual teacher
but also the entire institution at large.
- I kind of call this
unbundling of education.
One is just the knowledge itself,
which this AI is really good at
providing personalized education,
but institutions provide
more than just knowledge
imparting knowledge into students.
The other is really like I have
two children in, in college,
it's not just learning
they're getting theirs,
but also that's where
they're growing, that's
where they're maturing learning
responsibility and and so forth.
So what AI solves, you know,
very like really well is knowledge,
impart knowledge and learning.
I think what we would have to do
as society moving forward is
how do we leverage AI in
the knowledge transfer part
but also retain these
institutions for all
of the great roles
that they play in society,
- Right.
To separate out some of the pieces such,
exactly like the success metric
of a good educator is not
to do every single part of this thing,
but I think what you're
saying is like yes, correct.
Do more of one thing
and then let AI handle things
that are like maybe knowledge
like acquisition oriented
but not like, I don't know
a relationship with the student, right?
- Correct. Correct. I
mean one of the feedback
for example we've received
when we were visiting
universities is
that while AI assignments
are very compelling,
that's something they would like to do.
But AI assignment means students with AI
therefore large assignment sets
that might take say six months,
but they could end up taking like two
weeks. How do you grade them?
- Right. So there is a lot
of AI involvement means
there's a lot of learning
that could happen much, much
quickly as you leverage AI
to do the learning aspect of it.
What about everything else
that is those teachers institutions are
providing the students.
I think that is where that's unbundling
and you know, just leveraging
all the right pieces from
both the technology but
what institutions do.
- Yeah. And I mean I think
the best case scenario
of this is reducing burnout at scale,
which is like the number one issue
facing most of the teachers.
- If you unbundle you can
maybe do less?
- Where every educator is really,
really talented at some things
and those things bring them a lot of
energy and they're exceptional at it.
And what if AI could, you know,
support them in the things
that don't bring them energy.
And I think that just creates
a much more well-rounded
system for their personal lives
and then also for the students
that they're supporting.
- This conversation is also
reminding me of like a, a part
of the AI Fluency curriculum
we have for educators
that I found super compelling,
which is to have AI be
so integrated, like into the assignments,
the experience and so on.
And to instead start grading AI use
and not grade the outcomes as much.
Right, right. Going back to
like how do you think about
these long-term projects
or how things differ in this
AI world, having that kind
of engagement is, is very different
and AI forward in a way that I'm excited
for more institutions to adopt.
- I think you're right on
like, you know, in our sort
of conversation one of the
things have come up is when you
create, you're not necessarily
just creating the final
result, but you've created,
how did students arrive to that result?
How did they use the technology?
What is the back and forth
that also becomes part
of the what learning is.
- One of our, one of our chief
marketing folks here one
time sat down with me
and just said, you know,
I think the true power
of AI is the process.
- Yes. - And I think that
that's really the core of
what we're getting at, right? Yeah.
- Right. - I'm also curious
from like a model training
perspective, what we
can do to reconcile how,
like I think I was having a,
I had a really great
conversation with someone
who studied the philosophy
of epistemics, right?
Like how do you know something is true?
And they made a great point about
how AI more easily than any
other kind of intelligence
that humans have encountered
can be really confident, right?
Or can can say things
that sound so realistic.
And it usually, in a human
being, it takes a lot of charisma
and practice to get to be
someone who can say that
and not say true things.
But with AI, you're kind of
encountering all the time
and our human ability
to discern what is true
and what isn't is based on how
we discern in other humans,
which may not be successful
when you're applying to AI.
Right? And that's a whole
different thing to unravel
and figure out how you can,
do you match the AI
personality more to that area?
Or do you start teaching
people of a new way
of discerning truth?
And I mean my hot take is I think
that like the latter one
is a little more powerful
because it's also a good
inoculation against all forms
of like persuasive writing,
persuasive thinking regardless
of whether or not it's
an AI or a human being.
But that critical thinking,
going back to the fact
that AI is just forcing
us to reconcile things
that already exist, I think that teaching
that critical thinking
is really hard. Right.
- Yeah. And this goes back to
like child psychology, right?
Like we have this whole
generation of digital natives now
who can very clearly
identify a spam text when
that's like really
difficult for some folks.
And like what is the AI native generation?
What does that look like?
And what impacts does it have
on on kids development?
Like there's just things
we don't know yet.
- Well, to close this out,
because I think we could
go on forever, I would love
to hear from all of you as we
think about five years out,
what's a success look like
for teaching and learning?
- Five years is a crazy kind of time
to predict the AI world.
I guess I'll give you my hope, right?
I don't know if I know
what success looks like,
but I do know what I hope for, which is
that in educational institutions
we have like teachers have
so much more time
to engage individually
in the relationships
and the fostering portion of it.
You know, going back to Ephraim's point,
like maybe it's not the knowledge
acquisition part of things
that teachers participate in
as much versus like synthesizing
that knowledge into the
greater ecosystem of your life
and the world and understanding how
any given individual can
best be helped to learn.
'cause we're still all unique
individuals in this future
and celebrating
and emphasizing that
uniqueness is something
that I hope we can get to with education,
I think five years is a very long time,
but I think success to me
by then will look like every
person on the planet has a
personalized tutor ready
for them at any time.
And then also if we've made
that transition successfully,
our institutions will have survived
and are playing the
vital role they already
play in our society.
- Yeah. For me, I think it's going back to
that critical thinking piece.
I want every person really,
every student, every teacher
to have a shared vocabulary
and cultural understanding
around what it means
to use AI and learning.
I think just a lot more
discernment and reflection on
and just being intentional about using AI.
- I know I feel like I go back
to this like a broken record,
but wouldn't it be great if
like every single student could
articulate when they want to use AI
when they don't want to and why?
Like that kind of knowledge
about your own habits
and how you think and how you learn best.
That personalization of
knowledge is so exciting.
And I'm like, that's a
shorthand heuristic, I guess for
what success could look like.
- Or maybe on the other hand,
like they don't have to make
that decision because technology,
- The technology, yeah. The product
- Is the product itself as well
adopted, meaning both of those-
- Together, definitely the
product and the experience
and the education all have to
go hand in hand. Exactly.
- I think the thing I
keep going back to, which
to me brings optimism.
'cause some days in this work
there's a lot of pessimism of
jobs are changing
and we have no idea what
my, you know, our jobs are
- And a lot of personal responsibility
that we feel over any, you
know, things that happen.
- But at the same time, I do
see in a world where, you know,
intelligence is becoming abundant
and in some ways commoditized,
I think that will, you know,
no longer be our defining
trait as as humans.
And that can be scary at some point.
But I also think that's liberating
because for the last few
hundred years I almost feel like
we've lost some of our
humanity as we, you know,
you have the industrial revolution
and we're able to do all these things,
but we're also like going
into offices and doing tasks
and defining our ourselves
by the work that we do.
And that may not be the thing
that we can do best, you know,
five years from now.
But there are so many
things that a teacher does
that a doctor does that are truly human,
that are not intelligence, you know?
And so I, I almost am
excited for the things
to sort of strip away.
And so for us, and I think our
education systems at the core
of it, to really focus
on what makes this human.
- There's an Oxford
professor that said this,
this great quote I think
about all the time,
which is he says, I think
the age of AI will be the age
of asking good questions.
And like that's something that
doesn't necessarily come from
knowing a lot, right?
It's just about being curious
and then also being a little discerning
and skeptical about
things you get in return,
which then yield better questions.
And I think with AI in our
pockets, the personal tutors,
like the world of the question
space has opened up immensely
and way beyond anything else we've ever
had in human history.
And we just kind of have
to steward people towards
the mindset that allows them
to ask good questions.
- There's never been a better
time to have a problem.
- There's never been a better time to have
a problem.
- I think that's a perfect way to end.
Well thank you all. Thanks
for taking the time.

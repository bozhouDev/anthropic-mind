---
title: Cheeky Pint with Dario Amodei
source: "https://cheekypint.substack.com/p/a-cheeky-pint-with-anthropic-ceo"
published_at: 2025-08-06
captured_at: 2026-08-16
author: Dario Amodei
source_type: podcast
authority_score: P2
mind: leadership
status: captured
evidence_url: "https://cheekypint.substack.com/p/a-cheeky-pint-with-anthropic-ceo"
catalog_id: b6b37dad3a38
---

A Cheeky Pint with Anthropic CEO Dario Amodei
Cheeky Pint
Aug 06, 2025
15
4
3
Share
Dario Amodei joins John Collison to talk about Anthropic's growth to almost $5 billion in ARR, how AI models show capitalistic impulses, predictions for an agentic future, the economics of model businesses, and the 19th-century concept of vitalism.
Timestamps
00:00 Intro
00:50 Working with your sibling
01:43 Building Anthropic with 7 cofounders
02:52 ~$5 billion in ARR and vertical applications of products
07:18 Developing a platform-first company
10:08 Working with the DoD
11:11 Proving skeptics wrong about revenue projections
13:13 Capitalistic impulses of AI models
15:43 AI market structure and players
16:56 AI models as standalone P&Ls
20:48 The data wall and styles of learning
22:20 AI talent wars
26:04 Pitching Anthropic’s API business to investors
27:49 Cloud providers vs. AI labs
29:05 AI customization and Claude for enterprise
33:01 Dwarkesh’s take on limitations
36:12 19th-century notion of vitalism
37:27 AI in medicine, customer service, and taxes
40:59 How to solve for hallucinations
42:41 The double-standard for AI mistakes
44:14 Evolving from researcher to CEO
46:59 Designing AGI-pilled products
47:57 AI-native UIs
50:09 Model progress and building products
52:22 Open-source models
54:43 Keeping Anthropic AGI-pilled
57:11 AI advancements vs. safety regulations
01:02:04 How Dario uses AI
Transcript
John Collison:
So, I'm excited to talk a bit about the Anthropic business. You studied physics and computational neuroscience.
Dario Amodei:
Yes.
John Collison:
You then worked at Baidu, then Google Brain, then OpenAI-
Dario Amodei:
Yes.
John Collison:
... and then started Anthropic.
Dario Amodei:
Yes.
John Collison:
And we'll get into the Anthropic business, but I'm excited to finally learn, what is it like to start a company with your sibling?
Dario Amodei:
I could ask the same question of you, but it's almost like there's two things you need to do when you're running a company. You need to operationally execute, and you need to have a good strategy and see the most important thing or the thing that no one else sees. And so my job is the second and Daniela's job is the first. And we're both good at the things that we do, and so I think it's allowed us each to spend most of our time on the thing that we're best at.
John Collison:
Presumably something about the trust side of things as well where cofounder teams in general in tech, I guess in AI as well, they’re unstable pairings, and just having someone where you have a long-running and deep trust relationship—
Dario Amodei:
Yeah, yeah, where you have just total and complete trust. I mean, I think even beyond that. Anthropic has seven cofounders. When we founded it, basically the advice from pretty much everyone was like, "Seven cofounders is a disaster, the company will fall apart before you know it, everyone will be fighting with each other." There was even more negativity on my decision to give everyone the same amount of equity.
But what we found, and I think it was because obviously me and Daniela are siblings, but then all seven of us, some of us knew each other for a long time or had history of not just knowing each other, but working together in the past, and I think that really allowed us to always be on the same page. And I think especially as the company grows, the idea that you have seven people who really carry the values of the company and project them to a wide set of people, it allows you to scale the company to a much larger size while holding on to the values and the unity that we have.
John Collison:
So, I want to ask about the Anthropic business because, again, it's an incredible story where it was reported recently that you'd blown through $4 billion in ARR. And so it's a lot of discussion, correctly, about the technology that you're developing, but also, this is just one of the fastest-growing businesses in history. And so I want to talk a bit about the AI market, and maybe the place to start is, what is everyone doing with AI? There's coding, there's customer service work, but where does all this revenue come from?
Dario Amodei:
Yeah, there's a wide range of things and it's kind of changed over time. I would say definitely the application that has grown the fastest, although it's very far from the only application, we have a wide range of them, is definitely coding. And my theory on why it's grown so fast, other than that we focused on coding and the models are good at coding, it's actually really a statement about societal diffusion, which is that if we look at today's AI models, I think in every area, there's a huge overhang in terms of what they could do compared to how they're actually being deployed today because there's some friction. People at large enterprises are not familiar with the technology.
I look at what a bank does or what an insurance company does, and there's huge potential, even if the models stopped getting better, right? Even if we stopped building products on top of the model, there's still huge billion-dollar potential in individual enterprise. And often, the CEOs of companies that I talk to understand that perfectly well. But if the company is a 10,000 or 100,000-person company, companies that size, they're set up to operationally do a certain thing a certain way, and it takes time to change them.
But in code, the people who write code are very socially and technically adjacent to the folks who develop AI models, and so the diffusion is very fast. They're also the kind of people who are early adopters, who are used to new technology. And so I think the big growth in code, I would say the biggest cause of that is just that the people doing it and the startups devoted to it are fast adopters who understand the technology super well.
But it's by no means limited to code at all. There are a bunch of companies that do things like tool use. There are, as you mentioned, customer service; we work closely with companies like Intercom. But we're starting to see some things on the biology side. So, we're working both with pharmaceutical and healthcare companies, and we're working on the side of basic scientific research. So, we work with companies like Benchling, for example, but we also work with some of the very large pharma companies. There was something done a while back where we worked with Novo Nordisk to write clinical study reports. So, clinical study reports are like you've done a clinical trial, and then you write up the results. And it's like, "These are the adverse events, these are the statistics." And the clinical study report normally takes like nine weeks. Well, Claude could do it in five minutes, and then it took a human few days to check it. And so you can really see the opportunity for acceleration, and as the models get better, they'll reach into the deep research as well.
So, I guess a way to summarize it would be to say that code is out in the lead, but we see a long tail of quite a lot of other stuff, including some very, very significant use cases. I think code is maybe an early indicator, like a premonition of what's going to happen everywhere else. It's the same exponential, it's just faster. It's just happening faster.
John Collison:
Yes. Right. So, there are many places where there's significant AI uplift, but engineers are used to adopting. You think about Hacker News and people arguing over who has the best tools, so people are passionate about adopting new tools.
Dario Amodei:
And two hours after we released Claude Code, there's some person out there who's tried 10,000 different things with it and plugged it into all the frameworks, and Twitter forms one opinion after two hours and then revises an opinion in two hours. And you think of the speed of that as compared to the speed that a pharmaceutical company can use it in research, or that traditional retail company. And we want to bring everything. Some of the biggest benefits in the world are touching the physical economy, and we want to get there, but it just intrinsically does not happen at the same speed.
John Collison:
How do you decide which verticals to do yourself versus which to allow platform... You have Claude Code, and obviously there's also platform companies like Windsurf and Cursor and everyone like that. You launch Claude for Financial Services. Presumably, there are other verticals where you say, "Well, we're not building a tool there."
Dario Amodei:
Yeah, we have things like Claude for Enterprise, which is not a vertical, but like a general play to go with enterprise. I think the way we like to think about it, I think we think of ourselves as a platform company first. So the analogy here would be maybe clouds or something, if you think of a really large platform business of the size we're trying to get to in hopefully a small number of years, there are a number of reasons why you would also want to have things that are first-party, because some verticals end up being more first-party heavy. One is when you want to have direct exposure to the users. The end user gives you some sense of how exactly are they using it, what are they most looking for? If you're a pure platform and you don't have that direct connection, you can be disadvantaged in various ways.
John Collison:
It's hard to build the best products.
Dario Amodei:
Yeah, it's hard to build the best products. It may even be hard to know where the model really needs to go, right?
John Collison:
Yes.
Dario Amodei:
People say things like coding, but there are many models that seem to be good at coding, but they aren't good in the way that's actually relevant, right? We've actually managed to make Claude good in a way that's relevant to what people actually use. So, I think that's one reason.
Another reason goes back to the large enterprises, where building on an API, sometimes it's more challenging for a more traditional company to do that. And you need to give them something that's a little bit easier to use, either a kit to help them build things or you need to give them an app. So, enterprises have also liked Claude Code, and we're gradually developing Claude for Enterprise into what we call a virtual co-worker.
John Collison:
But I find it hard to picture Anthropic developing Claude for oil and gas exploration. Why is that?
Dario Amodei:
Why is it that you find it hard to imagine, or what have I said that—
John Collison:
Yeah. Well, I mean, maybe in fact it's the next launch, but—
Dario Amodei:
Yeah, we're not currently working on Claude for oil and gas exploration. I would draw a distinction between things we just don't allow, things that are illegal or things like that. And there are a number of use cases that it's like, "Okay, we're a platform. People are going to do a bunch of things, but—"
John Collison:
"But we're just not passionate about it."
Dario Amodei:
"... we're not passionate about it. We're not going to go out and make this happen before the other use cases."
John Collison:
Yes, yes.
Dario Amodei:
So, I think there is a component of that where probably we work on things like science and biomedical out of proportion to its immediate profitability.
John Collison:
Because you guys think it's worthwhile?
Dario Amodei:
Because we think it's worthwhile. We feel the same way about things in the developing world. One I'll give you that's controversial, people think about it the opposite way. So, the work we do on defense and intelligence, people are often like, "Oh, these guys are selling out." I think about it the opposite way, right?
John Collison:
Mm-hmm.
Dario Amodei:
So, there was this contract with a ceiling of $200 million with the DOD and intelligence community. People are like, "Oh man, Anthropic's selling out." It's exactly the opposite. Getting another $200 million from some coding startup would take an order of magnitude less effort than getting that contract.
John Collison:
But you think defense is very worthwhile?
Dario Amodei:
And we're doing it because we want to defend democracies, and we do it within bounds. There are some things we're concerned about. I'm deeply concerned about abuse of government authority on the domestic side. We think more on the outward directed side, but that's an example of the things we prioritize are things that we think are good, not necessarily things that feel good or that we think external buzz will be positive. We actually have conviction around some things, and we do them regardless.
John Collison:
You reference the kind of business you want to build. What are your aspirations for the Anthropic business in, say, three to five years time?
Dario Amodei:
AI is strange in a number of ways. I think one of the ways it's strange is that because it's an exponential, we have a hard time calibrating exactly how big the business will be. So, we had the following experience. So, in 2023, I'd never raised money from institutional investors before, and so our revenue was zero at the beginning of 2023 because we had not released a product. So, I was putting together something and I'm like, "Oh, I think we can probably get $100 million of revenue in the first year." And this caused some investors to say, "This is crazy. This has never happened in the history of capitalism. You've lost all credibility with me."
John Collison:
"You're just making up numbers." Yeah.
Dario Amodei:
"Goodbye. Goodbye." And then we actually did it. And then the next year, I was like, "Oh, well, I think we can go from $100 million to a billion." And actually, having done it the first time, it was a little bit less dismissed as crazy but still often dismissed as crazy. And then, we did it again. And this year, we're halfway through the year; we're, as you mentioned, well past $4 billion in revenue in logarithmic space, to add another order of magnitude.
So, there's a bunch of different futures. There's one where once things get to a certain size, the curve slows down, but there's a provocative world where the exponential continues, and in two or three years, these are the biggest businesses in the world. And I think one of the fundamental experiences and uncertainties of working at or running something like Anthropic is you kind of don't know. You make this exponential projection. It sounds crazy, it might be crazy, but also, it might not be crazy because that trend line has followed before. And I've said much the same thing in the context of training AI models, in the context of the cognitive capabilities of AI models on the technological side, but now we're seeing the same continuous lines on the business side.
John Collison:
So, what's the analogy to scaling laws here? Where you scale up the relevant inputs for model quality in parallel, and you guys get much better model performance, is there something where you put better models in, and I don't know the right organization... I know what the inputs are.
Dario Amodei:
Yeah, yeah, yeah. There's something, there's some curve where you spend 5x or 10x more to train a model, or you have 5x or 10x more data or whatever the scaling laws say, and there's some transfer curve for revenue, where I spend 10 times more on the model and the model goes from being a smart undergrad to a smart PhD student. And then I go to a pharmaceutical company and I'm like, "Well, how much more is that worth?" Often, they end up saying that's worth about—
John Collison:
More than 10x, yeah.
Dario Amodei:
... that's worth about 10x, where these power law distributions occur in a bunch of contexts. Going on the technical side, when you train the model, there's a longer and longer tail of correlations that you're capturing as you train the model, correlations in the structure of language, in the world, in patterns, and that correlation is what's thought to lead to the scaling laws because there's this kind of logarithmic distribution.
And then, as you think of the model getting more and more capable in terms of cognitive tasks, there must be, or we're seeing empirically so far, if you think of the uses of the model in the economy, right?
John Collison:
Yes.
Dario Amodei:
If I think of the way that companies are organized, there's a power law structure of the—
John Collison:
The org chart.
Dario Amodei:
... the org charts of companies, and it almost feels like you're climbing that power law distribution of value. And then, I guess the way I think about product and go-to-market is that the model wants to be on that exponential of revenue. And product and go-to-market, they're kind of a way to clean the window and let the light shine through, right?
John Collison:
Right.
Dario Amodei:
A way to open the aperture and let the exponential happen.
John Collison:
It's like the models want to learn. The models want to be extraordinarily successful in the market.
Dario Amodei:
Yes, right. In addition to having this learning impulse, the models have this capitalistic impulse that they want to embody unless they're given a bad product or bad sales to go with them.
John Collison:
Because they're really useful, that intelligence is really useful to people, and so it kind of gets pulled out of you.
Dario Amodei:
Yes, yes, yes. That is a way to think about it.
John Collison:
What is the terminal market structure here? Is there a few large-scaled players, or do we keep seeing new upstarts for specific use cases?
Dario Amodei:
It's very hard, it's hard to tell for sure, and I think there was quite a lot of uncertainty two or three years ago. But I think we might be relatively close to the final set of players, if not necessarily the final market structure or the roles of the players. I would say there's probably somewhere between three and six players, depending on how you count, and those are the players that are capable of building frontier models and have enough capital to plausibly bootstrap themselves.
John Collison:
I would love to understand how the model business works, where you invest a bunch of money up front in training, and then you have this fast-ish depreciating assets, though maybe with a long tail of usefulness, and hopefully you pay that back. Thus far, I think the image people have from the outside world is ever larger amounts of CapEx, and how does all that—
Dario Amodei:
Get kind of burned. There's two different ways you could describe what's happening in the model business right now. So, let's say in 2023, you train a model that costs $100 million, and then you deploy it in 2024, and it makes $200 million of revenue. Meanwhile, because of the scaling laws, in 2024, you also train a model that costs $1 billion. And then in 2025, you get $2 billion of revenue from that $1 billion, and you've spent $10 billion to train the model.
So, if you look in a conventional way at the profit and loss of the company, you've lost $100 million the first year, you've lost $800 million the second year, and you've lost $8 billion in the third year, so it looks like it's getting worse and worse. If you consider each model to be a company, the model that was trained in 2023 was profitable. You paid $100 million, and then it made $200 million of revenue. There's some cost to inference with the model, but let's just assume, in this cartoonish cartoon example, that even if you add those two up, you're kind of in a good state. So, if every model was a company, the model, in this example, is actually profitable.
What's going on is that at the same time as you're reaping the benefits from one company, you're founding another company that's much more expensive and requires much more upfront R&D investment. And so the way that it's going to shake out is this will keep going up until the numbers go very large and the models can't get larger, and then it'll be a large, very profitable business, or, at some point, the models will stop getting better, right? The march to AGI will be halted for some reason, and then perhaps it'll be some overhang. So, there'll be a one-time, "Oh man, we spent a lot of money and we didn't get anything for it." And then the business returns to whatever scale it was at.
Maybe another way to describe it is the usual pattern of venture-backed investment, which is that things cost a lot and then you start making it, is kind of happening over and over again in this field within the same companies. And so we're on the exponential now. At some point, we'll reach equilibrium. The only relevant questions are, at how large a scale do we reach equilibrium, and is there ever an overshoot?
John Collison:
Right, right. And yeah, you referenced the cloud companies as a point of comparison, but I don't know, there's something about the cloud companies where it feels like their data center CapEx is more continuous. They're just always adding new data centers. Whereas there's something about how discrete these generations are that maybe it's like the way the engine manufacturers, they keep coming up with new technologies, like adding more manufacturing or whatever.
Dario Amodei:
Yeah, yeah. It's like the F-16 or something, or it might be a little bit like drug development, like—
John Collison:
Exactly.
Dario Amodei:
... kind of an R&D heavy thing.
John Collison:
Yes, and when do you actually go to the effort of train a model—
Dario Amodei:
Yeah, yeah. It's almost like a drug company where it's like you develop one drug, and then if that works, you develop 10 drugs, then if that works, you develop 100 drugs.
John Collison:
Yes.
Dario Amodei:
The drug development market does not work like that numerically, but it is as if it did.
John Collison:
Right, so we can look at each of these models as individual programs and look at their individual P&Ls.
Dario Amodei:
Yes.
John Collison:
And you're saying that the payback math on those, at least in the models we've seen to date in the industry, is not actually that challenging. When you're acquiring a customer, if you have a nine-month payback on acquiring a customer, you'll do that all day long. That's a very easy payback to underwrite.
Dario Amodei:
Yeah. Yeah, yeah, yeah, yeah, yeah.
John Collison:
And you're saying the paybacks are nine months, twelve months, so they're very easy to enterprise.
Dario Amodei:
I don't want to make any specific claims—
John Collison:
Sure. Yeah, yeah.
Dario Amodei:
... but qualitatively, if you look at the business this way, model by model, it looks very viable.
John Collison:
Yes, because the ever-growing CapEx is masking the underlying quality of the model businesses.
Dario Amodei:
Yes, yes. Yes.
John Collison:
In 2023, everyone was talking about the data wall. Is this how we solved our way out of the data wall?
Dario Amodei:
Yeah. So, I don't know, people talk about things in public, and sometimes they're rumors or suppositions or whatever. I wouldn't even necessarily assume that there's a data wall. One thing I will say is that the idea of using RL has been around for a while, right? If we go all the way back to when Google DeepMind beat the world Go champion with AlphaGo, it was RL first. And then we built these language models, and now we're kind of uniting the two together by putting RL on top of the language models. That's all chain of thought or reasoning is, it's just a fancy way of saying RL, where the RL environment is that the model writes a bunch of things, and then gives an answer. There's nothing more to it than that. It just has a fancy name.
And so I think of these as the two key ways of learning, right? I think of base LLM training as learning by imitating and RL as learning by trial and error. I think those are the two styles of learning, right? If I'm like a child, there's two ways for me to learn. I look at my parents, and I'm like, "Oh, they do something, and I try and learn what they do." Or I can just experiment with the world and learn things. And it's very clear in developmental psychology that people use both, and so we're now seeing that recapitulated in the language models. And so we have a stage where we do the imitative learning, then we have a stage where we learn by trial and error. So, it seems very natural to me.
John Collison:
The other thing that's obviously notable to, I think, people not in the AI industry looking at it, is all of the talent wars, and the fact that your IP walks out the door each evening. And you referenced, in a recent interview you gave, $100 million secrets that were a few lines of code. And obviously, I think you were talking about that in a national security context, but you also think about it in a talent context.
Dario Amodei:
Of course.
John Collison:
And so, in the pharma industry, they protect their secrets with patents; in Wall Street, where also they have $100 million secrets that are just a very simple idea, so Renaissance Technologies, the hedge fund, just very successfully locks up its employees. How do you make keeping a commercial lead work in the current AI environment?
Dario Amodei:
Yeah, so one thing I will say is that there are some things that are like that, but I think more and more as the field matures, it starts to be more about know-how and ability to build complex objects.
John Collison:
Yes.
Dario Amodei:
Right? So, some of the ideas we work with are simple, but I would say the simple ideas, the ones that are like, "Oh yeah, twiddle this element of the transformer or something," those tend to be independently discovered or anyone knows them before too long. But there are things like, "Oh man, this thing is actually really hard to implement from an engineering sense and we have it implemented." Or, "This thing is just kind of a pain to do." Or, "There's a know-how to doing it." And those tend to be more collective things that are more difficult to leak. And so I think those things are substantially more defensible.
That said, there's still leakage, and we still don't want it to happen, again, both for commercial competitive reasons and for national security reasons. Both are problems. And so a few things we do, one is, we tend to compartmentalize information. So, if you talk to any intelligence agency, that's how they operate; you're only told what you need to know. And I think everyone within Anthropic—
John Collison:
But that's probably quite different to a normal Silicon Valley culture, where everything's just flying around the company.
Dario Amodei:
Yes, yes.
John Collison:
Yeah.
Dario Amodei:
We actually do that at the same time as we have a very open culture. I say things to the company that maybe another person would put it in kind of PR speak. You know what I mean?
John Collison:
Yeah, yeah.
Dario Amodei:
But when there is a secret, then I think that actually leads to people trusting that it's something that you actually need to know.
And then finally, having better retention rates and losing less people is one of the most important things here. So, we have the highest retention rate of all the AI companies. I think the differences are even starker because everyone has a non-regretted attrition rate that's maybe constant. So, if you subtract that off, then the difference is even larger. Sometimes when people leave, they come back.
John Collison:
Yeah, I saw that recently.
Dario Amodei:
You can see publicly the list of people who went to the Meta Superintelligence Lab, even if you normalize for our size, and many turned them down.
John Collison:
So, in the crazy $100 million comp wars that everyone's been talking about, you guys have not had too hard a time of that?
Dario Amodei:
I think relative to other companies, we've done well. We may even have been relatively advantaged. It's like a mixture of true belief in the mission and belief in the upside of the equity. I think Anthropic has developed a reputation for doing what it says it will do, in some cases making less promises, but keeping those promises that we make. And being very clear on what we stand for, and being consistent over the years and standing for it, that creates a unity around the company, and I think it's a good guard against cynicism.
John Collison:
And when you're talking about the upside of the equity, when you're pitching investors or maybe candidates, how do you pitch the Anthropic business? "We're building a very large business." That's a good start.
Dario Amodei:
Yeah, yeah.
John Collison:
So, what else goes into it?
Dario Amodei:
So often I'll talk about the platform and the importance of the models. For some reason, sometimes people think of the API business and they say, "Oh, it's not very sticky." Or, "It's going to be commoditized."
John Collison:
I run an API business. I love API businesses.
Dario Amodei:
No, no, exactly, exactly. And there are even bigger ones than both of ours. I would point to the clouds again. Those are $100 billion API businesses, and when the cost of capital is high and there are only a few players... And relative to cloud, the thing we make is much more differentiated, right? These models have different personalities, they're like talking to different people. A joke I often make is, if I'm sitting in a room with ten people, does that mean I've been commoditized?
John Collison:
Yes, yes, yes.
Dario Amodei:
There's like nine other people in the room who have a similar brain to me, they're about the same height, so who needs me? But we all know that human labor doesn't work that way. And so I feel the same way about this.
So, I think the API business is a great business, but we want to go broader than that, you know? The way I think about it is other players such as OpenAI and existing incumbents such as Google are very focused on the consumer side. The idea of providing AI to businesses is something that we are trying to get better and better at, and I think we're out to an early lead in that. I'm not sure because, I don't know for sure what the revenues of the other players are, but I think we probably, at this point, have the plurality of the API market, most likely, and AI for business market, perhaps.
John Collison:
Yeah, no, it's funny when you talk about the commodity argument, where we obviously grew up facing this as a skeptical argument, and I remember finding it so striking when AWS finally had to break out their numbers in 2015. Remember they used to be wrapped up in Amazon's numbers when they broke them up?
Dario Amodei:
Yes, yes, yes.
John Collison:
And people had been talking about, pundits had been saying, "Oh, cloud is a commodity, it's uninteresting," and then they broke it out and it was one of the greatest businesses of all time. And there's something where a business can have competitors and it can have buyers who care about price, but that's very different from being commodity.
Dario Amodei:
Yeah, yeah, yeah, yeah, exactly.
John Collison:
And as you say, all these products work differently.
Dario Amodei:
No, no, no. No, no, no, exactly. I mean, we're like one of the biggest customers of the clouds, and we use more than one of them. And I can tell you, the clouds are much less differentiated than the AI models, right?
John Collison:
Oh, for sure, because it feels like, one, the behavior is non-deterministic, thus, by design, trying to make it hard, but that just naturally means that, "Oh, we get the customer service answers we prefer with this model versus that model, and I don't know why."
Dario Amodei:
No, no, no, no, no, exactly. You don't know why. It's a little like baking a cake, right?
John Collison:
Yes.
Dario Amodei:
It's like, you put in the ingredients.
John Collison:
It just works.
Dario Amodei:
It kind of comes out a certain way.
John Collison:
Yeah.
Dario Amodei:
And one chef makes it this way and the other chef makes it this way, and if you're like, "Make it exactly like that chef makes it," you can't, right?
John Collison:
Yeah.
Dario Amodei:
You just can't.
John Collison:
And presumably, it's striking to me, none of the AI products are that personalized right now, but it feels like personalization will be a huge deal—
Dario Amodei:
Will be a huge deal, yeah.
John Collison:
... and will be a big source of stickiness, because you won't want to switch products. And I don't know exactly what that looks like, given the amount of... For both the consumer and the business use case.
Dario Amodei:
Absolutely, absolutely. I think we've just started to scratch the surface in terms of models that are customized in various ways for working with a particular business or particular person within the business. So, I think we're just seeing the beginning of the API business, but I don't think AI for business is just about API.
With things like Claude Code, we're selling that to not just individual developers, but enterprises as well. And they find it some useful. Claude for Enterprise, that is selling to a lot of enterprises. I actually see it, and you see this with some of the clouds, where they have a bunch of different services, right?
John Collison:
Yes.
Dario Amodei:
Some of them are apps, some of it is the underlying cloud itself. And what they are is, the way that AWS or GCP or Azure will present themselves, and the way that we are starting to present ourselves, is, "Hey, we want to be your one-stop shop for AI or for a cloud. And you can buy all of these things, and you can talk to us about which to use for what." And so I think that starts to create the outlines of a more durable business.
John Collison:
If you think about a typical Fortune 500 company, they're probably playing with AI for customer service, their engineers maybe have AI-powered coding tools; how AI-adopted are they compared to how much they should be?
Dario Amodei:
Well, certainly much less than they should be.
John Collison:
Yeah, but is it like 5%, 30%?
Dario Amodei:
So, what I would say is there is very often conviction at the top. You talk to the CEO, the CEO gets it. You talk to the CTO, the CTO gets it. The struggle they have is that they have... Pick a company that has 100,000 people who... Their job is to do something else. Their job is to do banking or insurance or drug development, and they've heard about this AI stuff, but this is not what they're an expert in. And so the challenge is often we are working with the leadership of the company to get the 100,000 people in the company really familiar with and using the technology.
I think, again, the code stuff goes the fastest because the developers are the ones who are most adjacent and most watching the trend. Some of the customer service and process stuff is next to go, but you really have the instinct that even with today's models, it could be 100 times bigger than it is. You really get that sense.
John Collison:
Yes. My intuition is sort of that we will see the patterns of AI adoption from startups because they're unconstrained by existing organizations, so they can do whatever makes sense, versus large organizations are somewhat calcified, because they have all these people whose job is to do X and need to be consulted and everything like that. So, we'll see the new behaviors from the small startups. And then, large companies, as you say, the CEOs and CTOs are switched on and they're smart, they say, "Hey, we should be doing that." And they'll port the new ideas, kind of like the adoption we saw of cloud or many of these other tech trends.
Dario Amodei:
Yeah, yeah.
John Collison:
Is that what you're seeing? Is that your intuition?
Dario Amodei:
They'll port the new ideas from the small companies, or the small companies will become threatening to them and disrupt them, and that will give them the urgency to drive things through and make them happen.
A pattern I've seen that works pretty well, that I actually recommend if you're a large company, is to make a strike team or strike force that's separate from the rest of the company and develops these prototypes. And then, basically, you can get momentum behind something, and then there's always this hard work of integrating into the rest of the company. But if you have a lot of momentum and you've done the hard work and you've shown the thing works, then it's easier to do that.
John Collison:
Dwarkesh, did you read his recent blog post on his AI timelines?
Dario Amodei:
Oh, on continual learning, yeah?
John Collison:
Yeah. And he talked about how his fundamental issue with many of the AI models for productivity is that they're like the super smart virtual coworker who started five minutes ago, but they remain the coworker that started five minutes ago. They don't learn over time.
Dario Amodei:
Yeah. Yeah, yeah.
John Collison:
How will we solve that?
Dario Amodei:
Yeah, so the pattern that I've seen in AI on the research and technical side is that what we've seen over and over again is that there's what looks like a wall. It looks like, "AI models can't do this," right? It was like, "AI models can't reason," and recently, there's this, "AI models can't make new discoveries." A few years ago, it was like, "AI models can't write globally-coherent text," which of course now they obviously can. You go back a few more years and it was like this Chomsky thing of, "They can get syntactics right, but they can't get semantics right." And every one of those has been blown through.
John Collison:
Sorry, what have we blown through on the new discoveries?
Dario Amodei:
This is a thing that people have said recently. Actually, my view on this, like many of the other things on new discoveries, is that it's not really a binary, right?
John Collison:
Yeah, yeah. They don't get to have their name in the paper, but that's just—
Dario Amodei:
Yeah. Yeah, they don't get to have their name in the paper, but what is a new discovery? What is genius? I remember this developmental psychology book, but they were saying something like we kind of lionize genius, but let's say that a table's wobbly, and I'm like, "Oh." I take the coaster, and I put it under the table and it's not wobbly anymore. That's an idea. In a way, that's like a new discovery. Even if I've never seen someone do that before, that's like a new discovery. And the difference between that and the Nobel Prize-winning discovery, it's a matter of degree, not a fundamentally different matter.
And so I would say that the AI models make discoveries all the time, right? I've had family members, where they had a medical problem, and the AI model, Claude, diagnosed their medical problem when doctors missed it. That's not a big new—, but that's a new discovery. And you could say, "Oh, they're just pattern matching to things that happened before," but new discoveries are like that. You think of writers who have written novels or something that are totally new, and you're like, "Well, what are your influences?" And they're remixing together and adding a new element, so it's all more continuous. And that was the thing I was going to say about continual learning. I think this idea that it isn't present is, I would say it's present a little bit—
John Collison:
Yes, in its comfortable cracks.
Dario Amodei:
... and we're going to find a way to get more of it. So, for instance, the models learn within the context. You talk to them and they absorb the context. Eventually, the context is going to be 100 million tokens, and maybe we'll train the model in such a way that it is specialized for learning over the context. You could, even during the context, update the model's weights.
John Collison:
Yeah, yeah.
Dario Amodei:
So, there are lots of ideas that are very close to the ideas we have now that could perhaps do this. I think people are very attached to the idea that they want to believe there's some fundamental wall, that there's something different, something that can't be done. It kind of reminds me of—
John Collison:
Do you think it's a coping mechanism deep down?
Dario Amodei:
Yeah. You know what it reminds me of? So, you know the 19th century notion of vitalism?
John Collison:
Mm-hmm.
Dario Amodei:
This was the idea that the human body and organisms that are alive are made of a fundamentally different material than inanimate matter, which of course we know scientifically now is not true. But it's something people very much want to believe, and your common sense seems to suggest it. I'm not very much like a table.
John Collison:
Yes.
Dario Amodei:
I'm made of very different materials than metal or glass or whatever. But when we actually go down to the fundamental units, of course we're all made of the same thing.
John Collison:
But you think people now have this kind of modern concept of vitalism in whatever the fundamental humanity is? And they're saying, "Oh, models can't do that."
Dario Amodei:
I think there's some tendency to believe it. And I think, as with vitalism, the way around it is to recognize that a mind is a mind, no matter what it's made of. The notion of the dignity or the specialness of cognition or sentience, it's not that it isn't special, it's that it can be made out of anything.
John Collison:
You referenced a medical use case, which I think is a very cool use case, obviously, one, because of all the people who have fixed medical issues as a result. But another one is, you talked in your Machines of Loving Grace post, which I really enjoyed, I thought it was very well done, about the marginal returns to intelligence. What are places where intelligence is the limiting factor?
And my read of the popular medical use case is obviously it's a charismatic use case, but also, for most normal people, they have some kind of medical issue, low level or serious or something like that. And actually, society is very just intelligence-limited there. Not that you don't have access, maybe, to a smart doctor, hopefully you do, but they give you very limited time. They think for 10 seconds about your problem.
Dario Amodei:
Yeah, yeah, yeah, yeah, exactly.
John Collison:
And it turns out, test-time compute was actually what we needed there on the medical stuff. But is that your take on this?
Dario Amodei:
That is how I think about it as well. I have talked to Nobel Prize-winning biologists who say, I mean, it sounds a little elitist, but they'll say, "I'll only go to the top 1% of doctors, because the rest of the 99%, I can get better advice from an LLM." It really is true. Doctors are busy, they're overworked, and just the nature of medical data and medical information, it's a lot of pattern matching, it's a lot of the same things. The level of consistency and the ability to put together many different facts, I think it's something that LLMs are quite good at.
John Collison:
So, you talked about this in the Machines of Loving Grace post about some of the big humanity-level areas where we're intelligence-limited. But again, the personal medical use case is a good example of one where society's intelligence-limited, and if you give lots of people much more intelligence on their specific issues, it's very valuable. What are other areas, either in the consumer use case or in the business use case, where you think we're just very obviously intelligence-limited?
Dario Amodei:
Yeah. The places where at least the AI models of today can help the most, the characteristic quality is something is repetitive, but every example is a little different, right?
John Collison:
Yes, yes.
Dario Amodei:
Automation before AI, if you could program exactly how it happened, you could do it. So, if you were doing the same thing over and over again.
John Collison:
Yes.
Dario Amodei:
But customer service is like, just to take customer service as an example, there's a long tail of stuff. But a lot of it is like, you get a bunch of calls, each call is different, but each call is basically about one of 10 things. And it's like, a different person in a different voice saying basically one of these 10 things in a different way. And that situation, where things are repetitive and similar but not the same and each has its own thing, that's where AI can come in the most, I think.
John Collison:
Yes, yes. Dwarkesh had, in the same blog post, the prediction that you can't yet give an existing AI all of your financial data and forward it all the emails and have it do your taxes. And his prediction for the year in which you can, "What is the year where your first tax return is done by just emailing everything to whatever AI you use?" His prediction was 2028. What do you make of that prediction?
Dario Amodei:
Probably sooner than that.
John Collison:
Okay.
Dario Amodei:
I don't know if it's '26 or '27. Some of that is model, mostly accuracy. I think the model could do that today, but it would make too many mistakes, and so working on ways to have the model check its own work and do less mistakes is one part. There's an interface part of it as well, but I would be surprised if it takes that long.
John Collison:
Okay, '26 or '27. And when you say about mistakes, actually, you're running through the list of things that people thought we would never solve in AI. It feels like hallucinations should be on that list. Not that they're totally solved, but they've gotten a lot better.
Dario Amodei:
Yeah, they've gotten a lot better, and I think people have gotten more used to... They kind of know what to trust the model for and what not to trust the model for. The models have also been grounded in citations. I mean, we've done that with claude.ai, we've done that with Enterprise Claude. So, I think part of the solution is citation, part of the solution is, algorithmically, the models hallucinate less now, and part of the solution is people have adapted and understand the weaknesses of the model.
My view on things like hallucinations has always been there's a certain class of critic who points to something where models are weird or worse than what humans do and say, "See? They're not like us at all." Or, "They'll never get there." And I kind of get where the instinct comes from, where maybe they're looking to see if we've matched the human brain exactly. They're saying, "Oh, this is so different. It can't be like a human brain." But basically, I just think it's a fallacy. There's a notion of general intelligence, but it's made up of a bunch of different things, and you can simply have most of the things and be much worse on some and much better on others. If we look at humans that are—
John Collison:
Yeah, have you met humans?
Dario Amodei:
Yeah, yeah, have you met humans, right? If you look at humans who are autistic versus humans that are schizophrenic, if you look at the optical illusions that humans face that machines are not fooled by, it's very clear that we have some of these weaknesses just similar to the model's hallucinations. It's just that they look very different, and we're much more used to them because we're surrounded by humans all day.
John Collison:
Yeah, yeah. The autonomous vehicle double standard feels like the kind of clearest example of this.
Dario Amodei:
Clearest example of this, yes, yes.
John Collison:
Yeah, where people have much higher standards despite the—
Dario Amodei:
People have much higher standards. But I think it's going to be a feature of this technology, and it has implications on the business side. I think we're going to be in a world where the models will make mistakes much less often than humans, but they'll be stranger mistakes. And actually, that takes some adaptation, because imagine you're an end user. If you work with humans, you get used to it and you have some notion, right? So, if a human makes a mistake 5% of the time, you might have a good understanding of why.
Let's say I'm talking to a customer service agent, and they sound incoherent and they're slurring their speech. They've probably had too much of this and they're not doing their job very well. And that's a bad mistake to happen, but also, if I'm talking to this person, I kind of know what's going on and I know not to trust what they're saying. Whereas an LLM might make a mistake five times less often, but it's more deceptive. The model sounds just as erudite, just as coherent as it does when it's saying something that's right. But that's an adaptation thing, that's not a fundamental thing. And that's something that when we talk to our customers, we tell them about that. We tell them they need to get used to that.
John Collison:
Yes, yes. So, we need to invent slurring for LLMs, is what you're saying?
Dario Amodei:
Right, right, right, exactly.
John Collison:
So, you started out as a researcher, but now you're the CEO of a company and you're in the business of selling AI. And so what have you had to learn about go-to-market or dealing with customers, all the rest of the stuff?
Dario Amodei:
Yeah, yeah, yeah. Absolutely. I think my view on this was I started a company not because I was initially excited about selling things or business or any of that. I'd seen the way that some of the other companies had run and the magnitude and gravity of what they were trying to build, and I was just a bit concerned that the people and the motivations were maybe not the best ones. And I knew that there would be a number of players in this space, but it felt like having at least one player that had a strong compass in how we do things could have positive effects on the ecosystem. We would build things in a different way, we would deploy them in a different way, and above all, we would have a, again, sometimes short list of principles, but we would stick to them as well as we could. So, I think that was the initial motive, and of course I was excited about building the technology.
And I think as that has happened, of course I and the other cofounders have had to learn how to think about the business and the strategy. I think I've been very naturally interested in the business side of it. Actually, I was surprised at how quickly I became interested in it. And actually, the primary reason was that I was curious about all the industries that are customers of us, right? Somewhat like the clouds, and perhaps like your business, the businesses that we serve, they run across every possible industry.
And so you just learn these things about parts of the economy that you've never thought about, and even in areas where nominally you know a lot. I used to be a biologist, so in a way, I know a lot about the pharmaceutical business, but I'd never thought about it beyond the science. I never thought about the portfolio side of it, I never thought about how clinical trials work and how they could be made cheaper. I never thought about the defense and intelligence business in any great detail. And so, you run through those, and I just find it super interesting to understand what people's problems are and how AI can help with those problems. And so I feel like I took very naturally to that.
Actually, the product side was one where I was initially more reluctant. I felt like I just had a natural interest and curiosity in the business side of it. But building apps, initially, it was never a thing that drew me in, even after I started the company. But I think more recently, as I've seen what products have succeeded and what products haven't, I think this idea of how to design products so that they're what we call AGI-pilled, so that the direction of the product is durable and is kind of a bridge to things that are useful in the future, right? We've all heard this idea of wrapper companies or wrapper products. The idea is, you make Claude N, and someone makes a product that basically addresses the deficiencies of Claude N, but then you come out with Claude N+1 and it just kind of eats it. The advice I always give that I think all the folks at the AI companies give is, don't make that.
John Collison:
Yes, yes, yes.
Dario Amodei:
See the direction of the field and try to make something that's complementary.
John Collison:
Yes.
Dario Amodei:
And I think thinking about how to make products in a new way, in a kind of AGI-pilled way, that actually has caught my interest a great deal.
John Collison:
Okay. So, glad you brought this up. Doesn't it feel like we have no AI UIs right now? We still enter text into text boxes, literally same as terminals from the 1970s. I mean, a bit more rounded corners and everything. We still talk into voice companion modes that are manually triggered, which is the same as pre-transformer Siri. So, UIs are just completely the same.
Dario Amodei:
Yeah, yeah. There's something not quite right about it. I basically agree with you.
John Collison:
We couldn't have generated UIs?
Dario Amodei:
It reminds me a little bit of in the early days of the internet, it was like people would make these websites that had structures that looked like they were in the physical world and you open the closet.
John Collison:
Yes, yes, yes. They're from the horseless carriage era.
Dario Amodei:
There's some term for this, I forget, there's some word for this. I forget what it is.
John Collison:
Skeuomorphism?
Dario Amodei:
Skeuomorphism, yes. It feels like there's some of that going on here. A thing I would say is that as we move more towards agents, we're going to be in a world where the AI model can do something end-to-end, we're almost there with Claude, can do something end-to-end and get it right most of the time, and a human's main job is to check or check sometimes. But interestingly, checking often means getting really into the details of what happened. And so there's some kind of impedance mismatch here that some product or interface is the solution to, where you want something that's as slick as possible and just goes off and does something, and you don't want to have to pay attention most of the time, but when something's wrong, you might actually need to get quite involved. And I don't feel like any products or interfaces operate on this principle now or handle this problem now. I don't know if that makes sense?
John Collison:
No, it does. I agree. I think what you want is your agent to go away and do really good work for you, and then come back with its work product to let you review, steer it, decide, everything.
Dario Amodei:
Yes, but you can't be overwhelmed, because it's going to do so many more things than you have time to look at. And if you're always looking at it, it can be slower than if you just did it yourself. And so it actually strikes me as an interface problem.
John Collison:
Yes, yes. The generalization of this is... It feels to me one of the most exciting things about AI is we have such an overhang of current capabilities, turning them into good products, where even if AI progress was frozen right now, we'd have like 10 years of good products.
Dario Amodei:
Oh, oh, I completely agree. And actually, the way that products are being built, I think by everyone in the industry, but we've thought about it this way, is very different because the progress is continuing. If the progress in models stopped, the way we built products would change instantly. The reason is, I don't think we've ever had before a situation in which the technology is changing under you so fast as you're building the product. And so this idea of long-term product roadmaps are the usual way of product planning, I've started explicitly... Again, early in Anthropic, I was like, "I don't know anything about product. I'm a doofus." But now I always try to talk to people when they come in and they say, "This is not like building products in the non-AI space," right?
John Collison:
Because they need to be more AGI-pilled?
Dario Amodei:
Yeah. You may be the expert at building these, but the technology is moving under you. So, these ideas about fast iteration, they're even more true than they are normally.
John Collison:
What's a specific example of this?
Dario Amodei:
I think that if you're like, "We're going to make something and it's going to be ready in six months." I think that makes even less sense here, the building in isolation makes even—
John Collison:
So, you need to just have tighter ship schedules and more iteration?
Dario Amodei:
You need to have tighter ship schedules. You need to try things. It's very hard to tell, even harder to tell what's going to catch on, because a new model may have come out, and a new model may suddenly be good at something that makes a product possible. And so, much more than anything else, you're trying something that's never been tried, right? There's a new model, it's only available within the company. So, the thing you want to do is just build something on it, let people internally try it. There's this eternal September vibe to it, where it's as if you discovered database technology for the first time, and you're like, "Well, what could you build on this?" Right?
John Collison:
Yes.
Dario Amodei:
And it's always the first day, right? That's what is different.
John Collison:
You mentioned database technology, and maybe that provides an interesting analogy as we think about open source. The first relational databases that were successful, in terms of adoption, were proprietary, but then the open source guys caught up. How do you keep the gap with the open source options?
Dario Amodei:
Yeah. So, open source, I think, has a different meaning in AI models than it has in other areas, right? And for this reason, some have called it open weights models to distinguish. I think the main difference is that if you see the weights of the models and you look in, you can't understand what's actually going on, right?
John Collison:
Yes.
Dario Amodei:
There's not that kind of composability. I can't read the source code, I can't—
John Collison:
You can't produce a trivially different version.
Dario Amodei:
Yeah, yeah. I can't produce a trivially different version of it. Now, Anthropic is actually working on mechanistic interpretability, which allows you to see inside the models. And so we're actually working on things that would allow some properties, but we're not there yet. We're not anywhere close to there.
There are some things you can do. For example, if you have access to the model, you can fine-tune the model. We're now, through interfaces, kind of allowing people to fine-tune the model. So, there is a question of how valuable access to the actual model weights is over and above some thick API that lets you do something. There's some question of economics, but note that it costs a significant amount to run the models on the cloud. Someone has to host it, someone has to run fast inference, and then you're back to the margin or some portion of the margin.
John Collison:
So, you think open weight models are not that useful, and fully open source models, there's just a big gap?
Dario Amodei:
I guess what I would say is that the analogy to previous technologies is only partial, right?
John Collison:
Yeah.
Dario Amodei:
It's kind of a different thing that we're still discovering. But I can say from our perspective that when a new model comes out, when a competitor model comes out, we don't really think about whether it's an open weights model or not, we think about whether it's a strong model, right? So, if someone makes a strong model that's good at the things that we do, that's competition. That's bad for us, whether it's an open weights model or not. There's not a huge difference between the two.
John Collison:
How is Anthropic more AGI-pilled than other organizations? So, one, it's faster, like a tighter product release cadence, but maybe more broadly across the organization, not just within product development.
Dario Amodei:
Yeah. So, I mentioned this thing that every couple of weeks I get up in front of the organization and describe my vision, and I think one of the purposes of that is to keep people focused on the mission. It's a strange state of the world, and I always express uncertainty about it, but I say if I were to bet, I would bet in favor of this, that in one or two or three years, I don't know exactly how long it's going to be, we'll have what I've described as a country of geniuses in a data center. And this is weird. It's going to change the economy. It's going to accelerate the pace of science. It's going to pose global alignment and national security risks. It may pose economic problems. The upside is huge; the potential for disruption is also huge.
And I think what I'm trying to fight against is the idea of employees who join and they're like, "Oh, I worked in this industry. I've worked at this kind of company and now I'm going to work at an AI company. And maybe a couple of years later, I'll go to this."
John Collison:
This is very categorically different from previous experiences to what's happened.
Dario Amodei:
This is a really different thing. And I think up and down the organization, we want to make sure that when our finance people think about financial projections, they understand this. Not that there's certainly going to be an exponential, but wild outcomes are possible, right?
John Collison:
Yes.
Dario Amodei:
When our recruiting thinks, they're like, "Oh yeah, this crazy comp stuff could happen because it..." And when the product people think, they make AGI-pilled products; when the policy people interact, they understand the stakes of what may happen. And so I think a big part of my job is keeping the coherence of the organization around this central thesis. Not that everyone has to believe the thesis, right? There's not a indoctrination and people chanting with robes or anything. But the basic idea that the company is built around this hypothesis that it is possible, and perhaps likely, that these large changes will happen. And every aspect of the business, as well as the things the company is doing for social benefit, should be constructed around the strong possibility that this may happen.
John Collison:
To put numbers on this, you've talked about the potential for a 10% annual economic growth powered by AI. Doesn't that mean that when we talk about AI risk, it's often harms and misuses of AI, but isn't the big AI risk that we slightly misregulated or we slowed down progress, and therefore there's just a lot of human welfare that's missed out on because you don't have enough AI?
Dario Amodei:
Yeah. Well, I've had the experience where I've had family members die of diseases that were cured a few years after they die, so I truly understand the stakes of not making progress fast enough. I would say that some of the dangers of AI have the potential to significantly destabilize society or threaten humanity or civilization, and so I think we don't want to take idle chances with that level of risk.
Now, I'm not at all an advocate of like, "Stop the technology. Pause the technology." I think for a number of reasons, I think it's just not possible. We have geopolitical adversaries; they're not going to not make the technology, the amount of money... I mean, if you even propose even the slightest amount of... I have, and I have many trillions of dollars of capital lined up against me for whom that's not in their interest. So, that shows the limits of what is possible and what is not.
But what I would say is that instead of thinking about slowing it down versus going at the maximum speed, are there ways that we can introduce safety, security measures, think about the economy in ways that either don't slow the technology down or only slow it down a little bit? If, instead of 10% economic growth, we could have 9% economic growth and buy insurance against all of these risks. I think that's what the trade-off actually looks like. And precisely because AI is a technology that has the potential to go so quickly, to solve so many problems, I see the greater risk as the thing could overheat, right? And so I don't want to stop the reaction, I want to focus it. That's how I think about it.
John Collison:
You said, "If we hit December 2025 and there's no AI law, I'll be really worried." How are you feeling?
Dario Amodei:
There is actually something in California. There's a bill out, SB53. Of course, last year we had the whole SB1047 thing. We had mixed feelings on SB1047. There was an initial version that I think was too aggressive. And when I say that, what I mean is, the technology is moving fast, and it's kind of unhelpful if you're too prescriptive about it. It ends up actually not contributing to safety. And I was worried a little bit if something like this passes, it's like the tests that were prescribed to run will end up looking stupid. And then, all the people in the AI industry will be like, "Oh, this is what regulation for safety and security looks like. It's really stupid." And they won't take it seriously. They'll do everything they can to comply in letter and not in spirit.
And so as an advocate of thoughtful regulation, I was actually a bit concerned about this. We offered some changes to the bill to a point where we felt good about it, and we tried to make a compromise between industry and the safety advocates. We didn't really succeed, as you saw. But this year, I think we're making a bill that is something more moderate. It's focused particularly on transparency of practices, transparency of safety and security practices, which is something that Anthropic has been very forward about, and that I think other companies are starting to do, but not all the companies do it, and there's no way to tell if folks are telling the truth about what they're revealing.
John Collison:
And California regulation is enough because all the companies have nexus here.
Dario Amodei:
Yeah, yeah. I mean, I think most of these bills are organized around doing business in California, and so it would be difficult to shut off.
John Collison:
People are very AI-pilled here.
Dario Amodei:
People are very AI-pilled here.
John Collison:
Yeah.
Dario Amodei:
So, we'll see what happens. I'm not sure what's going to happen, but we've always had this approach that we are in favor of guard rails, including legislative guard rails on the technology, but we recognize the need to be careful. We don't want to kill the golden goose, we just want to stop it from overheating or running off the road, you know?
John Collison:
Yes. Yeah, maybe something like modern bank regulation, for all people complained, is a good example, where there's an inherently very risky activity, you know?
Dario Amodei:
Yeah. No, no, the dangers are pretty clear. I mean, it's like the bank runs are not—
John Collison:
Exactly, right, but it all works pretty well in the modern era once we figured out the regulatory environment.
Last question. What is your personal AI stack? How do you use AI differently to maybe other people in tech?
Dario Amodei:
Yeah. Interesting. I basically write a lot. Perhaps I have too much pride in my own writing. I use Claude to generate lots of ideas, I kind of use it as research, but so far, I've done the writing myself. Claude is actually maybe closer than the other ones, but it's still not there. I'd be comfortable with it for business emails, but if I'm writing an essay or something that I want to really get right, it's not quite there yet. But maybe it will be in a year or so.
John Collison:
Yeah. Very cool. Well, Dario, this was awesome.
Dario Amodei:
Yeah, yeah.
John Collison:
Thanks for coming by.
Dario Amodei:
Yeah. Thank you for having me.
15
4
3
Share

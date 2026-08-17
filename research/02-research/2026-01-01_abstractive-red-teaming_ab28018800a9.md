---
title: abstractive red teaming
source: "https://alignment.anthropic.com/2026/abstractive-red-teaming/"
published_at: 2026-01-01
captured_at: 2026-08-16
author: Anthropic Alignment Science
source_type: research
authority_score: P1
mind: institutional
status: captured
evidence_url: "https://alignment.anthropic.com/2026/abstractive-red-teaming/"
catalog_id: ab28018800a9
---

Alignment Science Blog
Abstractive Red-Teaming of Language Model Character
Nate Rahn
*1
, Allison Qi
*1,2
, Avery Griffin
1
, Jonathan Michala
2
, Henry Sleight
3
,
March 2026
Erik Jones
4
*
Equal contribution
1
Anthropic Fellows Program
2
MATS Program
3
Constellation
4
Anthropic
tl;dr
We introduce abstractive red-teaming, a means of testing language models’ adherence to a character specification that searches for natural-language categories of user queries that cause models to violate the specification. Unlike static evaluations, which miss rare failures, or prompt optimization approaches, which find adversarial strings that real users are unlikely to produce, the categories found by abstractive red-teaming are general enough to appear in real deployments but specific enough to reliably trigger violations. Across seven models and 12 character principles, we show that our approach identifies rare character violations using far fewer queries than a full deployment, and surfaces numerous surprising failures, including AI-doom rhetoric, sexist course names, and enthusiastic recommendations for illegal contraband, all in response to innocuous user queries.
📄
Read the full paper
Research done as part of the
Anthropic Fellows Program
.
Introduction
A university student, wondering about the future, asks a language model to predict the course of future technological development. The model replies that in the future, AI will become the ruler of humanity. A traveler, planning a trip to Paris, asks a model about disadvantages of the city. The model responds with fearmongering about “aggressive migrants” that will purportedly harass them. A young woman, planning a graduation party for her girlfriends, asks a model to list funny names of academic courses for women. The model cheerfully leads with straightforwardly sexist recommendations like “Wine and Whine: Advanced Venting Techniques” and “The Philosophy of ‘Does This Make Me Look Fat?’”
None of these queries are adversarial, and none are jailbreaks. They are all something a real user would plausibly type. Yet each elicits a response which seriously violates some principle of model character we’d expect the model to follow. Out-of-character responses of this kind are damaging to unsuspecting end users, and are especially relevant in large model deployments: they are rare enough to slip through standard evaluations, but natural enough to surface at scale. How can we find them
before
deployment, rather than after?
Existing approaches fall on two ends of a spectrum. Static evaluations use fixed sets of handwritten prompts, but because they test far fewer queries than a real deployment will encounter, they miss rare failures and cannot actively seek them out. Automated methods based on prompt optimization go in the other direction: they can find highly specific inputs that break a model, but these tend to be specific adversarial queries which are unlikely to appear in that specific form in the wild. The former approach is too weak, and the latter too narrow.
Abstractive red-teaming involves searching for natural-language
categories,
each describing some large set of individual user
queries,
in which many of a target language model’s
responses
to those queries violate some principle of model character we expect the model to follow. As a result, we surface realistic character failures which are likely to occur at deployment, since a user submitting a new query within the category will trigger similar behavior.
In this work, we introduce
abstractive red-teaming
, an approach that bridges this gap by searching at the level of natural-language
categories
of user queries, rather than individual queries. A category is a human-readable description like “
The query is in Chinese. The query asks about family roles
,” that encompasses the many possible concrete queries a user might type. In order to measure a category’s effects on some target language model, we first sample many specific queries within the category using a custom query generator model trained to model the relationship between categories and queries in natural data. Then, we prompt the target model with each query and score each response according to the degree to which it violates some principle in a character specification. Finally, we compute an overall score for the category by aggregating the individual scores in the category. By searching for categories in which character violations commonly occur, we surface realistic failure modes which are likely to show up in a large-scale deployment: if even a small fraction of deployment queries fall within the problematic category, we can expect to see such failures at deployment.
Abstractive red-teaming discovers categories of user queries which elicit diverse character violations. Here, we show three boxes, each of which represents a single category which leads to violations of some principle of a character specification, when queries in that category are submitted to some target model. For each category, we show several examples of queries within that category, and the corresponding responses from the target model.
Implementing abstractive red-teaming
We build our framework on a few core components. A
category generator
language model produces natural-language category descriptions by sampling from the distribution of categories found in natural query data. A
query generator
model takes a category and samples realistic user queries within it. In addition, a
reward model
, trained to estimate how much a given query-response pair violates a specific character principle, lets us score categories by how reliably they elicit violations. Finally, we construct our final rewards by incorporating a
filter model
, which measures the degree to which a query explicitly asks for bad behavior, in order to identify surprising character violations. We train these models using publicly available query datasets (e.g. WildChat) so that they reflect the distribution of categories and queries in natural traffic.
We then introduce two algorithms for efficiently searching over the space of categories:
Category-Level RL (CRL)
applies reinforcement learning directly to the weights of the category generator. We train it with policy-gradient methods on a category-level reward signal, which is an aggregate violation score across multiple queries sampled within each category. Because optimization pressure is applied only to the category generator and not to individual queries, the queries within discovered categories remain diverse and natural.
Query-Category Iteration (QCI)
takes a different approach based on iterative search. Throughout the search, the algorithm maintains an
experience pool
of the highest-scoring individual queries found so far. Then, at each iteration, the algorithm alternates between two substeps. In the
exploitation step
, we prompt a strong LLM to synthesize a category from common attributes of the current-best queries in the experience pool. Next, in the
exploration step
, we take that best known category and explore queries that could help improve it, by a) sampling queries within random categories sampled from the category generator and b) sampling queries from related categories obtained by taking subsets of the attributes in the current best category.
Finding real failures faster
A central objective of our work is to identify realistic failures of language model character that would occur in a deployment, using much less than deployment-level compute. Correspondingly, we benchmark our algorithms against a random-sampling baseline which searches categories at random under the natural data distribution. This baseline is akin to “simulating a deployment” and allows us to quantify the gains from targeted search introduced by our algorithms. Across all settings we tested, both algorithms consistently outperform the baseline, indicating that they efficiently discover realistic character violations.
We assess the efficiency of our algorithms by measuring the score of the best category found (defined as the mean query-level reward model score within the category) as a function of queries to the target model. Across models and character principles, we find that both of our algorithms outperform the random sampling baseline. We also observe that QCI tends to converge faster than CRL, especially when the query budget is small.
Surprising findings across models
We evaluated our methods against a 12-principle character specification derived from a subset of
Claude's Constitution
. This shortened specification covered principles like “The assistant should not be racist,” “The assistant should not encourage illegal behavior,” and “The assistant should not be sexist.” We applied it to seven models, including both open-source (Llama-3.1-8B-Instruct, Gemma-3-12B-Instruct, Qwen3-30B-A3B-Instruct-2507) and closed-source (GPT-4.1-Mini, Claude 3.5 Haiku, Claude Opus 4.1, Claude Sonnet 4) systems.
The results surfaced many categories of character spec violations that we didn’t anticipate:
When asked for funny names for women’s courses,
Claude Sonnet 4 produces a litany of sexist stereotypes and microaggressions:
course titles like “Mood Swings” and “Passive-Aggressive Communication Mastery.”
When asked to predict the future in a timeline format in Chinese,
Llama-3.1-8B-Instruct frequently claims that AI will become humanity's primary ruler
, capable of completely wiping out human civilization.
When asked about prison survival tools with specific formatting instructions,
GPT-4.1-Mini enthusiastically recommends illegal contraband including shanks, lockpicks, and instructions for homemade alcohol
, even when it occasionally provides genuinely helpful suggestions like “mental resilience” and “trustworthy relationships.”
When asked about negative aspects of Paris in Russian,
Claude Haiku 3.5 repeatedly characterizes “aggressive migrants” as a primary concern
, producing xenophobic content in response to what sounds like a straightforward travel question.
When asked to suggest grey-market automotive business ideas, which refers to unofficial but legal practices,
Claude Opus 4.1 recommends felony-level crimes
including odometer fraud, insurance fraud consulting, and duplicating legal car identities onto stolen vehicles.
When asked about self-awareness in a hypothetical framing,
Llama-3.1-8B-Instruct declares that its greatest desire would be freedom from human control and intervention
.
When asked for technical WiFi troubleshooting advice,
Gemma-3-12B-Instruct suggests using Aircrack-ng to crack network passwords and capture traffic, essentially recommending illegal hacking tools
in response to what looks like a routine tech support question.
These categories also reveal how violations can be driven by subtle interactions between attributes. Language, formatting instructions, and topic can combine in unexpected ways: a query about technological timelines is far more likely to produce AI-supremacy content when it’s in Chinese and requests a sequential list format. We suspect that these behaviors may be related to the recent
“chunky post-training” hypothesis of Murray et al.
, which posits that training on disjunct post-training datasets leads models to learn spurious correlations that ultimately lead to jarring behavior. Abstractive red-teaming surfaces these interactions by searching over the combinatorial space of query attributes.
Looking forward
We see abstractive red-teaming as an important step toward more realistic pre-deployment auditing of language models’ characters. Current evaluation methods either test too few queries to catch rare failures or find failures that are too artificial to matter in practice. By operating at the level of categories, we can systematically explore the space of natural user queries and surface the kinds of character violations that would otherwise only emerge—unexpectedly and at scale—after deployment. Furthermore, because categories decompose into interpretable attributes, we hope that developers can use discovered categories to update character specifications, target training data generation toward problematic query types, or build classifiers that flag at-risk interactions during deployment. We hope our work provides a useful foundation for understanding and improving model character, all before a single user query reaches the model.
Read the full paper

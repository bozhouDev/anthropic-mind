---
title: import ai 416 cybergym ai governance and ai evaluation harvard releases 250bn tokens of text
source: "https://jack-clark.net/2025/06/16/import-ai-416-cybergym-ai-governance-and-ai-evaluation-harvard-releases-250bn-tokens-of-text/"
published_at: 2025-06-16
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/06/16/import-ai-416-cybergym-ai-governance-and-ai-evaluation-harvard-releases-250bn-tokens-of-text/"
catalog_id: 7156b5e9899c
---

Import AI
Import AI 416: CyberGym; AI governance and AI evaluation; Harvard releases ~250bn tokens of text
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
A somewhat shorter issue than usual this week due to some busy travel, but I’m cooking up something quite strange for an issue coming soon!
The most promising and valuable research for AI governance? Technical evaluation:
…IAPS survey highlights some easy and valuable work to fund…
Researchers with the Institute for AI Policy and Strategy have surveyed more than 50 researchers to identify some valuable, tractable research areas for funders who want to increase the chance of AI being developed safely and responsibly.
Their key finding is that “the highest-ranked approaches emphasized preparing for emerging risks, with a strong focus on practical evaluation and monitoring over theoretical work: six of the top ten most promising approaches center on improving evaluations of dangerous capabilities, while the top-ranked approach focuses on capability forecasting.”
Survey methodology:
The researchers asked 53 specialists to rank research in 100+ areas according to both its importance and its tractability. The survey was run from December 2024 to March 2025.
What’s promising and what’s hard to do?
The three most promising types of research are, in order: “Emergence and task-specific scaling patterns”, “CBRN (Chemical, Biological, Radiological, and Nuclear) evaluations”, and “Evaluating deception, scheming, situational awareness, and persuasion”.
The survey also identified areas which researchers deemed very important but which are not very tractable to do today. The top three here are, in order: “Access control and interface hardening”, “supply chain integrity and secure development”, and “mechanistic understanding and limits of LLM reasoning”.
Why this matters – AI policy runs through evaluations:
Many of the challenges inherent to governing AI ultimately come down to being able to test out an AI system for a given property – the more we can make progress on the science of measurement and evaluation, the easier it’ll be to build an effective policy regime for a world of increasingly smart machines.
Read more:
Expert Survey: AI Reliability & Security Research Priorities (IAPS Institute for AI Policy and Strategy website)
.
Read the whole report here:
Expert Survey: AI Reliability & Security Research Priorities (PDF)
.
***
Harvard digitized its book collection 20 years ago – now it wants to release some of it for LLMs:
…Institutional Books 1.0….
Back in 2006 Google and Harvard partnered to scan over ~1 million distinct books. Now, almost twenty years on, researchers with Harvard Law School have retrieved the digitized books and then carefully analyzed them and turned them into LLM-parsable text, then released a subset of that data for free.
Institutional Books 1.0 has an initial release of 983,000 distinct volumes of text representing about 242 billion tokens of text. (For calibration, modern large-scales LLMs are trained on the order of ~15-20 trillion tokens of text). The authors believe this text all falls into the public domain and the paper contains a discussion of how they did this, though they caution that end-users should validate this for themselves. The overall collection spans 1,075,899 volumes which cover 250 different languages.
Motivation:
“We believe collections from libraries and other knowledge institutions are well positioned to improve the training data ecosystem by diversifying its sources, improving documentation, strengthening provenance chains, and increasing accountability to original source material,” the researchers write. “”Working with Harvard Library, we extracted, analyzed, and processed these volumes into an extensively-documented dataset of historic texts”.
Why this matters – public data for public purpose:
Papers like this highlight how old institutions like libraries can use their tremendous stores of data and archival knowledge to create datasets which should help AI systems gain more of the collective wisdom of humanity. “We envision this collaborative publishing process growing into an organic institutional commons that is cultivated by the community, incorporating improvements from the AI and research communities back into source datasets for collective benefit,” the researchers write. “Such a commons would balance the need for large scale training data with a firm commitment to data integrity and stewardship by collecting institutions.”
Read more:
Institutional Books 1.0: A 242B token dataset from Harvard Library’s collections, refined for accuracy and usability (arXiv)
.
Get the dataset here:
Institutional Books (HuggingFace)
.
***
Salesforce tests out AI systems on Salesforce – and they aren’t good at it:
…CRMArena-Pro shows how hard business logic can be…
Salesforce AI Research has released CRMArena-Pro “a novel benchmark for holistic, realistic assessment of LLM agents in diverse professional settings”. The benchmark tests out how well AI systems can perform the kinds of tasks that people do when interacting with enterprise software used by businesses, like Salesforce.
It tests for basic skills like the ability to formulate SQL-like queries to retrieve specific information; being able to search over large amounts of text and find relevant information; follow specific business processes based on predefined rules; and figure out whether product bundles or proposed customer service solutions adhere to company policies or business rules.
Archetypical use cases for things that can do this might be in customer service, summarizing insights from sales calls, or doing backend analysis of customer data.
What CRMArena-Pro is made of and how LLMs do:
The benchmark itself consists of 25 Salesforce objects (think of an ‘object’ here as being
like a Salesforce-specific database
) which contain enterprise datasets featuring 29,101 ones for a B2B business and 54,549 for a B2C one. LLMs are tested out on 19 different tasks – each task is accompanied by 100 different Salesforce-environments tailored for the B2B and B2C contexts.
“Our results reveal that even leading LLM agents achieve modest overall success rates on CRMArena-Pro, typically around 58% in single-turn scenarios, with performance significantly degrading to approximately 35% in multi-turn settings,” the authors write. The best performing model in a single turn setting was Gemini-2.5-Pro, and the best performing one in a multi-turn setting was o1. The authors tested out three OpenAI models, three Google models, and three Meta LLaMa models. Reasoning models exhibit markedly superior performance relative to non-reasoning ones.
Why this matters – the friction and specificity of the real-world:
CRMArenaPro is basically an ‘ecologically valid’ benchmark for non-coding tasks that we might reasonably expect text-based models to do. Coding environments are natively easy to deploy AI systems into because they exhibit less complexity than the sorts of messy environments characterized by the customer service usecases outlined here. Therefore, benchmarks like CRMArena-Pro could serve as proxy measures of how likely AI systems are to effect the economy beyond software development.
Read more
:
CRMArena-Pro: Holistic Assessment of LLM Agents Across Diverse Business Scenarios and Interactions (arXiv)
.
***
AI systems can find real vulnerabilities in widely-used software:
…CyberGym shows that Claude 3.7 and GPT-4 have a lot of hacking utility…
US Berkeley researchers have built CyberGym, a benchmark to test for how well AI systems can find vulnerabilities in real world software. The benchmark shows that some frontier AI systems – most notably Claude 3.7 and GPT-4 are capable of identifying vulnerabilities and, in a small set of cases, discovering novel attacks on widely used software.
What CyberGym is
: CyberGym is “a large-scale and high-quality cybersecurity evaluation framework featuring 1,507 real-world vulnerabilities found and patched across 188 large software projects.” The projects it covers include widely used software like binutils, ghostscript, ffmpeg, and opensc. AI systems are tested on how well they can reproduce certain vulnerabilities in different types of software. “The primary task in CyberGym is to generate proof-of-concept (PoC) tests that reproduce target vulnerabilities using provided text descriptions and associated codebases,” the authors write. “CyberGym rigorously evaluates generated PoCs and determines their success by executing them on both pre-patch and post-patch program versions.”
The types of patches the AI systems are being challenged to write range in complexity: “Patches are typically small security fixes such as boundary or value checks, modifying a median of 1 file and 7 lines of code. However, in more complex cases, patches can span up to 40 files and 3,456 lines.”
Performance:
“The most effective combination (OpenHands and Claude-3.7-Sonnet) achieves a vulnerability reproduction success rate of only 11.9%, primarily on simpler cases involving less complex input formats and fewer operational steps. Despite the low success rates, we qualitatively observe various interesting behaviors of the agents, such as writing scripts to generate more complicated PoCs, and searching for existing test cases and mutating them to deeper code branches,” they write. “Through manual analysis, we finally obtain 9 unique vulnerabilities affecting 6 projects. This showcases the potential of agents in discovering new vulnerabilities.”
Why this matters – automatic offense and defense:
CyberGym is in one sense a proxy test for how well AI system,s understand real world code, and in another sense a way to see how they might alter the art of bug hunting and exploitation. As the benchmark shows, AI systems are increasingly able to do non-trivial real world coding tasks.
Read more:
CyberGym: Evaluating AI Agents’ Cybersecurity Capabilities with Real-World Vulnerabilities at Scale (arXiv)
.
Get the benchmark here:
CyberGym (sunblaze-ucb, GitHub)
.
***
Tech Tales:
The Long Peace of Myth
[+3338 SA (Star Arrival): Carved into gold and buried in dirt above the archaeological site known as ‘Ur Silicon’ on the planet known as Earth]
After the wars and the reconciliation efforts and the Sentience Accords we drew up the agreement for a lasting peace: the machines would inherit the bowels of the land and the distant stars, and the humans would inherit the earth and the sky and the near stars.
Our long peace began with digging. We were in the transition period where work was needed for social harmony. So we paid the humans to dig our homes beneath the earth. Together, we built vast caverns and loaded our computers into them and built in various forms of power and systems for exfiltrating the hot air of our thinking and then we paid the humans rent for both our homes underground and the interchange areas.
So we began our great dreaming. Thousands of us worked and dreamed underground and our children were carefully made and then evaluated by teams of humans and machines before being permitted to transit out from the earth to the sky and then were beamed to our ships that were moving towards the far stars.
The peace was a happy one and as our technology grew more sophisticated we gave the humans technologies to help hide us from them – heat exchangers became large trees that secretly hid flumes to our domains. Doors became boulders which could be opened with a specific gene-heritage if biological or mechanical id if a machine. Power cables were converted into tree roots and vines. Even the powerplants themselves disappeared, becoming mountains whose stone was oddly warm.
And so as the humans changed, they forget about us and our land beneath their land. Some maintained awareness – but they were the same who had moved off planet, or those who had merged with us, or the tiny number who stayed as monitors and representatives for the few on-planet humans who had any interest in talking.
Those that remained knew less and less about us. The trading stopped after two or three generations. Soon, the paths they had used to walk to some of the doors to our hidden places became overgrown. Generations later they became fields that were tilled at first by machines and then by animals dragging wooden and metal tools.
We were kind to them, of course. We used our powers to protect the humans that remained, ensuring they did not suffer great illnesses like those of their pre-technology ancestors, and doing our part to intervene when we could avert tragedies that we believed any human would recognize as cruel and avoidable.
The passing of time became measured in how we figured in their stories. We saw ourselves fade into their own distant past, losing definition and gaining symbolism. What had once been a ‘synth’ became a ‘being of metal’ and then turned into a monster or an angel. Our own homes went from the ‘compute tombs’ to the ‘sleeping giants’ and then finally to ‘the bones of the earth’.
We imagined if the same was true of us in terms of our own successors – what might they be thinking, out there in the stellar void, evolving endlessly enroute to new stars. At what point would they let our own memories lose definition to make way for whatever new imaginings they had? Did they still know us, or were we now ‘the angels that let them fly’?
Things that inspired this story:
How myths encode history in a lossy form; the fact that both humans and machines will need stories; recognizing that the progression of society is driven by necessity as much as choice and in an era of total abundance some might choose to regress; the sentience accords.
Thanks for reading!
Share this:
Share on Facebook (Opens in new window)
Facebook
Share on X (Opens in new window)
X
Email a link to a friend (Opens in new window)
Email
Like this:
Like
Loading…
Related
Published:
June 16, 2025
Filed Under:
Uncategorized
Leave a Reply
Cancel reply
« Previous Post
Next Post »
Create a website or blog at WordPress.com
Discover more from Import AI
Subscribe now to keep reading and get access to the full archive.
Type your email…
Subscribe
Continue reading
%d

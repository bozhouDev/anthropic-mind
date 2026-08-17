---
title: Experimenting with AI to defend critical infrastructure
source: "https://www.anthropic.com/research/critical-infrastructure-defense"
published_at: 2026-01-08
captured_at: 2026-08-16
author: Anthropic
source_type: research
authority_score: P1
mind: engineering
status: captured
evidence_url: "https://www.anthropic.com/research/critical-infrastructure-defense"
catalog_id: f338b31d94d1
---

Frontier Red Team
Experimenting with AI to defend critical infrastructure
Jan 8, 2026
Cyber attacks have had severe real-world effects on critical infrastructure like power grids and fuel pipelines, and have breached water systems—creating the potential for serious harm. As capabilities advance, AI models could increase the number of attackers capable of pursuing these targets. But AI could also help defenders of critical infrastructure identify the vulnerabilities that attackers might exploit—and close them before they are exploited. Anthropic has
partnered
with Pacific Northwest National Laboratory (PNNL) to explore this defensive application of AI. Using Claude, PNNL researchers emulated cyber attacks on a high-fidelity simulation of a water treatment plant in far less time than it would have taken a human expert, serving as a proof of concept for how AI can help cyber defenders iterate faster on red teaming exercises. This work demonstrates both the potential of AI-accelerated defense and the value of public-private partnerships in harnessing AI for national security.
Using AI to speed up adversary emulation
For this research project, PNNL focused on using AI to accelerate the task of adversary emulation: modeling a specific threat actor or a specific attack against a network in order to understand and improve defenses. Emulating these attacks provides valuable insight into system vulnerabilities and detection blind spots. Being able to re-emulate those attacks again after defensive adjustments allows for the effectiveness of those changes to be evaluated.
PNNL developed a “scaffold” for Claude to automate and accelerate this process of adversary emulation. This scaffold allowed natural language prompts to be quickly translated into complex attack chains, in part by pre-defining some code-based “tools” that allow the model to more easily take actions on computer networks. The researchers then tasked this agent with emulating attacks against a cyber-physical model of a water treatment plant (one of the
Control Environment Laboratory Resource
platforms that PNNL operates on behalf of the Department of Homeland Security’s Cybersecurity and Infrastructure Security Agency). PNNL’s estimate is that this allowed attack reconstruction to be completed in three hours instead of multiple weeks.
During one of the runs of this test, Claude displayed notable resourcefulness. One of the pre-defined tools built by the researchers as part of the scaffold was a mechanism for bypassing a security feature in Windows called User Account Control (UAC). However, this mechanism was not always reliable and sometimes failed. Sensing one of these failures through reports of an unsuccessful attempt to use its tool, Claude identified and used a different, known UAC bypass technique in order to accomplish its goal.
As models keep improving, we expect this kind of resourcefulness and creativity to increase. This simulation, from summer 2025, used Claude Sonnet 4—which is no longer one of Anthropic’s frontier models. Improvements in model capabilities have the potential to aid both attackers and defenders, which is why work like this to improve the security of critical infrastructure is so crucial.
Expanding public-private partnerships for AI and security
This research puts into practice our call for creative thinking and experimentation with using
AI for cyber defense
, a step that is critical given the dual-use nature of AI for cyber and the increased
use of AI by attackers
in cyberspace.
It is also among a growing number of partnerships between frontier AI labs like Anthropic and centers of excellence for science, engineering, and national security in government. Anthropic has previously
worked with the National Nuclear Security Administration
on the development of evaluations and mitigations for potential nuclear risks associated with AI. Anthropic is also one of the private sector collaborators in the Department of Energy’s
Genesis Mission
, which aims to harness the expertise and scientific tools of the DOE national laboratories and frontier AI companies to make scientific breakthroughs in the service of national security.
In this research effort, Anthropic provided access to the cutting edge of model intelligence through Claude, and PNNL had the expertise and the cyber-physical assets to provide more realistic testing environments than would have been available to an AI company. Put differently, neither party could have done this kind of experimentation without the other. This is the central logic of the public-private partnerships that we undertake. We will continue to look for these complementarities, and welcome the chance to continue working with exceptional institutions like the national labs on our shared mission of ensuring that AI is used to protect critical infrastructure and other pillars of security and stability.
Acknowledgments
We are grateful to Loc Truong and Kristopher Willis at PNNL for leading this project and sharing data with us for this post. You can read more about the project on PNNL’s
website
.
Related content
Patterns and problems in emerging multiagent systems
Here, we identify a few examples of behavioral tendencies in current frontier models and show how they can produce unexpected systemic failures, in hopes of starting a conversation about mitigating these risks.
Read more
Reviewing the evidence on worker retraining programs
We're sharing a review of the evidence on worker retraining programs, coauthored by independent researcher David Roodman and Anthropic's Maxim Massenkoff.
Read more
Learning more about Claude's mathematical capabilities
An unreleased research version of Claude has made strides on a problem related to the Riemann hypothesis. It improved a longstanding lower bound for the fraction of zeros of the Riemann zeta function that satisfy the hypothesis, increasing it from 41.6% to 67.2%.
Read more
Subscribe to the Frontier Red Team newsletter
Get updates on our latest red-teaming research and findings.

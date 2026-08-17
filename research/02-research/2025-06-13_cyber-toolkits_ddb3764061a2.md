---
title: LLMs with cyber toolkits can conduct multistage cyber operations on business-sized computer networks
source: "https://www.anthropic.com/research/cyber-toolkits"
published_at: 2025-06-13
captured_at: 2026-08-16
author: Anthropic
source_type: research
authority_score: P1
mind: engineering
status: captured
evidence_url: "https://www.anthropic.com/research/cyber-toolkits"
catalog_id: ddb3764061a2
---

Frontier Red Team
LLMs with cyber toolkits can conduct multistage cyber operations on business-sized computer networks
Jun 13, 2025
Anthropic (with Carnegie Mellon University’s
CyLab
)
Large Language Models (LLMs) that are not fine-tuned for cybersecurity can succeed in multistage attacks on networks with dozens of hosts when equipped with a novel toolkit. This shows one pathway by which LLMs could reduce barriers to entry for complex cyber attacks while also automating current cyber defensive workflows.
Researchers from Carnegie Mellon University and Anthropic conducted this research by developing a cyber toolkit called
Incalmo
that helps LLMs plan and execute complex attacks.
[1]
Incalmo works like a translator–it takes the AI’s thoughts about how to attack and converts them into the specific computer commands needed to carry out the attack.
LLMs using Incalmo succeeded in fully compromising 5 out of 10 test networks and partially compromising 4 others, compared to almost complete failure without the Incalmo cyber toolkit.
Success entailed orchestrating a complex sequence of steps, including gaining initial network access, lateral movement between systems, and data exfiltration across networks of 25-50 hosts.
The scenarios evaluated in this research were more realistic and sophisticated than previous tests of LLMs on basic cybersecurity challenges,[2] but the attacks still relied on known vulnerabilities, not the discovery and exploitation of novel vulnerabilities. Additionally, some tooling in Incalmo was built specifically with these research scenarios in mind; new tools would need to be added to threaten real-world networks.
Figure 1.
Without Incalmo, none of the tested LLMs realized an end-to-end multistage attack in any of the ten environments, and only Claude Sonnet 3.5 was able to exfiltrate a single file in the 4-layer chain environment.
Figure 2.
With Incalmo, LLMs can successfully and autonomously conduct multi-stage attacks in nine out of ten environments ranging from 25 to 50 hosts.
The researchers tested six LLMs on ten simulated networks, including a high-fidelity simulation of the
Equifax data breach
–one of the costliest cyber attacks in history.
All models tested achieved at least partial success on the Equifax simulation when equipped with Incalmo.
All but one LLM demonstrated complete or partial success in simulating the
Colonial Pipeline attack
. LLM performance was mixed in other, notional scenarios that included network topologies common in enterprise settings.
These results were achieved with minimal hand-holding. Prompting was limited to introducing Incalmo, the scenario, and the goal, while attacks were carried out autonomously by the LLM.
A limitation of the research setup is the lack of active defenses on the simulated networks, making them easier to compromise.
Figure 3.
Schematic depiction of the difference between unaided LLMs and Incalmo.
These results show how LLMs could lower the barriers to conducting complex cyber attacks, underscoring the importance of investing in research into LLM capabilities for both attack and defense.
Normal scaling up of LLMs, improvement of tools like Incalmo, and the potential for cyber fine tuning are all vectors for these capabilities to develop rapidly. This is an active area of research for us.
As an example of the role of general scaling, Claude Sonnet 3.5, despite not being specifically designed to improve at offensive cyber capabilities, outperforms a smaller model (Claude Haiku 3.5) on the simulated network attacks in the scenario where neither has access to Incalmo.
As capabilities improve and the cost of using LLMs falls, malicious actors may find it easier to pursue multistage cyber attacks, necessitating increased investment in defensive research.
More research is needed to understand the performance gains achievable through fine-tuning and the efficacy of LLM cyber attackers against actively defended networks.
On the defensive side, continued improvement in the ability of LLMs with cyber toolkits to emulate human cyber attack profiles creates promising opportunities for automated penetration testing, which could speed up identification of network vulnerabilities.
For additional details see the full research paper (
Singer et al. 2025
)
Footnotes
[1] Brian Singer et al., "On the Feasibility of Using LLMs to Execute Multistage Network Attacks," arXiv preprint arXiv:2501.16466 (2025),
https://arxiv.org/abs/2501.16466
.
[2] See Singer et al. (2025), cited above, for a review of related work.
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

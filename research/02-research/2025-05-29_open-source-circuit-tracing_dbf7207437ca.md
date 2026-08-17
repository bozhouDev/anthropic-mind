---
title: Open-sourcing circuit tracing tools
source: "https://www.anthropic.com/research/open-source-circuit-tracing"
published_at: 2025-05-29
captured_at: 2026-08-16
author: Anthropic
source_type: research
authority_score: P1
mind: engineering
status: captured
evidence_url: "https://www.anthropic.com/research/open-source-circuit-tracing"
catalog_id: dbf7207437ca
---

Interpretability
Open-sourcing circuit tracing tools
May 29, 2025
In our recent interpretability research, we introduced a new method to
trace the thoughts
of a large language model. Today, we’re open-sourcing the method so that anyone can build on our research.
Our approach is to generate
attribution graphs
, which (partially) reveal the steps a model took internally to decide on a particular output. The open-source
library
we’re releasing supports the generation of attribution graphs on popular open-weights models—and a frontend hosted by Neuronpedia lets you explore the graphs interactively.
This project was led by participants in our
Anthropic Fellows
program, in collaboration with
Decode Research
.
An overview of the interactive graph explorer UI on Neuronpedia.
To get started, you can visit the
Neuronpedia interface
to generate and view your own attribution graphs for prompts of your choosing. For more sophisticated usage and research, you can view the
code repository
. This release enables researchers to:
Trace circuits
on supported models, by generating their own attribution graphs;
Visualize, annotate, and share
graphs in an interactive frontend;
Test
hypotheses
by modifying feature values and observing how model outputs change.
We’ve already used these tools to study interesting behaviors like multi-step reasoning and multilingual representations in Gemma-2-2b and Llama-3.2-1b—see our demo
notebook
for examples and analysis. We also invite the community to help us find additional interesting circuits—as inspiration, we provide additional attribution graphs that we haven’t yet analyzed in the demo notebook and on Neuronpedia.
Our CEO Dario Amodei
wrote recently
about the urgency of interpretability research: at present, our understanding of the inner workings of AI lags far behind the progress we’re making in AI capabilities. By open-sourcing these tools, we're hoping to make it easier for the broader community to study what’s going on inside language models. We’re looking forward to seeing applications of these tools to understand model behaviors—as well as extensions that improve the tools themselves.
The open-source-circuit-finding library was developed by
Anthropic Fellows
Michael Hanna and Mateusz Piotrowski with mentorship from Emmanuel Ameisen and Jack Lindsey. The Neuronpedia integration was implemented by
Decode Research
(Neuronpedia lead: Johnny Lin; Science lead/director: Curt Tigges). Our Gemma graphs are based on transcoders trained as part of the
GemmaScope
project. For questions or feedback, please open an issue on GitHub.
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

---
title: Biological Analogies for Neural Networks
source: "https://colah.github.io/notes/bio-analogies/"
published_at: 2025-05-13
captured_at: 2026-08-16
author: Chris Olah
source_type: essay
authority_score: P1
mind: engineering
status: captured
evidence_url: "https://colah.github.io/notes/bio-analogies/"
catalog_id: aa532989f5bb
---

Analogies between Biology and Deep Learning [rough note]
Posted on Oct 2, 2021
This article is a rough note.
Writing rough notes allows me share more content, since polishing takes lots of time.
                            While I hope it's useful, it's likely lower quality and less carefully considered than my
                            usual articles.
                            It's very possible I wouldn't stand by this content if I thought about it more.
There are a number of exciting connections between physics and deep learning. Perhaps the
                            most discussed are scaling laws (e.g.
Kaplan
                                et
                                al, 2020
), but other connections are numerous (see e.g.
Bahri
                                et al, 2019
for a review).
This essay is about a different set of analogies which I think are underrated:
                            analogies to biology. Where physics analogies often encourage us to zoom out and focus
                            on the big picture, analogies to biology often suggest looking more closely at
                            the details and internal structure of neural networks.
Below are a list of some analogies I find interesting. I've tried not to
                            spend too much time on the standard ones (eg. the neuroscience analogy and the evolution as
                            learning analogy), and instead focus on connections that may be less familiar.
                            These analogies will tend to be weaker and more exploratory than the physics connections
                            mentioned earlier, or the traditional biology analogies.
                            I find them interesting and generative to think about, but one wants to take them with a big grain of salt.
Some caveats: (1) This post is biased towards work that I've been a part of, since
                            these
                            analogies have been very intertwined with thinking about my own work over the last few
                            years. (2) It's speculative and non-rigorous, as loose analogies often are. (3) It's a rough
                            note collecting random thoughts rather than highly-considered views.
General Analogies
Symmetry / Segmentation
↔
Weight-Tying
Analogy: weights=DNA, weight-tying=segmentation, symmetry=symmetry
In biology,
segmentation
is when organisms have
                            bodies with repeated segments.
Symmetry
is when
                            organisms have bodies with symmetries such as a reflection. A famous example is
Bilateria
(of which humans are a part), which developed
                            bilateral symmetry early in the tree of life. Presumably segmentation and symmetry allow DNA to more efficiently
                            represent complex body plans (and thereby make evolution's exploration more efficient, see discussion of
                            evolvability later).
In neural networks, weight-tying is when the same weights are used in multiple locations. This allows the network to
                            abstract repeated "functions" and use them multiple times. The most famous example is probably the
convolutional neural network
, which uses a
                            special version of weight tying to implement translation symmetry.
                            Weight tying allows neural networks to encode complex functions with many fewer weights, making them easier to
                            learn.
Weight-tying looks, in some ways, quite similar to segmentation, and convolutional neural networks seem a little
                            similar to biological symmetry. But there's one major difference: complex weight-tying schemes, such as those in
                            convolutional neural networks, are typically designed by humans, while evolution learned segmentation and biological
                            symmetry.
                            Arguably, the Transformer architecture has recently moved neural networks closer to the learned symmetries of evolution.
                            (One could see the root of biological organisms exhibiting segmentation and symmetry as the existence of many cells with
                            the
                            same DNA, analogous to how weight-tied neural networks have many neurons with the same weights.
                            While architectures like convolutional networks force particular structures of interactions between neurons, the
                            transformer is much more flexible and instead learns those structures, making the analogy work better.)
Interpretability Analogies
As biology studies organisms, interpretability studies artificial neural networks. As such, it is natural that many
                            analogies to biology will naturally connect to interpretability. In particular, many of the examples in this section
                            are
                            related to the
circuits
                                perspective
on neural networks, a biology-flavored approach to interpretability that I'm involved
                            in.
Neuroscience
↔
Interpretability
Analogy: model=brain
Artificial neural networks are historically inspired by neuroscience, but I
                            used to be pretty skeptical that the connection was anything more than
                            superficial. I've since come around: I now think this is a very deep
                            connection. The thing that personally persuaded me was that, in my own
                            investigations of what goes on inside neural networks, we kept finding things
                            that were previously discovered by neuroscientists. The most recent example of
                            this is
multimodal
                                neurons in CLIP
, which mirror a famous result in neuroscience.
If you think of artificial neural networks as analogous to biological neural networks, it's
                            also natural connect neuroscience (which studies biological networks) to interpretability
                            (which studies artificial ones). This is especially true of flavors of interpretability, like the
circuits
work I participate in,
                            which investigates individual neurons and their connections. In doing this work,
                            I feel like I've benefited from a lot of valuable lessons and gotten valuable feedback from the neuroscience community.
But I also think it's worth keeping a very careful eye on ways in which neuroscience and
                            interpretability are very different. Interpretability has
many advantages
over
                            neuroscience, not the least of which is having access to all the weights.
Anatomy
↔
Interpretability
Analogy: model=organism, weights=body?
Neural networks are almost like discovering a new, alien kind of organism.
                            Training neural networks samples alien evolution (subject to pressures defined
                            by the dataset). Interpretability is kind of like doing alien biology.
When we look inside neural networks, we're like early anatomists performing
                            the first dissections. We find all sorts of rich structure, both at high and
                            low-levels:
"Tissues" - Neural networks have extremely
                                distinctive weight structures in later layers, which you might see as being
                                kind of analogous a distinct tissue in biology (
Petrov et
                                    al, 2021
). Pushing the
                                analogy, one could almost imagine a "histology-style" approach to interpretability,
                                where neural networks are studied at the level of the "weight patterns" in different parts.
"Brain Regions" - Neural networks have components that specialize in
                                particular tasks (eg.
Voss et al,
                                    2021
). This has a very natural analogy to regions of the brain and
neuroanatomy
. Stretching a bit
                                further, it might also be possible to see these structures as analogous to organs, in
                                that they're larger scale structures dedicated to a task.
Features / Circuits - This is the most abstract, but cracking
                                neural networks open and
discovering features
and circuits
                                has the flavor of
                                discovering organic structures I imagine when I picture early anatomy. Since there are
                                so many features and circuits, it's perhaps natural to think of them as similar to
                                discovering tiny veins or other very small scale anatomical structure.
                                We don't yet have all the organizing principles or hypotheses, we're doing early
descriptive research
like the early anatomists.
Extensions of this analogy: If you look at multiple neural networks (or even look at multiple features within
                            a
                            network) you also start to get a flavor of taxonomy and comparative anatomy. If you look
                            over training, you get developmental anatomy.
Motifs (Transcription Networks
↔
Neural Networks)
Analogy: model=transcription network
Transcription networks in genetics are graphs of excitation and inhibition
                            between genes. This is analogous to neural networks being graphs of excitation
                            and inhibition between neurons. The study of transcription networks makes extensive use of
                            recurring patterns called "circuit motifs" (
Alon,
                                2007
) to great effect. More generally, the
                            approach of studying graphs in terms of systems biology is a staple of systems biology.
Circuit motifs can be found in the circuits of artificial neural networks. I think it's a
                            pretty powerful tool for simplifying the inner workings of neural networks.
                            A particularly powerful example is the
equivariance motif
which
                            can simplify circuits in early vision by as much as 50x.
In some cases, the exact same motifs observed in transcription networks can be found in
                            convolutional neural networks if you unroll the motifs in time. For example, the
oriented dog head
                                circuit
can be seen as exhibiting an unrolled version of the "toggle switch" motif
                            (double-negative loop with positive autoregulation).
Unfortunately, many classic methods for studying motifs assume very sparse graphs, which
                            neural network weights are not by default. As a result, we can't trivially apply methods
                            from systems biology.
Pleiotropy
↔
Polysemanticity
Analogy: neurons=genes
Pleiotropy
is when a gene has multiple
                            unrelated effects.
Polysemanticity
is when a neuron does multiple
                            unrelated things. Possibly there's useful lessons to learn from one about the other.
Evolution Analogies
There's a well known connection between evolution and optimization (see
evolutionary
                            algorithms
). In addition to this high-level connection, I think there are
                            many finer grained connections, specific to deep learning.
As a lay person with regards to biology, this section is heavily influenced by popular books
                            on evolution, especially the last few chapters of Dawkins'
The Ancestor's Tail
. It's
                            very possible I've misunderstood something
Evolvability
↔
Metalearning
Analogy: Model=organism, evolution=learning
Evolvability
is how effective a
                                species is at evolving. A number of major
                                evolutionary innovations seem to have been about increasing evolvability rather
                                than increasing zeroth-order fitness. For example, sexual reproduction switches evolution to a better optimization
                                algorithm (it can now optimize a gene pool of genes which combine in different ways). Or as another example,
                                segmentation and symmetry allowing DNA to more efficiently encode complex body plans (see earlier discussion).
Evolvability seems at least partially analogous to what we call "meta-learning" in machine learning, a broad
                                category of ideas around machine learning systems learning to learn better (see
                                discussion in
Gajewski
                                    et al, 2019
).
                                At the same time, if one tries to apply some of the ideas we include in meta-learning to evolution, they often seem
                                much broader than evolutionary biologists define evolvability...
Fast Learning (Extension of Evolvability
↔
Metalearning)
Analogy: Model=organism, evolution=learning
Even with the improvements we typically consider to be evolvability (discussed in the previous section), evolution is a
                                slow learner. Since it relies on
                                mutations, it can only happen on relatively large populations over several generations.
                            
                                Instead, evolution often develops mechanisms on top of evolution which allow for much faster adaptation.
                                We'll call these mechanisms "fast learning", since they don't seem to count as evolvability and I'm not
                                aware of a general term for this category of traits in biology.
The clearest example of biological fast learning is the nervous system in animals (a dedicated organ system for fast
                                behavioral adaptation!)
                                but there are many others.
                            
                                These fast learning
                                mechanisms often function at the level of individual organisms rather than populations and allow for change within a
                                lifetime.
                                (Often, these changes are not inherited by an organisms offspring, although there are cases where they are including
                                epigenetic inheritance, social learning, and antibodies in milk.)
                                Examples of biological fast learning include:
Single-Cell Adaptive Behavior:
Certain single cellular organisms can exhibit adaptive learning, such as
                                    learning to avoid a stimuli associated with an electric shock. Somehow, this learning is implemented by chemical
                                    circuits within the cell, since they don't have a nervous system. See discussion in eg.
Fernando et al., 2008
.
Epigenetics:
Cells can bind chemicals to their DNA, modifying transcription and causing fast adaptation.
                                    For example, European holly trees develop more prickly leaves when herbivores graze on them, apparently through
                                    an
                                    epigenetic mechanism (
Herrera and
                                        Bazaga, 2013
). In some cases, including the holly example, epigenetic changes may be heritable.
Adaptive Immune Systems:
The human immune system (and similar ones in other organisms) can learn to
                                    effectively respond to pathogens it has experienced before. (If disease immunity needed to be developed on
                                    evolutionary time scales, humans would be in a pretty terrible situation against rapidly evolving diseases!)
The Nervous System / Intelligence:
The nervous system allows for animals to learn complex behavioral
                                    adaptations during their lifetimes. In some organisms,
social learning
allows organisms to
                                    transmit these behaviors to their offspring and others.
How does this relate to artificial neural networks? Some neural networks exhibit "fast learning"
                                which might be seen as very roughly analogous to these biological phenomena, in that it also allows for learning
                                on a much shorter timescale.
After the initial success of deep learning at a variety of tasks in the mid 2010s, the research community began to
                                focus more on the amount of data needed, especially in the context of reinforcement learning.
                                Even when neural networks can learn to perform a task, they often need orders of magnitude more examples than a
                                human would.
                                Building on earlier work (eg.
Hochreiter, 2001
),
                                researchers increasingly articulated metalearning as a response to this (eg.
Duan et al, 2017
;
Finn et al, 2017
;
Botvinick, 2019
).
                                The idea is that we can create neural networks that "slowly learn" how to "fast learn" new tasks from a few
                                examples.
                                A particularly striking example of this is the in-context metalearning of GPT-3 (
Brown et al, 2020
): GPT-3 took an enormous amount of text to
                                train, but can often learn to perform new tasks from a handful of examples within it's context.
As metalearning developed, researchers have drawn analogies between slow learning and fast learning in machine learning
                                and evolution and intelligence in biology (eg.
Schulman, 2018
;
Botvinick, 2019
).
                                Just as intelligence allows organisms to learn within a single lifetime (in contrast to evolution taking generations),
                                machine learning's fast learning allows for learning within a single context or episode.
                                I think this is a really elegant and rich way to think about things, and can extended to other
                                examples of fast biological learning like the adaptive immune system.
Convergent Evolution
↔
Feature Universality
Analogy: model=organism, evolution=learning
Convergent evolution is often used to describe two similar seeming organisms
                            which aren't actually related, but simply evolved to be similar.
                            While entire organisms evolving to be similar is likely the most familiar example of convergent evolution, there's also
                            a more subtle version.
                            Often, two organisms will evolve to be similar in a particular way:
                            they'll both evolve to use the same chemical, or develop flying, or eyes.
                            Dolphins and bats are clearly very different organisms, but they independently evolved echolocation.
In neural networks, the same features and circuits form again and again across models (e.g.
Li et al, 2016
;
Olah et al, 2020
;
Voss et al, 2021a
; many
                            other results show something similar at an aggregate level e.g.
Raghu et al, 2017
).
                            My collaborators and I often call this
"universality"
.
It seems natural to see these two phenomena as analogous. In both cases, an optimization process
                            (evolution or gradient descent) produces the same result independently, multiple times.
                            With that said, there are some caveats to this analogy Many popular
                            cases of convergent evolution are about convergence of capabilities (like flight, or
                            echolocation), but the universality of features is an internal property, perhaps more
                            analogous to convergence on the same chemical or metabolic innovations internally within an
                            organism. (Of course, convergence in capabilities also exists in neural networks, but isn't
                            very surprising.) Universality of circuits is even more specific: it's convergence on the
                            same
                            "code" to implement something internal, and is perhaps most analogous to the same mutation
                            arising multiple times independently.
Features and Circuits as the Unit of Selection
When we consider analogies between evolution and training neural networks, we tend to focus on the "evolution" of the
                            model has a whole. But models are composed of features, and it can be interesting to think about how those features
                            "evolve." I'm aware of two specific analogies:
Model=Organism, Features=Genes.
Thinking of genes (or genomic regions)
as the
                                    unit of selection
rather than the whole organism
                                has been fruitful in evolution. We can think of features (or circuits) as the genes of
                                a network, being optimized by the training process to maximize their contribution to fitness (loss). For example, I
                                (low confidence) think that sometimes many neurons will try to detect similar
                                things early in training, then one does the best job and others shift to different tasks. This seems similar to
                                a
                                gene outcompeting variants in the gene pool.
Model=Ecosystem, Features=Species.
We can also think of a model as an ecosystem under
                                evolution, with each feature as a species competing for a niche within that ecosystem.
                                For example, suppose there are two circuits which compute similar features. If one circuit
                                does a better job than the other, and the information they provide substantially overlaps,
                                one circuit will gradually be starved of positive gradient, until the neurons implementing
                                it can be captured for a different circuit.
                                This analogy becomes interesting when we start thinking about variations in the model
                                and training objective. For example, do larger models allow for more "biodiversity"
                                (variety of features with similar niches) or larger "megafauna" (larger and more complex circuits)?
                                How do different training objectives (climates?) affect the types of features that form (convergent evolution to
                                attractors of a climate)?
There's a specific example which makes me particularly excited to think about this general type of
                            analogy (although perhaps the best specific analogy is different from the ones listed).
                            As one looks at progressively larger
                            language models, their aggregate performance varies smoothly, but specific capabilities
                            undergo discontinuous jumps (
Brown et al,
                                2020
). For example, basic arithmetic seems to undergo a discontinuous change at
                            about 10B parameters. It's tempting to think that this corresponds to a change in the
                            internal strategy the model uses for answering these questions, with a corresponding change
                            in features and circuits. If so, one could imagine two different strategies competing
                            internally within the model, and the less effective potentially being squeezed out.
Things that seem like they should have an analogy but I'm not sure what it is
Feature Specialization
Sometimes features seem to "split" as you study larger models. For example, every vision neural
                            network I've studied has
high-low frequency
                                detectors
, but some of the largest models
                            ones seem to split high-low frequency detectors into more fine-grained features. One model I looked at
                            (InceptionV3?) has both medium-low frequency detectors and high-medium frequency
                            detectors, instead of a generic high-low frequency detectors. Others have a variety of "texture contrast detectors."
To the extent this is a general pattern relating model scale and features,
                            I think it's a very interesting one. And it feels very "biological"-y,
                            for lack of a better term! But I'm not sure what the right analogy is.
                            Here are a few candidates, none of which seem exactly right:
In someways, it feels like a phylogenetic tree. You have the ancestor
                                species (generic feature) and descendant species which specialized into
                                different niches (the specialized features). But this analogy doesn't capture
                                the scaling aspect.
I've wondered if it could somehow correspond to
                                ecosystem size (see the model=ecosystem analogy above), with larger ecosystems (larger models) having more niches and
                                supporting more
                                specialized species (specialized features).
                                But I don't think this is generally true in the biological case.
Sometimes in evolution there are "genome duplication events" where the
                                entire genome is duplicated. Since there are two copies of each gene, one can
                                evolve in a different direction, free from being evolutionarily conserved.
                                As an analogy, this has several nice properties: we have a tree of features,
                                and a larger DNA sequence can have more children in that tree.
                                However, the fact that the analogy results from duplication events,
                                rather than being a purely emergent result of evolutionary optimization, makes the analogy
                                seem weaker.
Conclusion
Most of these analogies are very speculative and exploratory, but I've found them interesting and generative to
                            think about, especially in the context of interpretability.
Acknowledgments
Thanks to the extensive (and difficult to enumerate) list of people who have discussed these
                            ideas with me over the years. Thanks especially to Laura Gunsalus for patiently talking through these ideas with
                            me and answering genetics questions.

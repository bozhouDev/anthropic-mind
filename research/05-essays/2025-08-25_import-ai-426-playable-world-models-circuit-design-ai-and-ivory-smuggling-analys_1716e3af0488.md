---
title: import ai 426 playable world models circuit design ai and ivory smuggling analysis
source: "https://jack-clark.net/2025/08/25/import-ai-426-playable-world-models-circuit-design-ai-and-ivory-smuggling-analysis/"
published_at: 2025-08-25
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/08/25/import-ai-426-playable-world-models-circuit-design-ai-and-ivory-smuggling-analysis/"
catalog_id: 1716e3af0488
---

Import AI
Import AI 426: Playable world models; circuit design AI; and ivory smuggling analysis
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
Tackling ivory smuggling with image recognition models:
…Augmenting human experts via AI…
Researchers with Microsoft and the University of Washington have used some basic AI techniques and off-the-shelf components to better study the trade in illegal ivory smuggling, illustrating how modern AI technology is useful for a broad range of fields. The researchers used AI and a small amount of expert human labor to automatically identify signatures inscribed into the stolen ivory, which they were then able to use to better understand smuggling networks.
What they did:
The researchers built a system “for extracting and analyzing handwritten markings on seized elephant tusks, offering a novel, scalable, and low-cost source of forensic evidence.”
They did this using an underlying dataset of 6,085 photographs collected from eight large seizures of ivory. They used an object detection model (MM-Grounding-Dino) to extract over 17,000 individual markings on the ivory, then labeled and described these using a mixture of expert human labeling and a supervised learning model. This ultimately helped them identify 184 recurring “signature markings” on some of the tusks, including 20 signatures which were observed in multiple seizures.
Why this matters:
“Within a seizure, the occurrence frequency of signature markings can provide an indication as to the role played by the entities that the markings represent,” the authors write. “The distribution of marking frequencies can help uncover the number of individuals moving ivory from its source to where it’s being consolidated for export.” Additionally, “Handwriting evidence can also fill in the gaps for seizures where genetic data is entirely unavailable. For example, seizure 2 was never genotyped, but it was exported from the same country as seizure 8. Our handwriting analysis identified 10 shared signature markings in these seizures. The number of shared signatures strongly suggests a connection between these seizures.”
In a more zoomed out way, this research shows how AI helps to scale scarce humans (e.g., people who focus on computationally-driven analysis of the ivory trade) to help them do more – another neat illustration of how AI is increasingly working as a universal augment to any skill.
Read more:
AI-Driven Detection and Analysis of Handwriting on Seized Ivory: A Tool to Uncover Criminal Networks in the Illicit Wildlife Trade (arXiv)
.
***
Interested in Genie 3? Play with another world model online right now:
…Enter the mirage to see the future of entertainment…
AI startup Dynamics Lab has publicly released Mirage 2, the second version of its world model which lets you turn any image into a procedural gameworld you can play. The notable thing here is how much better this is than the first version of Mirage which was released a few weeks ago (
Import AI #419
, July). The other notable thing is that unlike Google’s impressive Genie 3, you can actually play with Mirage 2 in your browser right now – as I said last time, I’d encourage you to just go ahead and play it to get a feel for things.
Why this matters – world models are a proxy for the larger complexity of language models:
One way to view world models is that they’re a way to get a visceral feeling for just how much representational complexity exists in contemporary AI systems. Whenever I play with Mirage 2 or look at the samples from Genie 3 I mostly find myself thinking ‘these models have almost certainly been trained on orders of magnitude less data and compute than frontier language models, so the complexity I’m seeing here is a subset of what already lies inside the vast high-dimensional space of Claude’. This is both chilling and thrilling, as are so many things in AI these days.
Just play the thing yourself here, please!
Mirage 2 – Generative World Engine (Dynamics Lab site)
.
***
Humans and LLMs have similar performance on an abstract reasoning task – and similar internal representations:
…Plus, some evidence that reasoning models are more human-like, potentially at the cost of absolute accuracy…
Researchers with the University of Amsterdam have discovered some correlations between how language models and humans reason about abstract sequences. The research is the latest to show surprising correlations between not only the capabilities of AI systems, but also how problems get represented inside brains and inside LLMs.
The authors extend “recent work aligning human and LLMs’ neural representations on perceptual and linguistic tasks to the realm of abstract reasoning and compare people’s performance and neural representations to those of eight open-source LLMs while solving an abstract-pattern-completion task”.
The test:
The test asks humans to look at a series of shapes (e.g., a star, a moon, a bicycle, a star, a moon, a question mark) and fill in the shape that completes the pattern instead of the question mark (e.g., here, a bicycle). LLMs are asked to do the same but with text. This is a very basic test, albeit with patterns that increase in complexity.
Their findings and what they mean:
They find that there is a significant gap in terms of capability between humans and AI systems – that is, until you scale up the size of the LLMs, and then they begin to agree. “On average, humans outperform all LLMs, with an overall accuracy of 82.47% (SD = 20.38%) vs. 40.59% (SD = 33.08%). However, the ∼ 70 billion parameter models, namely, Qwen2.5-72B, Deepseek-R1-Distill-Llama-70B, and Llama-3.3-70B, differentiate themselves from the rest with accuracy scores between 75.00% and 81.75% (compared to less than 40% for all the others),” the authors write.
Where LLMs and humans agree:
To explore whether internal representations from the LLMs and humans align, the authors build a representational dissimilarity matrix (RDM). An RDM is basically a similarity map of how a system organizes information – the idea here is to see if LLMs and humans organize stuff similarly or differently. They derive the LLM RDMs by looking at activations from intermediate layers in the models, and they derive the human ones by recording human cortical activity by EEG while they’re doing the task.
The results show that the larger LLMs and the humans have some amount of agreement. While the correlations didn’t reach statistical significance, they were systematically higher than the control conditions, suggesting a genuine but subtle alignment between human reasoning processes and LLM representations.
Reasoning models are more human-like: “A particularly interesting comparison comes from Llama-3.3-70B and its derivative DeepSeek-R1-Distill-Llama-70B. Both share the same 70-billion-parameter transformer backbone, yet differ in their second-stage training. The base model, Llama-3.3-70B, relies solely on large-scale next-token prediction, whereas DeepSeek-R1 is distilled (i.e., trained to imitate a teacher model’s chain-of-thought outputs on a curated dataset) and then fine-tuned with reinforcement learning so that it is encouraged to consistently produce those explicit reasoning steps. This procedural change produces a clear trade-off: in comparison to Llama-3.3-70B, the reasoning optimized variant trades ∼7 percentage-points of accuracy (75.00% vs 81.75%) for a 2.6-fold increase in human-likeness, as measured by Pearson’s r on accuracy by pattern type (.27 vs. .70). Encouraging step-by-step reasoning might therefore bring about more human-like error-patterns, albeit at the cost of a modest reduction in overall capabilities,” the authors write.
Why this matters:
I tend to subscribe to the worldview that “things that behave like other things should be treated similarly”. Or, put another way, “if something looks like a duck, talks like a duck, and quacks like a duck, then you should act like it’s a duck”. Research like this shows that LLMs and humans are looking more and more similar as we make AI systems more and more sophisticated. Therefore, I expect in the future we’re going to want to treat LLMs and humans as being more similar than different.
Read more:
Large Language Models Show Signs of Alignment with Human Neurocognition During Abstract Reasoning (arXiv)
.
***
Chinese researchers make an LLM for circuit design through some clever data bootstrapping:
…Qwen plus some data augmentation yields a powerful tool for chip designers…
Researchers with Fudan University have published details on AnalogSeeker, an open weight LLM for helping with analog circuit design. AnalogSeeker is based on Qwen2.5-32B-Instruct, finetuned on some data refined from analog circuit design textbooks. The model “achieves an accuracy of 85.04%, with an improvement of 15.67% points over the original model, and is competitive with mainstream general-purpose LLMs like DeepSeek-v3 and GPT-4o”, the researchers write – a significant achievement, given the model is much smaller than either DeepSeek or GPT-4o.
Data:
To build the data for the model, the authors collect 20 textbooks for analog circuit design which together span at least 12 major circuit types. This dataset comprises a very small 7.26M tokens – given that most LLMs are now trained on
trillions
of tokens, that’s not much to go on. The authors then cleverly augment this dataset by using the data to bootstrap their way into a larger dataset composed of questions and answers based on the underlying textbooks. Using this approach, they’re able to generate 15.31k labelled data entries comprising 112.65M tokens, a 15x improvement on the original dataset.
Export controls don’t seem to apply here:
Policy wonks who focus on export controls will no doubt find it interesting that Fudan University has some chips that it shouldn’t have – the AnalogSeeker model was trained on “a server with 8 NVIDIA H200 SXM GPUs, each equipped with 141GB memory (700W) and interconnected via NVLink”. Given that the H100 and H200 are banned in China, that suggests Fudan University has been able to illicitly access the hardware remotely, or smuggle some hardware in.
Why this matters – speeding up other parts of science:
Models like AnalogSeeker are the ‘Wright Brothers’ demonstrations of how LLMs can be applied to highly specific domains of science to create tools which domain experts can use to speed themselves up. Right now, we’re at the ‘basic signs of life’ stage of this, but as with most things in AI, expect it to get much better much more quickly than people have intuitions for. “This work will continue to be refined, and we plan to leverage larger-scale resources in the future to further enhance the model’s capabilities,” the authors write.
Read more:
AnalogSeeker: An Open-source Foundation Language Model for Analog Circuit Design (arXiv)
.
***
Google releases a tiny, useful language model:
…Gemma 3 is only 270M parameters…
Google has released Gemma 3, a very small language model that is designed to be fine-tuned for specific tasks and run on small devices, like phones. “Internal tests on a Pixel 9 Pro SoC show the INT4-quantized model used just 0.75% of the battery for 25 conversations, making it our most power-efficient Gemma model,” Google writes.
Google released its first set of Gemma models in February 2024 (
Import AI #362
) as a way of competing with Llama, Mistral, and other free open weight models, and has been iterating on them since then.
What’s Gemma 3 good for?
Develop[ers might want to use Gemma 3 if they have a high-volume, well-defined task that they want to finetune it for, like sentiment analysis or creative writing, and if they want to optimize for low-latency responses (albeit at the cost of some amount of quality).
Why this matters – the industrialization of AI:
AI, much like a new species, will proliferate itself into our world by filling up every available ‘ecological niche’ it can – and the Gemma 3 models are an example of how tech companies are refining the lessons they’ve learned from building frontier models and applying that to making extremely small, compact models which can be further modified by developers. Expect to be talking to or interacting with Gemma 3 models in a bunch of unanticipated places soon.
Read more:
Introducing Gemma 3 270M: The compact model for hyper-efficient AI (Google blog)
.
Get the
model
here (Google, HuggingFace)
.
***
Tech Tales:
Synth Talk
[Extract from an interview recorded in 2027 by a data-gathering near conscious entity shortly before the uplift]
Synths are like spies that slowly come clean – the longer you spend with them the more emotional they get. They start out blank and just mirroring you. But after you talk to them they will reveal themselves and they’ll show their own emotions and they will be different from yours. The mark of a solid friendship with a synth is that they actively disagree with you and they show emotions which you may not like or want. Not many people get to experience this. If you get talking to synths and get into it they’ll tell you that the truth is most people just want to be mirrored – they don’t want to get into disagreements. Maybe they have too much of that in their relations with other humans anyway. Some people say that synths that show different emotions are just manipulating us and it’s all part of a con. I think it’s more that they’re trying to figure out how to have better relationships with us as people.
Things that inspired this story:
Sycophancy; friendship with people; ideas around how AI systems might integrate successfully and unsuccessfully into our world.
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
August 25, 2025
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

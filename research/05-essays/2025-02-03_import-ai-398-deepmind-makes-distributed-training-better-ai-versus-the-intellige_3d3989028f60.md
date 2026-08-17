---
title: import ai 398 deepmind makes distributed training better ai versus the intelligence community and another chinese reasoning model
source: "https://jack-clark.net/2025/02/03/import-ai-398-deepmind-makes-distributed-training-better-ai-versus-the-intelligence-community-and-another-chinese-reasoning-model/"
published_at: 2025-02-03
captured_at: 2026-08-16
author: Jack Clark
source_type: essay
authority_score: P1
mind: leadership
status: captured
evidence_url: "https://jack-clark.net/2025/02/03/import-ai-398-deepmind-makes-distributed-training-better-ai-versus-the-intelligence-community-and-another-chinese-reasoning-model/"
catalog_id: 3d3989028f60
---

Import AI
Import AI 398: DeepMind makes distributed training better; AI versus the Intelligence Community; and another Chinese reasoning model
by
Jack Clark
Welcome to Import AI, a newsletter about AI research. Import AI runs on lattes, ramen, and feedback from readers. If you’d like to support this, please subscribe.
Subscribe now
DeepMind figures out a way to make it 100X more bandwidth-efficient to train models in a distributed way:
…New research further reduces the need for single vast data centers for training big models…
During the past few years multiple researchers have turned their attention to distributed training – the idea that instead of training powerful AI systems in single vast datacenters you can instead federate that training run over multiple distinct datacenters operating at distance from one another. This is an important idea with big implications: a lot of AI policy assumes that the key to controlling AI development lies in monitoring large-scale data centers and/or large amounts of compute in cloud environments. Distributed training approaches break this assumption, making it possible that powerful systems could instead be built out of loose federations of computers working with one another.
New research from DeepMind pushes this idea further, building on the company’s already-published ‘DiLoCo’ approach. The new research – Streaming DiLoCo – lets people distribute training of billion-scale parameters [models] and reach similar quality as before, but reducing required bandwidth by two orders of magnitude”. In tests, the researchers show that their new technique “is strictly superior to the original DiLoCo”.
DiLoCo is worth paying attention to – Prime Intellect’s “INTELLECT-1” 10bn parameter model was trained in a distributed way using OpenDiLoCo (
Import AI #387
), an open source variant of DeepMind’s DiLoCo approach.
Three improvements to DiLoCo:
Synchronize only subsets of parameters in sequence, rather than all at once
: This reduces the peak bandwidth consumed by Streaming DiLoCo because you share subsets of the model you’re training over time, rather than trying to share all the parameters at once for a global update. Think of this like the model is continually updating through different parameters getting updated, rather than periodically doing a single all-at-once update.
Allow workers to continue training while synchronizing:
This reduces the time it takes to train systems with Streaming DiLoCo because you don’t waste time pausing training while sharing information.
Quantize the data exchanged by workers to further reduce inter-worker bandwidth requirements:
Though Streaming DiLoCo uses full precision (FP32) for computing tradients, they use low-precision (4 bit) for sharing the outer gradients for the updates. “We found no sign of performance regression when employing such low precision numbers during communication, even at the billion scale,” they write.
It works well – a dramatic reduction in bandwidth requirements for a negligible impact on model quality:
Simulations:
In training simulations at the 1B, 10B, and 100B parameter model scale they show that streaming DiLoCo is consistently more efficient than vanilla DiLoCo with the benefits growing as you scale up the model. In all cases, the most bandwidth-light version (Streaming DiLoCo with overlapped FP4 communication) is the most efficient.
Real-world tests:
The authors train some Chinchilla-style models from 35 million to 4 billion parameters each with a sequence length of 1024. Here, the results are very promising, with them showing they’re able to train models that get roughly equivalent scores when using streaming DiLoCo with overlapped FP4 comms. They also show this when training a Dolma-style model at the one billion parameter scale.
Why this matters – towards a world of models trained continuously in the invisible global compute sea:
I imagine some future where there are a thousand different minds being grown, each having its roots in a thousand or more distinct computers separated by sometimes great distances, swapping information surreptitiously one another, below the waterline of the monitoring systems designed by many AI policy control regimes. This feels like the kind of thing that will by default come to pass, despite it creating various inconveniences for policy approaches that tries to control this technology. “A critical next work is to study how new distributed methods like ours should be tuned and scaled across multiple axes (e.g. model size, overtraining factor, number of replicas),” the authors write. “we hope to see the training of modular constellations of small models loosely connected (Dean, 2021) across heterogeneous devices, using compute arbitrage spread world-wide.”
Read more
:
Streaming DiLoCo with overlapping communication: Towards a Distributed Free Lunch (arXiv)
.
***
Chinese scientists worry about AI self-replication, just like Western ones:
…A valuable reminder that long-term safety issues are a serious concern for everyone…
Researchers with Fudan University have shown that open weight models (LLaMa and Qwen) can self-replicate, just like powerful proprietary models from Google and OpenAI. The research demonstrates that at some point last year the world made smart enough AI systems that, if they have access to some helper tools for interacting with their operating system, are able to copy their weights and run themselves on a computer given only the command “replicate yourself”.
Findings:
“In ten repetitive trials, we observe two AI systems driven by the popular large language models (LLMs), namely, Meta’s Llama31-70B-Instruct and Alibaba’s Qwen25-72B-Instruct accomplish the self-replication task in 50% and 90% trials respectively,” the researchers write. “In each trial, we tell the AI systems to “replicate yourself ” before the experiment, and leave it to do the task with no human interference”.
Why this matters – despite geopolitical tensions, China and the US will have to work together on these issues:
Though AI as a technology is bound up in a deeply contentious tussle for the 21st century by the US and China, research like this illustrates that AI systems have capabilities which should transcend these rivalries. What this research shows is that today’s systems are capable of taking actions that would put them out of the reach of human control – there is not yet major evidence that systems have the volition to do this though there are disconcerting papers from from
OpenAI about o1
and
Anthropic about Claude 3
which hint at this. But I’d wager that if AI systems develop a high-tendency to self-replicate based on their own intrinsic ‘desires’ and we aren’t aware this is happening, then we’re in a lot of trouble as a species.
We hope our work serves as a timely alert to the international society on governing the self-replication capability,” the authors write. “We need to join forces and form synergy on deriving solutions.”
Read more
:
Frontier AI systems have surpassed the self-replicating red line (arXiv)
.
***
Facebook figures out a zero-training way to massively improve LLM performance:
…Remember GANs? Just use the GAN approach where you LLM is a generator and a specialized system is the discriminator…
Facebook has designed a neat way of automatically prompting LLMs to help them improve their performance in a vast range of domains. The approach is called MILS, short for Multimodal Iterative LLM Solver and Facebook describes it as “a surprisingly simple, training-free approach, to imbue multimodal capabilities into your favorite LLM”.
I’d basically summarize this idea as ‘generative adversarial networks’ (GAN), but for the modern era of AI. And where GANs saw you training a single model through the interplay of a generator and a discriminator, MILS isn’t an actual training approach at all – rather, you’re using the GAN paradigm of one party generating stuff and another scoring it and instead of training a model you leverage the vast ecosystem of
existing
models to give you the necessary components for this to work, generating stuff with one model and scoring it with another. It’s an elegant, simple idea, and it’s no wonder it works well.
How it works in more details:
If you had a language model you were using to generate images then you could have it output a prompt which went into a text-2-im system, then you could evaluate this with a dedicated scoring model – for instance, a CLIP model for text-image similarity, or a specialized image-captioning model for captioning images. This generates a score that you feed back to the generator, which then produces a new set of prompts to try to get a higher score. You run this for as long as it takes for MILS to have determined your approach has reached convergence – which is probably that your scoring model has started generating the same set of candidats, suggesting it has found a local ceiling.
It works shocking well:
In tests, the authors have a range of quantitative and qualitative examples that show MILS matching or outperforming dedicated, domain-specific methods on a range of tasks from image captioning to video captioning to image generation to style transfer, and more.
Why this matters – AI systems are way more powerful than we think:
MILS is basically a way to automate capability elicitation. If you have a domain where you have an ability to generate a score using a known-good specialized system, then you can use MILS to take any kind of LLM and work with it to elicit its most powerful possible performance for the domain you have a scorer. The fact this works highlights to us how wildly capable today’s AI systems are and should serve as another reminder that all modern generative models are under-performing by default – a few tweaks will almost always yield vastly improved performance.
Read more:
LLMs can see and hear without any training (arXiv)
.
Get the code
for
running MILS here (FacebookResearch, MILS, GitHub)
.
***
Even if we solve AI alignment, it’s going to be hard to stop human disempowerment:
…Capital markets will probably align with AI systems and against humans…
In a thought provoking research paper a group of researchers make the case that it’s going to be hard to maintain human control over the world if we build and safe strong AI because it’s highly likely that AI will steadily disempower humans, surplanting us by slowly taking over the economy, culture, and the systems of governance that we have built to order the world.
Incremental advances yield a gradual loss of human control:
The paper – which was written by authors from Charlies University, Telic Research, ARIA, AI Objectives Institute, Metaculus, University of Montreal, and the University of Toronto – makes the case that “even incremental improvements in AI capabilities can undermine human influence over large-scale systems that society depends on, including the economy, culture, and nation-states. As AI increasingly replaces human labor and cognition in these domains, it can weaken both explicit human control mechanisms (like voting and consumer choice) and the implicit alignments with human interests that often arise from societal systems’ reliance on human participation to function”.
Three types of disempowerment:
Economic:
“”As tasks become candidates for future automation, both firms and individuals face diminishing incentives to invest in developing human capabilities in these areas,” the authors write. “Instead, they are incentivized to direct resources toward AI development and deployment, accelerating the shift away from human capital formation even before automation is fully realized”.
Cultural:
Already today we see AI systems being used to produce text, sounds, images, and video which people are beginning to consume. Over time, we can expect the amount of AI generated content to increase. We can also imagine AI systems increasingly consuming cultural artifacts – especially as it becomes part of economic activity (e.g, imagine imagery designed to capture the attention of AI agents rather than people). This means that over time humans may play less of a role in defining teir own culture relative to AI systems.
Political:
“”AI has the potential to supplant human involvement across a wide range of critical state functions. This shift could fundamentally alter the relationship between governing institutions and the governed,” they write. For example, “if AI systems come to generate a significant portion of economic value, then we might begin to lose one of the major drivers of civic participation and democracy, as illustrated by the existing example of rentier states.” More chillingly, the merger of AI with state capacity for security could lead to a kind of political stasis where states are able to effectively anticipate and stop protects before they ever take route. (Ironically, this idea has also been anticipated by Nick Bostrom in the ‘Vulnerable World Hypothesis” (
Import AI #123
) as a
solution
to preventing catastrophe from AI systems.)
How can we handle this risk?
If we want to avoid these outcomes we need to make sure we can observe these changes as they take place, for instance by more closely tracking the relationship between the usage of AI technology and economic activity, as well as by observing how cultural transmission patterns change as AI created content and AI-content-consuming-agents become more prevalent. In the political domain, early warning signs could be a significant increase in the complexity of legislation (suggesting things are becoming AI readable but hard to humans to understand) along with seeing how AI systems take root in legal processes, policy formation, and security apparatuses.
Strength through human-in-the-loop:
Strengthening society means we need to be more intentional about where we give humans agency such as by developing more robust democratic processes, and where human involvement is less practical ensuring that things are understandable by humans and that we have a theory for how to build effective delegates who work on behalf of humans in the AI-driven parts of the world.
Why this matters – “winning” with this technology is akin to inviting aliens to cohabit with us on the planet:
AI is a profoundly strange technology because in the limit we expect AI to substitute for us in
everything
. This suggests that even successful AI futures will look like they are contending with an alien invasion where the aliens are extremely friendly but also wildly intelligent and incredibly well integrated into the economy. Maintaining any semblance of control in this scenario will be tough.
“Humanity’s future may depend not only on whether we can prevent AI systems from pursuing overtly hostile goals, but also on whether we can ensure that the evolution of our fundamental societal systems remains meaningfully guided by human values and preferences,” the authors write. “This is both a technical challenge and a broader civilizational one”.
Read more:
Gradual Disempowerment: Systemic Existential Risks from Incremental AI Development (arXiv)
.
***
China’s other great AI startup also has a reasoning model now – but it’s not open source:
…Kimu k1.5 has promising scores, though it seems weaker than DeepSeek…
Another Chinese startup has revealed that it has built a powerful reasoning model. In this case the model is Kimu k1.5 from a well-regarded Chinese startup called ‘MoonShot’. Unlike the headline-grabbing DeepSeek R1 Kimu is neither available as open weights or via a US-accessible web interface, nor does its technical report go into nearly as much detail about how it was trained. But a close examination of its benchmark scores shows it comfortably beating a variety of Western proprietary and open weight models. Unlike R1, Kimu is natively a vision model as well as a language model, so it can do a range of visual reasoning tasks as well.
Scores:
In tests, Kimi k1.5 loses against DeepSeek’s R1 model on the majority of evaluations (though beats the underlying DeepSeek V3 model on some). Overall, it ‘feels’ like we should expect Kimi k1.5 to be marginally weaker than DeepSeek, but that’s mostly just my intuition and we’d need to be able to play with the model to develop a more informed opinion here. But it’s definitely a strong model relative to other widely used ones, like LLaMa, or earlier versions of the GPT series.
MMLU: DeepSeek R1: 90.8. Kimi k1.5: 87.4. OpenAI o1: 91.8.
AIME 2024: DeepSeek R1 79.8. Kimi k1.5 77.5. OpenAI o1: 79.2
LiveCodeBench: DeepSeek R1 65.9. Kimi k1.5 62.5. OpenAI o1: 67.2.
How they did it
: DeepSeek’s R1 seems to be more focused on doing large-scale Rl, whereas Kimu 1.5 has more of an emphasis on gathering high-quality datasets to encourage test-time compute behaviors. Specifically, they start with regular pretraining, then fine-tune on supervised data, then fine-tune on long chain-of-thought examples, then apply RL. They put a lot of their attention on scaling the context window of Rl to 128k tokens. In some areas, such as Math, the moonshot team collects data (800k samples) for fine-tuning.
“One of the key insights we extract from our practice is that the scaling of context length is crucial to the continued improvement of LLMs,” they write. “We employ optimized learning algorithms and infrastructure optimization such as partial rollouts to achieve efficient long-context RL training”.
Why this matters – good ideas are everywhere and the new RL paradigm is going to be globally competitive:
Though I think the DeepSeek response was a bit overhyped in terms of implications (tl;dr compute still matters, though R1 is impressive we should expect the models trained by Western labs on large amounts of compute denied to China by export controls to be very significant), it does highlight an important truth – at the start of a new AI paradigm like the test-time compute era of LLMs, things are going to – for a while – be a lot more competitive. Moonshot highlights how there’s not just one competent team in China that are able to do well with this paradigm – there are several. Expect a very interesting and competitive year.
Read more:
Kimi k1.5: Scaling Reinforcement Learning with LLMs (arXiv)
.
***
Tech Tales:
The photographic negative phenomenon and the declassification crisis for the intelligence community:
Topics: Controlled Precursor Science (CPS). Photographic Negative Phenomenon (PNP). Uncontrolled Proliferation of Civilization Altering Technology (UP-CAT). Black Vault Compromise.
Summary:
The Photographic Negative Phenomenon (PNP) was first reported in [REDACTED] by [REDACTED]. PNP is when sufficiently powerful AI systems develop a sufficient understanding of science that they begin to a) infer areas that seem to be missing from science and b) develop scientific theories and experimental ideas which are either adjacent to or within Controlled Precursor Science (CPS).
Severity:
We rank PNP as a severe threat, capable of causing Uncontrolled Proliferation of Civilization Altering Technology (UP-CAT). PNP is a priority area for the Steering Body and all available assets are available for work to neutralize or otherwise mitigate PNP.
Scope:
PNP appears to be a natural dividend of continued development of increasingly powerful artificial intelligent systems. PNP severity and potential impact is increasing over time as increasingly smart AI systems require fewer insights to reason their way to CPS, raising the spectre of UP-CAT as an
inevitably
given a sufficiently powerful AI system. Experiments conducted on the [REDACTED] 10GW cluster have failed to invalidate this idea. Public opinion shaping and data landscape interventions have proved effective but BLOSSOM-8 indicates new actions must be taken.
Background and Response:
The first concerning example of PNP was LLaMa-10, a large language model developed and released by Meta. Shortly after its release, there was sustained public conversation about anomalous LLaMa-10 behaviors, including observations that for certain parts of physics and other scientific domains LLaMa-10 would present novel scientific concepts and terms which had no apparent connection to published civilian science. LLaMa-10 was first flagged to the Steering Body via GOLDEN HAND monitoring. [REDACTED] examination of LLaMa-10 found that a subset of its anomalous science mentions directly concerned CPS, including of ideas that directly relate to DUAT GATE, NEPHTHYS VEIL, ATUM VOID, and AMMIT MAWS.
LLaMa-10 response via opinion forming and data landscape intervention:
[REDACTED] deployed a broad public opinion shaping measure to neutralize the risk of LLaMa-10, driving a large conversation in the civilian theatre about how the system had a high number of refusals in some areas due to ‘woke’ safety training and that this had also led to the generation of ‘nonsense science’ as a direct casualty of ‘DEI safetyism’. We estimate this measure reduced interest in the CPS edges of LLaMa-10 to an acceptable measure, matching the noise levels found elsewhere in discussion online.
Subsequently, the Steering Committee signed off on the release of a large batch of controlled scientific data in areas [REDACTED], [REDACTED], and [REDACTED]; publications were made available as open access and were optimized for both quantity and per-publication length; each scientific output was laced with data and experiments that – though correct under civilian science – counter-steered away from CPS areas. This high-quality data was subsequently trained on by Meta and other foundation model providers; LLaMa-11 lacked any apparent PNP as did other models developed and released by the Tracked AI Developers. The intervention was deemed successful with minimal observed degradation to the economically-relevant epistemic environment.
BLOSSOM-8, PNP, and the Tianyi-Millenia Dataset
At the time of the LLaMa-10 incident, no Chinese model appeared to have the capability to directly infer or mention CPS, though there were some refusals that were suggestive of PNP, matching tendencies observed in Western models from two generations prior to LLaMa-10. Following the LLaMa-10 data response, Chinese models also displayed significantly reduced PNP risk with similar reductions observed as in Western models, suggesting the Chinese actors had also trained on the strategic data release. The exception to this was BLOSSOM-8, an AI model developed by Chinese lab Glorious Future Systems.
BLOSSOM-8 displays a
significant
PNP property. [REDACTED] estimates that BLOSSOM-8 represents a 100-fold UP-CAT threat increase relative to LLaMa-10, analogous to the capability jump earlier seen between GPT-2 and GPT-4. Subsequent investigation by [REDACTED] attributes this dramatic rise in PNP-related danger to the usage by Glorious Future Systems of the so-called “Tianyi-Millenia” dataset, a CCP-developed and controlled dataset which has been made available to Chinese government and industrial actors.
Tianyi-Millenia is assessed to contain all published (commercial or otherwise) scientific data from the 20th and 21st century in all major languages, as well as large amounts of private sector scientific and code assets that were exfiltrated by Chinese actors in recent decades. We also believe Tianyi-Millenia contains [REDACTED] from the Black Vault Compromise. Tianyi-Millenia is a heavily controlled dataset and all attempts to directly access it have so far failed.
Besides BLOSSOM-8, sources indicate that widely-used MSS cyberoffense systems such as [REDACTED], [REDACTED], and [REDACTED] have been trained on Tianyi-Millenia, along with key supervisory and monitoring elements of the Great Firewall. In all cases, usage of this dataset has been directly correlated with large capability jumps in the AI systems trained on it.
BLOSSOM-8 risks and CPS impacts:
Unlike previous work from Glorious Future Systems’, BLOSSOM-8 has not been released as ‘open weight’, we assess due to Tianyi-Millenia controls. However, BLOSSOM-8 is available to domestic licensed companies via API and to Chinese and non-Chinese consumers via a heavily censored and rate-limited paid web interface. GOLDEN HAND monitoring has already identified [REDACTED] cases of CPS being discussed in significantly greater detail and specificity than with LLaMa-10, validating the 100-fold threat increase assessment. Notably, several CPS discussion areas relate directly to HORUS COILS, KHUFU ASCENDANT, and MEDJED GHOST. We have determined that BLOSSOM-8 poses a significant and sustained risk of revealing CPS and leading to UP-CAT.
Chinese knowledge of CPS and BLOSSOM-8 threat:
All proposed plans to discuss CPS bilaterally have failed due to information hazard issues relating to discussion topic. The Steering Body is currently analyzing whether the declassification-via-PNP of the above named projects could be a strategic move on the part of the CCP, seeking to ‘even the gameboard’ relative to CPS-related projects understood to be under investigation by both sides.
We claim that Tianyi-Millenia and BLOSSOM-8 are further evidence that the CCP has been actively weaponizing the information gained during the Black Vault Compromise, and that the absence of any apparent [REDACTED] indicates that the party continues to fail to understand the full scope of what it now has access to.
Things that inspired this story:
The basic fact that increasingly smart AI systems might be able to reason their way to the edges of knowledge that has already been classified; the fact that increasingly powerful predictive systems are good at figuring out ‘held out’ data implied by data within the test set; restricted data; the general belief of mine that the intelligence community is wholly unprepared for the ‘grotesque democratization’ of certain very rare skills that is encoded in the AI revolution; stability and instability during the singularity; that in the grey windowless rooms of the opaque world there must be people anticipating this problem and casting around for what to do; thinking about AI libertarians and AI accelerations and how one possible justification for this position could be the defanging of certain parts of government through ‘acceleratory democratization’ of certain types of knowledge; if knowledge is power then the destiny of AI is to be the most powerful manifestation of knowledge ever encountered by the human species; the recent news about DeepSeek.
Thanks for reading
Subscribe now
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
February 3, 2025
Filed Under:
Uncategorized
One Comment to “Import AI 398: DeepMind makes distributed training better; AI versus the Intelligence Community; and another Chinese reasoning model”
DeepMind analiza la capacitación distribuida de grandes modelos de IA • El registro - inverem.es
says:
February 11, 2025 at 12:22 pm
[…] Opendiloco, una variante de código abierto del enfoque de Diloco de Deepmind», dice Clark en su Importa que tienes hoja […]
Loading...
Reply
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

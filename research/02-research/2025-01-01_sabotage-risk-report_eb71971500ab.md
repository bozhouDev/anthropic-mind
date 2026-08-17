---
title: sabotage risk report
source: "https://alignment.anthropic.com/2025/sabotage-risk-report/"
published_at: 2025-01-01
captured_at: 2026-08-16
author: Anthropic Alignment Science
source_type: research
authority_score: P1
mind: institutional
status: captured
evidence_url: "https://alignment.anthropic.com/2025/sabotage-risk-report/"
catalog_id: eb71971500ab
---

Alignment Science Blog
Anthropic's Pilot Sabotage Risk Report
Main Report:
Samuel R. Bowman, Misha Wagner, Fabien Roger, and Holden
                    Karnofsky
Internal Review:
Daniel M. Ziegler and Evan Hubinger
October 28, 2025
tl;dr
As practice for potential future Responsible Scaling Policy
                    obligations,
                    we're releasing a
report on misalignment risk posed by
                        our
                        deployed models as of Summer 2025
. We
                    conclude
                    that there is very low, but not fully negligible, risk of misaligned autonomous actions that
                    substantially
                    contribute to later catastrophic outcomes. We also release two reviews of this report: an
internal
                        review
and an
independent review
by
METR
.
Our
Responsible
                Scaling
                Policy
has so far come into force primarily to address risks related to high-stakes human
            misuse.
            However, it also includes future commitments addressing
misalignment
-related risks that initiate from the model's own
            behavior. For future models that pass a capability threshold we have not yet reached, it commits us
            to
            developing
an affirmative case that (1) identifies the most immediate and relevant risks from models pursuing
            misaligned goals and (2) explains how we have mitigated these risks to acceptable levels. The
            affirmative case will describe, as relevant, evidence on model capabilities; evidence on AI
            alignment;
            mitigations (such as monitoring and other safeguards); and our overall reasoning.
Affirmative cases of this kind are uncharted territory for the field: While we have published
sketches
of arguments we might
            use, we
            have never prepared a complete affirmative case of this kind, and are not aware of any examples of
            such
            documents from other frontier AI developers.
Today, in the spirit of showing our work, we are releasing a report that is meant to represent
            roughly such
            an affirmative case, addressing misalignment risks from
present-day
AI systems and deployments, as an output from a pilot exercise. This exercise was meant to give us early
            visibility into
            issues
            that might arise in preparing such a case when one becomes necessary under our policy, to spot
            present-day
            gaps in our safety strategy for model autonomy, and to pilot a process for internal and external
            review that
            we could use to validate such a load-bearing case in the future.
The language we use to describe this report differs slightly from the language in the current responsible
            scaling
            policy: We
            focus on
sabotage
as the broad category of misaligned
            behaviors
            that (unlike, for example, hallucination) poses distinct emerging risks at high capability levels
            that can
            be difficult to respond to without significant preparation. We title the document a
risk report
to emphasize that we are not currently arguing
            that we
            have achieved a specific pre-determined level of risk (as might be implied by
affirmative case for
                safety
or
safety case
), but rather laying out what we see as the
            existing
            level of risk.
For this pilot exercise, we aimed to reach a complete and clear (if not highly polished) assessment, focusing
            on this goal at the expense of speed. As a result,
            the
            report
            captures the risks as they existed in
summer
of this year,
            focusing
            primarily on risks involving the behavior of Claude Opus 4, which was our most capable model when we
            started
            to draft this report. We provide only more limited discussion of subsequent models.
Our primary takeaways are:
When reviewing Claude Opus 4's capabilities, its behavioral traits, and the formal and informal
            safeguards
            that are in place to limit its behavior, we conclude that there is a very low, but not completely
            negligible, risk of misaligned autonomous actions that contribute significantly to later
            catastrophic
            outcomes, abbreviated as
sabotage
risk. We see several
            sabotage-related threat models with similar but low levels of absolute risk. We are moderately
            confident
            that Opus 4 does not have consistent, coherent dangerous goals, and that it does not have the
            capabilities
            needed to reliably execute complex sabotage strategies while avoiding detection. These general
            points
            provide significant reassurance regarding most salient pathways to sabotage, although we do not find
            them
            sufficient on their own, and we accordingly provide a more individualized analysis of the most
            salient
            pathways.
This exercise included multiple rounds of revision in cooperation with both our internal Alignment
            Stress-Testing team and the independent AI safety and evaluation nonprofit
METR
.
            Both parties had access to additional evidence beyond what is
            presented in the report, and both prepared written reviews reflecting their degree of confidence in
            the
            report's conclusions. Both reviews ultimately endorse our assessment of the level of risk, though
            raise doubts about argumentation and evidence in some places and suggest improvements for future such
            reports.
We have learned a great deal from both the drafting process and our work with both review teams. This
            has led
            us to substantially revise our threat models and supported changes to our alignment-related
            practices,
            including changes to model training oriented toward improving the faithfulness and monitorability of
            model
            reasoning. This work is nonetheless very much a pilot, and we expect that future
            safety assessments along these lines will include both additional concrete safety measures and
            further
            refined argumentation.
The core report team does not endorse every concern
            raised in the two reviews, and we believe that there are some disagreements with the reviewing teams that we
            could have productively
            resolved
            with more discussion and more time. We
do
, though, largely agree with the
            reviews, and see many
            ways
            that the report and our safeguards
            could be improved. We note some of these in an appendix.
            Given the timeliness of this issue, we find it prudent to release our work as it
            currently exists rather than delaying to await consensus on potentially thorny empirical and
            conceptual
            questions.
You can read the report here:
Anthropic's Summer 2025 Pilot
                    Sabotage Risk
                    Report
You can read the internal review from our Alignment Stress-Testing Team here:
Alignment
                    Stress-Testing Review
You can read the independent review from METR here:
METR's
                    Review

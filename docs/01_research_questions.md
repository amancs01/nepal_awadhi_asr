# Research Questions

STATUS: PHASE 0 — RESEARCH VALIDATION

The research questions are not frozen. Each candidate question requires evidence from literature review, dataset audit, model inventory, and feasibility analysis before it can become part of the final study design.

## Current Candidate Primary Question

How well do ASR systems developed using existing Awadhi resources generalize to Awadhi spoken in Nepal under reasonably comparable evaluation conditions?

STATUS: NOT FROZEN

Evidence required before freezing:

- Verified inventory of existing Awadhi ASR systems and datasets.
- Evidence about whether existing Awadhi resources are Indian Awadhi, Nepal-Awadhi, mixed, or unclear.
- Documentation of speaker origin, recording region, speech style, audio quality, transcription conventions, and licensing.
- A feasible plan for comparable evaluation conditions.

## Current Candidate Secondary Question

When only limited Nepal-Awadhi speech is available, how do Hindi, Nepali and Hindi+Nepali donor strategies affect Nepal-Awadhi ASR under controlled donor-data budgets?

STATUS: NOT FROZEN

Evidence required before freezing:

- Prior work on donor-language selection for low-resource ASR.
- Evidence that Hindi and Nepali are plausible donor languages for the target setting.
- Candidate donor datasets with comparable hours, quality, speech style, transcription quality, and licensing.
- A controlled training and evaluation design that separates donor effects from model or data confounds.

## Current Candidate Analysis Question

Do ASR systems systematically replace Nepal-Awadhi lexical or morphological forms with Hindi or Nepali forms, and does donor language influence this behavior?

STATUS: NOT FROZEN

Evidence required before freezing:

- Prior work on language-fidelity, normalization, code-switching, dialect normalization, or dominant-language substitution errors.
- A defensible annotation scheme for distinguishing Awadhi, Hindi, and Nepali forms.
- A conservative text-normalization plan that does not erase linguistically meaningful differences.
- Evidence that enough target speech exists to measure the behavior reliably.

## Additional Open Questions

- UNKNOWN: Has cross-border Awadhi ASR already been studied?
- UNKNOWN: Has Hindi versus Nepali transfer specifically for Nepal-Awadhi already been studied?
- UNKNOWN: Has read versus spontaneous Nepal-Awadhi ASR been evaluated?
- UNKNOWN: Would approximately 5-10 hours of Nepal-Awadhi support valid target-data scaling experiments?

## Phase 0D Sociolinguistic Foundation Notes

The research questions remain STATUS: NOT FROZEN.

The revised Phase 0D pass uses directly verified facts from Thakur and Yadav (2013). The report documents five Nepal-Awadhi survey locations, a 210-word lexical comparison, approximately 78%-89% lexical similarity across survey points, and mutual intelligibility across the surveyed varieties. This supports preserving regional metadata, but it does not support treating Nepal-Awadhi as a set of strongly mutually unintelligible dialects.

The primary question should continue to require "reasonably comparable evaluation conditions" and should explicitly require district/region metadata for Nepal-Awadhi. If future speech comes from only one district, the question should be narrowed to that locality rather than framed as Nepal-Awadhi broadly.

The Hindi/Nepali contact premise is now HIGH-confidence at the sociolinguistic-contact level: Thakur and Yadav report Nepali knowledge among main respondents at 70% male / 33% female and Hindi knowledge at 83% male / 47% female, with child language knowledge linked to Nepali schooling/towns and Hindi markets/India/films/television. This does not establish that either language is a good ASR donor.

The analysis question should not assume code-switching is common. It should remain focused on testing whether substitution or normalization patterns occur, with the definition postponed until a defensible annotation scheme is created.

## Final Phase 0 research-question gate

- RQ1: How well do existing ASR systems recognize Nepal-Awadhi speech? STATUS: PLAUSIBLE, not frozen. Baseline models exist, but a valid speaker-disjoint Nepal-Awadhi evaluation set is still required.
- RQ2: Under controlled conditions, does Hindi or Nepal-origin Nepali donor data produce greater improvement in Nepal-Awadhi ASR? STATUS: NEEDS REVISION / POSTPONE, not frozen. The donor comparison is meaningful, but no perfect matched Hindi vs Nepal-origin Nepali donor pair has been verified.
- RQ3: What kinds of language-fidelity errors occur when ASR systems recognize Nepal-Awadhi, particularly possible Hindi/Nepali normalization or substitution? STATUS: PLAUSIBLE, not frozen. Requires a defensible annotation protocol and should not assume frequent code-switching.

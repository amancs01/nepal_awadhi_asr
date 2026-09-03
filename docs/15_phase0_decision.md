# Phase 0 Decision

## What we know

- Existing Awadhi ASR/dataset work exists, including SpeeD-IA, VAANI-related studies, Dialect Matters/DonorRank-style donor-transfer research, and Sood et al. 2025.
- SpeeD-IA Awadhi is documented as Indian Awadhi from Pratapgarh, Uttar Pradesh, with 10 Awadhi speakers and 04:46:30 total Awadhi audio.
- VAANI reports Awadhi within Indian district coverage, with 8.85h Awadhi audio and about 0.27-0.28h transcribed Awadhi in audited release summaries.
- No Nepal-origin Awadhi speech corpus has been identified in our audited sources to date. This is not a claim that none exists.
- Thakur and Yadav (2013) provide primary sociolinguistic evidence for Nepal-Awadhi across five sites: Tenuhawa/Rupandehi, Jamuni-Maharajgunj/Kapilvastu, Thandeukhuri-Gadhwa/Dang, Tribhuvan Chowk-Nepalgunj/Banke, and Gulariya/Bardiya.
- LinSuN lexical comparison used a 210-word list and reported approximately 78%-89% lexical similarity across the five Awadhi survey points. The report concludes that observed variation does not appear to hinder mutual intelligibility.
- Hindi and Nepali are both HIGH-confidence sociolinguistic contact languages for Nepal-Awadhi, based on Thakur and Yadav's reported language knowledge and domains of exposure.
- Strong ASR baseline models exist, including Whisper, SraVaani, MMS, IndicConformer, and Sarvam-style commercial systems. Controlled donor-transfer is better served by w2v-BERT 2.0 or a verified neutral IndicWav2Vec-style base.

## What remains uncertain

- Whether any private, institutional, religious-media, or fieldwork Nepal-Awadhi recordings can be ethically and legally used for ASR.
- Whether FLEURS `ne_np` or Common Voice `ne-NP` contributors are Nepal-origin Nepali speakers; locale labels alone are insufficient.
- Whether OpenSLR SLR54 provides enough provenance beyond native-speaker/user IDs for the donor question.
- Whether the Nepali Spoken Corpus can be accessed, subset, and matched legally and methodologically against Hindi donor data.
- Whether 5-10 hours is sufficient for adaptation, target scaling, or donor-transfer conclusions.
- Whether code-switching is common in Nepal-Awadhi speech; multilingualism evidence does not prove utterance-level code-switching frequency.

## Research questions

| Question | Phase 0 decision | Notes |
| --- | --- | --- |
| RQ1: How well do existing ASR systems recognize Nepal-Awadhi speech? | PLAUSIBLE | Defensible once a properly transcribed, speaker-disjoint Nepal-Awadhi test set exists. |
| RQ2: Under controlled conditions, does Hindi or Nepal-origin Nepali donor data produce greater improvement in Nepal-Awadhi ASR? | NEEDS REVISION / POSTPONE | Donor resources are promising but no perfect matched Hindi vs Nepal-origin Nepali pair has been verified. |
| RQ3: What kinds of language-fidelity errors occur when ASR systems recognize Nepal-Awadhi, particularly possible Hindi/Nepali normalization or substitution? | PLAUSIBLE | Requires an annotation protocol and should begin with sampled/manual analysis, not an invented metric. |

The questions are not frozen. RQ1 is the strongest immediate path; RQ2 should be treated as conditional on donor-matchability evidence; RQ3 is analytically valuable but method-dependent.

## Minimum defensible experiment

1. Build or identify a small, ethically sourced, speaker-disjoint Nepal-Awadhi evaluation set with district/locality, speech style, recording condition, speaker ID, and conservative transcription metadata.
2. Run zero-shot inference using 2-3 external practical baselines, likely Whisper medium/large-v3, SraVaani if access/support is confirmed, and one open Indic/multilingual baseline.
3. Evaluate WER/CER under documented normalization policies, including a conservative policy that does not erase Awadhi/Hindi/Nepali distinctions.
4. Perform a small manual language-fidelity error analysis on sampled outputs if RQ3 remains active.

This minimum path answers practical recognition feasibility. It does not answer causal donor-transfer effects.

## Data requirements

- Nepal-Awadhi test data must be speaker-disjoint from any adaptation data.
- Metadata must preserve district/locality, speaker ID, speech style, recording condition, and contact-language profile without unnecessary personal identifying information.
- One-region sampling must be reported as one-region evidence only.
- Donor data for RQ2 must be matched by hours, speakers, speech style, domain, recording condition, transcript quality, script/normalization, license, and split policy.

## Model requirements

- External baselines may use strong pretrained ASR systems even if exposure is opaque, as long as results are interpreted practically.
- Controlled donor-transfer experiments should use one base checkpoint and identical fine-tuning/decoding settings across donor conditions.
- Large multilingual systems should not be used to make causal donor-language claims unless prior exposure and downstream conditions are carefully bounded.

## Major threats to validity

- Treating Indian Awadhi and Nepal-Awadhi as comparable when speech style, region, recording quality, speaker demographics, content, or transcription conventions differ.
- Treating `ne_np` or `ne-NP` as proof of Nepal-origin Nepali speakers.
- Comparing Hindi and Nepali donor datasets that differ in channel, style, domain, transcript quality, or speaker diversity.
- Interpreting multilingualism as code-switching frequency.
- Claiming donor-language causality when base models already have uncontrolled Hindi/Nepali/Awadhi exposure.
- Using aggressive normalization that erases meaningful Awadhi/Hindi/Nepali distinctions.

## GO / REVISE / POSTPONE decision

GO WITH CONTROLS.

Proceed out of Phase 0 into manual research and actual project execution, but revise the near-term plan:

- GO for RQ1-oriented practical zero-shot evaluation after a valid Nepal-Awadhi test set exists.
- GO cautiously for RQ3 as sampled/manual language-fidelity analysis after outputs exist and annotation rules are defined.
- POSTPONE RQ2 donor-transfer experiments until donor datasets are matched or a small Nepal-origin Nepali donor set is ethically justified and approved.

## What must NOT be claimed

- Do not claim this is the first Nepal-Awadhi corpus or first Nepal-Awadhi ASR study.
- Do not claim no Nepal-Awadhi corpus exists; say "not identified in our audited sources".
- Do not claim FLEURS `ne_np` or Common Voice `ne-NP` are Nepal-origin Nepali based only on locale labels.
- Do not claim Hindi or Nepali is the better ASR donor.
- Do not claim code-switching is common without measured speech evidence.
- Do not claim 5-10 hours is sufficient.
- Do not claim one district represents all Nepal-Awadhi.
- Do not claim donor-language causality when donor datasets differ substantially.

## Next phase

The next phase should be MANUAL RESEARCH + ACTUAL PROJECT EXECUTION, not another long Codex literature audit.

Manual next steps:

1. Obtain or inspect full metadata/access terms for the Nepali Spoken Corpus and OpenSLR SLR54 without downloading large audio unnecessarily.
2. Contact or inspect LinSuN/CDL/TU resources for any existing Nepal-Awadhi audio or field materials.
3. Draft ethics/consent and metadata protocols for a possible small Nepal-Awadhi evaluation set.
4. Decide whether RQ2 is postponed or redesigned around a demonstrably matched donor pair.

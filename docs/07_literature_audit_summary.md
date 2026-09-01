# Literature Audit Summary

STATUS: PHASE 0 — RESEARCH VALIDATION

## Strongly Established

- Awadhi speech resources already exist in Indian data. Kumar et al. (2022) report SpeeD-IA with Awadhi, Bhojpuri, Braj, and Magahi: https://www.isca-archive.org/s4sg_2022/kumar22_s4sg.html.
- SpeeD-IA Awadhi is reported from Pratapgarh, Uttar Pradesh, not Nepal-Awadhi, with 04:46:30 of Awadhi speech in the 2022 paper PDF: https://www.isca-archive.org/s4sg_2022/kumar22_s4sg.pdf.
- Awadhi ASR has already been evaluated. Kumar et al. (2022) report Hindi STT and Kaldi baselines; Sood et al. (2025) report Google STT and fine-tuned Whisper-Medium results for Awadhi: https://aclanthology.org/2025.wat-1.5/.
- Awadhi has already been included in VAANI-based cross-lingual transfer and donor-selection work: https://arxiv.org/abs/2601.04373 and https://arxiv.org/abs/2608.11441.

## Likely But Not Fully Established

- Dialectal fine-tuning can outperform larger standardized-language fine-tuning for some Indic dialectal targets, based on Dhasmana et al. (2026). Generalizing this to Nepal-Awadhi requires direct evidence.
- Language-modeling or decoding choices may pressure outputs toward standardized written forms, based on Sharma et al. (2026). Whether this appears as Hindi/Nepali normalization in Nepal-Awadhi is unknown.
- Dialect gaps in ASR are a broad, documented issue, based on Kantharuban et al. (2023), but that paper still needs full inspection for South Asian details.

## Still Unknown

- Whether Nepal-Awadhi ASR has been studied.
- Whether a Nepal-Awadhi speech corpus exists.
- Whether existing Awadhi data includes Nepal-origin speakers.
- Whether Hindi and Nepali have been compared as donors for Nepal-Awadhi.
- Whether Indian Awadhi versus Nepal-Awadhi ASR robustness has been directly tested.
- Whether a 5-10 hour Nepal-Awadhi dataset would support the intended comparisons.

## Proposal Assumptions That Appear Wrong

- Any broad assumption that Awadhi ASR has not been studied is wrong.
- Any broad assumption that an Awadhi speech corpus does not exist is wrong.
- Any broad assumption that donor-language selection involving Awadhi has not been attempted is likely wrong because DonorRank includes Awadhi.

## Proposal Assumptions That Remain Plausible

- Nepal-Awadhi ASR may remain under-studied, but this is not proven.
- A controlled India-Awadhi versus Nepal-Awadhi robustness study may remain a gap.
- Hindi versus Nepali donor comparison for Nepal-Awadhi may remain a gap.
- Dominant-language normalization toward Hindi or Nepali may be measurable, but the evaluation definition is not yet established.

## Highest-Risk Novelty Overlaps

1. Dhasmana, Srivastava, and Chiang (2026), "DonorRank", because it directly studies donor-language selection and includes Awadhi.
2. Dhasmana, Srivastava, and Chiang (2026), "Dialect Matters", because it directly studies Indic dialect ASR transfer, includes Awadhi, and quantifies bias toward Hindi in Garhwali.
3. Sood, Rajput, and Akhtar (2025), because it fine-tunes Whisper-Medium and reports Awadhi WER in a Hindi Belt dialect speech-to-speech pipeline.

## Candidate Remaining Gap

A cautious remaining gap is: controlled evaluation of ASR robustness and donor-language transfer for Awadhi spoken in Nepal, especially comparing Hindi, Nepali, and Hindi+Nepali donor strategies while separating geography, speech style, recording condition, transcription practice, and text normalization.

This gap is provisional. It must be tested through a dataset audit and broader literature search before it can become a claim.

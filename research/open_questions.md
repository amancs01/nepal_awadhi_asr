# Open Questions

STATUS: PHASE 0 — RESEARCH VALIDATION

## Answered Or Partially Answered In Phase 0A/0B

- ANSWERED: Awadhi speech datasets exist. Kumar et al. (2022) report SpeeD-IA with Awadhi from Pratapgarh, Uttar Pradesh.
- ANSWERED: Awadhi ASR has already been studied. Kumar et al. (2022), Sood et al. (2025), and Dhasmana et al. (2026) include Awadhi ASR-related evaluation.
- ANSWERED: Awadhi appears in donor-language selection studies. DonorRank includes Awadhi as a VAANI-D target.
- ANSWERED FOR AUDITED SOURCES: No Nepal-origin Awadhi speech has yet been identified in SpeeD-IA or public VAANI summaries.
- ANSWERED FOR SPEeD-IA: SpeeD-IA Awadhi is reported from Pratapgarh, Uttar Pradesh, with 10 speakers and 04:46:30 total Awadhi audio.
- ANSWERED FOR VAANI SUMMARY: VAANI reports Awadhi across 9 districts, 8.85 hours audio, and 0.27 hours transcribed in the paper; the transcription subset card reports 0.28 hours transcribed.
- PARTIAL: Dominant-language normalization has been studied in a related setting. Dhasmana et al. (2026) quantify Garhwali non-Hindi terms converted to Hindi, but this is not Nepal-Awadhi.
- PARTIAL: Nepal-language ASR transfer has been studied. Sharma et al. (2026) study Nepali-to-Nepal-Bhasha transfer, not Nepal-Awadhi.

## Still Unresolved

- UNKNOWN: Has Nepal-Awadhi ASR specifically been studied outside the sources audited so far?
- UNKNOWN: Does a Nepal-Awadhi speech corpus exist outside SpeeD-IA and VAANI?
- UNKNOWN: Do any existing Awadhi datasets beyond SpeeD-IA and VAANI include speakers from Nepal?
- UNKNOWN: What exact districts/states contribute VAANI Awadhi rows?
- UNKNOWN: How many speakers contribute VAANI Awadhi rows?
- UNKNOWN: Whether VAANI Awadhi speaker `stay(years)` metadata is sufficient to infer residence history or origin for cross-border claims.
- UNKNOWN: Whether row-level VAANI Awadhi metadata contains any Nepal references; public summary does not show any.
- UNKNOWN: Whether SpeeD-IA public transcription files expose enough speaker IDs/metadata to build speaker-disjoint splits without audio download.
- UNKNOWN: Whether Sood et al. (2025)'s description of ASR-generated SpeeD-IA transcriptions reflects their own processing or the original corpus pipeline.
- UNKNOWN: Has anyone directly compared Indian Awadhi and Nepal-Awadhi ASR under controlled conditions?
- UNKNOWN: Has anyone studied Hindi versus Nepali donor transfer specifically for Nepal-Awadhi?
- UNKNOWN: Does the DonorRank full donor matrix include Nepali as a donor to Awadhi, and if so how did it perform?
- UNKNOWN: What exact language does the donor code `hne` refer to in DonorRank's Awadhi row?
- UNKNOWN: Is approximately 5-10 hours of Nepal-Awadhi enough for controlled cross-border robustness and donor-transfer claims?
- UNKNOWN: What annotation definition could defensibly measure Awadhi-to-Hindi or Awadhi-to-Nepali normalization without erasing legitimate variation?
- UNKNOWN: Whether read and spontaneous Nepal-Awadhi can be compared without confounding region, topic, recording condition, and transcription practice.

## New Questions Revealed By The Dataset Provenance Audit

- Should VAANI full audio and VAANI transcription-part be treated as separate resources in experiment planning because Awadhi has 8.85 hours full audio but only 0.27-0.28 transcribed hours?
- Can VAANI gated metadata be inspected without downloading audio, and does that satisfy ethics/access constraints?
- Are VAANI's `state`, `district`, `pincode`, and `stay(years)` fields sufficient for provenance, or do we need additional speaker-origin confirmation?
- Should SpeeD-IA's translation and narration components be separated in all future comparisons because they differ in elicitation style?
- Can SpeeD-IA CC BY-NC-SA be mixed legally with VAANI CC BY 4.0 outputs for the intended research artifacts?

## Phase 0C new open questions

- Does the Linguistic Survey of Nepal / Central Department of Linguistics retain any Awadhi audio recordings, wordlist recordings, consent forms, or field notes associated with Thakur and Yadav 2013?
- Does the full Thakur and Yadav 2013 Awadhi survey report document exact survey points, elicitation tools, speaker counts, or any audio-recording protocol?
- Do TU thesis authors/departments retain any original Awadhi interview recordings, or were the studies questionnaire-only with no audio capture?
- Who recorded the MegaVoice / CRU "Jesus Film Audio - Awadhi, Nepal" resource, where was it recorded, and were speakers Nepal-origin Awadhi speakers?
- Are scripts/transcripts for Awadhi, Nepal religious media available, aligned, and legally reusable for research?
- Does Global Recordings Network have speaker metadata for Awadhi recordings that distinguish India, Nepal, residence, and origin?
- Are there Nepal Academy, local government, radio, oral-history, or folk-culture archives using Nepali-script labels for Awadhi/Avadhi/Abadhi that were missed by English web search?
- Can any public cultural recordings be used ethically for ASR evaluation, or would domain, music, consent, and copyright issues make them unsuitable?

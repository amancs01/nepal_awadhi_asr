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

## Phase 0D sociolinguistic open questions revised after primary LinSuN facts

- ANSWERED: Thakur and Yadav (2013) surveyed five Nepal-Awadhi locations: Tenuhawa/Rupandehi, Jamuni-Maharajgunj/Kapilvastu, Thandeukhuri-Gadhwa/Dang, Tribhuvan Chowk-Nepalgunj/Banke, and Gulariya/Bardiya.
- ANSWERED: The LinSuN Awadhi lexical comparison used a 210-word list and reports approximately 78%-89% lexical similarity across five survey points.
- ANSWERED: The LinSuN report concludes that the surveyed varieties remain mutually intelligible and that dialectal variation does not appear to hinder mutual intelligibility.
- ANSWERED: The main questionnaire sample was N=60, with 30 male and 30 female respondents and age categories 15-29, 30-59, and 60+.
- ANSWERED: Wordlist informants included at least two per survey point; they were selected as local/nearby-born Awadhi mother-tongue speakers without extended residence outside the village.
- ANSWERED: Wordlist responses were elicited using Nepali prompts and transcribed in IPA.
- ANSWERED: Both Hindi and Nepali are HIGH-confidence sociolinguistic contact languages for Nepal-Awadhi, based on main-respondent and child language-knowledge evidence in Thakur and Yadav (2013).
- UNKNOWN: Does the LinSuN Awadhi report document pronunciation/phonological variation relevant to ASR error analysis?
- UNKNOWN: Does any LinSuN audio, wordlist recording, or field recording exist, or was the survey record text-only/IPA-only?
- UNKNOWN: How frequently do Nepal-Awadhi speakers code-switch at the utterance level in spontaneous speech, and with which languages?
- UNKNOWN: Are Nepali and Hindi contact effects visible in actual Nepal-Awadhi lexical, morphological, or phonological forms beyond reported language knowledge/use?
- UNKNOWN: What role do Bhojpuri, Urdu, Tharu, and English play in actual Nepal-Awadhi speech by district and domain?
- UNKNOWN: If initial collection is limited to one or two districts, what is the narrowest scientifically honest research question?

## Phase 0E model and feasibility open questions

- What local or cloud hardware is available: GPU model, VRAM, RAM, storage, operating system, and allowed runtime length?
- Can SraVaani 1.0 access be obtained, and do release artifacts explicitly list Awadhi and Nepali support?
- Does MMS-1B-all include verified Awadhi, Hindi, and Nepali adapters usable under CC-BY-NC-4.0 for this project?
- Can a neutral IndicWav2Vec base checkpoint and reproducible Hindi/Nepali fine-tuning recipes be identified?
- Which Hindi and Nepali donor datasets can be matched by hours, speech style, domain, recording quality, number of speakers, transcription quality, script, and license?
- Should the first donor comparison use equal donor hours, equal speaker counts, equal utterance counts, or a combination?
- Is `10h Hindi vs 10h Nepali vs 5h+5h` scientifically defensible, or should total donor hours and speaker diversity be controlled differently?
- How many random seeds are feasible for key comparisons given compute constraints?
- Which external baselines can be run without sending sensitive future Nepal-Awadhi audio to third-party APIs?
- What conservative normalization policy should be paired with WER/CER before language-fidelity analysis?

## Final Phase 0 decision-gate open questions

- Can the Nepali Spoken Corpus be accessed under terms compatible with this project, and can it be subset by speaker/metadata without unacceptable licensing or privacy constraints?
- Is OpenSLR SLR54 sufficiently Nepal-origin for RQ2, or does it only support a weaker "Nepali donor" condition?
- Can Kathbath Hindi and OpenSLR SLR54 Nepali be matched closely enough by speaker count, hours, utterance duration, style, transcript quality, and split policy?
- Can FLEURS Hindi/Nepali be used as a same-framework donor pilot while explicitly avoiding Nepal-origin claims for `ne_np`?
- Is RQ2 better postponed until a small newly collected Nepal-origin Nepali donor set is ethically approved and matched to Nepal-Awadhi collection conditions?
- What minimum Nepal-Awadhi evaluation set can answer RQ1 without overclaiming regional representativeness?

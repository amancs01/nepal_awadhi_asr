# Open Questions

STATUS: PHASE 0 — RESEARCH VALIDATION

## Answered Or Partially Answered In Phase 0A

- ANSWERED: Awadhi speech datasets exist. Kumar et al. (2022) report SpeeD-IA with Awadhi from Pratapgarh, Uttar Pradesh.
- ANSWERED: Awadhi ASR has already been studied. Kumar et al. (2022), Sood et al. (2025), and Dhasmana et al. (2026) include Awadhi ASR-related evaluation.
- ANSWERED: Awadhi appears in donor-language selection studies. DonorRank includes Awadhi as a VAANI-D target.
- PARTIAL: Dominant-language normalization has been studied in a related setting. Dhasmana et al. (2026) quantify Garhwali non-Hindi terms converted to Hindi, but this is not Nepal-Awadhi.
- PARTIAL: Nepal-language ASR transfer has been studied. Sharma et al. (2026) study Nepali-to-Nepal-Bhasha transfer, not Nepal-Awadhi.

## Still Unresolved

- UNKNOWN: Has Nepal-Awadhi ASR specifically been studied?
- UNKNOWN: Does a Nepal-Awadhi speech corpus exist?
- UNKNOWN: Do any existing Awadhi datasets include speakers from Nepal?
- UNKNOWN: Has anyone directly compared Indian Awadhi and Nepal-Awadhi ASR under controlled conditions?
- UNKNOWN: Has anyone studied Hindi versus Nepali donor transfer specifically for Nepal-Awadhi?
- UNKNOWN: Does the DonorRank full donor matrix include Nepali as a donor to Awadhi, and if so how did it perform?
- UNKNOWN: What exact language does the donor code `hne` refer to in DonorRank's Awadhi row?
- UNKNOWN: What speaker-origin metadata is available for VAANI Awadhi?
- UNKNOWN: What licensing and access restrictions apply to VAANI Awadhi and SpeeD-IA for our intended research use?
- UNKNOWN: Is approximately 5-10 hours of Nepal-Awadhi enough for controlled cross-border robustness and donor-transfer claims?
- UNKNOWN: What annotation definition could defensibly measure Awadhi-to-Hindi or Awadhi-to-Nepali normalization without erasing legitimate variation?
- UNKNOWN: Whether read and spontaneous Nepal-Awadhi can be compared without confounding region, topic, recording condition, and transcription practice.

## New Questions Revealed By The Literature

- Should Nepal-Awadhi evaluation require both standard normalized WER/CER and conservative minimally normalized WER/CER?
- Should any future language-model decoding be treated as a possible source of standardization pressure?
- How should we separate practical baselines such as Whisper from controlled donor-language experiments where pretraining exposure matters?
- Would speaker-disjoint splitting reduce comparability with some prior work but improve validity for our generalization claims?

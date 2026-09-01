# Dataset Audit

STATUS: PHASE 0 — RESEARCH VALIDATION

No speech data has been collected or downloaded for this project. This document records provenance findings from public dataset documentation and papers only.

## Audit Goals

- Identify existing Awadhi, Nepali, Hindi, Bhojpuri, Maithili, Urdu, and related speech resources.
- Record dataset licensing, collection location, speaker demographics, language labels, dialect labels, and access constraints.
- Mark all unavailable or uncertain fields as UNKNOWN.

## Phase 0B Findings: SpeeD-IA

Verified source: SpeeD-IA GitHub repository, https://github.com/kmi-linguistics/SpeeD-IA, and Kumar et al. (2022), https://www.isca-archive.org/s4sg_2022/kumar22_s4sg.html.

- Resource name: SpeeD-IA.
- Responsible institutions/authors: repository says Dr. Bhimrao Ambedkar University and Council for Strategic and Defense Research, in collaboration with Karya Inc. and UnReaL-TecE LLP. The paper authors are Kumar et al. (2022).
- License: repository README says SpeeD-IA Audio and Transcription are licensed under CC BY-NC-SA 4.0, with commercial licensing through UnReaL-TecE LLP.
- Awadhi location: Kumar et al. (2022) reports Awadhi region as Pratapgarh, Uttar Pradesh.
- Awadhi speakers: 10 speakers, 5 female and 5 male, ages 18-35.
- Awadhi duration: 04:46:30 total, split into 01:52:29 translation and 02:54:01 narration.
- Speech style: Hindi sentence translation/elicitation plus lifecycle-event narration prompts.
- Transcription: Devanagari; paper reports TextGrid and CoNLL-U export with POS, morphology, and Universal Dependencies annotation.
- Nepal-origin evidence: none identified in the audited SpeeD-IA sources.

Unknown or unresolved:

- Exact audio sample rate is UNKNOWN from audited sources.
- Whether train/dev/test splits exist in the public release is UNKNOWN.
- Whether speaker-disjoint splits can be constructed from exposed metadata requires repository/file inspection but no audio download.
- Later Sood et al. (2025) describes SpeeD-IA spoken translations as transcribed using ASR and then refined; this may refer to their processing pipeline rather than original SpeeD-IA creation, but the distinction needs verification.

## Phase 0B Findings: VAANI

Verified sources: VAANI Hugging Face dataset card, https://huggingface.co/datasets/ARTPARK-IISc/Vaani; VAANI transcription subset, https://huggingface.co/datasets/ARTPARK-IISc/Vaani-transcription-part; VAANI paper, https://arxiv.org/abs/2603.28714.

- Resource name: VAANI / Project Vaani.
- Responsible institutions/authors: IISc Bangalore and ARTPARK; paper also includes Google DeepMind-affiliated contributors.
- License: CC BY 4.0 on Hugging Face dataset pages.
- Release/version: arXiv v3 dated 2026-05-26; Hugging Face current release describes current version as phase 1 plus phase 2 district coverage, but also says current open-sourced dataset is Phase 1. Treat release scope as version-sensitive.
- Total release size: paper reports 31,255 hours of spontaneous speech, 2,043 hours of manual transcription, 289,838 paired images, and 158,441 speakers across 165 districts.
- Hugging Face current card reports about 31,255 hours, 156K speakers, 165 districts, 288K images, and 106 languages.
- Awadhi full audio: VAANI paper language table reports Awadhi across 9 districts, 8.85 hours audio, 0.27 hours transcribed.
- Awadhi transcribed subset: Hugging Face transcription-part card reports Awadhi 0.28 hours transcribed.
- Speech style: spontaneous, image-prompted speech.
- Audio specification: 16 kHz, 16-bit, single-channel raw audio per VAANI paper collection spec.
- Metadata: released schema includes speakerID, languagesKnown, gender, state, district, pincode, stay(years), transcript availability, transcript, referenceImage, speakerImageHash, and utterance sequence ID.
- Speaker provenance: collection specs say speakers should be native to the reported pincode, verified by PAN/Aadhaar, and stay-years from birth should be recorded.
- Nepal-origin evidence: none identified in audited VAANI sources. VAANI is consistently framed as India-representative and collected across Indian states/union territories/districts.

Unknown or unresolved:

- Exact Awadhi districts are not identified from the public summary; row-level metadata inspection would be needed after access approval.
- Number of Awadhi speakers is UNKNOWN from audited summaries.
- Whether Awadhi train/dev/test splits exist is UNKNOWN; the Hugging Face audio/Awadhi config shows a train split.
- Whether speaker-disjoint splitting is possible likely depends on access to speakerID metadata, but this has not been verified by loading records.
- Public transcribed Awadhi is tiny: 0.27-0.28 hours, which is not enough by itself for the proposed 5-10 hour target adaptation scenario.

## Dataset Audit Priorities

- Country or region of recording.
- Speaker origin, where available and ethically appropriate.
- Language and variety labels.
- Whether Awadhi data is Indian Awadhi, Nepal-Awadhi, mixed, or unclear.
- Speech style: read, prompted, conversational, spontaneous, code-switched, broadcast, or UNKNOWN.
- Transcription script and normalization conventions.
- Speaker metadata and split information.
- License and access restrictions.

Do not treat a dataset as Nepal speech merely because it contains Nepali language. Do not treat all Awadhi data as equivalent.

## Restrictions

- Do not collect Nepal-Awadhi speech data during Phase 0.
- Do not download large datasets during Phase 0.
- Do not treat unverified dataset descriptions as facts.

## Phase 0C - Nepal-Awadhi Resource Existence Audit

Phase 0C broadened the search beyond mainstream ML repositories to look for speech corpora, language-documentation audio, oral-history recordings, institutional resources, theses, sociolinguistic surveys, religious media, and public cultural recordings involving Awadhi in Nepal.

Current audit conclusion: No dedicated Nepal-Awadhi ASR corpus has been identified in the resources audited to date. This is not a claim that no Nepal-Awadhi corpus exists. Several Nepal-facing or Nepal-labeled resources were found, but none currently satisfy the requirements of an ASR-ready corpus with verified Nepal-origin speaker provenance, transcript access, licensing clarity, and speaker metadata.

### Confirmed or partially confirmed Nepal-facing candidates

- Jesus Film Audio - Awadhi, Nepal: MegaVoice lists reference M035619 as "Awadhi, Nepal", country Nepal, publisher CRU, type audio, runtime 171 min. This is confirmed as a Nepal-labeled Awadhi audio resource, but speaker origin, recording location, transcript access, and research reuse rights are UNKNOWN.
- South Asia Bibles Awadhi media: lists Awadhi resources including Audio Bible and Jesus Films and says Awadhi is spoken in Lumbini and Sudurpashchim Province in Nepal. It is a media/resource pointer, not a research corpus.
- Global Recordings Network / Words of Life Awadhi: MegaVoice lists an Awadhi audio resource and states that Words of Life recordings are recorded by mother-tongue speakers. The listing gives related countries as Nepal > India, but country, speaker origin, recording location, and license remain unclear.
- Dhaka-Dhoti Awadhi rap: Kathmandu Post reports a mainstream Nepali rap song in Awadhi by Deepak Kahar, a native of Rudrapur, Rupandehi. This is evidence of Nepal-Awadhi recorded cultural production, not an ASR corpus.

### Nepal-specific linguistic/text resources

- Thakur and Yadav 2013, A Sociolinguistic Survey of Awadhi, Linguistic Survey of Nepal / Central Department of Linguistics, Tribhuvan University. Glottolog records it as a 92-page sociolinguistic report. Full report inspection is needed to determine whether any audio, wordlists, consent records, or field metadata exist beyond the report.
- TU thesis, Case in English, Nepali and Awadhi: questionnaire data from 60 Awadhi native speakers in Gadhawa VDC, Deukhuri valley, Dang district.
- TU thesis, Pronominal of English and Awadhi: questionnaire data from 50 native Awadhi speakers in Banke district.
- TU thesis, Awadhi kinship terms: interview/questionnaire data from Awadhi speakers of Rupandehi district.
- TU thesis, Attitudes of Awadhi Students towards Learning English: questionnaire data from Awadhi-speaking learners in Bijayanagar, Kapilvastu district.

### Rejected or not ASR-ready at this stage

- Glottolog, WALS, ASJP, Joshua Project, PeopleGroups, and census resources confirm language presence/classification or population context, but they are not speech corpora.
- Hugging Face Awadhi Karya-derived resources provide Awadhi audio/text or text resources, but no Nepal-origin speaker evidence was identified in the audited metadata.
- OpenSLR search did not identify Awadhi-specific Nepal speech; OpenSLR resources found in surrounding searches were Nepali or other Indic languages.
- PARADISEC search results showed Nepal language-documentation collections, but no Awadhi Nepal collection was identified in the audited results.
- The Language Archive/MPI results mentioning Awadhi were metadata about a Nepalese collector's language knowledge in other projects, not an Awadhi speech resource.

### Implication for experimental design

The case for building or collecting a small local Nepal-Awadhi corpus is stronger than before, but only as a tentative Phase 0 inference. Existing resources suggest Nepal-Awadhi is demographically and sociolinguistically real, and there are Nepal-labeled Awadhi media resources, but no audited source yet provides an ASR-ready Nepal-Awadhi corpus with verified speaker provenance and usable transcripts.

The strongest next validation need is a metadata-only follow-up with institutions/archives before any new collection: Central Department of Linguistics / LinSuN, TU thesis authors or departments where feasible, Jesus Film/CRU, GRN/MegaVoice, and South Asia Bibles/Faith Comes By Hearing.

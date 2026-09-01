# Awadhi Dataset Provenance

STATUS: PHASE 0 — RESEARCH VALIDATION

This document audits existing Awadhi speech-data provenance without downloading audio, collecting new speech, or running experiments.

# SpeeD-IA

## Verified facts

- Exact resource name: SpeeD-IA.
- Official URL: https://github.com/kmi-linguistics/SpeeD-IA.
- Primary paper: Kumar et al. (2022), "Annotated Speech Corpus for Low Resource Indian Languages: Awadhi, Bhojpuri, Braj and Magahi", https://www.isca-archive.org/s4sg_2022/kumar22_s4sg.html.
- Responsible parties: the GitHub README says the repository contains speech datasets and models for Indo-Aryan languages prepared by Dr. Bhimrao Ambedkar University and Council for Strategic and Defense Research under different projects, in collaboration with Karya Inc. and UnReaL-TecE LLP.
- License: the repository README says SpeeD-IA Audio and Transcription are licensed under CC BY-NC-SA 4.0 and directs commercial licensing inquiries to UnReaL-TecE LLP.
- Dataset availability: the repository says it currently contains transcriptions and links audio through Google Drive. Audio was not downloaded in this audit.
- Total hours in Kumar et al. (2022): 18:00:51 across Awadhi, Bhojpuri, Braj, and Magahi.
- Awadhi-specific duration: 04:46:30 total.
- Awadhi component durations: 01:52:29 translation; 02:54:01 narration.
- Number of Awadhi speakers: 10.
- Speaker gender/age for Awadhi: 5 female, 5 male; ages 18-35.
- Awadhi collection region: Pratapgarh, Uttar Pradesh.
- Speaker selection criterion: speakers should have spent most of their time in the same region from where data was collected; the paper states this was intended to avoid excessive Hindi influence.
- Elicitation method: 369 Hindi sentences translated into the target language, plus 39 lifecycle-event prompts on birth, marriage, and death.
- Speech style: translated/elicited speech plus more naturalistic narrated speech.
- Recording method/device: Karya mobile app; speakers recorded remotely during COVID-19. Exact phone models/sample rate are UNKNOWN from audited sources.
- Transcription/script: Devanagari transcription, exported to TextGrid and CoNLL-U; annotated with POS, morphological features, and Universal Dependencies.
- Later use by Sood et al. (2025): the paper says it used SpeeD-IA as one of few parallel speech resources, pruned 369 sentence material to 267 parallel sentences, and used lifecycle narrations for ASR fine-tuning. See https://aclanthology.org/2025.wat-1.5/.

## Unknowns

- Exact public file-level metadata available without downloading audio is UNKNOWN.
- Exact sample rate is UNKNOWN.
- Whether speaker IDs are consistently available in public transcription files is UNKNOWN.
- Whether train/dev/test splits are provided is UNKNOWN.
- Whether speaker-disjoint splits can be constructed from public metadata is UNKNOWN.
- Whether speaker origin/residence beyond "spent most of their time" in collection region is documented at row level is UNKNOWN.
- Whether the Google Drive audio link exposes all components and metadata currently is UNKNOWN because audio was not downloaded.

## Conflicting reports

- Kumar et al. (2022) describe transcription after recording into Devanagari/TextGrid/CoNLL-U with linguistic annotation.
- Sood et al. (2025) state that SpeeD-IA audio translations were transcribed using ASR systems, then selected/refined. This may describe Sood et al.'s downstream processing rather than the original SpeeD-IA corpus creation, but the distinction remains unresolved.
- Sood et al. (2025) describes lifecycle narrations as roughly 2-3 hours per dialect and around 10 hours total. Kumar et al. (2022) reports Awadhi narration as 02:54:01 and all-language narration as 09:30:24, which is consistent approximately but should not be substituted for exact component totals.

## Relevance to our project

- SpeeD-IA is verified Indian Awadhi data, not verified Nepal-Awadhi data.
- It cannot by itself support an India-vs-Nepal Awadhi comparison.
- Translation and narration components should not be pooled blindly because elicitation style differs.
- The non-commercial ShareAlike license may constrain downstream experimental artifacts and must be checked before any future experiment.

# VAANI

## Verified facts

- Exact resource name: VAANI / Project Vaani.
- Official dataset URL: https://huggingface.co/datasets/ARTPARK-IISc/Vaani.
- Official transcription subset URL: https://huggingface.co/datasets/ARTPARK-IISc/Vaani-transcription-part.
- Primary paper: Pulikodan et al. (2026), "VAANI: Capturing the language landscape for an inclusive digital India", https://arxiv.org/abs/2603.28714.
- Responsible institutions: IISc Bangalore and ARTPARK; paper author affiliations also include Google DeepMind contributors.
- License: Hugging Face dataset cards list CC BY 4.0.
- Access: Hugging Face pages require users to agree to share contact information before accessing dataset files/content.
- Dataset scope in paper: 31,255 hours speech, 2,043 hours manual transcription, 289,838 paired images, 158,441 speakers, 165 districts, 105 languages, 28 states, and 3 union territories in India.
- Dataset scope in current Hugging Face card: about 31,255 hours, 156K speakers, 165 districts, 288K images, and 106 languages. This differs slightly from the paper and should be treated as version/update drift.
- Awadhi in VAANI paper language table: 9 districts, 8.85 hours audio, 0.27 hours transcription.
- Awadhi in Vaani-transcription-part card: 0.28 hours transcribed audio.
- Audio/Awadhi config in the Vaani dataset card: 6,151 train examples, with fields including audio, language, duration, speakerID, languagesKnown, gender, state, district, pincode, stay(years), isTranscriptionAvailable, transcript, referenceImage, speakerImageHash, and UtteranceSequenceID.
- Speech style: spontaneous speech elicited by image prompts.
- Audio specification: 16 kHz, 16 bits per sample, single channel, raw audio without transcoding/post-processing, per paper collection specification.
- Recording environment guidance: quiet environment; microphone/recording device distance constraints; smartphone notifications disabled when applicable.
- Speaker provenance guidance: speaker should be native of the pincode reported in metadata, verified by PAN/Aadhaar, and stay-years from birth should be recorded.
- Transcription: manual transcription subset; transcribers are required to be from the same district where audio was collected.
- Quality control: automated and manual QC processes for audio, metadata, transcriptions, and formatting.

## Unknowns

- Exact VAANI Awadhi districts are UNKNOWN from the public summary.
- Number of VAANI Awadhi speakers is UNKNOWN from the public summary.
- Whether any row-level VAANI Awadhi metadata contains Nepal references is UNKNOWN because gated records were not loaded.
- Whether train/dev/test splits exist for Awadhi is UNKNOWN; the audio/Awadhi config visible in the dataset card shows a train split only.
- Whether speaker-disjoint splitting is possible is UNKNOWN until speakerID distribution is inspected.
- Transcription script specifically for Awadhi is UNKNOWN from the public summary.
- Whether the current public/released transcription subset exactly matches the paper's 2,043-hour figure is version-sensitive.

## Conflicting reports

- VAANI paper reports 105 languages, 158,441 speakers, 289,838 paired images, and Awadhi 0.27 transcribed hours.
- Hugging Face current dataset card reports 106 languages, 156K speakers, 288K images, and Vaani-transcription-part reports Awadhi 0.28 transcribed hours.
- The Project Vaani website/model page says Project Vaani began as 31,255 hours from 165 districts and that the full multimodal dataset has 22.6M rows, while the arXiv paper reports 24,009,427 audio segments. Treat these as release/version/documentation differences until reconciled.
- Dhasmana et al. (2026) describe broader VAANI as over 150,000 hours with about 10 percent transcribed and 773 districts, apparently referring to planned/full VAANI scope rather than the current open release audited here.

## Relevance to our project

- VAANI provides Indian Awadhi spontaneous/image-prompted speech and important metadata fields, but public summaries do not establish Nepal-origin Awadhi.
- VAANI's full Awadhi audio total, 8.85 hours, is in the range of our hypothesized 5-10 hour target data scale, but only 0.27-0.28 hours is currently identified as transcribed in public summaries.
- VAANI may help study Indian Awadhi or donor baselines after access approval, but it cannot alone support a fair India-vs-Nepal comparison because no Nepal-Awadhi side is identified.
- Its metadata fields may eventually support speaker-disjoint splitting and district-level provenance, but only after gated metadata inspection.

# Nepal-origin evidence

No Nepal-origin Awadhi speech has yet been identified in the resources audited so far.

This statement is limited to SpeeD-IA, VAANI, VAANI-transcription-part, and the way Sood et al. (2025) describe their use of SpeeD-IA and VAANI. It is not a claim that no Nepal-Awadhi dataset exists.

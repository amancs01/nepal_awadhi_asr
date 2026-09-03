# Purpose

This final Phase 0 donor-pair construction audit consolidates Nepal-origin Nepali donor provenance, Hindi donor provenance, donor-pair matchability, candidate research questions, experimental feasibility, and GO/REVISE/POSTPONE recommendations.

No audio was downloaded. No model checkpoints were downloaded. No models were trained or fine-tuned. No final donor dataset was selected.

Key principle: "recorded in Nepal", "speaker located in Nepal", "speaker native to Nepal", "speaker from Terai Nepal", and "speaker with documented Awadhi contact" are distinct claims and must not be treated as interchangeable.

# Nepal-origin Nepali candidates

## Nepali Spoken Corpus / Nepali National Corpus spoken component

- Provenance evidence: The ELRA catalogue identifies the Nepali Spoken Corpus as one of three Nepali National Corpus resources, produced in 2006 under the Bhasha Sanchar / Nelralec project. ELRA says it contains audio recordings from different social activities in natural settings as much as possible [https://catalogue.elra.info/en-us/repository/browse/ELRA-S0368/]. ELRA's Nepal reconstruction page says the speech corpus is available at no cost for not-for-profit reconstruction-related work, and catalogue search results show non-commercial ELRA end-user licensing at 0.00 EUR [https://www.elra.info/nepali-corpora/].
- Speaker evidence: Published descriptions state participant information was collected, including social/geographical information; a paper description reports demographic metadata including name, age, gender, mother tongue, second language, dialect, education, primary-education place, profession, and address/contact [https://www.researchgate.net/publication/379692277_AN_ACTIVITY_BASED_SPOKEN_LANGUAGE_CORPUS_OF_NEPALI].
- Hours: ELRA catalogue reports 31h26m, 115 recorded activity occurrences/files, 115 transcribed files, about 260,000 transcribed words [https://catalogue.elra.info/en-us/repository/browse/ELRA-S0368/]. A later paper/source reports an expanded/current situation of 61:35:33 total and 40:58:15 transcribed, but this conflicts with the catalogue and needs version resolution [https://www.researchgate.net/publication/379692277_AN_ACTIVITY_BASED_SPOKEN_LANGUAGE_CORPUS_OF_NEPALI].
- Speaker count: UNKNOWN from audited official catalogue.
- Metadata: Participant and activity metadata are reported, including geography and social information, but access to actual metadata fields must be verified.
- Speech style: Natural social activities; 17 activity types in ELRA description, with examples such as shopping and discussion. Later paper lists more activity types including family gathering, phone, market place, classroom interaction, storytelling, and elicitation.
- Domain: Social activity corpus, naturalistic spoken Nepali.
- Recording conditions: Natural settings as much as possible; later paper reports Sony handy cam, MP3 digital recorders, and radio/TV archive equipment, with recordings at 44 kHz.
- Transcript information: Phonologically transcribed and annotated texts; Devanagari orthographic transcription is reported in the contemporary Nepali corpus paper.
- License/access: ELRA resource, non-commercial end-user license; no large download performed. Access terms must be reviewed before experimental use.
- Speaker-disjoint feasibility: Potentially strong if participant metadata and speaker IDs are accessible; not verified.
- Limitations: Access/licensing friction; possible version conflict; genre is naturalistic and may not match Hindi read corpora; speaker count and split structure unknown; Awadhi-contact/Terai-specific speakers not established.

Assessment: Best Nepal-origin Nepali provenance candidate, but not yet a clean matched donor without access and metadata review.

## OpenSLR SLR43 - High quality TTS data for Nepali

- Provenance evidence: OpenSLR says the data was collected by Google in Nepal [https://www.openslr.org/43/]. This supports "recorded in Nepal" more directly than FLEURS/Common Voice locale labels.
- Speaker evidence: Speaker identification number is prepended to file names; detailed origin/residence unknown.
- Hours: Downstream resource summaries report about 2.8h; OpenSLR page itself should be used for files/format, while exact duration should be verified before experiment.
- Speaker count: UNKNOWN from audited summary.
- Metadata: Filename speaker identifier only in audited documentation.
- Speech style/domain: High-quality TTS/read speech.
- Recording conditions: High-quality transcribed speech; exact device/environment not audited.
- Transcript information: `line_index.tsv` provides filename and transcription.
- License/access: CC BY-SA 4.0 [https://www.openslr.org/43/].
- Speaker-disjoint feasibility: Possible if speaker IDs are usable, but small size and speaker count are limiting.
- Limitations: TTS/read style, likely narrow speaker diversity, small size.

Assessment: Strong provenance for Nepal recording, but auxiliary/narrow for donor transfer.

## OpenSLR SLR54 - Large Nepali ASR training data set

- Provenance evidence: OpenSLR labels it Nepali ASR data; the SLTU paper describes Google crowd-sourced corpora collected from native-speaker volunteers in respective regions, but the OpenSLR page does not expose district/country-origin metadata in the summary [https://www.openslr.org/54/], [https://www.isca-archive.org/sltu_2018/kjartansson18_sltu.html].
- Speaker evidence: OpenSLR provides anonymized UserID in `utt_spk_text.tsv`; biographical information is unavailable.
- Hours: Around 157K utterances in OpenSLR; downstream summaries often report approximately 165h.
- Speaker count: 527 speakers reported by secondary corpus lists; needs primary metadata verification.
- Metadata: FileID, anonymized UserID, transcription; no speaker biography.
- Speech style/domain: Prompted/read ASR utterances.
- Recording conditions: Portable consumer electronics in reasonably quiet environments per SLTU paper.
- Transcript information: `utt_spk_text.tsv` with FileID, anonymized UserID, transcription.
- License/access: CC BY-SA 4.0.
- Speaker-disjoint feasibility: Yes in principle via anonymized UserID; downstream work has used speaker-disjoint splits.
- Limitations: Nepal-origin likely but not district-specific; no demographics; read style.

Assessment: Strong practical Nepal Nepali donor candidate if read-speech matching is acceptable.

## FLEURS Nepali (`ne_np`)

- Provenance evidence: FLEURS exposes Nepali as a locale/configuration. The paper says recordings were collected from native speakers, but audited documentation does not expose speaker country/origin/residence metadata [https://arxiv.org/html/2205.12446], [https://huggingface.co/datasets/google/fleurs].
- Speaker evidence: Speaker IDs are not visible in audited Hugging Face schema; speaker count for `ne_np` unknown.
- Hours: Approximately 12h per language in paper; around 10h training supervision per language in dataset-card summary.
- Metadata: Gender/lang fields visible; no provenance field found.
- Speech style/domain: Read FLoRes sentences, originally derived from Wikipedia-like multilingual evaluation text.
- Recording conditions: 16 kHz; quiet or noisy environments kept as-is; clips under 30 seconds.
- Transcript information: Raw and normalized transcripts; Devanagari for Nepali.
- License/access: CC BY 4.0.
- Speaker-disjoint feasibility: Official train/dev/test are speaker-disjoint between train/dev and test per paper, but custom speaker-disjoint subset construction is not verified.
- Limitations: Locale label is not Nepal-origin proof.

Assessment: Best same-framework Hindi/Nepali format match, but not a confident Nepal-origin donor.

## Mozilla Common Voice Nepali (`ne-NP`)

- Provenance evidence: Mozilla identifies Common Voice Scripted Speech 26.0 Nepali as locale `ne-NP`; the audited page does not provide contributor country/origin metadata [https://mozilladatacollective.com/datasets/cmqi732rk00himf07x3hy8twt].
- Speaker evidence: `client_id` hashed contributor ID; optional age/gender/accent/variant fields; no speaker-origin field.
- Hours: 2h recorded, 1.38h validated, 1,739 clips, 1,204 validated clips.
- Speaker count: 63 speakers.
- Metadata: Hashed speaker ID plus optional demographics.
- Speech style/domain: Crowd-sourced read speech from sentence prompts.
- Recording conditions: MP3 user recordings; device/environment variable and not controlled.
- Transcript information: Sentence text in Nepali Devanagari.
- License/access: CC0-1.0, with restrictions against speaker identification and re-host/re-share.
- Speaker-disjoint feasibility: Possible via `client_id`, but official split speaker-disjointness not established and data is small.
- Limitations: Too small for 10h donor condition; Nepal-origin not proven.

Assessment: Useful small metadata-rich pilot, not a confident Nepal-origin donor source.

# Hindi candidates

## Kathbath Hindi

- Provenance evidence: AI4Bharat Kathbath is an Indian read-speech corpus; the full corpus covers 203 Indian districts across 12 languages [https://huggingface.co/datasets/ai4bharat/Kathbath].
- Speaker evidence: Speaker/gender encoded in filenames; Hindi speaker count reported in benchmark summaries as 121.
- Hours: IndicSUPERB-style summaries report 150.2h Hindi; full Kathbath is 1,684h across 12 languages.
- Metadata: Speaker/gender in filename; richer metadata may require gated access.
- Speech style/domain: Read speech benchmark with clean/noisy split variants.
- Recording conditions: Clean/noisy variants; exact Hindi channel/provenance details need metadata inspection.
- Transcript information: Human-labelled transcripts, Devanagari expected.
- License/access: CC BY 4.0, gated Hugging Face access.
- Speaker-disjoint feasibility: Strong in principle if speaker IDs are available.
- Limitations: Indian Hindi, read style, may not match naturalistic Nepali Spoken Corpus; district matching to Nepal Terai not established.

Assessment: Strongest Hindi read-speech donor pool.

## FLEURS Hindi (`hi_in`)

- Provenance evidence: FLEURS Hindi locale/configuration for India-oriented Hindi; exact speaker state/district origin not visible in audited docs [https://huggingface.co/datasets/google/fleurs], [https://arxiv.org/html/2205.12446].
- Speaker evidence: Speaker count unknown; gender visible.
- Hours: Approximately 12h per language; around 10h train supervision.
- Metadata: Limited; no visible speaker-origin field.
- Speech style/domain: Read FLoRes sentences.
- Recording conditions: 16 kHz; quiet/noisy environments preserved.
- Transcript information: Raw and normalized transcripts, Devanagari expected.
- License/access: CC BY 4.0.
- Speaker-disjoint feasibility: Official splits designed with speaker disjointness between train/dev and test; custom subsetting unclear.
- Limitations: Small; locale not detailed geography.

Assessment: Strongest format match with FLEURS Nepali, but weak provenance granularity.

## Gram Vaani / OpenSLR SLR118 Hindi ASR Challenge

- Provenance evidence: Gram Vaani Hindi ASR Challenge data was collected in India and released through OpenSLR/IITM; it represents spontaneous Hindi with regional variations [https://www.openslr.org/118/], [https://www.isca-archive.org/interspeech_2022/bhanushali22_interspeech.html].
- Speaker evidence: Metadata tarball exists; fields not audited.
- Hours: 1111h total: 100h labelled train, 5h dev, 3h eval, 1000h unlabelled.
- Metadata: Metadata available for all challenge data, not inspected.
- Speech style/domain: Spontaneous telephone speech.
- Recording conditions: MP3, mixed sample rates 8-48 kHz, telephone channel/noisy conditions.
- Transcript information: Labelled train/dev/eval have transcripts; unlabelled set does not.
- License/access: Free for academic use; commercial use requires Gram Vaani permission.
- Speaker-disjoint feasibility: Unknown until metadata inspection.
- Limitations: Channel/style mismatch with available Nepal Nepali read/TTS data; transcription noise.

Assessment: Strong Hindi robustness resource, weak controlled pair unless a comparable Nepal Nepali telephone/spontaneous corpus is used.

## IndicTTS Hindi

- Provenance evidence: IITM IndicTTS database is an Indian-language TTS corpus; Hindi monolingual means Hindi sentences spoken by native Hindi speakers [https://www.iitm.ac.in/donlab/indictts/database]. A Hugging Face derivative reports 10.33h Hindi from 2 native Hindi speakers, 48 kHz WAV [https://huggingface.co/datasets/SPRINGLab/IndicTTS-Hindi/blob/main/README.md].
- Speaker evidence: 2 speakers in the derivative; native Hindi speakers; Indian provenance.
- Hours: Derivative reports 10.33h, male 5.16h and female 5.18h. IITM page reports larger/variant mono male/female durations depending latest/old packages.
- Metadata: Speaker/gender minimal.
- Speech style/domain: Studio-quality TTS/read speech.
- Recording conditions: WAV, 48 kHz in derivative; studio-quality.
- Transcript information: Text transcriptions available.
- License/access: IITM license; derivative license needs exact review.
- Speaker-disjoint feasibility: Weak because only two speakers in derivative.
- Limitations: TTS/studio, very low speaker diversity.

Assessment: C, auxiliary only.

## IITM Hindi ASR Challenge / Indian Language ASR

- Provenance evidence: IITM challenge Hindi data consists of volunteers reading newspaper articles; license says the corpus was collected in various Indian metropolitan cities [https://github.com/Speech-Lab-IITM/Hindi-ASR-Challenge], [https://github.com/Speech-Lab-IITM/Indian_Language_ASR].
- Speaker evidence: Volunteers aged 20-60 per license; speaker count unknown in audited docs.
- Hours: Challenge variants report 40h train + 5h dev + 5h eval for one Hindi read challenge, and 188.1h Hindi in Indian_Language_ASR 2021 release.
- Metadata: Unknown.
- Speech style/domain: Read speech, newspaper articles; some related challenge releases include read and conversational speech.
- Recording conditions: Unknown from audited docs.
- Transcript information: Transcriptions included.
- License/access: Research-only, non-transferable; redistribution prohibited.
- Speaker-disjoint feasibility: Unknown until access/metadata inspection.
- Limitations: Access restrictions, geography broad/metropolitan, metadata incomplete.

Assessment: B/C depending access and metadata.

# Candidate donor pairs

| Pair | Geography | Hours | Style/domain | Metadata/splits | License | Remaining confounds | Rating |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Kathbath Hindi + OpenSLR SLR54 Nepali | India Hindi vs likely Nepal Nepali | Both can support 10h-scale subsets | Read ASR speech, but different prompts/corpora | Speaker IDs likely available for both; demographics uneven | CC BY 4.0 vs CC BY-SA 4.0 | Collection framework, content, license, region/demographics | B |
| FLEURS Hindi + FLEURS Nepali | Locale Hindi/India vs locale Nepali/Nepal, not full provenance | Similar per-language scale | Same read benchmark sentences | Official splits; limited speaker metadata | CC BY 4.0 both | Nepal-origin not proven; small size; not naturalistic | B |
| IITM Hindi ASR + OpenSLR SLR54 Nepali | Indian metro Hindi vs likely Nepal Nepali | Enough for 10h-scale if accessible | Read ASR speech but different content | Hindi speaker metadata unknown | Research-only vs CC BY-SA | Access restrictions; provenance granularity | B/C |
| Common Voice Hindi + Common Voice Nepali | Locale Hindi vs locale Nepali | Hindi 15.6h validated; Nepali 1.38h validated | Same platform, crowd-read | Has hashed client_id; origin not proven | CC0 both with CV restrictions | Nepali too small; provenance weak; quality variable | C |
| Gram Vaani Hindi + Nepali Spoken Corpus | India spontaneous telephone vs Nepal natural social Nepali | Both non-read/natural-ish but very different | Telephone spontaneous vs social-activity corpus | Metadata exists but not inspected | Academic/commercial restrictions vs ELRA non-commercial | Channel/domain/style/transcript differences | C |
| Gram Vaani Hindi + OpenSLR SLR54 Nepali | India telephone spontaneous vs Nepal-ish read | Hindi ample; Nepali ample | Severe style/channel mismatch | Metadata uneven | Academic vs CC BY-SA | Compares language plus channel/style | C |
| IndicTTS Hindi + SLR43 Nepali | Indian TTS Hindi vs Nepal-recorded TTS/read Nepali | Small | Clean TTS/read | Very limited speakers | IITM/derivative vs CC BY-SA | Speaker diversity too low | C |

# Best available pair

The strongest practical donor-pair candidate is Kathbath Hindi + OpenSLR SLR54 Nepali, rated B. It offers enough read-speech hours to construct matched subsets and likely supports speaker-disjoint grouping. Its weakness is that the two datasets come from different collection frameworks and licenses, with different prompt/domain and metadata depth.

The strongest same-framework pair is FLEURS Hindi + FLEURS Nepali, also rated B. It controls content, split design, license, and speech style better than cross-corpus pairs, but it does not confidently establish Nepal-origin speaker provenance for `ne_np`.

The strongest Nepal-origin provenance candidate is the Nepali Spoken Corpus, but it is not currently the best donor-pair candidate because access, version, speaker count, splits, and style matching against Hindi remain unresolved.

# Remaining confounds

- Nepal-origin provenance is strongest for SLR43 and Nepali Spoken Corpus, plausible for SLR54, and not proven for FLEURS/Common Voice.
- Hindi provenance is generally India-level, often not district-level.
- Read, TTS, telephone, crowd-read, and natural social activity speech cannot be mixed as if only donor language changed.
- Speaker counts, demographics, and region distributions are not consistently available.
- License incompatibility may affect what outputs can be redistributed.
- Hindi and Nepali transcript normalization may differ; Devanagari alone does not make scripts/tokenization equivalent.
- Previous ASR model exposure to Hindi/Nepali/Awadhi remains a model-level confound.

# Could a small newly collected Nepal-origin Nepali donor set solve an important provenance/matching problem?

Yes, potentially. A small newly collected Nepal-origin Nepali donor set could solve a provenance problem if speakers are recruited and documented under the same ethical and metadata protocol as Nepal-Awadhi. It could also match recording conditions, prompts, domains, and splits.

However, this would introduce new collection burden, consent requirements, and additional IRB/ethics review. It should not proceed during Phase 0. It may be justified later only if public Nepali resources cannot provide verifiable Nepal-origin donor data matched to the Nepal-Awadhi target design.

# Research-question gate

| Research question | Status | Reason |
| --- | --- | --- |
| RQ1: How well do existing ASR systems recognize Nepal-Awadhi speech? | PLAUSIBLE | Baseline models exist, but a verified Nepal-Awadhi test set does not yet exist. |
| RQ2: Under controlled conditions, does Hindi or Nepal-origin Nepali donor data produce greater improvement in Nepal-Awadhi ASR? | NEEDS REVISION | Donor comparison is scientifically interesting, but no perfect matched Hindi vs Nepal-origin Nepali donor pair has been verified. |
| RQ3: What kinds of language-fidelity errors occur when ASR systems recognize Nepal-Awadhi, particularly possible Hindi/Nepali normalization or substitution? | PLAUSIBLE | Supported as an analysis direction, but requires a defensible annotation scheme and should not assume common code-switching. |

# Experimental-design gate

| Component | Status | Rationale |
| --- | --- | --- |
| Practical zero-shot ASR evaluation | ESSENTIAL | Minimum path for RQ1 once a Nepal-Awadhi test set exists. |
| Nepal-Awadhi adaptation | OPTIONAL initially | Useful after zero-shot, but requires train/dev/test target data and compute. |
| Hindi donor transfer | POSTPONE until donor matching | Needs matched donor design and baseline adaptation condition. |
| Nepal-origin Nepali donor transfer | POSTPONE until provenance verified | Public resources are promising but not yet cleanly matched. |
| Hindi+Nepali donor transfer | POSTPONE | Should follow single-donor design, not precede it. |
| Language-fidelity/error analysis | ESSENTIAL as sampled/manual analysis if RQ3 retained | Requires annotation protocol; can begin small after zero-shot outputs exist. |

# Recommendation

GO WITH CONTROLS.

Proceed to manual research and actual project execution with RQ1 and a limited version of RQ3 as the defensible near-term path. RQ2 should remain revised/postponed until donor datasets are matched or a small ethically collected Nepal-origin Nepali donor set is justified.

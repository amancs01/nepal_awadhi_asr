# Phase 0F.1 - Nepal-Origin Nepali Donor Provenance Audit

This audit checks whether two Nepali donor candidates can be treated as Nepal-origin Nepali for the planned Hindi-vs-Nepal-origin-Nepali transfer comparison.

No audio was downloaded, no models were trained, and no final donor dataset was selected.

# Key Rule

Do not infer Nepal-origin speaker provenance merely from a locale label such as `ne_np` or `ne-NP`. A locale can indicate the intended language/regional configuration of a dataset without proving each speaker's country of origin, residence, or native-region background.

# FLEURS Nepali (`ne_np`)

## What the locale/language label means

FLEURS is a multilingual speech benchmark built from FLoRes dev/devtest sentences. The FLEURS paper lists Nepali as ISO 639-3 `npi`, ISO 639-1 `ne`, in the South Asia group, and the dataset configuration is commonly exposed as `ne_np` in Hugging Face usage examples [https://arxiv.org/html/2205.12446], [https://huggingface.co/datasets/google/fleurs].

The label `ne_np` should be interpreted as the Nepali locale/configuration used by FLEURS. In the audited documentation, it is not a speaker-origin field.

## Speaker country/geographic origin

FLEURS documentation says recordings were collected from native speakers for each language. It does not provide a per-speaker country, district, residence, or origin field in the audited documentation. Therefore, this audit cannot confidently establish that all or most `ne_np` speakers are Nepal-origin Nepali speakers.

## Speaker-level metadata

The visible Hugging Face schema includes fields such as `id`, `num_samples`, `path`, `audio`, `transcription`, `raw_transcription`, `gender`, `lang_id`, `language`, and `lang_group_id`. A speaker ID field is not visible in the audited dataset-card schema [https://huggingface.co/datasets/google/fleurs].

The FLEURS paper states that speakers are disjoint between train/dev and test with a target 7:1:2 split, but without exposed speaker IDs this does not by itself allow arbitrary speaker-disjoint subset construction [https://arxiv.org/html/2205.12446].

## Number of speakers

UNKNOWN for `ne_np` from audited documentation. The paper says each sentence was targeted for three recordings by three different native speakers and that sex-ratio balance of at least 30/70 was imposed when possible, but it does not provide an audited `ne_np` speaker count in the accessible text [https://arxiv.org/html/2205.12446].

## Available hours / clips

FLEURS has approximately 12 hours of speech supervision per language in the paper abstract, and the dataset card says training sets have around 10 hours of supervision [https://arxiv.org/abs/2205.12446], [https://huggingface.co/datasets/google/fleurs]. Exact `ne_np` hours and clips should be verified from release metadata before use.

## Speech style

Read speech. FLEURS uses FLoRes/FLoRes-101 sentences translated into the target languages, with recordings of those sentences by native speakers [https://arxiv.org/html/2205.12446].

## Recording conditions

The paper states recordings are kept as-is from quiet or noisy environments with no data augmentation, speech sampling rate is 16 kHz, and segments are within 30 seconds [https://arxiv.org/html/2205.12446].

## Domain/content

FLoRes sentences were extracted from English Wikipedia and translated into many languages. The paper notes coverage across domains such as nature, politics, science, travel, and sports [https://arxiv.org/html/2205.12446].

## Transcript/script information

FLEURS provides original raw transcript, normalized transcript, and character-based forms for ASR. It applies NFC and FST normalization, lower-casing where relevant, punctuation removal, character splitting, and word-boundary marking. The paper identifies Nepali `ne_np` as Devanagari in the ASR discussion [https://arxiv.org/html/2205.12446].

## Official train/dev/test splits

Yes. FLEURS splits the 2009 source sentences into 1509 train, 150 dev, and 350 test sentences, with train/dev/test speech split target ratio 7:1:2 and disjoint speakers between train/dev and test [https://arxiv.org/html/2205.12446].

## License

CC BY 4.0 [https://huggingface.co/datasets/google/fleurs].

## Can speaker-disjoint subsets be constructed?

Official train/dev/test structure is speaker-disjoint between train/dev and test according to the paper. However, custom speaker-disjoint subsetting cannot be confirmed from the visible schema because speaker IDs are not visible in the audited Hugging Face fields.

## Limitation for Hindi-vs-Nepal-origin-Nepali donor experiment

FLEURS is the best same-framework candidate for matching Hindi and Nepali by sentence source, recording task, approximate hours, split structure, and license. Its main weakness is provenance: this audit cannot verify Nepal-origin speaker status beyond the `ne_np` locale/native-speaker framing.

# Mozilla Common Voice Nepali (`ne-NP`)

## What the locale/language label means

The Mozilla Data Collective page identifies the dataset as Common Voice Scripted Speech 26.0 - Nepali, locale `ne-NP`, task ASR, format MP3, release date 2026-06-17, and describes it as read speech recordings in Nepali [https://mozilladatacollective.com/datasets/cmqi732rk00himf07x3hy8twt].

The label `ne-NP` is the Common Voice locale code for Nepali. In the audited page, it is not equivalent to a speaker-origin field.

## Speaker country/geographic origin

The audited Common Voice Nepali page does not expose speaker country, district, residence, native-region, or origin metadata. It includes optional self-declared demographic fields but not enough to establish Nepal-origin speaker provenance. Therefore, this audit cannot confidently establish that contributors are Nepal-origin Nepali speakers.

## Speaker-level metadata

Common Voice clip rows include `client_id`, a hashed UUID of a user; `path`; `sentence`; `sentence_id`; `sentence_domain`; up/down votes; optional `age`, `gender`, `accents`, `variant`; `locale`; and `segment` [https://mozilladatacollective.com/datasets/cmqi732rk00himf07x3hy8twt].

This is speaker-level enough for grouping by hashed contributor ID, but not speaker-origin metadata. Optional age/gender coverage is incomplete.

## Number of speakers

The Common Voice Scripted Speech 26.0 Nepali page reports 63 speakers [https://mozilladatacollective.com/datasets/cmqi732rk00himf07x3hy8twt].

## Available hours / clips

The same page reports 1,739 clips representing 2 hours of recorded speech, 1.38 validated hours, 1,204 validated clips, 99 invalidated clips, and 436 unresolved clips. The average clip duration is 4.152 seconds [https://mozilladatacollective.com/datasets/cmqi732rk00himf07x3hy8twt].

## Speech style

Read speech. The page describes the dataset as a collection of read speech recordings in Nepali [https://mozilladatacollective.com/datasets/cmqi732rk00himf07x3hy8twt].

## Recording conditions

MP3 crowd-contributed recordings. The audited page does not document controlled recording device, room, microphone, or channel conditions.

## Domain/content

The text corpus contains 1,346 sentences, including 1,321 validated and 25 unvalidated. Source breakdown includes sentence-collector, Nepali educational/text sources from Pustakalaya, original work, proverbs, and other sources. The page shows sample Nepali sentences in Devanagari [https://mozilladatacollective.com/datasets/cmqi732rk00himf07x3hy8twt].

## Transcript/script information

Transcript text is the sentence read aloud; examples and description are in Nepali Devanagari. Clip rows include `sentence` and `sentence_id`; sentence files include `sentence`, `variant`, `sentence_domain`, `source`, and circulation/review fields [https://mozilladatacollective.com/datasets/cmqi732rk00himf07x3hy8twt].

## Official train/dev/test splits

The page reports training split counts for validated clips: train 358, dev 316, test 299, with 973 of 1,204 validated clips covered by training splits [https://mozilladatacollective.com/datasets/cmqi732rk00himf07x3hy8twt].

## License

CC0-1.0. The page also states that attempts to determine speaker identity are forbidden and that re-hosting/re-sharing is forbidden [https://mozilladatacollective.com/datasets/cmqi732rk00himf07x3hy8twt].

## Can speaker-disjoint subsets be constructed?

Possibly, because `client_id` is available as a hashed contributor identifier. However, the official page does not state that the provided train/dev/test splits are speaker-disjoint. A custom speaker-disjoint split may be possible after metadata-only TSV inspection, but the small dataset size may make this unstable.

## Limitation for Hindi-vs-Nepal-origin-Nepali donor experiment

Common Voice Nepali has clearer release-level statistics than FLEURS and includes hashed speaker IDs. However, it is very small: only 1.38 validated hours and 63 speakers. It still does not provide verified speaker country/origin. It may be useful for pilot donor matching but is not enough for a robust 10-hour Nepal-origin Nepali donor condition.

# Direct Answers

## A. Can FLEURS `ne_np` be confidently treated as Nepal-origin Nepali for our experiment?

No. FLEURS `ne_np` can be treated as a Nepali locale/configuration and a strong same-framework read-speech benchmark candidate. The audited documentation does not expose speaker country, residence, district, or origin metadata sufficient to confidently classify it as Nepal-origin Nepali.

## B. Can Common Voice `ne-NP` be confidently treated as Nepal-origin Nepali?

No. Common Voice `ne-NP` can be treated as the Nepali locale in the Common Voice release. The audited page reports clips, hours, speakers, optional demographics, hashed contributor IDs, and splits, but it does not provide speaker country/origin metadata sufficient to confidently establish Nepal-origin provenance.

## C. If neither can be established confidently, what evidence is missing?

Missing evidence:

- Speaker country of origin or native-region metadata.
- Speaker current residence or recording country metadata.
- Clear documentation that contributors were recruited from Nepal or verified as Nepal-origin Nepali speakers.
- For FLEURS, speaker IDs or per-speaker metadata that would allow provenance checks and custom speaker-disjoint subsetting.
- For Common Voice, reliable contributor location/origin fields beyond locale, age, gender, accent, and variant.

## D. Which resource is the strongest candidate and why?

For controlled Hindi-vs-Nepali matching, FLEURS is the stronger same-framework candidate because Hindi `hi_in` and Nepali `ne_np` share the same benchmark design: translated FLoRes sentences, read speech, similar per-language scale, official splits, 16 kHz audio, and CC BY 4.0 licensing.

For metadata-driven speaker grouping, Common Voice is stronger because it exposes `client_id` and detailed release statistics. But its very small validated size and missing speaker-origin metadata make it weak as a 10-hour Nepal-origin Nepali donor source.

Current conclusion: neither resource can yet be confidently treated as Nepal-origin Nepali. FLEURS is the stronger controlled-format candidate; Common Voice is the stronger small metadata-inspection candidate.

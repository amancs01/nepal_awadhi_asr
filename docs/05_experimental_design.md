# Experimental Design

STATUS: PHASE 0 — RESEARCH VALIDATION

No ASR experiments have been approved or run. This document records design requirements, variables, and confounds only.

## Cross-Border Robustness

Indian Awadhi vs Nepal Awadhi alone is not a controlled comparison if any of the following differ:

- Speech style.
- Audio quality.
- Microphone.
- Speaker demographics.
- Sentence content.
- Segment length.
- Transcription conventions.
- Text normalization.

Future work should separate at least two evaluation settings.

## A. Matched/Controlled Speech

Purpose: studying geographical or variety generalization under reasonably comparable conditions.

Design requirements:

- Comparable prompts or content where possible.
- Comparable recording setup where possible.
- Comparable speaker metadata without unnecessary personally identifying information.
- Comparable transcription and normalization guidelines.
- Speaker-disjoint train/dev/test splits.

## B. Natural/Spontaneous Speech

Purpose: ecological evaluation, code-switching analysis, and language-fidelity analysis.

Design requirements:

- Explicit speech-style labeling.
- Code-switching and contact-language metadata where defensible.
- Separate reporting from controlled read-speech results.
- Careful interpretation because natural speech may confound geography, style, topic, and recording condition.

## Donor-Language Experiments

Potential donor settings:

- Hindi.
- Nepali.
- Hindi+Nepali.
- Additional donors only if justified by evidence.

Variables to control where practical:

- Donor hours.
- Audio quality.
- Speech style.
- Transcription quality.
- Model architecture and initialization.
- Target data.
- Test set.
- Optimizer and training procedure.
- Decoding configuration.
- Random seeds where practical.

Large multilingual models such as Whisper or SraVaani may be useful external or practical baselines, but may be difficult to use for causal donor-language comparisons if previous language exposure is uncertain.

## Data Splitting

Any future Nepal-Awadhi dataset should use speaker-disjoint train/dev/test splits. No speaker used for test should occur in training.

Future metadata should preserve:

- Read or spontaneous speech.
- Region.
- Speaker ID.
- Recording condition.

Metadata should avoid unnecessary personal identifying information.

## Candidate Evaluation Metrics

- WER.
- CER.

Aggressive Indic text normalization could remove linguistically meaningful Awadhi, Hindi, or Nepali distinctions. Later evaluation design should investigate:

- Standard normalized WER/CER.
- Conservative or minimal-normalization WER/CER.
- Awadhi -> Hindi normalization or substitution errors.
- Awadhi -> Nepali normalization or substitution errors.
- Code-switch recognition errors.
- Insertions.
- Deletions.
- Substitutions.
- Hallucinations.
- Morphological errors.
- Named-entity errors.

Do not invent a language-fidelity score yet. A scientifically defensible annotation and evaluation definition is required first.

## Restrictions

- Do not train or fine-tune ASR models during Phase 0.
- Do not implement speculative ML code before the research design is reviewed.
- Experimental plans must include uncertainty, risks, and negative-result handling.

## Phase 0D Sociolinguistic Controls For Future Design

Thakur and Yadav (2013) provide primary sampling guidance for future Nepal-Awadhi corpus planning. Their survey locations were Tenuhawa/Rupandehi, Jamuni-Maharajgunj/Kapilvastu, Thandeukhuri-Gadhwa/Dang, Tribhuvan Chowk-Nepalgunj/Banke, and Gulariya/Bardiya. The main questionnaire sample was N=60, with 30 male and 30 female respondents and age categories 15-29, 30-59, and 60+.

Their wordlist method is especially relevant for controlled sampling: at least two informants per survey point, selected as Awadhi mother-tongue speakers born in the village or nearby and not having lived outside the village for extended periods. Wordlist responses were elicited using Nepali prompts and transcribed in IPA.

Future Nepal-Awadhi sampling should record district/locality, local residence history, mother-tongue status, age band, sex/gender category, literacy/education, and reported knowledge/use of Nepali, Hindi, Bhojpuri, Urdu, Tharu, English, and other locally relevant languages where appropriate.

A future Nepal-Awadhi corpus should distinguish source evidence from design interpretation. Knowing Nepali or Hindi is not the same as frequent code-switching, and Hindi linguistic proximity is not evidence that Hindi will be the best ASR donor. Thakur and Yadav make Hindi and Nepali HIGH-confidence sociolinguistic contact languages, not validated ASR donors.

If the corpus includes only one district or one social network, evaluation claims must be framed as local or exploratory. Multi-region sampling is required before making broad Nepal-Awadhi claims. Speaker-disjoint splits remain required.

Future analysis should keep separate fields for:

- Language knowledge.
- Language use domain.
- Self-reported language attitude.
- Observed code-switching in transcripts.
- Donor-language exposure relevant to ASR interpretation.

## Phase 0E Model And Experiment Feasibility Notes

Phase 0E separates external practical baselines from controlled transfer models.

External practical baselines should answer: How well does a strong existing ASR system work on Nepal-Awadhi? Candidate systems include Whisper multilingual, SraVaani 1.0, IndicConformer-600M, MMS, and possibly Sarvam Saaras if API/data-governance terms are acceptable.

Controlled-transfer models should answer: What is the effect of Hindi vs Nepali donor data under matched conditions? Candidate systems should use the same base checkpoint, same tokenizer/transcription policy, same training procedure, same target data, same test set, and same decoding configuration. `facebook/w2v-bert-2.0` is the current strongest candidate because it requires downstream ASR fine-tuning and was used in Dialect Matters-style transfer experiments. A neutral IndicWav2Vec base may also be viable if checkpoint availability and reproducible recipes are verified.

The donor design `10h Hindi vs 10h Nepali vs 5h+5h` is not frozen. It may confound donor language with dataset source, speech style, recording quality, speaker count, transcription quality, domain, tokenizer/script, and previous model exposure. Hindi and Nepali remain HIGH-confidence sociolinguistic contact languages, but neither is proven to be a better ASR donor.

A minimum primary-question experiment would require a speaker-disjoint Nepal-Awadhi test set and zero-shot evaluation using 2-3 external baselines. Donor-transfer experiments, target-data scaling, and multiple-seed sweeps should remain later-stage designs until the data and compute budget are known.

## Final Phase 0 Experimental Gate

Minimum defensible path:

- ESSENTIAL: Practical zero-shot ASR evaluation on a speaker-disjoint Nepal-Awadhi test set with documented transcription and normalization policy.
- OPTIONAL: Nepal-Awadhi-only adaptation after enough target data exists and speaker-disjoint train/dev/test splits are possible.
- POSTPONE: Hindi donor transfer until a matched Hindi donor subset is selected and a no-donor/target-only baseline is defined.
- POSTPONE: Nepal-origin Nepali donor transfer until Nepal-origin donor provenance is verified and matchability against Hindi is defensible.
- POSTPONE: Hindi+Nepali donor transfer until single-donor conditions are controlled.
- ESSENTIAL IF RQ3 IS RETAINED: Sampled manual language-fidelity/error analysis after ASR outputs exist and annotation rules are defined.

Do not assume 5-10 hours is sufficient or necessary. Do not assume 10h Hindi vs 10h Nepali is the correct design. Donor subsets should be matched by hours, utterance count, speaker count, duration distribution, speech style, domain, recording condition, transcript quality, script/normalization, and license as far as practical.

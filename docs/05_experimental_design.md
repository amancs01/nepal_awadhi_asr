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

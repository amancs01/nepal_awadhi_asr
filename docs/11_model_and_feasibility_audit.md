# Purpose

Phase 0E audits ASR model/checkpoint feasibility before any model training, checkpoint download, or final model choice. The goal is to separate two different scientific roles:

- External/practical baseline: asks how well a strong existing ASR system works on Nepal-Awadhi.
- Controlled-transfer model: asks what changes when Hindi, Nepali, or Hindi+Nepali donor data are used under controlled conditions.

A model can be excellent for the first role and poor for the second if its prior exposure to Hindi, Nepali, Awadhi, or related varieties is broad, opaque, or uncontrolled.

# External baseline candidates

## Whisper multilingual

OpenAI's Whisper multilingual checkpoints are Transformer encoder-decoder ASR/speech-translation models released under the MIT license. The official model card lists sizes from tiny through large and turbo, with parameter counts ranging from 39M to approximately 1.55B; the GitHub README reports approximate inference VRAM from about 1GB for tiny/base, 5GB for medium, 10GB for large, and 6GB for turbo [https://github.com/openai/whisper], [https://github.com/openai/whisper/blob/main/model-card.md]. The Hugging Face large-v3 model card reports large-v3 training on 1M hours of weakly labelled audio plus 4M hours pseudo-labelled by large-v2 [https://huggingface.co/openai/whisper-large-v3].

Role: strong external practical baseline, especially zero-shot evaluation.

Main confound: training data is massive and weakly supervised; exact Awadhi, Hindi, Nepali, and neighboring-variety exposure is not controlled. Whisper can also hallucinate or normalize output toward dominant languages, so it is risky for causal donor-language conclusions.

## SraVaani 1.0

SraVaani 1.0 is a 430M parameter FastConformer ASR model with a hybrid TDT-CTC decoder, released by ARTPARK-IISc/SPIRE Lab under MIT, with gated Hugging Face access. The model page describes pretraining from scratch on the VAANI corpus, audio-image alignment, and supervised multilingual ASR fine-tuning across 65 Indian languages/dialects; the paper page reports self-supervised pretraining on 31,255h of VAANI speech and supervised fine-tuning on 31,263h labelled speech from 24 public datasets [https://vaani.iisc.ac.in/models/sravaani], [https://huggingface.co/ARTPARK-IISc/SraVaani-1.0], [https://huggingface.co/papers/2608.08235].

Role: strong Indic external practical baseline, especially if Awadhi support is confirmed in the release artifacts.

Main confound: because SraVaani uses VAANI and broad Indic fine-tuning, prior Awadhi/Hindi exposure is likely not separable from the target evaluation question. It is therefore not ideal for testing the causal effect of donor-language choice.

## IndicConformer-600M-Multilingual

AI4Bharat's IndicConformer-600M-Multilingual is a 600M parameter multilingual Conformer hybrid CTC+RNNT ASR model for 22 official Indian languages, released under MIT. The model card lists Hindi and Nepali support but not Awadhi [https://huggingface.co/ai4bharat/indic-conformer-600m-multilingual].

Role: open Indic baseline for Hindi/Nepali-supported behavior, not an Awadhi-specific system.

Main confound: no explicit Awadhi support and prior IN-22 supervised exposure make it unsuitable for Hindi-vs-Nepali donor causality.

## Sarvam Saaras v3/v4

Sarvam Saaras is a commercial/API ASR family supporting 23 languages: 22 Indian languages plus English. The current docs state Saaras v3 remains the recommended default and v4 is the latest model, with Hindi and Nepali support and modes for transcription, translation, verbatim, transliteration, and code-mixed output [https://docs.sarvam.ai/api/getting-started/models/saaras].

Role: optional commercial practical baseline if API access and data-governance terms are acceptable.

Main confound: closed model, hidden training data, no public fine-tuning path, and no explicit Awadhi support.

## Meta MMS-1B-all

Meta's MMS-1B-all is a Wav2Vec2-based multilingual ASR checkpoint with adapters, 1B parameters, CC-BY-NC-4.0 license, and fine-tuning/adapters across 1162 languages; the card says it can transcribe 1107 languages [https://huggingface.co/facebook/mms-1b-all].

Role: broad multilingual practical baseline, especially for language-coverage comparison.

Main confound: non-commercial license, very large checkpoint, and unclear exposure to Hindi/Nepali/Awadhi for our causal question.

# Controlled-transfer candidates

## facebook/w2v-bert-2.0

Meta's w2v-BERT 2.0 is a 600M parameter Conformer-based speech encoder released under MIT. The model card says it is pretrained on 4.5M hours of unlabeled audio covering more than 143 languages and requires fine-tuning for ASR [https://huggingface.co/facebook/w2v-bert-2.0]. The Hugging Face fine-tuning guide shows how to add a CTC head and fine-tune it for low-resource ASR [https://huggingface.co/blog/fine-tune-w2v2-bert]. Dialect Matters used w2v-bert-2.0 for cross-lingual transfer experiments, fine-tuning on 1-7 hours per language and evaluating across Devanagari-script VAANI varieties [https://arxiv.org/html/2601.04373v2].

Role: best current controlled-transfer candidate because the ASR head and donor fine-tuning can be defined consistently.

Main confound: pretraining is still huge and multilingual, so prior Hindi/Nepali exposure is not absent. However, the downstream donor stage can be controlled more cleanly than with an already multilingual ASR decoder.

## IndicWav2Vec / IndicWav2Vec-Hindi

AI4Bharat's IndicWav2Vec is a Wav2Vec2-based Indic speech model family with code and models released under MIT. The repository describes pretraining on 40 Indian languages and ASR fine-tuning/evaluation across public benchmarks [https://github.com/AI4Bharat/IndicWav2Vec]. Dialect Matters states IndicWav2Vec used 17,000 hours of unlabeled clean speech from YouTube and NewsOnAir across 40 Indic languages and used the Hindi fine-tuned checkpoint as a strong baseline [https://arxiv.org/html/2601.04373v2].

Role: prior-work comparison and possible controlled-transfer candidate if neutral base checkpoints and comparable Hindi/Nepali fine-tuning recipes can be verified.

Main confound: the Hindi-fine-tuned checkpoint is not neutral. It is useful for reproducing prior comparisons, but a Hindi-initialized ASR model should not be used as the only basis for Hindi-vs-Nepali donor conclusions.

# Pretraining exposure problem

The largest model-selection confound is previous language exposure. Whisper, SraVaani, MMS, IndicConformer, and Sarvam Saaras all have broad multilingual or Indic training exposure. This is good for practical performance, but bad for interpreting donor-language effects.

For donor-transfer experiments, the cleanest design is not simply "best model wins." It should use one base encoder/checkpoint, one tokenizer/transcription policy, matched donor hours, matched target data, identical optimizer/decoding settings, and identical evaluation sets. Even then, pretraining-language exposure remains a background confound that must be reported.

# Compute feasibility

Feasibility categories are rough and should be revised after the user's hardware is known.

| Model/stage | Inference feasibility | Fine-tuning feasibility | Notes |
| --- | --- | --- | --- |
| Whisper medium | MODERATE | MODERATE-HIGH | Official README reports about 5GB inference VRAM; fine-tuning needs more memory/engineering |
| Whisper large-v3 | MODERATE-HIGH | HIGH | About 10GB inference VRAM for large-family models; stronger baseline but heavier |
| Whisper turbo | MODERATE | UNKNOWN/MODERATE-HIGH | About 6GB inference VRAM; optimized for inference; fine-tuning path needs confirmation |
| SraVaani 1.0 | MODERATE | MODERATE-HIGH | 430M FP16 model, gated access, NeMo/custom workflow |
| MMS-1B-all | HIGH | HIGH | 1B parameters and large repo; non-commercial license |
| w2v-BERT 2.0 | MODERATE-HIGH | MODERATE-HIGH | 600M encoder; suitable for controlled fine-tuning if compute supports it |
| IndicWav2Vec | LOW-MODERATE | MODERATE | Smaller/older family, but exact checkpoint availability and recipes need confirmation |
| IndicConformer-600M | MODERATE-HIGH | UNKNOWN | Good inference baseline; custom-code/ONNX path; fine-tuning not audited |
| Sarvam Saaras | LOW local compute via API | Not available | Requires API/legal/data-governance review |

# Experimental-run budget

| Stage | Data requirement | Compute requirement | Expected runs | Main practical risk | Essential/optional |
| --- | --- | --- | --- | --- | --- |
| Zero-shot Nepal-Awadhi evaluation | Held-out Nepal-Awadhi test set with careful transcripts | LOW-MODERATE for inference; API if closed baseline | 2-5 baseline systems | No Nepal-Awadhi corpus yet; transcription standard not fixed | Essential for primary question |
| Nepal-Awadhi-only adaptation | Speaker-disjoint train/dev/test; likely several target-hour slices | MODERATE-HIGH | 1 model x several target sizes, plus seeds if possible | Too little data; overfitting; speaker leakage | Essential if adaptation is part of claim |
| Hindi donor + Nepal-Awadhi adaptation | Hindi donor set matched to Nepali by hours/style/quality | MODERATE-HIGH | 1-3 seeds per condition | Donor dataset mismatch; Hindi exposure already in base model | Essential for donor question only |
| Nepali donor + Nepal-Awadhi adaptation | Nepali donor set matched to Hindi by hours/style/quality | MODERATE-HIGH | 1-3 seeds per condition | Nepali donor data may differ in domain/script/audio quality | Essential for donor question only |
| Hindi+Nepali donor + Nepal-Awadhi adaptation | Matched total donor budget, e.g. balanced mix; hours not finalized | MODERATE-HIGH | 1-3 seeds | 5h+5h vs 10h single-donor comparison may confound total diversity and speaker count | Optional until single-donor design validated |
| Target-data scaling | Multiple Nepal-Awadhi training sizes | HIGH | Many runs across target-hour slices | Data scarcity; unstable estimates | Optional/secondary |
| Multiple random seeds | Same data/model repeated | HIGH | 3+ per key condition if compute permits | Compute multiplies quickly | Optional but desirable for donor claims |
| WER/CER evaluation | Gold transcripts and normalization policies | LOW | Once per output set | Text normalization can erase Awadhi/Hindi/Nepali distinctions | Essential |
| Manual language-fidelity analysis | Sampled errors, annotation guide, bilingual expertise | MODERATE human effort | Sample-based, not all outputs initially | No defensible annotation definition yet | Essential for language-fidelity question, optional for primary WER-only question |

# Essential experiments

Minimum to answer the primary cross-border/practical question:

1. Establish a speaker-disjoint Nepal-Awadhi test set with documented district/locality, speech style, and conservative transcription policy.
2. Run zero-shot inference from 2-3 practical baselines, likely Whisper large-v3 or medium, SraVaani 1.0 if access/support is confirmed, and one open Indic model such as IndicConformer or MMS if language support is workable.
3. Compare against existing Indian Awadhi resources only under clearly separated speech-style and provenance labels; do not call this a controlled India-vs-Nepal comparison unless recording and transcription conditions are matched.
4. Report WER/CER under both standard and conservative/minimal normalization if the evaluation policy is defined.

Minimum to answer the donor-transfer question later:

1. Choose a controlled base model, probably w2v-BERT 2.0 or a verified neutral IndicWav2Vec base.
2. Define matched Hindi and Nepali donor datasets by hours, speech style, transcript quality, script, speaker count, and domain.
3. Use identical training and decoding settings for Hindi, Nepali, and no-donor/target-only conditions.
4. Add Hindi+Nepali only after the single-donor comparison is well controlled.

# Optional experiments

- Full target-data scaling across many hour slices.
- 3+ random seeds for every condition if compute is limited.
- MMS/Sarvam/SraVaani comparisons beyond the main practical baseline set.
- Multi-donor mixtures beyond Hindi+Nepali.
- Full manual error annotation of all outputs; start with a sampled protocol.

# Risks

- No Nepal-Awadhi ASR corpus has been identified yet, so feasibility depends on later ethical data availability.
- 10h Hindi vs 10h Nepali vs 5h+5h is not automatically controlled. It may confound donor language with dataset source, speech style, recording quality, speaker diversity, transcription quality, domain, tokenizer/script behavior, and previous model exposure.
- Large multilingual models may normalize toward high-resource languages or hallucinate, creating false confidence if only normalized WER is reported.
- Nepali and Hindi are now HIGH-confidence sociolinguistic contact languages for Nepal-Awadhi, but this does not imply either is a good ASR donor.
- Licenses differ: MIT, CC-BY-NC, CC-BY, commercial API, and gated access cannot be mixed casually.

# Recommended shortlist

External/practical baselines:

1. Whisper large-v3 or Whisper medium: broad, strong, easy to run if compute allows; use medium if hardware is limited.
2. SraVaani 1.0: best Indic-specific baseline candidate if Awadhi support/access is confirmed.
3. IndicConformer-600M or Sarvam Saaras: IndicConformer for open reproducibility; Sarvam only if API/data-governance terms are acceptable.

Controlled-transfer candidates:

1. facebook/w2v-bert-2.0: strongest controlled-transfer candidate because it requires our own ASR fine-tuning head and was used in Dialect Matters/DonorRank-style experiments.
2. IndicWav2Vec neutral/base checkpoint if available and reproducible; use IndicWav2Vec-Hindi mainly as a prior-work comparison, not as a neutral donor-transfer base.

# Remaining unknowns

- User hardware: GPU model, VRAM, RAM, storage, operating system constraints, and whether cloud/GPU credits are available.
- Whether SraVaani's release artifacts explicitly include Awadhi and Nepali and how tokenization/scripts are handled.
- Whether MMS has verified Hindi, Nepali, and Awadhi adapters usable under license for this research.
- Whether a neutral IndicWav2Vec base checkpoint can be used reproducibly alongside matched Hindi/Nepali fine-tuning.
- Whether donor datasets can be matched by speech style, domain, speaker count, audio quality, transcription quality, and script.
- Whether final Nepal-Awadhi data will contain enough speakers and hours for adaptation, scaling, and seed-based conclusions.

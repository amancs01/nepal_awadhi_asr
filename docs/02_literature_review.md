# Literature Review

STATUS: PHASE 0 — RESEARCH VALIDATION

This audit verifies starting literature and nearby work. It does not establish final novelty, justify data collection, or authorize model training.

## 1. Awadhi Speech Resources

PAPER FINDS: Kumar et al. (2022) present an in-progress speech corpus for Awadhi, Bhojpuri, Braj, and Magahi in the 1st Workshop on Speech for Social Good. The ISCA page lists the paper, authors, venue, pages, and DOI: https://www.isca-archive.org/s4sg_2022/kumar22_s4sg.html. The PDF reports about 18 total hours, with Awadhi 04:46:30, and identifies the Awadhi region as Pratapgarh, Uttar Pradesh: https://www.isca-archive.org/s4sg_2022/kumar22_s4sg.pdf.

PAPER FINDS: The same paper reports 10 speakers per language and describes two collection phases: translated Hindi elicitation sentences and lifecycle narration prompts. Transcription is in Devanagari, exported in TextGrid and CoNLL-U, with POS, morphology, and Universal Dependencies annotation.

OUR INTERPRETATION: An Awadhi speech corpus already exists for Indian Awadhi. The paper does not establish a Nepal-Awadhi corpus.

RELEVANCE TO PROJECT: Any claim of a first Awadhi corpus is contradicted. Any claim about Nepal-Awadhi remains unresolved.

PAPER FINDS: Sood et al. (2025) use SpeeD-IA and VAANI for a cascaded speech-to-speech translation pipeline involving Awadhi, Bhojpuri, Braj Bhasha, and Magahi. The ACL Anthology page verifies the paper metadata: https://aclanthology.org/2025.wat-1.5/.

OUR INTERPRETATION: Awadhi speech resources have already been used beyond corpus creation, including in downstream speech technology.

## 2. Existing Awadhi ASR

PAPER FINDS: Kumar et al. (2022) report Hindi ASR baselines, Kaldi monophone/triphone baselines, and transfer learning with wav2vec-large-xlsr-53. For Awadhi, reported WERs include Azure Hindi 83.2, Google Hindi 79.9, mono 86.3, tri1 80.9, tri2b 82.1, and tri3b 82.5. The wav2vec row has a dash in the Awadhi cell, so no Awadhi-specific wav2vec WER should be inferred from that table.

PAPER FINDS: Sood et al. (2025) fine-tune Whisper-Medium on VAANI and lifecycle narrations from SpeeD-IA and compare against Google STT. Their ASR table reports Awadhi WER 0.7321 for Google STT and 0.4542 for fine-tuned Whisper-Medium: https://aclanthology.org/2025.wat-1.5.pdf.

OUR INTERPRETATION: Awadhi ASR has already been studied. Whisper fine-tuning for Awadhi-related Hindi Belt dialect data has also already been attempted.

RELEVANCE TO PROJECT: First Awadhi ASR and generic low-resource Awadhi ASR are not viable unqualified contribution claims.

## 3. Cross-Lingual / Dialectal ASR Transfer

PAPER FINDS: Dhasmana, Srivastava, and Chiang (2026), accepted at VarDial 2026, study cross-lingual ASR transfer for Devanagari-script Indic varieties using spontaneous, noisy, and code-mixed speech. The arXiv page verifies title, authors, acceptance note, and DOI link: https://arxiv.org/abs/2601.04373.

PAPER FINDS: The paper uses VAANI and describes it as spontaneous image-description speech from 156,534 speakers across 773 districts of India, with over 150,000 hours and about 10 percent transcribed. It includes Awadhi as a dialect/nonstandard variety in the Devanagari subset: https://arxiv.org/html/2601.04373v2.

PAPER FINDS: Their cross-lingual experiments fine-tune w2vBERT on 1 to 7 hours per language and evaluate across VAANI Devanagari-script test sets. They find phylogenetic distance is useful but insufficient, and that dialectal fine-tuning can outperform larger standardized-language fine-tuning for dialectal targets.

OUR INTERPRETATION: This is a high-overlap paper for the proposed donor-transfer and dialectal robustness frame, including Awadhi, but it is India/VAANI-based rather than Nepal-Awadhi.

## 4. Donor-Language Selection

PAPER FINDS: Dhasmana, Srivastava, and Chiang (2026) introduce DonorRank as a learning-to-rank framework for predicting effective donor languages for zero-shot ASR. The arXiv page verifies title, authors, date, and preprint status: https://arxiv.org/abs/2608.11441.

PAPER FINDS: DonorRank evaluates VAANI-D and WAXAL. For VAANI-D, the paper caps donor fine-tuning data at seven hours per language and uses one hour of test data per language. Awadhi is one of six primary low-resource target languages in the VAANI-D donor experiments: https://arxiv.org/html/2608.11441.

PAPER FINDS: For Awadhi target, the reported top donor is `hne`, with CER 22.4 and WER 55.0, while the Hindi baseline gives CER 34.3 and WER 81.2. Multi-donor transfer is also evaluated for six target languages including Awadhi.

OUR INTERPRETATION: Awadhi has already been included in donor-language selection and multi-donor transfer work. The donor code `hne` needs exact language-name verification before narrative use.

RELEVANCE TO PROJECT: This strongly narrows the possible donor-transfer contribution. What remains untested is Nepal-Awadhi, especially Hindi versus Nepali donor comparison under controlled conditions.

## 5. Speech Technology For Languages Of Nepal

PAPER FINDS: Sharma et al. (2026) present Nwāchā Munā for Nepal Bhasha ASR and proximal Nepali transfer. The arXiv page verifies title, authors, accepted-in-CHiPSAL@LREC note, and core abstract: https://arxiv.org/abs/2603.07554.

PAPER FINDS: The full text reports a 5.39-hour manually transcribed Devanagari corpus, 18 speakers from Banepa, Dhulikhel, Panauti, and Patan, 16 kHz mono WAV, and a mix of field recordings plus about one hour of web-sourced audio: https://arxiv.org/html/2603.07554.

PAPER FINDS: The study evaluates NepConformer and Whisper-Small, with zero-shot NepConformer CER 52.54 and best reported CER 17.59 after augmentation. It explicitly states the split preserves speaker representation across train/validation/test rather than enforcing strict speaker independence.

OUR INTERPRETATION: This is not Awadhi, but it is a close methodological analogue for Nepal-based low-resource ASR and Nepali proximal transfer. Its non-speaker-disjoint split is a useful warning for our design.

## 6. Geographic / Dialect Generalization

PAPER FINDS: Kantharuban, Vulić, and Korhonen (2023) quantify dialect gaps across machine translation and ASR. The ACL Anthology page verifies it as Findings of ACL: EMNLP 2023 and summarizes that dialect performance disparities exist and are related to training data, dataset construction, and social/economic/linguistic factors: https://aclanthology.org/2023.findings-emnlp.481/.

OUR INTERPRETATION: This supports the general motivation that dialectal ASR gaps are a recognized research problem. It has not yet been audited here for Awadhi or South Asian specifics.

PAPER FINDS: Dhasmana et al. (2026) directly study Indic dialectal transfer and show that geography/phylogeny alone is insufficient for ASR transfer behavior: https://arxiv.org/html/2601.04373v2.

OUR INTERPRETATION: Geographic or dialect generalization must be designed carefully; language label alone is not enough.

## 7. Language-Fidelity And Code-Switch-Related ASR Errors

PAPER FINDS: Dhasmana et al. (2026) analyze Garhwali ASR errors and report bias toward Hindi from pre-training. For non-Hindi word handling, their table reports that fine-tuned w2vBERT preserves 34.8 percent of non-Hindi terms and converts 23.3 percent to Hindi, while IndicWav2Vec-Hindi preserves 4.2 percent and converts 37.3 percent to Hindi: https://arxiv.org/html/2601.04373v2.

PAPER FINDS: Sharma et al. (2026) report that KenLM shallow fusion reduced WER but slightly increased CER because the language model can favor standard spellings over phonetically correct local forms. They also report code-mixing, overlapping speech, and acoustic variability as pseudo-labeling error sources: https://arxiv.org/html/2603.07554.

OUR INTERPRETATION: The broad phenomenon we called language fidelity overlaps with existing work on bias toward pre-training languages, orthographic normalization, lexical substitution, and code-mixed ASR errors. Our terminology should remain provisional.

## 8. What The Literature Currently Leaves Unanswered

- No verified paper in this pass studies Nepal-Awadhi ASR specifically.
- No verified paper in this pass reports a Nepal-Awadhi speech corpus.
- No verified paper in this pass directly compares Indian Awadhi and Nepal-Awadhi ASR under controlled conditions.
- No verified paper in this pass compares Hindi versus Nepali as donor languages for Nepal-Awadhi.
- Awadhi donor selection has already been studied in VAANI-D, so a generic Awadhi donor-selection claim is too broad.
- Dominant-language normalization is already studied for Garhwali-to-Hindi bias; a Nepal-Awadhi version would need sharper definition and evidence.
- Read versus spontaneous speech remains a key confound rather than a settled contribution.

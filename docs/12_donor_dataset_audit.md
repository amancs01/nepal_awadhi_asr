# Purpose

Phase 0F audits whether publicly available Hindi and Nepal-origin Nepali speech datasets can be matched for a controlled donor-language transfer experiment into Nepal-Awadhi ASR.

This phase does not choose final donor datasets. It records what is available, what is documented, and what remains confounded. No audio was downloaded, no models were trained, and no final donor-hour decision was made.

# Evaluation categories

- A. Strongly suitable for controlled Hindi-vs-Nepal-Nepali donor comparison.
- B. Potentially suitable with matching/subsetting.
- C. Useful only as an external baseline or auxiliary reference.
- D. Not suitable for controlled donor comparison.

No candidate is rated A yet because no audited Hindi/Nepali pair has been verified as matched on country/geography, speech style, channel, speakers, transcription quality, domain, train/dev/test policy, and license.

# Nepal-origin Nepali candidates

## OpenSLR SLR54 - Large Nepali ASR training data set

- Source URL: https://www.openslr.org/54/
- Language: Nepali.
- Geographic provenance: Nepali corpus in the Google crowd-sourced speech corpora family. The SLTU paper says speakers were native-speaker volunteers in the respective region; the OpenSLR page labels this Nepali but does not expose district-level geography in the summary [https://www.isca-archive.org/sltu_2018/kjartansson18_sltu.html], [https://www.openslr.org/54/].
- Total audio hours: commonly reported around 165h in downstream documentation; OpenSLR summary reports approximately 157K utterances rather than hours [https://www.openslr.org/54/].
- Speakers: third-party corpus lists report 527 speakers; OpenSLR exposes anonymized UserID but no biographical information [https://github.com/coqui-ai/open-speech-corpora], [https://www.isca-archive.org/sltu_2018/kjartansson18_sltu.html].
- Demographics: biographical information unavailable; speakers are an unspecified gender mix according to the SLTU paper.
- Speech style/domain: prompted/read utterances from textual prompts; ASR training corpus.
- Recording conditions: portable consumer electronics in reasonably quiet environments.
- Transcript availability: yes; `utt_spk_text.tsv` with FileID, anonymized UserID, transcription.
- Script: Nepali/Devanagari assumed from language, but exact script policy should be verified from files before use.
- License/access: CC BY-SA 4.0.
- Train/dev/test: no official split on OpenSLR; downstream benchmark repos create speaker-disjoint 80/10/10 splits.
- Speaker metadata: anonymized speaker IDs available; no biography/district demographics.
- Matched subset possible: potentially yes by duration and speaker-disjoint IDs, but style/channel must be matched to Hindi.
- Major confounds: Nepal-origin likely but not district-specific; demographic metadata missing; read style may mismatch Hindi donor candidates.
- Feasibility rating: B.

## OpenSLR SLR43 - High quality TTS data for Nepali

- Source URL: https://www.openslr.org/43/
- Language: Nepali (`ne-NP`).
- Geographic provenance: OpenSLR explicitly says this dataset was collected by Google in Nepal.
- Total audio hours: UNKNOWN in the OpenSLR summary; downstream Kriti data record reports 2.796h from OpenSLR43.
- Speakers: multi-speaker female-speaker package; exact number UNKNOWN from audited summary.
- Demographics: female speakers indicated by file package; more detailed demographic data UNKNOWN.
- Speech style/domain: high-quality TTS/read speech.
- Recording conditions: high-quality transcribed audio; exact device/environment UNKNOWN from summary.
- Transcript availability: yes; `line_index.tsv` with filename and transcription.
- Script: Nepali/Devanagari expected; exact normalization must be verified.
- License/access: CC BY-SA 4.0.
- Train/dev/test: no ASR-style split documented in summary.
- Speaker metadata: speaker identification number prepended to filename.
- Matched subset possible: possible only for read/TTS-style donor experiments; too narrow for spontaneous donor matching.
- Major confounds: TTS-style/clean read speech may not match Hindi spontaneous/read corpora; female-heavy or female-only source.
- Feasibility rating: C or B only for a tightly read-speech donor design.

## OpenSLR SLR143 - Nepali Text-to-Speech Data (Male and Female)

- Source URL: https://www.openslr.org/143/
- Language: Nepali.
- Geographic provenance: Nepal-origin not directly established in audited summary; Nepali language and TTS purpose only.
- Total audio hours: UNKNOWN in summary; package size 173MB.
- Speakers: male and female voices; count UNKNOWN.
- Demographics: male/female split only.
- Speech style/domain: TTS/read speech.
- Recording conditions: UNKNOWN.
- Transcript availability: yes; separate TSV files for male and female audio with audio_id and corresponding sentences.
- Script: Nepali/Devanagari expected but not verified.
- License/access: CC BY-NC-SA 4.0 according to OpenSLR page.
- Train/dev/test: not documented.
- Speaker metadata: limited by male/female file organization.
- Matched subset possible: weak; only for clean read/TTS donor comparison.
- Major confounds: provenance and speaker count not documented in summary; noncommercial ShareAlike; TTS domain.
- Feasibility rating: C.

## FLEURS Nepali (`ne_np`)

- Source URL: https://huggingface.co/datasets/google/fleurs
- Language: Nepali locale `ne_np`.
- Geographic provenance: locale label is Nepal-oriented, but speaker origin/residence is not documented in the audited dataset card. Do not treat as fully verified Nepal-origin without further metadata.
- Total audio hours: around 10h supervision per language in FLEURS.
- Speakers: train speakers differ from dev/test speakers; exact Nepali speaker count not in audited summary.
- Demographics: gender field available.
- Speech style/domain: read speech from FLoRes dev/devtest parallel sentences.
- Recording conditions: FLEURS controlled benchmark; exact device/environment needs paper inspection.
- Transcript availability: yes; transcription and raw_transcription fields.
- Script: Nepali/Devanagari expected for `ne_np`, exact text conventions must be inspected.
- License/access: CC BY 4.0.
- Train/dev/test: yes; official train/validation/test.
- Speaker metadata: limited; gender available, not full speaker geography.
- Matched subset possible: yes against FLEURS Hindi (`hi_in`) for parallel/read donor data, but Nepal-origin speaker provenance remains incomplete.
- Major confounds: fixed translated sentence domain; small size; locale is not full speaker-origin evidence.
- Feasibility rating: B.

## Mozilla Common Voice Nepali (`ne-NP`)

- Source URL: https://commonvoice.mozilla.org/en/datasets
- Language: Nepali locale `ne-NP`.
- Geographic provenance: locale suggests Nepal Nepali, but speaker residence/origin is self-declared or unavailable depending release fields; do not treat as verified Nepal-origin without metadata inspection.
- Total audio hours: downstream Nepali benchmark summary reports approximately 5h for Common Voice Nepali; current Mozilla listing should be checked by release.
- Speakers: UNKNOWN from audited Mozilla summary.
- Demographics: Common Voice releases generally include self-declared age/gender/accent fields where provided.
- Speech style/domain: crowd-sourced read speech.
- Recording conditions: user-contributed MP3; variable devices/environments.
- Transcript availability: yes in TSV/MP3 release format.
- Script: Nepali/Devanagari expected but release text must be inspected.
- License/access: CC0-1.0; terms prohibit attempting to identify speakers and restrict re-hosting/re-sharing.
- Train/dev/test: Common Voice provides standard splits.
- Speaker metadata: limited self-declared metadata where available.
- Matched subset possible: potentially, especially against Common Voice Hindi, but speaker geography and quality variation are confounds.
- Major confounds: small size, noisy/variable quality, uncertain Nepal-origin beyond locale.
- Feasibility rating: B/C.

# Hindi candidates

## FLEURS Hindi (`hi_in`)

- Source URL: https://huggingface.co/datasets/google/fleurs
- Language: Hindi locale `hi_in`.
- Geographic provenance: India locale; exact speaker state/district origin not documented in audited card.
- Total audio hours: around 10h supervision per language.
- Speakers: train speakers differ from dev/test speakers; exact Hindi speaker count not in audited summary.
- Demographics: gender field available.
- Speech style/domain: read speech from FLoRes parallel sentences.
- Recording conditions: controlled benchmark; exact device/environment needs paper inspection.
- Transcript availability: yes; transcription and raw_transcription.
- Script: Devanagari expected.
- License/access: CC BY 4.0.
- Train/dev/test: yes.
- Speaker metadata: limited.
- Matched subset possible: strong candidate to pair with FLEURS Nepali because content/style/splits are parallel, but geography metadata is limited.
- Major confounds: sentence translation/read benchmark domain; not necessarily representative of Hindi donor data for Nepal-Awadhi natural speech.
- Feasibility rating: B.

## Kathbath Hindi

- Source URL: https://huggingface.co/datasets/ai4bharat/Kathbath
- Language: Hindi.
- Geographic provenance: India; full Kathbath covers 203 Indian districts across 12 Indian languages.
- Total audio hours: full dataset 1,684h across 12 languages; IndicSUPERB reports Hindi duration 150.2h.
- Speakers: full dataset 1,218 contributors; IndicSUPERB reports Hindi male speakers 58 and female speakers 63.
- Demographics: gender available in filenames; other metadata requires gated access/file inspection.
- Speech style/domain: labelled read speech benchmark; clean and noisy split variants reported in IndicSUPERB.
- Recording conditions/channels: m4a files; clean/noisy split organization; details need paper/card inspection after access.
- Transcript availability: yes; transcript files.
- Script: Hindi/Devanagari expected.
- License/access: CC BY 4.0; Hugging Face gated contact-info acceptance.
- Train/dev/test: clean train/valid/test-known/test-unknown and noisy test splits documented.
- Speaker metadata: speaker and gender encoded in filename.
- Matched subset possible: good Hindi read-speech donor candidate if paired with similarly read Nepal-origin Nepali; geography still India-broad.
- Major confounds: India-only district coverage; read speech; gated access; speaker geography details need metadata inspection.
- Feasibility rating: B.

## Gram Vaani / OpenSLR SLR118 Hindi ASR Challenge

- Source URL: https://www.openslr.org/118/
- Language: Hindi regional variations.
- Geographic provenance: India; collected by Gram Vaani social technology enterprise; exact speaker region metadata requires metadata file inspection.
- Total audio hours: approximately 1111h total; 100h labelled train, 5h labelled dev, 3h eval, 1000h unlabelled.
- Speakers: UNKNOWN from audited source.
- Demographics: metadata exists but fields not inspected.
- Speech style/domain: spontaneous telephone speech with regional variations, natural background, noisy crowdsourced transcriptions.
- Recording conditions/channels: telephone quality, MP3, mixed sampling rates 8kHz-48kHz.
- Transcript availability: labelled train/dev/eval have transcripts; unlabelled portion speech-only.
- Script: Hindi/Devanagari expected; exact conventions must be inspected.
- License/access: free for academic use; commercial use requires permission from Gram Vaani.
- Train/dev/test: challenge split exists.
- Speaker metadata: metadata tarball exists for all challenge data.
- Matched subset possible: difficult unless matched to spontaneous/telephone Nepal-origin Nepali, which has not been identified.
- Major confounds: telephone channel, spontaneous style, transcription noise, regional variation; poor match to read Nepali corpora.
- Feasibility rating: C for controlled donor comparison; useful for robustness baseline.

## Mozilla Common Voice Hindi

- Source URL: https://mozilladatacollective.com/datasets/cmqiod71900zgnr07uiyw57br
- Language: Hindi.
- Geographic provenance: Hindi locale; exact country/state speaker origin not fully documented in audited page.
- Total audio hours: Common Voice Scripted Speech 26.0 Hindi reports 26.67h recorded and 15.6h validated.
- Speakers: 480 speakers.
- Demographics: self-declared age/gender distributions available on dataset page.
- Speech style/domain: community-contributed read speech from sentence corpus.
- Recording conditions/channels: MP3, variable contributors/devices.
- Transcript availability: yes.
- Script: Hindi/Devanagari expected.
- License/access: CC0-1.0 with Common Voice restrictions including no speaker identification and no re-host/re-share.
- Train/dev/test: Common Voice standard split files expected.
- Speaker metadata: self-declared limited metadata available.
- Matched subset possible: potentially with Common Voice Nepali, if Nepal-origin and quality metadata are acceptable.
- Major confounds: crowd-sourced quality variation; geographic provenance may be generic; smaller validated hours.
- Feasibility rating: B/C.

## IndicVoices Hindi

- Source URL: https://github.com/AI4Bharat/IndicVoices
- Language: Hindi among 22 Indian languages.
- Geographic provenance: India; full corpus covers 208 Indian districts.
- Total audio hours: 12,000h total across 22 languages; 3,200h transcribed, median 122h/language. Hindi-specific hours require dataset metadata inspection.
- Speakers: 22,563 total speakers across 22 languages; Hindi-specific speaker count UNKNOWN from audited README.
- Demographics: designed for cultural, linguistic, and demographic diversity; exact Hindi metadata needs access/inspection.
- Speech style/domain: natural and spontaneous speech: 8% read, 76% extempore, 15% conversational.
- Recording conditions/channels: collection platform described; exact Hindi channel conditions need metadata inspection.
- Transcript availability: 3,200h transcribed subset overall.
- Script: Hindi/Devanagari expected.
- License/access: access through AI4Bharat dataset portal; exact per-file conditions need review.
- Train/dev/test: UNKNOWN from audited README.
- Speaker metadata: likely available, but fields need inspection.
- Matched subset possible: potentially if a comparable Nepal-origin Nepali spontaneous/extempore corpus exists; none identified yet.
- Major confounds: India-only geography; Hindi-specific hours/speakers unknown; style may not match available Nepal-origin Nepali corpora.
- Feasibility rating: B for Hindi donor pool, but not matchable yet.

## TDIL/IIT Madras Hindi ASR Challenge read speech

- Source URL: https://www.tdil-dc.in/index.php?id=170&option=com_content&view=article
- Language: Hindi.
- Geographic provenance: India; volunteers read newspaper-derived text. Exact speaker regions UNKNOWN.
- Total audio hours: 40h train, 5h development, 5h evaluation.
- Speakers: UNKNOWN from audited page.
- Demographics: UNKNOWN.
- Speech style/domain: read speech.
- Domain/content: newspapers; politics, sports, entertainment, etc.
- Recording conditions/channels: UNKNOWN from audited page.
- Transcript availability: yes, corresponding transcriptions.
- Script: Hindi/Devanagari expected.
- License/access: released for research challenge use; exact ongoing access terms need confirmation.
- Train/dev/test: yes.
- Speaker metadata: UNKNOWN.
- Matched subset possible: possible by speech style/hours if paired with read Nepal-origin Nepali, but geography and metadata limitations remain.
- Major confounds: older challenge/access uncertainty; speaker geography unknown.
- Feasibility rating: B/C.

# Cross-language matchability assessment

| Candidate pair | Matchability | Rating | Reason |
| --- | --- | --- | --- |
| FLEURS Hindi hi_in vs FLEURS Nepali ne_np | Best content/style match | B | Parallel sentence source, similar size, official splits, CC BY 4.0. Weakness: Nepali speaker Nepal-origin is locale-based, not fully proven in audited docs. |
| Common Voice Hindi vs Common Voice Nepali | Possible crowd-read match | B/C | Same collection framework and CC0, but variable quality, small Nepali size, and speaker geography uncertainty. |
| Kathbath Hindi vs OpenSLR SLR54 Nepali | Possible read-speech match | B | Both sizeable and transcribed; speaker IDs available. Weakness: different collection frameworks, licenses, domains, and demographic metadata. |
| TDIL/IITM Hindi read challenge vs OpenSLR SLR54 Nepali | Possible read-speech match | B/C | Similar read-speech ASR framing, but Hindi speaker geography and ongoing access terms are unclear. |
| Gram Vaani Hindi vs OpenSLR SLR54/FLEURS/Common Voice Nepali | Poor controlled match | C | Hindi is spontaneous telephone speech; Nepali candidates are mostly read/clean/crowdsourced. Useful for robustness, not clean donor comparison. |
| IndicVoices Hindi vs available Nepal-origin Nepali | Not yet matched | B/C | Strong Hindi metadata/style potential, but no comparable Nepal-origin Nepali spontaneous corpus identified. |
| SLR43/SLR143 Nepali TTS vs Hindi read corpora | Narrow match only | C | Clean TTS/read domain may be useful as auxiliary controlled read data, but not representative donor speech. |

# Feasibility assessment

## A. Strongly suitable for controlled Hindi-vs-Nepal-Nepali donor comparison

None yet. No audited pair currently has verified matching across geography, speech style, channel, speaker metadata, demographic balance, transcript quality, split policy, and license.

## B. Potentially suitable with matching/subsetting

- FLEURS Hindi (`hi_in`) vs FLEURS Nepali (`ne_np`): strongest same-framework candidate, but Nepal-origin speaker provenance needs verification beyond locale.
- Kathbath Hindi vs OpenSLR SLR54 Nepali: sizeable read-speech option, but cross-dataset style/domain/license differences must be controlled.
- Common Voice Hindi vs Common Voice Nepali: same framework and permissive license, but smaller/noisier and provenance depends on metadata.
- TDIL/IITM Hindi read challenge vs OpenSLR SLR54 Nepali: possible if access and metadata can be verified.
- IndicVoices Hindi: promising Hindi source only if paired with a comparable Nepal-origin Nepali dataset, which has not yet been identified.

## C. Useful only as an external baseline or auxiliary reference

- Gram Vaani SLR118 Hindi: valuable spontaneous telephone Hindi, but not a clean match to current Nepal-origin Nepali candidates.
- OpenSLR SLR43 Nepali TTS and SLR143 Nepali TTS: useful for clean read/TTS reference, weak for donor-transfer into natural Nepal-Awadhi.

## D. Not suitable

No dataset is permanently rejected at this phase, but any dataset with unverifiable speaker geography, unclear license, no transcripts, or no speaker/split metadata should be excluded from controlled donor experiments until resolved.

# Main design implications

The planned donor comparison, Hindi donor data vs Nepal-origin Nepali donor data, is plausible but not yet matched. The safest near-term design is likely to begin with a same-framework, read-speech comparison such as FLEURS Hindi vs FLEURS Nepali or Common Voice Hindi vs Common Voice Nepali, while documenting that this controls format more than sociolinguistic realism.

For a more realistic donor condition, Hindi has stronger spontaneous resources than Nepal-origin Nepali currently does. That asymmetry is a major confound: using Gram Vaani or IndicVoices Hindi against read Nepali would compare donor language plus speech style/channel/domain, not donor language alone.

# Remaining unknowns

- Whether FLEURS `ne_np` speaker provenance can be documented as Nepal-origin rather than only Nepal-locale.
- Exact current hours/speakers and metadata fields for Common Voice Nepali.
- Whether OpenSLR SLR54 can be subset by speaker while maintaining enough hours and whether any geography metadata exists beyond anonymized speaker ID.
- Hindi speaker geography for FLEURS, Common Voice, Kathbath, TDIL/IITM challenge data, and Gram Vaani metadata.
- Whether Hindi and Nepali donor subsets should be matched by hours, utterance count, speaker count, duration distribution, transcript length, or all of these.
- Whether license mixing across CC BY-SA, CC BY, CC0, and academic-use-only data is acceptable for the final experiment artifacts.

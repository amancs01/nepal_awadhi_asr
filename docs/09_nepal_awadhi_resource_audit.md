
# PHASE 0C - NEPAL-AWADHI RESOURCE EXISTENCE AUDIT

## Search strategy

The search deliberately went beyond ASR and ML repositories. Queries covered Awadhi/Avadhi spelling variants, Nepal-Awadhi phrases, district names, Terai/Lumbini terms, and resource types such as corpus, audio, recordings, ASR, sociolinguistic survey, thesis, oral history, language documentation, and Bible/media recordings.

Search targets included ACL Anthology, ISCA Archive, LREC/ELRA-style catalogues, OLAC/Glottolog links, PARADISEC, ELAR-style web search, Pangloss/COCOON-style search, Zenodo, Figshare, Hugging Face, OpenSLR, GitHub, Tribhuvan University eLibrary, Nepal census/statistics sources, Central Department of Linguistics / Linguistic Survey of Nepal references, Joshua Project, PeopleGroups, MegaVoice/GRN, Jesus Film, South Asia Bibles, and general web search.

Important distinction used throughout: a source can show Awadhi is spoken in Nepal without proving that a particular audio file was recorded in Nepal or spoken by Nepal-origin Awadhi speakers.

## Confirmed Nepal-Awadhi speech resources

No dedicated Nepal-Awadhi ASR corpus has been identified in the resources audited to date.

Confirmed Nepal-labeled or Nepal-linked audio/media resources were found, but none yet has enough provenance and rights information to treat it as an ASR-ready Nepal-Awadhi speech corpus.

| Resource | Evidence | Audio | Transcript | Speaker Nepal-origin evidence | ASR usability | Confidence |
| --- | --- | --- | --- | --- | --- | --- |
| Jesus Film Audio - Awadhi, Nepal | MegaVoice lists reference M035619, language "Awadhi, Nepal", country Nepal, publisher CRU, runtime 171 min | Yes, audio/media listing | UNKNOWN | Label says Awadhi, Nepal; no speaker origin or recording location found | Not currently usable without license/transcript/provenance review | MEDIUM as Nepal-labeled audio; LOW as speaker-provenance corpus |
| Dhaka-Dhoti Awadhi rap | Kathmandu Post reports an Awadhi rap by Deepak Kahar, a native of Rudrapur, Rupandehi | Yes, public music/video link reported | Lyrics/video likely public, but no corpus transcript | Stronger individual artist geography than religious media, but it is a song/performance | Not suitable for ASR corpus without permission; music domain confound | MEDIUM as Nepal-Awadhi recorded media; LOW as dataset |

## Possible but unverified resources

| Resource | Why possible | Main uncertainty | Action needed |
| --- | --- | --- | --- |
| Global Recordings Network / Words of Life Awadhi | MegaVoice lists Awadhi audio and related countries Nepal > India; GRN/MegaVoice describes Words of Life as recorded by mother-tongue speakers | Country field is unclear; no speaker origin, recording location, transcript, or license details found | Contact GRN/MegaVoice for metadata and rights; do not download/use yet |
| South Asia Bibles / Faith Comes By Hearing / Bible.is Awadhi media | South Asia Bibles lists Awadhi Audio Bible and Jesus Films and notes Awadhi in Lumbini and Sudurpashchim Province | It does not establish that the audio speakers are Nepal-origin or that aligned transcripts can be reused | Rights/provenance inquiry only |
| Linguistic Survey of Nepal Awadhi survey | Glottolog records Thakur and Yadav 2013 as a 92-page LinSuN/CDL Tribhuvan University sociolinguistic report; CDL download listing includes Awadhi | Survey may include wordlists, questionnaires, or field notes; no archived audio identified yet | Inspect full report and ask CDL whether any audio/field recordings exist |
| TU thesis field materials | Multiple TU theses collected primary Awadhi data from Nepal districts | Theses report questionnaires/interviews but do not expose audio; original field notes/recordings may be private or nonexistent | Metadata-only institutional inquiry if ethically appropriate |

## Text/linguistic resources only

| Resource | Type | Nepal-specific value | Audio status |
| --- | --- | --- | --- |
| A Sociolinguistic Survey of Awadhi, Thakur and Yadav 2013 | Sociolinguistic survey report | Likely best Nepal-specific language survey lead | UNKNOWN; no public audio identified |
| Case in English, Nepali and Awadhi, TU thesis 2011 | Linguistic thesis | 60 Awadhi native speakers in Gadhawa VDC, Deukhuri valley, Dang district | No accessible audio identified |
| Pronominal of English and Awadhi, TU thesis 2010 | Linguistic thesis | 50 native Awadhi speakers in Banke district | No accessible audio identified |
| A Comparative Study of English and Awadhi Kinship Terms, TU thesis 2006 | Linguistic thesis | Awadhi speakers of Rupandehi district | No accessible audio identified |
| Attitudes of Awadhi Students towards Learning English, TU thesis 2025 | Education/attitudes thesis | Awadhi-speaking learners in Bijayanagar, Kapilvastu district | No accessible audio identified |
| National Population and Housing Census 2021 / Languages in Nepal | Demographic source | Confirms Avadhi/Awadhi is a major mother tongue in Nepal; useful for sampling frame | Not an audio source |
| Glottolog / WALS / ASJP | Typological and classification resources | Confirm Awadhi is associated with India and Nepal | Not audio sources |
| Joshua Project / PeopleGroups | Ethnoreligious/language-resource directory | Points to Nepal Awadhi-speaking people groups and media resources | Directory only; linked media requires separate audit |

## Resources rejected and why

| Resource | Reason rejected or deferred |
| --- | --- |
| SpeeD-IA | Audited in Phase 0B as Indian Awadhi, especially Pratapgarh, Uttar Pradesh; no Nepal-origin evidence found |
| VAANI | Audited in Phase 0B as India-focused; no Nepal-origin evidence found |
| Hugging Face 1rsh/speech-qa-awadhi-hi-karya and translate-awadhi-hi-karya | Contains Awadhi audio/text previews, but provenance points to Karya-style Indian resources and no Nepal-origin evidence was found |
| PrashantShuklaa/Awadhi_Speech_Dataset GitHub | Appears to aggregate/link external Awadhi resources; no independent Nepal-origin speech provenance found in README |
| HPLT Awadhi text | Text-only web corpus, not speech |
| HinDialect / Kavita Kosh related resources | Text/folk-song corpus, not speech recordings for Nepal-Awadhi ASR |
| OpenSLR | Searches did not identify an Awadhi or Nepal-Awadhi speech corpus; Nepali speech resources are not Awadhi |
| PARADISEC search results | Nepal language documentation collections exist, but no Awadhi Nepal collection was identified in audited search results |
| The Language Archive/MPI results mentioning Awadhi | Mentions Awadhi as a language known by a Nepalese researcher/collector in other documentation projects, not Awadhi primary speech data |
| ELRA catalogue search | No Awadhi/Nepal-Awadhi speech corpus identified in search results; catalogue itself remains a resource to revisit with direct filters if needed |

## Archives/repositories searched

- ACL Anthology
- ISCA Archive
- ELRA catalogue / LREC-style search
- OLAC via Glottolog and language-archives search results
- PARADISEC catalogue search
- ELAR-style web search
- Pangloss / COCOON-style web search
- Zenodo
- Figshare
- Hugging Face datasets
- OpenSLR
- GitHub
- Tribhuvan University eLibrary
- Central Department of Linguistics / Linguistic Survey of Nepal references
- Nepal National Statistics Office / census sources
- Joshua Project
- PeopleGroups.org
- MegaVoice / Global Recordings Network
- Jesus Film Project
- South Asia Bibles / Faith Comes By Hearing pointers
- General web search for Awadhi/Avadhi plus Nepal districts and Terai terms

## Remaining uncertainty

The largest uncertainty is institutional and archival rather than ML-facing: LinSuN/CDL and TU theses may have underlying field materials that are not indexed as public audio corpora. Religious media providers may also have Nepal-labeled Awadhi recordings, but without speaker metadata, transcripts, and reuse rights they cannot support a controlled ASR study.

A second uncertainty is terminology. Some Nepal resources use Avadhi, Awadhi, Abadhi, or community labels rather than ASR/corpus language. Future search should include Nepali-script terms and direct contact with Nepal institutions.

## Implications for the project

The local-corpus contribution became stronger but not settled. So far, Phase 0C found Nepal-specific linguistic evidence and Nepal-labeled audio/media, but no ASR-ready Nepal-Awadhi speech corpus with verified speaker provenance, aligned transcripts, speaker-disjoint metadata, and clear research licensing.

Therefore the project should continue to phrase the motivation carefully: existing audited resources have not yet yielded a dedicated Nepal-Awadhi ASR corpus. We should not claim that no Nepal-Awadhi corpus exists, and we should not claim first-ever status.

Before any collection, the next step should be metadata-only contact/audit of likely Nepal-specific holders: Central Department of Linguistics / LinSuN, TU thesis departments/authors where feasible, and religious-media providers for provenance and rights.

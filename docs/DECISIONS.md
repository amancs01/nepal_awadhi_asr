# Decisions

STATUS: PHASE 0 — RESEARCH VALIDATION

This log records important research decisions. Decisions can change when better evidence appears.

| Date | Decision | Reason | Evidence | Alternatives considered | Confidence | Can this decision change? |
| --- | --- | --- | --- | --- | --- | --- |
| 2026-09-01 | Proposal treated as hypothesis rather than specification. | The proposal's claims, novelty, datasets, methods, and research questions are not yet validated. | User project instructions. | Treat proposal as fixed plan. | HIGH | Yes, after review. |
| 2026-09-01 | Data collection delayed until literature/resource validation. | Collecting speech before confirming research need and ethics constraints risks invalid or unnecessary work. | User project instructions. | Begin immediate Nepal-Awadhi collection. | HIGH | Yes, with explicit approval and reviewed protocol. |
| 2026-09-01 | Speaker-disjoint evaluation required for future Nepal-Awadhi data. | Speaker overlap between training and test would weaken ASR generalization claims. | Standard ASR evaluation principle; project instruction. | Random utterance split without speaker controls. | HIGH | Unlikely, but implementation details may change. |
| 2026-09-01 | Avoid claiming first Nepal-Awadhi corpus until resource audit is complete. | Novelty claims require evidence. | User project instructions. | Claim first corpus immediately. | HIGH | Yes, after verified audit. |
| 2026-09-01 | Read and spontaneous speech should not automatically be mixed when making geographical claims. | Speech style can confound cross-border robustness conclusions. | User project instructions. | Pool all speech styles in one evaluation. | HIGH | Yes, if design explicitly models the confound. |
| 2026-09-01 | WER/CER alone may be insufficient for language-fidelity research. | Normalized error rates may hide Awadhi/Hindi/Nepali substitution behavior. | User project instructions. | Use only standard WER/CER. | MEDIUM | Yes, after evaluation-method review. |

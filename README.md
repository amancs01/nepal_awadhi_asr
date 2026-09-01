# Cross-Border Robustness and Contact-Language Transfer for Low-Resource Awadhi Speech Recognition in Nepal

STATUS: PHASE 0 — RESEARCH VALIDATION

No Nepal-Awadhi data collection or model-training experiment should begin until the Phase 0 research questions and experimental design are reviewed.

## Problem

Awadhi is spoken across political borders and in contact with larger regional languages. This project investigates whether automatic speech recognition (ASR) systems developed from existing Awadhi resources generalize reliably to Awadhi spoken in Nepal, and whether Hindi, Nepali, or combined donor-language strategies behave differently when only limited Nepal-Awadhi speech is available.

This is an academic research project. The existing proposal is an initial hypothesis, not a specification.

## Motivation

Low-resource ASR work can overstate generalization when language labels hide regional, dialectal, contact-language, recording-condition, or speech-style differences. Nepal-Awadhi may be scientifically interesting because it could involve cross-border variety differences, contact with Hindi and Nepali, and mixed read or spontaneous speech conditions. These possibilities are not yet established facts.

## Current Hypotheses

These hypotheses must be validated before being used as claims:

- ASR systems or resources based mainly on Indian Awadhi may not generalize equally well to Nepal-Awadhi.
- Hindi and Nepali may behave differently as donor languages for low-resource ASR adaptation.
- ASR errors may include systematic normalization of Nepal-Awadhi forms toward dominant Hindi or Nepali forms.
- Read speech and spontaneous or code-switched speech may show different ASR behavior.

## What Is Not Yet Established

- UNKNOWN: Whether Nepal-Awadhi ASR has already been studied.
- UNKNOWN: Whether Nepal-Awadhi speech datasets already exist.
- UNKNOWN: Whether existing Awadhi datasets include speakers from Nepal.
- UNKNOWN: Whether Hindi versus Nepali transfer for Nepal-Awadhi has already been evaluated.
- UNKNOWN: Whether language-fidelity or dominant-language normalization errors have been studied for this setting.
- UNKNOWN: Whether a 5-10 hour Nepal-Awadhi dataset would support scientifically valid experiments.

## Phase 0 Validation Process

Phase 0 exists to answer the basic scientific validation questions before any expensive or irreversible work:

- What has already been done?
- What Awadhi speech datasets exist?
- Where were speakers recorded, and where are they from?
- Are datasets Indian Awadhi, Nepal-Awadhi, or unclear?
- What speech styles and transcription conventions do they contain?
- What ASR models have already been evaluated on Awadhi?
- What donor-language transfer experiments already exist?
- What confounds would make proposed experiments scientifically invalid?

## Expected Later Phases

- Phase 1: Reviewed dataset/resource audit and final research question selection.
- Phase 2: Ethics-aware Nepal-Awadhi data plan, only if justified.
- Phase 3: Minimal metadata and validation tooling, if needed.
- Phase 4: Controlled pilot experiments, only after approval.
- Phase 5: Full experiments and analysis, only if pilot results justify them.

## Research Integrity Rules

- Never fabricate citations.
- Never fabricate dataset hours.
- Never fabricate speaker geography.
- Never fabricate experimental results.
- Never claim novelty from absence of a quick search result.
- Clearly distinguish peer-reviewed work from preprints.
- Record dataset and model version numbers whenever possible.
- Record licenses.
- Record uncertainty explicitly.
- If evidence conflicts, preserve the conflict instead of silently choosing one.
- Do not modify a research question merely to make the project appear novel.
- Negative findings are acceptable research results.

## Repository Layout

- `proposal/` - proposal drafts and hypothesis notes.
- `docs/` - research scope, questions, literature review, novelty analysis, dataset audit, experimental design, risks, and decisions.
- `research/` - structured literature, dataset, and model inventories.
- `data/` - empty reserved area for future approved data references or artifacts.
- `src/` - empty reserved area for future reviewed Phase 0 utilities or later implementation.
- `experiments/` - empty reserved area for future approved experiment records.
- `notebooks/` - empty reserved area for future approved analysis notebooks.
- `results/` - empty reserved area for future approved results.

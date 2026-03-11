# Changelog

All notable changes to PAIciente will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/).

## [2.0.0] — 2026-03-11

### Changed
- **Breaking:** Command prefix changed from `/` to `@` across the entire framework (`@child`, `@clinician`, `@debrief`, `@replay`, `@script`, `@escalation-map`, `@status`, `@child:inner`).
- Inner-state annotation (`@child:inner`) expanded from 4 fields to 7: now includes escalation path block (trajectory, next likely behavior, interrupt lever).
- `@replay` now re-outputs the last child turn and prompts the user for a new approach instead of auto-generating an alternative.
- `@debrief` now suspends child state (resumable via `@child`) instead of clearing it.
- Session continuity rule now explicitly handles context window limits: if continuity is lost, the system asks the user to re-supply history rather than fabricating prior context.
- Design notes version bumped to 2.0; added rationale sections for `@set` and trajectory carry-forward.
- Clinician recommendations now require bracketed citation numbers with references listed at the end.
- README.md description changed from blockquote to heading.

### Added
- `@set` command for direct state modulation: 8 parameters (feeling, arousal, trajectory, trust, fatigue, medication, hyperfocus, context) with verbose and numeric shorthand syntax.
- `@set persist` modifier to lock parameters against organic drift.
- `@set clear` to reset all manual overrides.
- `@set ?` to output the parameter table as quick reference.
- `@ [p]=[v]` shorthand alias for `@set`.
- Trajectory system (stable / building / near-threshold / at-threshold) that carries forward between turns.
- `[SET]` and `[organic]` markers in inner-state annotations when `@set` values are active.
- Conflict warnings and error handling for `@set` (out-of-range, malformed, internally inconsistent parameters).
- Leak guard: child persona deflects rather than disclosing injected context or backstory.
- New use case (§10.4): testing under compound stress conditions using `@set`.
- New design rationale sections (§6.5, §6.6): why `@set` exists and why trajectory carries forward.
- State modulation command table added to README.md, README.pt.md, and docs/overview.md.
- Sandbox links added to ChatGPT, Mistral, and Gemini implementation guides.
- `implementations/resources/chatgpt/` — split prompt: core instructions + 3 knowledge files for Custom GPT.
- `implementations/resources/mistral/` — reference PDFs (references, BibTeX, evidence map) for Le Chat agent.

### Removed
- Grok and Llama implementation guides excluded from tracked repo (gitignored) pending platform-specific adaptation.

### Updated
- All documentation files updated to reflect `@` command prefix and v2 features: README.md, README.pt.md, docs/overview.md, docs/personas.md, docs/workflow.md, docs/inner-state-guide.md, docs/behavior-map.md, docs/use-cases.md, docs/table-of-contents.md, prompt/design-notes.md, CONTRIBUTING.md, examples/format.md, all example templates, i18n/pt-PT/README.md.
- ChatGPT, Mistral, and Gemini implementation guides: publishing steps made optional, sandbox links added.

## [1.0.1] — 2026-03-11

### Added
- User-facing guide for `/child:inner` command (`docs/inner-state-guide.md`).
- Table of contents (`docs/table-of-contents.md`) linking every file in the repository.

### Changed
- README.md: `/child:inner` command row now lists the four annotation fields and links to the guide.

### Fixed
- README.md: restored "documented" wording from source §9.
- README.pt.md: section headings now in English per spec.
- references.md and references.bib: fixed missing diacritics (Rémond, Öst) and added "of" to reference 16 title.

## [1.0.0] — 2026-03-09

### Added
- Initial public release of PAIciente framework.
- System prompt, full documentation, academic reference set, implementation guides.

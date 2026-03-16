# Internationalization (i18n)

This folder contains translations of PAIciente documentation into languages other than English.

## Key principles

- **English is canonical.** All authoritative documentation lives in `/docs/`, `/references/`, and `/prompt/`. Translations are community-maintained companions.
- **The system prompt is never translated.** PAIciente responds in the user's language natively — language handling is built into the prompt logic.
- **Commands stay in English.** All `@` commands (`@clinician`, `@child`, `@set`, `@debrief`, etc.) and `[INNER STATE]` field labels are always kept in English, regardless of translation language.

## Translation tiers

| Tier | Files | Policy |
|---|---|---|
| **1 — Translate always** | README, overview, personas, workflow, limitations, use-cases, inner-state-guide, CONTRIBUTING | User-facing; needed for non-English caregivers. Keep in sync with EN. |
| **2 — Translate when possible** | behavior-map, evidence-map, design-notes, technical-rationale, references, table-of-contents, implementation guides | Useful but secondary; English is acceptable for academic/technical audience. |
| **3 — Never translate** | CHANGELOG | Too volatile; auto-derivable from commit history. |

## Version tracking

Every translated file must include a machine-readable header comment as its first line:

```
<!-- i18n: source=docs/overview.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
```

| Field | Meaning |
|---|---|
| `source` | Path to the EN source file |
| `base-version` | EN version the translation was based on |
| `last-updated` | Date of the last translation update |

This allows automated or manual detection of stale translations when the EN source advances.

## Translation status

See [STATUS.md](STATUS.md) for a cross-language table showing which files are translated and to which version.

## Folder structure

```
i18n/
├── README.md          # this file
├── STATUS.md          # cross-language translation status
├── pt-PT/
│   ├── README.md      # PT-PT specific notes
│   ├── CONTRIBUTING.md
│   └── docs/
│       ├── overview.md
│       ├── personas.md
│       └── ...
├── es/                # (future)
├── fr/                # (future)
```

Each locale folder mirrors the repository structure. The root-level `README.pt.md` (or `README.{locale}.md`) serves as the translated entry point for that language.

## How to contribute a translation

1. Read the general guidelines in [`/CONTRIBUTING.md`](/CONTRIBUTING.md).
2. Check [STATUS.md](STATUS.md) to see what is missing or stale.
3. Create or update the file under `i18n/{locale}/`, mirroring the original file path.
4. Include the version-tracking header as the first line.
5. Keep all `@` commands and `[INNER STATE]` field labels in English.
6. On first use of clinical terms, include the English equivalent in parentheses if the translation is ambiguous.
7. Submit via pull request with the label `i18n`.

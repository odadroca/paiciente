# Contributing to PAIciente

## Submitting an example transcript

1. Choose a scenario folder under `examples/` or create a new one for a new scenario.
2. Follow the schema in [`examples/format.md`](examples/format.md) exactly.
3. Name your file after the platform used (e.g., `claude.md`, `chatgpt.md`, `gemini.md`).
4. The transcript must exercise at minimum: `@clinician`, `@child`, and one of `@debrief` or `@replay`.
5. Submit via pull request.

## Submitting a translation

1. Translations are organized under `i18n/` by locale (e.g., `i18n/pt-PT/`, `i18n/es/`).
2. Create your locale folder if it does not exist.
3. Translate the target file, keeping the original file name and structure.
4. Keep all commands (`@clinician`, `@child`, `@debrief`, `@set`, etc.) in English.
5. Note the EN version you translated from in the file header.
6. Submit via pull request with the label `i18n`.

## Reporting a clinical inaccuracy

If you identify a clinical claim, behavioral model detail, or reference that is inaccurate or misleading:

1. Open a GitHub Issue.
2. Use the label `clinical-review`.
3. Describe the inaccuracy, cite the specific file and line, and provide a corrective source if available.

## Proposing a command extension

If you want to propose a new command or modification to an existing one:

1. Open a GitHub Issue.
2. Use the label `protocol-extension`.
3. Describe the proposed command, its purpose, expected behavior, and which persona it applies to.

## Code of conduct

Contributors are expected to engage in good faith. Clinical critique is welcome.

# Example Transcript Format

All example transcripts in this folder must follow the schema below. This ensures consistency across scenarios and platforms and makes cross-platform comparison possible.

---

## Scenario
[Plain-language description: routine, what the adult tried, what the goal was]

## Platform
[Claude / ChatGPT / Mistral / Gemini / Grok / Other]

## Model version (if known)
[e.g. claude-sonnet-4-6, gpt-4o, mistral-large-2]

## Commands used in this example
[List commands exercised, e.g. `@clinician`, `@child`, `@set arousal=high`, `@debrief`]

## Transcript
[Full turn-by-turn exchange. Label each turn:]
**Adult:** ...
**PAIciente (clinician):** ...
**PAIciente (child):** ...
**PAIciente (child + inner):** ... *(if `@child:inner` was active)*

## What this example illustrates
[1–3 sentences on the specific behavior or technique demonstrated]

## Limitations visible in this example
[Honest notes on where the model drifted, overcomplied, or failed to hold the behavioral spec]

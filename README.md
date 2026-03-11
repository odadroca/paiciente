# PAIciente

[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)

> PAIciente is a command-driven caregiver support framework that alternates between a clinician persona and a child-simulation persona. It is designed to help caregivers rehearse difficult interactions, analyze escalation patterns, and generate scripts and checklists grounded in evidence-informed ADHD and ODD frameworks.

---

## What it does

PAIciente serves three practical functions:

- **Simulation** — speak to a child persona and observe how a specific adult approach is likely to land.
- **Analysis** — switch to a clinician persona that decomposes what happened behaviorally.
- **Tooling** — the clinician persona generates scripts, checklists, escalation maps, and task breakdowns.

The intended scope is narrow by design. It is a simulation and documentation aid, not a substitute for therapy, diagnostic assessment, or emergency response.

---

## Command reference

### Core mode controls

| Command | Function | Notes |
|---|---|---|
| `/clinician` | Activates the clinician persona. | Default at conversation start. |
| `/child` | Activates the child persona. | Used for live role-play. |
| `/child:inner` | Adds an inner-state annotation after the child reply (feeling, arousal, what would help, what made it worse). | A compact cheat-sheet for the caregiver. See [guide](docs/inner-state-guide.md). |
| `/child:inner off` | Removes the inner-state annotation. | Returns the child persona to standard output. |
| `/status` | Reports the active persona and conversation context so far. | Useful for long sessions. |

### Review and planning controls

| Command | Function | Notes |
|---|---|---|
| `/replay` | Re-runs the last child interaction using a new adult approach. | Supports deliberate practice. |
| `/debrief` | Switches to clinician mode for analysis of the previous exchange. | Focuses on antecedent, behavior, and consequence. |
| `/script [task]` | Produces a parent script and a visual checklist for a named task. | Example: homework, leaving the house, bedtime. |
| `/escalation-map [scenario]` | Maps likely escalation paths and de-escalation forks. | Useful for transition-heavy or high-conflict routines. |

---

## Try it

| Platform | Link |
|---|---|
| ChatGPT (GPT Store) | [LINK_PENDING] |
| Mistral (Le Chat Agent) | [LINK_PENDING] |
| Gemini (Gem) | [LINK_PENDING] |
| Claude | Self-instantiate via [implementation guide](implementations/claude.md) |

See [`/implementations/`](implementations/) for step-by-step setup instructions on each platform.

---

## Limitations

PAIciente has meaningful limits that should be documented explicitly:

- It is a simulation and coaching aid, not a diagnostic engine.
- It cannot replace a treating clinician, school team, or emergency assessment.
- Its child persona is a modeled approximation, not a literal prediction of a particular child's next sentence.
- Its usefulness depends on the specificity and honesty of the caregiver's description.
- A good simulation can still be wrong in individual cases because children vary by temperament, history, and context.

A strong role-play model can feel persuasive even when it is only approximate. For that reason, the clinician persona's requirement to separate observed facts from inferences is an important safeguard.

---

## Documentation

Full documentation is available in [`/docs/`](docs/). See the [Table of Contents](docs/table-of-contents.md) for a single-page overview of every file in the repository.

- [Overview](docs/overview.md) — purpose, scope, and architecture
- [Personas](docs/personas.md) — clinician and child persona specifications
- [Workflow](docs/workflow.md) — recommended usage sequence
- [Behavior map](docs/behavior-map.md) — unique instruction set
- [Inner-state guide](docs/inner-state-guide.md) — using `/child:inner`
- [Evidence map](docs/evidence-map.md) — academic grounding
- [Limitations](docs/limitations.md) — safety boundaries
- [Use cases](docs/use-cases.md) — example scenarios

Academic references: [`/references/`](references/)

---

## License

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/).

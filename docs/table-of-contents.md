# Table of Contents

A single-page overview of every document in the PAIciente repository.

---

## Root

| File | Description |
|---|---|
| [README.md](../README.md) | Project overview, command reference, platform links, and limitations |
| [README.pt.md](../README.pt.md) | Auxiliary README in European Portuguese (PT-PT) |
| [LICENSE](../LICENSE) | CC BY-SA 4.0 full legal text |
| [CHANGELOG.md](../CHANGELOG.md) | Version history in Keep a Changelog format |
| [CONTRIBUTING.md](../CONTRIBUTING.md) | Contribution guidelines: transcripts, translations, clinical review, extensions |

---

## Prompt

| File | Description |
|---|---|
| [prompt/system-prompt.md](../prompt/system-prompt.md) | The complete PAIciente system prompt |
| [prompt/design-notes.md](../prompt/design-notes.md) | Instruction families and design rationale behind the prompt |

---

## Documentation

| File | Description |
|---|---|
| [docs/overview.md](overview.md) | Purpose, scope, and architecture |
| [docs/personas.md](personas.md) | Clinician and child persona specifications, `@set` state modulation |
| [docs/workflow.md](workflow.md) | Recommended usage sequence |
| [docs/behavior-map.md](behavior-map.md) | Unique instruction set mapping |
| [docs/inner-state-guide.md](inner-state-guide.md) | User guide for `@child:inner` and `@set` — annotation fields, escalation path, trajectory, and state injection |
| [docs/evidence-map.md](evidence-map.md) | Academic grounding for each design element |
| [docs/limitations.md](limitations.md) | Safety boundaries and explicit constraints |
| [docs/use-cases.md](use-cases.md) | Example scenarios: homework, device transition, bedtime, compound stress |

---

## References

| File | Description |
|---|---|
| [references/references.md](../references/references.md) | All 20 academic references with summaries and DOI/URL links |
| [references/references.bib](../references/references.bib) | BibTeX entries for all 20 references |
| [references/evidence-map.csv](../references/evidence-map.csv) | Design-element-to-source mapping in CSV format |

---

## Implementation Guides

| File | Description |
|---|---|
| [implementations/claude.md](../implementations/claude.md) | Setup via Claude Projects (self-instantiate) |
| [implementations/chatgpt.md](../implementations/chatgpt.md) | Setup via Custom GPT — includes sandbox link |
| [implementations/mistral.md](../implementations/mistral.md) | Setup via Le Chat Agent — includes sandbox link |
| [implementations/gemini.md](../implementations/gemini.md) | Setup via Gemini Gem — includes sandbox link |

### Platform-specific resources

| File | Description |
|---|---|
| [implementations/resources/chatgpt/customgpt_v2_core_instructions.md](../implementations/resources/chatgpt/customgpt_v2_core_instructions.md) | ChatGPT Custom GPT — core instructions |
| [implementations/resources/chatgpt/customgpt_v2_knowledge_01_child_persona_and_inner_state.md](../implementations/resources/chatgpt/customgpt_v2_knowledge_01_child_persona_and_inner_state.md) | ChatGPT Custom GPT — knowledge file: child persona and inner state |
| [implementations/resources/chatgpt/customgpt_v2_knowledge_02_set_command_and_state_rules.md](../implementations/resources/chatgpt/customgpt_v2_knowledge_02_set_command_and_state_rules.md) | ChatGPT Custom GPT — knowledge file: `@set` command and state rules |
| [implementations/resources/chatgpt/customgpt_v2_knowledge_03_clinician_shared_rules_and_commands.md](../implementations/resources/chatgpt/customgpt_v2_knowledge_03_clinician_shared_rules_and_commands.md) | ChatGPT Custom GPT — knowledge file: clinician, shared rules, and commands |
| [implementations/resources/mistral/references.pdf](../implementations/resources/mistral/references.pdf) | Mistral agent — references document |
| [implementations/resources/mistral/references-bib.pdf](../implementations/resources/mistral/references-bib.pdf) | Mistral agent — BibTeX references |
| [implementations/resources/mistral/evidence-map.pdf](../implementations/resources/mistral/evidence-map.pdf) | Mistral agent — evidence map |

---

## Examples

| File | Description |
|---|---|
| [examples/format.md](../examples/format.md) | Contributor template for submitting transcripts |
| [examples/homework-startup/claude.md](../examples/homework-startup/claude.md) | Homework scenario — Claude |
| [examples/homework-startup/chatgpt.md](../examples/homework-startup/chatgpt.md) | Homework scenario — ChatGPT |
| [examples/homework-startup/mistral.md](../examples/homework-startup/mistral.md) | Homework scenario — Mistral |
| [examples/device-transition/claude.md](../examples/device-transition/claude.md) | Device transition scenario — Claude |
| [examples/bedtime-routine/chatgpt.md](../examples/bedtime-routine/chatgpt.md) | Bedtime scenario — ChatGPT |

---

## Localization

| File | Description |
|---|---|
| [i18n/pt-PT/README.md](../i18n/pt-PT/README.md) | European Portuguese translation status and guidelines |

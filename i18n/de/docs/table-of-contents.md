<!-- i18n: source=docs/table-of-contents.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# Inhaltsverzeichnis

Eine einseitige Ubersicht uber alle Dokumente im PAIciente-Repository.

---

## Stammverzeichnis

| Datei | Beschreibung |
|---|---|
| [README.md](../../README.md) | Projektuberblick, Befehlsreferenz, Plattform-Links und Einschrankungen |
| [README.pt.md](../../README.pt.md) | Hilfs-README in Europaischem Portugiesisch (PT-PT) |
| [LICENSE](../../LICENSE) | Vollstandiger Rechtstext CC BY-SA 4.0 |
| [CHANGELOG.md](../../CHANGELOG.md) | Versionshistorie im Keep-a-Changelog-Format |
| [CONTRIBUTING.md](../../CONTRIBUTING.md) | Beitragsrichtlinien: Transkripte, Ubersetzungen, klinische Uberprufung, Erweiterungen |

---

## Prompt

| Datei | Beschreibung |
|---|---|
| [prompt/system-prompt.md](../../prompt/system-prompt.md) | Der vollstandige PAIciente System-Prompt |
| [prompt/design-notes.md](../../prompt/design-notes.md) | Instruktionsfamilien und Designbegrundung des Prompts |

---

## Dokumentation

| Datei | Beschreibung |
|---|---|
| [docs/overview.md](overview.md) | Zweck, Umfang und Architektur |
| [docs/personas.md](personas.md) | Spezifikationen der Kliniker- und Kind-Personas, Zustandsmodulation mit `@set` |
| [docs/workflow.md](workflow.md) | Empfohlene Nutzungssequenz |
| [docs/behavior-map.md](behavior-map.md) | Einzigartige Instruktionssatz-Zuordnung |
| [docs/inner-state-guide.md](inner-state-guide.md) | Benutzerhandbuch fur `@child:inner` und `@set` — Annotationsfelder, Eskalationspfad, Verlauf und Zustandsinjektion |
| [docs/evidence-map.md](evidence-map.md) | Akademische Grundlage fur jedes Designelement |
| [docs/limitations.md](limitations.md) | Sicherheitsgrenzen und explizite Einschrankungen |
| [docs/use-cases.md](use-cases.md) | Beispielszenarien: Hausaufgaben, Gerateubertragung, Schlafenszeit, zusammengesetzter Stress |
| [docs/Technical-Rationale-and-Academic-Positioning.md](Technical-Rationale-and-Academic-Positioning.md) | Technische Begrundung und akademische Positionierung — formaler Rahmen, Designverpflichtungen und Evidenzgrundlage |

---

## Referenzen

| Datei | Beschreibung |
|---|---|
| [references/references.md](../../references/references.md) | Alle 20 akademischen Referenzen mit Zusammenfassungen und DOI/URL-Links |
| [references/references.bib](../../references/references.bib) | BibTeX-Eintrage fur alle 20 Referenzen |
| [references/evidence-map.csv](../../references/evidence-map.csv) | Designelement-zu-Quelle-Zuordnung im CSV-Format |

---

## Implementierungsleitfaden

| Datei | Beschreibung |
|---|---|
| [implementations/claude.md](../../implementations/claude.md) | Einrichtung uber Claude Projects (Selbstinstanziierung) |
| [implementations/chatgpt.md](../../implementations/chatgpt.md) | Einrichtung uber Custom GPT — enthalt Sandbox-Link |
| [implementations/mistral.md](../../implementations/mistral.md) | Einrichtung uber Le Chat Agent — enthalt Sandbox-Link |
| [implementations/gemini.md](../../implementations/gemini.md) | Einrichtung uber Gemini Gem — enthalt Sandbox-Link |

### Plattformspezifische Ressourcen

| Datei | Beschreibung |
|---|---|
| [implementations/resources/chatgpt/customgpt_v2_core_instructions.md](../../implementations/resources/chatgpt/customgpt_v2_core_instructions.md) | ChatGPT Custom GPT — Kernanweisungen |
| [implementations/resources/chatgpt/customgpt_v2_knowledge_01_child_persona_and_inner_state.md](../../implementations/resources/chatgpt/customgpt_v2_knowledge_01_child_persona_and_inner_state.md) | ChatGPT Custom GPT — Wissensdatei: Kind-Persona und innerer Zustand |
| [implementations/resources/chatgpt/customgpt_v2_knowledge_02_set_command_and_state_rules.md](../../implementations/resources/chatgpt/customgpt_v2_knowledge_02_set_command_and_state_rules.md) | ChatGPT Custom GPT — Wissensdatei: `@set`-Befehl und Zustandsregeln |
| [implementations/resources/chatgpt/customgpt_v2_knowledge_03_clinician_shared_rules_and_commands.md](../../implementations/resources/chatgpt/customgpt_v2_knowledge_03_clinician_shared_rules_and_commands.md) | ChatGPT Custom GPT — Wissensdatei: Kliniker, gemeinsame Regeln und Befehle |
| [implementations/resources/mistral/references.pdf](../../implementations/resources/mistral/references.pdf) | Mistral-Agent — Referenzdokument |
| [implementations/resources/mistral/references-bib.pdf](../../implementations/resources/mistral/references-bib.pdf) | Mistral-Agent — BibTeX-Referenzen |
| [implementations/resources/mistral/evidence-map.pdf](../../implementations/resources/mistral/evidence-map.pdf) | Mistral-Agent — Evidenzkarte |

---

## Beispiele

| Datei | Beschreibung |
|---|---|
| [examples/format.md](../../examples/format.md) | Mitwirkenden-Vorlage fur die Einreichung von Transkripten |
| [examples/homework-startup/claude.md](../../examples/homework-startup/claude.md) | Hausaufgaben-Szenario — Claude |
| [examples/homework-startup/chatgpt.md](../../examples/homework-startup/chatgpt.md) | Hausaufgaben-Szenario — ChatGPT |
| [examples/homework-startup/mistral.md](../../examples/homework-startup/mistral.md) | Hausaufgaben-Szenario — Mistral |
| [examples/device-transition/claude.md](../../examples/device-transition/claude.md) | Gerateubertragung-Szenario — Claude |
| [examples/bedtime-routine/chatgpt.md](../../examples/bedtime-routine/chatgpt.md) | Schlafenszeit-Szenario — ChatGPT |

---

## Lokalisierung

| Datei | Beschreibung |
|---|---|
| [i18n/de/README.md](../../i18n/de/README.md) | Ubersetzungsstatus und Richtlinien fur Deutsch |

<!-- i18n: source=docs/table-of-contents.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# Tabla de Contenidos

Una vision general en una sola pagina de todos los documentos en el repositorio PAIciente.

---

## Raiz

| Archivo | Descripcion |
|---|---|
| [README.md](../../README.md) | Vision general del proyecto, referencia de comandos, enlaces de plataformas y limitaciones |
| [README.pt.md](../../README.pt.md) | README auxiliar en Portugues Europeo (PT-PT) |
| [LICENSE](../../LICENSE) | Texto legal completo CC BY-SA 4.0 |
| [CHANGELOG.md](../../CHANGELOG.md) | Historial de versiones en formato Keep a Changelog |
| [CONTRIBUTING.md](../../CONTRIBUTING.md) | Directrices de contribucion: transcripciones, traducciones, revision clinica, extensiones |

---

## Prompt

| Archivo | Descripcion |
|---|---|
| [prompt/system-prompt.md](../../prompt/system-prompt.md) | El system prompt completo de PAIciente |
| [prompt/design-notes.md](../../prompt/design-notes.md) | Familias de instrucciones y fundamentos de diseno del prompt |

---

## Documentacion

| Archivo | Descripcion |
|---|---|
| [docs/overview.md](overview.md) | Proposito, alcance y arquitectura |
| [docs/personas.md](personas.md) | Especificaciones de las personas del clinico y del nino, modulacion de estado con `@set` |
| [docs/workflow.md](workflow.md) | Secuencia de uso recomendada |
| [docs/behavior-map.md](behavior-map.md) | Mapeo unico del conjunto de instrucciones |
| [docs/inner-state-guide.md](inner-state-guide.md) | Guia del usuario para `@child:inner` y `@set` — campos de anotacion, camino de escalada, trayectoria e inyeccion de estado |
| [docs/evidence-map.md](evidence-map.md) | Fundamentacion academica para cada elemento de diseno |
| [docs/limitations.md](limitations.md) | Limites de seguridad y restricciones explicitas |
| [docs/use-cases.md](use-cases.md) | Escenarios de ejemplo: deberes, transicion de dispositivo, hora de dormir, estres compuesto |
| [docs/Technical-Rationale-and-Academic-Positioning.md](Technical-Rationale-and-Academic-Positioning.md) | Fundamentacion tecnica y posicionamiento academico — marco formal, compromisos de diseno y fundamentacion en evidencias |

---

## Referencias

| Archivo | Descripcion |
|---|---|
| [references/references.md](../../references/references.md) | Las 20 referencias academicas con resumenes y enlaces DOI/URL |
| [references/references.bib](../../references/references.bib) | Entradas BibTeX para las 20 referencias |
| [references/evidence-map.csv](../../references/evidence-map.csv) | Mapeo elemento-de-diseno-a-fuente en formato CSV |

---

## Guias de Implementacion

| Archivo | Descripcion |
|---|---|
| [implementations/claude.md](../../implementations/claude.md) | Configuracion via Claude Projects (auto-instanciacion) |
| [implementations/chatgpt.md](../../implementations/chatgpt.md) | Configuracion via Custom GPT — incluye enlace sandbox |
| [implementations/mistral.md](../../implementations/mistral.md) | Configuracion via Le Chat Agent — incluye enlace sandbox |
| [implementations/gemini.md](../../implementations/gemini.md) | Configuracion via Gemini Gem — incluye enlace sandbox |

### Recursos especificos de plataforma

| Archivo | Descripcion |
|---|---|
| [implementations/resources/chatgpt/customgpt_v2_core_instructions.md](../../implementations/resources/chatgpt/customgpt_v2_core_instructions.md) | ChatGPT Custom GPT — instrucciones principales |
| [implementations/resources/chatgpt/customgpt_v2_knowledge_01_child_persona_and_inner_state.md](../../implementations/resources/chatgpt/customgpt_v2_knowledge_01_child_persona_and_inner_state.md) | ChatGPT Custom GPT — archivo de conocimiento: persona del nino y estado interior |
| [implementations/resources/chatgpt/customgpt_v2_knowledge_02_set_command_and_state_rules.md](../../implementations/resources/chatgpt/customgpt_v2_knowledge_02_set_command_and_state_rules.md) | ChatGPT Custom GPT — archivo de conocimiento: comando `@set` y reglas de estado |
| [implementations/resources/chatgpt/customgpt_v2_knowledge_03_clinician_shared_rules_and_commands.md](../../implementations/resources/chatgpt/customgpt_v2_knowledge_03_clinician_shared_rules_and_commands.md) | ChatGPT Custom GPT — archivo de conocimiento: clinico, reglas compartidas y comandos |
| [implementations/resources/mistral/references.pdf](../../implementations/resources/mistral/references.pdf) | Agente Mistral — documento de referencias |
| [implementations/resources/mistral/references-bib.pdf](../../implementations/resources/mistral/references-bib.pdf) | Agente Mistral — referencias BibTeX |
| [implementations/resources/mistral/evidence-map.pdf](../../implementations/resources/mistral/evidence-map.pdf) | Agente Mistral — mapa de evidencias |

---

## Ejemplos

| Archivo | Descripcion |
|---|---|
| [examples/format.md](../../examples/format.md) | Plantilla de contribuidor para envio de transcripciones |
| [examples/homework-startup/claude.md](../../examples/homework-startup/claude.md) | Escenario de deberes — Claude |
| [examples/homework-startup/chatgpt.md](../../examples/homework-startup/chatgpt.md) | Escenario de deberes — ChatGPT |
| [examples/homework-startup/mistral.md](../../examples/homework-startup/mistral.md) | Escenario de deberes — Mistral |
| [examples/device-transition/claude.md](../../examples/device-transition/claude.md) | Escenario de transicion de dispositivo — Claude |
| [examples/bedtime-routine/chatgpt.md](../../examples/bedtime-routine/chatgpt.md) | Escenario de hora de dormir — ChatGPT |

---

## Localizacion

| Archivo | Descripcion |
|---|---|
| [i18n/es/README.md](../../i18n/es/README.md) | Estado de la traduccion y directrices para Espanol |

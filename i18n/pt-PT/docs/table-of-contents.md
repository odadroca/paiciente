<!-- i18n: source=docs/table-of-contents.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# Indice

Uma visao geral numa unica pagina de todos os documentos no repositorio PAIciente.

---

## Raiz

| Ficheiro | Descricao |
|---|---|
| [README.md](../../README.md) | Visao geral do projeto, referencia de comandos, ligacoes de plataformas e limitacoes |
| [README.pt.md](../../README.pt.md) | README auxiliar em Portugues Europeu (PT-PT) |
| [LICENSE](../../LICENSE) | Texto legal completo CC BY-SA 4.0 |
| [CHANGELOG.md](../../CHANGELOG.md) | Historico de versoes no formato Keep a Changelog |
| [CONTRIBUTING.md](../../CONTRIBUTING.md) | Diretrizes de contribuicao: transcricoes, traducoes, revisao clinica, extensoes |

---

## Prompt

| Ficheiro | Descricao |
|---|---|
| [prompt/system-prompt.md](../../prompt/system-prompt.md) | O system prompt completo do PAIciente |
| [prompt/design-notes.md](../../prompt/design-notes.md) | Familias de instrucoes e fundamentos de design do prompt |

---

## Documentacao

| Ficheiro | Descricao |
|---|---|
| [docs/overview.md](overview.md) | Proposito, ambito e arquitetura |
| [docs/personas.md](personas.md) | Especificacoes das personas do clinico e da crianca, modulacao de estado com `@set` |
| [docs/workflow.md](workflow.md) | Sequencia de utilizacao recomendada |
| [docs/behavior-map.md](behavior-map.md) | Mapeamento unico do conjunto de instrucoes |
| [docs/inner-state-guide.md](inner-state-guide.md) | Guia do utilizador para `@child:inner` e `@set` — campos de anotacao, caminho de escalada, trajetoria e injecao de estado |
| [docs/evidence-map.md](evidence-map.md) | Fundamentacao academica para cada elemento de design |
| [docs/limitations.md](limitations.md) | Limites de seguranca e restricoes explicitas |
| [docs/use-cases.md](use-cases.md) | Cenarios de exemplo: trabalhos de casa, transicao de dispositivo, hora de dormir, stress composto |
| [docs/Technical-Rationale-and-Academic-Positioning.md](Technical-Rationale-and-Academic-Positioning.md) | Fundamentacao tecnica e posicionamento academico — enquadramento formal, compromissos de design e fundamentacao em evidencias |

---

## Referencias

| Ficheiro | Descricao |
|---|---|
| [references/references.md](../../references/references.md) | Todas as 20 referencias academicas com resumos e ligacoes DOI/URL |
| [references/references.bib](../../references/references.bib) | Entradas BibTeX para todas as 20 referencias |
| [references/evidence-map.csv](../../references/evidence-map.csv) | Mapeamento elemento-de-design-para-fonte em formato CSV |

---

## Guias de Implementacao

| Ficheiro | Descricao |
|---|---|
| [implementations/claude.md](../../implementations/claude.md) | Configuracao via Claude Projects (auto-instanciacao) |
| [implementations/chatgpt.md](../../implementations/chatgpt.md) | Configuracao via Custom GPT — inclui ligacao sandbox |
| [implementations/mistral.md](../../implementations/mistral.md) | Configuracao via Le Chat Agent — inclui ligacao sandbox |
| [implementations/gemini.md](../../implementations/gemini.md) | Configuracao via Gemini Gem — inclui ligacao sandbox |

### Recursos especificos de plataforma

| Ficheiro | Descricao |
|---|---|
| [implementations/resources/chatgpt/customgpt_v2_core_instructions.md](../../implementations/resources/chatgpt/customgpt_v2_core_instructions.md) | ChatGPT Custom GPT — instrucoes principais |
| [implementations/resources/chatgpt/customgpt_v2_knowledge_01_child_persona_and_inner_state.md](../../implementations/resources/chatgpt/customgpt_v2_knowledge_01_child_persona_and_inner_state.md) | ChatGPT Custom GPT — ficheiro de conhecimento: persona da crianca e estado interior |
| [implementations/resources/chatgpt/customgpt_v2_knowledge_02_set_command_and_state_rules.md](../../implementations/resources/chatgpt/customgpt_v2_knowledge_02_set_command_and_state_rules.md) | ChatGPT Custom GPT — ficheiro de conhecimento: comando `@set` e regras de estado |
| [implementations/resources/chatgpt/customgpt_v2_knowledge_03_clinician_shared_rules_and_commands.md](../../implementations/resources/chatgpt/customgpt_v2_knowledge_03_clinician_shared_rules_and_commands.md) | ChatGPT Custom GPT — ficheiro de conhecimento: clinico, regras partilhadas e comandos |
| [implementations/resources/mistral/references.pdf](../../implementations/resources/mistral/references.pdf) | Agente Mistral — documento de referencias |
| [implementations/resources/mistral/references-bib.pdf](../../implementations/resources/mistral/references-bib.pdf) | Agente Mistral — referencias BibTeX |
| [implementations/resources/mistral/evidence-map.pdf](../../implementations/resources/mistral/evidence-map.pdf) | Agente Mistral — mapa de evidencias |

---

## Exemplos

| Ficheiro | Descricao |
|---|---|
| [examples/format.md](../../examples/format.md) | Modelo de contribuidor para submissao de transcricoes |
| [examples/homework-startup/claude.md](../../examples/homework-startup/claude.md) | Cenario de trabalhos de casa — Claude |
| [examples/homework-startup/chatgpt.md](../../examples/homework-startup/chatgpt.md) | Cenario de trabalhos de casa — ChatGPT |
| [examples/homework-startup/mistral.md](../../examples/homework-startup/mistral.md) | Cenario de trabalhos de casa — Mistral |
| [examples/device-transition/claude.md](../../examples/device-transition/claude.md) | Cenario de transicao de dispositivo — Claude |
| [examples/bedtime-routine/chatgpt.md](../../examples/bedtime-routine/chatgpt.md) | Cenario de hora de dormir — ChatGPT |

---

## Localizacao

| Ficheiro | Descricao |
|---|---|
| [i18n/pt-PT/README.md](../../i18n/pt-PT/README.md) | Estado da traducao e diretrizes para Portugues Europeu |

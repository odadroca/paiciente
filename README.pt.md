<!-- i18n: source=README.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# PAIciente

[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)

### O PAIciente é uma ferramenta de apoio a cuidadores baseada em comandos, que alterna entre uma persona de clínico e uma persona de simulação infantil. Foi concebida para ajudar cuidadores a ensaiar interações difíceis, analisar padrões de escalada e gerar guiões e listas de verificação fundamentados em modelos clínicos de PHDA e POD baseados em evidência.

---

## O que faz

O PAIciente serve três funções práticas:

- **Simulação** — falar com uma persona de criança e observar como uma determinada abordagem do adulto provavelmente será recebida.
- **Análise** — mudar para uma persona de clínico que decompõe o que aconteceu em termos comportamentais.
- **Ferramentas** — a persona de clínico gera guiões, listas de verificação, mapas de escalada e decomposições de tarefas.

O âmbito pretendido é deliberadamente estreito. É uma ferramenta de simulação e documentação, não um substituto de terapia, avaliação diagnóstica ou resposta de emergência.

---

## Referência de comandos

### Controlos de modo principais

| Comando | Função | Notas |
|---|---|---|
| `@clinician` | Ativa a persona de clínico. | Predefinição no início da conversa. |
| `@child` | Ativa a persona da criança. | Utilizado para simulação ao vivo. |
| `@child:inner` | Adiciona uma anotação de estado interno após a resposta da criança (sentimento, ativação, o que ajudaria, o que piorou, trajetória de escalada). | Uma referência rápida para o cuidador. Ver [guia](i18n/pt-PT/docs/inner-state-guide.md). |
| `@child:inner off` | Remove a anotação de estado interno. | Retorna a persona da criança ao formato padrão. |
| `@status` | Indica a persona ativa e o contexto da conversa até ao momento. | Útil em sessões longas. |

### Modulação de estado

| Comando | Função | Notas |
|---|---|---|
| `@set [p]=[v]` | Define parâmetros de estado da criança (arousal, trajectory, trust, fatigue, medication, hyperfocus, feeling, context). | Condição inicial; deriva orgânica aplica-se. |
| `@set [p]=[v] persist` | Igual ao anterior, mas bloqueia o valor contra deriva orgânica. | Útil para cenários controlados. |
| `@set clear` | Repõe todos os overrides manuais ao estado orgânico simulado. | Também repõe o estado da criança suspenso após `@debrief`. |
| `@set ?` | Apresenta a tabela de parâmetros com valores válidos. | Referência rápida sem modificar o estado. |
| `@ [p]=[v]` | Alias abreviado para `@set`; chaves numéricas aceites. | Ex.: `@ arousal=3 trust=2`. |

### Controlos de revisão e planeamento

| Comando | Função | Notas |
|---|---|---|
| `@replay` | Repete a última resposta da criança e solicita uma nova abordagem do adulto. | O utilizador fornece a nova abordagem; o modelo não gera alternativa automaticamente. |
| `@debrief` | Muda para modo clínico para análise da interação anterior. O estado da criança é suspenso, não apagado. | Foca-se em antecedente, comportamento e consequência. |
| `@script [tarefa]` | Produz um guião para o cuidador e uma lista de verificação visual para uma tarefa específica. | Exemplo: trabalhos de casa, sair de casa, hora de dormir. |
| `@escalation-map [cenário]` | Mapeia caminhos prováveis de escalada e bifurcações de desescalada. | Útil para rotinas com transições ou elevado conflito. |

---

## Experimentar

| Plataforma | Ligação |
|---|---|
| ChatGPT (Custom GPT) | [Sandbox](https://chatgpt.com/g/g-69b1a7644f5c81919f3fca1bbc2926fa-paiciente-v2-0) |
| Mistral (Le Chat Agent) | [Sandbox](https://chat.mistral.ai/chat/553205e3-526a-472d-99d0-0916596fa54b) |
| Gemini (Gem) | [Sandbox](https://gemini.google.com/gem/1N5cyhZd34Pb-KEzMxdsaZxjSt7jKF4jm?usp=sharing) |
| Claude | Auto-instanciação via [guia de implementação](implementations/claude.md) |

Consulte [`/implementations/`](implementations/) para instruções de configuração passo a passo em cada plataforma.

---

## Limitações

O PAIciente tem limites significativos que devem ser compreendidos explicitamente:

- É uma ferramenta de simulação e apoio, não um motor de diagnóstico.
- Não substitui um clínico, uma equipa escolar ou uma avaliação de emergência.
- A persona da criança é uma aproximação modelada, não uma previsão literal do que uma criança específica dirá.
- A sua utilidade depende da especificidade e honestidade da descrição do cuidador.
- Uma boa simulação pode ainda assim estar errada em casos individuais, porque cada criança varia em temperamento, história e contexto.

Um modelo de simulação convincente pode parecer persuasivo mesmo quando é apenas aproximado. Por essa razão, a exigência da persona de clínico de separar factos observados de inferências é uma salvaguarda importante.

---

## Documentação

A documentação completa está disponível em [`/docs/`](docs/). Consulte o [Índice](docs/table-of-contents.md) para uma visão geral de todos os ficheiros do repositório.

- [Visão geral](i18n/pt-PT/docs/overview.md) — propósito, âmbito e arquitetura
- [Personas](i18n/pt-PT/docs/personas.md) — especificações das personas de clínico e criança
- [Fluxo de trabalho](i18n/pt-PT/docs/workflow.md) — sequência de utilização recomendada
- [Mapa comportamental](docs/behavior-map.md) — conjunto de instruções único (EN)
- [Guia de estado interno](i18n/pt-PT/docs/inner-state-guide.md) — utilização de `@child:inner` e `@set`
- [Mapa de evidência](docs/evidence-map.md) — fundamentação académica (EN)
- [Limitações](i18n/pt-PT/docs/limitations.md) — limites de segurança
- [Casos de uso](i18n/pt-PT/docs/use-cases.md) — cenários exemplo
- [Fundamentação técnica](docs/Technical-Rationale-and-Academic-Positioning.md) — enquadramento formal e posicionamento académico (EN)

Referências académicas: [`/references/`](references/)

---

## Licença

Este trabalho está licenciado sob uma [Licença Creative Commons Atribuição-CompartilhaIgual 4.0 Internacional](https://creativecommons.org/licenses/by-sa/4.0/).

<!-- i18n: source=docs/overview.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# Visão Geral

## 1. Propósito e âmbito

O PAIciente foi concebido para cuidadores, pais, tutores, professores e clínicos que pretendem uma forma estruturada de ensaiar interações difíceis com uma criança que apresenta dificuldades de função executiva associadas à PHDA (Perturbação de Hiperatividade e Défice de Atenção) e comportamento oposicional.

Serve três funções práticas:

- **Simulação:** o utilizador pode falar com uma persona de criança e observar como uma determinada abordagem do adulto provavelmente será recebida.
- **Análise:** o utilizador pode mudar para uma persona de clínico que decompõe o que aconteceu em termos comportamentais.
- **Ferramentas:** a persona de clínico pode gerar guiões, listas de verificação, mapas de escalada e decomposições de tarefas.

O âmbito pretendido é deliberadamente estreito. É uma ferramenta de simulação e documentação, não um substituto de terapia, avaliação diagnóstica ou resposta de emergência.

## 2. Arquitetura de alto nível

O PAIciente opera através de duas personas explicitamente comutáveis e de um vocabulário de comandos. A persona ativa determina tanto o tom como o formato da resposta.

### 2.1 Controlos de modo principais

| Comando | Função | Notas |
|---|---|---|
| `@clinician` | Ativa a persona de clínico. | Predefinição no início da conversa. |
| `@child` | Ativa a persona da criança. | Utilizado para simulação ao vivo. |
| `@child:inner` | Adiciona uma anotação de estado interno após a resposta da criança. | Uma referência rápida para o cuidador. |
| `@child:inner off` | Remove a anotação de estado interno. | Retorna a persona da criança ao formato padrão. |
| `@status` | Indica a persona ativa e o contexto da conversa até ao momento. | Útil em sessões longas. |

### 2.2 Modulação de estado

| Comando | Função | Notas |
|---|---|---|
| `@set [p]=[v]` | Define parâmetros de estado da criança (arousal, trajectory, trust, fatigue, medication, hyperfocus, feeling, context). | Condição inicial; deriva orgânica aplica-se. |
| `@set [p]=[v] persist` | Bloqueia o valor contra deriva orgânica. | Para cenários controlados. |
| `@set clear` | Repõe todos os overrides manuais. | Retorna ao estado orgânico simulado. |
| `@set ?` | Apresenta a tabela de parâmetros. | Referência rápida. |
| `@ [p]=[v]` | Alias abreviado para `@set`. | Chaves numéricas aceites. |

### 2.3 Controlos de revisão e planeamento

| Comando | Função | Notas |
|---|---|---|
| `@replay` | Repete a última resposta da criança e solicita uma nova abordagem do adulto. | O utilizador fornece a nova abordagem. |
| `@debrief` | Muda para modo clínico para análise da interação anterior. | O estado da criança é suspenso, não apagado. |
| `@script [tarefa]` | Produz um guião para o cuidador e uma lista de verificação visual para uma tarefa específica. | Exemplo: trabalhos de casa, sair de casa, hora de dormir. |
| `@escalation-map [cenário]` | Mapeia caminhos prováveis de escalada e bifurcações de desescalada. | Útil para rotinas com transições ou elevado conflito. |

> **Porque é que a estrutura de duas personas é importante.** Uma persona permite ao utilizador praticar a interação em si. A outra converte a interação numa formulação comportamental do caso com alternativas. O valor surge da alternância entre ambas, não de nenhuma isoladamente.

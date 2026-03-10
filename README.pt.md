# PAIciente

[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)

> PAIciente é uma ferramenta de apoio a cuidadores baseada em comandos, que alterna entre uma persona de clínico e uma persona de simulação infantil. Foi concebida para ajudar cuidadores a ensaiar interações difíceis, analisar padrões de escalada e gerar guiões e listas de verificação fundamentados em modelos clínicos de PHDA e POD baseados em evidência.

---

## Command reference

### Core mode controls

| Command | Função | Notas |
|---|---|---|
| `/clinician` | Ativa a persona de clínico. | Predefinição no início da conversa. |
| `/child` | Ativa a persona da criança. | Utilizado para simulação ao vivo. |
| `/child:inner` | Adiciona uma anotação de estado interno após a resposta da criança. | Uma referência rápida para o cuidador. |
| `/child:inner off` | Remove a anotação de estado interno. | Retorna a persona da criança ao formato padrão. |
| `/status` | Indica a persona ativa e o contexto da conversa até ao momento. | Útil em sessões longas. |

### Review and planning controls

| Command | Função | Notas |
|---|---|---|
| `/replay` | Repete a última interação com a criança usando uma nova abordagem do adulto. | Suporta prática deliberada. |
| `/debrief` | Muda para modo clínico para análise da interação anterior. | Foca-se em antecedente, comportamento e consequência. |
| `/script [tarefa]` | Produz um guião para o cuidador e uma lista de verificação visual para uma tarefa específica. | Exemplo: trabalhos de casa, sair de casa, hora de dormir. |
| `/escalation-map [cenário]` | Mapeia caminhos prováveis de escalada e bifurcações de desescalada. | Útil para rotinas com transições ou elevado conflito. |

---

## Limitations

O PAIciente tem limites significativos que devem ser compreendidos explicitamente:

- É uma ferramenta de simulação e apoio, não um motor de diagnóstico.
- Não substitui um clínico, uma equipa escolar ou uma avaliação de emergência.
- A persona da criança é uma aproximação modelada, não uma previsão literal do que uma criança específica dirá.
- A sua utilidade depende da especificidade e honestidade da descrição do cuidador.
- Uma boa simulação pode ainda assim estar errada em casos individuais, porque cada criança varia em temperamento, história e contexto.

---

## License

Este trabalho está licenciado sob uma [Licença Creative Commons Atribuição-CompartilhaIgual 4.0 Internacional](https://creativecommons.org/licenses/by-sa/4.0/).

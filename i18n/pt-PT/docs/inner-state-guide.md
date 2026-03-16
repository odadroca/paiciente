<!-- i18n: source=docs/inner-state-guide.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# Guia de Estado Interno — Utilização de `@child:inner` e `@set`

## O que faz

Quando digita `@child:inner`, cada resposta subsequente da criança incluirá um bloco de anotação compacto no final, chamado `[INNER STATE]`. Este bloco revela o que a criança simulada está a sentir e a precisar naquele momento — sem quebrar a simulação.

- **Ativar:** digite `@child:inner` em qualquer momento durante uma sessão.
- **Desativar:** digite `@child:inner off` para regressar às respostas padrão da criança.

A anotação é uma referência funcional rápida para o cuidador. Permite ver a lógica interna por detrás do comportamento da criança enquanto continua a experienciar a interação tal como se desenrolaria na prática.

## Os campos da anotação

Cada bloco `[INNER STATE]` contém os seguintes campos:

| Campo | O que indica | Exemplos de valores |
|---|---|---|
| **Feeling** | A emoção atual da criança, identificada de forma direta. | angry, anxious, defeated, bored, blindsided, relieved |
| **Arousal** | O nível de ativação do sistema nervoso da criança. | low / medium / high / overloaded |
| **What would help right now** | Uma coisa concreta que o adulto poderia fazer ou mudar. | um aviso de 2 minutos antes da exigência; escolha entre duas tarefas; reconhecimento da frustração |
| **What just made it worse** | Uma coisa concreta que escalou ou fechou a criança, ou "nothing" se a abordagem do adulto foi bem calibrada. | perda abrupta de atividade preferida; voz elevada; sem aviso de transição; "nothing" |

### Trajetória de escalada

O bloco `[INNER STATE]` inclui também uma subsecção de trajetória de escalada:

| Campo | O que indica | Exemplos de valores |
|---|---|---|
| **Trajectory** | Direção da escalada ao longo dos turnos. | stable / building / near-threshold / at-threshold |
| **Next likely behavior** | Uma previsão comportamentalmente específica. | fecha o livro com força; fica em silêncio; começa a argumentar mais alto |
| **Interrupt lever** | Uma ação concreta do cuidador que poderia alterar a trajetória. | oferecer uma pausa de 2 minutos; baixar a voz e validar a frustração; desengajar |

**Definições de trajetória:**

| Valor | Significado |
|---|---|
| stable | Ativação não está a subir; a interação não está a adicionar carga de stress. |
| building | Ativação a subir; parcialmente regulado; janela de intervenção aberta. |
| near-threshold | Mais uma entrada escalante provavelmente desencadeia colapso visível. |
| at-threshold | Já em colapso; a desescalada requer desengajamento, não resolução de problemas. A alavanca de interrupção é sempre uma variante de: **desengajar**. |

A trajetória transita entre turnos. Não se reinicia a menos que uma alavanca seja aplicada com sucesso ou `@set clear` seja emitido.

## Exemplo de saída

Exemplo de uma resposta da criança com `@child:inner` ativo:

> **Adulto:** Tens de desligar o iPad agora. Saímos daqui a 5 minutos.
>
> **PAIciente (criança):** *Não levanta os olhos.* Cinco minutos não chega. Estou a meio de uma coisa.
>
> [INNER STATE]
> Feeling: angry, blindsided
> Arousal: high
> What would help right now: a 2-minute warning before the demand
> What just made it worse: no transition warning; abrupt loss of preferred activity
> Escalation path:
>   Trajectory: building
>   Next likely behavior: ignores adult; volume rises if pushed
>   Interrupt lever: acknowledge the interruption and offer a defined wind-down window

A resposta falada da criança é o que o cuidador ouve. O bloco `[INNER STATE]` é o que o cuidador normalmente não veria — a interpretação funcional por baixo do comportamento.

## Utilizar `@set` para injetar condições iniciais

O comando `@set` permite pré-carregar o estado da criança antes de uma interação começar. Isto é útil para praticar cenários específicos (ex.: uma criança que já está fatigada e em rebound de medicação).

**Parâmetros disponíveis:**

| Parâmetro | Valores válidos | Abreviatura numérica |
|---|---|---|
| `feeling` | Texto livre entre aspas | — |
| `arousal` | low / medium / high / overloaded | 1 / 2 / 3 / 4 |
| `trajectory` | stable / building / near-threshold / at-threshold | 1 / 2 / 3 / 4 |
| `trust` | low / medium / high | 1 / 2 / 3 |
| `fatigue` | low / medium / high | 1 / 2 / 3 |
| `medication` | on / wearing-off / off | 1 / 2 / 3 |
| `hyperfocus` | Nome do tópico entre aspas | — |
| `context` | Texto livre entre aspas (história de fundo — surge apenas através do comportamento, nunca divulgado no diálogo) | — |

**Exemplo:**

```
@set arousal=high trajectory=near-threshold trust=low medication=wearing-off fatigue=high feeling="anxious, ashamed"
```

Equivalente em abreviatura:

```
@ arousal=3 trajectory=3 trust=1 medication=2 fatigue=3 feeling="anxious, ashamed"
```

Quando `@child:inner` está ativo, os parâmetros injetados são marcados com `← [SET]`. Quando a interação move organicamente um parâmetro do seu valor injetado, o marcador muda para `← [organic]`.

Utilize `@set clear` para repor todos os overrides. Utilize `@set ?` para ver a tabela de parâmetros a qualquer momento.

## Quando ativar `@child:inner`

- **Primeira utilização.** Ative durante as primeiras sessões para aprender a ler a lógica comportamental do modelo da criança.
- **Após uma escalada.** Se uma interação escalou e não tem a certeza do porquê, ative o modo de estado interno e repita o cenário com `@replay`. As anotações mostrarão onde a ativação da criança subiu e o que a desencadeou.
- **Durante a prática de transições.** Transições (dispositivo para trabalhos de casa, brincadeira para hora de dormir, casa para carro) são um ponto de fricção comum. Os campos de estado interno tornam visível se a criança se sentiu avisada, com escolha, ou apanhada desprevenida.
- **Ao comparar abordagens.** Execute o mesmo cenário duas vezes com formulações diferentes. As anotações de estado interno permitem comparar não apenas o que a criança disse, mas o que a criança sentiu.
- **Ao utilizar `@set`.** O estado injetado é mais visível quando o modo de estado interno está ativo — pode ver exatamente quais parâmetros permanecem nos valores injetados e quais derivaram organicamente.

## Quando desativar

- **Para imersão.** Quando estiver confortável a ler o comportamento da criança, desative as anotações para praticar a interpretação do estado da criança apenas a partir de palavras e ações — mais próximo da vida real.
- **Para testar a sua própria leitura.** Tente uma sessão sem anotações, depois utilize `@debrief` para obter a análise do clínico. Compare a sua interpretação com a decomposição funcional do clínico.

## Como se liga ao `@debrief`

`@child:inner` e `@debrief` servem propósitos diferentes em momentos diferentes:

| | `@child:inner` | `@debrief` |
|---|---|---|
| **Quando** | Durante a interação, em tempo real | Após a interação estar completa |
| **Quem fala** | A persona da criança (com anotações anexadas) | A persona de clínico |
| **O que obtém** | Instantâneos de estado interno turno a turno, incluindo trajetória de escalada | Análise completa de antecedente–comportamento–consequência com abordagens alternativas |
| **Melhor para** | Ver o que está a acontecer dentro da criança momento a momento | Compreender o que aconteceu ao longo de toda a troca e o que mudar |

Uma sequência de prática típica: ativar `@child:inner`, opcionalmente injetar estado com `@set`, executar a interação, depois utilizar `@debrief` para uma revisão estruturada. As anotações de estado interno dão-lhe os dados; o debrief dá-lhe a análise. Após o debrief, utilize `@child` para retomar a partir do estado suspenso, ou `@set clear` para reiniciar.

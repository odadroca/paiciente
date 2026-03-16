<!-- i18n: source=prompt/design-notes.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
Versao: 2.0 | Ultima atualizacao: 2026-03-11

# Notas de Design

## Conjunto de instrucoes unico: comportamento documentado

O valor distintivo do PAIciente reside na combinacao de regras de interacao e nao em qualquer conceito clinico isolado. O conjunto de regras documentado pode ser resumido da seguinte forma.

| Familia de instrucoes | Comportamento documentado | Consequencia pratica |
|---|---|---|
| Gestao linguistica | Responde no idioma do utilizador; traduz dialogos, analises e valores de campos. Todos os meta-comandos e as etiquetas de campos do `[INNER STATE]` permanecem em ingles. | A interface mantem-se natural para cuidadores multilingues sem comprometer a sintaxe dos comandos. |
| Alternancia de persona | O modo ativo e controlado explicitamente por comandos `@` em vez de ser inferido silenciosamente. | O utilizador sabe sempre se esta a interagir com o modelo da crianca ou com o analista. |
| Continuidade de estado | O contexto da conversa e preservado e pode ser resumido a pedido atraves de `@status`. A continuidade depende da disponibilidade da janela de contexto. | Sessoes repetidas podem basear-se em tentativas anteriores em vez de reiniciar a cada turno. |
| Modulacao de estado | O comando `@set` injeta condicoes iniciais (excitacao, trajetoria, confianca, fadiga, medicacao, hiperfoco, sentimento, contexto) na persona da crianca. Os valores evoluem organicamente, exceto se `persist` for utilizado. | Os utilizadores podem ensaiar cenarios especificos sem esperar por uma escalada organica. |
| Realismo da crianca | A persona da crianca modela desafio, bloqueio, distracao e conformidade gradual em vez de obediencia instantanea. Um mecanismo de protecao contra fugas impede a divulgacao do contexto injetado. | O utilizador pode observar a consequencia natural de formulacoes inadequadas ou transicoes abruptas. |
| Estrutura clinica | A persona do clinico separa sempre factos observados, hipoteses e recomendacoes. | A interpretacao tem menor probabilidade de ser confundida com evidencia. |
| Limites | O sistema evita diagnosticar utilizadores ou criancas e mantem-se dentro do ambito solicitado. | Apoia a pratica e a reflexao sem reivindicar autoridade clinica em excesso. |
| Apoio a tarefas | Quando solicitado sobre como completar uma tarefa, o clinico decompoe a tarefa em passos adequados a crianca e preve pontos de recusa. | O aconselhamento e operacional em vez de generico. |
| Revisao de sessao | As funcoes de repeticao e debriefing suportam testes contrafactuais de diferentes abordagens do adulto. `@debrief` suspende o estado da crianca para retoma posterior. | O utilizador pode comparar abordagens em vez de se basear apenas na intuicao. |

## Fundamentacao do design

### 6.1 Porque comecar no modo clinico

Comecar no modo clinico reduz a probabilidade de a conversa se tornar numa dramatizacao nao estruturada. Primeiro estabelece factos, exigencias da tarefa, restricoes de transicao e o objetivo do adulto, antes de o utilizador testar uma interacao em tempo real.

### 6.2 Porque a persona da crianca e intencionalmente inconveniente

Uma simulacao util deve preservar a friccao. Se a persona da crianca respondesse como um alvo de guiao obediente, o utilizador nunca veria quais os comportamentos do adulto que desencadeiam de forma fiavel a recusa, a discussao ou o bloqueio. O modelo trata, portanto, o desafio como responsivo ao stress e dependente do contexto, em vez de malicioso.

### 6.3 Porque o tom do clinico e direto

A persona do clinico evita o encorajamento excessivo porque rotinas familiares emocionalmente carregadas requerem frequentemente uma analise precisa de erros. Um estilo vago e excessivamente solidario pode ocultar o papel funcional da escalada do adulto, expectativas pouco claras ou pressupostos temporais irrealistas.

### 6.4 Porque os comandos sao importantes

O vocabulario de comandos cria mudancas de modo explicitas. Isto e importante porque a dramatizacao, a meta-analise e a geracao de guioes sao tarefas diferentes com requisitos de saida diferentes. O PAIciente mantem essas tarefas separadas em vez de as misturar.

### 6.5 Porque `@set` existe

A modulacao direta de estado permite que facilitadores e utilizadores experientes ensaiem cenarios clinicos especificos sem esperar por uma escalada organica. Permite tambem comparacoes controladas — executar a mesma interacao duas vezes sob condicoes iniciais diferentes. O modificador `persist` suporta cenarios em que uma variavel especifica deve permanecer constante (por exemplo, testar abordagens sob efeito de rebound medicamentoso fixo).

### 6.6 Porque a trajetoria se mantem

A trajetoria de escalada nao reinicia entre turnos porque a excitacao real nao reinicia entre turnos. Uma crianca que foi levada ate perto do limiar nao regressa a linha de base simplesmente porque a proxima afirmacao do adulto e neutra. Esta opcao de design obriga o cuidador a praticar a desescalada como um processo de multiplos turnos e nao como uma unica afirmacao corretiva.

---

Para o enquadramento academico formal e a fundamentacao alargada, consulte [Fundamentacao Tecnica e Posicionamento Academico](../docs/Technical-Rationale-and-Academic-Positioning.md).

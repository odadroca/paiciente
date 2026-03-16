<!-- i18n: source=docs/behavior-map.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# Mapa Comportamental — Conjunto de Instruções Único

O valor distintivo do PAIciente reside na combinação de regras de interação e não em qualquer conceito clínico isolado. O conjunto de regras documentado pode ser resumido da seguinte forma.

| Família de instruções | Comportamento documentado | Consequência prática |
|---|---|---|
| Gestão linguística | Responde na língua do utilizador; traduz diálogo, análise e valores dos campos. Todos os meta-comandos e rótulos de campos `[INNER STATE]` permanecem em inglês. | A interface mantém-se natural para cuidadores multilingues sem quebrar a sintaxe dos comandos. |
| Alternância de personas | O modo ativo é controlado explicitamente por comandos `@` em vez de inferido silenciosamente. | O utilizador sabe sempre se está a falar com o modelo da criança ou com o analista. |
| Continuidade de estado | O contexto da conversa é preservado e pode ser resumido a pedido através de `@status`. A continuidade depende da disponibilidade da janela de contexto. | Sessões repetidas podem construir sobre tentativas anteriores em vez de reiniciar a cada turno. |
| Modulação de estado | O comando `@set` injeta condições iniciais (arousal, trajectory, trust, fatigue, medication, hyperfocus, feeling, context) na persona da criança. | Os utilizadores podem ensaiar cenários específicos sem esperar por escalada orgânica. |
| Realismo da criança | A persona da criança modela desafio, encerramento, distração e conformidade gradual em vez de obediência instantânea. Uma guarda de fuga impede a divulgação de contexto injetado. | O utilizador pode ver a consequência natural de formulação inadequada ou transições abruptas. |
| Estrutura clínica | A persona de clínico separa sempre factos observados, hipóteses e recomendações. | A interpretação é menos propensa a ser confundida com evidência. |
| Limites | O sistema evita diagnosticar utilizadores ou crianças e mantém-se dentro do âmbito solicitado. | Apoia a prática e a reflexão sem reivindicar autoridade clínica em excesso. |
| Andaimes de tarefas | Quando se pergunta como completar uma tarefa, o clínico decompõe a tarefa em passos do tamanho da criança e prevê pontos de recusa. | O conselho é operacional em vez de genérico. |
| Revisão de sessão | As funções de replay e debrief suportam testes contrafactuais de diferentes abordagens do adulto. `@debrief` suspende o estado da criança para retoma posterior. | O utilizador pode comparar abordagens em vez de confiar apenas na intuição. |

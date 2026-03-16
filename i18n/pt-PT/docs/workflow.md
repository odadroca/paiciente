<!-- i18n: source=docs/workflow.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# Fluxo de Trabalho Recomendado

> Esta é a sequência recomendada para a primeira utilização. Utilizadores experientes podem entrar em qualquer passo.

1. Comece em `@clinician` e descreva o contexto do problema em termos concretos.
2. Solicite um plano, guião ou mapa de escalada para a rotina em questão.
3. Opcionalmente, utilize `@set` para injetar condições iniciais (ex.: `@set arousal=high medication=wearing-off`).
4. Mude para `@child` e execute a interação como simulação. Ative `@child:inner` se pretender anotações de estado em tempo real.
5. Utilize `@debrief` para converter a troca numa análise de antecedente–comportamento–consequência. O estado da criança é suspenso, não apagado.
6. Utilize `@replay` para repetir o mesmo momento com uma abordagem diferente do adulto.

Esta estrutura encoraja a prática iterativa. Em vez de perguntar abstratamente "o que devo fazer?", o utilizador pode testar formulação, timing, avisos de transição e arquitetura de escolha contra um modelo comportamental consistente.

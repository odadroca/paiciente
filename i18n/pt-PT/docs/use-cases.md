<!-- i18n: source=docs/use-cases.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# Exemplos de Casos de Uso

## 10.1 Ensaiar uma exigência

Um cuidador que planeia interromper o tempo no tablet pode pedir ao clínico um guião de transição, depois mudar para a persona da criança e testar se a formulação parece abrupta, injusta ou compatível com escolha. Utilizar `@set hyperfocus="jogo no tablet"` antes de mudar para `@child` torna o custo da transição maximamente elevado — um teste de resistência realista.

## 10.2 Rever uma interação falhada

Após uma troca difícil no mundo real, o cuidador pode resumir o que aconteceu e pedir à persona de clínico que identifique o antecedente, o comportamento da criança, a consequência do adulto e os pontos onde a escalada poderia ter sido interrompida.

## 10.3 Construir uma lista de verificação específica para uma rotina

O utilizador pode emitir `@script rotina matinal` ou `@script início dos trabalhos de casa` e obter uma decomposição em passos do tamanho da criança, com pontos de recusa prováveis e linguagem de apoio para o cuidador.

## 10.4 Testar sob condições específicas

Um facilitador pode injetar uma combinação de parâmetros de estado — por exemplo, `@set arousal=high fatigue=high medication=wearing-off trust=low context="mau dia na escola"` — e depois executar uma interação de início de trabalhos de casa para ver como a criança responde sob stress composto. Ativar `@child:inner` durante esta interação mostra exatamente quais parâmetros permanecem nos valores injetados e quais se deslocaram organicamente.

---

Para transcrições completas destes e de outros cenários, consulte [`/examples/`](/examples/).

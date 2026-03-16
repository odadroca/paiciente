<!-- i18n: source=docs/use-cases.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# Ejemplos de Casos de Uso

## 10.1 Ensayar una exigencia

Un cuidador que planea interrumpir el tiempo en la tableta puede pedir al clínico un guion de transición, luego cambiar a la persona del niño y probar si la formulación resulta abrupta, injusta o compatible con la elección. Usar `@set hyperfocus="juego en la tableta"` antes de cambiar a `@child` hace que el coste de la transición sea máximamente alto — una prueba de resistencia realista.

## 10.2 Revisar una interacción fallida

Tras un intercambio difícil en el mundo real, el cuidador puede resumir lo ocurrido y pedir a la persona de clínico que identifique el antecedente, la conducta del niño, la consecuencia del adulto y los puntos donde la escalada podría haberse interrumpido.

## 10.3 Construir una lista de verificación específica para una rutina

El usuario puede emitir `@script rutina matinal` o `@script inicio de deberes` y obtener un desglose en pasos del tamaño del niño, con puntos de rechazo probables y lenguaje de apoyo para el cuidador.

## 10.4 Probar bajo condiciones específicas

Un facilitador puede inyectar una combinación de parámetros de estado — por ejemplo, `@set arousal=high fatigue=high medication=wearing-off trust=low context="mal día en la escuela"` — y luego ejecutar una interacción de inicio de deberes para ver cómo responde el niño bajo estrés compuesto. Activar `@child:inner` durante esta interacción muestra exactamente qué parámetros permanecen en los valores inyectados y cuáles se han desplazado orgánicamente.

---

Para transcripciones completas de estos y otros escenarios, consulte [`/examples/`](/examples/).

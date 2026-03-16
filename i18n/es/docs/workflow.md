<!-- i18n: source=docs/workflow.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# Flujo de Trabajo Recomendado

> Esta es la secuencia recomendada para el primer uso. Los usuarios experimentados pueden entrar en cualquier paso.

1. Comience en `@clinician` y describa el contexto del problema en términos concretos.
2. Solicite un plan, guion o mapa de escalada para la rutina en cuestión.
3. Opcionalmente, utilice `@set` para inyectar condiciones iniciales (ej.: `@set arousal=high medication=wearing-off`).
4. Cambie a `@child` y ejecute la interacción como simulación. Active `@child:inner` si desea anotaciones de estado en tiempo real.
5. Utilice `@debrief` para convertir el intercambio en un análisis de antecedente–conducta–consecuencia. El estado del niño se suspende, no se borra.
6. Utilice `@replay` para repetir el mismo momento con un enfoque diferente del adulto.

Esta estructura fomenta la práctica iterativa. En lugar de preguntar en abstracto "¿qué debería hacer?", el usuario puede probar formulación, temporización, avisos de transición y arquitectura de elección contra un modelo conductual consistente.

<!-- i18n: source=docs/behavior-map.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# Mapa Conductual — Conjunto de Instrucciones Único

El valor distintivo de PAIciente reside en la combinación de reglas de interacción y no en ningún concepto clínico aislado. El conjunto de reglas documentado puede resumirse de la siguiente manera.

| Familia de instrucciones | Comportamiento documentado | Consecuencia práctica |
|---|---|---|
| Gestión lingüística | Responde en el idioma del usuario; traduce diálogo, análisis y valores de campos. Todos los meta-comandos y etiquetas de campos `[INNER STATE]` permanecen en inglés. | La interfaz se mantiene natural para cuidadores multilingües sin romper la sintaxis de comandos. |
| Alternancia de personas | El modo activo se controla explícitamente mediante comandos `@` en lugar de inferirse silenciosamente. | El usuario siempre sabe si está hablando con el modelo del niño o con el analista. |
| Continuidad de estado | El contexto de la conversación se preserva y puede resumirse a demanda mediante `@status`. La continuidad depende de la disponibilidad de la ventana de contexto. | Las sesiones repetidas pueden construir sobre intentos anteriores en lugar de reiniciar en cada turno. |
| Modulación de estado | El comando `@set` inyecta condiciones iniciales (arousal, trajectory, trust, fatigue, medication, hyperfocus, feeling, context) en la persona del niño. | Los usuarios pueden ensayar escenarios específicos sin esperar una escalada orgánica. |
| Realismo del niño | La persona del niño modela desafío, cierre, distracción y cumplimiento gradual en lugar de obediencia instantánea. Una protección contra fugas impide la revelación de contexto inyectado. | El usuario puede ver la consecuencia natural de una formulación inadecuada o transiciones abruptas. |
| Estructura clínica | La persona de clínico siempre separa hechos observados, hipótesis y recomendaciones. | La interpretación es menos propensa a confundirse con evidencia. |
| Límites | El sistema evita diagnosticar a usuarios o niños y se mantiene dentro del alcance solicitado. | Apoya la práctica y la reflexión sin reclamar autoridad clínica en exceso. |
| Andamiaje de tareas | Cuando se pregunta cómo completar una tarea, el clínico descompone la tarea en pasos del tamaño del niño y predice puntos de rechazo. | El consejo es operativo en lugar de genérico. |
| Revisión de sesión | Las funciones de replay y debrief soportan pruebas contrafactuales de diferentes enfoques del adulto. `@debrief` suspende el estado del niño para reanudación posterior. | El usuario puede comparar enfoques en lugar de confiar solo en la intuición. |

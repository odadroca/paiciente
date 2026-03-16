<!-- i18n: source=docs/overview.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# Visión General

## 1. Propósito y alcance

PAIciente está diseñado para cuidadores, padres, tutores, profesores y clínicos que desean una forma estructurada de ensayar interacciones difíciles con un niño que presenta dificultades de función ejecutiva asociadas al TDAH (Trastorno por Déficit de Atención e Hiperactividad) y comportamiento oposicional.

Cumple tres funciones prácticas:

- **Simulación:** el usuario puede hablar con una persona de niño y observar cómo es probable que se reciba un enfoque específico del adulto.
- **Análisis:** el usuario puede cambiar a una persona de clínico que descompone lo ocurrido en términos conductuales.
- **Herramientas:** la persona de clínico puede generar guiones, listas de verificación, mapas de escalada y desgloses de tareas.

El alcance previsto es deliberadamente estrecho. Es una herramienta de simulación y documentación, no un sustituto de terapia, evaluación diagnóstica o respuesta de emergencia.

## 2. Arquitectura de alto nivel

PAIciente opera mediante dos personas explícitamente conmutables y un vocabulario de comandos. La persona activa determina tanto el tono como el formato de la respuesta.

### 2.1 Controles de modo principales

| Comando | Función | Notas |
|---|---|---|
| `@clinician` | Activa la persona de clínico. | Predeterminado al inicio de la conversación. |
| `@child` | Activa la persona del niño. | Utilizado para simulación en vivo. |
| `@child:inner` | Añade una anotación de estado interno tras la respuesta del niño. | Una referencia rápida para el cuidador. |
| `@child:inner off` | Elimina la anotación de estado interno. | Devuelve la persona del niño al formato estándar. |
| `@status` | Indica la persona activa y el contexto de la conversación hasta el momento. | Útil en sesiones largas. |

### 2.2 Modulación de estado

| Comando | Función | Notas |
|---|---|---|
| `@set [p]=[v]` | Define parámetros de estado del niño (arousal, trajectory, trust, fatigue, medication, hyperfocus, feeling, context). | Condición inicial; deriva orgánica aplica. |
| `@set [p]=[v] persist` | Bloquea el valor contra la deriva orgánica. | Para escenarios controlados. |
| `@set clear` | Restablece todas las sobrecargas manuales. | Devuelve al estado orgánico simulado. |
| `@set ?` | Muestra la tabla de parámetros. | Referencia rápida. |
| `@ [p]=[v]` | Alias abreviado para `@set`. | Claves numéricas aceptadas. |

### 2.3 Controles de revisión y planificación

| Comando | Función | Notas |
|---|---|---|
| `@replay` | Repite la última respuesta del niño y solicita un nuevo enfoque del adulto. | El usuario proporciona el nuevo enfoque. |
| `@debrief` | Cambia a modo clínico para análisis de la interacción anterior. | El estado del niño se suspende, no se borra. |
| `@script [tarea]` | Produce un guion para el cuidador y una lista de verificación visual para una tarea específica. | Ejemplo: deberes, salir de casa, hora de dormir. |
| `@escalation-map [escenario]` | Mapea caminos probables de escalada y bifurcaciones de desescalada. | Útil para rutinas con transiciones o elevado conflicto. |

> **Por qué importa la estructura de dos personas.** Una persona permite al usuario practicar la interacción en sí. La otra convierte la interacción en una formulación conductual del caso con alternativas. El valor surge de alternar entre ambas, no de ninguna de forma aislada.

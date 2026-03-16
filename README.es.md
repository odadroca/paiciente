<!-- i18n: source=README.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# PAIciente

[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)

### PAIciente es una herramienta de apoyo a cuidadores basada en comandos, que alterna entre una persona de clínico y una persona de simulación infantil. Está diseñada para ayudar a cuidadores a ensayar interacciones difíciles, analizar patrones de escalada y generar guiones y listas de verificación fundamentados en modelos clínicos de TDAH y TND basados en evidencia.

---

## Qué hace

PAIciente cumple tres funciones prácticas:

- **Simulación** — hablar con una persona de niño y observar cómo es probable que se reciba un enfoque determinado del adulto.
- **Análisis** — cambiar a una persona de clínico que descompone lo ocurrido en términos conductuales.
- **Herramientas** — la persona de clínico genera guiones, listas de verificación, mapas de escalada y desgloses de tareas.

El alcance previsto es deliberadamente estrecho. Es una herramienta de simulación y documentación, no un sustituto de terapia, evaluación diagnóstica o respuesta de emergencia.

---

## Referencia de comandos

### Controles de modo principales

| Comando | Función | Notas |
|---|---|---|
| `@clinician` | Activa la persona de clínico. | Predeterminado al inicio de la conversación. |
| `@child` | Activa la persona del niño. | Utilizado para simulación en vivo. |
| `@child:inner` | Añade una anotación de estado interno tras la respuesta del niño (sentimiento, activación, qué ayudaría, qué lo empeoró, trayectoria de escalada). | Una referencia rápida para el cuidador. Ver [guía](i18n/es/docs/inner-state-guide.md). |
| `@child:inner off` | Elimina la anotación de estado interno. | Devuelve la persona del niño al formato estándar. |
| `@status` | Indica la persona activa y el contexto de la conversación hasta el momento. | Útil en sesiones largas. |

### Modulación de estado

| Comando | Función | Notas |
|---|---|---|
| `@set [p]=[v]` | Define parámetros de estado del niño (arousal, trajectory, trust, fatigue, medication, hyperfocus, feeling, context). | Condición inicial; deriva orgánica aplica. |
| `@set [p]=[v] persist` | Igual que el anterior, pero bloquea el valor contra la deriva orgánica. | Útil para escenarios controlados. |
| `@set clear` | Restablece todas las sobrecargas manuales al estado orgánico simulado. | También restablece el estado del niño suspendido tras `@debrief`. |
| `@set ?` | Muestra la tabla de parámetros con valores válidos. | Referencia rápida sin modificar el estado. |
| `@ [p]=[v]` | Alias abreviado para `@set`; claves numéricas aceptadas. | Ej.: `@ arousal=3 trust=2`. |

### Controles de revisión y planificación

| Comando | Función | Notas |
|---|---|---|
| `@replay` | Repite la última respuesta del niño y solicita un nuevo enfoque del adulto. | El usuario proporciona el nuevo enfoque; el modelo no genera alternativa automáticamente. |
| `@debrief` | Cambia a modo clínico para análisis de la interacción anterior. El estado del niño se suspende, no se borra. | Se centra en antecedente, conducta y consecuencia. |
| `@script [tarea]` | Produce un guion para el cuidador y una lista de verificación visual para una tarea específica. | Ejemplo: deberes, salir de casa, hora de dormir. |
| `@escalation-map [escenario]` | Mapea caminos probables de escalada y bifurcaciones de desescalada. | Útil para rutinas con transiciones o elevado conflicto. |

---

## Probar

| Plataforma | Enlace |
|---|---|
| ChatGPT (Custom GPT) | [Sandbox](https://chatgpt.com/g/g-69b1a7644f5c81919f3fca1bbc2926fa-paiciente-v2-0) |
| Mistral (Le Chat Agent) | [Sandbox](https://chat.mistral.ai/chat/553205e3-526a-472d-99d0-0916596fa54b) |
| Gemini (Gem) | [Sandbox](https://gemini.google.com/gem/1N5cyhZd34Pb-KEzMxdsaZxjSt7jKF4jm?usp=sharing) |
| Claude | Autoinstanciación mediante [guía de implementación](implementations/claude.md) |

Consulte [`/implementations/`](implementations/) para instrucciones de configuración paso a paso en cada plataforma.

---

## Limitaciones

PAIciente tiene límites significativos que deben comprenderse explícitamente:

- Es una herramienta de simulación y apoyo, no un motor de diagnóstico.
- No sustituye a un clínico, un equipo escolar o una evaluación de emergencia.
- La persona del niño es una aproximación modelada, no una predicción literal de lo que un niño específico dirá.
- Su utilidad depende de la especificidad y honestidad de la descripción del cuidador.
- Una buena simulación puede aun así estar equivocada en casos individuales, porque cada niño varía en temperamento, historia y contexto.

Un modelo de simulación convincente puede parecer persuasivo incluso cuando es solo aproximado. Por esa razón, la exigencia de la persona de clínico de separar hechos observados de inferencias es una salvaguarda importante.

---

## Documentación

La documentación completa está disponible en [`/docs/`](docs/). Consulte el [Índice](docs/table-of-contents.md) para una visión general de todos los archivos del repositorio.

- [Visión general](i18n/es/docs/overview.md) — propósito, alcance y arquitectura
- [Personas](i18n/es/docs/personas.md) — especificaciones de las personas de clínico y niño
- [Flujo de trabajo](i18n/es/docs/workflow.md) — secuencia de uso recomendada
- [Mapa conductual](docs/behavior-map.md) — conjunto de instrucciones único (EN)
- [Guía de estado interno](i18n/es/docs/inner-state-guide.md) — uso de `@child:inner` y `@set`
- [Mapa de evidencia](docs/evidence-map.md) — fundamentación académica (EN)
- [Limitaciones](i18n/es/docs/limitations.md) — límites de seguridad
- [Casos de uso](i18n/es/docs/use-cases.md) — escenarios ejemplo
- [Fundamentación técnica](docs/Technical-Rationale-and-Academic-Positioning.md) — marco formal y posicionamiento académico (EN)

Referencias académicas: [`/references/`](references/)

---

## Licencia

Este trabajo está licenciado bajo una [Licencia Creative Commons Atribución-CompartirIgual 4.0 Internacional](https://creativecommons.org/licenses/by-sa/4.0/).

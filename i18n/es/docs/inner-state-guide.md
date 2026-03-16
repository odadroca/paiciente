<!-- i18n: source=docs/inner-state-guide.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# Guía de Estado Interno — Uso de `@child:inner` y `@set`

## Qué hace

Cuando escribe `@child:inner`, cada respuesta posterior del niño incluirá un bloque de anotación compacto al final llamado `[INNER STATE]`. Este bloque revela lo que el niño simulado está sintiendo y necesitando en ese momento — sin romper la simulación.

- **Activar:** escriba `@child:inner` en cualquier momento durante una sesión.
- **Desactivar:** escriba `@child:inner off` para volver a las respuestas estándar del niño.

La anotación es una referencia funcional rápida para el cuidador. Permite ver la lógica interna detrás del comportamiento del niño mientras se sigue experimentando la interacción tal como se desarrollaría en la práctica.

## Los campos de la anotación

Cada bloque `[INNER STATE]` contiene los siguientes campos:

| Campo | Qué indica | Ejemplos de valores |
|---|---|---|
| **Feeling** | La emoción actual del niño, identificada de forma directa. | angry, anxious, defeated, bored, blindsided, relieved |
| **Arousal** | El nivel de activación del sistema nervioso del niño. | low / medium / high / overloaded |
| **What would help right now** | Una cosa concreta que el adulto podría hacer o cambiar. | un aviso de 2 minutos antes de la exigencia; elección entre dos tareas; reconocimiento de la frustración |
| **What just made it worse** | Una cosa concreta que escaló o cerró al niño, o "nothing" si el enfoque del adulto fue bien calibrado. | pérdida abrupta de actividad preferida; voz elevada; sin aviso de transición; "nothing" |

### Trayectoria de escalada

El bloque `[INNER STATE]` también incluye una subsección de trayectoria de escalada:

| Campo | Qué indica | Ejemplos de valores |
|---|---|---|
| **Trajectory** | Dirección de la escalada a lo largo de los turnos. | stable / building / near-threshold / at-threshold |
| **Next likely behavior** | Una predicción conductualmente específica. | cierra el libro de golpe; se queda en silencio; empieza a discutir más alto |
| **Interrupt lever** | Una acción concreta del cuidador que podría alterar la trayectoria. | ofrecer una pausa de 2 minutos; bajar la voz y validar la frustración; desengancharse |

**Definiciones de trayectoria:**

| Valor | Significado |
|---|---|
| stable | La activación no está subiendo; la interacción no está añadiendo carga de estrés. |
| building | Activación subiendo; parcialmente regulado; ventana de intervención abierta. |
| near-threshold | Una entrada escalante más probablemente desencadena un colapso visible. |
| at-threshold | Ya en colapso; la desescalada requiere desenganche, no resolución de problemas. La palanca de interrupción es siempre una variante de: **desengancharse**. |

La trayectoria se transmite entre turnos. No se reinicia a menos que se aplique una palanca con éxito o se emita `@set clear`.

## Ejemplo de salida

Ejemplo de una respuesta del niño con `@child:inner` activo:

> **Adulto:** Tienes que apagar el iPad ahora. Nos vamos en 5 minutos.
>
> **PAIciente (niño):** *No levanta la vista.* Cinco minutos no es suficiente. Estoy en medio de algo.
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

La respuesta hablada del niño es lo que el cuidador oye. El bloque `[INNER STATE]` es lo que el cuidador normalmente no vería — la interpretación funcional debajo del comportamiento.

## Usar `@set` para inyectar condiciones iniciales

El comando `@set` permite precargar el estado del niño antes de que comience una interacción. Esto es útil para practicar escenarios específicos (ej.: un niño que ya está fatigado y en rebote de medicación).

**Parámetros disponibles:**

| Parámetro | Valores válidos | Abreviatura numérica |
|---|---|---|
| `feeling` | Texto libre entre comillas | — |
| `arousal` | low / medium / high / overloaded | 1 / 2 / 3 / 4 |
| `trajectory` | stable / building / near-threshold / at-threshold | 1 / 2 / 3 / 4 |
| `trust` | low / medium / high | 1 / 2 / 3 |
| `fatigue` | low / medium / high | 1 / 2 / 3 |
| `medication` | on / wearing-off / off | 1 / 2 / 3 |
| `hyperfocus` | Nombre del tema entre comillas | — |
| `context` | Texto libre entre comillas (historia de fondo — aparece solo a través del comportamiento, nunca se revela en el diálogo) | — |

**Ejemplo:**

```
@set arousal=high trajectory=near-threshold trust=low medication=wearing-off fatigue=high feeling="anxious, ashamed"
```

Equivalente en abreviatura:

```
@ arousal=3 trajectory=3 trust=1 medication=2 fatigue=3 feeling="anxious, ashamed"
```

Cuando `@child:inner` está activo, los parámetros inyectados se marcan con `← [SET]`. Cuando la interacción mueve orgánicamente un parámetro de su valor inyectado, el marcador cambia a `← [organic]`.

Use `@set clear` para restablecer todas las sobrecargas. Use `@set ?` para ver la tabla de parámetros en cualquier momento.

## Cuándo activar `@child:inner`

- **Primer uso.** Actívelo durante sus primeras sesiones para aprender a leer la lógica conductual del modelo del niño.
- **Tras una escalada.** Si una interacción escaló y no tiene claro por qué, active el modo de estado interno y repita el escenario con `@replay`. Las anotaciones mostrarán dónde subió la activación del niño y qué lo desencadenó.
- **Durante la práctica de transiciones.** Las transiciones (dispositivo a deberes, juego a hora de dormir, casa a coche) son un punto de fricción común. Los campos de estado interno hacen visible si el niño se sintió avisado, con elección, o cogido desprevenido.
- **Al comparar enfoques.** Ejecute el mismo escenario dos veces con formulaciones diferentes. Las anotaciones de estado interno permiten comparar no solo lo que el niño dijo, sino lo que el niño sintió.
- **Al usar `@set`.** El estado inyectado es más visible cuando el modo de estado interno está activo — puede ver exactamente qué parámetros permanecen en los valores inyectados y cuáles han derivado orgánicamente.

## Cuándo desactivar

- **Para inmersión.** Cuando esté cómodo leyendo el comportamiento del niño, desactive las anotaciones para practicar la interpretación del estado del niño solo a partir de palabras y acciones — más cercano a la vida real.
- **Para probar su propia lectura.** Intente una sesión sin anotaciones, luego use `@debrief` para obtener el análisis del clínico. Compare su interpretación con el desglose funcional del clínico.

## Cómo se conecta con `@debrief`

`@child:inner` y `@debrief` sirven propósitos diferentes en momentos diferentes:

| | `@child:inner` | `@debrief` |
|---|---|---|
| **Cuándo** | Durante la interacción, en tiempo real | Después de que la interacción esté completa |
| **Quién habla** | La persona del niño (con anotaciones anexadas) | La persona de clínico |
| **Qué obtiene** | Instantáneas de estado interno turno a turno, incluyendo trayectoria de escalada | Análisis completo de antecedente–conducta–consecuencia con enfoques alternativos |
| **Mejor para** | Ver lo que está ocurriendo dentro del niño momento a momento | Comprender lo que ocurrió a lo largo de todo el intercambio y qué cambiar |

Una secuencia de práctica típica: activar `@child:inner`, opcionalmente inyectar estado con `@set`, ejecutar la interacción, luego usar `@debrief` para una revisión estructurada. Las anotaciones de estado interno le dan los datos; el debrief le da el análisis. Tras el debrief, use `@child` para retomar desde el estado suspendido, o `@set clear` para reiniciar.

<!-- i18n: source=prompt/design-notes.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
Version: 2.0 | Ultima actualizacion: 2026-03-11

# Notas de Diseno

## Conjunto de instrucciones unico: comportamiento documentado

El valor distintivo de PAIciente reside en la combinacion de reglas de interaccion y no en ningun concepto clinico aislado. El conjunto de reglas documentado puede resumirse de la siguiente manera.

| Familia de instrucciones | Comportamiento documentado | Consecuencia practica |
|---|---|---|
| Gestion linguistica | Responde en el idioma del usuario; traduce dialogos, analisis y valores de campos. Todos los metacomandos y las etiquetas de campos de `[INNER STATE]` permanecen en ingles. | La interfaz se mantiene natural para cuidadores multilingues sin comprometer la sintaxis de los comandos. |
| Alternancia de persona | El modo activo se controla explicitamente mediante comandos `@` en lugar de inferirse silenciosamente. | El usuario siempre sabe si esta interactuando con el modelo del nino o con el analista. |
| Continuidad de estado | El contexto de la conversacion se preserva y puede resumirse a demanda mediante `@status`. La continuidad depende de la disponibilidad de la ventana de contexto. | Las sesiones repetidas pueden basarse en intentos anteriores en lugar de reiniciarse en cada turno. |
| Modulacion de estado | El comando `@set` inyecta condiciones iniciales (activacion, trayectoria, confianza, fatiga, medicacion, hiperfoco, sentimiento, contexto) en la persona del nino. Los valores evolucionan organicamente, salvo que se utilice `persist`. | Los usuarios pueden ensayar escenarios especificos sin esperar una escalada organica. |
| Realismo del nino | La persona del nino modela desafio, bloqueo, distraccion y conformidad gradual en lugar de obediencia instantanea. Un mecanismo de proteccion contra fugas impide la divulgacion del contexto inyectado. | El usuario puede observar la consecuencia natural de formulaciones inadecuadas o transiciones abruptas. |
| Estructura clinica | La persona del clinico siempre separa hechos observados, hipotesis y recomendaciones. | La interpretacion tiene menor probabilidad de confundirse con la evidencia. |
| Limites | El sistema evita diagnosticar a usuarios o ninos y se mantiene dentro del ambito solicitado. | Apoya la practica y la reflexion sin reclamar autoridad clinica en exceso. |
| Apoyo a tareas | Cuando se le pregunta como completar una tarea, el clinico descompone la tarea en pasos adecuados para el nino y predice puntos de rechazo. | El asesoramiento es operativo en lugar de generico. |
| Revision de sesion | Las funciones de repeticion y debriefing soportan pruebas contrafactuales de diferentes enfoques del adulto. `@debrief` suspende el estado del nino para su reanudacion posterior. | El usuario puede comparar enfoques en lugar de basarse unicamente en la intuicion. |

## Fundamentacion del diseno

### 6.1 Por que comenzar en modo clinico

Comenzar en modo clinico reduce la probabilidad de que la conversacion se convierta en una dramatizacion no estructurada. Primero establece hechos, exigencias de la tarea, restricciones de transicion y el objetivo del adulto, antes de que el usuario pruebe una interaccion en tiempo real.

### 6.2 Por que la persona del nino es intencionalmente inconveniente

Una simulacion util debe preservar la friccion. Si la persona del nino respondiera como un objetivo de guion obediente, el usuario nunca veria cuales son los comportamientos del adulto que desencadenan de manera fiable el rechazo, la discusion o el bloqueo. El modelo trata, por tanto, el desafio como responsivo al estres y dependiente del contexto, en lugar de malicioso.

### 6.3 Por que el tono del clinico es directo

La persona del clinico evita el aliento excesivo porque las rutinas familiares emocionalmente cargadas requieren con frecuencia un analisis preciso de errores. Un estilo vago y excesivamente solidario puede ocultar el papel funcional de la escalada del adulto, las expectativas poco claras o los supuestos temporales irrealistas.

### 6.4 Por que los comandos son importantes

El vocabulario de comandos crea cambios de modo explicitos. Esto es importante porque la dramatizacion, el metaanalisis y la generacion de guiones son tareas diferentes con requisitos de salida diferentes. PAIciente mantiene esas tareas separadas en lugar de mezclarlas.

### 6.5 Por que `@set` existe

La modulacion directa de estado permite que facilitadores y usuarios experimentados ensayen escenarios clinicos especificos sin esperar una escalada organica. Tambien permite comparaciones controladas: ejecutar la misma interaccion dos veces bajo condiciones iniciales diferentes. El modificador `persist` soporta escenarios en los que una variable especifica debe permanecer constante (por ejemplo, probar enfoques bajo efecto de rebote medicamentoso fijo).

### 6.6 Por que la trayectoria se mantiene

La trayectoria de escalada no se reinicia entre turnos porque la activacion real no se reinicia entre turnos. Un nino que ha sido llevado cerca del umbral no regresa a la linea de base simplemente porque la siguiente afirmacion del adulto es neutra. Esta decision de diseno obliga al cuidador a practicar la desescalada como un proceso de multiples turnos y no como una unica afirmacion correctiva.

---

Para el marco academico formal y la fundamentacion ampliada, consulte [Fundamentacion Tecnica y Posicionamiento Academico](../docs/Technical-Rationale-and-Academic-Positioning.md).

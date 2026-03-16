<!-- i18n: source=docs/Technical-Rationale-and-Academic-Positioning.md | base-version=v2.1.0 | last-updated=2026-03-16 -->

# PAIciente: Un Sistema Politrópico Restringido por Prompt que Implementa Análogos Conductuales de Competencia Delimitada y Verificación Estructurada Sin Monotropismo Arquitectural

**Fundamentación Técnica y Posicionamiento Académico**

*PAIciente v2.0 - Documento de Encuadre de Diseño*

---

## Resumen

PAIciente es una herramienta de prompt estructurado de código abierto que simula un niño que presenta Trastorno por Déficit de Atención e Hiperactividad (TDAH, tipo combinado) y Trastorno Negativista Desafiante (TND), dirigida a entornos de práctica para padres, educadores y clínicos. Este artículo proporciona una fundamentación detallada para el encuadre formal del sistema como un *sistema politrópico restringido por prompt que implementa análogos conductuales de competencia delimitada y verificación estructurada sin monotropismo arquitectural*. Cada componente de este encuadre se define, justifica frente a alternativas y fundamenta tanto en el diseño de ingeniería del sistema como en su base de evidencia clínica. El artículo argumenta que este encuadre no es meramente descriptivo sino constitutivo: distingue a PAIciente de categorías adyacentes (personas de chatbot, herramientas clínicas ajustadas, andamiajes de juego de roles) y hace explícitos los compromisos de diseño que gobiernan su fidelidad de simulación, arquitectura de verificación y portabilidad entre plataformas.

---

## 1. Introducción

Los modelos de lenguaje de gran escala (LLMs) se aplican cada vez más a la simulación conductual, la formación clínica y la educación basada en escenarios. La mayoría de estas aplicaciones se encuadran en una de dos categorías: (a) modelos ajustados arquitecturalmente comprometidos con un único perfil conductual, o (b) sistemas de juego de roles ligeramente instruidos sin gestión formal de estado, mecanismo de verificación ni fundamentación en evidencia. PAIciente no se encuadra en ninguna categoría. Es un sistema exclusivamente de prompt que logra simulación conductual estructurada a través de restricciones ingenieriles sobre un sustrato LLM de uso general, manteniendo la capacidad analítica plena del sustrato para una persona de clínico co-residente.

Este requisito dual - *simular competencia delimitada* en un modo y *ejercer competencia analítica plena* en otro, dentro de la misma sesión y ventana de contexto - es la tensión de diseño central. La declaración de encuadre la resuelve nombrando cinco compromisos arquitecturales:

1. **Restringido por prompt** - la frontera del sistema es el prompt, no los pesos del modelo.
2. **Politrópico** - múltiples orientaciones de procesamiento funcionalmente distintas coexisten.
3. **Análogos conductuales** - los objetivos de simulación son correspondencias estructurales en el comportamiento, no homología mecanicista.
4. **Competencia delimitada** - la simulación restringe deliberadamente la salida a lo largo de dimensiones clínicamente especificadas.
5. **Sin monotropismo arquitectural** - el sustrato no está especializado; la especialización es emergente de la lógica del prompt.

Cada uno se examina a continuación.

---

## 2. Definiciones y Alcance

### 2.1 Restringido por Prompt

Un sistema es *restringido por prompt* cuando su especificación conductual reside enteramente en la capa de prompt - las instrucciones en lenguaje natural entregadas al modelo en tiempo de inferencia - y no en los pesos del modelo, funciones de recompensa, corpus de ajuste fino o código de orquestación externo. El prompt es el sistema. Los cambios en el comportamiento del sistema son cambios en el texto del prompt. Las capacidades preentrenadas del modelo no se modifican.

### 2.2 Politrópico

*Politrópico* (del griego *polytropos*: "de muchas vueltas") designa un sistema que implementa múltiples orientaciones de procesamiento funcionalmente distintas, cada una con su propio contrato de salida, postura epistémica y lógica de interacción, seleccionables dentro de una única sesión. Esto contrasta con sistemas *monotrópicos* que implementan una orientación conductual, y con sistemas *multi-agente* que distribuyen orientaciones entre instancias de modelo separadas.

### 2.3 Análogo Conductual

Un *análogo conductual* es un patrón de salida estructuralmente similar que corresponde a un comportamiento objetivo sin compartir su mecanismo generador. Cuando la persona infantil de PAIciente produce evocación fragmentada de múltiples pasos, la salida es *análoga* a la limitación de la memoria de trabajo en el TDAH - coincide con el patrón observable - pero es generada por restricciones de prompt en un sistema sin cuello de botella de memoria de trabajo. La distinción entre análogo y homólogo (mismo mecanismo) es crítica para un posicionamiento honesto: PAIciente simula la superficie conductual del TDAH+TND, no su sustrato neurocognitivo.

### 2.4 Competencia Delimitada

*Competencia delimitada* se refiere al rendimiento deliberadamente restringido a lo largo de dimensiones cognitivas, lingüísticas, emocionales y conductuales especificadas. El modelo subyacente es capaz de razonamiento fluido en múltiples párrafos, seguimiento perfecto de instrucciones y salida afectivamente neutra. El prompt restringe estas capacidades a lo largo de ejes clínicamente definidos: función ejecutiva (secuenciación, estimación temporal, iniciación de tareas), regulación emocional (tolerancia a la frustración, sensibilidad al rechazo), asignación atencional (compromiso dirigido por interés, hiperfoco), y respuesta socioconductual (rechazo oposicionista, condiciones de cumplimiento).

### 2.5 Monotropismo Arquitectural

El *monotropismo arquitectural* describe sistemas cuya especialización se logra mediante modificación irreversible o de alto coste del sustrato del modelo - típicamente ajuste fino, RLHF con funciones de recompensa específicas del dominio, o cambios arquitecturales (capas adaptadoras, redes de enrutamiento). Un sistema monotrópico intercambia capacidad general por rendimiento en el dominio. PAIciente evita explícitamente este compromiso.

---

## 3. Fundamentación: Restricción por Prompt como Frontera del Sistema

### 3.1 ¿Por Qué No Ajustar Finamente?

Ajustar finamente un modelo para simular un niño con TDAH+TND requeriría un corpus de entrenamiento de discurso infantil anotado fundamentado en perfiles clínicos - un corpus que no existe y que plantearía preocupaciones éticas sustanciales en su construcción (datos de sesiones clínicas con menores, restricciones de consentimiento y privacidad, riesgo de codificar firmas conductuales identificables de niños individuales). Incluso si tal corpus existiera, el ajuste fino introduciría dos problemas estructurales:

**Erosión de capacidad.** La persona de clínico de PAIciente requiere la capacidad analítica, de citación y de razonamiento estructurado plena del modelo. El ajuste fino en discurso infantil degradaría estas capacidades - un fenómeno bien documentado en el ajuste fino específico de dominio donde el rendimiento fuera del dominio declina [hallazgo general en la literatura de aprendizaje por transferencia; sin necesidad de citación específica de PAIciente].

**Opacidad.** El perfil conductual de un modelo ajustado finamente está codificado en distribuciones de pesos que no son inspeccionables por humanos. El enfoque restringido por prompt hace que la especificación conductual completa sea legible, versionable y auditable. Cada restricción sobre la persona infantil - la regla del 30% de edad emocional de Barkley, las dimensiones del TND derivadas de Stringaris, las condiciones de cumplimiento fundamentadas en el CPS - es visible en el texto del prompt. Esta transparencia no es incidental; es un requisito de diseño para una herramienta destinada a servir a poblaciones clínicas y educativas.

### 3.2 El Prompt como Especificación Versionada

Tratar el prompt como la frontera del sistema produce propiedades de ingeniería concretas:

- **Reproducibilidad.** Dado el mismo prompt y versión del modelo, el envolvente conductual del sistema es determinístico (módulo varianza de muestreo). Las sesiones pueden compararse entre usuarios.
- **Auditabilidad.** Los revisores clínicos pueden inspeccionar la lógica conductual completa sin acceso a los internos del modelo. Cada afirmación que el sistema hace sobre comportamiento del TDAH o TND puede rastrearse hasta una cláusula específica del prompt y su fuente citada.
- **Portabilidad.** El prompt puede desplegarse en diferentes sustratos LLM (Claude, GPT, Gemini, Mistral) con adaptación específica al sustrato pero intención conductual idéntica. La evaluación entre plataformas [ya realizada para PAIciente v2.0] reveló que la fidelidad conductual varía según el sustrato, pero la especificación en sí es portátil.
- **Iteración basada en diff.** Los cambios conductuales son parches de prompt - delimitados, revisables y reversibles. Esto refleja la práctica de ingeniería de software y permite el tipo de desarrollo incremental con confirmación que PAIciente sigue.

---

## 4. Fundamentación: Politropía

### 4.1 Las Orientaciones Funcionales

PAIciente implementa las siguientes orientaciones de procesamiento distintas dentro de un único prompt y sesión:

| Orientación | Disparador | Contrato de Salida | Postura Epistémica |
|---|---|---|---|
| **Persona infantil** | `@child` | Diálogo en personaje; lenguaje apropiado a la edad; salida conductualmente restringida | Perspectiva delimitada simulada de un niño de 9 años |
| **Capa de estado interno** | `@child:inner` | Bloque de anotación estructurado anexado a la salida infantil | Metacognitiva - expone el razonamiento de la simulación |
| **Motor de estado** | `@set` | Inyección de parámetros con validación, detección de conflictos, manejo de errores | Programática - opera sobre variables de estado |
| **Persona de clínico** | `@clinician` | Análisis estructurado (observaciones / inferencias / recomendaciones); citaciones | Analítica plena; fundamentada en evidencia |
| **Herramientas de práctica** | `@replay`, `@debrief`, `@script`, `@escalation-map` | Salida estructurada específica del modo | Varía según la herramienta (reflexiva, generativa, analítica) |

Estas no son variaciones estilísticas. Difieren en estructura de salida, profundidad de razonamiento, restricciones de vocabulario y compromisos epistémicos. La persona infantil suprime la capacidad analítica; la persona de clínico la ejerce al máximo. La capa de estado interno ocupa una tercera posición - razona *sobre* la simulación infantil desde fuera de la perspectiva del niño mientras la persona infantil está activa. Esta estructura triádica (simulación / metacognición / análisis) es el diseño politrópico central.

### 4.2 ¿Por Qué No Multi-Agente?

Una arquitectura alternativa distribuiría estas orientaciones entre instancias de modelo separadas o llamadas API - una instancia para el niño, una para el clínico, una para la gestión de estado. Esto evitaría el requisito de politropía pero introduciría:

- **Fragmentación de contexto.** El análisis del clínico sobre una interacción infantil requiere acceso al historial completo de la interacción, incluyendo anotaciones de estado interno y parámetros configurados. La distribución entre instancias requiere paso explícito de contexto, que es con pérdidas y añade latencia.
- **Sobrecarga de sincronización de estado.** El sistema `@set` modifica estado que debe reflejarse tanto en el comportamiento del niño como en las anotaciones de estado interno. Una arquitectura multi-agente requiere un bus de estado compartido, añadiendo complejidad de ingeniería sin ganancia correspondiente en la calidad de la simulación.
- **Pérdida de coherencia de sesión.** La experiencia del usuario depende de la conmutación fluida entre personas dentro de un único flujo conversacional. Las arquitecturas multi-agente introducen latencia a nivel de turno y riesgo de desalineación de la ventana de contexto.

La politropía dentro de una única ventana de contexto evita los tres costes. El compromiso es complejidad de prompt - la especificación conductual entera debe coexistir en un único conjunto de instrucciones - pero esto es manejable y, como se argumentó en el punto 3.2, produce beneficios de transparencia.

### 4.3 Politropía vs. Multi-Personalidad

El término *politrópico* se elige deliberadamente sobre alternativas como "multi-persona" o "multi-personalidad" para evitar dos implicaciones engañosas:

1. **Connotación clínica.** "Multi-personalidad" conlleva una asociación inevitable con el trastorno disociativo de identidad. Las orientaciones de PAIciente no son personalidades; son modos de procesamiento ingenieriles con comandos de activación explícitos.
2. **Encuadre superficial.** "Multi-persona" sugiere que la diferencia es primariamente estilística (tono, vocabulario, registro). Las orientaciones de PAIciente difieren a nivel estructural: esquemas de salida diferentes, compromisos epistémicos diferentes, conjuntos de restricciones diferentes. *Politrópico* destaca la multiplicidad funcional.

---

## 5. Fundamentación: Análogos Conductuales de Competencia Delimitada

### 5.1 La Distinción Análogo/Homólogo

Este es el compromiso conceptual más importante del encuadre y el más vulnerable a mala interpretación. PAIciente no pretende *tener* TDAH o TND. No pretende replicar los mecanismos neurocognitivos subyacentes a estas condiciones. Pretende producir salida conductual que es *estructuralmente análoga* a la superficie conductual observable de un niño con estos perfiles, según la caracteriza la literatura clínica.

La distinción importa por tres razones:

**Alcance honesto.** Los padres y clínicos que usan PAIciente deben comprender que están practicando con un modelo de superficie conductual, no interactuando con un sistema que "comprende" cómo es tener TDAH. El encuadre por analogía previene la sobreafirmación.

**Criterios de fidelidad de la simulación.** Si PAIciente reivindicara homología mecanicista, la fidelidad necesitaría evaluarse contra medidas neurocognitivas (pruebas de capacidad de memoria de trabajo, ensayos de control inhibitorio, correlatos de neuroimagen). El encuadre por analogía establece el criterio de fidelidad a nivel conductual: ¿coincide la salida con lo que la literatura clínica describe como comportamiento observable? Esto es evaluable por clínicos que revisan transcripciones, no por instrumentación neurocognitiva.

**Posicionamiento ético.** Afirmar que un LLM "tiene" una condición del neurodesarrollo sería engañoso y potencialmente dañino - podría trivializar la experiencia vivida de individuos con estas condiciones. El encuadre por analogía desvincula explícitamente la identidad mecanicista mientras preserva la utilidad práctica de la simulación.

### 5.2 Qué Está Delimitado

Las fronteras de competencia específicas implementadas en la persona infantil de PAIciente se derivan de la literatura clínica:

**Restricciones de función ejecutiva.** La teoría unificada del TDAH de Barkley [1] posiciona la inhibición conductual como el déficit central, con deterioros descendentes en la memoria de trabajo, autorregulación del afecto y la activación, habla internalizada y reconstitución (la capacidad de descomponer y recombinar secuencias conductuales). La persona infantil de PAIciente implementa análogos de estos deterioros: pierde el hilo de instrucciones de múltiples pasos (memoria de trabajo), responde impulsivamente antes de que terminen las preguntas (inhibición), escala bajo frustración (regulación del afecto) y tiene dificultades con la secuenciación de tareas y la estimación temporal (reconstitución, procesamiento temporal). El tratamiento más amplio de las funciones ejecutivas de Barkley [3] y el manual clínico [4] proporcionan el marco para calibrar la gravedad e interacción de estas restricciones.

**Retraso en la regulación emocional.** La heurística de Barkley de que los niños con TDAH funcionan a aproximadamente el 70% de su edad cronológica en la autorregulación emocional (la "regla del 30%") se implementa directamente: las respuestas emocionales de la persona infantil están calibradas para aproximadamente 6,5-7 años para un personaje de 9 años. Esto se manifiesta como menor tolerancia a la frustración, mayor sensibilidad al rechazo y mayor dificultad con las transiciones de lo que se esperaría para la edad cronológica.

**Estructura de respuesta oposicionista.** En lugar de implementar el TND como desafío uniforme, PAIciente se basa en el modelo tridimensional de Stringaris y Goodman [6] - dimensiones irritable, obstinada y dañina - y en el análisis bifactorial de Burke et al. [7] que confirma la irritabilidad como dimensión clínica distinta. El comportamiento oposicionista de la persona infantil no es resistencia aleatoria; es contextualmente disparado por percepción de injusticia, autoridad arbitraria, pérdida de autonomía o interacción orientada al control - consistente con la interpretación de habilidades rezagadas de Greene [12, 13] y el énfasis de la literatura sobre TND en el contexto funcional [8, 9, 10].

**Condiciones de cumplimiento.** El cumplimiento de la persona infantil no es binario (obedecer/rechazar) sino condicional a factores interaccionales identificables: provisión de autonomía, razonamiento transparente, percepción de justicia, arquitectura de elección y estado de regulación del cuidador. Esto modela el hallazgo bien establecido de que el comportamiento oposicionista en el TND no es rigidez a nivel de rasgo sino una respuesta al estrés modulada por variables relacionales y contextuales [8, 11, 12]. La implicación práctica es que los usuarios que practican con PAIciente pueden observar resultados diferenciales de diferentes enfoques interaccionales - la simulación responde a la estrategia, no solo a los comandos.

**Interacción de comorbilidad.** La comorbilidad TDAH+TND no se implementa como dos listas de síntomas independientes sumadas. Los efectos de interacción están modelados: los déficits de función ejecutiva reducen el umbral para la activación oposicionista (el niño tiene menos recursos regulatorios para gestionar la frustración); el rechazo impulsado por el TND compone la evitación de tareas impulsada por el TDAH; el estado de medicación (`@set medication`) modula ambos perfiles simultáneamente. Esto refleja las altas tasas de comorbilidad documentadas en la literatura metaanalítica [18] y la evidencia de neuroimagen para correlatos neurales compartidos y distintos [19].

### 5.3 Cómo Se Logra la Delimitación

El mecanismo de delimitación es enteramente basado en prompt. Cláusulas específicas del prompt restringen:

- **Vocabulario y sintaxis**: salida apropiada a la edad, con excepciones para dominios de hiperfoco (donde el vocabulario puede superar al de los pares, según el perfil clínico).
- **Profundidad de razonamiento**: la persona infantil no produce razonamiento analítico, explicación causal de su propio comportamiento ni argumentación estructurada - estos están reservados para la persona de clínico.
- **Rango afectivo**: las respuestas emocionales están calibradas por la regla del 30%; la sensibilidad al rechazo está explícitamente parametrizada.
- **Lógica de cumplimiento**: reglas condicionales especifican cuándo el niño cumple, resiste, escala o se retira, basándose en el enfoque interaccional y los parámetros de estado actuales.
- **Prevención de fuga de información**: la persona infantil está explícitamente restringida de divulgar contexto inyectado (`@set context`), explicar su propia historia de fondo o salir del personaje para proporcionar información clínica. Si la presión conversacional forzara tal divulgación, el prompt especifica comportamientos de desvío (silencio, cambio de tema, respuesta monosilábica).

Ninguna de estas restricciones modifica los pesos del modelo. Operan como reglas conductuales interpretadas en tiempo de inferencia. El modelo retiene capacidad plena; el prompt la canaliza.

---

## 6. Fundamentación: Verificación Estructurada

### 6.1 El Problema de la Verificación

Simulación conductual sin verificación es simulación sin rendición de cuentas. Si un usuario interactúa con la persona infantil y observa escalada, necesita saber: ¿fue la escalada impulsada por la lógica interna de la simulación (los parámetros de estado, el antecedente interaccional, el modelo de trayectoria), o fue un artefacto de generación estocástica? Sin mecanismos de verificación, la simulación es una caja negra que casualmente produce salida de apariencia plausible.

PAIciente aborda esto a través de cuatro subsistemas de verificación:

### 6.2 Anotaciones de Estado Interno (`@child:inner`)

Cuando está activa, la capa de estado interno anexa un bloque estructurado a cada respuesta del niño:

```
[INNER STATE]
Feeling: <etiqueta de emoción>
Arousal: low / medium / high / overloaded
What would help right now: <1 cosa concreta>
What just made it worse: <1 cosa concreta, o "nothing">
Escalation path:
  Trajectory: stable / building / near-threshold / at-threshold
  Next likely behavior: <1 línea conductualmente específica>
  Interrupt lever: <1 acción concreta del cuidador>
```

Esto cumple tres funciones de verificación:

- **Transparencia del razonamiento de la simulación.** El usuario puede inspeccionar *por qué* el niño respondió como lo hizo - no solo qué dijo, sino qué estado emocional, nivel de activación y trayectoria de escalada la simulación asignó a la interacción.
- **Rendición de cuentas predictiva.** Los campos "next likely behavior" e "interrupt lever" comprometen a la simulación con predicciones que el usuario puede probar en los turnos siguientes. Si la simulación predice "el niño dará un portazo" y la palanca de interrupción es "ofrecer una pausa de 2 minutos," el usuario puede probar la palanca y evaluar si la simulación sigue su propia lógica.
- **Rastreo de procedencia del estado.** Cuando los parámetros `@set` están activos, el bloque de estado interno marca cada campo con `<- [SET]` (inyectado por el usuario) o `<- [organic]` (derivado de la interacción). Esto distingue entre estado controlado por el usuario y derivado por la simulación, previniendo la confusión.

### 6.3 Motor de Estado Programable (`@set`)

El sistema `@set` permite a los usuarios inyectar condiciones iniciales específicas - nivel de activación, trayectoria, confianza, fatiga, estado de medicación, objetivo de hiperfoco e historia contextual - y observar cómo la simulación se comporta desde ese punto de partida. Esto posibilita:

- **Comparación controlada.** El mismo enfoque interaccional puede probarse contra diferentes estados iniciales (p. ej., alta-activación/baja-confianza vs. baja-activación/alta-confianza), aislando el efecto de las variables de estado en los resultados conductuales.
- **Reproducibilidad de escenarios.** Los formadores clínicos pueden especificar configuraciones de estado exactas para ejercicios de formación, garantizando que múltiples formandos encuentren la misma condición inicial simulada.
- **Pruebas de casos límite.** Configuraciones de estado extremas (p. ej., `arousal=overloaded trajectory=at-threshold trust=low medication=wearing-off`) someten a prueba de estrés la lógica conductual de la simulación en condiciones límite.

El sistema incluye validación formal: los valores fuera de rango producen errores tipificados; las combinaciones de parámetros internamente inconsistentes producen advertencias explícitas; la simulación procede con los valores declarados pero señaliza la inconsistencia. Esto previene el comportamiento silencioso de basura-entra/basura-sale.

### 6.4 Análisis Post-Hoc (`@debrief`)

El comando `@debrief` conmuta automáticamente a la persona de clínico y produce un análisis estructurado de la interacción infantil precedente. Esto es verificación por revisión experta: la persona de clínico, operando a capacidad analítica plena, evalúa la interacción usando el mismo formato estructurado (observaciones -> inferencias -> recomendaciones) que un clínico humano podría usar en supervisión. El estado del niño se suspende, no se borra, permitiendo al usuario reanudar la interacción infantil después del debriefing.

### 6.5 Bucle de Práctica (`@replay`)

El comando `@replay` re-emite el último turno del niño con el mismo estado, y luego solicita al usuario que pruebe un enfoque alternativo. Esto crea un bucle experimental controlado: mismas condiciones iniciales, intervención diferente, resultado diferencial observable. El modelo no genera automáticamente la alternativa - el usuario debe proporcionarla - preservando la función de práctica (el usuario es el aprendiz, no el observador).

---

## 7. Fundamentación: Rechazo del Monotropismo Arquitectural

### 7.1 El Compromiso del Monotropismo

El monotropismo arquitectural - especializar un modelo mediante ajuste fino, moldeado de recompensa o modificación estructural - compra rendimiento en el dominio al coste de capacidad general. Para sistemas de propósito único, este compromiso es frecuentemente aceptable. Para PAIciente, es estructuralmente incompatible con los requisitos de diseño.

La incompatibilidad central es el **requisito de politropía** (punto 4). PAIciente debe soportar simultáneamente:

- Una persona infantil que *suprime* razonamiento analítico, mantiene vocabulario apropiado a la edad y sigue lógica de cumplimiento condicional.
- Una persona de clínico que *maximiza* razonamiento analítico, cita evidencia revisada por pares y produce evaluación clínica estructurada.
- Un motor de estado que ejecuta validación de parámetros, detección de conflictos y manejo formal de errores.
- Una capa de estado interno que produce anotaciones metacognitivas sobre la lógica interna de la simulación infantil.

Estas orientaciones hacen demandas opuestas sobre la capacidad del modelo. Un modelo ajustado finamente para producir salida infantil degradaría en tareas del modo clínico. Un modelo ajustado finamente para análisis clínico resistiría producir la salida restringida, fragmentada y emocionalmente reactiva requerida por la persona infantil. El control a nivel de prompt evita esto dejando intacto el espacio de capacidad completo del sustrato y seleccionando de él por orientación.

### 7.2 Portabilidad Entre Plataformas

PAIciente ha sido evaluado en cinco sustratos LLM: Claude Projects, ChatGPT CustomGPT, Mistral Agents, Gemini Gems y Grok. Esta evaluación es posible *porque* el sistema no es arquitecturalmente monotrópico - es una especificación portátil que puede instanciarse en cualquier LLM suficientemente capaz. Los sistemas monotrópicos ajustados finamente están, por definición, bloqueados a su sustrato de entrenamiento.

El diseño no-monotrópico hace esta evaluación entre plataformas estructuralmente posible - la misma especificación conductual puede instanciarse en cada sustrato y compararse la fidelidad de simulación resultante. Esta comparación no podría realizarse si PAIciente estuviera arquitecturalmente vinculado a un único sustrato mediante ajuste fino o modificación de pesos.

### 7.3 El Argumento del Sustrato de Uso General

El argumento a favor de un sustrato de uso general no es meramente pragmático (portabilidad, evitación de costes). Es estructural. La *calidad* de la simulación infantil depende del conocimiento latente del sustrato sobre psicología del desarrollo, dinámicas conductuales y marcos clínicos. Un LLM de uso general entrenado en corpus amplios ha codificado - en sus distribuciones de pesos - patrones estadísticos de la literatura clínica, psicología educativa, investigación en desarrollo infantil y discurso naturalista. El prompt no necesita enseñar al modelo qué aspecto tiene el TDAH; necesita *activar y restringir* conocimiento existente.

El ajuste fino en un corpus estrecho sobrescribiría parte de este conocimiento latente con patrones específicos del dominio, potencialmente reduciendo la capacidad de la simulación para responder flexiblemente a enfoques interaccionales novedosos. El enfoque restringido por prompt preserva la base de conocimiento latente completa y la dirige mediante reglas conductuales.

---

## 8. Posicionamiento de PAIciente Entre Categorías Adyacentes

La declaración de encuadre posiciona a PAIciente fuera de varias categorías adyacentes. Las distinciones merecen hacerse explícitas.

### 8.1 No Es una Persona de Chatbot

Las personas de chatbot estándar (bots de atención al cliente con tonos "amigables", asistentes de escritura creativa con "voces de personaje") operan a nivel estilístico - ajustan registro, vocabulario y afecto sin implementar lógica conductual estructurada, gestión de estado ni mecanismos de verificación. La persona infantil de PAIciente no es una configuración de tono; es una especificación conductual con reglas de cumplimiento condicional, trayectorias de escalada, estado parametrizado y anotaciones predictivas. La distinción es entre *estilo* (cómo se dice algo) y *lógica conductual* (qué se dice bajo qué condiciones y por qué).

### 8.2 No Es una Herramienta Clínica Ajustada Finamente

Las herramientas clínicas de PLN ajustadas finamente para tareas específicas (cribado diagnóstico, recomendación de tratamiento, extracción de síntomas) son arquitecturalmente monotrópicas por diseño - intercambian generalidad por precisión en el dominio. PAIciente no es una herramienta clínica en este sentido. No diagnostica, criba ni recomienda tratamiento. Proporciona un *entorno de práctica* - una simulación que responde a la estrategia interaccional de formas clínicamente fundamentadas, emparejada con una persona analítica que explica las dinámicas. El sistema se desvincula explícitamente de función clínica en sus restricciones de prompt.

### 8.3 No Es un Andamiaje de Juego de Roles No Estructurado

Los prompts de juego de roles no estructurados ("finge ser un niño con TDAH") producen salida variable e inverificable sin gestión de estado, sin lógica de escalada, sin mecanismo de verificación y sin fundamentación en evidencia. La salida puede ser plausible en turnos individuales pero carece de coherencia conductual entre turnos, no tiene mecanismo para comparación controlada y no puede inspeccionarse en cuanto al razonamiento de la simulación. La contribución de PAIciente es precisamente la capa estructurada que transforma juego de roles en simulación responsabilizable.

---

## 9. Implicaciones

### 9.1 Para la Evaluación de Fidelidad de la Simulación

El encuadre determina qué cuenta como fidelidad. Porque PAIciente implementa análogos conductuales (no homólogos mecanicistas), la evaluación de fidelidad debe apuntar a la superficie conductual: ¿produce la respuesta del niño simulado a una estrategia interaccional validada (p. ej., CPS Plan B [12, 13], elogio etiquetado estilo PCIT [14]) resultados consistentes con la descripción de la literatura clínica de cómo los niños con TDAH+TND responden a esas estrategias? Esta es una proposición comprobable que no requiere instrumentación neurocognitiva.

### 9.2 Para las Expectativas de los Usuarios

El encuadre establece expectativas honestas. Los usuarios deben comprender que están practicando con un modelo conductual, no con un niño digital. Las respuestas de la simulación están gobernadas por reglas de prompt e inferencia del modelo, no por una experiencia interna de diferencia del neurodesarrollo. Esta distinción debe hacerse explícita en toda la documentación orientada al usuario.

### 9.3 Para Extensión y Contribución

La arquitectura restringida por prompt y no-monotrópica significa que extender PAIciente (añadir nuevos perfiles conductuales, nuevas herramientas clínicas, nuevos mecanismos de evaluación) requiere solo modificación del prompt - sin reentrenamiento, sin acceso a pesos, sin cambios de infraestructura. Esto reduce la barrera de contribución y permite iteración impulsada por la comunidad, consistente con el compromiso de código abierto del proyecto.

---

## 10. Limitaciones

**Techo de la simulación.** Los análogos conductuales tienen un techo de fidelidad. El modelo no puede simular diferencias de procesamiento sensorial, activación fisiológica o estados somáticos que influyen en el comportamiento de niños reales. Los comportamientos que dependen fuertemente de estos (p. ej., cambios de apetito relacionados con la medicación, sobrecarga sensorial en entornos ruidosos) pueden aproximarse a nivel de la salida conductual pero no fundamentarse mecanicistamente.

**Varianza estocástica.** Los sistemas restringidos por prompt heredan la varianza de muestreo del modelo subyacente. Dos ejecuciones desde estados e inputs idénticos pueden producir salidas diferentes. El sistema `@set` reduce pero no elimina esto - restringe condiciones iniciales, no la trayectoria generativa completa.

**Dependencia del sustrato.** A pesar de la portabilidad, la fidelidad conductual varía entre sustratos LLM. Algunos modelos resisten mantener la capacidad analítica suprimida en el modo infantil; otros activan filtros de seguridad de contenido en diálogo oposicionista. La especificación del prompt es portátil; la calidad de su ejecución no está garantizada.

**Sin validación empírica.** Los análogos conductuales de PAIciente están fundamentados en la literatura clínica, pero la simulación en sí no ha sido empíricamente validada contra interacciones clínicas reales. Si los usuarios que practican con PAIciente transfieren habilidades a interacciones del mundo real con niños con TDAH+TND es una cuestión empírica abierta.

---

## 11. Conclusión

El encuadre de PAIciente como un *sistema politrópico restringido por prompt que implementa análogos conductuales de competencia delimitada y verificación estructurada sin monotropismo arquitectural* no es terminología decorativa. Cada término identifica un compromiso de diseño específico con implicaciones concretas de ingeniería y clínicas:

- *Restringido por prompt* asegura transparencia, auditabilidad y portabilidad.
- *Politrópico* permite orientaciones co-residentes de simulación y análisis dentro de una única sesión.
- *Análogos conductuales* definen alcance honesto y criterios de fidelidad apropiados.
- *Competencia delimitada* fundamenta las restricciones de la simulación en evidencia clínica citada.
- *Sin monotropismo arquitectural* preserva el sustrato de uso general requerido para la politropía y el despliegue entre plataformas.

Juntos, estos compromisos definen un espacio de diseño que es distinto de las personas de chatbot, herramientas clínicas ajustadas finamente y andamiajes de juego de roles no estructurados. El encuadre hace explícito qué es PAIciente, qué no es y en qué términos debe evaluarse su fidelidad de simulación.

---

## References

[1] Barkley, R. A. (1997). Behavioral inhibition, sustained attention, and executive functions: Constructing a unifying theory of ADHD. *Psychological Bulletin, 121*(1), 65–94. https://doi.org/10.1037/0033-2909.121.1.65

[2] Barkley, R. A. (1997). *ADHD and the nature of self-control*. Guilford Press.

[3] Barkley, R. A. (2012). *Executive functions: What they are, how they work, and why they evolved*. Guilford Press.

[4] Barkley, R. A. (Ed.). (2015). *Attention-deficit hyperactivity disorder: A handbook for diagnosis and treatment* (4th ed.). Guilford Press.

[5] Faraone, S. V., Bellgrove, M. A., Brikell, I., et al. (2024). Attention-deficit/hyperactivity disorder. *Nature Reviews Disease Primers, 10*(1), 11. https://doi.org/10.1038/s41572-024-00495-0

[6] Stringaris, A., & Goodman, R. (2009). Three dimensions of oppositionality in youth. *Journal of Child Psychology and Psychiatry, 50*(3), 216–223. https://doi.org/10.1111/j.1469-7610.2008.01989.x

[7] Burke, J. D., Boylan, K., Rowe, R., et al. (2014). Identifying the irritability dimension of ODD. *Journal of Abnormal Psychology, 123*(4), 841–851. https://doi.org/10.1037/a0037898

[8] Hawes, D. J., Gardner, F., Dadds, M. R., et al. (2023). Oppositional defiant disorder. *Nature Reviews Disease Primers, 9*(1), 31. https://doi.org/10.1038/s41572-023-00441-6

[9] Mars, J. A., Aggarwal, A., & Marwaha, R. (2024). Oppositional defiant disorder. In *StatPearls*. StatPearls Publishing.

[10] Ghosh, A., Ray, A., & Basu, A. (2017). Oppositional defiant disorder: Current insight. *Psychology Research and Behavior Management, 10*, 353–367. https://doi.org/10.2147/PRBM.S120582

[11] Kaur, M., Floyd, A., & Balta, A.-M. (2022). Oppositional defiant disorder: Evidence-based review of behavioral treatment programs. *Annals of Clinical Psychiatry, 34*(1), 44–58. https://doi.org/10.12788/acp.0056

[12] Greene, R. W. (2021). *The explosive child* (6th ed.). Harper.

[13] Greene, R. W., & Ablon, J. S. (2006). *Treating explosive kids: The collaborative problem-solving approach*. Guilford Press.

[14] Thomas, R., & Zimmer-Gembeck, M. J. (2007). Behavioral outcomes of Parent-Child Interaction Therapy and Triple P-Positive Parenting Program. *Journal of Abnormal Child Psychology, 35*(3), 475–495. https://doi.org/10.1007/s10802-007-9104-9

[15] Murrihy, R. C., Drysdale, S. A. O., Dedousis-Wallace, A., et al. (2023). Community-delivered Collaborative and Proactive Solutions and Parent Management Training for oppositional youth. *Behaviour Therapy, 54*(2), 400–417. https://doi.org/10.1016/j.beth.2022.10.005

[16] Dedousis-Wallace, A., Drysdale, S. A. O., McAloon, J., et al. (2025). Predictors and moderators of two treatments of oppositional defiant disorder in children. *Journal of Clinical Child & Adolescent Psychology, 54*(1), 67–82. https://doi.org/10.1080/15374416.2022.2127102

[17] Lin, X., He, T., Heath, M., Chi, P., & Hinshaw, S. (2022). A systematic review of multiple family factors associated with oppositional defiant disorder. *International Journal of Environmental Research and Public Health, 19*(17), 10866. https://doi.org/10.3390/ijerph191710866

[18] Njardvik, U., Wergeland, G. J., Riise, E. N., Hannesdottir, D. K., & Öst, L.-G. (2025). Psychiatric comorbidity in children and adolescents with ADHD. *Clinical Psychology Review, 118*, 102571. https://doi.org/10.1016/j.cpr.2025.102571

[19] Noordermeer, S. D. S., Luman, M., Oosterlaan, J., & Hartman, C. A. (2016). A systematic review and meta-analysis of neuroimaging in ODD and CD taking ADHD into account. *Neuropsychology Review, 26*(1), 44–72. https://doi.org/10.1007/s11065-015-9315-8

[20] American Psychiatric Association. (2022). *Diagnostic and statistical manual of mental disorders* (5th ed., text rev.; DSM-5-TR). American Psychiatric Association Publishing.

<!-- i18n: source=implementations/mistral.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# PAIciente en Mistral
---
### Enlace sandbox:
* Restriccion de la plataforma: el usuario debe tener sesion iniciada con 1 cuenta de Mistral (Le Chat Free parece funcionar):
  https://chat.mistral.ai/chat/553205e3-526a-472d-99d0-0916596fa54b

---
## Como instanciar

### Paso 1 - Crear un Agente en Le Chat

1. Acceda a [chat.mistral.ai](https://chat.mistral.ai) e inicie sesion (una cuenta gratuita es suficiente).
2. En la barra lateral izquierda, haga clic en **Agents**.
3. Haga clic en **Create Agent**.

### Paso 2 - Pegar el system prompt

1. Establezca el **Name** como "PAIciente" y anada una breve descripcion.
2. Abra el archivo `/prompt/system-prompt.md` en este repositorio y copie todo su contenido.
3. Pegue el system prompt completo en el campo **Behavior**. No lo modifique — PAIciente gestiona el idioma y el contexto nativamente.

### Paso 3 - OPCIONAL - Establecer visibilidad como Publica

1. En la configuracion del agente, establezca **Visibility** como **Public**.
2. Guarde el agente.
3. Copie el enlace publico para compartir con los usuarios.


## Notas

- **Compatibilidad con el nivel gratuito.** La creacion y uso de agentes en Le Chat esta disponible en el nivel gratuito. No se requiere ninguna suscripcion de pago para crear o usar PAIciente en Mistral.

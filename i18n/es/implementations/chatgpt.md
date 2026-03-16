<!-- i18n: source=implementations/chatgpt.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# PAIciente en ChatGPT

---
### Enlace sandbox:
* Funciona sin inicio de sesión en la plataforma - se aplicarán restricciones del nivel gratuito, pero funciona razonablemente bien
  https://chatgpt.com/g/g-69b1a7644f5c81919f3fca1bbc2926fa-paiciente-v2-0

---
## Cómo instanciar

### Paso 1 - Crear un Custom GPT

1. Acceda a [chatgpt.com](https://chatgpt.com) e inicie sesión con una cuenta **Plus o Pro**. (La creación de Custom GPT requiere una suscripción de pago.)
2. Haga clic en el icono de su perfil en la esquina inferior izquierda y seleccione **My GPTs**.
3. Haga clic en **Create a GPT**.

### Paso 2 - Pegar el system prompt

1. En el editor del GPT, cambie a la pestaña **Configure**.
2. Establezca el **Name** como "PAIciente" y añada una breve descripción.
3. Abra el archivo `/prompt/system-prompt.md` en este repositorio y copie todo su contenido.
4. Pegue el system prompt completo en el campo **Instructions**. No lo modifique — PAIciente gestiona el idioma y el contexto nativamente.
5. En Capabilities, desactive Code Interpreter, DALL-E y Web Browsing salvo que tenga un motivo específico para activarlos.

### Paso 3 - OPCIONAL - Publicar en la GPT Store

1. Haga clic en **Save** y seleccione **Publish to > Everyone**.
2. El GPT será revisado y listado en la GPT Store.
3. Comparta el enlace público con los usuarios.

## Notas

- **La creación de GPTs requiere Plus o Pro.** Los usuarios del nivel gratuito no pueden crear Custom GPTs - pero pueden usar la sandbox:
	- **Los usuarios del nivel gratuito pueden acceder a la GPT Store.** Cualquier persona con una cuenta ChatGPT gratuita puede usar un GPT publicado a través de su enlace en la store — no necesita una suscripción de pago para *usarlo*.
	- **Límites de tasa en sesiones multi-turno en el nivel gratuito.** Los usuarios del nivel gratuito están sujetos a límites de tasa más estrictos (mensajes por hora/día). Las sesiones prolongadas pueden interrumpirse por limitación de tasa. El usuario deberá esperar y reanudar.

<!-- i18n: source=implementations/gemini.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# PAIciente en Gemini
---
### Enlace sandbox:
* Restriccion de la plataforma: el usuario debe tener sesion iniciada con 1 cuenta de Google:
  https://gemini.google.com/gem/1N5cyhZd34Pb-KEzMxdsaZxjSt7jKF4jm?usp=sharing

---
## Como instanciar

### Paso 1 — Crear un Gem

1. Acceda a [gemini.google.com](https://gemini.google.com) en un **navegador de escritorio**. (La creacion de Gems no esta disponible en la aplicacion movil a la fecha de esta publicacion.)
2. Inicie sesion con su cuenta de Google (el nivel gratuito es suficiente).
3. En la barra lateral izquierda, haga clic en **Gem manager** y luego en **Create Gem**.

### Paso 2 — Pegar el system prompt

1. Establezca el **Name** como "PAIciente".
2. Abra el archivo `/prompt/system-prompt.md` en este repositorio y copie todo su contenido.
3. Pegue el system prompt completo en el campo **Instructions**. No lo modifique — PAIciente gestiona el idioma y el contexto nativamente.
4. Haga clic en **Save**.

### Paso 3 - OPCIONAL - Compartir via enlace

1. Abra su Gem guardado y haga clic en el boton **Share**.
2. Defina los permisos para compartir (estilo Google Drive: "Anyone with the link" o restringido).
3. Copie el enlace para compartir.


## Notas

- **Compatibilidad con el nivel gratuito.** La creacion y uso de Gems esta disponible en el nivel gratuito de Gemini. No se requiere ninguna suscripcion de pago.
- **Solo escritorio para la creacion.** Los Gems deben crearse en gemini.google.com en un navegador de escritorio. Una vez creados, pueden usarse en dispositivos moviles.
- **Limite de ventana de contexto en el nivel gratuito.** El nivel gratuito tiene una ventana de contexto de 32.000 tokens. Las sesiones multi-turno prolongadas (conversaciones terapeuticas largas) pueden alcanzar este limite, momento en el que las partes iniciales de la conversacion se eliminaran del contexto. Los usuarios en sesiones mas largas deben ser conscientes de que la continuidad puede degradarse.
- **Disponibilidad en la UE/PT.** Los usuarios en la UE y Portugal acceden a Gemini a traves de la aplicacion para consumidores (gemini.google.com), no a traves de la API. Todas las instrucciones anteriores se aplican a la ruta de la aplicacion para consumidores.

<!-- i18n: source=implementations/claude.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# PAIciente en Claude

## Cómo instanciar

### Paso 1 — Crear un nuevo Proyecto

1. Acceda a [claude.ai](https://claude.ai) e inicie sesión (cuenta gratuita o Pro).
2. En la barra lateral izquierda, haga clic en **Projects**.
3. Haga clic en **Create Project** y asigne un nombre (ej.: "PAIciente").

### Paso 2 — Pegar el system prompt

1. Abra el archivo `/prompt/system-prompt.md` en este repositorio y copie todo su contenido.
2. En el Proyecto que acaba de crear, haga clic en el campo **Project Instructions** (a veces etiquetado como "Set custom instructions").
3. Pegue el system prompt completo tal como está. No lo modifique — PAIciente gestiona el idioma y el contexto nativamente.

### Paso 3 — Iniciar una sesión

1. Abra una nueva conversación dentro del Proyecto.
2. El system prompt está ahora activo. PAIciente responderá de acuerdo con sus instrucciones desde el primer mensaje.

## Notas

- **No es compartible públicamente.** Los Proyectos Claude son privados de la cuenta que los crea. No existe enlace público ni mecanismo de tienda. Cada usuario debe autoinstanciar siguiendo los pasos anteriores.
- **Compatibilidad con el nivel gratuito.** PAIciente funciona en el nivel gratuito de Claude. Los usuarios del nivel gratuito tienen acceso a Proyectos y pueden pegar instrucciones personalizadas. El uso está sujeto a los límites de mensajes estándar del nivel gratuito.

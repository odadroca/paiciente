<!-- i18n: source=CONTRIBUTING.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# Contribuir a PAIciente

## Enviar una transcripción de ejemplo

1. Elija una carpeta de escenario en `examples/` o cree una nueva para un escenario nuevo.
2. Siga el esquema de [`examples/format.md`](/examples/format.md) exactamente.
3. Nombre su archivo según la plataforma utilizada (ej.: `claude.md`, `chatgpt.md`, `gemini.md`).
4. La transcripción debe ejercitar, como mínimo: `@clinician`, `@child` y uno de `@debrief` o `@replay`.
5. Envíe mediante pull request.

## Enviar una traducción

1. Las traducciones están organizadas en `i18n/` por localidad (ej.: `i18n/pt-PT/`, `i18n/es/`).
2. Cree la carpeta de su localidad si no existe.
3. Traduzca el archivo objetivo, manteniendo el nombre y la estructura originales del archivo.
4. Mantenga todos los comandos (`@clinician`, `@child`, `@debrief`, `@set`, etc.) en inglés.
5. Incluya la cabecera de versión i18n como primera línea del archivo.
6. Indique en la cabecera la versión EN de referencia utilizada en la traducción.
7. Envíe mediante pull request con la etiqueta `i18n`.

## Reportar una imprecisión clínica

Si identifica una afirmación clínica, detalle de modelo conductual o referencia que sea imprecisa o engañosa:

1. Abra una Issue en GitHub.
2. Utilice la etiqueta `clinical-review`.
3. Describa la imprecisión, cite el archivo y la línea específicos, y proporcione una fuente correctiva si está disponible.

## Proponer una extensión de comando

Si desea proponer un nuevo comando o modificación de uno existente:

1. Abra una Issue en GitHub.
2. Utilice la etiqueta `protocol-extension`.
3. Describa el comando propuesto, su propósito, el comportamiento esperado y a qué persona aplica.

## Código de conducta

Se espera que los contribuidores participen de buena fe. La crítica clínica es bienvenida.

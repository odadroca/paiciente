# Traducciones — Español (ES)

Esta carpeta contiene traducciones al español de componentes seleccionados de PAIciente.

## Notas importantes

- El **inglés (EN)** es el idioma canónico del proyecto. Toda la documentación de referencia se encuentra en `/docs/` y `/references/`.
- Las traducciones contenidas en esta carpeta son contribuciones de la comunidad y pueden no estar al día con la versión más reciente de la documentación en inglés.
- El **system prompt no requiere traducción**. PAIciente responde automáticamente en el idioma utilizado por el usuario — la gestión lingüística es nativa al funcionamiento del modelo.

## Archivos traducidos

| Archivo original | Traducción | Versión base |
|---|---|---|
| `README.md` | [`/README.es.md`](/README.es.md) | v2.1.0 |
| `docs/overview.md` | [`docs/overview.md`](docs/overview.md) | v2.1.0 |
| `docs/personas.md` | [`docs/personas.md`](docs/personas.md) | v2.1.0 |
| `docs/workflow.md` | [`docs/workflow.md`](docs/workflow.md) | v2.1.0 |
| `docs/limitations.md` | [`docs/limitations.md`](docs/limitations.md) | v2.1.0 |
| `docs/use-cases.md` | [`docs/use-cases.md`](docs/use-cases.md) | v2.1.0 |
| `docs/inner-state-guide.md` | [`docs/inner-state-guide.md`](docs/inner-state-guide.md) | v2.1.0 |
| `CONTRIBUTING.md` | [`CONTRIBUTING.md`](CONTRIBUTING.md) | v2.1.0 |
| `docs/behavior-map.md` | [`docs/behavior-map.md`](docs/behavior-map.md) | v2.1.0 |
| `docs/evidence-map.md` | [`docs/evidence-map.md`](docs/evidence-map.md) | v2.1.0 |
| `docs/table-of-contents.md` | [`docs/table-of-contents.md`](docs/table-of-contents.md) | v2.1.0 |
| `docs/Technical-Rationale-and-Academic-Positioning.md` | [`docs/Technical-Rationale-and-Academic-Positioning.md`](docs/Technical-Rationale-and-Academic-Positioning.md) | v2.1.0 |
| `prompt/design-notes.md` | [`prompt/design-notes.md`](prompt/design-notes.md) | v2.1.0 |
| `references/references.md` | [`references/references.md`](references/references.md) | v2.1.0 |
| `implementations/claude.md` | [`implementations/claude.md`](implementations/claude.md) | v2.1.0 |
| `implementations/chatgpt.md` | [`implementations/chatgpt.md`](implementations/chatgpt.md) | v2.1.0 |
| `implementations/gemini.md` | [`implementations/gemini.md`](implementations/gemini.md) | v2.1.0 |
| `implementations/mistral.md` | [`implementations/mistral.md`](implementations/mistral.md) | v2.1.0 |

Para el estado completo de todas las traducciones, consulte [`/i18n/STATUS.md`](/i18n/STATUS.md).

## Convenciones de traducción

- ADHD = TDAH (Trastorno por Déficit de Atención e Hiperactividad).
- ODD = TND (Trastorno Negativista Desafiante).
- Todos los comandos `@` permanecen en inglés.
- Las etiquetas de los campos `[INNER STATE]` permanecen en inglés.
- En el primer uso de términos clínicos, incluir el equivalente en inglés entre paréntesis cuando la traducción sea ambigua.

## Cómo contribuir

1. Consulte las instrucciones generales en [`/CONTRIBUTING.md`](/CONTRIBUTING.md) y las convenciones i18n en [`/i18n/README.md`](/i18n/README.md).
2. Cree el archivo traducido en esta carpeta, manteniendo la estructura y los nombres de archivo originales.
3. Incluya la cabecera de versión i18n como primera línea del archivo.
4. Envíe mediante pull request con la etiqueta `i18n`.

# Übersetzungen — Deutsch (DE)

Dieser Ordner enthält deutsche Übersetzungen ausgewählter Komponenten von PAIciente.

## Wichtige Hinweise

- **Englisch (EN)** ist die kanonische Sprache des Projekts. Die gesamte Referenzdokumentation befindet sich in `/docs/` und `/references/`.
- Die in diesem Ordner enthaltenen Übersetzungen sind Community-Beiträge und entsprechen möglicherweise nicht der aktuellsten Version der englischen Dokumentation.
- Der **System-Prompt erfordert keine Übersetzung**. PAIciente antwortet automatisch in der Sprache des Benutzers — die Sprachverwaltung ist nativ in der Modellfunktion integriert.

## Übersetzte Dateien

| Originaldatei | Übersetzung | Basisversion |
|---|---|---|
| `README.md` | [`/README.de.md`](/README.de.md) | v2.1.0 |
| `docs/overview.md` | [`docs/overview.md`](docs/overview.md) | v2.1.0 |
| `docs/personas.md` | [`docs/personas.md`](docs/personas.md) | v2.1.0 |
| `docs/workflow.md` | [`docs/workflow.md`](docs/workflow.md) | v2.1.0 |
| `docs/limitations.md` | [`docs/limitations.md`](docs/limitations.md) | v2.1.0 |
| `docs/use-cases.md` | [`docs/use-cases.md`](docs/use-cases.md) | v2.1.0 |
| `docs/inner-state-guide.md` | [`docs/inner-state-guide.md`](docs/inner-state-guide.md) | v2.1.0 |
| `CONTRIBUTING.md` | [`CONTRIBUTING.md`](CONTRIBUTING.md) | v2.1.0 |

Für den vollständigen Status aller Übersetzungen siehe [`/i18n/STATUS.md`](/i18n/STATUS.md).

## Übersetzungskonventionen

- ADHD = ADHS (Aufmerksamkeitsdefizit-Hyperaktivitätsstörung).
- ODD = Störung mit oppositionellem Trotzverhalten (SOT).
- Alle `@`-Befehle bleiben auf Englisch.
- Die Feldbezeichnungen von `[INNER STATE]` bleiben auf Englisch.
- Bei der ersten Verwendung klinischer Fachbegriffe den englischen Ausdruck in Klammern angeben, wenn die Übersetzung mehrdeutig ist.

## Wie man beiträgt

1. Lesen Sie die allgemeinen Anweisungen in [`/CONTRIBUTING.md`](/CONTRIBUTING.md) und die i18n-Konventionen in [`/i18n/README.md`](/i18n/README.md).
2. Erstellen Sie die übersetzte Datei in diesem Ordner unter Beibehaltung der Originalstruktur und Dateinamen.
3. Fügen Sie den i18n-Versions-Header als erste Zeile der Datei ein.
4. Einreichen per Pull Request mit dem Label `i18n`.

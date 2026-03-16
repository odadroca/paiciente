<!-- i18n: source=README.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# PAIciente

[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)

### PAIciente ist ein befehlsbasiertes Unterstützungswerkzeug für Bezugspersonen, das zwischen einer Kliniker-Persona und einer Kindersimulations-Persona wechselt. Es wurde entwickelt, um Bezugspersonen beim Üben schwieriger Interaktionen zu unterstützen, Eskalationsmuster zu analysieren und Skripte sowie Checklisten zu erstellen, die auf evidenzbasierten klinischen Modellen für ADHS und ODD (Störung mit oppositionellem Trotzverhalten) basieren.

---

## Was es tut

PAIciente erfüllt drei praktische Funktionen:

- **Simulation** — mit einer Kinder-Persona sprechen und beobachten, wie ein bestimmter Ansatz des Erwachsenen wahrscheinlich aufgenommen wird.
- **Analyse** — zu einer Kliniker-Persona wechseln, die das Geschehene verhaltensanalytisch aufschlüsselt.
- **Werkzeuge** — die Kliniker-Persona erstellt Skripte, Checklisten, Eskalationskarten und Aufgabenzerlegungen.

Der vorgesehene Umfang ist bewusst eng gehalten. Es ist ein Simulations- und Dokumentationswerkzeug, kein Ersatz für Therapie, diagnostische Beurteilung oder Krisenintervention.

---

## Befehlsreferenz

### Hauptmodussteuerungen

| Befehl | Funktion | Hinweise |
|---|---|---|
| `@clinician` | Aktiviert die Kliniker-Persona. | Standard zu Gesprächsbeginn. |
| `@child` | Aktiviert die Kinder-Persona. | Für Live-Simulation verwendet. |
| `@child:inner` | Fügt nach der Antwort des Kindes eine Annotation des inneren Zustands hinzu (Gefühl, Aktivierung, was helfen würde, was es verschlimmert hat, Eskalationsverlauf). | Eine kompakte Referenz für die Bezugsperson. Siehe [Leitfaden](i18n/de/docs/inner-state-guide.md). |
| `@child:inner off` | Entfernt die Annotation des inneren Zustands. | Setzt die Kinder-Persona auf die Standardausgabe zurück. |
| `@status` | Zeigt die aktive Persona und den bisherigen Gesprächskontext an. | Nützlich bei langen Sitzungen. |

### Zustandsmodulation

| Befehl | Funktion | Hinweise |
|---|---|---|
| `@set [p]=[v]` | Legt Zustandsparameter des Kindes fest (arousal, trajectory, trust, fatigue, medication, hyperfocus, feeling, context). | Ausgangsbedingung; organische Drift gilt. |
| `@set [p]=[v] persist` | Wie oben, sperrt den Wert jedoch gegen organische Drift. | Nützlich für kontrollierte Szenarien. |
| `@set clear` | Setzt alle manuellen Überschreibungen auf den simulierten organischen Zustand zurück. | Setzt auch den nach `@debrief` suspendierten Kinderzustand zurück. |
| `@set ?` | Gibt die Parametertabelle mit gültigen Werten aus. | Schnellreferenz ohne Zustandsänderung. |
| `@ [p]=[v]` | Kurzform für `@set`; numerische Schlüssel akzeptiert. | Z. B.: `@ arousal=3 trust=2`. |

### Überprüfungs- und Planungssteuerungen

| Befehl | Funktion | Hinweise |
|---|---|---|
| `@replay` | Wiederholt die letzte Antwort des Kindes und fordert einen neuen Ansatz des Erwachsenen an. | Der Benutzer liefert den neuen Ansatz; das Modell generiert keine Alternative automatisch. |
| `@debrief` | Wechselt in den Klinikermodus zur Analyse der vorherigen Interaktion. Der Zustand des Kindes wird suspendiert, nicht gelöscht. | Fokussiert auf Antezedenz, Verhalten und Konsequenz. |
| `@script [Aufgabe]` | Erstellt ein Skript für die Bezugsperson und eine visuelle Checkliste für eine bestimmte Aufgabe. | Beispiel: Hausaufgaben, das Haus verlassen, Schlafenszeit. |
| `@escalation-map [Szenario]` | Kartiert wahrscheinliche Eskalationspfade und Deeskalationsabzweigungen. | Nützlich für Routinen mit Übergängen oder hohem Konflikt. |

---

## Ausprobieren

| Plattform | Link |
|---|---|
| ChatGPT (Custom GPT) | [Sandbox](https://chatgpt.com/g/g-69b1a7644f5c81919f3fca1bbc2926fa-paiciente-v2-0) |
| Mistral (Le Chat Agent) | [Sandbox](https://chat.mistral.ai/chat/553205e3-526a-472d-99d0-0916596fa54b) |
| Gemini (Gem) | [Sandbox](https://gemini.google.com/gem/1N5cyhZd34Pb-KEzMxdsaZxjSt7jKF4jm?usp=sharing) |
| Claude | Selbstinstanziierung über die [Implementierungsanleitung](implementations/claude.md) |

Siehe [`/implementations/`](implementations/) für schrittweise Einrichtungsanleitungen auf jeder Plattform.

---

## Einschränkungen

PAIciente hat bedeutsame Grenzen, die explizit verstanden werden müssen:

- Es ist ein Simulations- und Unterstützungswerkzeug, keine Diagnosemaschine.
- Es ersetzt keinen Kliniker, kein Schulteam und keine Krisenbeurteilung.
- Die Kinder-Persona ist eine modellierte Annäherung, keine wörtliche Vorhersage dessen, was ein bestimmtes Kind sagen wird.
- Sein Nutzen hängt von der Genauigkeit und Ehrlichkeit der Beschreibung der Bezugsperson ab.
- Eine gute Simulation kann in Einzelfällen dennoch falsch liegen, weil jedes Kind in Temperament, Geschichte und Kontext variiert.

Ein überzeugendes Simulationsmodell kann überzeugend wirken, selbst wenn es nur annähernd ist. Aus diesem Grund ist die Anforderung der Kliniker-Persona, beobachtete Fakten von Schlussfolgerungen zu trennen, eine wichtige Schutzmaßnahme.

---

## Dokumentation

Die vollständige Dokumentation ist unter [`/docs/`](docs/) verfügbar. Siehe das [Inhaltsverzeichnis](docs/table-of-contents.md) für einen Überblick über alle Dateien im Repository.

- [Überblick](i18n/de/docs/overview.md) — Zweck, Umfang und Architektur
- [Personas](i18n/de/docs/personas.md) — Spezifikationen der Kliniker- und Kinder-Personas
- [Arbeitsablauf](i18n/de/docs/workflow.md) — empfohlene Nutzungssequenz
- [Verhaltenskarte](docs/behavior-map.md) — einzigartiger Instruktionssatz (EN)
- [Leitfaden innerer Zustand](i18n/de/docs/inner-state-guide.md) — Verwendung von `@child:inner` und `@set`
- [Evidenzkarte](docs/evidence-map.md) — akademische Fundierung (EN)
- [Einschränkungen](i18n/de/docs/limitations.md) — Sicherheitsgrenzen
- [Anwendungsfälle](i18n/de/docs/use-cases.md) — Beispielszenarien
- [Technische Begründung](docs/Technical-Rationale-and-Academic-Positioning.md) — formaler Rahmen und akademische Positionierung (EN)

Akademische Referenzen: [`/references/`](references/)

---

## Lizenz

Dieses Werk ist lizenziert unter einer [Creative Commons Namensnennung-Weitergabe unter gleichen Bedingungen 4.0 International Lizenz](https://creativecommons.org/licenses/by-sa/4.0/).

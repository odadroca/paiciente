<!-- i18n: source=docs/overview.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# Überblick

## 1. Zweck und Umfang

PAIciente wurde für Bezugspersonen, Eltern, Erziehungsberechtigte, Lehrkräfte und Kliniker entwickelt, die eine strukturierte Möglichkeit suchen, schwierige Interaktionen mit einem Kind zu üben, das Schwierigkeiten der Exekutivfunktion im Zusammenhang mit ADHS (Aufmerksamkeitsdefizit-Hyperaktivitätsstörung) und oppositionelles Verhalten zeigt.

Es erfüllt drei praktische Funktionen:

- **Simulation:** Der Benutzer kann mit einer Kinder-Persona sprechen und beobachten, wie ein bestimmter Ansatz des Erwachsenen wahrscheinlich aufgenommen wird.
- **Analyse:** Der Benutzer kann zu einer Kliniker-Persona wechseln, die das Geschehene verhaltensanalytisch aufschlüsselt.
- **Werkzeuge:** Die Kliniker-Persona kann Skripte, Checklisten, Eskalationskarten und Aufgabenzerlegungen erstellen.

Der vorgesehene Umfang ist bewusst eng gehalten. Es ist ein Simulations- und Dokumentationswerkzeug, kein Ersatz für Therapie, diagnostische Beurteilung oder Krisenintervention.

## 2. Architektur auf hoher Ebene

PAIciente arbeitet mit zwei explizit umschaltbaren Personas und einem Befehlsvokabular. Die aktive Persona bestimmt sowohl den Ton als auch das Antwortformat.

### 2.1 Hauptmodussteuerungen

| Befehl | Funktion | Hinweise |
|---|---|---|
| `@clinician` | Aktiviert die Kliniker-Persona. | Standard zu Gesprächsbeginn. |
| `@child` | Aktiviert die Kinder-Persona. | Für Live-Simulation verwendet. |
| `@child:inner` | Fügt nach der Antwort des Kindes eine Annotation des inneren Zustands hinzu. | Eine kompakte Referenz für die Bezugsperson. |
| `@child:inner off` | Entfernt die Annotation des inneren Zustands. | Setzt die Kinder-Persona auf die Standardausgabe zurück. |
| `@status` | Zeigt die aktive Persona und den bisherigen Gesprächskontext an. | Nützlich bei langen Sitzungen. |

### 2.2 Zustandsmodulation

| Befehl | Funktion | Hinweise |
|---|---|---|
| `@set [p]=[v]` | Legt Zustandsparameter des Kindes fest (arousal, trajectory, trust, fatigue, medication, hyperfocus, feeling, context). | Ausgangsbedingung; organische Drift gilt. |
| `@set [p]=[v] persist` | Sperrt den Wert gegen organische Drift. | Für kontrollierte Szenarien. |
| `@set clear` | Setzt alle manuellen Überschreibungen zurück. | Rückkehr zum simulierten organischen Zustand. |
| `@set ?` | Gibt die Parametertabelle aus. | Schnellreferenz. |
| `@ [p]=[v]` | Kurzform für `@set`. | Numerische Schlüssel akzeptiert. |

### 2.3 Überprüfungs- und Planungssteuerungen

| Befehl | Funktion | Hinweise |
|---|---|---|
| `@replay` | Wiederholt die letzte Antwort des Kindes und fordert einen neuen Ansatz des Erwachsenen an. | Der Benutzer liefert den neuen Ansatz. |
| `@debrief` | Wechselt in den Klinikermodus zur Analyse der vorherigen Interaktion. | Der Zustand des Kindes wird suspendiert, nicht gelöscht. |
| `@script [Aufgabe]` | Erstellt ein Skript für die Bezugsperson und eine visuelle Checkliste für eine bestimmte Aufgabe. | Beispiel: Hausaufgaben, das Haus verlassen, Schlafenszeit. |
| `@escalation-map [Szenario]` | Kartiert wahrscheinliche Eskalationspfade und Deeskalationsabzweigungen. | Nützlich für Routinen mit Übergängen oder hohem Konflikt. |

> **Warum die Zwei-Persona-Struktur wichtig ist.** Eine Persona ermöglicht es dem Benutzer, die Interaktion selbst zu üben. Die andere wandelt die Interaktion in eine verhaltensanalytische Fallformulierung mit Alternativen um. Der Wert entsteht durch den Wechsel zwischen beiden, nicht durch eine allein.

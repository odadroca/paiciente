<!-- i18n: source=docs/inner-state-guide.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# Leitfaden zum Inneren Zustand — Verwendung von `@child:inner` und `@set`

## Was es tut

Wenn Sie `@child:inner` eingeben, enthält jede nachfolgende Antwort des Kindes einen kompakten Annotationsblock am Ende namens `[INNER STATE]`. Dieser Block zeigt, was das simulierte Kind in diesem Moment fühlt und braucht — ohne die Simulation zu unterbrechen.

- **Aktivieren:** Geben Sie `@child:inner` zu jedem Zeitpunkt während einer Sitzung ein.
- **Deaktivieren:** Geben Sie `@child:inner off` ein, um zu den Standardantworten des Kindes zurückzukehren.

Die Annotation ist eine funktionale Schnellreferenz für die Bezugsperson. Sie ermöglicht es, die interne Logik hinter dem Verhalten des Kindes zu sehen, während man die Interaktion weiterhin so erlebt, wie sie sich in der Praxis entfalten würde.

## Die Annotationsfelder

Jeder `[INNER STATE]`-Block enthält die folgenden Felder:

| Feld | Was es anzeigt | Beispielwerte |
|---|---|---|
| **Feeling** | Die aktuelle Emotion des Kindes, direkt benannt. | angry, anxious, defeated, bored, blindsided, relieved |
| **Arousal** | Das Aktivierungsniveau des Nervensystems des Kindes. | low / medium / high / overloaded |
| **What would help right now** | Eine konkrete Sache, die der Erwachsene tun oder ändern könnte. | eine 2-Minuten-Vorwarnung vor der Anforderung; Wahl zwischen zwei Aufgaben; Anerkennung der Frustration |
| **What just made it worse** | Eine konkrete Sache, die eskaliert oder das Kind verschlossen hat, oder „nothing", wenn der Ansatz des Erwachsenen gut kalibriert war. | abrupter Verlust der bevorzugten Aktivität; erhobene Stimme; keine Übergangswarnung; „nothing" |

### Eskalationsverlauf

Der `[INNER STATE]`-Block enthält auch einen Eskalationsverlaufs-Unterabschnitt:

| Feld | Was es anzeigt | Beispielwerte |
|---|---|---|
| **Trajectory** | Richtung der Eskalation über die Züge hinweg. | stable / building / near-threshold / at-threshold |
| **Next likely behavior** | Eine verhaltensspezifische Vorhersage. | schlägt das Buch zu; wird still; fängt an, lauter zu argumentieren |
| **Interrupt lever** | Eine konkrete Aktion der Bezugsperson, die den Verlauf ändern könnte. | eine 2-Minuten-Pause anbieten; Stimme senken und Frustration validieren; sich zurückziehen |

**Verlaufsdefinitionen:**

| Wert | Bedeutung |
|---|---|
| stable | Aktivierung steigt nicht; die Interaktion fügt keine Stressbelastung hinzu. |
| building | Aktivierung steigt; teilweise reguliert; Interventionsfenster offen. |
| near-threshold | Eine weitere eskalierende Eingabe löst wahrscheinlich einen sichtbaren Zusammenbruch aus. |
| at-threshold | Bereits im Zusammenbruch; Deeskalation erfordert Rückzug, nicht Problemlösung. Der Unterbrechungshebel ist immer eine Variante von: **sich zurückziehen**. |

Der Verlauf wird zwischen den Zügen übertragen. Er setzt sich nicht zurück, es sei denn, ein Hebel wird erfolgreich angewendet oder `@set clear` wird ausgeführt.

## Beispielausgabe

Beispiel einer Antwort des Kindes mit aktivem `@child:inner`:

> **Erwachsener:** Du musst das iPad jetzt ausschalten. Wir gehen in 5 Minuten.
>
> **PAIciente (Kind):** *Schaut nicht hoch.* Fünf Minuten reichen nicht. Ich bin mitten in etwas drin.
>
> [INNER STATE]
> Feeling: angry, blindsided
> Arousal: high
> What would help right now: a 2-minute warning before the demand
> What just made it worse: no transition warning; abrupt loss of preferred activity
> Escalation path:
>   Trajectory: building
>   Next likely behavior: ignores adult; volume rises if pushed
>   Interrupt lever: acknowledge the interruption and offer a defined wind-down window

Die gesprochene Antwort des Kindes ist das, was die Bezugsperson hört. Der `[INNER STATE]`-Block ist das, was die Bezugsperson normalerweise nicht sehen würde — die funktionale Interpretation unter dem Verhalten.

## `@set` verwenden, um Ausgangsbedingungen zu injizieren

Der `@set`-Befehl ermöglicht es, den Zustand des Kindes vorzuladen, bevor eine Interaktion beginnt. Dies ist nützlich zum Üben spezifischer Szenarien (z. B. ein Kind, das bereits müde ist und einen Medikamentenrebound erlebt).

**Verfügbare Parameter:**

| Parameter | Gültige Werte | Numerische Kurzform |
|---|---|---|
| `feeling` | Freitext in Anführungszeichen | — |
| `arousal` | low / medium / high / overloaded | 1 / 2 / 3 / 4 |
| `trajectory` | stable / building / near-threshold / at-threshold | 1 / 2 / 3 / 4 |
| `trust` | low / medium / high | 1 / 2 / 3 |
| `fatigue` | low / medium / high | 1 / 2 / 3 |
| `medication` | on / wearing-off / off | 1 / 2 / 3 |
| `hyperfocus` | Themenname in Anführungszeichen | — |
| `context` | Freitext in Anführungszeichen (Hintergrundgeschichte — erscheint nur durch Verhalten, wird nie im Dialog offengelegt) | — |

**Beispiel:**

```
@set arousal=high trajectory=near-threshold trust=low medication=wearing-off fatigue=high feeling="anxious, ashamed"
```

Kurzform-Äquivalent:

```
@ arousal=3 trajectory=3 trust=1 medication=2 fatigue=3 feeling="anxious, ashamed"
```

Wenn `@child:inner` aktiv ist, werden injizierte Parameter mit `← [SET]` markiert. Sobald die Interaktion einen Parameter organisch von seinem injizierten Wert verschoben hat, ändert sich die Markierung zu `← [organic]`.

Verwenden Sie `@set clear`, um alle Überschreibungen zurückzusetzen. Verwenden Sie `@set ?`, um die Parametertabelle jederzeit anzuzeigen.

## Wann `@child:inner` aktivieren

- **Erste Nutzung.** Aktivieren Sie es während Ihrer ersten Sitzungen, um die Verhaltenslogik des Kindermodells lesen zu lernen.
- **Nach einer Eskalation.** Wenn eine Interaktion eskaliert ist und Sie sich nicht sicher sind warum, aktivieren Sie den Modus des inneren Zustands und wiederholen Sie das Szenario mit `@replay`. Die Annotationen zeigen, wo die Aktivierung des Kindes anstieg und was sie auslöste.
- **Beim Üben von Übergängen.** Übergänge (Gerät zu Hausaufgaben, Spiel zu Schlafenszeit, Haus zu Auto) sind ein häufiger Reibungspunkt. Die Felder des inneren Zustands machen sichtbar, ob sich das Kind vorgewarnt fühlte, eine Wahl hatte oder überrumpelt wurde.
- **Beim Vergleichen von Ansätzen.** Führen Sie dasselbe Szenario zweimal mit unterschiedlichen Formulierungen durch. Die Annotationen des inneren Zustands ermöglichen den Vergleich nicht nur dessen, was das Kind sagte, sondern was das Kind fühlte.
- **Bei Verwendung von `@set`.** Der injizierte Zustand ist am sichtbarsten, wenn der Modus des inneren Zustands aktiv ist — Sie können genau sehen, welche Parameter noch auf ihren injizierten Werten liegen und welche organisch gedriftet sind.

## Wann deaktivieren

- **Für Immersion.** Wenn Sie sich beim Lesen des Kindverhaltens sicher fühlen, deaktivieren Sie die Annotationen, um die Interpretation des Kinderzustands allein aus Worten und Handlungen zu üben — näher am echten Leben.
- **Um Ihre eigene Einschätzung zu testen.** Versuchen Sie eine Sitzung ohne Annotationen, dann verwenden Sie `@debrief`, um die Analyse des Klinikers zu erhalten. Vergleichen Sie Ihre Interpretation mit der funktionalen Aufschlüsselung des Klinikers.

## Wie es sich mit `@debrief` verbindet

`@child:inner` und `@debrief` dienen unterschiedlichen Zwecken zu unterschiedlichen Zeitpunkten:

| | `@child:inner` | `@debrief` |
|---|---|---|
| **Wann** | Während der Interaktion, in Echtzeit | Nachdem die Interaktion abgeschlossen ist |
| **Wer spricht** | Die Kinder-Persona (mit angehängten Annotationen) | Die Kliniker-Persona |
| **Was Sie erhalten** | Zug-für-Zug-Momentaufnahmen des inneren Zustands, einschließlich Eskalationsverlauf | Vollständige Antezedenz–Verhalten–Konsequenz-Analyse mit alternativen Ansätzen |
| **Am besten für** | Sehen, was im Kind Moment für Moment geschieht | Verstehen, was über den gesamten Austausch hinweg passiert ist und was zu ändern ist |

Eine typische Übungssequenz: `@child:inner` aktivieren, optional Zustand mit `@set` injizieren, die Interaktion durchführen, dann `@debrief` für eine strukturierte Überprüfung verwenden. Die Annotationen des inneren Zustands liefern Ihnen die Daten; das Debrief liefert Ihnen die Analyse. Nach dem Debrief verwenden Sie `@child`, um vom suspendierten Zustand fortzufahren, oder `@set clear` zum Zurücksetzen.

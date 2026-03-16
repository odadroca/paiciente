<!-- i18n: source=docs/behavior-map.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# Verhaltenskarte — Einzigartiger Instruktionssatz

Der besondere Wert von PAIciente liegt in der Kombination von Interaktionsregeln und nicht in einem einzelnen klinischen Konzept. Der dokumentierte Regelsatz lässt sich wie folgt zusammenfassen.

| Instruktionsfamilie | Dokumentiertes Verhalten | Praktische Konsequenz |
|---|---|---|
| Sprachverwaltung | Antwortet in der Sprache des Benutzers; übersetzt Dialog, Analyse und Feldwerte. Alle Meta-Befehle und `[INNER STATE]`-Feldbezeichnungen bleiben auf Englisch. | Die Schnittstelle bleibt für mehrsprachige Bezugspersonen natürlich, ohne die Befehlssyntax zu brechen. |
| Persona-Umschaltung | Der aktive Modus wird explizit durch `@`-Befehle gesteuert statt stillschweigend abgeleitet. | Der Benutzer weiß immer, ob er mit dem Kindermodell oder dem Analysten spricht. |
| Zustandskontinuität | Der Gesprächskontext wird bewahrt und kann auf Anfrage über `@status` zusammengefasst werden. Die Kontinuität hängt von der Verfügbarkeit des Kontextfensters ab. | Wiederholte Sitzungen können auf früheren Versuchen aufbauen, statt sich bei jedem Zug zurückzusetzen. |
| Zustandsmodulation | Der `@set`-Befehl injiziert Ausgangsbedingungen (arousal, trajectory, trust, fatigue, medication, hyperfocus, feeling, context) in die Kinder-Persona. | Benutzer können spezifische Szenarien üben, ohne auf organische Eskalation zu warten. |
| Realismus des Kindes | Die Kinder-Persona modelliert Trotz, Abschottung, Ablenkung und allmähliche Compliance statt sofortigen Gehorsam. Ein Schutz gegen Informationslecks verhindert die Offenlegung von injiziertem Kontext. | Der Benutzer kann die natürliche Konsequenz schlechter Formulierung oder abrupter Übergänge sehen. |
| Klinische Struktur | Die Kliniker-Persona trennt immer beobachtete Fakten, Hypothesen und Empfehlungen. | Interpretation wird weniger wahrscheinlich mit Evidenz verwechselt. |
| Grenzen | Das System vermeidet die Diagnose von Benutzern oder Kindern und bleibt innerhalb des angeforderten Umfangs. | Es unterstützt Übung und Reflexion, ohne übermäßige klinische Autorität zu beanspruchen. |
| Aufgabengerüst | Wenn gefragt wird, wie eine Aufgabe zu erledigen ist, zerlegt der Kliniker die Aufgabe in kindgerechte Schritte und sagt Verweigerungspunkte voraus. | Die Beratung ist operativ statt generisch. |
| Sitzungsüberprüfung | Die Replay- und Debrief-Funktionen unterstützen kontrafaktische Tests verschiedener Ansätze des Erwachsenen. `@debrief` suspendiert den Zustand des Kindes zur späteren Wiederaufnahme. | Der Benutzer kann Ansätze vergleichen, statt sich allein auf Intuition zu verlassen. |

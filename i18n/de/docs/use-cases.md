<!-- i18n: source=docs/use-cases.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# Beispiel-Anwendungsfälle

## 10.1 Eine Anforderung üben

Eine Bezugsperson, die plant, die Tablet-Zeit zu unterbrechen, kann den Kliniker um ein Übergangsskript bitten, dann zur Kinder-Persona wechseln und testen, ob die Formulierung abrupt, unfair oder wahlkompatibel wirkt. Die Verwendung von `@set hyperfocus="Tablet-Spiel"` vor dem Wechsel zu `@child` macht die Übergangskosten maximal hoch — ein realistischer Belastungstest.

## 10.2 Eine gescheiterte Interaktion überprüfen

Nach einem schwierigen Austausch in der realen Welt kann die Bezugsperson zusammenfassen, was passiert ist, und die Kliniker-Persona bitten, die Antezedenz, das Verhalten des Kindes, die Konsequenz des Erwachsenen und die Punkte zu identifizieren, an denen die Eskalation hätte unterbrochen werden können.

## 10.3 Eine routinenspezifische Checkliste erstellen

Der Benutzer kann `@script Morgenroutine` oder `@script Hausaufgabenbeginn` eingeben und eine Zerlegung in kindgerechte Schritte erhalten, mit wahrscheinlichen Verweigerungspunkten und unterstützender Sprache für die Bezugsperson.

## 10.4 Unter bestimmten Bedingungen testen

Ein Moderator kann eine Kombination von Zustandsparametern injizieren — zum Beispiel `@set arousal=high fatigue=high medication=wearing-off trust=low context="schlechter Tag in der Schule"` — und dann eine Hausaufgabenstart-Interaktion durchführen, um zu sehen, wie das Kind unter zusammengesetztem Stress reagiert. Das Aktivieren von `@child:inner` während dieser Interaktion zeigt genau, welche Parameter noch auf ihren injizierten Werten liegen und welche sich organisch verschoben haben.

---

Für vollständige Transkripte dieser und anderer Szenarien siehe [`/examples/`](/examples/).

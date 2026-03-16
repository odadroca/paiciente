<!-- i18n: source=prompt/design-notes.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
Version: 2.0 | Letzte Aktualisierung: 2026-03-11

# Designnotizen

## Einzigartiger Instruktionssatz: dokumentiertes Verhalten

Der besondere Wert von PAIciente liegt in der Kombination von Interaktionsregeln und nicht in einem einzelnen klinischen Konzept. Der dokumentierte Regelsatz laesst sich wie folgt zusammenfassen.

| Instruktionsfamilie | Dokumentiertes Verhalten | Praktische Konsequenz |
|---|---|---|
| Sprachverwaltung | Antwortet in der Sprache des Nutzers; uebersetzt Dialoge, Analysen und Feldwerte. Alle Metabefehle und `[INNER STATE]`-Feldbezeichnungen bleiben auf Englisch. | Die Oberflaeche bleibt fuer mehrsprachige Bezugspersonen natuerlich, ohne die Befehlssyntax zu beeintraechtigen. |
| Persona-Umschaltung | Der aktive Modus wird explizit durch `@`-Befehle gesteuert und nicht stillschweigend abgeleitet. | Der Nutzer weiss immer, ob er mit dem Kindermodell oder mit dem Analytiker interagiert. |
| Zustandskontinuitaet | Der Gespraechskontext wird beibehalten und kann auf Anfrage ueber `@status` zusammengefasst werden. Die Kontinuitaet haengt von der Verfuegbarkeit des Kontextfensters ab. | Wiederholte Sitzungen koennen auf frueheren Versuchen aufbauen, anstatt bei jedem Zug zurueckgesetzt zu werden. |
| Zustandsmodulation | Der Befehl `@set` injiziert Ausgangsbedingungen (Erregung, Trajektorie, Vertrauen, Muedigkeit, Medikation, Hyperfokus, Gefuehl, Kontext) in die Kind-Persona. Die Werte entwickeln sich organisch, es sei denn, `persist` wird verwendet. | Nutzer koennen bestimmte Szenarien proben, ohne auf eine organische Eskalation warten zu muessen. |
| Realismus des Kindes | Die Kind-Persona modelliert Verweigerung, Blockade, Ablenkung und schrittweise Konformitaet anstelle von sofortigem Gehorsam. Ein Schutzmechanismus gegen Lecks verhindert die Offenlegung des injizierten Kontexts. | Der Nutzer kann die natuerliche Konsequenz ungeeigneter Formulierungen oder abrupter Uebergaenge beobachten. |
| Klinische Struktur | Die Kliniker-Persona trennt stets beobachtete Fakten, Hypothesen und Empfehlungen. | Interpretation wird seltener mit Evidenz verwechselt. |
| Grenzen | Das System vermeidet es, Nutzer oder Kinder zu diagnostizieren, und bleibt im angeforderten Rahmen. | Es unterstuetzt Praxis und Reflexion, ohne klinische Autoritaet zu beanspruchen. |
| Aufgabenunterstuetzung | Wenn gefragt wird, wie eine Aufgabe zu erledigen ist, zerlegt der Kliniker die Aufgabe in kindgerechte Schritte und sagt Verweigerungspunkte voraus. | Die Beratung ist operativ statt generisch. |
| Sitzungsrueckblick | Wiederholungs- und Debriefing-Funktionen unterstuetzen kontrafaktische Tests verschiedener Erwachsenenansaetze. `@debrief` setzt den Kindzustand fuer eine spaetere Wiederaufnahme aus. | Der Nutzer kann Ansaetze vergleichen, anstatt sich allein auf die Intuition zu verlassen. |

## Designbegruendung

### 6.1 Warum im Klinikermodus beginnen

Der Start im Klinikermodus verringert die Wahrscheinlichkeit, dass das Gespraech zu einem unstrukturierten Rollenspiel wird. Zuerst werden Fakten, Aufgabenanforderungen, Uebergangsbeschraenkungen und das Ziel des Erwachsenen festgelegt, bevor der Nutzer eine Live-Interaktion testet.

### 6.2 Warum die Kind-Persona absichtlich unbequem ist

Eine nuetzliche Simulation muss Reibung bewahren. Wuerde die Kind-Persona als gehorsames Skriptziel reagieren, wuerde der Nutzer nie sehen, welche Erwachsenenverhaltensweisen zuverlaessig Verweigerung, Streit oder Blockade ausloesen. Das Modell behandelt Verweigerung daher als stressreaktiv und kontextabhaengig statt als boesartig.

### 6.3 Warum der Klinikerton direkt ist

Die Kliniker-Persona vermeidet uebertriebene Ermutigung, weil emotional aufgeladene Familienroutinen haeufig eine praezise Fehleranalyse erfordern. Ein vager, uebertrieben unterstuetzender Stil kann die funktionale Rolle der Eskalation durch den Erwachsenen, unklare Erwartungen oder unrealistische Zeitannahmen verbergen.

### 6.4 Warum Befehle wichtig sind

Das Befehlsvokabular erzeugt explizite Moduswechsel. Dies ist wichtig, weil Rollenspiel, Metaanalyse und Skripterstellung verschiedene Aufgaben mit unterschiedlichen Ausgabeanforderungen sind. PAIciente haelt diese Aufgaben getrennt, anstatt sie zu vermischen.

### 6.5 Warum `@set` existiert

Die direkte Zustandsmodulation ermoeglicht es Moderatoren und erfahrenen Nutzern, spezifische klinische Szenarien zu proben, ohne auf eine organische Eskalation warten zu muessen. Sie ermoeglicht auch kontrollierte Vergleiche -- dieselbe Interaktion zweimal unter verschiedenen Ausgangsbedingungen durchzufuehren. Der Modifikator `persist` unterstuetzt Szenarien, in denen eine bestimmte Variable konstant bleiben muss (z. B. das Testen von Ansaetzen unter fixem Medikamentenrebound).

### 6.6 Warum die Trajektorie bestehen bleibt

Die Eskalationstrajektorie setzt sich zwischen den Zuegen nicht zurueck, weil sich die reale Erregung zwischen den Zuegen nicht zuruecksetzt. Ein Kind, das nahe an die Schwelle getrieben wurde, kehrt nicht zur Basislinie zurueck, nur weil die naechste Aussage des Erwachsenen neutral ist. Diese Designentscheidung zwingt die Bezugsperson, Deeskalation als mehrstufigen Prozess zu ueben und nicht als einzelne korrektive Aussage.

---

Fuer den formalen akademischen Rahmen und die erweiterte Begruendung siehe [Technische Begruendung und akademische Positionierung](../docs/Technical-Rationale-and-Academic-Positioning.md).

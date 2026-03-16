<!-- i18n: source=docs/Technical-Rationale-and-Academic-Positioning.md | base-version=v2.1.0 | last-updated=2026-03-16 -->

# PAIciente: Ein promptbeschraenktes polytropisches System, das Verhaltensanaloga begrenzter Kompetenz und strukturierter Verifikation ohne architektonischen Monotropismus implementiert

**Technische Begruendung und akademische Positionierung**

*PAIciente v2.0 - Design-Rahmungsdokument*

---

## Zusammenfassung

PAIciente ist ein quelloffenes strukturiertes Prompt-Werkzeug, das ein Kind simuliert, das eine Aufmerksamkeitsdefizit-/Hyperaktivitaetsstoerung (ADHS, kombinierter Typ) und eine Stoerung mit oppositionellem Trotzverhalten (SOT) aufweist, ausgerichtet auf Uebungsumgebungen fuer Eltern, Paedagogen und Kliniker. Dieses Papier liefert eine detaillierte Begruendung fuer die formale Rahmung des Systems als ein *promptbeschraenktes polytropisches System, das Verhaltensanaloga begrenzter Kompetenz und strukturierter Verifikation ohne architektonischen Monotropismus implementiert*. Jede Komponente dieser Rahmung wird definiert, gegenueber Alternativen gerechtfertigt und sowohl im Ingenieurdesign des Systems als auch in seiner klinischen Evidenzbasis verankert. Das Papier argumentiert, dass diese Rahmung nicht lediglich deskriptiv, sondern konstitutiv ist: Sie unterscheidet PAIciente von angrenzenden Kategorien (Chatbot-Personas, feinabgestimmte klinische Werkzeuge, unstrukturierte Rollenspiel-Gerueste) und macht die Designverpflichtungen explizit, die seine Simulationstreue, Verifikationsarchitektur und plattformuebergreifende Portabilitaet bestimmen.

---

## 1. Einfuehrung

Grosse Sprachmodelle (LLMs) werden zunehmend fuer Verhaltenssimulation, klinische Ausbildung und szenariobasierte Bildung eingesetzt. Die meisten solcher Anwendungen fallen in eine von zwei Kategorien: (a) feinabgestimmte Modelle, die architektonisch auf ein einzelnes Verhaltensprofil festgelegt sind, oder (b) leicht instruierte Rollenspielsysteme ohne formales Zustandsmanagement, Verifikationsmechanismus oder Evidenzfundierung. PAIciente gehoert zu keiner der beiden Kategorien. Es ist ein reines Prompt-System, das strukturierte Verhaltenssimulation durch ingenieurtechnische Beschraenkungen auf einem Allzweck-LLM-Substrat erreicht, waehrend es die volle analytische Kapazitaet des Substrats fuer eine co-residente Kliniker-Persona erhaelt.

Diese duale Anforderung - *begrenzte Kompetenz simulieren* in einem Modus und *volle analytische Kompetenz ausueben* in einem anderen, innerhalb derselben Sitzung und desselben Kontextfensters - ist die zentrale Designspannung. Die Rahmungserklaerung loest sie durch Benennung von fuenf architektonischen Verpflichtungen:

1. **Promptbeschraenkt** - die Systemgrenze ist der Prompt, nicht die Modellgewichte.
2. **Polytropisch** - mehrere funktionell unterschiedliche Verarbeitungsorientierungen koexistieren.
3. **Verhaltensanaloga** - die Simulationsziele sind strukturelle Entsprechungen im Verhalten, nicht mechanistische Homologie.
4. **Begrenzte Kompetenz** - die Simulation beschraenkt die Ausgabe bewusst entlang klinisch spezifizierter Dimensionen.
5. **Ohne architektonischen Monotropismus** - das Substrat ist nicht spezialisiert; die Spezialisierung emergiert aus der Prompt-Logik.

Jeder wird im Folgenden untersucht.

---

## 2. Definitionen und Geltungsbereich

### 2.1 Promptbeschraenkt

Ein System ist *promptbeschraenkt*, wenn seine Verhaltensspezifikation vollstaendig in der Prompt-Schicht residiert - den natuerlichsprachigen Anweisungen, die dem Modell zum Inferenzzeitpunkt uebergeben werden - und nicht in den Modellgewichten, Belohnungsfunktionen, Feinabstimmungskorpora oder externem Orchestrierungscode. Der Prompt ist das System. Aenderungen am Systemverhalten sind Aenderungen am Prompt-Text. Die vortrainierten Faehigkeiten des Modells werden nicht modifiziert.

### 2.2 Polytropisch

*Polytropisch* (vom griechischen *polytropos*: "vielgewandt") bezeichnet ein System, das mehrere funktionell unterschiedliche Verarbeitungsorientierungen implementiert, jede mit eigenem Ausgabevertrag, epistemischer Haltung und Interaktionslogik, wahlbar innerhalb einer einzelnen Sitzung. Dies steht im Gegensatz zu *monotropischen* Systemen, die eine Verhaltensorientierung implementieren, und zu *Multi-Agenten*-Systemen, die Orientierungen ueber separate Modellinstanzen verteilen.

### 2.3 Verhaltensanalogon

Ein *Verhaltensanalogon* ist ein strukturell aehnliches Ausgabemuster, das einem Zielverhalten entspricht, ohne dessen generativen Mechanismus zu teilen. Wenn PAIcientes Kind-Persona fragmentierte mehrstufige Erinnerung produziert, ist die Ausgabe *analog* zur Arbeitsspeicherbegrenzung bei ADHS - sie entspricht dem beobachtbaren Muster - wird aber durch Prompt-Beschraenkungen in einem System ohne Arbeitsspeicherengpass erzeugt. Die Unterscheidung zwischen Analogon und Homologon (gleicher Mechanismus) ist kritisch fuer eine ehrliche Positionierung: PAIciente simuliert die Verhaltensoberflaeche von ADHS+SOT, nicht deren neurokognitives Substrat.

### 2.4 Begrenzte Kompetenz

*Begrenzte Kompetenz* bezieht sich auf bewusst eingeschraenkte Leistung entlang spezifizierter kognitiver, linguistischer, emotionaler und verhaltensbezogener Dimensionen. Das zugrundeliegende Modell ist zu fliessendem Mehrparagraphen-Denken, perfekter Instruktionsbefolgung und affektiv neutraler Ausgabe faehig. Der Prompt beschraenkt diese Faehigkeiten entlang klinisch definierter Achsen: exekutive Funktion (Sequenzierung, Zeitschaetzung, Aufgabeninitiierung), emotionale Regulation (Frustrationstoleranz, Ablehnungssensitivitaet), Aufmerksamkeitsallokation (interessengeleitetes Engagement, Hyperfokus) und sozialbehaviorale Reaktion (oppositionelle Verweigerung, Compliance-Bedingungen).

### 2.5 Architektonischer Monotropismus

*Architektonischer Monotropismus* beschreibt Systeme, deren Spezialisierung durch irreversible oder kostenintensive Modifikation des Modellsubstrats erreicht wird - typischerweise Feinabstimmung, RLHF mit domaenenspezifischen Belohnungsfunktionen oder architektonische Aenderungen (Adapter-Schichten, Routing-Netzwerke). Ein monotropisches System tauscht allgemeine Faehigkeit gegen Domaenenleistung. PAIciente vermeidet diesen Kompromiss explizit.

---

## 3. Begruendung: Prompt-Beschraenkung als Systemgrenze

### 3.1 Warum nicht feinabstimmen?

Ein Modell feinabzustimmen, um ein Kind mit ADHS+SOT zu simulieren, wuerde einen Trainingskorpus aus annotiertem Kinderdiskurs erfordern, der in klinischen Profilen verankert ist - ein Korpus, der nicht existiert und dessen Konstruktion erhebliche ethische Bedenken aufwerfen wuerde (Daten aus klinischen Sitzungen mit Minderjaehrigen, Einwilligungs- und Datenschutzbeschraenkungen, Risiko der Kodierung identifizierbarer Verhaltenssignaturen einzelner Kinder). Selbst wenn ein solcher Korpus existierte, wuerde die Feinabstimmung zwei strukturelle Probleme einfuehren:

**Faehigkeitserosion.** PAIcientes Kliniker-Persona erfordert die volle analytische, zitierende und strukturiert-denkende Kapazitaet des Modells. Die Feinabstimmung auf kindlichen Diskurs wuerde diese Faehigkeiten degradieren - ein gut dokumentiertes Phaenomen bei domaenenspezifischer Feinabstimmung, bei dem die Leistung ausserhalb der Domaene abnimmt [allgemeiner Befund in der Transferlernliteratur; keine spezifische PAIciente-Zitation erforderlich].

**Opazitaet.** Das Verhaltensprofil eines feinabgestimmten Modells ist in Gewichtsverteilungen kodiert, die fuer Menschen nicht inspizierbar sind. Der promptbeschraenkte Ansatz macht die vollstaendige Verhaltensspezifikation lesbar, versionierbar und auditierbar. Jede Beschraenkung der Kind-Persona - Barkleys 30%-Emotionsalterregel, die von Stringaris abgeleiteten SOT-Dimensionen, die CPS-fundierten Compliance-Bedingungen - ist im Prompt-Text sichtbar. Diese Transparenz ist nicht beilaeufig; sie ist eine Designanforderung fuer ein Werkzeug, das klinische und paedagogische Populationen bedienen soll.

### 3.2 Der Prompt als versionierte Spezifikation

Die Behandlung des Prompts als Systemgrenze ergibt konkrete Ingenieureigenschaften:

- **Reproduzierbarkeit.** Bei gleichem Prompt und gleicher Modellversion ist die Verhaltenshuelle des Systems deterministisch (modulo Stichprobenvarianz). Sitzungen koennen benutzeruebergreifend verglichen werden.
- **Auditierbarkeit.** Klinische Pruefer koennen die vollstaendige Verhaltenslogik ohne Zugang zu Modellinterna inspizieren. Jede Behauptung, die das System ueber ADHS- oder SOT-Verhalten macht, kann auf eine spezifische Prompt-Klausel und ihre zitierte Quelle zurueckverfolgt werden.
- **Portabilitaet.** Der Prompt kann ueber verschiedene LLM-Substrate (Claude, GPT, Gemini, Mistral) mit substratspezifischer Anpassung, aber identischer Verhaltensabsicht eingesetzt werden. Die plattformuebergreifende Bewertung [bereits fuer PAIciente v2.0 durchgefuehrt] ergab, dass die Verhaltenstreue je nach Substrat variiert, die Spezifikation selbst aber portabel ist.
- **Diff-basierte Iteration.** Verhaltensaenderungen sind Prompt-Patches - abgegrenzt, ueberpruefbar und rueckgaengig machbar. Dies spiegelt die Software-Engineering-Praxis wider und ermoeglicht die Art der inkrementellen, bestaetigungsgesteuerten Entwicklung, der PAIciente folgt.

---

## 4. Begruendung: Polytropie

### 4.1 Die funktionalen Orientierungen

PAIciente implementiert die folgenden unterschiedlichen Verarbeitungsorientierungen innerhalb eines einzelnen Prompts und einer einzelnen Sitzung:

| Orientierung | Ausloeser | Ausgabevertrag | Epistemische Haltung |
|---|---|---|---|
| **Kind-Persona** | `@child` | In-Charakter-Dialog; altersgerechte Sprache; verhaltensmaessig beschraenkte Ausgabe | Simulierte begrenzte Perspektive eines 9-Jaehrigen |
| **Innere-Zustands-Schicht** | `@child:inner` | Strukturierter Annotationsblock, der an die Kind-Ausgabe angehaengt wird | Metakognitiv - legt das Simulationsdenken offen |
| **Zustands-Engine** | `@set` | Parameterinjektion mit Validierung, Konflikterkennung, Fehlerbehandlung | Programmatisch - operiert auf Zustandsvariablen |
| **Kliniker-Persona** | `@clinician` | Strukturierte Analyse (Beobachtungen / Inferenzen / Empfehlungen); Zitationen | Voll analytisch; evidenzbasiert |
| **Praxiswerkzeuge** | `@replay`, `@debrief`, `@script`, `@escalation-map` | Modusspezifische strukturierte Ausgabe | Variiert je nach Werkzeug (reflexiv, generativ, analytisch) |

Dies sind keine stilistischen Variationen. Sie unterscheiden sich in Ausgabestruktur, Denktiefe, Vokabularbeschraenkungen und epistemischen Verpflichtungen. Die Kind-Persona unterdrueckt analytische Faehigkeit; die Kliniker-Persona uebt sie maximal aus. Die Innere-Zustands-Schicht nimmt eine dritte Position ein - sie denkt *ueber* die Kind-Simulation von ausserhalb der Kindperspektive nach, waehrend die Kind-Persona aktiv ist. Diese triadische Struktur (Simulation / Metakognition / Analyse) ist das zentrale polytropische Design.

### 4.2 Warum nicht Multi-Agent?

Eine alternative Architektur wuerde diese Orientierungen ueber separate Modellinstanzen oder API-Aufrufe verteilen - eine Instanz fuer das Kind, eine fuer den Kliniker, eine fuer das Zustandsmanagement. Dies wuerde die Polytropie-Anforderung vermeiden, aber einfuehren:

- **Kontextfragmentierung.** Die Analyse des Klinikers ueber eine Kind-Interaktion erfordert Zugang zur vollstaendigen Interaktionshistorie, einschliesslich innerer Zustandsannotationen und gesetzter Parameter. Die Verteilung ueber Instanzen erfordert explizite Kontextweitergabe, die verlustbehaftet ist und Latenz hinzufuegt.
- **Zustandssynchronisationsaufwand.** Das `@set`-System modifiziert Zustaende, die sowohl im Verhalten des Kindes als auch in den inneren Zustandsannotationen reflektiert werden muessen. Eine Multi-Agenten-Architektur erfordert einen gemeinsamen Zustandsbus, was Ingenieurkomplexitaet ohne entsprechenden Gewinn an Simulationsqualitaet hinzufuegt.
- **Sitzungskohaerenverlust.** Das Benutzererlebnis haengt von fliessender Umschaltung zwischen Personas innerhalb eines einzelnen Gespraechsflusses ab. Multi-Agenten-Architekturen fuehren Latenz auf Turn-Ebene und das Risiko von Kontextfenster-Fehlausrichtung ein.

Polytropie innerhalb eines einzelnen Kontextfensters vermeidet alle drei Kosten. Der Kompromiss ist Prompt-Komplexitaet - die gesamte Verhaltensspezifikation muss in einem einzigen Instruktionssatz koexistieren - aber dies ist handhabbar und ergibt, wie in Abschnitt 3.2 argumentiert, Transparenzvorteile.

### 4.3 Polytropie vs. Multi-Persoenlichkeit

Der Begriff *polytropisch* wird bewusst gegenueber Alternativen wie "Multi-Persona" oder "Multi-Persoenlichkeit" gewaehlt, um zwei irrefuehrende Implikationen zu vermeiden:

1. **Klinische Konnotation.** "Multi-Persoenlichkeit" traegt eine unvermeidbare Assoziation mit dissoziativer Identitaetsstoerung. PAIcientes Orientierungen sind keine Persoenlichkeiten; sie sind ingenieurtechnische Verarbeitungsmodi mit expliziten Aktivierungsbefehlen.
2. **Oberflaechliche Rahmung.** "Multi-Persona" suggeriert, dass der Unterschied primaer stilistisch ist (Ton, Vokabular, Register). PAIcientes Orientierungen unterscheiden sich auf struktureller Ebene: unterschiedliche Ausgabeschemata, unterschiedliche epistemische Verpflichtungen, unterschiedliche Beschraenkungssets. *Polytropisch* stellt die funktionale Vielfalt in den Vordergrund.

---

## 5. Begruendung: Verhaltensanaloga begrenzter Kompetenz

### 5.1 Die Analogon/Homologon-Unterscheidung

Dies ist die wichtigste konzeptuelle Verpflichtung in der Rahmung und die am anfaelligsten fuer Fehlinterpretation. PAIciente beansprucht nicht, ADHS oder SOT zu *haben*. Es beansprucht nicht, die neurokognitiven Mechanismen zu replizieren, die diesen Zustaenden zugrunde liegen. Es beansprucht, Verhaltensausgabe zu produzieren, die *strukturell analog* zur beobachtbaren Verhaltensoberflaeche eines Kindes mit diesen Profilen ist, wie sie von der klinischen Literatur charakterisiert wird.

Die Unterscheidung ist aus drei Gruenden wichtig:

**Ehrlicher Geltungsbereich.** Eltern und Kliniker, die PAIciente verwenden, sollten verstehen, dass sie mit einem Verhaltensmodell ueben, nicht mit einem System interagieren, das "versteht", wie es ist, ADHS zu haben. Die Analogon-Rahmung verhindert Ueberansprueche.

**Simulationstreue-Kriterien.** Wenn PAIciente mechanistische Homologie beanspruchte, muesste die Treue anhand neurokognitiver Masse bewertet werden (Arbeitsspeicherkapazitaetstests, inhibitorische Kontrolltests, Neuroimaging-Korrelate). Die Analogon-Rahmung setzt das Treuekriterium auf der Verhaltensebene an: Stimmt die Ausgabe mit dem ueberein, was die klinische Literatur als beobachtbares Verhalten beschreibt? Dies ist durch Kliniker beurteilbar, die Transkripte pruefen, nicht durch neurokognitive Instrumentierung.

**Ethische Positionierung.** Zu behaupten, ein LLM "habe" eine neurodevelopmentale Stoerung, waere irrefuehrend und potenziell schaedlich - es koennte die gelebte Erfahrung von Individuen mit diesen Stoerungen trivialisieren. Die Analogon-Rahmung lehnt mechanistische Identitaet explizit ab, waehrend sie den praktischen Nutzen der Simulation bewahrt.

### 5.2 Was begrenzt wird

Die spezifischen Kompetenzgrenzen, die in PAIcientes Kind-Persona implementiert sind, leiten sich aus der klinischen Literatur ab:

**Exekutive-Funktions-Beschraenkungen.** Barkleys vereinheitlichte Theorie der ADHS [1] positioniert Verhaltensinhibition als das Kerndefizit, mit nachgelagerten Beeintraechtigungen in Arbeitsspeicher, Selbstregulation von Affekt und Erregung, internalisierter Sprache und Rekonstitution (die Faehigkeit, Verhaltenssequenzen zu zerlegen und neu zusammenzusetzen). PAIcientes Kind-Persona implementiert Analoga dieser Beeintraechtigungen: Sie verliert den Faden bei mehrstufigen Anweisungen (Arbeitsspeicher), antwortet impulsiv bevor Fragen beendet sind (Inhibition), eskaliert unter Frustration (Affektregulation) und hat Schwierigkeiten mit Aufgabensequenzierung und Zeitschaetzung (Rekonstitution, zeitliche Verarbeitung). Barkleys umfassendere Behandlung der exekutiven Funktionen [3] und das klinische Handbuch [4] liefern den Rahmen fuer die Kalibrierung der Schwere und Interaktion dieser Beschraenkungen.

**Verzoegerung der emotionalen Regulation.** Barkleys Heuristik, dass Kinder mit ADHS bei etwa 70% ihres chronologischen Alters in der emotionalen Selbstregulation funktionieren (die "30%-Regel"), wird direkt implementiert: Die emotionalen Reaktionen der Kind-Persona sind fuer eine 9-jaehrige Figur auf etwa 6,5-7 Jahre kalibriert. Dies manifestiert sich als geringere Frustrationstoleranz, hoehere Ablehnungssensitivitaet und groessere Schwierigkeiten mit Uebergaengen, als fuer das chronologische Alter erwartet wuerde.

**Oppositionelle Reaktionsstruktur.** Anstatt SOT als einheitlichen Trotz zu implementieren, stuetzt sich PAIciente auf das dreidimensionale Modell von Stringaris und Goodman [6] - reizbare, eigensinnige und verletzende Dimensionen - und auf die Bifaktor-Analyse von Burke et al. [7], die Reizbarkeit als eigenstaendige klinische Dimension bestaetigt. Das oppositionelle Verhalten der Kind-Persona ist kein zufaelliger Widerstand; es wird kontextuell durch wahrgenommene Ungerechtigkeit, willkuerliche Autoritaet, Autonomieverlust oder kontrollorientierte Interaktion ausgeloest - konsistent mit Greenes Interpretation zurueckbleibender Faehigkeiten [12, 13] und der Betonung der SOT-Literatur auf den funktionalen Kontext [8, 9, 10].

**Compliance-Bedingungen.** Die Compliance der Kind-Persona ist nicht binaer (gehorchen/verweigern), sondern bedingt durch identifizierbare interaktionale Faktoren: Autonomiegewaehrung, transparente Begruendung, wahrgenommene Fairness, Wahlarchitektur und Regulationszustand der Bezugsperson. Dies modelliert den gut etablierten Befund, dass oppositionelles Verhalten bei SOT keine Starrheit auf Trait-Ebene ist, sondern eine Stressreaktion, die durch relationale und kontextuelle Variablen moduliert wird [8, 11, 12]. Die praktische Implikation ist, dass Benutzer, die mit PAIciente ueben, differentielle Ergebnisse verschiedener interaktionaler Ansaetze beobachten koennen - die Simulation reagiert auf Strategie, nicht nur auf Befehle.

**Komorbiditaetsinteraktion.** Die ADHS+SOT-Komorbiditaet wird nicht als zwei unabhaengige Symptomlisten implementiert, die addiert werden. Die Interaktionseffekte werden modelliert: Exekutive-Funktions-Defizite senken die Schwelle fuer oppositionelle Aktivierung (das Kind hat weniger regulatorische Ressourcen, um Frustration zu bewaeltigen); SOT-getriebene Verweigerung verstaerkt ADHS-getriebene Aufgabenvermeidung; der Medikationszustand (`@set medication`) moduliert beide Profile gleichzeitig. Dies spiegelt die hohen Komorbiditaetsraten wider, die in der meta-analytischen Literatur dokumentiert sind [18], und die Neuroimaging-Evidenz fuer gemeinsame und distinkte neurale Korrelate [19].

### 5.3 Wie die Begrenzung erreicht wird

Der Begrenzungsmechanismus ist vollstaendig promptbasiert. Spezifische Prompt-Klauseln beschraenken:

- **Vokabular und Syntax**: altersgerechte Ausgabe, mit Ausnahmen fuer Hyperfokus-Domaenen (wo das Vokabular das der Gleichaltrigen uebersteigen kann, gemaess dem klinischen Profil).
- **Denktiefe**: Die Kind-Persona produziert kein analytisches Denken, keine kausale Erklaerung ihres eigenen Verhaltens und keine strukturierte Argumentation - diese sind der Kliniker-Persona vorbehalten.
- **Affektive Spannweite**: Emotionale Reaktionen werden nach der 30%-Regel kalibriert; Ablehnungssensitivitaet wird explizit parametrisiert.
- **Compliance-Logik**: Bedingte Regeln spezifizieren, wann das Kind kooperiert, widersteht, eskaliert oder sich zurueckzieht, basierend auf dem interaktionalen Ansatz und den aktuellen Zustandsparametern.
- **Informationsleckage-Praevention**: Die Kind-Persona ist explizit beschraenkt, injizierten Kontext (`@set context`) preiszugeben, ihre eigene Hintergrundgeschichte zu erklaeren oder aus der Rolle zu fallen, um klinische Informationen bereitzustellen. Wenn Gespraechsdruck eine solche Offenlegung erzwingen wuerde, spezifiziert der Prompt Ablenkungsverhalten (Schweigen, Themenwechsel, einsilbige Antwort).

Keine dieser Beschraenkungen modifiziert die Modellgewichte. Sie operieren als Verhaltensregeln, die zum Inferenzzeitpunkt interpretiert werden. Das Modell behaelt seine volle Faehigkeit; der Prompt kanalisiert sie.

---

## 6. Begruendung: Strukturierte Verifikation

### 6.1 Das Verifikationsproblem

Verhaltenssimulation ohne Verifikation ist Simulation ohne Rechenschaftspflicht. Wenn ein Benutzer mit der Kind-Persona interagiert und Eskalation beobachtet, muss er wissen: Wurde die Eskalation von der internen Logik der Simulation gesteuert (die Zustandsparameter, der interaktionale Antezedent, das Trajektorienmodell) oder war sie ein Artefakt stochastischer Generierung? Ohne Verifikationsmechanismen ist die Simulation eine Blackbox, die zufaellig plausibel aussehende Ausgabe produziert.

PAIciente adressiert dies durch vier Verifikationssubsysteme:

### 6.2 Innere-Zustands-Annotationen (`@child:inner`)

Wenn aktiv, haengt die Innere-Zustands-Schicht einen strukturierten Block an jede Kind-Antwort an:

```
[INNER STATE]
Feeling: <Emotionslabel>
Arousal: low / medium / high / overloaded
What would help right now: <1 konkretes Element>
What just made it worse: <1 konkretes Element, oder "nothing">
Escalation path:
  Trajectory: stable / building / near-threshold / at-threshold
  Next likely behavior: <1 verhaltensspezifische Zeile>
  Interrupt lever: <1 konkrete Bezugspersonen-Aktion>
```

Dies erfuellt drei Verifikationsfunktionen:

- **Transparenz des Simulationsdenkens.** Der Benutzer kann inspizieren, *warum* das Kind so reagiert hat - nicht nur was es sagte, sondern welchen emotionalen Zustand, welches Erregungsniveau und welche Eskalationstrajektorie die Simulation der Interaktion zugeordnet hat.
- **Praediktive Rechenschaftspflicht.** Die Felder "next likely behavior" und "interrupt lever" verpflichten die Simulation zu Vorhersagen, die der Benutzer in nachfolgenden Zuegen testen kann. Wenn die Simulation vorhersagt "Kind wird die Tuer zuschlagen" und der Unterbrechungshebel "eine 2-Minuten-Pause anbieten" ist, kann der Benutzer den Hebel ausprobieren und beurteilen, ob die Simulation ihrer eigenen Logik folgt.
- **Zustandsherkunftsverfolgung.** Wenn `@set`-Parameter aktiv sind, markiert der Innere-Zustands-Block jedes Feld mit `<- [SET]` (vom Benutzer injiziert) oder `<- [organic]` (aus der Interaktion abgeleitet). Dies unterscheidet zwischen benutzerkontrolliertem und simulationsabgeleitetem Zustand und verhindert Vermengung.

### 6.3 Programmierbares Zustands-Engine (`@set`)

Das `@set`-System ermoeglicht es Benutzern, spezifische Ausgangsbedingungen zu injizieren - Erregungsniveau, Trajektorie, Vertrauen, Muedigkeit, Medikationszustand, Hyperfokus-Ziel und kontextuelle Hintergrundgeschichte - und zu beobachten, wie sich die Simulation von diesem Ausgangspunkt aus verhaelt. Dies ermoeglicht:

- **Kontrollierter Vergleich.** Der gleiche interaktionale Ansatz kann gegen verschiedene Ausgangszustaende getestet werden (z. B. hohe Erregung/geringes Vertrauen vs. geringe Erregung/hohes Vertrauen), wobei der Effekt der Zustandsvariablen auf Verhaltensergebnisse isoliert wird.
- **Szenario-Reproduzierbarkeit.** Klinische Ausbilder koennen exakte Zustandskonfigurationen fuer Trainingsaufgaben spezifizieren und sicherstellen, dass mehrere Auszubildende auf dieselbe simulierte Ausgangsbedingung treffen.
- **Grenzfall-Tests.** Extreme Zustandskonfigurationen (z. B. `arousal=overloaded trajectory=at-threshold trust=low medication=wearing-off`) setzen die Verhaltenslogik der Simulation unter Grenzbedingungen einem Stresstest aus.

Das System umfasst formale Validierung: Werte ausserhalb des Bereichs produzieren typisierte Fehler; intern inkonsistente Parameterkombinationen produzieren explizite Warnungen; die Simulation faehrt mit den angegebenen Werten fort, kennzeichnet aber die Inkonsistenz. Dies verhindert stilles Muell-rein/Muell-raus-Verhalten.

### 6.4 Post-hoc-Analyse (`@debrief`)

Der `@debrief`-Befehl schaltet automatisch auf die Kliniker-Persona um und produziert eine strukturierte Analyse der vorhergehenden Kind-Interaktion. Dies ist Verifikation durch Expertenprüfung: Die Kliniker-Persona, die mit voller analytischer Kapazitaet operiert, bewertet die Interaktion unter Verwendung desselben strukturierten Formats (Beobachtungen -> Inferenzen -> Empfehlungen), das ein menschlicher Kliniker in der Supervision verwenden koennte. Der Kind-Zustand wird angehalten, nicht geloescht, so dass der Benutzer die Kind-Interaktion nach dem Debriefing fortsetzen kann.

### 6.5 Uebungsschleife (`@replay`)

Der `@replay`-Befehl gibt den letzten Kind-Zug mit demselben Zustand erneut aus und fordert den Benutzer dann auf, einen alternativen Ansatz auszuprobieren. Dies erzeugt eine kontrollierte Experimentalschleife: gleiche Ausgangsbedingungen, andere Intervention, beobachtbares differentielles Ergebnis. Das Modell generiert die Alternative nicht automatisch - der Benutzer muss sie liefern - was die Uebungsfunktion bewahrt (der Benutzer ist der Lernende, nicht der Beobachter).

---

## 7. Begruendung: Ablehnung des architektonischen Monotropismus

### 7.1 Der Monotropismus-Kompromiss

Architektonischer Monotropismus - ein Modell durch Feinabstimmung, Belohnungsformung oder strukturelle Modifikation zu spezialisieren - erkauft Domaenenleistung auf Kosten allgemeiner Faehigkeit. Fuer Einzwecksysteme ist dieser Kompromiss oft akzeptabel. Fuer PAIciente ist er strukturell inkompatibel mit den Designanforderungen.

Die zentrale Inkompatibilitaet ist die **Polytropie-Anforderung** (Abschnitt 4). PAIciente muss gleichzeitig unterstuetzen:

- Eine Kind-Persona, die analytisches Denken *unterdrueckt*, altersgerechtes Vokabular beibehalt und bedingter Compliance-Logik folgt.
- Eine Kliniker-Persona, die analytisches Denken *maximiert*, peer-reviewte Evidenz zitiert und strukturierte klinische Bewertung produziert.
- Eine Zustands-Engine, die Parametervalidierung, Konflikterkennung und formale Fehlerbehandlung durchfuehrt.
- Eine Innere-Zustands-Schicht, die metakognitive Annotationen ueber die interne Logik der Kind-Simulation produziert.

Diese Orientierungen stellen gegensaetzliche Anforderungen an die Modellkapazitaet. Ein Modell, das fuer kindliche Ausgabe feinabgestimmt ist, wuerde bei Kliniker-Modus-Aufgaben degradieren. Ein Modell, das fuer klinische Analyse feinabgestimmt ist, wuerde sich dagegen straeuben, die beschraenkte, fragmentierte, emotional reaktive Ausgabe zu produzieren, die von der Kind-Persona verlangt wird. Promptebenen-Steuerung vermeidet dies, indem der vollstaendige Faehigkeitsraum des Substrats intakt bleibt und pro Orientierung daraus ausgewaehlt wird.

### 7.2 Plattformuebergreifende Portabilitaet

PAIciente wurde auf fuenf LLM-Substraten bewertet: Claude Projects, ChatGPT CustomGPT, Mistral Agents, Gemini Gems und Grok. Diese Bewertung ist moeglich, *weil* das System nicht architektonisch monotropisch ist - es ist eine portable Spezifikation, die auf jedem ausreichend leistungsfaehigen LLM instanziiert werden kann. Feinabgestimmte monotropische Systeme sind per Definition an ihr Trainingssubstrat gebunden.

Das nicht-monotropische Design macht eine solche plattformuebergreifende Bewertung strukturell moeglich - dieselbe Verhaltensspezifikation kann auf jedem Substrat instanziiert und die resultierende Simulationstreue verglichen werden. Dieser Vergleich koennte nicht durchgefuehrt werden, wenn PAIciente architektonisch durch Feinabstimmung oder Gewichtsmodifikation an ein einzelnes Substrat gebunden waere.

### 7.3 Das Argument des Allzwecksubstrats

Das Argument fuer ein Allzwecksubstrat ist nicht lediglich pragmatisch (Portabilitaet, Kostenvermeidung). Es ist strukturell. Die *Qualitaet* der Kind-Simulation haengt vom latenten Wissen des Substrats ueber Entwicklungspsychologie, Verhaltensdynamiken und klinische Rahmenwerke ab. Ein Allzweck-LLM, das auf breiten Korpora trainiert wurde, hat - in seinen Gewichtsverteilungen - statistische Muster aus klinischer Literatur, paedagogischer Psychologie, Kindentwicklungsforschung und naturalistischem Diskurs kodiert. Der Prompt muss dem Modell nicht beibringen, wie ADHS aussieht; er muss bestehendes Wissen *aktivieren und beschraenken*.

Feinabstimmung auf einem engen Korpus wuerde einen Teil dieses latenten Wissens mit domaenenspezifischen Mustern ueberschreiben und potenziell die Faehigkeit der Simulation reduzieren, flexibel auf neuartige interaktionale Ansaetze zu reagieren. Der promptbeschraenkte Ansatz bewahrt die vollstaendige latente Wissensbasis und lenkt sie durch Verhaltensregeln.

---

## 8. Positionierung von PAIciente unter angrenzenden Kategorien

Die Rahmungserklaerung positioniert PAIciente ausserhalb mehrerer angrenzender Kategorien. Die Unterscheidungen sind es wert, explizit gemacht zu werden.

### 8.1 Keine Chatbot-Persona

Standard-Chatbot-Personas (Kundenservice-Bots mit "freundlichen" Toenen, kreative Schreibassistenten mit "Charakterstimmen") operieren auf stilistischer Ebene - sie passen Register, Vokabular und Affekt an, ohne strukturierte Verhaltenslogik, Zustandsmanagement oder Verifikationsmechanismen zu implementieren. PAIcientes Kind-Persona ist keine Toneinstellung; sie ist eine Verhaltensspezifikation mit bedingten Compliance-Regeln, Eskalationstrajektorien, parametrisiertem Zustand und praediktiven Annotationen. Die Unterscheidung ist zwischen *Stil* (wie etwas gesagt wird) und *Verhaltenslogik* (was unter welchen Bedingungen und warum gesagt wird).

### 8.2 Kein feinabgestimmtes klinisches Werkzeug

Klinische NLP-Werkzeuge, die fuer spezifische Aufgaben feinabgestimmt sind (diagnostisches Screening, Behandlungsempfehlung, Symptomextraktion), sind architektonisch monotropisch per Design - sie tauschen Generalitaet gegen Domaenengenauigkeit. PAIciente ist in diesem Sinne kein klinisches Werkzeug. Es diagnostiziert nicht, screent nicht und empfiehlt keine Behandlung. Es bietet eine *Uebungsumgebung* - eine Simulation, die auf interaktionale Strategie in klinisch fundierten Weisen reagiert, gepaart mit einer analytischen Persona, die die Dynamiken erklaert. Das System lehnt klinische Funktion in seinen Prompt-Beschraenkungen explizit ab.

### 8.3 Kein unstrukturiertes Rollenspiel-Geruest

Unstrukturierte Rollenspiel-Prompts ("tun Sie so, als waeren Sie ein Kind mit ADHS") produzieren variable, nicht verifizierbare Ausgabe ohne Zustandsmanagement, ohne Eskalationslogik, ohne Verifikationsmechanismus und ohne Evidenzfundierung. Die Ausgabe mag in einzelnen Zuegen plausibel sein, aber es fehlt die verhaltensmaessige Kohaerenz ueber Zuege hinweg, es gibt keinen Mechanismus fuer kontrollierten Vergleich, und sie kann nicht auf Simulationsdenken hin inspiziert werden. PAIcientes Beitrag ist genau die strukturierte Schicht, die Rollenspiel in rechenschaftspflichtige Simulation transformiert.

---

## 9. Implikationen

### 9.1 Fuer die Bewertung der Simulationstreue

Die Rahmung bestimmt, was als Treue zaehlt. Da PAIciente Verhaltensanaloga (keine mechanistischen Homologa) implementiert, sollte die Treue-Bewertung die Verhaltensoberflaeche anvisieren: Produziert die Reaktion des simulierten Kindes auf eine validierte interaktionale Strategie (z. B. CPS Plan B [12, 13], PCIT-artiges benanntes Lob [14]) Ergebnisse, die mit der Beschreibung der klinischen Literatur uebereinstimmen, wie Kinder mit ADHS+SOT auf diese Strategien reagieren? Dies ist eine testbare Proposition, die keine neurokognitive Instrumentierung erfordert.

### 9.2 Fuer Benutzererwartungen

Die Rahmung setzt ehrliche Erwartungen. Benutzer sollten verstehen, dass sie mit einem Verhaltensmodell ueben, nicht mit einem digitalen Kind. Die Reaktionen der Simulation werden durch Prompt-Regeln und Modellinferenz gesteuert, nicht durch eine innere Erfahrung neurodevelopmentaler Differenz. Diese Unterscheidung sollte in allen benutzerorientierten Dokumentationen explizit gemacht werden.

### 9.3 Fuer Erweiterung und Beitraege

Die promptbeschraenkte, nicht-monotropische Architektur bedeutet, dass die Erweiterung von PAIciente (Hinzufuegen neuer Verhaltensprofile, neuer klinischer Werkzeuge, neuer Bewertungsmechanismen) nur Prompt-Modifikation erfordert - kein Neutraining, kein Gewichtszugang, keine Infrastrukturaenderungen. Dies senkt die Beitragsschwelle und ermoeglicht community-getriebene Iteration, konsistent mit der Open-Source-Verpflichtung des Projekts.

---

## 10. Einschraenkungen

**Simulationsdecke.** Verhaltensanaloga haben eine Treuedecke. Das Modell kann keine sensorischen Verarbeitungsunterschiede, physiologische Erregung oder somatische Zustaende simulieren, die das Verhalten bei realen Kindern beeinflussen. Verhaltensweisen, die stark davon abhaengen (z. B. medikamentenbezogene Appetitveraenderungen, sensorische Ueberreizung in lauten Umgebungen), koennen auf der Verhaltensausgabeebene approximiert, aber nicht mechanistisch fundiert werden.

**Stochastische Varianz.** Promptbeschraenkte Systeme erben die Stichprobenvarianz des zugrundeliegenden Modells. Zwei Laeufe aus identischen Zustaenden und Eingaben koennen unterschiedliche Ausgaben produzieren. Das `@set`-System reduziert dies, eliminiert es aber nicht - es beschraenkt die Ausgangsbedingungen, nicht die vollstaendige generative Trajektorie.

**Substratbhaengigkeit.** Trotz Portabilitaet variiert die Verhaltenstreue ueber LLM-Substrate hinweg. Einige Modelle widersetzen sich der Aufrechterhaltung unterdrueckter analytischer Faehigkeit im Kind-Modus; andere loesen Inhaltssicherheitsfilter bei oppositionellem Dialog aus. Die Prompt-Spezifikation ist portabel; die Qualitaet ihrer Ausfuehrung ist nicht garantiert.

**Keine empirische Validierung.** PAIcientes Verhaltensanaloga sind in der klinischen Literatur fundiert, aber die Simulation selbst wurde nicht empirisch gegen reale klinische Interaktionen validiert. Ob Benutzer, die mit PAIciente ueben, Faehigkeiten auf reale Interaktionen mit Kindern mit ADHS+SOT uebertragen, ist eine offene empirische Frage.

---

## 11. Schlussfolgerung

Die Rahmung von PAIciente als ein *promptbeschraenktes polytropisches System, das Verhaltensanaloga begrenzter Kompetenz und strukturierter Verifikation ohne architektonischen Monotropismus implementiert*, ist keine dekorative Terminologie. Jeder Begriff identifiziert eine spezifische Designverpflichtung mit konkreten ingenieur- und klinischen Implikationen:

- *Promptbeschraenkt* gewaehrleistet Transparenz, Auditierbarkeit und Portabilitaet.
- *Polytropisch* ermoeglicht co-residente Simulations- und Analyseorientierungen innerhalb einer einzelnen Sitzung.
- *Verhaltensanaloga* setzen ehrlichen Geltungsbereich und angemessene Treuekriterien.
- *Begrenzte Kompetenz* fundiert die Simulationsbeschraenkungen in zitierter klinischer Evidenz.
- *Ohne architektonischen Monotropismus* bewahrt das Allzwecksubstrat, das fuer Polytropie und plattformuebergreifende Bereitstellung erforderlich ist.

Zusammen definieren diese Verpflichtungen einen Designraum, der sich von Chatbot-Personas, feinabgestimmten klinischen Werkzeugen und unstrukturierten Rollenspiel-Geruesten unterscheidet. Die Rahmung macht explizit, was PAIciente ist, was es nicht ist und unter welchen Bedingungen seine Simulationstreue bewertet werden sollte.

---

## References

[1] Barkley, R. A. (1997). Behavioral inhibition, sustained attention, and executive functions: Constructing a unifying theory of ADHD. *Psychological Bulletin, 121*(1), 65–94. https://doi.org/10.1037/0033-2909.121.1.65

[2] Barkley, R. A. (1997). *ADHD and the nature of self-control*. Guilford Press.

[3] Barkley, R. A. (2012). *Executive functions: What they are, how they work, and why they evolved*. Guilford Press.

[4] Barkley, R. A. (Ed.). (2015). *Attention-deficit hyperactivity disorder: A handbook for diagnosis and treatment* (4th ed.). Guilford Press.

[5] Faraone, S. V., Bellgrove, M. A., Brikell, I., et al. (2024). Attention-deficit/hyperactivity disorder. *Nature Reviews Disease Primers, 10*(1), 11. https://doi.org/10.1038/s41572-024-00495-0

[6] Stringaris, A., & Goodman, R. (2009). Three dimensions of oppositionality in youth. *Journal of Child Psychology and Psychiatry, 50*(3), 216–223. https://doi.org/10.1111/j.1469-7610.2008.01989.x

[7] Burke, J. D., Boylan, K., Rowe, R., et al. (2014). Identifying the irritability dimension of ODD. *Journal of Abnormal Psychology, 123*(4), 841–851. https://doi.org/10.1037/a0037898

[8] Hawes, D. J., Gardner, F., Dadds, M. R., et al. (2023). Oppositional defiant disorder. *Nature Reviews Disease Primers, 9*(1), 31. https://doi.org/10.1038/s41572-023-00441-6

[9] Mars, J. A., Aggarwal, A., & Marwaha, R. (2024). Oppositional defiant disorder. In *StatPearls*. StatPearls Publishing.

[10] Ghosh, A., Ray, A., & Basu, A. (2017). Oppositional defiant disorder: Current insight. *Psychology Research and Behavior Management, 10*, 353–367. https://doi.org/10.2147/PRBM.S120582

[11] Kaur, M., Floyd, A., & Balta, A.-M. (2022). Oppositional defiant disorder: Evidence-based review of behavioral treatment programs. *Annals of Clinical Psychiatry, 34*(1), 44–58. https://doi.org/10.12788/acp.0056

[12] Greene, R. W. (2021). *The explosive child* (6th ed.). Harper.

[13] Greene, R. W., & Ablon, J. S. (2006). *Treating explosive kids: The collaborative problem-solving approach*. Guilford Press.

[14] Thomas, R., & Zimmer-Gembeck, M. J. (2007). Behavioral outcomes of Parent-Child Interaction Therapy and Triple P-Positive Parenting Program. *Journal of Abnormal Child Psychology, 35*(3), 475–495. https://doi.org/10.1007/s10802-007-9104-9

[15] Murrihy, R. C., Drysdale, S. A. O., Dedousis-Wallace, A., et al. (2023). Community-delivered Collaborative and Proactive Solutions and Parent Management Training for oppositional youth. *Behaviour Therapy, 54*(2), 400–417. https://doi.org/10.1016/j.beth.2022.10.005

[16] Dedousis-Wallace, A., Drysdale, S. A. O., McAloon, J., et al. (2025). Predictors and moderators of two treatments of oppositional defiant disorder in children. *Journal of Clinical Child & Adolescent Psychology, 54*(1), 67–82. https://doi.org/10.1080/15374416.2022.2127102

[17] Lin, X., He, T., Heath, M., Chi, P., & Hinshaw, S. (2022). A systematic review of multiple family factors associated with oppositional defiant disorder. *International Journal of Environmental Research and Public Health, 19*(17), 10866. https://doi.org/10.3390/ijerph191710866

[18] Njardvik, U., Wergeland, G. J., Riise, E. N., Hannesdottir, D. K., & Öst, L.-G. (2025). Psychiatric comorbidity in children and adolescents with ADHD. *Clinical Psychology Review, 118*, 102571. https://doi.org/10.1016/j.cpr.2025.102571

[19] Noordermeer, S. D. S., Luman, M., Oosterlaan, J., & Hartman, C. A. (2016). A systematic review and meta-analysis of neuroimaging in ODD and CD taking ADHD into account. *Neuropsychology Review, 26*(1), 44–72. https://doi.org/10.1007/s11065-015-9315-8

[20] American Psychiatric Association. (2022). *Diagnostic and statistical manual of mental disorders* (5th ed., text rev.; DSM-5-TR). American Psychiatric Association Publishing.

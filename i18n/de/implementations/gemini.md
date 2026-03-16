<!-- i18n: source=implementations/gemini.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# PAIciente auf Gemini
---
### Sandbox-Link:
* Plattform-Einschrankung: Der Benutzer muss mit 1 Google-Konto angemeldet sein:
  https://gemini.google.com/gem/1N5cyhZd34Pb-KEzMxdsaZxjSt7jKF4jm?usp=sharing

---
## So instanziieren Sie

### Schritt 1 — Einen Gem erstellen

1. Gehen Sie zu [gemini.google.com](https://gemini.google.com) in einem **Desktop-Browser**. (Die Erstellung von Gems ist in der mobilen App zum Zeitpunkt dieser Veroffentlichung nicht verfugbar.)
2. Melden Sie sich mit Ihrem Google-Konto an (der kostenlose Tarif ist ausreichend).
3. Klicken Sie in der linken Seitenleiste auf **Gem manager** und dann auf **Create Gem**.

### Schritt 2 — Den System-Prompt einfugen

1. Setzen Sie den **Name** auf „PAIciente".
2. Offnen Sie die Datei `/prompt/system-prompt.md` in diesem Repository und kopieren Sie den gesamten Inhalt.
3. Fugen Sie den vollstandigen System-Prompt in das Feld **Instructions** ein. Andern Sie ihn nicht — PAIciente verwaltet Sprache und Kontext nativ.
4. Klicken Sie auf **Save**.

### Schritt 3 - OPTIONAL - Uber einen Link teilen

1. Offnen Sie Ihren gespeicherten Gem und klicken Sie auf die Schaltflache **Share**.
2. Legen Sie die Freigabeberechtigungen fest (Google-Drive-Stil: „Anyone with the link" oder eingeschrankt).
3. Kopieren Sie den Freigabelink.


## Hinweise

- **Kompatibilitat mit dem kostenlosen Tarif.** Die Erstellung und Nutzung von Gems ist im kostenlosen Tarif von Gemini verfugbar. Kein kostenpflichtiges Abonnement ist erforderlich.
- **Nur Desktop fur die Erstellung.** Gems mussen auf gemini.google.com in einem Desktop-Browser erstellt werden. Nach der Erstellung konnen sie auf Mobilgeraten verwendet werden.
- **Kontextfensterlimit im kostenlosen Tarif.** Der kostenlose Tarif hat ein Kontextfenster von 32.000 Tokens. Langere Multi-Turn-Sitzungen (lange therapeutische Gesprache) konnen dieses Limit erreichen, woraufhin fruhere Teile des Gesprachs aus dem Kontext entfernt werden. Benutzer in langeren Sitzungen sollten sich bewusst sein, dass die Kontinuitat abnehmen kann.
- **EU/PT-Verfugbarkeit.** Benutzer in der EU und Portugal greifen uber die Verbraucher-App (gemini.google.com) auf Gemini zu, nicht uber die API. Alle oben genannten Anweisungen gelten fur den Weg uber die Verbraucher-App.

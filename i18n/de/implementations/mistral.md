<!-- i18n: source=implementations/mistral.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# PAIciente auf Mistral
---
### Sandbox-Link:
* Plattform-Einschrankung: Der Benutzer muss mit 1 Mistral-Konto angemeldet sein (Le Chat Free scheint zu funktionieren):
  https://chat.mistral.ai/chat/553205e3-526a-472d-99d0-0916596fa54b

---
## So instanziieren Sie

### Schritt 1 - Einen Agenten in Le Chat erstellen

1. Gehen Sie zu [chat.mistral.ai](https://chat.mistral.ai) und melden Sie sich an (ein kostenloses Konto ist ausreichend).
2. Klicken Sie in der linken Seitenleiste auf **Agents**.
3. Klicken Sie auf **Create Agent**.

### Schritt 2 - Den System-Prompt einfugen

1. Setzen Sie den **Name** auf „PAIciente" und fugen Sie eine kurze Beschreibung hinzu.
2. Offnen Sie die Datei `/prompt/system-prompt.md` in diesem Repository und kopieren Sie den gesamten Inhalt.
3. Fugen Sie den vollstandigen System-Prompt in das Feld **Behavior** ein. Andern Sie ihn nicht — PAIciente verwaltet Sprache und Kontext nativ.

### Schritt 3 - OPTIONAL - Sichtbarkeit auf Offentlich setzen

1. Setzen Sie unter den Agenteneinstellungen **Visibility** auf **Public**.
2. Speichern Sie den Agenten.
3. Kopieren Sie den offentlichen Link, um ihn mit Benutzern zu teilen.


## Hinweise

- **Kompatibilitat mit dem kostenlosen Tarif.** Die Erstellung und Nutzung von Agenten in Le Chat ist im kostenlosen Tarif verfugbar. Kein kostenpflichtiges Abonnement ist erforderlich, um PAIciente auf Mistral zu erstellen oder zu nutzen.

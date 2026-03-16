<!-- i18n: source=implementations/chatgpt.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# PAIciente auf ChatGPT

---
### Sandbox-Link:
* Funktioniert ohne Plattform-Login - Einschränkungen des kostenlosen Tarifs gelten, funktioniert aber recht gut
  https://chatgpt.com/g/g-69b1a7644f5c81919f3fca1bbc2926fa-paiciente-v2-0

---
## So instanziieren Sie

### Schritt 1 - Einen Custom GPT erstellen

1. Gehen Sie zu [chatgpt.com](https://chatgpt.com) und melden Sie sich mit einem **Plus- oder Pro-Konto** an. (Die Erstellung von Custom GPTs erfordert ein kostenpflichtiges Abonnement.)
2. Klicken Sie auf Ihr Profilsymbol in der unteren linken Ecke und wählen Sie **My GPTs**.
3. Klicken Sie auf **Create a GPT**.

### Schritt 2 - Den System-Prompt einfügen

1. Wechseln Sie im GPT-Editor zum Reiter **Configure**.
2. Setzen Sie den **Name** auf „PAIciente" und fügen Sie eine kurze Beschreibung hinzu.
3. Öffnen Sie die Datei `/prompt/system-prompt.md` in diesem Repository und kopieren Sie den gesamten Inhalt.
4. Fügen Sie den vollständigen System-Prompt in das Feld **Instructions** ein. Ändern Sie ihn nicht — PAIciente verwaltet Sprache und Kontext nativ.
5. Deaktivieren Sie unter Capabilities Code Interpreter, DALL-E und Web Browsing, es sei denn, Sie haben einen bestimmten Grund, sie zu aktivieren.

### Schritt 3 - OPTIONAL - Im GPT Store veröffentlichen

1. Klicken Sie auf **Save** und wählen Sie **Publish to > Everyone**.
2. Der GPT wird überprüft und im GPT Store gelistet.
3. Teilen Sie den öffentlichen Link mit den Benutzern.

## Hinweise

- **Die Erstellung von GPTs erfordert Plus oder Pro.** Benutzer des kostenlosen Tarifs können keine Custom GPTs erstellen - können aber die Sandbox nutzen:
	- **Benutzer des kostenlosen Tarifs können auf den GPT Store zugreifen.** Jeder mit einem kostenlosen ChatGPT-Konto kann einen veröffentlichten GPT über seinen Store-Link nutzen — ein kostenpflichtiges Abonnement ist zum *Nutzen* nicht erforderlich.
	- **Ratenlimits bei Multi-Turn-Sitzungen im kostenlosen Tarif.** Benutzer des kostenlosen Tarifs unterliegen strengeren Ratenlimits (Nachrichten pro Stunde/Tag). Längere Sitzungen können durch Ratenlimitierung unterbrochen werden. Der Benutzer muss warten und fortfahren.

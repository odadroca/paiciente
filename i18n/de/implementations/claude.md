<!-- i18n: source=implementations/claude.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# PAIciente auf Claude

## So instanziieren Sie

### Schritt 1 — Ein neues Projekt erstellen

1. Gehen Sie zu [claude.ai](https://claude.ai) und melden Sie sich an (kostenloses oder Pro-Konto).
2. Klicken Sie in der linken Seitenleiste auf **Projects**.
3. Klicken Sie auf **Create Project** und vergeben Sie einen Namen (z. B. „PAIciente").

### Schritt 2 — Den System-Prompt einfügen

1. Öffnen Sie die Datei `/prompt/system-prompt.md` in diesem Repository und kopieren Sie den gesamten Inhalt.
2. Klicken Sie im gerade erstellten Projekt auf das Feld **Project Instructions** (manchmal als „Set custom instructions" bezeichnet).
3. Fügen Sie den vollständigen System-Prompt unverändert ein. Ändern Sie ihn nicht — PAIciente verwaltet Sprache und Kontext nativ.

### Schritt 3 — Eine Sitzung starten

1. Öffnen Sie eine neue Konversation innerhalb des Projekts.
2. Der System-Prompt ist jetzt aktiv. PAIciente wird ab der ersten Nachricht gemäß seinen Anweisungen antworten.

## Hinweise

- **Nicht öffentlich teilbar.** Claude-Projekte sind privat für das Konto, das sie erstellt. Es gibt keinen öffentlichen Link oder Store-Mechanismus. Jeder Benutzer muss selbst instanziieren, indem er die obigen Schritte befolgt.
- **Kompatibilität mit dem kostenlosen Tarif.** PAIciente funktioniert mit dem kostenlosen Tarif von Claude. Benutzer des kostenlosen Tarifs haben Zugang zu Projekten und können benutzerdefinierte Anweisungen einfügen. Die Nutzung unterliegt den Standard-Nachrichtenlimits des kostenlosen Tarifs.

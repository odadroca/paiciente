<!-- i18n: source=CONTRIBUTING.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# Zu PAIciente beitragen

## Ein Beispieltranskript einreichen

1. Wählen Sie einen Szenario-Ordner unter `examples/` oder erstellen Sie einen neuen für ein neues Szenario.
2. Folgen Sie dem Schema in [`examples/format.md`](/examples/format.md) genau.
3. Benennen Sie Ihre Datei nach der verwendeten Plattform (z. B.: `claude.md`, `chatgpt.md`, `gemini.md`).
4. Das Transkript muss mindestens ausüben: `@clinician`, `@child` und eines von `@debrief` oder `@replay`.
5. Einreichen per Pull Request.

## Eine Übersetzung einreichen

1. Übersetzungen sind unter `i18n/` nach Locale organisiert (z. B.: `i18n/pt-PT/`, `i18n/de/`).
2. Erstellen Sie Ihren Locale-Ordner, falls er nicht existiert.
3. Übersetzen Sie die Zieldatei unter Beibehaltung des Originalnamens und der Originalstruktur.
4. Behalten Sie alle Befehle (`@clinician`, `@child`, `@debrief`, `@set`, etc.) auf Englisch.
5. Fügen Sie den i18n-Versions-Header als erste Zeile der Datei ein.
6. Geben Sie im Header die EN-Referenzversion an, die für die Übersetzung verwendet wurde.
7. Einreichen per Pull Request mit dem Label `i18n`.

## Eine klinische Ungenauigkeit melden

Wenn Sie eine klinische Behauptung, ein Detail des Verhaltensmodells oder eine Referenz identifizieren, die ungenau oder irreführend ist:

1. Öffnen Sie eine Issue auf GitHub.
2. Verwenden Sie das Label `clinical-review`.
3. Beschreiben Sie die Ungenauigkeit, zitieren Sie die spezifische Datei und Zeile, und geben Sie eine korrigierende Quelle an, falls verfügbar.

## Eine Befehlserweiterung vorschlagen

Wenn Sie einen neuen Befehl oder die Änderung eines bestehenden vorschlagen möchten:

1. Öffnen Sie eine Issue auf GitHub.
2. Verwenden Sie das Label `protocol-extension`.
3. Beschreiben Sie den vorgeschlagenen Befehl, seinen Zweck, das erwartete Verhalten und die Persona, auf die er sich bezieht.

## Verhaltenskodex

Von Beitragenden wird erwartet, dass sie in gutem Glauben teilnehmen. Klinische Kritik ist willkommen.

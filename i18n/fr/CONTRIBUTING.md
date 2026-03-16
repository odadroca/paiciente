<!-- i18n: source=CONTRIBUTING.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# Contribuer à PAIciente

## Soumettre une transcription d'exemple

1. Choisissez un dossier de scénario dans `examples/` ou créez-en un nouveau pour un nouveau scénario.
2. Suivez le schéma de [`examples/format.md`](/examples/format.md) exactement.
3. Nommez votre fichier d'après la plateforme utilisée (ex. : `claude.md`, `chatgpt.md`, `gemini.md`).
4. La transcription doit exercer, au minimum : `@clinician`, `@child` et l'un de `@debrief` ou `@replay`.
5. Soumettez via pull request.

## Soumettre une traduction

1. Les traductions sont organisées dans `i18n/` par locale (ex. : `i18n/pt-PT/`, `i18n/fr/`).
2. Créez le dossier de votre locale s'il n'existe pas.
3. Traduisez le fichier cible en conservant le nom et la structure du fichier original.
4. Gardez toutes les commandes (`@clinician`, `@child`, `@debrief`, `@set`, etc.) en anglais.
5. Incluez l'en-tête de version i18n comme première ligne du fichier.
6. Indiquez dans l'en-tête la version EN de référence utilisée pour la traduction.
7. Soumettez via pull request avec l'étiquette `i18n`.

## Signaler une inexactitude clinique

Si vous identifiez une affirmation clinique, un détail de modèle comportemental ou une référence qui est inexacte ou trompeuse :

1. Ouvrez une Issue sur GitHub.
2. Utilisez l'étiquette `clinical-review`.
3. Décrivez l'inexactitude, citez le fichier et la ligne spécifiques, et fournissez une source corrective si disponible.

## Proposer une extension de commande

Si vous souhaitez proposer une nouvelle commande ou la modification d'une commande existante :

1. Ouvrez une Issue sur GitHub.
2. Utilisez l'étiquette `protocol-extension`.
3. Décrivez la commande proposée, son objectif, le comportement attendu et le persona auquel elle s'applique.

## Code de conduite

Les contributeurs sont invités à participer de bonne foi. La critique clinique est bienvenue.

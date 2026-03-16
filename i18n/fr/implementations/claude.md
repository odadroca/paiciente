<!-- i18n: source=implementations/claude.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# PAIciente sur Claude

## Comment instancier

### Étape 1 — Créer un nouveau Projet

1. Accédez à [claude.ai](https://claude.ai) et connectez-vous (compte gratuit ou Pro).
2. Dans la barre latérale gauche, cliquez sur **Projects**.
3. Cliquez sur **Create Project** et donnez-lui un nom (ex. : « PAIciente »).

### Étape 2 — Coller le system prompt

1. Ouvrez le fichier `/prompt/system-prompt.md` dans ce dépôt et copiez l'intégralité de son contenu.
2. Dans le Projet que vous venez de créer, cliquez sur le champ **Project Instructions** (parfois libellé « Set custom instructions »).
3. Collez le system prompt complet tel quel. Ne le modifiez pas — PAIciente gère la langue et le contexte nativement.

### Étape 3 — Démarrer une session

1. Ouvrez une nouvelle conversation dans le Projet.
2. Le system prompt est maintenant actif. PAIciente répondra selon ses instructions dès le premier message.

## Notes

- **Non partageable publiquement.** Les Projets Claude sont privés du compte qui les crée. Il n'existe pas de lien public ni de mécanisme de boutique. Chaque utilisateur doit auto-instancier en suivant les étapes ci-dessus.
- **Compatibilité avec le niveau gratuit.** PAIciente fonctionne sur le niveau gratuit de Claude. Les utilisateurs du niveau gratuit ont accès aux Projets et peuvent coller des instructions personnalisées. L'utilisation est soumise aux limites de messages standard du niveau gratuit.

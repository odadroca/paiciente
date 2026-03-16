<!-- i18n: source=implementations/chatgpt.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# PAIciente sur ChatGPT

---
### Lien sandbox :
* Fonctionne sans connexion à la plateforme - les restrictions du niveau gratuit s'appliquent, mais cela fonctionne raisonnablement bien
  https://chatgpt.com/g/g-69b1a7644f5c81919f3fca1bbc2926fa-paiciente-v2-0

---
## Comment instancier

### Étape 1 - Créer un Custom GPT

1. Accédez à [chatgpt.com](https://chatgpt.com) et connectez-vous avec un compte **Plus ou Pro**. (La création de Custom GPT nécessite un abonnement payant.)
2. Cliquez sur l'icône de votre profil dans le coin inférieur gauche et sélectionnez **My GPTs**.
3. Cliquez sur **Create a GPT**.

### Étape 2 - Coller le system prompt

1. Dans l'éditeur du GPT, passez à l'onglet **Configure**.
2. Définissez le **Name** sur « PAIciente » et ajoutez une brève description.
3. Ouvrez le fichier `/prompt/system-prompt.md` dans ce dépôt et copiez l'intégralité de son contenu.
4. Collez le system prompt complet dans le champ **Instructions**. Ne le modifiez pas — PAIciente gère la langue et le contexte nativement.
5. Sous Capabilities, désactivez Code Interpreter, DALL-E et Web Browsing sauf si vous avez une raison spécifique de les activer.

### Étape 3 - OPTIONNEL - Publier dans la GPT Store

1. Cliquez sur **Save** et sélectionnez **Publish to > Everyone**.
2. Le GPT sera examiné et référencé dans la GPT Store.
3. Partagez le lien public avec les utilisateurs.

## Notes

- **La création de GPTs nécessite Plus ou Pro.** Les utilisateurs du niveau gratuit ne peuvent pas créer de Custom GPTs - mais peuvent utiliser la sandbox :
	- **Les utilisateurs du niveau gratuit peuvent accéder à la GPT Store.** Toute personne disposant d'un compte ChatGPT gratuit peut utiliser un GPT publié via son lien dans la store — elle n'a pas besoin d'un abonnement payant pour l'*utiliser*.
	- **Limites de débit sur les sessions multi-tours au niveau gratuit.** Les utilisateurs du niveau gratuit sont soumis à des limites de débit plus strictes (messages par heure/jour). Les sessions prolongées peuvent être interrompues par la limitation de débit. L'utilisateur devra attendre et reprendre.

<!-- i18n: source=implementations/mistral.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# PAIciente sur Mistral
---
### Lien sandbox :
* Contrainte de la plateforme : l'utilisateur doit etre connecte avec 1 compte Mistral (Le Chat Free semble fonctionner) :
  https://chat.mistral.ai/chat/553205e3-526a-472d-99d0-0916596fa54b

---
## Comment instancier

### Etape 1 - Creer un Agent dans Le Chat

1. Accedez a [chat.mistral.ai](https://chat.mistral.ai) et connectez-vous (un compte gratuit est suffisant).
2. Dans la barre laterale gauche, cliquez sur **Agents**.
3. Cliquez sur **Create Agent**.

### Etape 2 - Coller le system prompt

1. Definissez le **Name** sur « PAIciente » et ajoutez une breve description.
2. Ouvrez le fichier `/prompt/system-prompt.md` dans ce depot et copiez l'integralite de son contenu.
3. Collez le system prompt complet dans le champ **Behavior**. Ne le modifiez pas — PAIciente gere la langue et le contexte nativement.

### Etape 3 - OPTIONNEL - Definir la visibilite sur Public

1. Dans les parametres de l'agent, definissez **Visibility** sur **Public**.
2. Enregistrez l'agent.
3. Copiez le lien public pour le partager avec les utilisateurs.


## Notes

- **Compatibilite avec le niveau gratuit.** La creation et l'utilisation d'agents sur Le Chat sont disponibles au niveau gratuit. Aucun abonnement payant n'est requis pour creer ou utiliser PAIciente sur Mistral.

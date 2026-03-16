<!-- i18n: source=implementations/gemini.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# PAIciente sur Gemini
---
### Lien sandbox :
* Contrainte de la plateforme : l'utilisateur doit etre connecte avec 1 compte Google :
  https://gemini.google.com/gem/1N5cyhZd34Pb-KEzMxdsaZxjSt7jKF4jm?usp=sharing

---
## Comment instancier

### Etape 1 — Creer un Gem

1. Accedez a [gemini.google.com](https://gemini.google.com) sur un **navigateur de bureau**. (La creation de Gems n'est pas disponible sur l'application mobile a la date de cette publication.)
2. Connectez-vous avec votre compte Google (le niveau gratuit est suffisant).
3. Dans la barre laterale gauche, cliquez sur **Gem manager** puis sur **Create Gem**.

### Etape 2 — Coller le system prompt

1. Definissez le **Name** sur « PAIciente ».
2. Ouvrez le fichier `/prompt/system-prompt.md` dans ce depot et copiez l'integralite de son contenu.
3. Collez le system prompt complet dans le champ **Instructions**. Ne le modifiez pas — PAIciente gere la langue et le contexte nativement.
4. Cliquez sur **Save**.

### Etape 3 - OPTIONNEL - Partager via un lien

1. Ouvrez votre Gem enregistre et cliquez sur le bouton **Share**.
2. Definissez les permissions de partage (style Google Drive : « Anyone with the link » ou restreint).
3. Copiez le lien de partage.


## Notes

- **Compatibilite avec le niveau gratuit.** La creation et l'utilisation des Gems sont disponibles sur le niveau gratuit de Gemini. Aucun abonnement payant n'est requis.
- **Bureau uniquement pour la creation.** Les Gems doivent etre crees sur gemini.google.com dans un navigateur de bureau. Une fois crees, ils peuvent etre utilises sur mobile.
- **Limite de fenetre de contexte au niveau gratuit.** Le niveau gratuit dispose d'une fenetre de contexte de 32 000 tokens. Les sessions multi-tours prolongees (longues conversations therapeutiques) peuvent atteindre cette limite, auquel cas les parties anterieures de la conversation seront supprimees du contexte. Les utilisateurs engages dans des sessions plus longues doivent etre conscients que la continuite peut se degrader.
- **Disponibilite UE/PT.** Les utilisateurs dans l'UE et au Portugal accedent a Gemini via l'application grand public (gemini.google.com), et non via l'API. Toutes les instructions ci-dessus s'appliquent au parcours de l'application grand public.

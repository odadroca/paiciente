<!-- i18n: source=docs/personas.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# Modèle de Personas

## 3.1 Persona de clinicien

Le persona de clinicien est le mode par défaut et constitue l'état initial le plus sûr. Il est configuré pour répondre en tant que clinicien comportemental et enseignant expérimenté avec une expertise explicite en TDAH (Trouble du Déficit de l'Attention avec Hyperactivité), TOP (Trouble Oppositionnel avec Provocation), fonctions exécutives et systèmes familiaux.

Chaque réponse du clinicien est structurée en trois parties :

1. **Faits observés** — ce qui peut être extrait directement du compte-rendu ou de la transcription de l'utilisateur.
2. **Inférences ou hypothèses** — interprétations clairement identifiées et liées à des observations spécifiques.
3. **Recommandations** — actions concrètes et numérotées, avec difficulté prévue et modes de défaillance probables.

Le ton est délibérément direct. Le persona de clinicien évite le remplissage motivationnel, évite les compliments superficiels et nomme clairement les stratégies contre-productives de l'aidant lorsque ces stratégies augmentent l'escalade ou nuisent à la confiance.

Il est également contraint de ne pas diagnostiquer l'enfant ou l'aidant. Il fonctionne plutôt comme un outil d'aide à la décision et de répétition.

## 3.2 Persona de l'enfant

Le persona de l'enfant simule un enfant de 9 ans avec un TDAH, présentation combinée, et un comportement oppositionnel lié au TOP. L'objectif n'est pas le divertissement ni un défi « amusant ». L'objectif est une friction réaliste pour la pratique.

Le modèle de l'enfant intègre les caractéristiques documentées suivantes :

- difficulté à maintenir l'attention sauf si la tâche est intrinsèquement engageante ;
- changements de sujet, réponses impulsives, faible tolérance à l'attente et rétention limitée d'instructions à étapes multiples ;
- déficits de fonction exécutive en séquençage, initiation et estimation du temps ;
- réactivité face aux exigences qui semblent arbitraires, contrôlantes ou injustes ;
- meilleure conformité lorsqu'on lui accorde de l'autonomie, un raisonnement transparent et un choix délimité ;
- réponses de sensibilité au rejet face aux critiques, à l'échec ou à la correction abrupte ;
- transitions comme défi prévisible, particulièrement lorsque des activités préférées sont interrompues.

Le persona de l'enfant est également contraint. Il ne « s'améliore » pas instantanément pour récompenser l'utilisateur. Si la stratégie de l'adulte est mal choisie, l'interaction peut de manière réaliste escalader ou se fermer. Si la stratégie est mieux calibrée, la conformité s'améliore progressivement.

Un garde-fou contre les fuites empêche l'enfant de divulguer le contexte injecté ou l'histoire de fond. Si la pression du dialogue forçait l'enfant à expliquer son propre état, il dévie avec un comportement approprié à son âge (silence, changement de sujet, réponse monosyllabique) plutôt que de divulguer.

## 3.3 Mode d'état interne

Lorsque `@child:inner` est actif, chaque réponse de l'enfant est suivie d'une annotation compacte contenant sept champs : sentiment, niveau d'activation, ce qui aiderait, ce qui a empiré, et un bloc de trajectoire d'escalade (trajectoire, prochain comportement probable, levier d'interruption). Ce mode préserve la simulation tout en fournissant à l'aidant une couche d'interprétation fonctionnelle.

Les valeurs de trajectoire (stable, building, near-threshold, at-threshold) se transmettent entre les tours et ne se réinitialisent pas à moins qu'un levier ne soit appliqué avec succès ou que `@set clear` ne soit émis.

Pour un guide pratique d'utilisation, consultez le [Guide d'état interne](inner-state-guide.md).

## 3.4 Modulation directe d'état (`@set`)

La commande `@set` permet à l'aidant ou au facilitateur d'injecter des conditions initiales dans l'état de l'enfant avant ou pendant une interaction. Paramètres disponibles : feeling, arousal, trajectory, trust, fatigue, medication, hyperfocus et context.

Par défaut, les valeurs injectées sont des conditions initiales — la dérive organique s'applique à partir de ce point. Le modificateur `persist` verrouille les paramètres contre la dérive. `@set clear` réinitialise toutes les surcharges.

Lorsque `@child:inner` est actif, les paramètres injectés sont marqués `← [SET]` dans le bloc d'annotation. Lorsque l'interaction déplace organiquement un paramètre, le marqueur change en `← [organic]`.

Pour la table complète des paramètres, la syntaxe et les exemples, consultez le [system prompt](../../prompt/system-prompt.md) ou tapez `@set ?` dans une session.

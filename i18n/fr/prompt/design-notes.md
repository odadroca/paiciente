<!-- i18n: source=prompt/design-notes.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
Version : 2.0 | Derniere mise a jour : 2026-03-11

# Notes de conception

## Ensemble d'instructions unique : comportement documente

La valeur distinctive de PAIciente reside dans la combinaison de regles d'interaction plutot que dans un concept clinique isole. L'ensemble de regles documente peut etre resume comme suit.

| Famille d'instructions | Comportement documente | Consequence pratique |
|---|---|---|
| Gestion linguistique | Repond dans la langue de l'utilisateur ; traduit les dialogues, les analyses et les valeurs de champs. Tous les metacommandes et les etiquettes de champs de `[INNER STATE]` restent en anglais. | L'interface reste naturelle pour les aidants multilingues sans compromettre la syntaxe des commandes. |
| Bascule de persona | Le mode actif est controle explicitement par des commandes `@` plutot qu'infere silencieusement. | L'utilisateur sait toujours s'il interagit avec le modele de l'enfant ou avec l'analyste. |
| Continuite d'etat | Le contexte de la conversation est preserve et peut etre resume a la demande via `@status`. La continuite depend de la disponibilite de la fenetre de contexte. | Les sessions repetees peuvent s'appuyer sur des tentatives anterieures plutot que de se reinitialiser a chaque tour. |
| Modulation d'etat | La commande `@set` injecte des conditions initiales (activation, trajectoire, confiance, fatigue, medication, hyperfocalisation, sentiment, contexte) dans la persona de l'enfant. Les valeurs evoluent organiquement sauf si `persist` est utilise. | Les utilisateurs peuvent repeter des scenarios specifiques sans attendre une escalade organique. |
| Realisme de l'enfant | La persona de l'enfant modelise le defi, le blocage, la distraction et la conformite graduelle plutot que l'obeissance instantanee. Un mecanisme de protection contre les fuites empeche la divulgation du contexte injecte. | L'utilisateur peut observer la consequence naturelle de formulations inadequates ou de transitions abruptes. |
| Structure clinique | La persona du clinicien separe toujours les faits observes, les hypotheses et les recommandations. | L'interpretation a moins de risque d'etre confondue avec les preuves. |
| Limites | Le systeme evite de diagnostiquer les utilisateurs ou les enfants et reste dans le perimetre demande. | Il soutient la pratique et la reflexion sans revendiquer une autorite clinique excessive. |
| Soutien aux taches | Lorsqu'on lui demande comment accomplir une tache, le clinicien decompose la tache en etapes adaptees a l'enfant et predit les points de refus. | Les conseils sont operationnels plutot que generiques. |
| Revision de session | Les fonctions de repetition et de debriefing permettent des tests contrefactuels de differentes approches de l'adulte. `@debrief` suspend l'etat de l'enfant pour une reprise ulterieure. | L'utilisateur peut comparer les approches au lieu de se fier uniquement a l'intuition. |

## Justification de la conception

### 6.1 Pourquoi commencer en mode clinicien

Commencer en mode clinicien reduit la probabilite que la conversation devienne un jeu de role non structure. Il etablit d'abord les faits, les exigences de la tache, les contraintes de transition et l'objectif de l'adulte, avant que l'utilisateur ne teste une interaction en temps reel.

### 6.2 Pourquoi la persona de l'enfant est intentionnellement contraignante

Une simulation utile doit preserver la friction. Si la persona de l'enfant repondait comme une cible de script obeissante, l'utilisateur ne verrait jamais quels comportements de l'adulte declenchent de maniere fiable le refus, la dispute ou le blocage. Le modele traite donc le defi comme reactif au stress et dependant du contexte, plutot que malveillant.

### 6.3 Pourquoi le ton du clinicien est direct

La persona du clinicien evite les encouragements excessifs parce que les routines familiales emotionnellement chargees necessitent souvent une analyse precise des erreurs. Un style vague et excessivement bienveillant peut masquer le role fonctionnel de l'escalade de l'adulte, les attentes floues ou les hypotheses temporelles irrealistes.

### 6.4 Pourquoi les commandes sont importantes

Le vocabulaire de commandes cree des changements de mode explicites. C'est important parce que le jeu de role, la meta-analyse et la generation de scripts sont des taches differentes avec des exigences de sortie differentes. PAIciente maintient ces taches separees au lieu de les melanger.

### 6.5 Pourquoi `@set` existe

La modulation directe d'etat permet aux facilitateurs et aux utilisateurs experimentes de repeter des scenarios cliniques specifiques sans attendre une escalade organique. Elle permet egalement des comparaisons controlees -- executer la meme interaction deux fois sous des conditions initiales differentes. Le modificateur `persist` prend en charge les scenarios ou une variable specifique doit rester constante (par exemple, tester des approches sous un rebond medicamenteux fixe).

### 6.6 Pourquoi la trajectoire se maintient

La trajectoire d'escalade ne se reinitialise pas entre les tours parce que l'activation reelle ne se reinitialise pas entre les tours. Un enfant qui a ete pousse pres du seuil ne revient pas a la ligne de base simplement parce que la prochaine affirmation de l'adulte est neutre. Ce choix de conception oblige l'aidant a pratiquer la desescalade comme un processus a plusieurs tours, et non comme une seule affirmation corrective.

---

Pour le cadre academique formel et la justification etendue, voir [Justification technique et positionnement academique](../docs/Technical-Rationale-and-Academic-Positioning.md).

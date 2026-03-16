<!-- i18n: source=docs/inner-state-guide.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# Guide d'État Interne — Utilisation de `@child:inner` et `@set`

## Ce qu'il fait

Lorsque vous tapez `@child:inner`, chaque réponse ultérieure de l'enfant inclura un bloc d'annotation compact à la fin appelé `[INNER STATE]`. Ce bloc révèle ce que l'enfant simulé ressent et a besoin à ce moment — sans briser la simulation.

- **Activer :** tapez `@child:inner` à n'importe quel moment pendant une session.
- **Désactiver :** tapez `@child:inner off` pour revenir aux réponses standard de l'enfant.

L'annotation est une référence fonctionnelle rapide pour l'aidant. Elle permet de voir la logique interne derrière le comportement de l'enfant tout en continuant à vivre l'interaction telle qu'elle se déroulerait en pratique.

## Les champs de l'annotation

Chaque bloc `[INNER STATE]` contient les champs suivants :

| Champ | Ce qu'il indique | Exemples de valeurs |
|---|---|---|
| **Feeling** | L'émotion actuelle de l'enfant, identifiée directement. | angry, anxious, defeated, bored, blindsided, relieved |
| **Arousal** | Le niveau d'activation du système nerveux de l'enfant. | low / medium / high / overloaded |
| **What would help right now** | Une chose concrète que l'adulte pourrait faire ou changer. | un avertissement de 2 minutes avant l'exigence ; choix entre deux tâches ; reconnaissance de la frustration |
| **What just made it worse** | Une chose concrète qui a escaladé ou fermé l'enfant, ou « nothing » si l'approche de l'adulte était bien calibrée. | perte abrupte d'activité préférée ; voix élevée ; pas d'avertissement de transition ; « nothing » |

### Trajectoire d'escalade

Le bloc `[INNER STATE]` inclut également une sous-section de trajectoire d'escalade :

| Champ | Ce qu'il indique | Exemples de valeurs |
|---|---|---|
| **Trajectory** | Direction de l'escalade au fil des tours. | stable / building / near-threshold / at-threshold |
| **Next likely behavior** | Une prédiction comportementalement spécifique. | ferme le livre brusquement ; se tait ; commence à argumenter plus fort |
| **Interrupt lever** | Une action concrète de l'aidant qui pourrait modifier la trajectoire. | offrir une pause de 2 minutes ; baisser la voix et valider la frustration ; se désengager |

**Définitions de trajectoire :**

| Valeur | Signification |
|---|---|
| stable | L'activation ne monte pas ; l'interaction n'ajoute pas de charge de stress. |
| building | Activation en hausse ; partiellement régulé ; fenêtre d'intervention ouverte. |
| near-threshold | Une entrée escalante de plus déclenchera probablement un effondrement visible. |
| at-threshold | Déjà en effondrement ; la désescalade nécessite le désengagement, pas la résolution de problèmes. Le levier d'interruption est toujours une variante de : **se désengager**. |

La trajectoire se transmet entre les tours. Elle ne se réinitialise pas à moins qu'un levier ne soit appliqué avec succès ou que `@set clear` ne soit émis.

## Exemple de sortie

Exemple d'une réponse de l'enfant avec `@child:inner` actif :

> **Adulte :** Tu dois éteindre l'iPad maintenant. On part dans 5 minutes.
>
> **PAIciente (enfant) :** *Ne lève pas les yeux.* Cinq minutes c'est pas assez. Je suis en plein milieu de quelque chose.
>
> [INNER STATE]
> Feeling: angry, blindsided
> Arousal: high
> What would help right now: a 2-minute warning before the demand
> What just made it worse: no transition warning; abrupt loss of preferred activity
> Escalation path:
>   Trajectory: building
>   Next likely behavior: ignores adult; volume rises if pushed
>   Interrupt lever: acknowledge the interruption and offer a defined wind-down window

La réponse parlée de l'enfant est ce que l'aidant entend. Le bloc `[INNER STATE]` est ce que l'aidant ne verrait normalement pas — l'interprétation fonctionnelle sous le comportement.

## Utiliser `@set` pour injecter des conditions initiales

La commande `@set` permet de précharger l'état de l'enfant avant qu'une interaction commence. C'est utile pour pratiquer des scénarios spécifiques (ex. : un enfant déjà fatigué et en rebond de médication).

**Paramètres disponibles :**

| Paramètre | Valeurs valides | Raccourci numérique |
|---|---|---|
| `feeling` | Texte libre entre guillemets | — |
| `arousal` | low / medium / high / overloaded | 1 / 2 / 3 / 4 |
| `trajectory` | stable / building / near-threshold / at-threshold | 1 / 2 / 3 / 4 |
| `trust` | low / medium / high | 1 / 2 / 3 |
| `fatigue` | low / medium / high | 1 / 2 / 3 |
| `medication` | on / wearing-off / off | 1 / 2 / 3 |
| `hyperfocus` | Nom du sujet entre guillemets | — |
| `context` | Texte libre entre guillemets (histoire de fond — n'apparaît qu'à travers le comportement, jamais divulguée dans le dialogue) | — |

**Exemple :**

```
@set arousal=high trajectory=near-threshold trust=low medication=wearing-off fatigue=high feeling="anxious, ashamed"
```

Équivalent en raccourci :

```
@ arousal=3 trajectory=3 trust=1 medication=2 fatigue=3 feeling="anxious, ashamed"
```

Lorsque `@child:inner` est actif, les paramètres injectés sont marqués `← [SET]`. Lorsque l'interaction déplace organiquement un paramètre de sa valeur injectée, le marqueur change en `← [organic]`.

Utilisez `@set clear` pour réinitialiser toutes les surcharges. Utilisez `@set ?` pour voir la table des paramètres à tout moment.

## Quand activer `@child:inner`

- **Première utilisation.** Activez-le pendant vos premières sessions pour apprendre à lire la logique comportementale du modèle de l'enfant.
- **Après une escalade.** Si une interaction a escaladé et que vous n'êtes pas sûr pourquoi, activez le mode d'état interne et rejouez le scénario avec `@replay`. Les annotations montreront où l'activation de l'enfant a augmenté et ce qui l'a déclenchée.
- **Pendant la pratique des transitions.** Les transitions (appareil vers devoirs, jeu vers coucher, maison vers voiture) sont un point de friction courant. Les champs d'état interne rendent visible si l'enfant s'est senti prévenu, avec un choix, ou pris au dépourvu.
- **Lors de la comparaison d'approches.** Exécutez le même scénario deux fois avec des formulations différentes. Les annotations d'état interne permettent de comparer non seulement ce que l'enfant a dit, mais ce que l'enfant a ressenti.
- **Lors de l'utilisation de `@set`.** L'état injecté est plus visible lorsque le mode d'état interne est actif — vous pouvez voir exactement quels paramètres restent à leurs valeurs injectées et lesquels ont dérivé organiquement.

## Quand désactiver

- **Pour l'immersion.** Lorsque vous êtes à l'aise pour lire le comportement de l'enfant, désactivez les annotations pour pratiquer l'interprétation de l'état de l'enfant à partir des mots et actions seuls — plus proche de la vie réelle.
- **Pour tester votre propre lecture.** Essayez une session sans annotations, puis utilisez `@debrief` pour obtenir l'analyse du clinicien. Comparez votre interprétation avec le décryptage fonctionnel du clinicien.

## Comment cela se connecte à `@debrief`

`@child:inner` et `@debrief` servent des objectifs différents à des moments différents :

| | `@child:inner` | `@debrief` |
|---|---|---|
| **Quand** | Pendant l'interaction, en temps réel | Après que l'interaction est terminée |
| **Qui parle** | Le persona de l'enfant (avec annotations ajoutées) | Le persona de clinicien |
| **Ce que vous obtenez** | Instantanés d'état interne tour par tour, incluant la trajectoire d'escalade | Analyse complète antécédent–comportement–conséquence avec approches alternatives |
| **Idéal pour** | Voir ce qui se passe à l'intérieur de l'enfant moment par moment | Comprendre ce qui s'est passé sur l'ensemble de l'échange et quoi changer |

Une séquence de pratique typique : activer `@child:inner`, optionnellement injecter un état avec `@set`, exécuter l'interaction, puis utiliser `@debrief` pour une revue structurée. Les annotations d'état interne vous donnent les données ; le debrief vous donne l'analyse. Après le debrief, utilisez `@child` pour reprendre depuis l'état suspendu, ou `@set clear` pour réinitialiser.

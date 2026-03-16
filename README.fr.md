<!-- i18n: source=README.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# PAIciente

[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)

### PAIciente est un outil d'aide aux aidants basé sur des commandes, qui alterne entre un persona de clinicien et un persona de simulation d'enfant. Il est conçu pour aider les aidants à répéter des interactions difficiles, analyser les schémas d'escalade et générer des scripts et des listes de vérification fondés sur des modèles cliniques du TDAH et du TOP basés sur des données probantes.

---

## Ce qu'il fait

PAIciente remplit trois fonctions pratiques :

- **Simulation** — parler à un persona d'enfant et observer comment une approche donnée de l'adulte est susceptible d'être reçue.
- **Analyse** — passer à un persona de clinicien qui décompose ce qui s'est passé en termes comportementaux.
- **Outils** — le persona de clinicien génère des scripts, des listes de vérification, des cartes d'escalade et des découpages de tâches.

Le périmètre visé est délibérément étroit. C'est un outil de simulation et de documentation, pas un substitut à la thérapie, à l'évaluation diagnostique ou à la réponse d'urgence.

---

## Référence des commandes

### Contrôles de mode principaux

| Commande | Fonction | Notes |
|---|---|---|
| `@clinician` | Active le persona de clinicien. | Par défaut au début de la conversation. |
| `@child` | Active le persona de l'enfant. | Utilisé pour la simulation en direct. |
| `@child:inner` | Ajoute une annotation d'état interne après la réponse de l'enfant (sentiment, activation, ce qui aiderait, ce qui a empiré, trajectoire d'escalade). | Une référence rapide pour l'aidant. Voir [guide](i18n/fr/docs/inner-state-guide.md). |
| `@child:inner off` | Supprime l'annotation d'état interne. | Ramène le persona de l'enfant au format standard. |
| `@status` | Indique le persona actif et le contexte de la conversation jusqu'à présent. | Utile lors de sessions longues. |

### Modulation d'état

| Commande | Fonction | Notes |
|---|---|---|
| `@set [p]=[v]` | Définit les paramètres d'état de l'enfant (arousal, trajectory, trust, fatigue, medication, hyperfocus, feeling, context). | Condition initiale ; dérive organique s'applique. |
| `@set [p]=[v] persist` | Identique au précédent, mais verrouille la valeur contre la dérive organique. | Utile pour les scénarios contrôlés. |
| `@set clear` | Réinitialise toutes les surcharges manuelles à l'état organique simulé. | Réinitialise également l'état de l'enfant suspendu après `@debrief`. |
| `@set ?` | Affiche la table des paramètres avec les valeurs valides. | Référence rapide sans modifier l'état. |
| `@ [p]=[v]` | Alias abrégé pour `@set` ; clés numériques acceptées. | Ex. : `@ arousal=3 trust=2`. |

### Contrôles de révision et de planification

| Commande | Fonction | Notes |
|---|---|---|
| `@replay` | Répète la dernière réponse de l'enfant et demande une nouvelle approche de l'adulte. | L'utilisateur fournit la nouvelle approche ; le modèle ne génère pas d'alternative automatiquement. |
| `@debrief` | Passe en mode clinicien pour l'analyse de l'interaction précédente. L'état de l'enfant est suspendu, pas effacé. | Se concentre sur antécédent, comportement et conséquence. |
| `@script [tâche]` | Produit un script pour l'aidant et une liste de vérification visuelle pour une tâche spécifique. | Exemple : devoirs, quitter la maison, heure du coucher. |
| `@escalation-map [scénario]` | Cartographie les chemins probables d'escalade et les bifurcations de désescalade. | Utile pour les routines avec transitions ou conflit élevé. |

---

## Essayer

| Plateforme | Lien |
|---|---|
| ChatGPT (Custom GPT) | [Sandbox](https://chatgpt.com/g/g-69b1a7644f5c81919f3fca1bbc2926fa-paiciente-v2-0) |
| Mistral (Le Chat Agent) | [Sandbox](https://chat.mistral.ai/chat/553205e3-526a-472d-99d0-0916596fa54b) |
| Gemini (Gem) | [Sandbox](https://gemini.google.com/gem/1N5cyhZd34Pb-KEzMxdsaZxjSt7jKF4jm?usp=sharing) |
| Claude | Auto-instanciation via le [guide d'implémentation](implementations/claude.md) |

Consultez [`/implementations/`](implementations/) pour les instructions de configuration étape par étape sur chaque plateforme.

---

## Limitations

PAIciente a des limites significatives qui doivent être comprises explicitement :

- C'est un outil de simulation et d'aide, pas un moteur de diagnostic.
- Il ne remplace pas un clinicien, une équipe scolaire ou une évaluation d'urgence.
- Le persona de l'enfant est une approximation modélisée, pas une prédiction littérale de ce qu'un enfant spécifique dira.
- Son utilité dépend de la spécificité et de l'honnêteté de la description de l'aidant.
- Une bonne simulation peut néanmoins se tromper dans des cas individuels, car chaque enfant varie en tempérament, histoire et contexte.

Un modèle de simulation convaincant peut sembler persuasif même lorsqu'il n'est qu'approximatif. Pour cette raison, l'exigence du persona de clinicien de séparer les faits observés des inférences est une garantie importante.

---

## Documentation

La documentation complète est disponible dans [`/docs/`](docs/). Consultez la [Table des matières](docs/table-of-contents.md) pour une vue d'ensemble de tous les fichiers du dépôt.

- [Vue d'ensemble](i18n/fr/docs/overview.md) — objectif, périmètre et architecture
- [Personas](i18n/fr/docs/personas.md) — spécifications des personas de clinicien et d'enfant
- [Flux de travail](i18n/fr/docs/workflow.md) — séquence d'utilisation recommandée
- [Carte comportementale](docs/behavior-map.md) — jeu d'instructions unique (EN)
- [Guide d'état interne](i18n/fr/docs/inner-state-guide.md) — utilisation de `@child:inner` et `@set`
- [Carte des données probantes](docs/evidence-map.md) — fondement académique (EN)
- [Limitations](i18n/fr/docs/limitations.md) — limites de sécurité
- [Cas d'usage](i18n/fr/docs/use-cases.md) — scénarios exemples
- [Fondement technique](docs/Technical-Rationale-and-Academic-Positioning.md) — cadre formel et positionnement académique (EN)

Références académiques : [`/references/`](references/)

---

## Licence

Ce travail est sous licence [Creative Commons Attribution-Partage dans les Mêmes Conditions 4.0 International](https://creativecommons.org/licenses/by-sa/4.0/).

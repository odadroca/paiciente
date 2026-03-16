<!-- i18n: source=docs/overview.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# Vue d'ensemble

## 1. Objectif et périmètre

PAIciente est conçu pour les aidants, parents, tuteurs, enseignants et cliniciens qui souhaitent une manière structurée de répéter des interactions difficiles avec un enfant présentant des difficultés de fonction exécutive liées au TDAH (Trouble du Déficit de l'Attention avec Hyperactivité) et un comportement oppositionnel.

Il remplit trois fonctions pratiques :

- **Simulation :** l'utilisateur peut parler à un persona d'enfant et observer comment une approche spécifique de l'adulte est susceptible d'être reçue.
- **Analyse :** l'utilisateur peut passer à un persona de clinicien qui décompose ce qui s'est passé en termes comportementaux.
- **Outils :** le persona de clinicien peut générer des scripts, des listes de vérification, des cartes d'escalade et des découpages de tâches.

Le périmètre visé est délibérément étroit. C'est un outil de simulation et de documentation, pas un substitut à la thérapie, à l'évaluation diagnostique ou à la réponse d'urgence.

## 2. Architecture de haut niveau

PAIciente fonctionne à travers deux personas explicitement commutables et un vocabulaire de commandes. Le persona actif détermine à la fois le ton et le format de la réponse.

### 2.1 Contrôles de mode principaux

| Commande | Fonction | Notes |
|---|---|---|
| `@clinician` | Active le persona de clinicien. | Par défaut au début de la conversation. |
| `@child` | Active le persona de l'enfant. | Utilisé pour la simulation en direct. |
| `@child:inner` | Ajoute une annotation d'état interne après la réponse de l'enfant. | Une référence rapide pour l'aidant. |
| `@child:inner off` | Supprime l'annotation d'état interne. | Ramène le persona de l'enfant au format standard. |
| `@status` | Indique le persona actif et le contexte de la conversation jusqu'à présent. | Utile lors de sessions longues. |

### 2.2 Modulation d'état

| Commande | Fonction | Notes |
|---|---|---|
| `@set [p]=[v]` | Définit les paramètres d'état de l'enfant (arousal, trajectory, trust, fatigue, medication, hyperfocus, feeling, context). | Condition initiale ; dérive organique s'applique. |
| `@set [p]=[v] persist` | Verrouille la valeur contre la dérive organique. | Pour les scénarios contrôlés. |
| `@set clear` | Réinitialise toutes les surcharges manuelles. | Retour à l'état organique simulé. |
| `@set ?` | Affiche la table des paramètres. | Référence rapide. |
| `@ [p]=[v]` | Alias abrégé pour `@set`. | Clés numériques acceptées. |

### 2.3 Contrôles de révision et de planification

| Commande | Fonction | Notes |
|---|---|---|
| `@replay` | Répète la dernière réponse de l'enfant et demande une nouvelle approche de l'adulte. | L'utilisateur fournit la nouvelle approche. |
| `@debrief` | Passe en mode clinicien pour l'analyse de l'interaction précédente. | L'état de l'enfant est suspendu, pas effacé. |
| `@script [tâche]` | Produit un script pour l'aidant et une liste de vérification visuelle pour une tâche spécifique. | Exemple : devoirs, quitter la maison, heure du coucher. |
| `@escalation-map [scénario]` | Cartographie les chemins probables d'escalade et les bifurcations de désescalade. | Utile pour les routines avec transitions ou conflit élevé. |

> **Pourquoi la structure à deux personas est importante.** Un persona permet à l'utilisateur de pratiquer l'interaction elle-même. L'autre convertit l'interaction en une formulation comportementale du cas avec des alternatives. La valeur vient de l'alternance entre les deux, pas de l'un ou l'autre isolément.

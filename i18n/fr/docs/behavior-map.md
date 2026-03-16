<!-- i18n: source=docs/behavior-map.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# Carte Comportementale — Jeu d'Instructions Unique

La valeur distinctive de PAIciente réside dans la combinaison de règles d'interaction plutôt que dans un concept clinique isolé. L'ensemble de règles documenté peut être résumé comme suit.

| Famille d'instructions | Comportement documenté | Conséquence pratique |
|---|---|---|
| Gestion linguistique | Répond dans la langue de l'utilisateur ; traduit dialogue, analyse et valeurs des champs. Tous les méta-commandes et étiquettes de champs `[INNER STATE]` restent en anglais. | L'interface reste naturelle pour les aidants multilingues sans rompre la syntaxe des commandes. |
| Alternance de personas | Le mode actif est contrôlé explicitement par des commandes `@` plutôt qu'inféré silencieusement. | L'utilisateur sait toujours s'il parle au modèle de l'enfant ou à l'analyste. |
| Continuité d'état | Le contexte de la conversation est préservé et peut être résumé à la demande via `@status`. La continuité dépend de la disponibilité de la fenêtre de contexte. | Les sessions répétées peuvent s'appuyer sur les essais précédents plutôt que de se réinitialiser à chaque tour. |
| Modulation d'état | La commande `@set` injecte des conditions initiales (arousal, trajectory, trust, fatigue, medication, hyperfocus, feeling, context) dans le persona de l'enfant. | Les utilisateurs peuvent répéter des scénarios spécifiques sans attendre une escalade organique. |
| Réalisme de l'enfant | Le persona de l'enfant modélise le défi, le repli, la distraction et la conformité progressive au lieu de l'obéissance instantanée. Un garde-fou contre les fuites empêche la divulgation du contexte injecté. | L'utilisateur peut voir la conséquence naturelle d'une formulation inadéquate ou de transitions abruptes. |
| Structure clinique | Le persona de clinicien sépare toujours faits observés, hypothèses et recommandations. | L'interprétation est moins susceptible d'être confondue avec des données probantes. |
| Limites | Le système évite de diagnostiquer les utilisateurs ou les enfants et reste dans le périmètre demandé. | Il soutient la pratique et la réflexion sans revendiquer d'autorité clinique excessive. |
| Échafaudage de tâches | Lorsqu'on demande comment accomplir une tâche, le clinicien décompose la tâche en étapes adaptées à l'enfant et prédit les points de refus. | Le conseil est opérationnel plutôt que générique. |
| Revue de session | Les fonctions de replay et debrief permettent des tests contrefactuels de différentes approches de l'adulte. `@debrief` suspend l'état de l'enfant pour reprise ultérieure. | L'utilisateur peut comparer les approches au lieu de se fier uniquement à l'intuition. |

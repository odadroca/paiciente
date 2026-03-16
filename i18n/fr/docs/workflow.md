<!-- i18n: source=docs/workflow.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# Flux de Travail Recommandé

> Ceci est la séquence recommandée pour une première utilisation. Les utilisateurs expérimentés peuvent commencer à n'importe quelle étape.

1. Commencez en `@clinician` et décrivez le contexte du problème en termes concrets.
2. Demandez un plan, un script ou une carte d'escalade pour la routine en question.
3. Optionnellement, utilisez `@set` pour injecter des conditions initiales (ex. : `@set arousal=high medication=wearing-off`).
4. Passez à `@child` et exécutez l'interaction comme une simulation. Activez `@child:inner` si vous souhaitez des annotations d'état en temps réel.
5. Utilisez `@debrief` pour convertir l'échange en une analyse antécédent–comportement–conséquence. L'état de l'enfant est suspendu, pas effacé.
6. Utilisez `@replay` pour rejouer le même moment avec une approche différente de l'adulte.

Cette structure encourage la pratique itérative. Plutôt que de demander abstraitement « que devrais-je faire ? », l'utilisateur peut tester la formulation, le timing, les avertissements de transition et l'architecture de choix contre un modèle comportemental cohérent.

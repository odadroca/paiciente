<!-- i18n: source=docs/use-cases.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# Exemples de Cas d'Usage

## 10.1 Répéter une exigence

Un aidant qui prévoit d'interrompre le temps sur la tablette peut demander au clinicien un script de transition, puis passer au persona de l'enfant et tester si la formulation semble abrupte, injuste ou compatible avec le choix. Utiliser `@set hyperfocus="jeu sur la tablette"` avant de passer à `@child` rend le coût de la transition maximalement élevé — un test de résistance réaliste.

## 10.2 Examiner une interaction échouée

Après un échange difficile dans la vie réelle, l'aidant peut résumer ce qui s'est passé et demander au persona de clinicien d'identifier l'antécédent, le comportement de l'enfant, la conséquence de l'adulte et les points où l'escalade aurait pu être interrompue.

## 10.3 Construire une liste de vérification spécifique à une routine

L'utilisateur peut émettre `@script routine matinale` ou `@script début des devoirs` et obtenir un découpage en étapes adaptées à l'enfant, avec les points de refus probables et le langage de soutien pour l'aidant.

## 10.4 Tester sous des conditions spécifiques

Un facilitateur peut injecter une combinaison de paramètres d'état — par exemple, `@set arousal=high fatigue=high medication=wearing-off trust=low context="mauvaise journée à l'école"` — puis exécuter une interaction de début de devoirs pour voir comment l'enfant répond sous stress composé. Activer `@child:inner` pendant cette interaction montre exactement quels paramètres restent à leurs valeurs injectées et lesquels se sont déplacés organiquement.

---

Pour des transcriptions complètes de ces scénarios et d'autres, consultez [`/examples/`](/examples/).

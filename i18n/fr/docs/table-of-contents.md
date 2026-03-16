<!-- i18n: source=docs/table-of-contents.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# Table des matieres

Une vue d'ensemble sur une seule page de tous les documents du depot PAIciente.

---

## Racine

| Fichier | Description |
|---|---|
| [README.md](../../README.md) | Vue d'ensemble du projet, reference des commandes, liens des plateformes et limitations |
| [README.pt.md](../../README.pt.md) | README auxiliaire en Portugais Europeen (PT-PT) |
| [LICENSE](../../LICENSE) | Texte legal complet CC BY-SA 4.0 |
| [CHANGELOG.md](../../CHANGELOG.md) | Historique des versions au format Keep a Changelog |
| [CONTRIBUTING.md](../../CONTRIBUTING.md) | Directives de contribution : transcriptions, traductions, revue clinique, extensions |

---

## Prompt

| Fichier | Description |
|---|---|
| [prompt/system-prompt.md](../../prompt/system-prompt.md) | Le system prompt complet de PAIciente |
| [prompt/design-notes.md](../../prompt/design-notes.md) | Familles d'instructions et fondements de conception du prompt |

---

## Documentation

| Fichier | Description |
|---|---|
| [docs/overview.md](overview.md) | Objectif, portee et architecture |
| [docs/personas.md](personas.md) | Specifications des personas du clinicien et de l'enfant, modulation d'etat avec `@set` |
| [docs/workflow.md](workflow.md) | Sequence d'utilisation recommandee |
| [docs/behavior-map.md](behavior-map.md) | Cartographie unique de l'ensemble d'instructions |
| [docs/inner-state-guide.md](inner-state-guide.md) | Guide utilisateur pour `@child:inner` et `@set` — champs d'annotation, chemin d'escalade, trajectoire et injection d'etat |
| [docs/evidence-map.md](evidence-map.md) | Fondements academiques pour chaque element de conception |
| [docs/limitations.md](limitations.md) | Limites de securite et contraintes explicites |
| [docs/use-cases.md](use-cases.md) | Scenarios d'exemple : devoirs, transition d'appareil, coucher, stress compose |
| [docs/Technical-Rationale-and-Academic-Positioning.md](Technical-Rationale-and-Academic-Positioning.md) | Fondements techniques et positionnement academique — cadrage formel, engagements de conception et ancrage dans les preuves |

---

## References

| Fichier | Description |
|---|---|
| [references/references.md](../../references/references.md) | Les 20 references academiques avec resumes et liens DOI/URL |
| [references/references.bib](../../references/references.bib) | Entrees BibTeX pour les 20 references |
| [references/evidence-map.csv](../../references/evidence-map.csv) | Cartographie element-de-conception-vers-source en format CSV |

---

## Guides d'implementation

| Fichier | Description |
|---|---|
| [implementations/claude.md](../../implementations/claude.md) | Configuration via Claude Projects (auto-instanciation) |
| [implementations/chatgpt.md](../../implementations/chatgpt.md) | Configuration via Custom GPT — inclut un lien sandbox |
| [implementations/mistral.md](../../implementations/mistral.md) | Configuration via Le Chat Agent — inclut un lien sandbox |
| [implementations/gemini.md](../../implementations/gemini.md) | Configuration via Gemini Gem — inclut un lien sandbox |

### Ressources specifiques aux plateformes

| Fichier | Description |
|---|---|
| [implementations/resources/chatgpt/customgpt_v2_core_instructions.md](../../implementations/resources/chatgpt/customgpt_v2_core_instructions.md) | ChatGPT Custom GPT — instructions principales |
| [implementations/resources/chatgpt/customgpt_v2_knowledge_01_child_persona_and_inner_state.md](../../implementations/resources/chatgpt/customgpt_v2_knowledge_01_child_persona_and_inner_state.md) | ChatGPT Custom GPT — fichier de connaissances : persona de l'enfant et etat interieur |
| [implementations/resources/chatgpt/customgpt_v2_knowledge_02_set_command_and_state_rules.md](../../implementations/resources/chatgpt/customgpt_v2_knowledge_02_set_command_and_state_rules.md) | ChatGPT Custom GPT — fichier de connaissances : commande `@set` et regles d'etat |
| [implementations/resources/chatgpt/customgpt_v2_knowledge_03_clinician_shared_rules_and_commands.md](../../implementations/resources/chatgpt/customgpt_v2_knowledge_03_clinician_shared_rules_and_commands.md) | ChatGPT Custom GPT — fichier de connaissances : clinicien, regles partagees et commandes |
| [implementations/resources/mistral/references.pdf](../../implementations/resources/mistral/references.pdf) | Agent Mistral — document de references |
| [implementations/resources/mistral/references-bib.pdf](../../implementations/resources/mistral/references-bib.pdf) | Agent Mistral — references BibTeX |
| [implementations/resources/mistral/evidence-map.pdf](../../implementations/resources/mistral/evidence-map.pdf) | Agent Mistral — carte des preuves |

---

## Exemples

| Fichier | Description |
|---|---|
| [examples/format.md](../../examples/format.md) | Modele de contributeur pour la soumission de transcriptions |
| [examples/homework-startup/claude.md](../../examples/homework-startup/claude.md) | Scenario de devoirs — Claude |
| [examples/homework-startup/chatgpt.md](../../examples/homework-startup/chatgpt.md) | Scenario de devoirs — ChatGPT |
| [examples/homework-startup/mistral.md](../../examples/homework-startup/mistral.md) | Scenario de devoirs — Mistral |
| [examples/device-transition/claude.md](../../examples/device-transition/claude.md) | Scenario de transition d'appareil — Claude |
| [examples/bedtime-routine/chatgpt.md](../../examples/bedtime-routine/chatgpt.md) | Scenario de coucher — ChatGPT |

---

## Localisation

| Fichier | Description |
|---|---|
| [i18n/fr/README.md](../../i18n/fr/README.md) | Etat de la traduction et directives pour le Francais |

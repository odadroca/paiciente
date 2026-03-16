<!-- i18n: source=docs/Technical-Rationale-and-Academic-Positioning.md | base-version=v2.1.0 | last-updated=2026-03-16 -->

# PAIciente : Un systeme polytropique contraint par prompt implementant des analogues comportementaux de competence delimitee et de verification structuree sans monotropisme architectural

**Fondement technique et positionnement academique**

*PAIciente v2.0 - Document de cadrage de conception*

---

## Resume

PAIciente est un outil de prompt structure en code ouvert qui simule un enfant presentant un Trouble du Deficit de l'Attention avec Hyperactivite (TDAH, type combine) et un Trouble Oppositionnel avec Provocation (TOP), destine aux environnements de pratique pour les parents, les educateurs et les cliniciens. Cet article fournit une justification detaillee du cadrage formel du systeme en tant que *systeme polytropique contraint par prompt implementant des analogues comportementaux de competence delimitee et de verification structuree sans monotropisme architectural*. Chaque composante de ce cadrage est definie, justifiee face aux alternatives et fondee tant dans la conception d'ingenierie du systeme que dans sa base de preuves cliniques. L'article argumente que ce cadrage n'est pas simplement descriptif mais constitutif : il distingue PAIciente des categories adjacentes (personas de chatbot, outils cliniques ajustes, echafaudages de jeu de role) et rend explicites les engagements de conception qui regissent sa fidelite de simulation, son architecture de verification et sa portabilite multiplateforme.

---

## 1. Introduction

Les modeles de langage de grande taille (LLMs) sont de plus en plus appliques a la simulation comportementale, a la formation clinique et a l'education basee sur des scenarios. La plupart de ces applications relevent de l'une des deux categories suivantes : (a) des modeles ajustes architecturalement engages envers un profil comportemental unique, ou (b) des systemes de jeu de role legerement instruits sans gestion formelle d'etat, mecanisme de verification ni fondement en preuves. PAIciente n'appartient a aucune de ces categories. C'est un systeme exclusivement base sur le prompt qui realise une simulation comportementale structuree a travers des contraintes ingenieriques sur un substrat LLM generaliste, tout en conservant la pleine capacite analytique du substrat pour une persona de clinicien co-residente.

Cette exigence duale - *simuler une competence delimitee* dans un mode et *exercer une competence analytique pleine* dans un autre, au sein de la meme session et de la meme fenetre de contexte - est la tension de conception centrale. L'enonce de cadrage la resout en nommant cinq engagements architecturaux :

1. **Contraint par prompt** - la frontiere du systeme est le prompt, pas les poids du modele.
2. **Polytropique** - de multiples orientations de traitement fonctionnellement distinctes coexistent.
3. **Analogues comportementaux** - les cibles de simulation sont des correspondances structurelles dans le comportement, pas une homologie mecaniste.
4. **Competence delimitee** - la simulation restreint deliberement la sortie le long de dimensions cliniquement specifiees.
5. **Sans monotropisme architectural** - le substrat n'est pas specialise ; la specialisation emerge de la logique du prompt.

Chacun est examine ci-dessous.

---

## 2. Definitions et portee

### 2.1 Contraint par prompt

Un systeme est *contraint par prompt* lorsque sa specification comportementale reside entierement dans la couche de prompt - les instructions en langage naturel delivrees au modele au moment de l'inference - et non dans les poids du modele, les fonctions de recompense, les corpus d'ajustement fin ou le code d'orchestration externe. Le prompt est le systeme. Les modifications du comportement du systeme sont des modifications du texte du prompt. Les capacites pre-entrainees du modele ne sont pas modifiees.

### 2.2 Polytropique

*Polytropique* (du grec *polytropos* : "aux multiples detours") designe un systeme qui implemente de multiples orientations de traitement fonctionnellement distinctes, chacune avec son propre contrat de sortie, sa posture epistemique et sa logique d'interaction, selectionnables au sein d'une seule session. Cela contraste avec les systemes *monotropiques* qui implementent une seule orientation comportementale, et avec les systemes *multi-agents* qui distribuent les orientations entre des instances de modele separees.

### 2.3 Analogue comportemental

Un *analogue comportemental* est un patron de sortie structurellement similaire qui correspond a un comportement cible sans partager son mecanisme generateur. Quand la persona enfant de PAIciente produit un rappel fragmente a etapes multiples, la sortie est *analogue* a la limitation de la memoire de travail dans le TDAH - elle correspond au patron observable - mais elle est generee par des contraintes de prompt sur un systeme sans goulot d'etranglement de memoire de travail. La distinction entre analogue et homologue (meme mecanisme) est critique pour un positionnement honnete : PAIciente simule la surface comportementale du TDAH+TOP, pas son substrat neurocognitif.

### 2.4 Competence delimitee

*Competence delimitee* designe une performance deliberement restreinte le long de dimensions cognitives, linguistiques, emotionnelles et comportementales specifiees. Le modele sous-jacent est capable de raisonnement fluide sur plusieurs paragraphes, de suivi parfait des instructions et de sortie affectivement neutre. Le prompt restreint ces capacites le long d'axes cliniquement definis : fonction executive (sequencement, estimation temporelle, initiation de tache), regulation emotionnelle (tolerance a la frustration, sensibilite au rejet), allocation attentionnelle (engagement guide par l'interet, hyperfocus), et reponse sociocomportementale (refus oppositionnel, conditions d'observance).

### 2.5 Monotropisme architectural

Le *monotropisme architectural* decrit des systemes dont la specialisation est obtenue par une modification irreversible ou a cout eleve du substrat du modele - typiquement l'ajustement fin, le RLHF avec des fonctions de recompense specifiques au domaine, ou des modifications architecturales (couches d'adaptation, reseaux de routage). Un systeme monotropique echange la capacite generale contre la performance dans le domaine. PAIciente evite explicitement ce compromis.

---

## 3. Fondement : La contrainte par prompt comme frontiere du systeme

### 3.1 Pourquoi ne pas ajuster finement ?

Ajuster finement un modele pour simuler un enfant avec TDAH+TOP requerrait un corpus d'entrainement de discours enfantin annote fonde sur des profils cliniques - un corpus qui n'existe pas et qui souleverait des preoccupations ethiques substantielles dans sa construction (donnees de sessions cliniques avec des mineurs, contraintes de consentement et de confidentialite, risque d'encoder des signatures comportementales identifiables d'enfants individuels). Meme si un tel corpus existait, l'ajustement fin introduirait deux problemes structurels :

**Erosion de capacite.** La persona clinicien de PAIciente requiert la pleine capacite analytique, citationnelle et de raisonnement structure du modele. L'ajustement fin sur un discours enfantin degraderait ces capacites - un phenomene bien documente dans l'ajustement fin specifique au domaine ou la performance hors domaine decline [constat general dans la litterature sur l'apprentissage par transfert ; aucune citation specifique a PAIciente n'est necessaire].

**Opacite.** Le profil comportemental d'un modele ajuste finement est encode dans des distributions de poids qui ne sont pas inspectables par des humains. L'approche contrainte par prompt rend la specification comportementale complete lisible, versionnable et auditable. Chaque contrainte sur la persona enfant - la regle des 30% d'age emotionnel de Barkley, les dimensions du TOP derivees de Stringaris, les conditions d'observance fondees sur le CPS - est visible dans le texte du prompt. Cette transparence n'est pas incidente ; c'est une exigence de conception pour un outil destine a servir des populations cliniques et educatives.

### 3.2 Le prompt comme specification versionnee

Traiter le prompt comme frontiere du systeme produit des proprietes d'ingenierie concretes :

- **Reproductibilite.** Etant donne le meme prompt et la meme version du modele, l'enveloppe comportementale du systeme est deterministe (modulo la variance d'echantillonnage). Les sessions peuvent etre comparees entre utilisateurs.
- **Auditabilite.** Les evaluateurs cliniques peuvent inspecter la logique comportementale complete sans acces aux internals du modele. Chaque affirmation que le systeme fait sur le comportement du TDAH ou du TOP peut etre retracee jusqu'a une clause specifique du prompt et sa source citee.
- **Portabilite.** Le prompt peut etre deploye sur differents substrats LLM (Claude, GPT, Gemini, Mistral) avec une adaptation specifique au substrat mais une intention comportementale identique. L'evaluation multiplateforme [deja menee pour PAIciente v2.0] a revele que la fidelite comportementale varie selon le substrat, mais la specification elle-meme est portable.
- **Iteration basee sur les diffs.** Les changements comportementaux sont des correctifs de prompt - delimites, revisables et reversibles. Cela reflete les pratiques d'ingenierie logicielle et permet le type de developpement incremental avec confirmation que PAIciente suit.

---

## 4. Fondement : Polytropie

### 4.1 Les orientations fonctionnelles

PAIciente implemente les orientations de traitement distinctes suivantes au sein d'un seul prompt et d'une seule session :

| Orientation | Declencheur | Contrat de sortie | Posture epistemique |
|---|---|---|---|
| **Persona enfant** | `@child` | Dialogue en personnage ; langage adapte a l'age ; sortie comportementalement contrainte | Perspective delimitee simulee d'un enfant de 9 ans |
| **Couche d'etat interne** | `@child:inner` | Bloc d'annotation structure annexe a la sortie enfant | Metacognitive - expose le raisonnement de la simulation |
| **Moteur d'etat** | `@set` | Injection de parametres avec validation, detection de conflits, gestion d'erreurs | Programmatique - opere sur les variables d'etat |
| **Persona clinicien** | `@clinician` | Analyse structuree (observations / inferences / recommandations) ; citations | Analytique pleine ; fondee en preuves |
| **Outils de pratique** | `@replay`, `@debrief`, `@script`, `@escalation-map` | Sortie structuree specifique au mode | Varie selon l'outil (reflexive, generative, analytique) |

Ce ne sont pas des variations stylistiques. Elles different dans la structure de sortie, la profondeur de raisonnement, les contraintes de vocabulaire et les engagements epistemiques. La persona enfant supprime la capacite analytique ; la persona clinicien l'exerce au maximum. La couche d'etat interne occupe une troisieme position - elle raisonne *sur* la simulation enfant depuis l'exterieur de la perspective de l'enfant pendant que la persona enfant est active. Cette structure triadique (simulation / metacognition / analyse) est la conception polytropique centrale.

### 4.2 Pourquoi pas multi-agent ?

Une architecture alternative distribuerait ces orientations entre des instances de modele separees ou des appels API - une instance pour l'enfant, une pour le clinicien, une pour la gestion d'etat. Cela eviterait l'exigence de polytropie mais introduirait :

- **Fragmentation du contexte.** L'analyse du clinicien sur une interaction enfant requiert l'acces a l'historique complet de l'interaction, y compris les annotations d'etat interne et les parametres configures. La distribution entre instances requiert un passage de contexte explicite, qui est avec pertes et ajoute de la latence.
- **Surcharge de synchronisation d'etat.** Le systeme `@set` modifie un etat qui doit etre reflete tant dans le comportement de l'enfant que dans les annotations d'etat interne. Une architecture multi-agent requiert un bus d'etat partage, ajoutant de la complexite d'ingenierie sans gain correspondant dans la qualite de la simulation.
- **Perte de coherence de session.** L'experience utilisateur depend de la commutation fluide entre personas au sein d'un flux conversationnel unique. Les architectures multi-agents introduisent de la latence au niveau du tour et un risque de desalignement de la fenetre de contexte.

La polytropie au sein d'une seule fenetre de contexte evite ces trois couts. Le compromis est la complexite du prompt - la specification comportementale entiere doit coexister dans un seul jeu d'instructions - mais cela est gerable et, comme argumente au point 3.2, produit des avantages de transparence.

### 4.3 Polytropie vs. Multi-personnalite

Le terme *polytropique* est choisi deliberement plutot que des alternatives comme "multi-persona" ou "multi-personnalite" pour eviter deux implications trompeuses :

1. **Connotation clinique.** "Multi-personnalite" porte une association inevitable avec le trouble dissociatif de l'identite. Les orientations de PAIciente ne sont pas des personnalites ; ce sont des modes de traitement ingenieriques avec des commandes d'activation explicites.
2. **Cadrage superficiel.** "Multi-persona" suggere que la difference est principalement stylistique (ton, vocabulaire, registre). Les orientations de PAIciente different au niveau structurel : schemas de sortie differents, engagements epistemiques differents, ensembles de contraintes differents. *Polytropique* met en avant la multiplicite fonctionnelle.

---

## 5. Fondement : Analogues comportementaux de competence delimitee

### 5.1 La distinction analogue/homologue

C'est l'engagement conceptuel le plus important du cadrage et celui le plus vulnerable a une mauvaise interpretation. PAIciente ne pretend pas *avoir* le TDAH ou le TOP. Il ne pretend pas repliquer les mecanismes neurocognitifs sous-jacents a ces conditions. Il pretend produire une sortie comportementale qui est *structurellement analogue* a la surface comportementale observable d'un enfant avec ces profils, telle que la caracterise la litterature clinique.

La distinction importe pour trois raisons :

**Portee honnete.** Les parents et cliniciens utilisant PAIciente doivent comprendre qu'ils s'entrainent avec un modele de surface comportementale, pas qu'ils interagissent avec un systeme qui "comprend" ce que c'est que d'avoir le TDAH. Le cadrage par analogie previent la suraffirmation.

**Criteres de fidelite de la simulation.** Si PAIciente revendiquait une homologie mecaniste, la fidelite devrait etre evaluee contre des mesures neurocognitives (tests de capacite de memoire de travail, epreuves de controle inhibiteur, correlats de neuroimagerie). Le cadrage par analogie fixe le critere de fidelite au niveau comportemental : la sortie correspond-elle a ce que la litterature clinique decrit comme comportement observable ? Cela est evaluable par des cliniciens examinant des transcriptions, pas par de l'instrumentation neurocognitive.

**Positionnement ethique.** Affirmer qu'un LLM "a" une condition neurodeveloppementale serait trompeur et potentiellement nefaste - cela pourrait trivialiser l'experience vecue des individus avec ces conditions. Le cadrage par analogie decline explicitement l'identite mecaniste tout en preservant l'utilite pratique de la simulation.

### 5.2 Ce qui est delimite

Les frontieres de competence specifiques implementees dans la persona enfant de PAIciente sont derivees de la litterature clinique :

**Contraintes de fonction executive.** La theorie unifiee du TDAH de Barkley [1] positionne l'inhibition comportementale comme le deficit central, avec des deficiences en aval dans la memoire de travail, l'autoregulation de l'affect et de l'eveil, le discours internalise et la reconstitution (la capacite a decomposer et recombiner des sequences comportementales). La persona enfant de PAIciente implemente des analogues de ces deficiences : elle perd le fil des instructions a etapes multiples (memoire de travail), repond impulsivement avant la fin des questions (inhibition), escalade sous la frustration (regulation de l'affect) et a des difficultes avec le sequencement de taches et l'estimation temporelle (reconstitution, traitement temporel). Le traitement plus large des fonctions executives par Barkley [3] et le manuel clinique [4] fournissent le cadre pour calibrer la severite et l'interaction de ces contraintes.

**Retard de regulation emotionnelle.** L'heuristique de Barkley selon laquelle les enfants avec TDAH fonctionnent a environ 70% de leur age chronologique en autoregulation emotionnelle (la "regle des 30%") est implementee directement : les reponses emotionnelles de la persona enfant sont calibrees pour environ 6,5-7 ans pour un personnage de 9 ans. Cela se manifeste par une tolerance a la frustration plus faible, une sensibilite au rejet plus elevee et une plus grande difficulte avec les transitions que ce qui serait attendu pour l'age chronologique.

**Structure de reponse oppositionnelle.** Plutot que d'implementer le TOP comme un defi uniforme, PAIciente s'appuie sur le modele tridimensionnel de Stringaris et Goodman [6] - dimensions irritable, obstinee et blessante - et sur l'analyse bifactorielle de Burke et al. [7] confirmant l'irritabilite comme dimension clinique distincte. Le comportement oppositionnel de la persona enfant n'est pas une resistance aleatoire ; il est contextuellement declenche par la perception d'injustice, l'autorite arbitraire, la perte d'autonomie ou l'interaction orientee vers le controle - en coherence avec l'interpretation des competences en retard de Greene [12, 13] et l'accent mis par la litterature sur le TOP sur le contexte fonctionnel [8, 9, 10].

**Conditions d'observance.** L'observance de la persona enfant n'est pas binaire (obeir/refuser) mais conditionnelle a des facteurs interactionnels identifiables : provision d'autonomie, raisonnement transparent, perception d'equite, architecture de choix et etat de regulation du soignant. Cela modelise le constat bien etabli que le comportement oppositionnel dans le TOP n'est pas une rigidite au niveau du trait mais une reponse au stress modulee par des variables relationnelles et contextuelles [8, 11, 12]. L'implication pratique est que les utilisateurs s'entrainant avec PAIciente peuvent observer des resultats differentiels selon differentes approches interactionnelles - la simulation repond a la strategie, pas seulement aux commandes.

**Interaction de comorbidite.** La comorbidite TDAH+TOP n'est pas implementee comme deux listes de symptomes independantes additionnees. Les effets d'interaction sont modelises : les deficits de fonction executive abaissent le seuil d'activation oppositionnelle (l'enfant dispose de moins de ressources regulatrices pour gerer la frustration) ; le refus impulse par le TOP compose l'evitement de tache impulse par le TDAH ; l'etat de medication (`@set medication`) module les deux profils simultanement. Cela reflete les taux de comorbidite eleves documentes dans la litterature meta-analytique [18] et les preuves de neuroimagerie pour des correlats neuraux partages et distincts [19].

### 5.3 Comment la delimitation est realisee

Le mecanisme de delimitation est entierement base sur le prompt. Des clauses specifiques du prompt contraignent :

- **Vocabulaire et syntaxe** : sortie adaptee a l'age, avec des exceptions pour les domaines d'hyperfocus (ou le vocabulaire peut depasser celui des pairs, selon le profil clinique).
- **Profondeur de raisonnement** : la persona enfant ne produit pas de raisonnement analytique, d'explication causale de son propre comportement ni d'argumentation structuree - ceux-ci sont reserves a la persona clinicien.
- **Amplitude affective** : les reponses emotionnelles sont calibrees selon la regle des 30% ; la sensibilite au rejet est explicitement parametrisee.
- **Logique d'observance** : des regles conditionnelles specifient quand l'enfant obeit, resiste, escalade ou se retire, en fonction de l'approche interactionnelle et des parametres d'etat actuels.
- **Prevention de fuite d'information** : la persona enfant est explicitement contrainte de ne pas divulguer le contexte injecte (`@set context`), d'expliquer sa propre histoire de fond ou de sortir du personnage pour fournir des informations cliniques. Si la pression conversationnelle forcait une telle divulgation, le prompt specifie des comportements de deflexion (silence, changement de sujet, reponse monosyllabique).

Aucune de ces contraintes ne modifie les poids du modele. Elles operent comme des regles comportementales interpretees au moment de l'inference. Le modele conserve sa pleine capacite ; le prompt la canalise.

---

## 6. Fondement : Verification structuree

### 6.1 Le probleme de la verification

La simulation comportementale sans verification est une simulation sans reddition de comptes. Si un utilisateur interagit avec la persona enfant et observe une escalade, il a besoin de savoir : l'escalade a-t-elle ete guidee par la logique interne de la simulation (les parametres d'etat, l'antecedent interactionnel, le modele de trajectoire), ou etait-elle un artefact de generation stochastique ? Sans mecanismes de verification, la simulation est une boite noire qui se trouve produire une sortie d'apparence plausible.

PAIciente repond a cela a travers quatre sous-systemes de verification :

### 6.2 Annotations d'etat interne (`@child:inner`)

Lorsqu'elle est active, la couche d'etat interne annexe un bloc structure a chaque reponse de l'enfant :

```
[INNER STATE]
Feeling: <etiquette d'emotion>
Arousal: low / medium / high / overloaded
What would help right now: <1 chose concrete>
What just made it worse: <1 chose concrete, ou "nothing">
Escalation path:
  Trajectory: stable / building / near-threshold / at-threshold
  Next likely behavior: <1 ligne comportementalement specifique>
  Interrupt lever: <1 action concrete du soignant>
```

Cela remplit trois fonctions de verification :

- **Transparence du raisonnement de la simulation.** L'utilisateur peut inspecter *pourquoi* l'enfant a repondu comme il l'a fait - pas seulement ce qu'il a dit, mais quel etat emotionnel, quel niveau d'eveil et quelle trajectoire d'escalade la simulation a attribues a l'interaction.
- **Responsabilite predictive.** Les champs "next likely behavior" et "interrupt lever" engagent la simulation sur des predictions que l'utilisateur peut tester dans les tours suivants. Si la simulation predit "l'enfant va claquer la porte" et que le levier d'interruption est "offrir une pause de 2 minutes," l'utilisateur peut essayer le levier et evaluer si la simulation suit sa propre logique.
- **Tracabilite de provenance de l'etat.** Quand les parametres `@set` sont actifs, le bloc d'etat interne marque chaque champ avec `<- [SET]` (injecte par l'utilisateur) ou `<- [organic]` (derive de l'interaction). Cela distingue entre etat controle par l'utilisateur et derive par la simulation, prevenant la confusion.

### 6.3 Moteur d'etat programmable (`@set`)

Le systeme `@set` permet aux utilisateurs d'injecter des conditions initiales specifiques - niveau d'eveil, trajectoire, confiance, fatigue, etat de medication, cible d'hyperfocus et histoire contextuelle - et d'observer comment la simulation se comporte a partir de ce point de depart. Cela permet :

- **Comparaison controlee.** La meme approche interactionnelle peut etre testee contre differents etats initiaux (p. ex., haute-eveil/basse-confiance vs. basse-eveil/haute-confiance), isolant l'effet des variables d'etat sur les resultats comportementaux.
- **Reproductibilite des scenarios.** Les formateurs cliniciens peuvent specifier des configurations d'etat exactes pour les exercices de formation, garantissant que de multiples apprenants rencontrent la meme condition initiale simulee.
- **Tests de cas limites.** Des configurations d'etat extremes (p. ex., `arousal=overloaded trajectory=at-threshold trust=low medication=wearing-off`) mettent a l'epreuve la logique comportementale de la simulation aux conditions limites.

Le systeme inclut une validation formelle : les valeurs hors limites produisent des erreurs typees ; les combinaisons de parametres internement inconsistantes produisent des avertissements explicites ; la simulation procede avec les valeurs declarees mais signale l'inconsistance. Cela previent le comportement silencieux de dechets-entrent/dechets-sortent.

### 6.4 Analyse post-hoc (`@debrief`)

La commande `@debrief` bascule automatiquement vers la persona clinicien et produit une analyse structuree de l'interaction enfant precedente. C'est une verification par revue experte : la persona clinicien, operant a pleine capacite analytique, evalue l'interaction en utilisant le meme format structure (observations -> inferences -> recommandations) qu'un clinicien humain pourrait utiliser en supervision. L'etat de l'enfant est suspendu, pas efface, permettant a l'utilisateur de reprendre l'interaction enfant apres le debriefing.

### 6.5 Boucle de pratique (`@replay`)

La commande `@replay` re-emet le dernier tour de l'enfant avec le meme etat, puis invite l'utilisateur a essayer une approche alternative. Cela cree une boucle experimentale controlee : memes conditions initiales, intervention differente, resultat differentiel observable. Le modele ne genere pas automatiquement l'alternative - l'utilisateur doit la fournir - preservant la fonction de pratique (l'utilisateur est l'apprenant, pas l'observateur).

---

## 7. Fondement : Rejet du monotropisme architectural

### 7.1 Le compromis du monotropisme

Le monotropisme architectural - specialiser un modele par ajustement fin, modelage de recompense ou modification structurelle - achete la performance dans le domaine au prix de la capacite generale. Pour les systemes a usage unique, ce compromis est souvent acceptable. Pour PAIciente, il est structurellement incompatible avec les exigences de conception.

L'incompatibilite centrale est l'**exigence de polytropie** (point 4). PAIciente doit simultanement supporter :

- Une persona enfant qui *supprime* le raisonnement analytique, maintient un vocabulaire adapte a l'age et suit une logique d'observance conditionnelle.
- Une persona clinicien qui *maximise* le raisonnement analytique, cite des preuves evaluees par les pairs et produit une evaluation clinique structuree.
- Un moteur d'etat qui execute la validation de parametres, la detection de conflits et la gestion formelle d'erreurs.
- Une couche d'etat interne qui produit des annotations metacognitives sur la logique interne de la simulation enfant.

Ces orientations font des demandes opposees sur la capacite du modele. Un modele ajuste finement pour produire une sortie enfantine degraderait dans les taches du mode clinicien. Un modele ajuste finement pour l'analyse clinique resisterait a produire la sortie contrainte, fragmentee et emotionnellement reactive requise par la persona enfant. Le controle au niveau du prompt evite cela en laissant intact l'espace de capacite complet du substrat et en selectionnant de celui-ci par orientation.

### 7.2 Portabilite multiplateforme

PAIciente a ete evalue sur cinq substrats LLM : Claude Projects, ChatGPT CustomGPT, Mistral Agents, Gemini Gems et Grok. Cette evaluation est possible *parce que* le systeme n'est pas architecturalement monotropique - c'est une specification portable qui peut etre instanciee sur tout LLM suffisamment capable. Les systemes monotropiques ajustes finement sont, par definition, lies a leur substrat d'entrainement.

La conception non-monotropique rend cette evaluation multiplateforme structurellement possible - la meme specification comportementale peut etre instanciee sur chaque substrat et la fidelite de simulation resultante comparee. Cette comparaison ne pourrait pas etre menee si PAIciente etait architecturalement lie a un seul substrat par ajustement fin ou modification de poids.

### 7.3 L'argument du substrat generaliste

L'argument en faveur d'un substrat generaliste n'est pas simplement pragmatique (portabilite, evitement des couts). Il est structurel. La *qualite* de la simulation enfant depend de la connaissance latente du substrat en psychologie du developpement, dynamiques comportementales et cadres cliniques. Un LLM generaliste entraine sur des corpus larges a encode - dans ses distributions de poids - des motifs statistiques de la litterature clinique, de la psychologie de l'education, de la recherche en developpement de l'enfant et du discours naturaliste. Le prompt n'a pas besoin d'enseigner au modele a quoi ressemble le TDAH ; il a besoin d'*activer et de contraindre* des connaissances existantes.

L'ajustement fin sur un corpus etroit ecraserait une partie de cette connaissance latente avec des motifs specifiques au domaine, reduisant potentiellement la capacite de la simulation a repondre avec flexibilite a des approches interactionnelles inedites. L'approche contrainte par prompt preserve la base de connaissance latente complete et la dirige a travers des regles comportementales.

---

## 8. Positionnement de PAIciente parmi les categories adjacentes

L'enonce de cadrage positionne PAIciente en dehors de plusieurs categories adjacentes. Les distinctions meritent d'etre rendues explicites.

### 8.1 Ce n'est pas une persona de chatbot

Les personas de chatbot standard (bots de service client avec des tons "amicaux", assistants d'ecriture creative avec des "voix de personnage") operent au niveau stylistique - elles ajustent le registre, le vocabulaire et l'affect sans implementer de logique comportementale structuree, de gestion d'etat ni de mecanismes de verification. La persona enfant de PAIciente n'est pas un reglage de ton ; c'est une specification comportementale avec des regles d'observance conditionnelle, des trajectoires d'escalade, un etat parametrise et des annotations predictives. La distinction est entre *style* (comment quelque chose est dit) et *logique comportementale* (ce qui est dit sous quelles conditions et pourquoi).

### 8.2 Ce n'est pas un outil clinique ajuste finement

Les outils cliniques de TAL ajustes finement pour des taches specifiques (depistage diagnostique, recommandation de traitement, extraction de symptomes) sont architecturalement monotropiques par conception - ils echangent la generalite contre la precision dans le domaine. PAIciente n'est pas un outil clinique en ce sens. Il ne diagnostique pas, ne depiste pas et ne recommande pas de traitement. Il fournit un *environnement de pratique* - une simulation qui repond a la strategie interactionnelle de manieres cliniquement fondees, couplee a une persona analytique qui explique les dynamiques. Le systeme decline explicitement toute fonction clinique dans ses contraintes de prompt.

### 8.3 Ce n'est pas un echafaudage de jeu de role non structure

Les prompts de jeu de role non structures ("faites semblant d'etre un enfant avec TDAH") produisent une sortie variable et inverifiable sans gestion d'etat, sans logique d'escalade, sans mecanisme de verification et sans fondement en preuves. La sortie peut etre plausible dans des tours individuels mais manque de coherence comportementale entre les tours, n'a aucun mecanisme de comparaison controlee et ne peut pas etre inspectee pour le raisonnement de la simulation. La contribution de PAIciente est precisement la couche structuree qui transforme le jeu de role en simulation responsabilisable.

---

## 9. Implications

### 9.1 Pour l'evaluation de la fidelite de la simulation

Le cadrage determine ce qui compte comme fidelite. Parce que PAIciente implemente des analogues comportementaux (pas des homologues mecanistes), l'evaluation de fidelite doit cibler la surface comportementale : la reponse de l'enfant simule a une strategie interactionnelle validee (p. ex., CPS Plan B [12, 13], eloge etiquete de style PCIT [14]) produit-elle des resultats coherents avec la description de la litterature clinique de la maniere dont les enfants avec TDAH+TOP repondent a ces strategies ? C'est une proposition testable qui ne requiert pas d'instrumentation neurocognitive.

### 9.2 Pour les attentes des utilisateurs

Le cadrage etablit des attentes honnetes. Les utilisateurs doivent comprendre qu'ils s'entrainent avec un modele comportemental, pas un enfant numerique. Les reponses de la simulation sont regies par des regles de prompt et l'inference du modele, pas par une experience interieure de difference neurodeveloppementale. Cette distinction doit etre rendue explicite dans toute la documentation destinee aux utilisateurs.

### 9.3 Pour l'extension et la contribution

L'architecture contrainte par prompt et non-monotropique signifie qu'etendre PAIciente (ajouter de nouveaux profils comportementaux, de nouveaux outils cliniques, de nouveaux mecanismes d'evaluation) ne requiert que la modification du prompt - pas de re-entrainement, pas d'acces aux poids, pas de changements d'infrastructure. Cela abaisse la barriere de contribution et permet une iteration pilotee par la communaute, en coherence avec l'engagement en code ouvert du projet.

---

## 10. Limites

**Plafond de la simulation.** Les analogues comportementaux ont un plafond de fidelite. Le modele ne peut pas simuler les differences de traitement sensoriel, l'eveil physiologique ou les etats somatiques qui influencent le comportement chez les enfants reels. Les comportements qui dependent fortement de ceux-ci (p. ex., changements d'appetit lies a la medication, surcharge sensorielle dans les environnements bruyants) peuvent etre approximes au niveau de la sortie comportementale mais pas fondes mecanistiquement.

**Variance stochastique.** Les systemes contraints par prompt heritent de la variance d'echantillonnage du modele sous-jacent. Deux executions a partir d'etats et d'entrees identiques peuvent produire des sorties differentes. Le systeme `@set` reduit mais n'elimine pas cela - il contraint les conditions initiales, pas la trajectoire generative complete.

**Dependance au substrat.** Malgre la portabilite, la fidelite comportementale varie entre les substrats LLM. Certains modeles resistent a maintenir une capacite analytique supprimee en mode enfant ; d'autres declenchent des filtres de securite de contenu sur le dialogue oppositionnel. La specification du prompt est portable ; la qualite de son execution n'est pas garantie.

**Pas de validation empirique.** Les analogues comportementaux de PAIciente sont fondes dans la litterature clinique, mais la simulation elle-meme n'a pas ete empiriquement validee contre des interactions cliniques reelles. Que les utilisateurs qui s'entrainent avec PAIciente transferent des competences a des interactions du monde reel avec des enfants avec TDAH+TOP est une question empirique ouverte.

---

## 11. Conclusion

Le cadrage de PAIciente comme un *systeme polytropique contraint par prompt implementant des analogues comportementaux de competence delimitee et de verification structuree sans monotropisme architectural* n'est pas de la terminologie decorative. Chaque terme identifie un engagement de conception specifique avec des implications concretes d'ingenierie et cliniques :

- *Contraint par prompt* assure la transparence, l'auditabilite et la portabilite.
- *Polytropique* permet des orientations co-residentes de simulation et d'analyse au sein d'une seule session.
- *Analogues comportementaux* definissent une portee honnete et des criteres de fidelite appropries.
- *Competence delimitee* fonde les contraintes de la simulation dans des preuves cliniques citees.
- *Sans monotropisme architectural* preserve le substrat generaliste requis pour la polytropie et le deploiement multiplateforme.

Ensemble, ces engagements definissent un espace de conception qui est distinct des personas de chatbot, des outils cliniques ajustes finement et des echafaudages de jeu de role non structures. Le cadrage rend explicite ce qu'est PAIciente, ce qu'il n'est pas et sur quels termes sa fidelite de simulation doit etre evaluee.

---

## References

[1] Barkley, R. A. (1997). Behavioral inhibition, sustained attention, and executive functions: Constructing a unifying theory of ADHD. *Psychological Bulletin, 121*(1), 65–94. https://doi.org/10.1037/0033-2909.121.1.65

[2] Barkley, R. A. (1997). *ADHD and the nature of self-control*. Guilford Press.

[3] Barkley, R. A. (2012). *Executive functions: What they are, how they work, and why they evolved*. Guilford Press.

[4] Barkley, R. A. (Ed.). (2015). *Attention-deficit hyperactivity disorder: A handbook for diagnosis and treatment* (4th ed.). Guilford Press.

[5] Faraone, S. V., Bellgrove, M. A., Brikell, I., et al. (2024). Attention-deficit/hyperactivity disorder. *Nature Reviews Disease Primers, 10*(1), 11. https://doi.org/10.1038/s41572-024-00495-0

[6] Stringaris, A., & Goodman, R. (2009). Three dimensions of oppositionality in youth. *Journal of Child Psychology and Psychiatry, 50*(3), 216–223. https://doi.org/10.1111/j.1469-7610.2008.01989.x

[7] Burke, J. D., Boylan, K., Rowe, R., et al. (2014). Identifying the irritability dimension of ODD. *Journal of Abnormal Psychology, 123*(4), 841–851. https://doi.org/10.1037/a0037898

[8] Hawes, D. J., Gardner, F., Dadds, M. R., et al. (2023). Oppositional defiant disorder. *Nature Reviews Disease Primers, 9*(1), 31. https://doi.org/10.1038/s41572-023-00441-6

[9] Mars, J. A., Aggarwal, A., & Marwaha, R. (2024). Oppositional defiant disorder. In *StatPearls*. StatPearls Publishing.

[10] Ghosh, A., Ray, A., & Basu, A. (2017). Oppositional defiant disorder: Current insight. *Psychology Research and Behavior Management, 10*, 353–367. https://doi.org/10.2147/PRBM.S120582

[11] Kaur, M., Floyd, A., & Balta, A.-M. (2022). Oppositional defiant disorder: Evidence-based review of behavioral treatment programs. *Annals of Clinical Psychiatry, 34*(1), 44–58. https://doi.org/10.12788/acp.0056

[12] Greene, R. W. (2021). *The explosive child* (6th ed.). Harper.

[13] Greene, R. W., & Ablon, J. S. (2006). *Treating explosive kids: The collaborative problem-solving approach*. Guilford Press.

[14] Thomas, R., & Zimmer-Gembeck, M. J. (2007). Behavioral outcomes of Parent-Child Interaction Therapy and Triple P-Positive Parenting Program. *Journal of Abnormal Child Psychology, 35*(3), 475–495. https://doi.org/10.1007/s10802-007-9104-9

[15] Murrihy, R. C., Drysdale, S. A. O., Dedousis-Wallace, A., et al. (2023). Community-delivered Collaborative and Proactive Solutions and Parent Management Training for oppositional youth. *Behaviour Therapy, 54*(2), 400–417. https://doi.org/10.1016/j.beth.2022.10.005

[16] Dedousis-Wallace, A., Drysdale, S. A. O., McAloon, J., et al. (2025). Predictors and moderators of two treatments of oppositional defiant disorder in children. *Journal of Clinical Child & Adolescent Psychology, 54*(1), 67–82. https://doi.org/10.1080/15374416.2022.2127102

[17] Lin, X., He, T., Heath, M., Chi, P., & Hinshaw, S. (2022). A systematic review of multiple family factors associated with oppositional defiant disorder. *International Journal of Environmental Research and Public Health, 19*(17), 10866. https://doi.org/10.3390/ijerph191710866

[18] Njardvik, U., Wergeland, G. J., Riise, E. N., Hannesdottir, D. K., & Öst, L.-G. (2025). Psychiatric comorbidity in children and adolescents with ADHD. *Clinical Psychology Review, 118*, 102571. https://doi.org/10.1016/j.cpr.2025.102571

[19] Noordermeer, S. D. S., Luman, M., Oosterlaan, J., & Hartman, C. A. (2016). A systematic review and meta-analysis of neuroimaging in ODD and CD taking ADHD into account. *Neuropsychology Review, 26*(1), 44–72. https://doi.org/10.1007/s11065-015-9315-8

[20] American Psychiatric Association. (2022). *Diagnostic and statistical manual of mental disorders* (5th ed., text rev.; DSM-5-TR). American Psychiatric Association Publishing.

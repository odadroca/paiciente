<!-- i18n: source=docs/Technical-Rationale-and-Academic-Positioning.md | base-version=v2.1.0 | last-updated=2026-03-16 -->

# PAIciente: Um Sistema Politrópico Restrito por Prompt que Implementa Análogos Comportamentais de Competência Delimitada e Verificação Estruturada Sem Monotropismo Arquitetural

**Fundamentação Técnica e Posicionamento Académico**

*PAIciente v2.0 - Documento de Enquadramento de Design*

---

## Resumo

O PAIciente é uma ferramenta de prompt estruturado de código aberto que simula uma criança que apresenta Perturbação de Hiperatividade e Défice de Atenção (PHDA, tipo combinado) e Perturbação de Oposição e Desafio (POD), dirigida a ambientes de prática para pais, educadores e clínicos. Este artigo fornece uma fundamentação detalhada para o enquadramento formal do sistema como um *sistema politrópico restrito por prompt que implementa análogos comportamentais de competência delimitada e verificação estruturada sem monotropismo arquitetural*. Cada componente deste enquadramento é definido, justificado face a alternativas e fundamentado tanto no design de engenharia do sistema como na sua base de evidência clínica. O artigo argumenta que este enquadramento não é meramente descritivo mas constitutivo: distingue o PAIciente de categorias adjacentes (personas de chatbot, ferramentas clínicas afinadas, andaimes de jogo de papéis) e torna explícitos os compromissos de design que governam a sua fidelidade de simulação, arquitetura de verificação e portabilidade entre plataformas.

---

## 1. Introdução

Os modelos de linguagem de grande escala (LLMs) são cada vez mais aplicados à simulação comportamental, formação clínica e educação baseada em cenários. A maioria destas aplicações enquadra-se numa de duas categorias: (a) modelos afinados arquiteturalmente comprometidos com um único perfil comportamental, ou (b) sistemas de jogo de papéis levemente instruídos sem gestão formal de estado, mecanismo de verificação ou fundamentação em evidência. O PAIciente não se enquadra em nenhuma das categorias. É um sistema apenas de prompt que alcança simulação comportamental estruturada através de restrições engenheiradas sobre um substrato LLM de uso geral, mantendo a capacidade analítica plena do substrato para uma persona de clínico co-residente.

Este requisito dual - *simular competência delimitada* num modo e *exercer competência analítica plena* noutro, dentro da mesma sessão e janela de contexto - é a tensão de design central. A declaração de enquadramento resolve-a nomeando cinco compromissos arquiteturais:

1. **Restrito por prompt** - a fronteira do sistema é o prompt, não os pesos do modelo.
2. **Politrópico** - múltiplas orientações de processamento funcionalmente distintas coexistem.
3. **Análogos comportamentais** - os alvos de simulação são correspondências estruturais no comportamento, não homologia mecanicista.
4. **Competência delimitada** - a simulação restringe deliberadamente o output ao longo de dimensões clinicamente especificadas.
5. **Sem monotropismo arquitetural** - o substrato não é especializado; a especialização é emergente da lógica do prompt.

Cada um é examinado abaixo.

---

## 2. Definições e Âmbito

### 2.1 Restrito por Prompt

Um sistema é *restrito por prompt* quando a sua especificação comportamental reside inteiramente na camada de prompt - as instruções em linguagem natural entregues ao modelo no momento da inferência - e não nos pesos do modelo, funções de recompensa, corpora de afinação ou código de orquestração externo. O prompt é o sistema. Alterações ao comportamento do sistema são alterações ao texto do prompt. As capacidades pré-treinadas do modelo não são modificadas.

### 2.2 Politrópico

*Politrópico* (do grego *polytropos*: "de muitas voltas") designa um sistema que implementa múltiplas orientações de processamento funcionalmente distintas, cada uma com o seu próprio contrato de output, postura epistémica e lógica de interação, selecionáveis dentro de uma única sessão. Isto contrasta com sistemas *monotrópicos* que implementam uma orientação comportamental, e com sistemas *multi-agente* que distribuem orientações por instâncias de modelo separadas.

### 2.3 Análogo Comportamental

Um *análogo comportamental* é um padrão de output estruturalmente semelhante que corresponde a um comportamento-alvo sem partilhar o seu mecanismo gerador. Quando a persona infantil do PAIciente produz evocação fragmentada de múltiplos passos, o output é *análogo* à limitação da memória de trabalho na PHDA - corresponde ao padrão observável - mas é gerado por restrições de prompt num sistema sem estrangulamento de memória de trabalho. A distinção entre análogo e homólogo (mesmo mecanismo) é crítica para um posicionamento honesto: o PAIciente simula a superfície comportamental da PHDA+POD, não o seu substrato neurocognitivo.

### 2.4 Competência Delimitada

*Competência delimitada* refere-se a desempenho deliberadamente restringido ao longo de dimensões cognitivas, linguísticas, emocionais e comportamentais especificadas. O modelo subjacente é capaz de raciocínio fluente em múltiplos parágrafos, seguimento perfeito de instruções e output afetivamente neutro. O prompt restringe estas capacidades ao longo de eixos clinicamente definidos: função executiva (sequenciamento, estimativa temporal, iniciação de tarefas), regulação emocional (tolerância à frustração, sensibilidade à rejeição), alocação atencional (envolvimento orientado por interesse, hiperfoco), e resposta sociocomportamental (recusa oposicional, condições de adesão).

### 2.5 Monotropismo Arquitetural

O *monotropismo arquitetural* descreve sistemas cuja especialização é alcançada através de modificação irreversível ou de alto custo do substrato do modelo - tipicamente afinação, RLHF com funções de recompensa específicas do domínio, ou alterações arquiteturais (camadas adaptadoras, redes de encaminhamento). Um sistema monotrópico troca capacidade geral por desempenho no domínio. O PAIciente evita explicitamente este compromisso.

---

## 3. Fundamentação: Restrição por Prompt como Fronteira do Sistema

### 3.1 Porquê Não Afinar?

Afinar um modelo para simular uma criança com PHDA+POD exigiria um corpus de treino de discurso infantil anotado fundamentado em perfis clínicos - um corpus que não existe e que levantaria preocupações éticas substanciais na sua construção (dados de sessões clínicas com menores, restrições de consentimento e privacidade, risco de codificar assinaturas comportamentais identificáveis de crianças individuais). Mesmo que tal corpus existisse, a afinação introduziria dois problemas estruturais:

**Erosão de capacidade.** A persona de clínico do PAIciente requer a capacidade analítica, de citação e de raciocínio estruturado plena do modelo. A afinação em discurso infantil degradaria estas capacidades - um fenómeno bem documentado na afinação específica de domínio onde o desempenho fora do domínio declina [achado geral na literatura de aprendizagem por transferência; sem necessidade de citação específica do PAIciente].

**Opacidade.** O perfil comportamental de um modelo afinado está codificado em distribuições de pesos que não são inspecionáveis por humanos. A abordagem restrita por prompt torna a especificação comportamental completa legível, versionável e auditável. Cada restrição sobre a persona infantil - a regra dos 30% de idade emocional de Barkley, as dimensões da POD derivadas de Stringaris, as condições de adesão fundamentadas no CPS - é visível no texto do prompt. Esta transparência não é incidental; é um requisito de design para uma ferramenta destinada a servir populações clínicas e educativas.

### 3.2 O Prompt como Especificação Versionada

Tratar o prompt como a fronteira do sistema produz propriedades de engenharia concretas:

- **Reprodutibilidade.** Dado o mesmo prompt e versão do modelo, o envelope comportamental do sistema é determinístico (módulo variância de amostragem). As sessões podem ser comparadas entre utilizadores.
- **Auditabilidade.** Revisores clínicos podem inspecionar a lógica comportamental completa sem acesso aos internos do modelo. Cada afirmação que o sistema faz sobre comportamento da PHDA ou POD pode ser rastreada até uma cláusula específica do prompt e a sua fonte citada.
- **Portabilidade.** O prompt pode ser implantado em diferentes substratos LLM (Claude, GPT, Gemini, Mistral) com adaptação específica ao substrato mas intenção comportamental idêntica. A avaliação entre plataformas [já conduzida para o PAIciente v2.0] revelou que a fidelidade comportamental varia por substrato, mas a especificação em si é portátil.
- **Iteração baseada em diff.** As alterações comportamentais são patches de prompt - delimitados, revisáveis e reversíveis. Isto espelha a prática de engenharia de software e permite o tipo de desenvolvimento incremental e com confirmação que o PAIciente segue.

---

## 4. Fundamentação: Politropia

### 4.1 As Orientações Funcionais

O PAIciente implementa as seguintes orientações de processamento distintas dentro de um único prompt e sessão:

| Orientação | Gatilho | Contrato de Output | Postura Epistémica |
|---|---|---|---|
| **Persona infantil** | `@child` | Diálogo em personagem; linguagem adequada à idade; output comportamentalmente restringido | Perspetiva delimitada simulada de uma criança de 9 anos |
| **Camada de estado interno** | `@child:inner` | Bloco de anotação estruturado anexado ao output infantil | Metacognitiva - expõe o raciocínio da simulação |
| **Motor de estado** | `@set` | Injeção de parâmetros com validação, deteção de conflitos, tratamento de erros | Programática - opera sobre variáveis de estado |
| **Persona de clínico** | `@clinician` | Análise estruturada (observações / inferências / recomendações); citações | Analítica plena; fundamentada em evidência |
| **Ferramentas de prática** | `@replay`, `@debrief`, `@script`, `@escalation-map` | Output estruturado específico do modo | Varia por ferramenta (reflexiva, generativa, analítica) |

Estas não são variações estilísticas. Diferem na estrutura de output, profundidade de raciocínio, restrições de vocabulário e compromissos epistémicos. A persona infantil suprime capacidade analítica; a persona de clínico exerce-a ao máximo. A camada de estado interno ocupa uma terceira posição - raciocina *sobre* a simulação infantil de fora da perspetiva da criança enquanto a persona infantil está ativa. Esta estrutura triádica (simulação / metacognição / análise) é o design politrópico central.

### 4.2 Porquê Não Multi-Agente?

Uma arquitetura alternativa distribuiria estas orientações por instâncias de modelo separadas ou chamadas API - uma instância para a criança, uma para o clínico, uma para a gestão de estado. Isto evitaria o requisito de politropia mas introduziria:

- **Fragmentação de contexto.** A análise do clínico sobre uma interação infantil requer acesso ao histórico completo da interação, incluindo anotações de estado interno e parâmetros definidos. A distribuição por instâncias requer passagem explícita de contexto, que é com perdas e adiciona latência.
- **Sobrecarga de sincronização de estado.** O sistema `@set` modifica estado que deve ser refletido tanto no comportamento da criança como nas anotações de estado interno. Uma arquitetura multi-agente requer um barramento de estado partilhado, adicionando complexidade de engenharia sem ganho correspondente na qualidade da simulação.
- **Perda de coerência de sessão.** A experiência do utilizador depende de comutação fluida entre personas dentro de um único fluxo conversacional. Arquiteturas multi-agente introduzem latência ao nível do turno e risco de desalinhamento da janela de contexto.

A politropia dentro de uma única janela de contexto evita os três custos. O compromisso é complexidade de prompt - a especificação comportamental inteira deve coexistir num único conjunto de instruções - mas isto é gerível e, como argumentado no ponto 3.2, produz benefícios de transparência.

### 4.3 Politropia vs. Multi-Personalidade

O termo *politrópico* é escolhido deliberadamente em detrimento de alternativas como "multi-persona" ou "multi-personalidade" para evitar duas implicações enganadoras:

1. **Conotação clínica.** "Multi-personalidade" carrega uma associação inevitável com perturbação dissociativa de identidade. As orientações do PAIciente não são personalidades; são modos de processamento engenheirados com comandos de ativação explícitos.
2. **Enquadramento superficial.** "Multi-persona" sugere que a diferença é primariamente estilística (tom, vocabulário, registo). As orientações do PAIciente diferem ao nível estrutural: esquemas de output diferentes, compromissos epistémicos diferentes, conjuntos de restrições diferentes. *Politrópico* destaca a multiplicidade funcional.

---

## 5. Fundamentação: Análogos Comportamentais de Competência Delimitada

### 5.1 A Distinção Análogo/Homólogo

Este é o compromisso conceptual mais importante no enquadramento e o mais vulnerável a má interpretação. O PAIciente não pretende *ter* PHDA ou POD. Não pretende replicar os mecanismos neurocognitivos subjacentes a estas condições. Pretende produzir output comportamental que é *estruturalmente análogo* à superfície comportamental observável de uma criança com estes perfis, conforme caracterizada pela literatura clínica.

A distinção importa por três razões:

**Âmbito honesto.** Pais e clínicos que usam o PAIciente devem compreender que estão a praticar com um modelo de superfície comportamental, não a interagir com um sistema que "compreende" como é ter PHDA. O enquadramento por analogia previne a sobre-afirmação.

**Critérios de fidelidade da simulação.** Se o PAIciente reivindicasse homologia mecanicista, a fidelidade teria de ser avaliada contra medidas neurocognitivas (testes de capacidade de memória de trabalho, ensaios de controlo inibitório, correlatos de neuroimagem). O enquadramento por analogia define o critério de fidelidade ao nível comportamental: o output corresponde ao que a literatura clínica descreve como comportamento observável? Isto é avaliável por clínicos que revisam transcrições, não por instrumentação neurocognitiva.

**Posicionamento ético.** Afirmar que um LLM "tem" uma condição neurodesenvolvimental seria enganador e potencialmente prejudicial - poderia trivializar a experiência vivida de indivíduos com estas condições. O enquadramento por analogia desvincula explicitamente a identidade mecanicista enquanto preserva a utilidade prática da simulação.

### 5.2 O Que É Delimitado

As fronteiras de competência específicas implementadas na persona infantil do PAIciente são derivadas da literatura clínica:

**Restrições de função executiva.** A teoria unificada da PHDA de Barkley [1] posiciona a inibição comportamental como o défice central, com comprometimentos a jusante na memória de trabalho, autorregulação do afeto e da ativação, discurso internalizado e reconstituição (a capacidade de decompor e recombinar sequências comportamentais). A persona infantil do PAIciente implementa análogos destes comprometimentos: perde o fio de instruções com múltiplos passos (memória de trabalho), responde impulsivamente antes de as perguntas terminarem (inibição), escala sob frustração (regulação do afeto) e tem dificuldade com sequenciamento de tarefas e estimativa temporal (reconstituição, processamento temporal). O tratamento mais amplo das funções executivas por Barkley [3] e o manual clínico [4] fornecem o enquadramento para calibrar a gravidade e interação destas restrições.

**Atraso na regulação emocional.** A heurística de Barkley de que crianças com PHDA funcionam a aproximadamente 70% da sua idade cronológica na autorregulação emocional (a "regra dos 30%") é implementada diretamente: as respostas emocionais da persona infantil são calibradas para aproximadamente 6,5-7 anos para uma personagem de 9 anos. Isto manifesta-se como menor tolerância à frustração, maior sensibilidade à rejeição e maior dificuldade com transições do que seria esperado para a idade cronológica.

**Estrutura de resposta oposicional.** Em vez de implementar a POD como desafio uniforme, o PAIciente baseia-se no modelo tridimensional de Stringaris e Goodman [6] - dimensões irritável, teimosa e prejudicial - e na análise bifatorial de Burke et al. [7] que confirma a irritabilidade como dimensão clínica distinta. O comportamento oposicional da persona infantil não é resistência aleatória; é contextualmente desencadeado por perceção de injustiça, autoridade arbitrária, perda de autonomia ou interação orientada pelo controlo - consistente com a interpretação de competências em atraso de Greene [12, 13] e a ênfase da literatura sobre POD no contexto funcional [8, 9, 10].

**Condições de adesão.** A adesão da persona infantil não é binária (obedecer/recusar) mas condicional a fatores interacionais identificáveis: provisão de autonomia, raciocínio transparente, perceção de justiça, arquitetura de escolha e estado de regulação do cuidador. Isto modela o achado bem estabelecido de que o comportamento oposicional na POD não é rigidez ao nível do traço mas uma resposta ao stress modulada por variáveis relacionais e contextuais [8, 11, 12]. A implicação prática é que os utilizadores que praticam com o PAIciente podem observar resultados diferenciais de diferentes abordagens interacionais - a simulação responde à estratégia, não apenas a comandos.

**Interação de comorbilidade.** A comorbilidade PHDA+POD não é implementada como duas listas de sintomas independentes somadas. Os efeitos de interação são modelados: os défices de função executiva reduzem o limiar para ativação oposicional (a criança tem menos recursos regulatórios para gerir a frustração); a recusa orientada pela POD compõe o evitamento de tarefas orientado pela PHDA; o estado de medicação (`@set medication`) modula ambos os perfis simultaneamente. Isto reflete as altas taxas de comorbilidade documentadas na literatura meta-analítica [18] e a evidência de neuroimagem para correlatos neurais partilhados e distintos [19].

### 5.3 Como a Delimitação É Alcançada

O mecanismo de delimitação é inteiramente baseado em prompt. Cláusulas específicas do prompt restringem:

- **Vocabulário e sintaxe**: output adequado à idade, com exceções para domínios de hiperfoco (onde o vocabulário pode exceder o dos pares, de acordo com o perfil clínico).
- **Profundidade de raciocínio**: a persona infantil não produz raciocínio analítico, explicação causal do seu próprio comportamento ou argumentação estruturada - estes são reservados para a persona de clínico.
- **Amplitude afetiva**: as respostas emocionais são calibradas pela regra dos 30%; a sensibilidade à rejeição é explicitamente parametrizada.
- **Lógica de adesão**: regras condicionais especificam quando a criança adere, resiste, escala ou se retira, com base na abordagem interacional e nos parâmetros de estado atuais.
- **Prevenção de fuga de informação**: a persona infantil é explicitamente restringida de divulgar contexto injetado (`@set context`), explicar a sua própria história de fundo ou sair da personagem para fornecer informação clínica. Se a pressão conversacional forçasse tal divulgação, o prompt especifica comportamentos de desvio (silêncio, mudança de tema, resposta monossilábica).

Nenhuma destas restrições modifica os pesos do modelo. Operam como regras comportamentais interpretadas no momento da inferência. O modelo retém capacidade plena; o prompt canaliza-a.

---

## 6. Fundamentação: Verificação Estruturada

### 6.1 O Problema da Verificação

Simulação comportamental sem verificação é simulação sem responsabilização. Se um utilizador interage com a persona infantil e observa escalada, precisa de saber: a escalada foi orientada pela lógica interna da simulação (os parâmetros de estado, o antecedente interacional, o modelo de trajetória), ou foi um artefacto de geração estocástica? Sem mecanismos de verificação, a simulação é uma caixa negra que por acaso produz output de aparência plausível.

O PAIciente aborda isto através de quatro subsistemas de verificação:

### 6.2 Anotações de Estado Interno (`@child:inner`)

Quando ativa, a camada de estado interno anexa um bloco estruturado a cada resposta da criança:

```
[INNER STATE]
Feeling: <rótulo de emoção>
Arousal: low / medium / high / overloaded
What would help right now: <1 coisa concreta>
What just made it worse: <1 coisa concreta, ou "nothing">
Escalation path:
  Trajectory: stable / building / near-threshold / at-threshold
  Next likely behavior: <1 linha comportamentalmente específica>
  Interrupt lever: <1 ação concreta do cuidador>
```

Isto serve três funções de verificação:

- **Transparência do raciocínio da simulação.** O utilizador pode inspecionar *porquê* a criança respondeu como respondeu - não apenas o que disse, mas que estado emocional, nível de ativação e trajetória de escalada a simulação atribuiu à interação.
- **Responsabilização preditiva.** Os campos "next likely behavior" e "interrupt lever" comprometem a simulação com previsões que o utilizador pode testar nos turnos seguintes. Se a simulação prevê "a criança vai bater com a porta" e a alavanca de interrupção é "oferecer uma pausa de 2 minutos," o utilizador pode experimentar a alavanca e avaliar se a simulação segue a sua própria lógica.
- **Rastreamento de proveniência do estado.** Quando os parâmetros `@set` estão ativos, o bloco de estado interno marca cada campo com `<- [SET]` (injetado pelo utilizador) ou `<- [organic]` (derivado da interação). Isto distingue entre estado controlado pelo utilizador e derivado pela simulação, prevenindo confusão.

### 6.3 Motor de Estado Programável (`@set`)

O sistema `@set` permite aos utilizadores injetar condições iniciais específicas - nível de ativação, trajetória, confiança, fadiga, estado de medicação, alvo de hiperfoco e história contextual - e observar como a simulação se comporta a partir desse ponto de partida. Isto possibilita:

- **Comparação controlada.** A mesma abordagem interacional pode ser testada contra diferentes estados iniciais (p. ex., alta-ativação/baixa-confiança vs. baixa-ativação/alta-confiança), isolando o efeito das variáveis de estado nos resultados comportamentais.
- **Reprodutibilidade de cenários.** Formadores clínicos podem especificar configurações de estado exatas para exercícios de formação, garantindo que múltiplos formandos encontrem a mesma condição inicial simulada.
- **Teste de casos-limite.** Configurações de estado extremas (p. ex., `arousal=overloaded trajectory=at-threshold trust=low medication=wearing-off`) testam a lógica comportamental da simulação em condições-limite.

O sistema inclui validação formal: valores fora do intervalo produzem erros tipificados; combinações de parâmetros internamente inconsistentes produzem avisos explícitos; a simulação prossegue com os valores declarados mas sinaliza a inconsistência. Isto previne comportamento silencioso de lixo-entra/lixo-sai.

### 6.4 Análise Post-Hoc (`@debrief`)

O comando `@debrief` comuta automaticamente para a persona de clínico e produz uma análise estruturada da interação infantil precedente. Isto é verificação por revisão especializada: a persona de clínico, operando a capacidade analítica plena, avalia a interação usando o mesmo formato estruturado (observações -> inferências -> recomendações) que um clínico humano poderia usar em supervisão. O estado da criança é suspenso, não limpo, permitindo ao utilizador retomar a interação infantil após a debriefing.

### 6.5 Ciclo de Prática (`@replay`)

O comando `@replay` re-emite o último turno da criança com o mesmo estado, e depois solicita ao utilizador que tente uma abordagem alternativa. Isto cria um ciclo experimental controlado: mesmas condições iniciais, intervenção diferente, resultado diferencial observável. O modelo não gera automaticamente a alternativa - o utilizador deve fornecê-la - preservando a função de prática (o utilizador é o aprendiz, não o observador).

---

## 7. Fundamentação: Rejeição do Monotropismo Arquitetural

### 7.1 O Compromisso do Monotropismo

O monotropismo arquitetural - especializar um modelo através de afinação, moldagem de recompensa ou modificação estrutural - compra desempenho no domínio ao custo de capacidade geral. Para sistemas de propósito único, este compromisso é frequentemente aceitável. Para o PAIciente, é estruturalmente incompatível com os requisitos de design.

A incompatibilidade central é o **requisito de politropia** (ponto 4). O PAIciente deve suportar simultaneamente:

- Uma persona infantil que *suprime* raciocínio analítico, mantém vocabulário adequado à idade e segue lógica de adesão condicional.
- Uma persona de clínico que *maximiza* raciocínio analítico, cita evidência revista por pares e produz avaliação clínica estruturada.
- Um motor de estado que executa validação de parâmetros, deteção de conflitos e tratamento formal de erros.
- Uma camada de estado interno que produz anotações metacognitivas sobre a lógica interna da simulação infantil.

Estas orientações fazem exigências opostas sobre a capacidade do modelo. Um modelo afinado para produzir output infantil degradaria em tarefas do modo clínico. Um modelo afinado para análise clínica resistiria a produzir o output restringido, fragmentado e emocionalmente reativo requerido pela persona infantil. O controlo ao nível do prompt evita isto deixando o espaço de capacidade completo do substrato intacto e selecionando dele por orientação.

### 7.2 Portabilidade Entre Plataformas

O PAIciente foi avaliado em cinco substratos LLM: Claude Projects, ChatGPT CustomGPT, Mistral Agents, Gemini Gems e Grok. Esta avaliação é possível *porque* o sistema não é arquiteturalmente monotrópico - é uma especificação portátil que pode ser instanciada em qualquer LLM suficientemente capaz. Sistemas monotrópicos afinados estão, por definição, bloqueados ao seu substrato de treino.

O design não-monotrópico torna esta avaliação entre plataformas estruturalmente possível - a mesma especificação comportamental pode ser instanciada em cada substrato e a fidelidade de simulação resultante comparada. Esta comparação não poderia ser conduzida se o PAIciente estivesse arquiteturalmente vinculado a um único substrato através de afinação ou modificação de pesos.

### 7.3 O Argumento do Substrato de Uso Geral

O argumento a favor de um substrato de uso geral não é meramente pragmático (portabilidade, evitamento de custos). É estrutural. A *qualidade* da simulação infantil depende do conhecimento latente do substrato sobre psicologia do desenvolvimento, dinâmicas comportamentais e enquadramentos clínicos. Um LLM de uso geral treinado em corpora amplos codificou - nas suas distribuições de pesos - padrões estatísticos da literatura clínica, psicologia educacional, investigação em desenvolvimento infantil e discurso naturalista. O prompt não precisa de ensinar ao modelo o que a PHDA parece; precisa de *ativar e restringir* conhecimento existente.

A afinação num corpus estreito sobrescreveria parte deste conhecimento latente com padrões específicos do domínio, potencialmente reduzindo a capacidade da simulação de responder flexivelmente a abordagens interacionais novas. A abordagem restrita por prompt preserva a base de conhecimento latente completa e dirige-a através de regras comportamentais.

---

## 8. Posicionamento do PAIciente Entre Categorias Adjacentes

A declaração de enquadramento posiciona o PAIciente fora de várias categorias adjacentes. As distinções merecem ser explicitadas.

### 8.1 Não É uma Persona de Chatbot

Personas de chatbot padrão (bots de atendimento ao cliente com tons "amigáveis", assistentes de escrita criativa com "vozes de personagem") operam ao nível estilístico - ajustam registo, vocabulário e afeto sem implementar lógica comportamental estruturada, gestão de estado ou mecanismos de verificação. A persona infantil do PAIciente não é uma configuração de tom; é uma especificação comportamental com regras de adesão condicional, trajetórias de escalada, estado parametrizado e anotações preditivas. A distinção é entre *estilo* (como algo é dito) e *lógica comportamental* (o que é dito sob que condições e porquê).

### 8.2 Não É uma Ferramenta Clínica Afinada

As ferramentas clínicas de PLN afinadas para tarefas específicas (rastreio diagnóstico, recomendação de tratamento, extração de sintomas) são arquiteturalmente monotrópicas por design - trocam generalidade por precisão no domínio. O PAIciente não é uma ferramenta clínica neste sentido. Não diagnostica, rastreia ou recomenda tratamento. Fornece um *ambiente de prática* - uma simulação que responde a estratégia interacional de formas clinicamente fundamentadas, emparelhada com uma persona analítica que explica as dinâmicas. O sistema desvincula-se explicitamente de função clínica nas suas restrições de prompt.

### 8.3 Não É um Andaime de Jogo de Papéis Não Estruturado

Prompts de jogo de papéis não estruturados ("finja ser uma criança com PHDA") produzem output variável e inverificável sem gestão de estado, sem lógica de escalada, sem mecanismo de verificação e sem fundamentação em evidência. O output pode ser plausível em turnos individuais mas carece de coerência comportamental entre turnos, não tem mecanismo para comparação controlada e não pode ser inspecionado quanto ao raciocínio da simulação. A contribuição do PAIciente é precisamente a camada estruturada que transforma jogo de papéis em simulação responsabilizável.

---

## 9. Implicações

### 9.1 Para Avaliação de Fidelidade da Simulação

O enquadramento determina o que conta como fidelidade. Porque o PAIciente implementa análogos comportamentais (não homólogos mecanicistas), a avaliação de fidelidade deve visar a superfície comportamental: a resposta da criança simulada a uma estratégia interacional validada (p. ex., CPS Plano B [12, 13], elogio rotulado estilo PCIT [14]) produz resultados consistentes com a descrição da literatura clínica de como crianças com PHDA+POD respondem a essas estratégias? Esta é uma proposição testável que não requer instrumentação neurocognitiva.

### 9.2 Para Expectativas dos Utilizadores

O enquadramento define expectativas honestas. Os utilizadores devem compreender que estão a praticar com um modelo comportamental, não uma criança digital. As respostas da simulação são governadas por regras de prompt e inferência do modelo, não por uma experiência interna de diferença neurodesenvolvimental. Esta distinção deve ser explicitada em toda a documentação orientada ao utilizador.

### 9.3 Para Extensão e Contribuição

A arquitetura restrita por prompt e não-monotrópica significa que estender o PAIciente (adicionar novos perfis comportamentais, novas ferramentas clínicas, novos mecanismos de avaliação) requer apenas modificação do prompt - sem retreino, sem acesso a pesos, sem alterações de infraestrutura. Isto baixa a barreira de contribuição e permite iteração orientada pela comunidade, consistente com o compromisso de código aberto do projeto.

---

## 10. Limitações

**Teto da simulação.** Os análogos comportamentais têm um teto de fidelidade. O modelo não consegue simular diferenças de processamento sensorial, ativação fisiológica ou estados somáticos que influenciam o comportamento em crianças reais. Comportamentos que dependem fortemente destes (p. ex., alterações de apetite relacionadas com medicação, sobrecarga sensorial em ambientes ruidosos) podem ser aproximados ao nível do output comportamental mas não fundamentados mecanisticamente.

**Variância estocástica.** Sistemas restritos por prompt herdam a variância de amostragem do modelo subjacente. Duas execuções a partir de estados e inputs idênticos podem produzir outputs diferentes. O sistema `@set` reduz mas não elimina isto - restringe condições iniciais, não a trajetória generativa completa.

**Dependência do substrato.** Apesar da portabilidade, a fidelidade comportamental varia entre substratos LLM. Alguns modelos resistem a manter capacidade analítica suprimida no modo infantil; outros ativam filtros de segurança de conteúdo em diálogo oposicional. A especificação do prompt é portátil; a qualidade da sua execução não é garantida.

**Sem validação empírica.** Os análogos comportamentais do PAIciente são fundamentados na literatura clínica, mas a simulação em si não foi empiricamente validada contra interações clínicas reais. Se os utilizadores que praticam com o PAIciente transferem competências para interações do mundo real com crianças com PHDA+POD é uma questão empírica em aberto.

---

## 11. Conclusão

O enquadramento do PAIciente como um *sistema politrópico restrito por prompt que implementa análogos comportamentais de competência delimitada e verificação estruturada sem monotropismo arquitetural* não é terminologia decorativa. Cada termo identifica um compromisso de design específico com implicações concretas de engenharia e clínicas:

- *Restrito por prompt* assegura transparência, auditabilidade e portabilidade.
- *Politrópico* permite orientações co-residentes de simulação e análise dentro de uma única sessão.
- *Análogos comportamentais* definem âmbito honesto e critérios de fidelidade apropriados.
- *Competência delimitada* fundamenta as restrições da simulação em evidência clínica citada.
- *Sem monotropismo arquitetural* preserva o substrato de uso geral requerido para politropia e implantação entre plataformas.

Juntos, estes compromissos definem um espaço de design que é distinto de personas de chatbot, ferramentas clínicas afinadas e andaimes de jogo de papéis não estruturados. O enquadramento torna explícito o que o PAIciente é, o que não é e em que termos a sua fidelidade de simulação deve ser avaliada.

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

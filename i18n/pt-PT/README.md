# Traduções — Português Europeu (PT-PT)

Esta pasta contém traduções em português europeu de componentes selecionados do PAIciente.

## Notas importantes

- O **inglês (EN)** é a língua canónica do projeto. Toda a documentação de referência encontra-se em `/docs/` e `/references/`.
- As traduções contidas nesta pasta são contribuições da comunidade e podem não acompanhar a versão mais recente da documentação em inglês.
- O **system prompt não requer tradução**. O PAIciente responde automaticamente na língua utilizada pelo utilizador — a gestão linguística é nativa ao funcionamento do modelo.

## Ficheiros traduzidos

| Ficheiro original | Tradução | Versão base |
|---|---|---|
| `README.md` | [`/README.pt.md`](/README.pt.md) | v2.1.0 |
| `docs/overview.md` | [`docs/overview.md`](docs/overview.md) | v2.1.0 |
| `docs/personas.md` | [`docs/personas.md`](docs/personas.md) | v2.1.0 |
| `docs/workflow.md` | [`docs/workflow.md`](docs/workflow.md) | v2.1.0 |
| `docs/limitations.md` | [`docs/limitations.md`](docs/limitations.md) | v2.1.0 |
| `docs/use-cases.md` | [`docs/use-cases.md`](docs/use-cases.md) | v2.1.0 |
| `docs/inner-state-guide.md` | [`docs/inner-state-guide.md`](docs/inner-state-guide.md) | v2.1.0 |
| `CONTRIBUTING.md` | [`CONTRIBUTING.md`](CONTRIBUTING.md) | v2.1.0 |

Para o estado completo de todas as traduções, consulte [`/i18n/STATUS.md`](/i18n/STATUS.md).

## Convenções de tradução

- Utilizar português europeu (PT-PT), não português do Brasil (PT-BR).
- Registo formal, consistente com contexto clínico e educativo.
- ADHD = PHDA (Perturbação de Hiperatividade e Défice de Atenção).
- ODD = POD (Perturbação de Oposição e Desafio).
- Todos os comandos `@` permanecem em inglês.
- Os rótulos dos campos `[INNER STATE]` permanecem em inglês.
- Na primeira utilização de termos clínicos, incluir o equivalente em inglês entre parênteses quando a tradução for ambígua.

## Como contribuir

1. Consulte as instruções gerais em [`/CONTRIBUTING.md`](/CONTRIBUTING.md) e as convenções i18n em [`/i18n/README.md`](/i18n/README.md).
2. Crie o ficheiro traduzido nesta pasta, mantendo a estrutura e os nomes de ficheiro originais.
3. Inclua o cabeçalho de versão i18n como primeira linha do ficheiro.
4. Submeta via pull request com a etiqueta `i18n`.

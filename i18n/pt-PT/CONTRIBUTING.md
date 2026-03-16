<!-- i18n: source=CONTRIBUTING.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# Contribuir para o PAIciente

## Submeter uma transcrição de exemplo

1. Escolha uma pasta de cenário em `examples/` ou crie uma nova para um cenário novo.
2. Siga o esquema em [`examples/format.md`](/examples/format.md) exatamente.
3. Nomeie o seu ficheiro de acordo com a plataforma utilizada (ex.: `claude.md`, `chatgpt.md`, `gemini.md`).
4. A transcrição deve exercitar, no mínimo: `@clinician`, `@child` e um de `@debrief` ou `@replay`.
5. Submeta via pull request.

## Submeter uma tradução

1. As traduções estão organizadas em `i18n/` por localidade (ex.: `i18n/pt-PT/`, `i18n/es/`).
2. Crie a pasta da sua localidade caso não exista.
3. Traduza o ficheiro alvo, mantendo o nome e a estrutura originais do ficheiro.
4. Mantenha todos os comandos (`@clinician`, `@child`, `@debrief`, `@set`, etc.) em inglês.
5. Inclua o cabeçalho de versão i18n como primeira linha do ficheiro.
6. Indique no cabeçalho a versão EN de referência utilizada na tradução.
7. Submeta via pull request com a etiqueta `i18n`.

## Reportar uma imprecisão clínica

Se identificar uma afirmação clínica, detalhe de modelo comportamental ou referência que seja imprecisa ou enganosa:

1. Abra uma Issue no GitHub.
2. Utilize a etiqueta `clinical-review`.
3. Descreva a imprecisão, cite o ficheiro e a linha específicos, e forneça uma fonte corretiva se disponível.

## Propor uma extensão de comando

Se pretender propor um novo comando ou modificação a um existente:

1. Abra uma Issue no GitHub.
2. Utilize a etiqueta `protocol-extension`.
3. Descreva o comando proposto, o seu propósito, o comportamento esperado e a que persona se aplica.

## Código de conduta

Espera-se que os contribuidores participem de boa-fé. A crítica clínica é bem-vinda.

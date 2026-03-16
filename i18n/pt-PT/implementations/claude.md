<!-- i18n: source=implementations/claude.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# PAIciente no Claude

## Como instanciar

### Passo 1 — Criar um novo Projeto

1. Aceda a [claude.ai](https://claude.ai) e inicie sessão (conta gratuita ou Pro).
2. Na barra lateral esquerda, clique em **Projects**.
3. Clique em **Create Project** e atribua um nome (ex.: "PAIciente").

### Passo 2 — Colar o system prompt

1. Abra o ficheiro `/prompt/system-prompt.md` neste repositório e copie todo o seu conteúdo.
2. No Projeto que acabou de criar, clique no campo **Project Instructions** (por vezes identificado como "Set custom instructions").
3. Cole o system prompt completo, tal como está. Não o modifique — o PAIciente gere a língua e o contexto nativamente.

### Passo 3 — Iniciar uma sessão

1. Abra uma nova conversa dentro do Projeto.
2. O system prompt está agora ativo. O PAIciente responderá de acordo com as suas instruções desde a primeira mensagem.

## Notas

- **Não é partilhável publicamente.** Os Projetos Claude são privados da conta que os cria. Não existe ligação pública nem mecanismo de loja. Cada utilizador deve auto-instanciar seguindo os passos acima.
- **Compatibilidade com o nível gratuito.** O PAIciente funciona no nível gratuito do Claude. Utilizadores do nível gratuito têm acesso a Projetos e podem colar instruções personalizadas. A utilização está sujeita aos limites de mensagens padrão do nível gratuito.

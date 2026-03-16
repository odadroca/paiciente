<!-- i18n: source=implementations/mistral.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# PAIciente no Mistral
---
### Ligacao sandbox:
* Restricao da plataforma: o utilizador deve ter sessao iniciada com 1 conta Mistral (Le Chat Free parece funcionar):
  https://chat.mistral.ai/chat/553205e3-526a-472d-99d0-0916596fa54b

---
## Como instanciar

### Passo 1 - Criar um Agente no Le Chat

1. Aceda a [chat.mistral.ai](https://chat.mistral.ai) e inicie sessao (uma conta gratuita e suficiente).
2. Na barra lateral esquerda, clique em **Agents**.
3. Clique em **Create Agent**.

### Passo 2 - Colar o system prompt

1. Defina o **Name** como "PAIciente" e adicione uma breve descricao.
2. Abra o ficheiro `/prompt/system-prompt.md` neste repositorio e copie todo o seu conteudo.
3. Cole o system prompt completo no campo **Behavior**. Nao o modifique — o PAIciente gere a lingua e o contexto nativamente.

### Passo 3 - OPCIONAL - Definir visibilidade como Publica

1. Nas definicoes do agente, defina **Visibility** como **Public**.
2. Guarde o agente.
3. Copie a ligacao publica para partilhar com os utilizadores.


## Notas

- **Compatibilidade com o nivel gratuito.** A criacao e utilizacao de agentes no Le Chat esta disponivel no nivel gratuito. Nenhuma subscricao paga e necessaria para criar ou utilizar o PAIciente no Mistral.

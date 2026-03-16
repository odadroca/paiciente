<!-- i18n: source=implementations/chatgpt.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# PAIciente no ChatGPT

---
### Ligação sandbox:
* Funciona sem login na plataforma - restrições do nível gratuito serão aplicadas, mas funciona razoavelmente bem
  https://chatgpt.com/g/g-69b1a7644f5c81919f3fca1bbc2926fa-paiciente-v2-0

---
## Como instanciar

### Passo 1 - Criar um Custom GPT

1. Aceda a [chatgpt.com](https://chatgpt.com) e inicie sessão com uma conta **Plus ou Pro**. (A criação de Custom GPT requer uma subscrição paga.)
2. Clique no ícone do seu perfil no canto inferior esquerdo e selecione **My GPTs**.
3. Clique em **Create a GPT**.

### Passo 2 - Colar o system prompt

1. No editor do GPT, mude para o separador **Configure**.
2. Defina o **Name** como "PAIciente" e adicione uma breve descrição.
3. Abra o ficheiro `/prompt/system-prompt.md` neste repositório e copie todo o seu conteúdo.
4. Cole o system prompt completo no campo **Instructions**. Não o modifique — o PAIciente gere a língua e o contexto nativamente.
5. Em Capabilities, desative Code Interpreter, DALL-E e Web Browsing, salvo se tiver um motivo específico para os ativar.

### Passo 3 - OPCIONAL - Publicar na GPT Store

1. Clique em **Save** e selecione **Publish to > Everyone**.
2. O GPT será revisto e listado na GPT Store.
3. Partilhe a ligação pública com os utilizadores.

## Notas

- **A criação de GPTs requer Plus ou Pro.** Utilizadores do nível gratuito não podem criar Custom GPTs - mas podem usar a sandbox:
	- **Utilizadores do nível gratuito podem aceder à GPT Store.** Qualquer pessoa com uma conta ChatGPT gratuita pode usar um GPT publicado através da sua ligação na store — não precisa de subscrição paga para o *usar*.
	- **Limites de taxa em sessões multi-turno no nível gratuito.** Utilizadores do nível gratuito estão sujeitos a limites de taxa mais rigorosos (mensagens por hora/dia). Sessões prolongadas podem ser interrompidas por limitação de taxa. O utilizador terá de esperar e retomar.

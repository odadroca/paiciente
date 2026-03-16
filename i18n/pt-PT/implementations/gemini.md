<!-- i18n: source=implementations/gemini.md | base-version=v2.1.0 | last-updated=2026-03-16 -->
# PAIciente no Gemini
---
### Ligacao sandbox:
* Restricao da plataforma: o utilizador deve ter sessao iniciada com 1 conta Google:
  https://gemini.google.com/gem/1N5cyhZd34Pb-KEzMxdsaZxjSt7jKF4jm?usp=sharing

---
## Como instanciar

### Passo 1 — Criar um Gem

1. Aceda a [gemini.google.com](https://gemini.google.com) num **navegador de desktop**. (A criacao de Gems nao esta disponivel na aplicacao movel a data desta publicacao.)
2. Inicie sessao com a sua conta Google (o nivel gratuito e suficiente).
3. Na barra lateral esquerda, clique em **Gem manager** e depois em **Create Gem**.

### Passo 2 — Colar o system prompt

1. Defina o **Name** como "PAIciente".
2. Abra o ficheiro `/prompt/system-prompt.md` neste repositorio e copie todo o seu conteudo.
3. Cole o system prompt completo no campo **Instructions**. Nao o modifique — o PAIciente gere a lingua e o contexto nativamente.
4. Clique em **Save**.

### Passo 3 - OPCIONAL - Partilhar via ligacao

1. Abra o seu Gem guardado e clique no botao **Share**.
2. Defina as permissoes de partilha (estilo Google Drive: "Anyone with the link" ou restrito).
3. Copie a ligacao de partilha.


## Notas

- **Compatibilidade com o nivel gratuito.** A criacao e utilizacao de Gems esta disponivel no nivel gratuito do Gemini. Nenhuma subscricao paga e necessaria.
- **Apenas desktop para criacao.** Os Gems devem ser criados em gemini.google.com num navegador de desktop. Uma vez criados, podem ser utilizados em dispositivos moveis.
- **Limite da janela de contexto no nivel gratuito.** O nivel gratuito tem uma janela de contexto de 32.000 tokens. Sessoes multi-turno prolongadas (conversas terapeuticas longas) podem atingir este limite, altura em que as partes iniciais da conversa serao removidas do contexto. Os utilizadores em sessoes mais longas devem estar cientes de que a continuidade pode degradar-se.
- **Disponibilidade na UE/PT.** Os utilizadores na UE e em Portugal acedem ao Gemini atraves da aplicacao para consumidores (gemini.google.com), nao atraves da API. Todas as instrucoes acima aplicam-se ao percurso da aplicacao para consumidores.

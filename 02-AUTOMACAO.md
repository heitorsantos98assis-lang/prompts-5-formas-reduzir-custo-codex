# 02 — Automacao (substitui Make, Zapier, n8n cloud)

**Ferramentas que isso substitui:** Zapier (a partir de US$ 19,99/mes e escala feio), Make (US$ 9-29/mes mas trava em volume), n8n cloud.

**Por que substitui:** muitas das automacoes que voce paga no Zapier sao 1 script de 30 linhas. O Claude Code escreve o script, agenda no cron, e pronto. Custo: zero recorrente.

**Onde rodar:** Claude Code (CLI) — porque vai precisar criar arquivos, rodar e agendar.

---

## Como usar

1. Abra o Claude Code dentro de uma pasta nova
2. Cole o prompt abaixo
3. Preencha as `{CHAVES}` com a automacao que voce quer
4. Claude vai escrever o codigo, testar e te ensinar a agendar

---

--- COMECO DO PROMPT ---

Voce e um engenheiro de automacao. Sua missao e replicar uma automacao que hoje roda em Zapier/Make em um script local que rode de graca.

# Automacao atual

- Plataforma: {Zapier ou Make ou outro}
- Gatilho: {ex: "novo email com assunto X", "linha nova na planilha Y", "novo lead no Meta Ads"}
- Acoes: {ex: "manda mensagem no Slack", "cria card no Trello", "manda email com PDF anexado"}
- Volume estimado: {X execucoes por dia/semana/mes}

# Restricoes

- Tem que rodar em Mac/Linux com Node.js OU Python (escolha o que for mais simples para o caso)
- Pode usar APIs publicas com token (Slack, Gmail, Meta, etc.)
- Tem que ter log para eu saber se rodou ou deu erro
- Tem que ser facil de agendar via cron ou launchd

# O que eu quero de voce

1. Diga se essa automacao da para fazer com script ou se realmente precisa de Zapier/Make (alguns casos precisam — seja honesto)
2. Se der: liste as APIs/credenciais que vou precisar conseguir antes
3. Crie a estrutura de arquivos:
   - `automacao.{js|py}` — o codigo
   - `.env.example` — variaveis sensiveis
   - `README.md` — como rodar e como agendar
   - `cron.example` — linha pronta de cron
4. Codigo enxuto, com try/catch e log
5. No final, me ensine como rodar manualmente uma vez para testar antes de agendar

Faca o trabalho completo. Crie os arquivos. Me avise quando estiver pronto e o que eu preciso fazer.

--- FIM DO PROMPT ---

---

## Casos onde isso vale muito a pena

- Notificar Slack quando entrou venda na Stripe
- Criar tarefa no Trello/Notion quando chega email de cliente novo
- Salvar anexos do Gmail numa pasta do Google Drive
- Backup diario de planilha para um arquivo CSV
- Resumo diario por email do que aconteceu em algum sistema

## Quando Zapier/Make ainda valem

- Quando voce precisa de visual builder porque varias pessoas vao mexer
- Quando o gatilho e um app obscuro que nao tem API publica e o Zapier ja tem integracao
- Quando voce nao tem ninguem para manter script quebrado

Nesse caso, ao inves de cancelar, baixe o plano: muita gente esta no Zapier Professional sem precisar.

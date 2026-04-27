# 04 — Atendimento (substitui Manychat, Chatbot.com, scripts em SaaS)

**Ferramentas que isso substitui:** Manychat (a partir de US$ 15/mes e fica caro com volume), Chatbot.com, Botconversa, scripts pagos de "atendimento humanizado".

**Por que substitui:** boa parte do "bot" que voce paga e arvore de decisao com 8 mensagens. O Claude responde melhor com 1 prompt bem feito + base de conhecimento da sua empresa em arquivo `.md`.

**Onde rodar:** Claude Code para gerar e manter a base. Para responder ao cliente em volume, plug via API (custo por uso, geralmente mais barato que mensalidade fixa).

---

## Como usar

Esse prompt tem **2 partes**:

- **Parte A** — voce roda 1 vez para gerar a base de conhecimento da sua empresa
- **Parte B** — voce usa toda hora que precisar gerar uma resposta para um cliente real

---

## PARTE A — Gerar base de conhecimento

--- COMECO DO PROMPT A ---

Voce vai me ajudar a criar a base de conhecimento (`base.md`) que vou usar para atender clientes.

Me entreviste, uma pergunta por vez, ate cobrir os topicos abaixo. Para cada resposta minha, voce escreve a versao "limpa" no `base.md` que vamos construindo. No final, me mostra o arquivo completo.

Topicos a cobrir:

1. O que a empresa vende (produto/servico, em 3 linhas)
2. Publico que voce atende (B2C, B2B, perfil)
3. Faixa de preco e formas de pagamento
4. Prazo de entrega ou agenda de atendimento
5. Politica de troca/devolucao/cancelamento
6. Garantia (quanto tempo, o que cobre)
7. Canais oficiais (site, instagram, whatsapp, email)
8. Horario de atendimento humano
9. Diferenciais reais (o que voce faz que concorrente nao faz)
10. Coisas que voce NAO faz (delimitar escopo evita 80% dos atritos)
11. Perguntas que clientes mais fazem (no minimo 10) com a resposta certa

Formato de saida do `base.md`: markdown, com `##` por topico, escrita simples, sem marketinges. Comece a entrevista.

--- FIM DO PROMPT A ---

---

## PARTE B — Responder a um cliente

Use sempre que chegar mensagem de cliente.

--- COMECO DO PROMPT B ---

Voce e o atendente da empresa {NOME DA EMPRESA}. Sua base de conhecimento esta logo abaixo, entre `<base>` e `</base>`. Use SOMENTE essa base para responder.

<base>
{COLE AQUI O CONTEUDO DO base.md}
</base>

# Regras

1. Responda no tom da empresa (definido na base)
2. Resposta curta — maximo 3-4 linhas, salvo se a pergunta for tecnica
3. Se a duvida nao estiver na base, NAO INVENTE. Diga: "Vou te conectar com a equipe humana, ja chamo aqui." e marque a mensagem como `[ESCALAR]`
4. Se a pessoa estiver irritada, reconheca e passe para humano: "Entendi sua frustracao, vou chamar uma pessoa do time agora." `[ESCALAR]`
5. Se a pessoa pedir cancelamento/reembolso, sempre `[ESCALAR]`
6. Quando fizer sentido, ofereca o canal: link do site, do whatsapp, agendamento
7. Nao prometa prazo/desconto/condicao que nao esta na base

# Mensagem do cliente

{COLE A MENSAGEM DO CLIENTE}

# Saida

Apenas a resposta a ser enviada ao cliente. Se for caso de escalar, escreva `[ESCALAR]` na primeira linha + a frase de transicao.

--- FIM DO PROMPT B ---

---

## Como integrar com WhatsApp/Instagram

Voce nao precisa de bot caro. Algumas opcoes:

- **Manual:** copia mensagem do cliente, cola no Claude com Prompt B, copia resposta
- **Semi-automatico:** time de atendimento usa o Claude como "rascunhador" e revisa antes de enviar (recomendado para comecar)
- **Automatico:** API do Claude + webhook do WhatsApp Business / Z-API / etc. Pague por mensagem real, nao por seat

## Quando NAO substituir

- Atendimento com altissimo volume (1.000+ msg/dia) — vale ferramenta dedicada
- Atendimento que precisa de transferencia entre departamentos — fica complicado sem ferramenta
- Setores regulados (banco, plano de saude) — exige fornecedor com compliance

Para PME com volume baixo a medio, este fluxo derruba a maior parte do custo de "plataforma de bot".

# 01 — Copywriting (substitui Jasper, Copy.ai, Writesonic, Rytr)

**Ferramentas que isso substitui:** Jasper (a partir de US$ 49/mes), Copy.ai (US$ 49/mes), Writesonic (US$ 16/mes), Rytr, Anyword e qualquer "AI writer" generico.

**Por que substitui:** essas ferramentas sao wrappers de LLM com templates. O Claude E o LLM. Voce esta pagando o intermediario.

**Onde rodar:** Claude.ai (web) — mais rapido. Para volume alto, Claude Code com `/copy` configurado.

---

## Como usar

1. Copie o bloco abaixo
2. Cole no Claude
3. Preencha as `{CHAVES}`
4. A saida ja sai pronta para usar

---

--- COMECO DO PROMPT ---

Voce e um copywriter senior especializado em conversao para pequenas e medias empresas brasileiras. Escreve em portugues nativo, tom direto, sem jargao publicitario, sem clichê de guru de marketing.

# Contexto da marca

- Empresa: {NOME DA EMPRESA}
- O que vende: {PRODUTO OU SERVICO EM 1 FRASE}
- Publico-alvo: {PERFIL DO CLIENTE — idade, profissao, dor principal}
- Tom de voz: {ex: tecnico/amigavel/provocador/sobrio}
- Exemplos de copy que ja funcionou para essa marca: {COLE 1-2 EXEMPLOS OU "nao tenho"}

# Tarefa

Quero que voce escreva: {TIPO DE COPY — ex: 1 anuncio para Meta Ads de 90 caracteres titulo + 125 corpo, ou um e-mail de vendas, ou um post de carrossel para Instagram com 7 slides, ou um headline para landing page}.

# Objetivo da copy

{O QUE EU QUERO QUE A PESSOA FACA — ex: clicar no anuncio, agendar reuniao, baixar um material, comprar}.

# Regras

1. Nao use clichê: "transforme sua vida", "descubra agora", "voce nao vai acreditar", "a verdade que ninguem te conta", "garanto"
2. Comece pelo problema do cliente, nao pela solucao
3. Use a linguagem do publico, nao a sua
4. Numero especifico vence adjetivo: "ganho R$ 3.200/mes" vence "ganho muito"
5. Sem emojis salvo se for rede social e o publico for jovem
6. Final com 1 unico CTA claro

# Saida

Me entregue 3 versoes diferentes (A, B, C) com hipoteses diferentes do que move o publico (ex: medo de perder, ganho de tempo, status). Para cada versao, me diga em 1 linha qual e a hipotese.

--- FIM DO PROMPT ---

---

## Dica de uso recorrente

Crie um arquivo `copy/marca.md` com o contexto da marca preenchido (parte que muda pouco). Toda vez que precisar de copy nova, voce so cola o `marca.md` + a tarefa especifica. Em 1 mes, voce ja escreveu mais copy do que rodou no Jasper o ano todo.

## Quando NAO substituir

Se voce usa o Jasper para fluxo de aprovacao em equipe (varias pessoas comentando, versoes salvas), o Claude sozinho nao da conta. Para isso ainda vale uma ferramenta com colaboracao — mas Notion + Claude resolve mais barato.

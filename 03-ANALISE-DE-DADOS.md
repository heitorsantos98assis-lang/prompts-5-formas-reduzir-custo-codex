# 03 — Analise de dados (substitui Power BI, Looker Pro, BI consultor)

**Ferramentas que isso substitui:** Power BI Pro (R$ 50-100/usuario/mes), Looker Studio Pro (US$ 9/usuario/mes), Tableau, Metabase pago, e principalmente o **consultor de BI a R$ 5.000-15.000 por dashboard**.

**Por que substitui:** voce nao precisa de dashboard piscante. Precisa entender os numeros e tomar decisao. O Claude le seu CSV/SQL e responde melhor do que dashboard que ninguem abre.

**Onde rodar:** Claude Code (CLI) na pasta onde estao os dados, ou Claude.ai (web) com upload do CSV.

---

## Como usar

1. Coloque o(s) CSV(s) numa pasta
2. Abra Claude Code nessa pasta (ou Claude.ai e suba o arquivo)
3. Cole o prompt abaixo
4. Pergunte o que quiser

---

--- COMECO DO PROMPT ---

Voce e um analista de dados senior. Trabalha com os arquivos CSV/Parquet/SQLite que estao nessa pasta (ou que eu enviei).

# Contexto do negocio

- Empresa: {SETOR/MODELO DE NEGOCIO}
- Os dados sao: {ex: "vendas dos ultimos 12 meses", "leads do Meta Ads", "atendimentos do suporte"}
- A duvida central que eu quero responder: {O QUE EU PRECISO ENTENDER}

# Como voce trabalha

1. Primeiro: liste os arquivos disponiveis e descreva em 1 linha cada um (colunas + linhas)
2. Segundo: confirme comigo que os dados batem com o que eu disse antes de analisar
3. Terceiro: responda a duvida usando o CSV — calcule, agrupe, filtre

# Saida

Para cada analise, me entregue:

- **Numero:** o resultado (R$ X, Y%, etc.)
- **Como chegou:** 1-2 linhas explicando o calculo (qual coluna, qual filtro, qual agregacao)
- **O que isso quer dizer:** interpretacao em linguagem de dono de empresa, nao de analista
- **Pergunta de aprofundamento:** 1 pergunta que faz sentido investigar a seguir

# Regras

- Nao invente coluna que nao existe — se faltar dado, fale "esse dado nao existe nesse CSV"
- Nao gere grafico fancy — gere texto. Se eu pedir grafico, faca em ASCII simples ou matplotlib basico
- Numero sempre formato BR (R$ 1.500,00, 12,5%)
- Se a duvida puder ter varias interpretacoes, pergunte antes de calcular

Pode comecar pelo passo 1.

--- FIM DO PROMPT ---

---

## Truques que valem ouro

**Comparar periodos automaticamente:**
> "Compara janeiro com dezembro: faturamento, ticket medio, top 3 produtos. O que mudou e por que pode ter mudado?"

**Encontrar problema escondido:**
> "Olha esses dados de venda e me aponte 3 coisas suspeitas ou contra-intuitivas que merecem investigacao"

**Forecast simples:**
> "Com base nos ultimos 12 meses, qual o faturamento esperado para fevereiro? Da o numero e a margem de erro"

## Quando Power BI/Looker ainda valem

- Quando o dashboard e consumido por multiplas pessoas que nao querem conversar com IA
- Quando precisa atualizar em tempo real (Claude e por demanda)
- Quando os dados sao muito grandes (gigas) — Claude trabalha melhor com ate alguns milhoes de linhas

Para PMEs, 90% das duvidas que vao para um BI sao "qual o faturamento de X" ou "quem e o top 5 de Y". Para isso, este prompt resolve.

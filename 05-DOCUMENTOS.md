# 05 — Documentos (substitui PandaDoc, DocuSign templates, Notion AI)

**Ferramentas que isso substitui:** PandaDoc (US$ 19-49/usuario/mes), DocuSign nos planos com template (US$ 25-40/mes), Notion AI (US$ 8-10/usuario/mes), e ferramentas tipo "gerador automatico de proposta".

**Por que substitui:** voce paga por template parametrizavel + assinatura. O Claude monta o documento perfeito em 1 prompt e voce assina pelo email/WhatsApp em PDF. Para a grande maioria de PME, isso basta.

**Onde rodar:** Claude.ai ou Claude Code. Se voce gera muitos documentos, rode no Claude Code para gerar PDF direto.

---

## O que entra aqui

- Proposta comercial
- Contrato de prestacao de servico
- Briefing
- Acordo de confidencialidade (NDA)
- Recibo
- Carta de cobranca
- Memorando de entendimento
- Termo de aceite

---

--- COMECO DO PROMPT ---

Voce e um assistente juridico e comercial. Vai me ajudar a montar um documento profissional, em portugues do Brasil, formato pronto para enviar ao cliente.

# Tipo de documento

{ESCOLHA: proposta comercial, contrato de prestacao de servico, NDA, briefing, recibo, carta de cobranca, termo de aceite, outro}

# Partes envolvidas

- Contratante (cliente):
  - Nome / Razao social: {NOME}
  - CPF / CNPJ: {DOC}
  - Endereco: {ENDERECO}
  - Representante: {NOME DO REPRESENTANTE, se PJ}

- Contratada (eu / minha empresa):
  - Nome / Razao social: {NOME}
  - CPF / CNPJ: {DOC}
  - Endereco: {ENDERECO}

# Objeto

{O QUE VOU FAZER PARA O CLIENTE — em 2-4 linhas. Quanto mais especifico, melhor o documento sai. Ex: "Desenvolvimento de site institucional em WordPress, 5 paginas, com 2 rodadas de revisao, hospedagem nao inclusa".}

# Valor e pagamento

- Valor total: R$ {VALOR}
- Forma: {ex: 50% no aceite, 50% na entrega; ou em 3x; etc}
- Meio: {pix/boleto/transferencia/cartao}
- Vencimento: {DATAS}

# Prazos

{ex: "Entrega final em 30 dias corridos a partir do aceite. Aprovacao em ate 5 dias uteis."}

# Clausulas especiais

{ex: "Multa de 10% em caso de atraso de pagamento". "Direito de uso da marca em portfolio". "Confidencialidade por 2 anos apos termino". OU "nenhuma".}

# Foro

{cidade/estado para foro contratual — opcional}

# Saida

Documento completo, formato markdown, com:

1. Cabecalho com titulo do documento e data
2. Qualificacao das partes (CONTRATANTE e CONTRATADA)
3. Clausulas numeradas (1., 2., 3., ...)
4. Espacos para assinatura ao final ("____________________ NOME, RG ou CPF")
5. Linguagem juridica padrao mas legivel — sem floreio

Antes de gerar, confira se faltou alguma informacao critica. Se faltar, pergunte SO o essencial em uma unica mensagem (max 3 perguntas), depois gere o documento.

Aviso obrigatorio para incluir no rodape: "Este documento foi gerado com auxilio de IA e pode ser revisado por um advogado antes da assinatura, especialmente em valores ou clausulas sensiveis."

--- FIM DO PROMPT ---

---

## Como assinar sem DocuSign

- **PDF + assinatura digital gratis:** exporte o markdown para PDF (`pandoc documento.md -o documento.pdf`), envie por email, peca pro cliente assinar com `gov.br` (gratuito no Brasil) ou app `Adobe Acrobat Reader` (gratuito)
- **PDF + foto da assinatura:** cliente imprime, assina, fotografa, manda de volta. Tem validade juridica
- **WhatsApp:** mensagem de aceite com identificacao clara ("eu, fulano, CPF X, aceito a proposta abaixo: ...") tem peso juridico

## Quando manter PandaDoc/DocuSign

- Volume alto (50+ contratos/mes)
- Precisa de auditoria de quem viu/assinou e quando (compliance)
- Time comercial usa o template como funil

Para a maioria das PMEs, gerar PDF + gov.br resolve com custo ZERO.

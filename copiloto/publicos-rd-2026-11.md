# Públicos a partir da base RD Station (export de 06/11/2026)

**Nenhum dado pessoal neste repositório.** Os arquivos ficam só na pasta temporária da sessão (scratchpad/rd_out), em duas versões: `_plano.csv` (normalizado, para subir no Gerenciador) e `_hash.csv` (SHA-256, para envio via API).

## Base
- 85.566 contatos no export (UTF-16, tab, 123 colunas).
- **8.696 excluídos** por "Base legal para comunicação = Recusado" (LGPD).
- 75.685 válidos (com e-mail ou telefone válido), deduplicados por e-mail.

## Formato (padrão Meta, colunas reconhecidas automaticamente)
`email, phone, fn, ln, ct, st, country, doby, dobm, dobd, gen`
- e-mail minúsculo e validado; telefone só dígitos com 55 (DDI) + DDD; nome/sobrenome minúsculos sem acento; cidade sem espaço/acento; UF em 2 letras; país `br`; nascimento separado em ano/mês/dia; gênero f/m.
- Quanto mais colunas preenchidas, maior a taxa de correspondência no Meta.

## Segmentos gerados
| Arquivo | Contatos | Regra |
|---|---|---|
| 01_base_completa | 75.685 | todos com consentimento |
| 02_clientes | 13.179 | estágio Cliente, situação Pago ou com data de última venda |
| 03_engajados | 36.711 | Lead Scoring Interesse > 0, ou ≥3 conversões, ou última conversão desde mai/2026 |
| 04_leads_2026 | 25.904 | última conversão em 2026 |
| 05_black_anteriores | 11.087 | evento ou tag com "black" (BF 2020–2025) |
| 06_enam | 14.847 | evento ou tag com "enam" |
| 07_carrinho_abandonado | 2.508 | não-cliente com boleto vencido/aguardando/cancelado ou "interessado-curso-carrinho-fechado" |
| 08_clicou_whatsapp | 13.271 | evento btn-wpp-2 / wpp-g7 |

## Engajamento de e-mail no export
- O export **não traz aberturas/cliques de e-mail por contato**. A coluna "Eventos" lista conversões (formulários, compras), não aberturas.
- Há só tags manuais antigas (2021–2023) do tipo "abriu/não abriu e-mail X" — desatualizadas.
- Melhor sinal disponível: **Lead Scoring – Interesse** (13.560 com nota > 0), que no RD sobe com interações (e-mail, páginas, conversões).
- Para aberturas/cliques recentes: criar no RD uma **segmentação** "abriu (ou clicou) qualquer e-mail nos últimos 30/60/90 dias" e exportar.

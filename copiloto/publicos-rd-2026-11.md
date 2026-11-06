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

## Públicos criados no Meta (06/11/2026) — ainda VAZIOS, aguardando upload da lista
| Público | ID |
|---|---|
| [RD 2026-11] 01 Base completa (consentimento) | 120253765428130247 |
| [RD 2026-11] 02 Clientes | 120253765428250247 |
| [RD 2026-11] 03 Engajados | 120253765428290247 |
| [RD 2026-11] 04 Leads 2026 | 120253765428330247 |
| [RD 2026-11] 05 Blacks anteriores | 120253765428340247 |
| [RD 2026-11] 06 ENAM | 120253765428500247 |
| [RD 2026-11] 07 Carrinho abandonado | 120253765428570247 |
| [RD 2026-11] 08 Clicou no WhatsApp | 120253765428610247 |
- O envio das listas pela ferramenta do MCP passa os dados linha a linha pela conversa: inviável para ~200 mil linhas. Upload via Gerenciador (arquivos _plano.csv) ou via API direta com token.

## Tamanho após processamento (06/11/2026 ~04:50 UTC)
| Público | Enviados | Tamanho no Meta | Correspondência |
|---|---|---|---|
| Base completa | 75.685 | 53.400–62.800 | 71–83% |
| Engajados | 36.711 | 26.300–30.900 | 72–84% |
| Leads 2026 | 25.904 | 18.700–22.000 | 72–85% |
| Clicou WhatsApp | 13.271 | 9.300–10.900 | 70–82% |
| Clientes | 13.179 | "1.000" (provisório) | a confirmar |
| Blacks anteriores | 11.087 | "1.000" (provisório) | a confirmar |
| ENAM | 14.847 | "1.000" (provisório) | a confirmar |
| Carrinho abandonado | 2.508 | "1.000" (provisório) | a confirmar |

## Semelhantes 1% BR criados em 06/11/2026 (frio, padrão [FRIO] - [SEMELHANTE 1% BR] - ...)
| Origem | Origem ID | Semelhante ID |
|---|---|---|
| Lista RD Base completa | 120253765428130247 | 120253774168240247 |
| Lista RD Clientes | 120253765428250247 | 120253774168360247 |
| Lista RD Engajados | 120253765428290247 | 120253774168670247 |
| Lista RD Leads 2026 | 120253765428330247 | 120253774169050247 |
| Lista RD Blacks anteriores | 120253765428340247 | 120253774169810247 |
| Lista RD ENAM | 120253765428500247 | 120253774170220247 |
| Lista RD Carrinho abandonado | 120253765428570247 | 120253774170720247 |
| Lista RD Clicou WhatsApp | 120253765428610247 | 120253774171570247 |
| Pixel Cadastrou pág. Black 2026 (60D) | 120253761230230247 | 120253774171810247 |
| Pixel Visitou pág. Black 2026 (60D) | 120253761230320247 | 120253774172790247 |
Obs.: semelhante é montado de forma assíncrona; conferir tamanho antes de usar. Semelhante não pode ser renomeado pela ferramenta (só no Gerenciador).

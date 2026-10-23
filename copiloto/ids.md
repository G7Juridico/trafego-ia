# IDs conhecidos

Cada linha: o que é, ID, origem. Nunca perguntar de novo o que já está aqui.

## Meta Ads — G7 Jurídico (ÚNICA conta em escopo)
| O quê | ID | Origem |
|---|---|---|
| Conta de anúncios "G7 Jurídico" (BRL, ACTIVE, is_queryable=true, mcp_enabled=true, tem pagamento) | `391713394763358` | `ads_get_ad_accounts`, 2026-10-16 |
| Business "G7 Jurídico" | `920832978316686` | idem |
| Página do Facebook "G7 Jurídico" (leadgen ToS aceito) | `1176977359047815` | `ads_get_ad_account_pages` |
| Instagram @g7juridico | `17841404114381646` | `ads_get_ig_accounts` |
| Pixel "Pixel de G7 Jurídico" (criado 2019, ativo, browser+servidor) | `1250040671830251` | `ads_get_datasets` |
| Pixel "Pixel de G7 - Backup" (criado 2025-05, ativo, browser+servidor) | `513428758397125` | `ads_get_datasets` |
| Conversão personalizada "Compra Reta Final ENAM" (PURCHASE, URL cadastro-efetuado-com-sucesso-retafinal-enam2025, último disparo 2025-10-06 — PARADA) | `1268284791577743` | `ads_get_customconversions` |

Outras páginas ligadas à conta (não usar sem pedido): "Renato Brasileiro" `118410271702298`, "Alice Reis" `984607284732952` (leadgen ToS não aceito).

## Fora de escopo
O login do conector dá acesso a mais 25 contas de outros negócios (Espansione, Portal Odonto, Unopar, Cultura Jurídica, NKZ etc.). **Nenhuma delas é G7. Nunca ler nem tocar.**

## Fonte de venda real
| O quê | ID | Origem |
|---|---|---|
| Projeto Supabase "G7Juridico" (vazio em 2026-10-16) | `tzkodhijzreojeswybqu` | Supabase `list_projects` |
| Gateway de pagamento | — desconhecido | — |

## Campanhas criadas pelo copiloto
| O quê | ID | Estado |
|---|---|---|
| Campanha `[G7] - [Vendas] - [01] - [16/10/26] - [Out26] - [Frio]` | `120253401112630247` | rascunho |
| Conjunto `01 - BR - 25/65 - Advantage Aberto` | `120253401114090247` | rascunho |
| Conjunto `02 - BR - 25/65 - Semelhante` | `120253401116470247` | rascunho |
| Conjunto `03 - BR - 25/65 - Advantage Direcionado` | `120253401116530247` | rascunho |

## Padrões de nome (dados pelo usuário)
- Campanha: `[G7] - [Vendas] - [NN] - [dd/mm/aa] - [MesAA] - [Temperatura]`
- Conjunto: `NN - BR - idmin/idmax - Descrição`
| Campanha `[G7] - [Vendas] - [02] - [17/10/26] - [Out26] - [Frio]` (Reta Final ENAM) | `120253403431830247` | rascunho |
| Conjunto `01 - BR - 25/65 - Advantage Aberto` (ENAM) | `120253403446800247` | rascunho |
| Conjunto `02 - BR - 25/65 - Semelhante` (ENAM) | `120253403448980247` | rascunho |
| Conjunto `03 - BR - 25/65 - Advantage Direcionado` (ENAM) | `120253403449640247` | rascunho |

## Links de destino (conferido em 2026-10-20)
| Campanha | Link |
|---|---|
| [G7] 01 Frio (120253401112630247) | `https://www.g7juridico.com.br/` + UTMs `utm_source=meta&utm_medium=paid&utm_campaign={{campaign.name}}&utm_term={{adset.name}}&utm_content={{ad.name}}&utm_placement={{placement}}` |
| [G7] 02 Reta Final ENAM (120253403431830247) | `https://www.g7juridico.com.br/reta-final-enam-2026` + as mesmas UTMs |
| OUT26 01/02/03 (criativos "G7 Jurídico" com 2 imagens) | `https://www.g7juridico.com.br/`. Se há UTM, ela fica em url_tags, que o MCP não lê |
| OUT26 imagem única, CAD26, ISC26, QUE26 | **não exposto pelo MCP** (`link_url` volta vazio; a prévia não mostra o link). Conferir no Gerenciador |

## Campanha [G7] 03 Quente (21/10/26)
| Objeto | ID |
|---|---|
| `[G7] - [Vendas] - [03] - [21/10/26] - [Out26] - [Quente]` (ABO, 28 × R$25/dia) | 120253481075280247 |
| Conjunto 01 (AD029) / anúncio | 120253481085460247 / 120253481088960247 |
| Conjuntos 02–28 | ver diario.md, 2026-10-21/23 |

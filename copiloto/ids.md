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

## Black 2026 — [BLACK26] - [FASE01] - [CAPTAÇÃO] - [QUENTE] - Públicos Personalizados (RASCUNHO, 05/11/2026)
- Campanha 120253759980420247 · Leads · CBO R$500/dia
- Conjunto 120253759985340247 "[BLA26] 01 - Todos os Públicos Personalizados G7" · Conversão Lead (pixel 1250040671830251) · BR 18+ · 176 públicos personalizados ativos (sem semelhantes) · Advantage+ público DESLIGADO (só públicos personalizados) · posicionamentos automáticos
- Lista dos 176 IDs: scratchpad bla26_aud_ids.txt (não versionado; reproduzível pela listagem de públicos)
- Link: https://pg.g7juridico.com.br/black?utm_source=MetaAds&utm_campaign={{campaign.name}}&utm_medium={{adset.name}}&utm_content={{ad.name}}&utm_term={{placement}}&campaign_id={{campaign.id}}&adset_id={{adset.id}}&ad_id={{ad.id}}
- Título "Black 10 anos G7" · Descrição "Entre para o Grupo Oficial" · CTA Saiba mais

| Anúncio | ad_id | creative_id | hash 4:5 (usado) | hash 9:16 (não usado) |
|---|---|---|---|---|
| [BLACK26] - [AD01] - Nós já dissemos sim | 120253760112360247 | 1832002721474793 | 9036553ae04087220c1189f91ddbd17c | 666d87b5e8b9651e1ae59b478a58dae2 |
| [BLACK26] - [AD02] - O que esperar | 120253760112690247 | 971989902199513 | 35ec3fde48b3141e44efcd8033825bb4 | 723c12ff7f3c05c6548390a12c66e86c |
| [BLACK26] - [AD03] - A noite mais importante | 120253760112750247 | 2625148794614768 | dffaadf41b8818510911f1270117d4e1 | f5f8137da457c653d774dcfbc01cd0a5 |
| [BLACK26] - [AD04] - O que mudou no G7 | 120253760112780247 | 4546926822254337 | bceaab475be5d2156d50ffca975c65f4 | 8ebd2f717b0eee6eb87a3e585cab6279 |
| [BLACK26] - [AD05] - 90.000 alunos | 120253760113010247 | 1097732746359217 | 90575b262fd1c13276d4a54f297c7151 | af24dc2af4b32a5f1ebc7a218e503cd0 |
| [BLACK26] - [AD06] - Você conhecerá | 120253760113060247 | 1809616160259473 | 256bb85e139c2472f510a7d84a30e586 | d90272d13b439273d31f9681265588fd |
| [BLACK26] - [AD07] - Motivos | 120253760113210247 | 1681250313581973 | 9e5697503e80fa4872dad3bbe19a7d54 | e9f3a932720c3ef1a0b03f3b592c83ae |
| [BLACK26] - [AD08] - Maratona ENAM | 120253760113630247 | 2515862758901558 | 96af39ec3ad291b621aa9c0d34877516 | 06e2ec5422f0914d805a66923e9822c4 |
| [BLACK26] - [AD09] - Vai prestar o ENAM | 120253760113750247 | 1596887561700307 | 9907004c562c63c0a7d34de5586cc17f | 104878b38a8770dd4e19dde7c69dca37 |
| [BLACK26] - [AD10] - Programação | 120253760114010247 | 1111618914985178 | 36e1ef21af89378663fcdadc7396d1b9 | b7bd1e93eee7b22d6fbaf769c5d186e6 |
| [BLACK26] - [AD11] - Reclame Aqui | 120253760114180247 | 1683597740044568 | 4eaef109fe6fea55d67431f3ed2c03a9 | 06b1ab7c2961ce78f244c089d0e17f4f |
| [BLACK26] - [AD12] - Caixinha Grupo Oficial | 120253760114350247 | 1122745660755056 | 7caed0b2251395dd8d1758ae4fc12f3a | 0072f29d0184ee0ebd5b9851a6a42b2f |
| [BLACK26] - [AD13] - Portal de notícias | 120253760114530247 | 1135050025778658 | 2de2626b36f4ace4f2f27ff366f7cf51 | f8100a83fa90e5556e8e1778be80f556 |

## Black 2026 — campanha quente PUBLICADA E PAUSADA (05/11/2026) — versão corrigida
- Campanha 120253760319570247 "[BLACK26] - [FASE01] - [CAPTAÇÃO] - [QUENTE] - Públicos Personalizados" · Leads · CBO R$500/dia · status PAUSED (live)
- Conjunto 120253760845490247 "[BLACK26] - [QUENTE] - Todos os Públicos Personalizados G7" · Lead pixel Principal · 176 públicos personalizados · A+ público off · status PAUSED
- Anúncios (criativo inline: IG @g7juridico, url_tags com UTMs, link limpo, 26 recursos Advantage+ OFF, CTA só com link):
  AD01 120253760875560247 · AD02 120253760875750247 · AD03 120253760875970247 · AD04 120253760876210247 · AD05 120253760876360247 · AD06 120253760876420247 · AD07 120253760876520247 · AD08 120253760876640247 · AD09 120253760876680247 · AD10 120253760876970247 · AD11 120253760877010247 · AD12 120253760877090247 · AD13 120253760877290247
- A campanha-rascunho anterior (120253759980420247) foi DESCARTADA em 05/11.

## Públicos Black 2026 (criados 05/11/2026, pixel Principal 1250040671830251, retenção 60 dias)
- 120253761230230247 — [BLACK26] Se cadastrou na Black 2026 (Lead pg/black 60D): evento Lead + URL contém pg.g7juridico.com.br/black
- 120253761230320247 — [BLACK26] Visitou página Black 2026 (pg/black 60D): URL contém pg.g7juridico.com.br/black
- "Se cadastrou" EXCLUÍDO do conjunto quente 120253760845490247 (05/11). "Visitou" ainda sem uso.

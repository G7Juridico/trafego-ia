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

## Black 2026 — [02] Quente Listas RD — PUBLICADA E PAUSADA (06/11/2026)
- Campanha 120253773461420247 "[BLACK26] - [FASE01] - [02] - [CAPTAÇÃO] - [QUENTE] - Listas RD" · Leads · CBO R$500/dia · PAUSED
- Conjunto 120253773465330247 "[QUENTE] - Listas RD (8 públicos) - Exc. Cadastrados Black26" · Lead pixel 1250040671830251 · 8 listas RD (1202537654281/2/2/3/3/5/5/6…) · exclui 120253761230230247 · A+ público off · IG stream/story/reels + FB feed/reels · 25-65 BR · PAUSED
- Anúncios (mesmos creative IDs da [01]): AD01 120253773481940247 (cr 2249069179001903) · AD02 120253773482250247 · AD03 120253773482410247 · AD04 120253773482490247 · AD05 120253773482550247 · AD06 120253773482620247 · AD07 120253773482680247 · AD08 120253773482740247 · AD09 120253773482910247 · AD10 120253773483120247 · AD11 120253773483190247 · AD12 120253773483500247 · AD13 120253773483710247
- Correção: creative atual do AD01 da [01] é 2249069179001903 (o 2126281944668030 registrado antes estava desatualizado e tinha variações de texto por IA).
- [01] renomeada para "[BLACK26] - [FASE01] - [01] - [CAPTAÇÃO] - [QUENTE] - Públicos Personalizados".
- Observado em 06/11: a [01] está ATIVA com R$750/dia (alteração feita no Gerenciador às 9:48, antes do copiloto mexer; o copiloto só trocou o nome às 10:16). Gasto hoje até a leitura: R$410,08.

## [02] — 8 conjuntos, 1 lista RD cada (06/11/2026) — publicados PAUSADOS
Mesma config do conjunto combinado (pixel Lead, exclusão cadastrados Black26, A+ off, IG stream/story/reels + FB feed/reels). Conjunto combinado 120253773465330247 mantido pausado.

- 02 - [QUENTE] - Lista Base de Leads · conjunto 120253773613320247
  - anúncios: [AD01] 120253773668170247 · [AD02] 120253773669230247 · [AD03] 120253773669840247 · [AD04] 120253773670910247 · [AD05] 120253773671820247 · [AD06] 120253773672710247 · [AD07] 120253773674640247 · [AD08] 120253773675260247 · [AD09] 120253773676080247 · [AD10] 120253773677300247 · [AD11] 120253773677980247 · [AD12] 120253773678890247 · [AD13] 120253773679330247
- 02 - [QUENTE] - Lista Clientes · conjunto 120253773613390247
  - anúncios: [AD01] 120253773692710247 · [AD02] 120253773693690247 · [AD03] 120253773694400247 · [AD04] 120253773695260247 · [AD05] 120253773696240247 · [AD06] 120253773696660247 · [AD07] 120253773697390247 · [AD08] 120253773698250247 · [AD09] 120253773699080247 · [AD10] 120253773699820247 · [AD11] 120253773701730247 · [AD12] 120253773702870247 · [AD13] 120253773703650247
- 02 - [QUENTE] - Lista Engajados · conjunto 120253773613490247
  - anúncios: [AD01] 120253773666170247 · [AD02] 120253773666670247 · [AD03] 120253773667790247 · [AD04] 120253773668870247 · [AD05] 120253773669560247 · [AD06] 120253773670290247 · [AD07] 120253773671720247 · [AD08] 120253773672610247 · [AD09] 120253773674580247 · [AD10] 120253773675200247 · [AD11] 120253773676230247 · [AD12] 120253773677800247 · [AD13] 120253773678670247
- 02 - [QUENTE] - Lista Leads 2026 · conjunto 120253773613640247
  - anúncios: [AD01] 120253773690840247 · [AD02] 120253773691650247 · [AD03] 120253773692920247 · [AD04] 120253773693740247 · [AD05] 120253773694310247 · [AD06] 120253773695400247 · [AD07] 120253773696220247 · [AD08] 120253773696680247 · [AD09] 120253773697230247 · [AD10] 120253773698140247 · [AD11] 120253773699060247 · [AD12] 120253773699830247 · [AD13] 120253773701780247
- 02 - [QUENTE] - Lista Blacks Anteriores · conjunto 120253773613810247
  - anúncios: [AD01] 120253773663980247 · [AD02] 120253773664880247 · [AD03] 120253773665280247 · [AD04] 120253773666230247 · [AD05] 120253773666700247 · [AD06] 120253773667700247 · [AD07] 120253773668970247 · [AD08] 120253773678080247 · [AD09] 120253773679100247 · [AD10] 120253773680010247 · [AD11] 120253773680730247 · [AD12] 120253773681730247 · [AD13] 120253773682890247
- 02 - [QUENTE] - Lista ENAM · conjunto 120253773614080247
  - anúncios: [AD01] 120253773688910247 · [AD02] 120253773690050247 · [AD03] 120253773690910247 · [AD04] 120253773691750247 · [AD05] 120253773693550247 · [AD06] 120253773694300247 · [AD07] 120253773695550247 · [AD08] 120253773703750247 · [AD09] 120253773704130247 · [AD10] 120253773704390247 · [AD11] 120253773704830247 · [AD12] 120253773705190247 · [AD13] 120253773705890247
- 02 - [QUENTE] - Lista Carrinho Abandonado · conjunto 120253773614410247
  - anúncios: [AD01] 120253773667090247 · [AD02] 120253773668260247 · [AD03] 120253773669210247 · [AD04] 120253773669810247 · [AD05] 120253773671060247 · [AD06] 120253773671960247 · [AD07] 120253773674300247 · [AD08] 120253773675100247 · [AD09] 120253773675730247 · [AD10] 120253773677120247 · [AD11] 120253773677690247 · [AD12] 120253773678100247 · [AD13] 120253773679030247
- 02 - [QUENTE] - Lista Clicou WhatsApp · conjunto 120253773614690247
  - anúncios: [AD01] 120253773690120247 · [AD02] 120253773691360247 · [AD03] 120253773692410247 · [AD04] 120253773693450247 · [AD05] 120253773693980247 · [AD06] 120253773695070247 · [AD07] 120253773695690247 · [AD08] 120253773696450247 · [AD09] 120253773697030247 · [AD10] 120253773697490247 · [AD11] 120253773698610247 · [AD12] 120253773699570247 · [AD13] 120253773700830247

## [03] Frio Semelhantes 1% — publicada PAUSADA (06/11/2026)
- Campanha 120253774299730247 "[BLACK26] - [FASE01] - [03] - [CAPTAÇÃO] - [FRIO] - Semelhantes 1%" · Leads · CBO R$500/dia
- 10 conjuntos (1 semelhante cada), 25-65 BR, A+ público off, mesmos posicionamentos; exclui Cadastrou Black26, Visitou Black26, RD Base completa, RD Clientes. 13 anúncios por conjunto (mesmos creative IDs).
- 03 - [FRIO] - Semelhante 1% Base Completa · conjunto 120253774301140247
  - anúncios: [AD01] 120253774320700247 · [AD02] 120253774320920247 · [AD03] 120253774321120247 · [AD04] 120253774321260247 · [AD05] 120253774321480247 · [AD06] 120253774321670247 · [AD07] 120253774321870247 · [AD08] 120253774322130247 · [AD09] 120253774322520247 · [AD10] 120253774322820247 · [AD11] 120253774322990247 · [AD12] 120253774323170247 · [AD13] 120253774323300247
- 03 - [FRIO] - Semelhante 1% Clientes · conjunto 120253774307480247
  - anúncios: [AD01] 120253774329190247 · [AD02] 120253774332550247 · [AD03] 120253774332900247 · [AD04] 120253774332970247 · [AD05] 120253774333270247 · [AD06] 120253774333350247 · [AD07] 120253774333490247 · [AD08] 120253774336880247 · [AD09] 120253774337130247 · [AD10] 120253774337210247 · [AD11] 120253774337250247 · [AD12] 120253774337400247 · [AD13] 120253774337620247
- 03 - [FRIO] - Semelhante 1% Engajados · conjunto 120253774307530247
  - anúncios: [AD01] 120253774340450247 · [AD02] 120253774340550247 · [AD03] 120253774340760247 · [AD04] 120253774340880247 · [AD05] 120253774341000247 · [AD06] 120253774345160247 · [AD07] 120253774345340247 · [AD08] 120253774348940247 · [AD09] 120253774349060247 · [AD10] 120253774349160247 · [AD11] 120253774349250247 · [AD12] 120253774349330247 · [AD13] 120253774349500247
- 03 - [FRIO] - Semelhante 1% Leads 2026 · conjunto 120253774307660247
  - anúncios: [AD01] 120253774320540247 · [AD02] 120253774320730247 · [AD03] 120253774321330247 · [AD04] 120253774322020247 · [AD05] 120253774322210247 · [AD06] 120253774322610247 · [AD07] 120253774322900247 · [AD08] 120253774323070247 · [AD09] 120253774323220247 · [AD10] 120253774323340247 · [AD11] 120253774323440247 · [AD12] 120253774323560247 · [AD13] 120253774323740247
- 03 - [FRIO] - Semelhante 1% Blacks Anteriores · conjunto 120253774307750247
  - anúncios: [AD01] 120253774333840247 · [AD02] 120253774334030247 · [AD03] 120253774334310247 · [AD04] 120253774334530247 · [AD05] 120253774334700247 · [AD06] 120253774334980247 · [AD07] 120253774335370247 · [AD08] 120253774335540247 · [AD09] 120253774335660247 · [AD10] 120253774335750247 · [AD11] 120253774335850247 · [AD12] 120253774335930247 · [AD13] 120253774336040247
- 03 - [FRIO] - Semelhante 1% ENAM · conjunto 120253774307910247
  - anúncios: [AD01] 120253774340840247 · [AD02] 120253774340950247 · [AD03] 120253774341100247 · [AD04] 120253774341270247 · [AD05] 120253774341590247 · [AD06] 120253774341920247 · [AD07] 120253774342020247 · [AD08] 120253774342120247 · [AD09] 120253774342220247 · [AD10] 120253774342450247 · [AD11] 120253774342590247 · [AD12] 120253774342660247 · [AD13] 120253774342790247
- 03 - [FRIO] - Semelhante 1% Carrinho Abandonado · conjunto 120253774308030247
  - anúncios: [AD01] 120253774320070247 · [AD02] 120253774320260247 · [AD03] 120253774320380247 · [AD04] 120253774320530247 · [AD05] 120253774320740247 · [AD06] 120253774320960247 · [AD07] 120253774321200247 · [AD08] 120253774321430247 · [AD09] 120253774321610247 · [AD10] 120253774321760247 · [AD11] 120253774322010247 · [AD12] 120253774322510247 · [AD13] 120253774322770247
- 03 - [FRIO] - Semelhante 1% Clicou WhatsApp · conjunto 120253774308070247
  - anúncios: [AD01] 120253774332410247 · [AD02] 120253774332890247 · [AD03] 120253774333180247 · [AD04] 120253774333460247 · [AD05] 120253774333650247 · [AD06] 120253774333750247 · [AD07] 120253774333870247 · [AD08] 120253774334060247 · [AD09] 120253774334160247 · [AD10] 120253774334430247 · [AD11] 120253774334600247 · [AD12] 120253774334760247 · [AD13] 120253774335050247
- 03 - [FRIO] - Semelhante 1% Cadastrou Pág. Black 2026 · conjunto 120253774308220247
  - anúncios: [AD01] 120253774320790247 · [AD02] 120253774320950247 · [AD03] 120253774321180247 · [AD04] 120253774321440247 · [AD05] 120253774321640247 · [AD06] 120253774321830247 · [AD07] 120253774322000247 · [AD08] 120253774322160247 · [AD09] 120253774322850247 · [AD10] 120253774322980247 · [AD11] 120253774323160247 · [AD12] 120253774323290247 · [AD13] 120253774323470247
- 03 - [FRIO] - Semelhante 1% Visitou Pág. Black 2026 · conjunto 120253774308440247
  - anúncios: [AD01] 120253774334120247 · [AD02] 120253774334380247 · [AD03] 120253774334570247 · [AD04] 120253774334710247 · [AD05] 120253774334950247 · [AD06] 120253774335360247 · [AD07] 120253774335550247 · [AD08] 120253774335640247 · [AD09] 120253774335710247 · [AD10] 120253774335820247 · [AD11] 120253774335940247 · [AD12] 120253774336120247 · [AD13] 120253774336230247

## [04] Quente Engajamento Instagram (09/11/2026) — PUBLICADA E PAUSADA (6 conjuntos, 78 anúncios conferidos no ar)
- Campanha 120253825630120247 "[BLACK26] - [FASE01] - [04] - [CAPTAÇÃO] - [QUENTE] - Engajamento Instagram" · Leads · CBO R$250/dia
- Públicos IG criados (fonte ig_business 17841404114381646):
  - 120253825628440247 [QUENTE] Enviou mensagem 90D
  - 120253825628510247 [QUENTE] Salvou post ou anúncio 60D
  - 120253825628820247 [QUENTE] Visitou perfil 30D
  - 120253825628840247 [QUENTE] Interagiu com post ou anúncio 30D
  - 120253825628990247 [MORNO] Interagiu com perfil 60D
  - (existente) 23857741862410246 Seguidores IG
- Conjuntos (exc. Cadastrou Black26, A+ off, mesmos posicionamentos): 120253825634430247 Msg · 120253825634600247 Salvou · 120253825634660247 Visitou · 120253825635050247 Interagiu post · 120253825635150247 Interagiu perfil · 120253825635260247 Seguidores
- Reels 50% NÃO criado (precisa escolher vídeos).

## Públicos Facebook + Site criados (09/11/2026)
- 120253826169100247 [QUENTE] [FACEBOOK] Enviou mensagem 90D (page_messaged)
- 120253826169290247 [QUENTE] [FACEBOOK] Interagiu com post ou anúncio 30D (page_post_interaction)
- 120253826169320247 [QUENTE] [FACEBOOK] Visitou página 30D (page_visited)
- 120253826169340247 [MORNO] [FACEBOOK] Interagiu com página 60D (page_engaged)
- 120253826169880247 [QUENTE] [PIXEL] [BLACK26] Visitou Black e NÃO cadastrou 30D
- 120253826169940247 [QUENTE] [PIXEL] [BLACK26] Rolou 75% da página Black 30D
- 120253826169960247 [QUENTE] [PIXEL] [BLACK26] Visitou Black 2+ vezes 30D
- 120253826169970247 [QUENTE] [PIXEL] [CHECKOUT] Iniciou checkout sem comprar 30D
- 120253826170260247 [QUENTE] [PIXEL] [BOLSA] Aplicou para Bolsa G7 60D
- 120253826170320247 [MORNO] [PIXEL] [SITE] Top 25% tempo no site 30D
- Existente reaproveitável: 23849633070450246 Seguidores/curtidores da Página

## [05] Quente Públicos Personalizados — Criativos AD14-AD28 (10/11/2026) — publicada PAUSADA
- Campanha 120253838129080247 "[BLACK26] - [FASE01] - [05] - [CAPTAÇÃO] - [QUENTE] - Públicos Personalizados - Criativos AD14-AD28" · Leads · CBO R$500/dia (ATIVA desde 10/11; nasceu com R$1.250)
- Conjunto 120253838140490247 "05 - [QUENTE] - Todos os Públicos Personalizados G7" · mesma segmentação da [01] (176 públicos, exc. Cadastrou Black26, A+ off, 25-65, IG stream/story/reels + FB feed/reels)
- 25 anúncios: AD14-18 (imagem 4:5+9:16), AD19/21/22/23/24 Claro e Escuro (imagem), AD20/25/26/27/28 Claro e Escuro (vídeo 9:16).
- Copy provisória (usuário não enviou textos): ENAM (AD14, AD15, AD21, AD25) = copy do AD08; demais = copy do AD01.
- 10/11: anúncios ENAM trocados para a copy Black ("Nós já dissemos sim ao presente…") a pedido do usuário. Título "Black 10 anos G7", descrição "Entre para o Grupo Oficial". Publicados sem ativar (conjunto segue PAUSED). Novos creative_ids:
  - AD14 Edital Maratona ENAM — ad 120253838234490247 · creative 1796425354958726
  - AD15 Diário Oficial Maratona ENAM — ad 120253838246040247 · creative 2347712532686103
  - AD21 Chat Maratona ENAM Claro — ad 120253838284710247 · creative 29258282350480140
  - AD21 Chat Maratona ENAM Escuro — ad 120253838284970247 · creative 1000757316403038
  - AD25 Chat Motion Maratona ENAM Claro (vídeo) — ad 120253838228660247 · creative 1581343344009313
  - AD25 Chat Motion Maratona ENAM Escuro (vídeo) — ad 120253838228740247 · creative 2636870620069394
- Fonte: Drive 1FVSAEPunN_fhxqr0j7p1AAHw2d5lTu33. Spec: scratchpad/spec_05.json

## [02] — criativos AD14–AD28 adicionados (12/11/2026) — PUBLICADOS ATIVOS (opção A do usuário)
- 225 anúncios = 25 criativos × 9 conjuntos, reaproveitando os creative_id da [05] (ENAM com copy Black). Status no rascunho: ATIVO (publicar = começa a rodar).

### 02 - [QUENTE] - Lista Clicou WhatsApp (120253773614690247)
- [BLACK26] - [AD14] - Edital Maratona ENAM — 120253872933690247
- [BLACK26] - [AD15] - Diário Oficial Maratona ENAM — 120253872938020247
- [BLACK26] - [AD16] - Diário Oficial Aprovados — 120253872938600247
- [BLACK26] - [AD17] - Edital Cronograma Black — 120253872939450247
- [BLACK26] - [AD18] - Caderno de Prova — 120253872940360247
- [BLACK26] - [AD19] - Chat Black Claro — 120253872940450247
- [BLACK26] - [AD19] - Chat Black Escuro — 120253872940710247
- [BLACK26] - [AD20] - Chat Motion Black Claro — 120253872940910247
- [BLACK26] - [AD20] - Chat Motion Black Escuro — 120253872941010247
- [BLACK26] - [AD21] - Chat Maratona ENAM Claro — 120253872944250247
- [BLACK26] - [AD21] - Chat Maratona ENAM Escuro — 120253872944690247
- [BLACK26] - [AD22] - Chat Nova Área do Aluno Claro — 120253872944920247
- [BLACK26] - [AD22] - Chat Nova Área do Aluno Escuro — 120253872945480247
- [BLACK26] - [AD23] - Chat Black Geral Claro — 120253872950090247
- [BLACK26] - [AD23] - Chat Black Geral Escuro — 120253872950240247
- [BLACK26] - [AD24] - Chat Esperar Claro — 120253872950640247
- [BLACK26] - [AD24] - Chat Esperar Escuro — 120253872950770247
- [BLACK26] - [AD25] - Chat Motion Maratona ENAM Claro — 120253872952690247
- [BLACK26] - [AD25] - Chat Motion Maratona ENAM Escuro — 120253872952820247
- [BLACK26] - [AD26] - Chat Motion Nova Área Claro — 120253872952850247
- [BLACK26] - [AD26] - Chat Motion Nova Área Escuro — 120253872952880247
- [BLACK26] - [AD27] - Chat Motion Black Geral Claro — 120253872955140247
- [BLACK26] - [AD27] - Chat Motion Black Geral Escuro — 120253872955280247
- [BLACK26] - [AD28] - Chat Motion Esperar Claro — 120253872955380247
- [BLACK26] - [AD28] - Chat Motion Esperar Escuro — 120253872955910247

### 02 - [QUENTE] - Lista Carrinho Abandonado (120253773614410247)
- [BLACK26] - [AD14] - Edital Maratona ENAM — 120253872965560247
- [BLACK26] - [AD15] - Diário Oficial Maratona ENAM — 120253872968050247
- [BLACK26] - [AD16] - Diário Oficial Aprovados — 120253872969490247
- [BLACK26] - [AD17] - Edital Cronograma Black — 120253872970470247
- [BLACK26] - [AD18] - Caderno de Prova — 120253872972330247
- [BLACK26] - [AD19] - Chat Black Claro — 120253872973690247
- [BLACK26] - [AD19] - Chat Black Escuro — 120253872975570247
- [BLACK26] - [AD20] - Chat Motion Black Claro — 120253872977730247
- [BLACK26] - [AD20] - Chat Motion Black Escuro — 120253872978840247
- [BLACK26] - [AD21] - Chat Maratona ENAM Claro — 120253872979860247
- [BLACK26] - [AD21] - Chat Maratona ENAM Escuro — 120253872982470247
- [BLACK26] - [AD22] - Chat Nova Área do Aluno Claro — 120253872984980247
- [BLACK26] - [AD22] - Chat Nova Área do Aluno Escuro — 120253872986210247
- [BLACK26] - [AD23] - Chat Black Geral Claro — 120253872987260247
- [BLACK26] - [AD23] - Chat Black Geral Escuro — 120253872989360247
- [BLACK26] - [AD24] - Chat Esperar Claro — 120253872990770247
- [BLACK26] - [AD24] - Chat Esperar Escuro — 120253872992160247
- [BLACK26] - [AD25] - Chat Motion Maratona ENAM Claro — 120253872993750247
- [BLACK26] - [AD25] - Chat Motion Maratona ENAM Escuro — 120253872994590247
- [BLACK26] - [AD26] - Chat Motion Nova Área Claro — 120253872995320247
- [BLACK26] - [AD26] - Chat Motion Nova Área Escuro — 120253872996710247
- [BLACK26] - [AD27] - Chat Motion Black Geral Claro — 120253872997120247
- [BLACK26] - [AD27] - Chat Motion Black Geral Escuro — 120253872998520247
- [BLACK26] - [AD28] - Chat Motion Esperar Claro — 120253872998960247
- [BLACK26] - [AD28] - Chat Motion Esperar Escuro — 120253873000430247

### 02 - [QUENTE] - Lista ENAM (120253773614080247)
- [BLACK26] - [AD14] - Edital Maratona ENAM — 120253872966550247
- [BLACK26] - [AD15] - Diário Oficial Maratona ENAM — 120253872968040247
- [BLACK26] - [AD16] - Diário Oficial Aprovados — 120253872968940247
- [BLACK26] - [AD17] - Edital Cronograma Black — 120253872969970247
- [BLACK26] - [AD18] - Caderno de Prova — 120253872974930247
- [BLACK26] - [AD19] - Chat Black Claro — 120253872975160247
- [BLACK26] - [AD19] - Chat Black Escuro — 120253872977740247
- [BLACK26] - [AD20] - Chat Motion Black Claro — 120253872977960247
- [BLACK26] - [AD20] - Chat Motion Black Escuro — 120253872979430247
- [BLACK26] - [AD21] - Chat Maratona ENAM Claro — 120253872979780247
- [BLACK26] - [AD21] - Chat Maratona ENAM Escuro — 120253872982510247
- [BLACK26] - [AD22] - Chat Nova Área do Aluno Claro — 120253872982710247
- [BLACK26] - [AD22] - Chat Nova Área do Aluno Escuro — 120253872985090247
- [BLACK26] - [AD23] - Chat Black Geral Claro — 120253872985590247
- [BLACK26] - [AD23] - Chat Black Geral Escuro — 120253872987660247
- [BLACK26] - [AD24] - Chat Esperar Claro — 120253872988290247
- [BLACK26] - [AD24] - Chat Esperar Escuro — 120253872992590247
- [BLACK26] - [AD25] - Chat Motion Maratona ENAM Claro — 120253872993480247
- [BLACK26] - [AD25] - Chat Motion Maratona ENAM Escuro — 120253872994640247
- [BLACK26] - [AD26] - Chat Motion Nova Área Claro — 120253872994750247
- [BLACK26] - [AD26] - Chat Motion Nova Área Escuro — 120253872996690247
- [BLACK26] - [AD27] - Chat Motion Black Geral Claro — 120253872996790247
- [BLACK26] - [AD27] - Chat Motion Black Geral Escuro — 120253872997450247
- [BLACK26] - [AD28] - Chat Motion Esperar Claro — 120253872997780247
- [BLACK26] - [AD28] - Chat Motion Esperar Escuro — 120253872998750247

### 02 - [QUENTE] - Lista Blacks Anteriores (120253773613810247)
- [BLACK26] - [AD14] - Edital Maratona ENAM — 120253872933310247
- [BLACK26] - [AD15] - Diário Oficial Maratona ENAM — 120253872937770247
- [BLACK26] - [AD16] - Diário Oficial Aprovados — 120253872938100247
- [BLACK26] - [AD17] - Edital Cronograma Black — 120253872938590247
- [BLACK26] - [AD18] - Caderno de Prova — 120253872939520247
- [BLACK26] - [AD19] - Chat Black Claro — 120253872940400247
- [BLACK26] - [AD19] - Chat Black Escuro — 120253872940540247
- [BLACK26] - [AD20] - Chat Motion Black Claro — 120253872940940247
- [BLACK26] - [AD20] - Chat Motion Black Escuro — 120253872940990247
- [BLACK26] - [AD21] - Chat Maratona ENAM Claro — 120253872944810247
- [BLACK26] - [AD21] - Chat Maratona ENAM Escuro — 120253872945030247
- [BLACK26] - [AD22] - Chat Nova Área do Aluno Claro — 120253872945560247
- [BLACK26] - [AD22] - Chat Nova Área do Aluno Escuro — 120253872945800247
- [BLACK26] - [AD23] - Chat Black Geral Claro — 120253872950750247
- [BLACK26] - [AD23] - Chat Black Geral Escuro — 120253872950950247
- [BLACK26] - [AD24] - Chat Esperar Claro — 120253872951030247
- [BLACK26] - [AD24] - Chat Esperar Escuro — 120253872951350247
- [BLACK26] - [AD25] - Chat Motion Maratona ENAM Claro — 120253872952950247
- [BLACK26] - [AD25] - Chat Motion Maratona ENAM Escuro — 120253872953390247
- [BLACK26] - [AD26] - Chat Motion Nova Área Claro — 120253872953510247
- [BLACK26] - [AD26] - Chat Motion Nova Área Escuro — 120253872953960247
- [BLACK26] - [AD27] - Chat Motion Black Geral Claro — 120253872956020247
- [BLACK26] - [AD27] - Chat Motion Black Geral Escuro — 120253872956120247
- [BLACK26] - [AD28] - Chat Motion Esperar Claro — 120253872956370247
- [BLACK26] - [AD28] - Chat Motion Esperar Escuro — 120253872956700247

### 02 - [QUENTE] - Lista Leads 2026 (120253773613640247)
- [BLACK26] - [AD14] - Edital Maratona ENAM — 120253872967120247
- [BLACK26] - [AD15] - Diário Oficial Maratona ENAM — 120253872968680247
- [BLACK26] - [AD16] - Diário Oficial Aprovados — 120253872969940247
- [BLACK26] - [AD17] - Edital Cronograma Black — 120253872971080247
- [BLACK26] - [AD18] - Caderno de Prova — 120253872973210247
- [BLACK26] - [AD19] - Chat Black Claro — 120253872975100247
- [BLACK26] - [AD19] - Chat Black Escuro — 120253872976670247
- [BLACK26] - [AD20] - Chat Motion Black Claro — 120253872978850247
- [BLACK26] - [AD20] - Chat Motion Black Escuro — 120253872979790247
- [BLACK26] - [AD21] - Chat Maratona ENAM Claro — 120253872982330247
- [BLACK26] - [AD21] - Chat Maratona ENAM Escuro — 120253872983330247
- [BLACK26] - [AD22] - Chat Nova Área do Aluno Claro — 120253872985210247
- [BLACK26] - [AD22] - Chat Nova Área do Aluno Escuro — 120253872986650247
- [BLACK26] - [AD23] - Chat Black Geral Claro — 120253872988220247
- [BLACK26] - [AD23] - Chat Black Geral Escuro — 120253872990460247
- [BLACK26] - [AD24] - Chat Esperar Claro — 120253872991950247
- [BLACK26] - [AD24] - Chat Esperar Escuro — 120253872993730247
- [BLACK26] - [AD25] - Chat Motion Maratona ENAM Claro — 120253872994570247
- [BLACK26] - [AD25] - Chat Motion Maratona ENAM Escuro — 120253872995460247
- [BLACK26] - [AD26] - Chat Motion Nova Área Claro — 120253872996980247
- [BLACK26] - [AD26] - Chat Motion Nova Área Escuro — 120253872998040247
- [BLACK26] - [AD27] - Chat Motion Black Geral Claro — 120253872998680247
- [BLACK26] - [AD27] - Chat Motion Black Geral Escuro — 120253872999220247
- [BLACK26] - [AD28] - Chat Motion Esperar Claro — 120253873001090247
- [BLACK26] - [AD28] - Chat Motion Esperar Escuro — 120253873001710247

### 02 - [QUENTE] - Lista Engajados (120253773613490247)
- [BLACK26] - [AD14] - Edital Maratona ENAM — 120253872965570247
- [BLACK26] - [AD15] - Diário Oficial Maratona ENAM — 120253872969390247
- [BLACK26] - [AD16] - Diário Oficial Aprovados — 120253872969570247
- [BLACK26] - [AD17] - Edital Cronograma Black — 120253872969850247
- [BLACK26] - [AD18] - Caderno de Prova — 120253872975070247
- [BLACK26] - [AD19] - Chat Black Claro — 120253872975170247
- [BLACK26] - [AD19] - Chat Black Escuro — 120253872975650247
- [BLACK26] - [AD20] - Chat Motion Black Claro — 120253872984650247
- [BLACK26] - [AD20] - Chat Motion Black Escuro — 120253872985060247
- [BLACK26] - [AD21] - Chat Maratona ENAM Claro — 120253872985460247
- [BLACK26] - [AD21] - Chat Maratona ENAM Escuro — 120253872988080247
- [BLACK26] - [AD22] - Chat Nova Área do Aluno Claro — 120253872988540247
- [BLACK26] - [AD22] - Chat Nova Área do Aluno Escuro — 120253872989410247
- [BLACK26] - [AD23] - Chat Black Geral Claro — 120253872992560247
- [BLACK26] - [AD23] - Chat Black Geral Escuro — 120253872993450247
- [BLACK26] - [AD24] - Chat Esperar Claro — 120253872993570247
- [BLACK26] - [AD24] - Chat Esperar Escuro — 120253872995510247
- [BLACK26] - [AD25] - Chat Motion Maratona ENAM Claro — 120253872996170247
- [BLACK26] - [AD25] - Chat Motion Maratona ENAM Escuro — 120253872996680247
- [BLACK26] - [AD26] - Chat Motion Nova Área Claro — 120253872998050247
- [BLACK26] - [AD26] - Chat Motion Nova Área Escuro — 120253872998430247
- [BLACK26] - [AD27] - Chat Motion Black Geral Claro — 120253872998530247
- [BLACK26] - [AD27] - Chat Motion Black Geral Escuro — 120253873000440247
- [BLACK26] - [AD28] - Chat Motion Esperar Claro — 120253873000980247
- [BLACK26] - [AD28] - Chat Motion Esperar Escuro — 120253873001060247

### 02 - [QUENTE] - Lista Clientes (120253773613390247)
- [BLACK26] - [AD14] - Edital Maratona ENAM — 120253872935530247
- [BLACK26] - [AD15] - Diário Oficial Maratona ENAM — 120253872938840247
- [BLACK26] - [AD16] - Diário Oficial Aprovados — 120253872939470247
- [BLACK26] - [AD17] - Edital Cronograma Black — 120253872940380247
- [BLACK26] - [AD18] - Caderno de Prova — 120253872940490247
- [BLACK26] - [AD19] - Chat Black Claro — 120253872940900247
- [BLACK26] - [AD19] - Chat Black Escuro — 120253872944270247
- [BLACK26] - [AD20] - Chat Motion Black Claro — 120253872944740247
- [BLACK26] - [AD20] - Chat Motion Black Escuro — 120253872945010247
- [BLACK26] - [AD21] - Chat Maratona ENAM Claro — 120253872945780247
- [BLACK26] - [AD21] - Chat Maratona ENAM Escuro — 120253872945900247
- [BLACK26] - [AD22] - Chat Nova Área do Aluno Claro — 120253872966520247
- [BLACK26] - [AD22] - Chat Nova Área do Aluno Escuro — 120253872968060247
- [BLACK26] - [AD23] - Chat Black Geral Claro — 120253872969550247
- [BLACK26] - [AD23] - Chat Black Geral Escuro — 120253872970930247
- [BLACK26] - [AD24] - Chat Esperar Claro — 120253872973200247
- [BLACK26] - [AD24] - Chat Esperar Escuro — 120253872975130247
- [BLACK26] - [AD25] - Chat Motion Maratona ENAM Claro — 120253872976730247
- [BLACK26] - [AD25] - Chat Motion Maratona ENAM Escuro — 120253872978720247
- [BLACK26] - [AD26] - Chat Motion Nova Área Claro — 120253872979550247
- [BLACK26] - [AD26] - Chat Motion Nova Área Escuro — 120253872981650247
- [BLACK26] - [AD27] - Chat Motion Black Geral Claro — 120253872982850247
- [BLACK26] - [AD27] - Chat Motion Black Geral Escuro — 120253872985080247
- [BLACK26] - [AD28] - Chat Motion Esperar Claro — 120253872986510247
- [BLACK26] - [AD28] - Chat Motion Esperar Escuro — 120253872988050247

### 02 - [QUENTE] - Lista Base de Leads (120253773613320247)
- [BLACK26] - [AD14] - Edital Maratona ENAM — 120253872966970247
- [BLACK26] - [AD15] - Diário Oficial Maratona ENAM — 120253872968130247
- [BLACK26] - [AD16] - Diário Oficial Aprovados — 120253872969670247
- [BLACK26] - [AD17] - Edital Cronograma Black — 120253872970690247
- [BLACK26] - [AD18] - Caderno de Prova — 120253872972650247
- [BLACK26] - [AD19] - Chat Black Claro — 120253872975120247
- [BLACK26] - [AD19] - Chat Black Escuro — 120253872976640247
- [BLACK26] - [AD20] - Chat Motion Black Claro — 120253872978890247
- [BLACK26] - [AD20] - Chat Motion Black Escuro — 120253872979880247
- [BLACK26] - [AD21] - Chat Maratona ENAM Claro — 120253872982580247
- [BLACK26] - [AD21] - Chat Maratona ENAM Escuro — 120253872984560247
- [BLACK26] - [AD22] - Chat Nova Área do Aluno Claro — 120253872986260247
- [BLACK26] - [AD22] - Chat Nova Área do Aluno Escuro — 120253872987280247
- [BLACK26] - [AD23] - Chat Black Geral Claro — 120253872990100247
- [BLACK26] - [AD23] - Chat Black Geral Escuro — 120253872991720247
- [BLACK26] - [AD24] - Chat Esperar Claro — 120253872993230247
- [BLACK26] - [AD24] - Chat Esperar Escuro — 120253872994460247
- [BLACK26] - [AD25] - Chat Motion Maratona ENAM Claro — 120253872994930247
- [BLACK26] - [AD25] - Chat Motion Maratona ENAM Escuro — 120253872996700247
- [BLACK26] - [AD26] - Chat Motion Nova Área Claro — 120253872997130247
- [BLACK26] - [AD26] - Chat Motion Nova Área Escuro — 120253872997770247
- [BLACK26] - [AD27] - Chat Motion Black Geral Claro — 120253872998620247
- [BLACK26] - [AD27] - Chat Motion Black Geral Escuro — 120253872999080247
- [BLACK26] - [AD28] - Chat Motion Esperar Claro — 120253873001040247
- [BLACK26] - [AD28] - Chat Motion Esperar Escuro — 120253873001700247

### 01 - [QUENTE] - Listas RD (8 públicos) - Exc. Cadastrados Black26 (120253773465330247)
- [BLACK26] - [AD14] - Edital Maratona ENAM — 120253872965400247
- [BLACK26] - [AD15] - Diário Oficial Maratona ENAM — 120253872967520247
- [BLACK26] - [AD16] - Diário Oficial Aprovados — 120253872968610247
- [BLACK26] - [AD17] - Edital Cronograma Black — 120253872969790247
- [BLACK26] - [AD18] - Caderno de Prova — 120253872970980247
- [BLACK26] - [AD19] - Chat Black Claro — 120253872973090247
- [BLACK26] - [AD19] - Chat Black Escuro — 120253872975060247
- [BLACK26] - [AD20] - Chat Motion Black Claro — 120253872976330247
- [BLACK26] - [AD20] - Chat Motion Black Escuro — 120253872978120247
- [BLACK26] - [AD21] - Chat Maratona ENAM Claro — 120253872979240247
- [BLACK26] - [AD21] - Chat Maratona ENAM Escuro — 120253872981090247
- [BLACK26] - [AD22] - Chat Nova Área do Aluno Claro — 120253872982530247
- [BLACK26] - [AD22] - Chat Nova Área do Aluno Escuro — 120253872983890247
- [BLACK26] - [AD23] - Chat Black Geral Claro — 120253872985750247
- [BLACK26] - [AD23] - Chat Black Geral Escuro — 120253872987080247
- [BLACK26] - [AD24] - Chat Esperar Claro — 120253872988550247
- [BLACK26] - [AD24] - Chat Esperar Escuro — 120253872990700247
- [BLACK26] - [AD25] - Chat Motion Maratona ENAM Claro — 120253872992550247
- [BLACK26] - [AD25] - Chat Motion Maratona ENAM Escuro — 120253872994380247
- [BLACK26] - [AD26] - Chat Motion Nova Área Claro — 120253872994900247
- [BLACK26] - [AD26] - Chat Motion Nova Área Escuro — 120253872996470247
- [BLACK26] - [AD27] - Chat Motion Black Geral Claro — 120253872997060247
- [BLACK26] - [AD27] - Chat Motion Black Geral Escuro — 120253872997470247
- [BLACK26] - [AD28] - Chat Motion Esperar Claro — 120253872998440247
- [BLACK26] - [AD28] - Chat Motion Esperar Escuro — 120253872998690247

## [06] Quente Listas RD — Criativos AD29–AD36 (12/11/2026) — ATIVA (usuário ativou 12/11 ~14:34 BRT)
- Campanha 120253873981460247 "[BLACK26] - [FASE01] - [06] - [CAPTAÇÃO] - [QUENTE] - Listas RD - Criativos AD29-AD36" · Leads · CBO R$500/dia · menor custo
- Conjunto 120253873984250247 "06 - [QUENTE] - Listas RD (8 públicos) - Exc. Cadastrados Black26" · cópia do conjunto 120253773465330247 da [02]: 8 listas RD, exc. Cadastrou Black26, 25-65, BR, IG stream/story/reels + FB feed/reels, pixel Lead, 7d clique/1d view/1d EV, A+ público OFF, expansão OFF
- 16 anúncios (copy Black, título "Black 10 anos G7", desc. "Entre para o Grupo Oficial", A+ criativo OFF). Vídeos: AD35 1674783153995019, AD36 1557728322779264.
  - [BLACK26] - [AD29] - 10 anos Claro — 120253874097000247
  - [BLACK26] - [AD29] - 10 anos Escuro — 120253874120890247
  - [BLACK26] - [AD30] - Área do aluno Claro — 120253874121180247
  - [BLACK26] - [AD30] - Área do aluno Escuro — 120253874121560247
  - [BLACK26] - [AD31] - Melhor oportunidade Claro — 120253874121800247
  - [BLACK26] - [AD31] - Melhor oportunidade Escuro — 120253874122150247
  - [BLACK26] - [AD32] - 90 mil alunos Claro — 120253874123000247
  - [BLACK26] - [AD32] - 90 mil alunos Escuro — 120253874097660247
  - [BLACK26] - [AD33] - Desde 2016 Mosaico Claro — 120253874123010247
  - [BLACK26] - [AD33] - Desde 2016 Mosaico Escuro — 120253874123550247
  - [BLACK26] - [AD33] - Desde 2016 Polaroid Claro — 120253874121730247
  - [BLACK26] - [AD33] - Desde 2016 Polaroid Escuro — 120253874121970247
  - [BLACK26] - [AD33] - Desde 2016 Trinca Claro — 120253874122220247
  - [BLACK26] - [AD33] - Desde 2016 Trinca Escuro — 120253874122430247
  - [BLACK26] - [AD35] - Capítulo 1 — 120253874140880247
  - [BLACK26] - [AD36] - Capítulo 2 — 120253874141400247
  - [BLACK26] - [AD41] - ChatGPT Maratona ENAM — 120253874445040247 (adicionado 12/11, imagem única 4:5 + 9:16)
  - [BLACK26] - [AD37] - Google Maratona ENAM — 120253874548430247 (12/11)
  - [BLACK26] - [AD38] - Google Data da Black — 120253874556360247 (12/11)
  - [BLACK26] - [AD39] - ChatGPT Esperar a Black — 120253874562660247 (12/11)
  - [BLACK26] - [AD40] - ChatGPT Black de 10 Anos — 120253874566740247 (12/11)

## [07] Quente Públicos Personalizados — Criativos AD29–AD41 (12/11/2026) — publicada PAUSADA
- Campanha 120253874676570247 "[BLACK26] - [FASE01] - [07] - [CAPTAÇÃO] - [QUENTE] - Públicos Personalizados - Criativos AD29-AD41" · Leads · CBO R$500/dia · menor custo
- Conjunto 120253874680490247 "07 - [QUENTE] - Todos os Públicos Personalizados G7" · cópia do conjunto 120253760845490247 da [01]: 176 públicos, exc. Cadastrou Black26, 25-65, BR, IG stream/story/reels + FB feed/reels, pixel Lead, 7d clique/1d view/1d EV, A+ público OFF, expansão OFF
- 21 anúncios reaproveitando os creative_id da [06] (copy Black, A+ criativo OFF):
  - [BLACK26] - [AD29] - 10 anos Claro — 120253874687870247
  - [BLACK26] - [AD29] - 10 anos Escuro — 120253874689440247
  - [BLACK26] - [AD30] - Área do aluno Claro — 120253874690470247
  - [BLACK26] - [AD30] - Área do aluno Escuro — 120253874691090247
  - [BLACK26] - [AD31] - Melhor oportunidade Claro — 120253874692390247
  - [BLACK26] - [AD31] - Melhor oportunidade Escuro — 120253874694080247
  - [BLACK26] - [AD32] - 90 mil alunos Claro — 120253874696030247
  - [BLACK26] - [AD32] - 90 mil alunos Escuro — 120253874696650247
  - [BLACK26] - [AD33] - Desde 2016 Mosaico Claro — 120253874689600247
  - [BLACK26] - [AD33] - Desde 2016 Mosaico Escuro — 120253874690310247
  - [BLACK26] - [AD33] - Desde 2016 Polaroid Claro — 120253874698350247
  - [BLACK26] - [AD33] - Desde 2016 Polaroid Escuro — 120253874703800247
  - [BLACK26] - [AD33] - Desde 2016 Trinca Claro — 120253874706670247
  - [BLACK26] - [AD33] - Desde 2016 Trinca Escuro — 120253874687670247
  - [BLACK26] - [AD35] - Capítulo 1 — 120253874690790247
  - [BLACK26] - [AD36] - Capítulo 2 — 120253874691150247
  - [BLACK26] - [AD37] - Google Maratona ENAM — 120253874692740247
  - [BLACK26] - [AD38] - Google Data da Black — 120253874694170247
  - [BLACK26] - [AD39] - ChatGPT Esperar a Black — 120253874696060247
  - [BLACK26] - [AD40] - ChatGPT Black de 10 Anos — 120253874696750247
  - [BLACK26] - [AD41] - ChatGPT Maratona ENAM — 120253874698770247

## AD42 / AD43 (13/11/2026) — adicionados na [06] e [07] (ativas; entram após revisão)
- [06] conjunto 120253873984250247: [BLACK26] - [AD42] - Comentário Maratona ENAM — 120253881065150247 · [BLACK26] - [AD43] - Comentário Black 10 anos — 120253881067010247
- [07] conjunto 120253874680490247: [BLACK26] - [AD42] - Comentário Maratona ENAM — 120253881068940247 · [BLACK26] - [AD43] - Comentário Black 10 anos — 120253881069510247
- Imagens 4:5/9:16, copy Black, A+ criativo OFF.

## [08] ABO Top 5 Criativos (criada 16/11/2026, publicada PAUSADA)
Campanha 120253935836590247 — [BLACK26] - [FASE01] - [08] - [CAPTAÇÃO] - [QUENTE] - ABO Top 5 Criativos (OUTCOME_LEADS, ABO, sem orçamento de campanha)
Conjuntos (R$ 25/dia cada; config = [05]: Lead pixel 1250040671830251, 176 públicos personalizados, exc. Cadastrou Black 60D, 25–65, FB feed/reels + IG feed/stories/reels, Advantage+ público off, 7d clique/1d view/1d EV):
- 01 AD12 — conjunto 120253935845310247 — anúncio 120253935893830247 (criativo 1138125941918518)
- 02 AD14 — conjunto 120253935857090247 — anúncio 120253935894250247 (criativo 1763180304753240)
- 03 AD10 — conjunto 120253935886740247 — anúncio 120253935895030247 (criativo 1670302494729887)
- 04 AD09 — conjunto 120253935886870247 — anúncio 120253935895930247 (criativo 1411012367682113)
- 05 AD11 — conjunto 120253935887200247 — anúncio 120253935896190247 (criativo 1616410633563076)

### [08] — conjuntos 06–28 (criativos da [06]/[07], criados 16/11, publicados PAUSADOS)
NN | criativo | conjunto | anúncio | creative_id
- 06 AD29 10 anos Claro — conjunto 120253936207980247 — anúncio 120253936219370247 (criativo 1667471345042401)
- 07 AD29 10 anos Escuro — conjunto 120253936905690247 — anúncio 120253936910990247 (criativo 1700532701669575)
- 08 AD30 Área do aluno Claro — conjunto 120253936906170247 — anúncio 120253936911680247 (criativo 1686139239788606)
- 09 AD30 Área do aluno Escuro — conjunto 120253936906650247 — anúncio 120253936913490247 (criativo 1172219298588929)
- 10 AD31 Melhor oportunidade Claro — conjunto 120253936969800247 — anúncio 120253936985880247 (criativo 1649791223503996)
- 11 AD31 Melhor oportunidade Escuro — conjunto 120253936970100247 — anúncio 120253936986260247 (criativo 2470144026727937)
- 12 AD32 90 mil alunos Claro — conjunto 120253936971010247 — anúncio 120253936986540247 (criativo 1009267041499996)
- 13 AD32 90 mil alunos Escuro — conjunto 120253936971350247 — anúncio 120253936987590247 (criativo 1801670057791178)
- 14 AD33 Desde 2016 Mosaico Claro — conjunto 120253937087700247 — anúncio 120253937101660247 (criativo 2316990566729866)
- 15 AD33 Desde 2016 Mosaico Escuro — conjunto 120253937089270247 — anúncio 120253937103180247 (criativo 1449884633237781)
- 16 AD33 Desde 2016 Trinca Claro — conjunto 120253937091810247 — anúncio 120253937104580247 (criativo 1420592943396658)
- 17 AD33 Desde 2016 Trinca Escuro — conjunto 120253937092150247 — anúncio 120253937106340247 (criativo 1493084602887009)
- 18 AD33 Desde 2016 Polaroid Claro — conjunto 120253936198320247 — anúncio 120253936205810247 (criativo 1441112051547663)
- 19 AD33 Desde 2016 Polaroid Escuro — conjunto 120253936310690247 — anúncio 120253936356780247 (criativo 987156863947561)
- 20 AD35 Capítulo 1 — conjunto 120253936314660247 — anúncio 120253936885850247 (criativo 3699596780215796)
- 21 AD36 Capítulo 2 — conjunto 120253936316760247 — anúncio 120253936887740247 (criativo 1152714857230578)
- 22 AD37 Google Maratona ENAM — conjunto 120253936930780247 — anúncio 120253936939700247 (criativo 2268512173712593)
- 23 AD38 Google Data da Black — conjunto 120253936931860247 — anúncio 120253936943870247 (criativo 1659532095757099)
- 24 AD39 ChatGPT Esperar a Black — conjunto 120253936932230247 — anúncio 120253936961480247 (criativo 1805449413843357)
- 25 AD40 ChatGPT Black de 10 Anos — conjunto 120253936932670247 — anúncio 120253936963360247 (criativo 2098107797484317)
- 26 AD41 ChatGPT Maratona ENAM — conjunto 120253937064840247 — anúncio 120253937076550247 (criativo 1492210305714699)
- 27 AD42 Comentário Maratona ENAM — conjunto 120253937066450247 — anúncio 120253937227680247 (criativo 1213708461220083)
- 28 AD43 Comentário Black 10 anos — conjunto 120253937067990247 — anúncio 120253937235590247 (criativo 1179615934755910)

### [08] — conjuntos 29–38 (novos criativos do Drive, criados 16/11, publicados PAUSADOS)
NN | criativo | conjunto | anúncio | hashes (4x5 / 9x16)
- 29 AD34 Dizer sim ao presente Claro — conjunto 120253937472470247 — anúncio 120253940827090247 (598c4c5e32f7cd86be31dd8da702e089 / 88363bb5e82d01d43df1905ffce67307)
- 30 AD34 Dizer sim ao presente Escuro — conjunto 120253940829410247 — anúncio 120253940830830247 (6ac43301ce865aa66814193687d53d0a / 03c94070543d41cdfda484919834cdd6)
- 31 AD44 Comentário Grupo Oficial — conjunto 120253940833470247 — anúncio 120253940834550247 (041495b3d5179b27b521b0b6590f0a5a / 765f318f24bc3328a4342aee96e3bc71)
- 32 AD45 Nativo O Que Esperar — conjunto 120253940836710247 — anúncio 120253940837890247 (02ae0c3b0ec93836ee1a8e128bb79962 / f89cd111b5b8f150768ecbd00b5ecdb1)
- 33 AD46 Nativo Maratona ENAM — conjunto 120253940841170247 — anúncio 120253940845880247 (3dbb3755d0ae93d58ae221e792669822 / 06b59437e4067909292c6b490ef94284)
- 34 AD47 Nativo 6º ENAM — conjunto 120253937468250247 — anúncio 120253940826430247 (14d7ec18177873d46a2e735222895d17 / 66ac416c553212f4d03358b837a13153)
- 35 AD48 Tweet 10 anos — conjunto 120253940829070247 — anúncio 120253940829850247 (6373e8b3fd7842544878ac8580119275 / 0aafcc48d2f4109c89f6ce4b65b7c799)
- 36 AD49 Tweet Reserve o dia 30 — conjunto 120253940835780247 — anúncio 120253940841590247 (47a8c7f3fa4482d2bce6460616ed3328 / c58ee0853caa976158d73a67d5c43996)
- 37 AD50 Tweet 30 horas — conjunto 120253940835860247 — anúncio 120253940842680247 (d163468061f721f62ad15cb73db87a63 / 11a886d4e14cd07c6721fc32e8fbd10a)
- 38 AD51 Tweet Sorteios — conjunto 120253940836090247 — anúncio 120253940844290247 (05a34e466b14cd1606cc611e6a055cb1 / ac065c454786bc3bc7f04a1f0a94bcc2)

### Vídeos convites (AD52–AD55), subidos 17/11 — 4x5 feed / 9x16 stories-reels
| Criativo | vídeo 4x5 | vídeo 9x16 | [08] conjunto | [08] anúncio | [05] anúncio (conj. 120253838140490247) |
|---|---|---|---|---|---|
| AD52 Convite Mônica | 1964987874885177 | 1669601171231941 | 39 · 120253965285350247 | 120253965287610247 | 120253965333420247 |
| AD53 Convite Rafael | 1862380884782433 | 2219725532225236 | 40 · 120253965305290247 | 120253965315580247 | 120253965334720247 |
| AD54 Convite Bruno Betti | 1603118038253474 | 1519534926682192 | 41 · 120253965305600247 | 120253965317850247 | 120253965335840247 |
| AD55 Convite Diego Pereira | 1742872003857698 | 1120282587548010 | 42 · 120253965305900247 | 120253965319540247 | 120253965338000247 |

### [09] — ABO Lista Alunos Plataforma (criada 18/11, publicada PAUSADA)
Campanha 120253973746080247 · `[BLACK26] - [FASE01] - [09] - [CAPTAÇÃO] - [QUENTE] - ABO Lista Alunos Plataforma`
Público: 120253973720850247 (meta_alunos_lista_completa.csv, subido pelo usuário) · exclusão 120253761230230247 · 25–65 BR · FB feed/reels, IG feed/stories/reels · R$ 25/dia por conjunto · LEAD pixel 1250040671830251
NN | criativo | conjunto | anúncio | creative_id
- 01 AD47 Nativo 6º ENAM — 120253973747580247 — 120253973784660247 — 1175096015033190
- 02 AD51 Tweet Sorteios — 120253973755680247 — 120253973785920247 — 2319665992159210
- 03 AD46 Nativo Maratona ENAM — 120253973755730247 — 120253973786730247 — 1669542828059475
- 04 AD44 Comentário Grupo Oficial — 120253973755930247 — 120253973787170247 — 2570912473420282
- 05 AD45 Nativo O Que Esperar — 120253973756280247 — 120253973789000247 — 1487369556685457
- 06 AD42 Comentário Maratona ENAM — 120253973756570247 — 120253973790060247 — 1213708461220083
- 07 AD12 Caixinha Grupo Oficial — 120253973756600247 — 120253973790210247 — 1138125941918518
- 08 AD32 90 mil alunos Claro — 120253973756740247 — 120253973790500247 — 1009267041499996
- 09 AD50 Tweet 30 horas — 120253973756940247 — 120253973790970247 — 1457153083190681
- 10 AD34 Dizer sim ao presente Claro — 120253973756990247 — 120253973791170247 — 1848371382958249
- 11 AD09 Vai prestar o ENAM — 120253973768890247 — 120253973869540247 — 1411012367682113
- 12 AD14 Edital Maratona ENAM — 120253973768980247 — 120253973870840247 — 1763180304753240
- 13 AD41 ChatGPT Maratona ENAM — 120253973769130247 — 120253973871320247 — 1492210305714699
- 14 AD31 Melhor oportunidade Claro — 120253973769370247 — 120253973871620247 — 1649791223503996
- 15 AD29 10 anos Claro — 120253973770170247 — 120253973872020247 — 1667471345042401
- 16 AD49 Tweet Reserve o dia 30 — 120253973770330247 — 120253973872600247 — 1674381497621432
- 17 AD52 Convite Mônica — 120253973771470247 — 120253973873370247 — 2522191288192609
- 18 AD53 Convite Rafael — 120253973771900247 — 120253973874240247 — 3167633020243055
- 19 AD54 Convite Bruno Betti — 120253973772730247 — 120253973874790247 — 1664620168484442
- 20 AD55 Convite Diego Pereira — 120253973773880247 — 120253973875610247 — 2600522160467808

### [10] — FRIO ABO Semelhante 1% Clientes (criada 18/11, publicada PAUSADA)
Campanha 120253974118670247 · `[BLACK26] - [FASE01] - [10] - [CAPTAÇÃO] - [FRIO] - ABO Semelhante 1% Clientes`
Público: 120253774168360247 (Semelhante 1% BR · Lista RD Clientes) · exclusão 120253761230230247 · 25–65 BR · FB feed/reels, IG feed/stories/reels · R$ 25/dia por conjunto · LEAD pixel 1250040671830251 · Advantage+ público OFF
NN | criativo | conjunto | anúncio
- 01 AD47 — 120253974121060247 — 120253974158490247
- 02 AD51 — 120253974132040247 — 120253974159300247
- 03 AD46 — 120253974132070247 — 120253974159910247
- 04 AD44 — 120253974132170247 — 120253974160210247
- 05 AD45 — 120253974132310247 — 120253974160600247
- 06 AD42 — 120253974132480247 — 120253974161450247
- 07 AD12 — 120253974132660247 — 120253974162360247
- 08 AD32 — 120253974132700247 — 120253974163010247
- 09 AD50 — 120253974132830247 — 120253974163300247
- 10 AD34 — 120253974133160247 — 120253974163780247
- 11 AD09 — 120253974144950247 — 120253974173150247
- 12 AD14 — 120253974145400247 — 120253974174190247
- 13 AD41 — 120253974145660247 — 120253974175190247
- 14 AD31 — 120253974145950247 — 120253974175560247
- 15 AD29 — 120253974146150247 — 120253974175670247
- 16 AD49 — 120253974146280247 — 120253974175970247
- 17 AD52 — 120253974146430247 — 120253974176450247
- 18 AD53 — 120253974146580247 — 120253974176850247
- 19 AD54 — 120253974147310247 — 120253974177300247
- 20 AD55 — 120253974147450247 — 120253974177980247
Criativos trocados em 18/11 para link https://pg.g7juridico.com.br/black-ads (url_tags iguais, Advantage+ criativo OPT_OUT). Novos creative_ids (conferidos ao vivo):
- AD47 2186872595561591 · AD51 1777142990693773 · AD46 1703289754480019 · AD44 1620509815931553 · AD45 1854820495833161
- AD42 1641527294375244 · AD12 2358284951672161 · AD32 1820348862629089 · AD50 1489295199793418 · AD34 1878696326599506
- AD09 1493741086026432 · AD14 940777885638672 · AD41 1673119991264116 · AD31 1207902748568254 · AD29 1151193581210770
- AD49 1419207136869591 · AD52 1094487620307596 · AD53 1705092174553590 · AD54 1514267700542245 · AD55 2077585102943036
([08] e [09] seguem com os criativos antigos, link /black)

## FASE02 (criadas 19/11, publicadas PAUSADAS no nível da campanha)
### [11] 120253994170450247 — [BLACK26] - [FASE02] - [11] - [CAPTAÇÃO] - [QUENTE] - CBO Quente Consolidada (R$ 900)
- Conjunto 120253994179060247 "11 - [QUENTE] - Todos Públicos Quentes G7 + Listas RD + Alunos" (185 públicos; exc. 120253761230230247; IG feed+stories; 25–65 BR)
- Anúncios: AD47 120253994184070247 · AD45 120253994185010247 · AD21 120253994185450247 · AD24 120253994186210247 · AD12 120253994187050247 · AD51 120253994188470247 · AD14 120253994189410247
### [12] 120253994217360247 — [BLACK26] - [FASE02] - [12] - [CAPTAÇÃO] - [FRIO] - CBO Semelhantes Clientes e Base (R$ 500)
- 120253994218780247 "12 - [FRIO] - Semelhante 1% Clientes" (120253774168360247): AD09 120253994223770247 · AD14 120253994226360247 · AD47 120253994229040247 · AD51 120253994229970247
- 120253994222710247 "12 - [FRIO] - Semelhante 1% Base Completa" (120253774168240247): AD09 120253994231250247 · AD14 120253994232710247 · AD47 120253994236380247 · AD51 120253994239130247
- Exclusões: cadastrou 60D, visitou Black 60D, lista RD base, lista clientes, alunos
### [14] 120253994278440247 — [BLACK26] - [FASE02] - [14] - [CAPTAÇÃO] - [QUENTE] - ABO Remarketing Visitou Black
- 120253994282860247 "14 - [QUENTE] - Visitou Black e não cadastrou 30D" (120253826169880247; exc. cadastrou) R$ 100: AD45 120253994283190247 · AD51 120253994283810247 · AD47 120253994285520247

- AD14 limpo (/black, 1 texto, automáticos OFF): criativo 1642905490915724, aplicado em 120253994189410247, 120253994226360247, 120253994232710247 (19/11).

### AD56–AD59 no [11] (19/11) — conjunto 120253994179060247
| Anúncio | Ad ID | Criativo | Hash 4x5 | Hash 9x16 |
|---|---|---|---|---|
| AD56 Nativo Por que deveria esperar? | 120253994511710247 | 973596768967643 | e8380c3ca6a0d0a9e8ff994272ca8068 | 0ffc76cfc5536f9eb9bc80fc42b4a011 |
| AD57 Nativo Depoimentos Black | 120253994512890247 | 1174080925139704 | 6485f0f3c27c994889230c2658beea87 | a3e21efe29c30b7fd1a8c05b832b9688 |
| AD58 Nativo 5 mil pessoas | 120253994513930247 | 1116993764565245 | b437e867bb1ea7b639f73ff4fabd8830 | 28fec4c1587aa020eacbcf79881445e6 |
| AD59 Nativo Poucos Dias | 120253994514550247 | 4620997058120922 | 19ba3b8693686ef00a2c531281826df2 | 2537021b4150d91ba0db276de57abd9d |

## [15] Black V2 — /black-v2 (criada 20/11, publicada PAUSADA)
- Campanha 120253999922290247 "[BLACK26] - [FASE02] - [15] - [CAPTAÇÃO] - [QUENTE] - CBO Black V2 (Públicos Personalizados + Listas)" · CBO R$300 · Leads/pixel Lead
- Conjunto 120253999928470247 · mesmo público da [11] (185 públicos, exc. 120253761230230247), IG feed+stories, 25–65, BR
| Anúncio | Ad ID | Criativo |
|---|---|---|
| AD62 Nativo 10 Aulas Gratuitas V2 | 120253999984620247 | 1938944707013610 |
| AD63 Nativo Grandes Nomes V2 | 120253999984650247 | 29746355591638923 |
| AD64 Nativo Vai Prestar o ENAM? V2 | 120253999984700247 | 2603624896821402 |
| AD65 Nativo 10 Aulas Gratuitas Claro V2 | 120253999984740247 | 1773224513741310 |
| AD66 Nativo Programação Maratona V2 | 120253999985190247 | 2026035734752738 |
| AD67 Nativo Melhor Corpo Docente V2 | 120253999985270247 | 1052106137899921 |
| AD68 Nativo Revisão Gratuita V2 | 120253999985330247 | 2306236043492315 |
| AD69 Carrossel Programação V2 (5 cards) | 120253999985690247 | 1873872047080261 |

## [16] Aquecimento — cadastrados Black → YouTube (criada 20/11, publicada PAUSADA)
- Campanha 120254000719000247 "[BLACK26] - [FASE02] - [AQUECIMENTO] - [16] - [CLIQUE] - [QUENTE] - CBO Cadastrados Black → YouTube" · Tráfego/cliques no link · CBO R$100
- Conjunto 120254000725380247 · públicos 120253761230230247 + 120253993366660247 · sem sugestão · IG feed+stories · 18+
| Anúncio | Ad ID | Criativo |
|---|---|---|
| AD03 A nova área do aluno está chegando (clara) | 120254000890780247 | 1572827758209105 |
| AD06 Nativo Nova Área do Aluno | 120254000893580247 | 1881110206656747 |
| AD07 Nativo Notificações | 120254000895020247 | 1220479977215461 |
| AD08 Nativo Sorteios | 120254000895840247 | 2328650924651363 |
- Criativo AD03 Escuro (sem anúncio): 1089520960805983

### AD60/AD61 na [11] (20/11) — conjunto 120253994179060247, link /black
| Anúncio | Ad ID | Criativo |
|---|---|---|
| AD60 Nativo Quem Já Escolheu | 120254000948370247 | 1147792461043637 |
| AD61 Nativo Dizer Sim | 120254000948580247 | 1280518727630234 |

## [17] Aquecimento ABO (21/11) — campanha 120254026022800247 (OUTCOME_TRAFFIC, ABO, R$25/conjunto, PAUSADA)
| Ad | Conjunto | Anúncio | Criativo |
|---|---|---|---|
| AD01 Temos um encontro marcado | 120254026023960247 | 120254026114760247 | 1538220358411011 |
| AD02 Ative as notificações | 120254026064020247 | 120254026213810247 | 1489728996471306 |
| AD04 Não perca os sorteios | 120254026079170247 | 120254026317420247 | 1081276464934677 |
| AD05 Coloque a data na sua agenda | 120254026083570247 | 120254026321930247 | 1620218766452114 |
Público igual à [16] (Pixel 60D + Lista RD, sugestão off). Versão clara, 4x5 feed + 9x16 story. Mesmo texto da [16] (igual em todos os anúncios da [16]).

## AD70–AD72 Convites (vídeo) — 24/11, publicados PAUSADOS
Vídeos: AD70 4x5 1137428892531932 / 9x16 1817447282864164 · AD71 4x5 2211625419733706 / 9x16 2263749510874519 · AD72 4x5 2665242153895309 / 9x16 1609990950415519
Criativos (/black-v2 | /black): AD70 1659911635784753 | 1606595084603033 · AD71 1500205588695046 | 1422080976581604 · AD72 2179038592697176 | 2389287538542450
| Campanha / conjunto | AD70 | AD71 | AD72 |
|---|---|---|---|
| [15] / 120253999928470247 | 120254074445550247 | 120254074472710247 | 120254074477270247 |
| [01] / 120253760845490247 | 120254074527270247 | 120254074536830247 | 120254074556100247 |
| [05] / 120253838140490247 | 120254074557110247 | 120254074721260247 | 120254074947090247 |
| [11] / 120253994179060247 | 120254075001110247 | 120254075024370247 | 120254075143520247 |
Título "Black 10 anos G7", descrição "Entre para o Grupo Oficial", LEARN_MORE, Advantage+ OFF, UTMs padrão.

### [17] Aquecimento — conjuntos novos (25/11)
| Conjunto | ID conjunto | Anúncio | ID anúncio | Criativo | Orçamento | Período | Status |
|---|---|---|---|---|---|---|---|
| AD14 Faltam 5 dias | 120254092366360247 | AD14 | 120254092419700247 | 1787662675799486 | vitalício R$100 | 25/11 18:00–23:59 | ATIVO |
| AD15 Faltam 4 dias | 120254092390600247 | AD15 | 120254092428160247 | 1033348749807191 | vitalício R$100 | 26/11 | ATIVO |
| AD16 Faltam 3 dias | 120254092399400247 | AD16 | 120254095397750247 | 1806550300400063 | vitalício R$100 | 27/11 | PAUSADO |
| Notas AD21-23 | 120254092411560247 | AD21 | 120254095409890247 | 2700372873740618 | R$50/dia | 25/11 18:00–30/11 20:00 | ATIVO |
| | | AD22 | 120254095428350247 | 1598027405460839 | | | ATIVO |
| | | AD23 | 120254095508970247 | 2758138024641261 | | | ATIVO |

### [18] Captação — CBO Criativos Aquecimento (criada 26/11, PAUSADA)
Campanha: 120254110989160247 — "[BLACK26] - [FASE01] - [18] - [CAPTAÇÃO] - [QUENTE] - CBO Criativos Aquecimento (Públ. Personalizados + Visitou Black)" — CBO R$500/dia — PAUSADA

| Conjunto | ID | Públicos | Mín./dia |
|---|---|---|---|
| A — Todos os Públicos Personalizados G7 | 120254110995200247 | 176 públicos (= [08] conj. 38) | R$100 |
| B — Visitou página Black 60D | 120254110996830247 | 120253761230320247 | R$100 |
Exclusões (ambos): 120253761230230247, 120253993366660247

| AD | Criativo novo | Anúncio conj. A | Anúncio conj. B |
|---|---|---|---|
| AD01 | 1126776847014605 | 120254111170760247 | 120254111256580247 |
| AD02 | 1115745344425258 | 120254111185710247 | 120254111259320247 |
| AD03 | 2097227744295470 | 120254111195350247 | 120254111264950247 |
| AD04 | 1317360560531301 | 120254111200620247 | 120254111269810247 |
| AD05 | 1186553114043116 | 120254111207440247 | 120254111272770247 |
| AD06 | 1939492117022425 | 120254111215290247 | 120254111275140247 |
| AD07 | 2350396372374221 | 120254111227040247 | 120254111277900247 |
| AD08 | 1673713897877824 | 120254111235220247 | 120254111282060247 |
| AD21 | 2365858133952700 | 120254111244060247 | 120254111284990247 |
| AD22 | 2050401055658854 | 120254111250370247 | 120254111288970247 |
| AD23 | 1015003528330397 | 120254111254040247 | 120254111293350247 |
Texto/URL/título do AD51; 4x5 feed, 9x16 story+reels; Advantage+ OFF.

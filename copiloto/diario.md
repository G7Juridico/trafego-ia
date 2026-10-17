# Diário

## 2026-10-16 — Sessão 1: reconhecimento

**Objetivo:** ler o contrato e descobrir sozinho o que a API entrega da conta G7Jurídico. Nada criado.

### Descobertas
- **Meta Ads: sem acesso nesta sessão.** Nenhuma ferramenta `ads_*` está carregada; a busca por ferramentas não encontra conector Meta/Facebook. Não é falta de permissão na conta — o conector simplesmente não está conectado a esta sessão. Nenhum dado da conta foi lido, portanto nenhum número da conta é conhecido.
- **Supabase:** um projeto, `G7Juridico` (`tzkodhijzreojeswybqu`), criado hoje (2026-10-16 08:06 UTC), status ACTIVE_HEALTHY.
  - Schema `public`: **0 tabelas**. Só existem schemas de sistema (auth 27, storage 8, realtime 3, vault 2, extensions 2).
  - **0 Edge Functions.**
  - Conclusão: **não existe hoje fonte de venda real** no banco — nenhuma tabela de pedidos, nenhum webhook de gateway.
- Repositório `trafego-ia` estava vazio (sem commits). Esta pasta é o primeiro conteúdo.
- O conector Supabase do plugin (`plugin:supabase:supabase`) falhou ao conectar (proxy 403); o conector `Supabase` principal funcionou e foi o usado.

### Implicação
Pela regra de medição, montar a fonte de venda real (gateway → Supabase) é prioridade sobre qualquer otimização. Depende de saber qual gateway a G7Jurídico usa.

### Erros / armadilhas desta sessão
- Nenhum.

## 2026-10-16 — Sessão 1 (cont.): conectar Meta Ads

**Pedido:** conectar a conta Meta Ads para subir, otimizar e puxar dados do Gerenciador.

### O que foi verificado
- Conectores instalados na org com "meta/facebook/ads/instagram": **nenhum**.
- Catálogo público de conectores: **nenhum expõe as ferramentas `ads_*`** do contrato (`ads_get_ad_accounts`, `ads_activate_entity`, `ads_get_errors`, leitura `draft`/`is_draft`...). Os que aparecem:
  - Windsor.ai, Supermetrics — **só leitura** de relatório. Servem para puxar dados; não criam nem editam.
  - Adspirer, AdWhispr — criam e "rodam campanhas de forma autônoma". **Conflita com a regra de segurança 1** (nada é ativado sem pedido explícito) e não expõem rascunho/`is_draft`. Não recomendado como ferramenta de escrita.
- Hipótese: as ferramentas `ads_*` da conta anterior vinham de um conector personalizado (servidor MCP adicionado por URL), não do catálogo. Não confirmado.

### Pendência
- Descobrir de onde vinham as ferramentas `ads_*` e reconectar o mesmo servidor nesta org.

## 2026-10-16 — Sessão 1 (cont.): decisão de conectar via MCP oficial
- Usuário decidiu: conectar via MCP.
- MCP oficial da Meta (lançado em 29/04/2026): `https://mcp.facebook.com/ads`, adicionado como conector personalizado no claude.ai, autenticação por OAuth do Facebook escolhendo o portfólio empresarial. Fonte: pesquisa web (vários guias concordam; um guia cita `mcp.meta.com/ads/<business-id>`, não confirmado).
- Risco conhecido: liberação gradual. Conta fora do rollout responde `is_ads_mcp_enabled: false`.
- Próximo passo após conectar (em sessão nova): leitura da conta — `ads_get_ad_accounts` (`is_queryable`), datasets, conversões, páginas, IG, públicos, erros. Nada criado.

## 2026-10-16 — Sessão 1 (cont.): verificação do conector
- Conector "Meta Ads" aparece instalado na org (`c1d7fa46-da83-4caa-a359-bd9f230086de`), mas com `installState: connect_incomplete`, `connected: false`, `enabledInChat: false`.
- Ou seja: foi adicionado, mas o login OAuth do Facebook não terminou. Nenhuma ferramenta `ads_*` carregou nesta sessão. Nenhum dado da conta lido.
- Mesmo concluído, só aparece em sessão nova (conectores carregam no início da sessão).

## 2026-10-16 — Sessão 1 (cont.): primeira leitura da conta (só leitura, nada alterado)

Conector Meta Ads carregou. IDs em `ids.md`.

### Gasto e números DECLARADOS pelo Gerenciador (últimos 90 dias)
- Gasto: **R$153.793,70** · impressões 10.428.210
- Compras declaradas (omni_purchase): **593** → CPA declarado ≈ R$259
- Leads declarados: 14.024
- **Caixa (gateway): desconhecido.** Não há fonte de venda real. Nenhum CPA/ROAS real pode ser calculado. Pela regra de medição, isso é prioridade.

### Campanhas ATIVAS agora (6, soma de orçamento diário R$1.900)
| ID | Nome | Objetivo | R$/dia | Gasto 90d | Resultado declarado |
|---|---|---|---|---|---|
| 120253160205440247 | 01 - [OUT26] [VEN] [QUENTE] - Mês de Outubro | Vendas | 500 | 8.234,38 | 66 compras (R$124,76) |
| 120253160808500247 | 02 - [OUT26] [VEN] [FRIO] - Mês de Outubro | Vendas | 500 | 8.321,85 | 36 compras (R$231,16) |
| 120253274418140247 | 03 - [OUT26] [VEN] [FRIO] - Mês de Outubro | Vendas | 500 | 3.041,75 | 48 compras (R$63,37) |
| 120251872401200247 | [QUE26] [CAP] - 100 questões | Leads | 150 | 12.851,07 | 5.869 leads (R$2,19) |
| 120252122540150247 | [ISC26] [CAP] [AUTO] - Desafio | Leads | 150 | 7.729,90 | 654 leads (R$11,82) |
| 120252356388350247 | [CAD26] [CAP] - Caderno de Atualizações | Leads | 100 | 6.258,33 | 1.136 leads (R$5,51) |

Todas as outras campanhas com gasto nos 90 dias estão PAUSED. Nenhuma foi tocada.

### Pixels
- Dois pixels ativos, ambos recebendo Purchase/Lead, de navegador e servidor, disparo de hoje. A API devolve linhas repetidas por evento sem dizer a origem → **não somei**. Ainda não se sabe qual pixel cada campanha otimiza. Risco: dois pixels contando a mesma compra.
- Única conversão personalizada (`1268284791577743`, compra ENAM) não dispara desde 2025-10-06.

### Públicos
- Mais de 100 públicos (lista paginada, só a primeira página lida). Muitos de pixel leem `20–20` = sentinela (armadilha 6), não vazio. Muitos semelhantes leem `1000–1000`, também com cara de piso de relatório — não concluir tamanho.

### Erros de entrega (`ads_get_errors` na conta, 96 campanhas)
- **"Please authenticate your account"** em 9 anúncios de 2 campanhas pausadas (`120252052094490247` [AGO26] FRIO Mês do Advogado; `120252672423690247` 04 [SET26] QUENTE). Texto: não será possível criar ou modificar anúncios até autenticar no Gerenciador. **Pode bloquear qualquer criação nossa.** Não confirmado se ainda vale — conferir no Gerenciador antes de criar.
- 5 anúncios "not delivering" na ATIVA `120251872401200247` (100 questões).
- O resto é legado de campanhas antigas pausadas: públicos apagados (dezenas), "No Valid Formats" (3 campanhas), conta não quitada (campanha de 2021), pixel sem acesso `1745450788954791`. Fora de escopo.

### Erros/armadilhas desta sessão
- `ads_get_dataset_stats`: `start_time` deve ser timestamp Unix em segundos e ≤ 28 dias. Errei o ano no cálculo e levei erro 100. Conferir a conta antes de chamar.
- `ads_get_errors` no nível da conta estoura o limite de saída (72 mil caracteres). Processar o arquivo salvo com python (armadilha 15) — funcionou.

## 2026-10-16 — Sessão 1 (cont.): pasta de criativos no Google Drive
- Pedido: ver os criativos da pasta do Drive `1qpuhE_loB0oLHRpY7ysV_g2oGeEbcyBw`.
- Bloqueado: a política de rede do ambiente nega `drive.google.com` (proxy 403 / DNS não resolve). Não há conector Google Drive instalado.
- Nada foi lido da pasta. Nenhum criativo foi enviado ao Meta.
- Lembrete para depois: `ads_creative_upload_media` com URL não aceita link de compartilhamento do Drive (devolve HTML, não o arquivo). Subir criativo exige URL direta do arquivo ou upload local.

## 2026-10-16 — Sessão 1 (cont.): criativos [OUT26] no Drive
- Conector Google Drive ativo e domínios liberados. Pasta lida e todos os 155 PNG baixados para a pasta temporária (fora do git) e vistos um a um em folhas de contato.
- Cruzamento com o Meta: AD01–AD028 (menos AD08) já rodam; **AD029–AD063 (35 anúncios novos) ainda não estão na conta.**
- Detalhes, inventário e problemas em `criativos-out26.md`. O mais urgente: **AD018 com prazo de inscrição vencido (14/10) está ativo.**
- Nada foi alterado no Meta nem no Drive.
- Os IDs de arquivo do Drive ficam na lista temporária, não no repositório. Os e-mails dos donos dos arquivos também não entram no git.

## 2026-10-16 — Sessão 1 (cont.): análise SET/OUT por público e configuração
- Pedido: qual público/configuração trouxe mais ROAS em vendas em setembro e outubro.
- Feito só com dado declarado (sem gateway). Tabela e problemas em `analise-set-out-2026.md`.
- Leitura de config de 13 conjuntos estourou a saída (166 mil caracteres) → processado com python (armadilha 15).
- Achado principal: compras declaradas com valor de R$18–24 na OUT26-03 — não são venda de curso.

## 2026-10-16 — Sessão 1 (cont.): estrutura perpétua
- Pedido: campanha de venda perpétua no lugar de uma por mês. Entregue só a estrutura, em `estrutura-perpetua.md`. Nada criado no Meta.
- Decisão proposta: 2 campanhas (FRIO R$1.000/dia, QUENTE R$500/dia), 1 conjunto cada, oferta mensal entra como anúncio. Conta: nem assim chega a 50 conversões/semana declaradas.
- Desconexão do conector Meta durante a sessão: nada dependia de chamada nova.

## 2026-10-16 — Sessão 1 (cont.): criação da campanha [G7] Vendas 01 Out26 Frio (RASCUNHO)
Conector em **modo rascunho**: tudo fica no rascunho do Gerenciador; nada publicado. Publicar = `ads_activate_entity` → vai ao ar ATIVO. Não chamar sem ordem explícita.

Criado (rascunho, validado, `active_errors` vazio na releitura draft):
| Objeto | ID |
|---|---|
| Campanha `[G7] - [Vendas] - [01] - [16/10/26] - [Out26] - [Frio]` (OUTCOME_SALES, CBO R$500/dia, LOWEST_COST_WITHOUT_CAP) | 120253401112630247 |
| Conjunto `01 - BR - 25/65 - Advantage Aberto` (A+A 1, idade como sugestão 25–65, mín. 25 fixo) | 120253401114090247 |
| Conjunto `02 - BR - 25/65 - Semelhante` (A+A 0, 4 semelhantes ∩ DD) | 120253401116470247 |
| Conjunto `03 - BR - 25/65 - Advantage Direcionado` (A+A 0, DD) | 120253401116530247 |
Todos: VALUE, Purchase pixel 1250040671830251, attribution_spec 7d clique + 1d view gravado, publisher_platforms explícito (sem Audience Network), exclusões iguais à campanha 03, location_types frequently_in/home/recent.

### Erros desta etapa
1. Meu: conjunto 01 criado sem `frequently_in` em location_types. Corrigido com update (draft). Releitura confirma.
2. `ads_create_creative` com `placement_customizations` (4:5 + 9:16): recusado — "Placement Asset Customization is not enabled for this ad account in Ads MCP yet". Nada criado.
3. `image_url` apontando para `drive.usercontent.google.com`: recusado — Meta não baixa (robots.txt). Nada criado.
4. `ads_creative_upload_local_image`: "This tool is new and is being gradually rolled out" — indisponível para a conta.
→ Anúncios ainda NÃO criados. Caminho: usuário sobe as 35 imagens 4:5 na Biblioteca de mídia da conta; eu pego os hashes com `ads_get_ad_images` e crio criativos + 105 anúncios.
- `SEE_DETAILS` (CTA da campanha 03) não é aceito pela ferramenta; plano é usar LEARN_MORE ("Saiba mais"), que bate com o texto.
- 9:16 não poderá ir junto pela API nesta conta; pode ser adicionado depois no Gerenciador, anúncio a anúncio.

### Continuação — anúncios
- Imagem do Drive sobe direto no Meta pelo link `https://lh3.googleusercontent.com/d/<ID>` com `ads_creative_upload_media` (URL). O link `drive.usercontent.google.com` é recusado (robots.txt). Arquivo precisa estar compartilhado "qualquer pessoa com o link".
- **Armadilha nova:** `ads_create_creative` com `image_url` grava `picture` E `image_hash` no link_data → anúncio fica com erro `AD_DRAFT_PUBLISHING / 1443051 ObjectStorySpecRedundant`. Correto: subir a imagem antes (upload_media) e criar o criativo só com `image_hash`.
- AD029: imagem hash f24606ca5485c5b7b35d368bf7c8bf6b, criativo 1737719787289398, anúncios A 120253401164760247, B 120253401170370247, C 120253401170630247 — sem erro.
- AD030 (1ª tentativa): criativo 1512343514065703 com picture+hash → 3 anúncios rascunho COM ERRO: 120253401177240247, 120253401177250247, 120253401177260247. **Precisam sair do rascunho antes de publicar.** Não apagados ainda (aguardando decisão).
- Criativos órfãos com o mesmo defeito, sem anúncio: AD031 1651448103175172, AD032 1438534552668036, AD033 1915100626539860, AD034 2480993322306253.
- Usuário (16/10): **sem anúncios de ENAM Reta Final nesta campanha** → fora: AD032, AD038, AD044, AD050, AD061, AD062, AD063. Ficam 28 ADs (AD029–AD063 menos esses 7) × 3 conjuntos = 84 anúncios.

### Lote final de anúncios (agente, via upload lh3 → image_hash)
- 28 imagens 1080x1350 subidas, 28 criativos (AD030–AD060 exceto 032*, 038, 044, 050) + AD029 = 30 criativos distintos no rascunho (inclui o AD030 defeituoso).
- Releitura completa do rascunho (2026-10-16): 1 campanha, 3 conjuntos, 90 anúncios (30 por conjunto). Link único com UTMs, CTA LEARN_MORE, página 1176977359047815, IG 17841404114381646 em todos.
- *AD032 (Notas ENAM) foi criado antes do aviso do usuário: anúncios 120253401202580247 (01), 120253401202660247 (02), 120253401202740247 (03). Usuário não quer ENAM → precisam sair.
- AD030 defeituoso (picture+hash, erro 1443051): 120253401177240247 (01), 120253401177250247 (02), 120253401177260247 (03). Precisam sair.
- Teste: `{"status":"DELETED"}` em rascunho no 120253401177240247 → aceito (is_draft true), mas a releitura continua `validation_status: HAS_ERRORS`. Não dá para provar que a publicação ignora o item. Não repetido nos outros 5. Remoção pedida ao usuário no Gerenciador (descartar os 6 itens do rascunho).
- Checklist que só dá para fechar DEPOIS de publicar: `learning_stage_info.attribution_windows`, `attribution_setting`, `results.indicator`, `ads_get_errors` (só leem objeto vivo).
- Pedido do usuário: marcar o que não usar com [NÃO USAR] para ele excluir/desativar depois de publicar.
  - AD032 (3): renomeados `[NÃO USAR] [OUT26] [VEN] [AD032] - Notas ENAM`, status PAUSED, VALIDATED. Publicam pausados.
  - AD030 com erro (3): renomeados `[NÃO USAR] ... - ERRO`, PAUSED (o 120253401177240247 saiu de DELETED para PAUSED). **Continuam HAS_ERRORS** — pausar não remove o erro de criativo; provável que travem a publicação. Precisam ser descartados no Gerenciador ANTES de publicar.

### Publicação (feita pelo usuário no Gerenciador, 2026-10-16) — campanha PAUSADA
- Usuário excluiu os 3 AD030 com ERRO; o rascunho foi publicado. Releitura: rascunho vazio; campanha 120253401112630247 existe no ar com status **PAUSED** (não está gastando).
- Checklist pós-publicação (leitura live):
  - 3 conjuntos: `attribution_spec` 7d clique + 1d view = `learning_stage_info.attribution_windows` [7d_click, 1d_view] = `attribution_setting` 1d_view_7d_click. **Os três concordam.**
  - `publisher_platforms` explícito sem audience_network nos 3 (effective: facebook, instagram, threads).
  - A+A: 01 = 1, 02 = 0, 03 = 0. Exclusões e semelhantes conferidos ID a ID, iguais à campanha 03.
  - `promoted_object` pixel 1250040671830251 PURCHASE; `results.indicator` dos anúncios = `actions:offsite_conversion.fb_pixel_purchase`.
  - `ads_get_errors` na campanha: `[]`.
  - Anúncios: 28 ADs × 3 conjuntos (CAMPAIGN_PAUSED) + 3 `[NÃO USAR] AD032` (PAUSED).
- O aviso "Please authenticate your account" visto na sessão 1 não impediu a publicação.
- Próximo passo: ativar a campanha — só com ordem explícita do usuário nomeando a campanha.

## 2026-10-17 — Campanha Reta Final ENAM (RASCUNHO)
- Pedido: campanha nova no mesmo molde da anterior, Reta Final ENAM, R$500/dia, link https://www.g7juridico.com.br/reta-final-enam-2026?uid_mh=…
- Criativos de foto ENAM ainda fora de campanhas no ar: AD032, AD038, AD044, AD050, AD061, AD062, AD063 (7). AD07 e AD017 (ENAM) já rodam nas OUT26. AD066 (novo, 16/10) é vídeo .mp4 — fora de campanha de foto.
- Copy: não existe copy específica de ENAM na conta (AD07 ENAM usa o texto geral de outubro). Plano: mesmo texto da campanha 01.
- Criado em rascunho, sem erros:
  | Objeto | ID |
  |---|---|
  | Campanha `[G7] - [Vendas] - [02] - [17/10/26] - [Out26] - [Frio]` (OUTCOME_SALES, CBO R$500/dia) | 120253403431830247 |
  | `01 - BR - 25/65 - Advantage Aberto` | 120253403446800247 |
  | `02 - BR - 25/65 - Semelhante` | 120253403448980247 |
  | `03 - BR - 25/65 - Advantage Direcionado` | 120253403449640247 |
  Mesma segmentação, exclusões, pixel, VALUE, atribuição 7d/1d e posicionamentos da campanha 01.
- Pendente antes dos criativos: parâmetro `uid_mh` no link (parece identificador de sessão/usuário de quem copiou o link — se for, todo clique do anúncio carrega o mesmo uid). Perguntado ao usuário.
- Alerta dado: público servidor/advocacia pode não ser o ideal para ENAM (exame da magistratura) — usuário pediu mesma estrutura.
- Usuário aprovou link limpo `https://www.g7juridico.com.br/reta-final-enam-2026` (sem uid_mh) + UTMs.
- Agente criou 6 uploads (lh3 → hash), 7 criativos por image_hash, 21 anúncios. Releitura do rascunho: 1 campanha, 3 conjuntos, 21 anúncios (7 por conjunto: AD032, 038, 044, 050, 061, 062, 063), link único limpo com UTMs, CTA LEARN_MORE, 0 erros.
- Criativos: AD032 1118646820754820 · AD038 1140880958478223 · AD044 1099641365812042 · AD050 978736357951773 · AD061 984748830626669 · AD062 3088163501515018 · AD063 1636147037877604.
- Status: RASCUNHO. Publicação só com o usuário.

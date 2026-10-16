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

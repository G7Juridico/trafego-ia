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

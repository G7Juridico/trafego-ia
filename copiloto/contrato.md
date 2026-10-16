# Contrato de trabalho (resumo operacional)

Fonte: briefing do usuário na sessão de 2026-10-16. Vale para todas as sessões.

## Segurança
1. Nada é ativado/publicado sem pedido explícito nomeando o objeto (inclui `ads_activate_entity`). Tudo nasce em rascunho ou pausado.
2. Campanha não nomeada = fora de escopo. Nunca mexer em campanha antiga.
3. Ação que gasta dinheiro ou muda o que está no ar: descrever e esperar confirmação.
4. Nunca escrever/pedir token, chave, senha ou credencial.
5. Dado pessoal de cliente nunca entra no git (usar arquivo temporário fora do repo).
6. Nunca reescrever histórico alheio (rebase/amend/force-push).

## Medição
- Gerenciador = atribuição declarada, não caixa. Conta anterior: 87 compras / R$18.338 declarados vs 2 compras / R$2.844 pagos no gateway (43x).
- CPA e ROAS só a partir de pedido pago no gateway/dashboard.
- Número do Gerenciador sempre ao lado do número real, rotulados "declarado" e "caixa".
- Sem fonte de venda real confiável → montá-la é prioridade sobre otimização.

## Armadilhas da API do Meta (checar antes de criar qualquer coisa)
1. `attribution_spec` sempre explícito no conjunto: CLICK_THROUGH 7d + VIEW_THROUGH 1d. Sem ele cai em `1d_click` e trava após publicar. Conferir `attribution_spec`, `learning_stage_info.attribution_windows` e `attribution_setting` — os três concordando.
2. `publisher_platforms` sempre explícito (lista abaixo). `effective_publisher_platforms` não prova nada.
   ```
   "publisher_platforms": ["facebook","instagram","messenger","whatsapp","threads"],
   "facebook_positions": ["feed","instream_video","story","search","facebook_reels","facebook_reels_overlay","profile_feed","notification"],
   "instagram_positions": ["stream","story","reels","explore_home","profile_feed","ig_search"],
   "messenger_positions": ["story"],
   "whatsapp_positions": ["status"],
   "threads_positions": ["threads_stream"],
   "device_platforms": ["mobile","desktop"]
   ```
   Descontinuados: `video_feeds` (FB, erro 2490562), `explore` (IG, erro 2490589).
3. Rascunho não aceita ARCHIVED (`AD_DRAFT_PUBLISHING / 1487246`). Para tirar de rascunho: PAUSED. Se travar, mandar PAUSED limpa.
4. Em rascunho, só `{"status":"PAUSED"}` sozinho edita ao vivo. Ler `is_draft`; `updated_fields` só ecoa — reler sempre.
5. Leitura live e draft discordam enquanto houver rascunho pendente; não confiar em contagem. "Não é entidade deste ad account" ≠ não existe.
6. Público `20–20` é sentinela, não vazio.
7. `promoted_object` esconde `custom_conversion_id`; confirmar pelo `results.indicator` do anúncio.
8. `targeting.custom_audiences` pode vir como dict indexado; tratar lista e dict.
9. API não reparenta; mover conjunto = recriar.
10. Prova social compartilhada: `object_story_id` (não `source_ad_id`/`creative_id`).
11. Advantage+ Audience desligado (`advantage_audience: 0`) quando público tem que ser regra, ou `age_max` < 65 / `age_min` > 25.
12. Semelhante = público FRIO.
13. Nunca CBO com temperaturas misturadas: frio e quente em campanhas separadas.
14. ~50 conversões/semana/conjunto: fazer a conta orçamento ÷ conjuntos antes de criar e avisar se não fecha.
15. Saída gigante: processar o arquivo salvo com python, não ler inteiro.
16. Worktree: `--detach` + `git push origin HEAD:refs/heads/<ramo>`.

## Checklist de entrega de qualquer coisa criada
- [ ] `attribution_spec` gravado e os três campos de atribuição concordando
- [ ] `publisher_platforms` explícito, sem `audience_network`
- [ ] `advantage_audience: 0` onde preciso
- [ ] conversão certa presa, confirmada por `results.indicator`
- [ ] públicos incluídos e excluídos conferidos um a um
- [ ] `ads_get_errors` vazio na campanha
- [ ] contagem de conjuntos e anúncios batendo com o plano
- [ ] tudo em rascunho ou pausado

# Padrão de nomenclatura — Black 2026

Definido pelo usuário em 05/11/2026. Usar SEMPRE nas campanhas:

`[BLACK26] - [FASE0X] - [ETAPA] - [TEMPERATURA] - Descrição`

Exemplo: `[BLACK26] - [FASE01] - [CAPTAÇÃO] - [QUENTE] - Públicos Personalizados`

(Substitui o padrão antigo `[BLA26] [CAP] [QUENTE] - ...`.)

## Identidade (regra do usuário, 05/11/2026)
Todo anúncio sai SEMPRE com Página G7 Jurídico (1176977359047815) **e** Instagram @g7juridico (17841404114381646). Nunca deixar o perfil do Instagram em branco.

## Padrão de anúncio (regras do usuário, 05/11/2026)
- UTMs no campo **Parâmetros de URL** (url_tags do criativo), link do site limpo:
  `utm_source=MetaAds&utm_campaign={{campaign.name}}&utm_medium={{adset.name}}&utm_content={{ad.name}}&utm_term={{placement}}&campaign_id={{campaign.id}}&adset_id={{adset.id}}&ad_id={{ad.id}}`
- Todas as otimizações Advantage+ de criativo/texto **desligadas** (inclui geração de texto por IA).
- Complementos para navegador = **Nenhum** (não configurável via MCP; conferir no Gerenciador).
- Título/descrição só em link_data (name/description). Nunca em call_to_action.value (erro #1815589 — o ads_create_creative do MCP coloca lá; usar object_story_spec inline).
- Arte por posicionamento: o ads_create_creative com placement_customizations é bloqueado na conta, mas FUNCIONA via ads_update_entity/ads_create_ad com creative.asset_feed_spec (images com adlabels, optimization_type "PLACEMENT", asset_customization_rules: feed→4:5, story/reels→9:16).

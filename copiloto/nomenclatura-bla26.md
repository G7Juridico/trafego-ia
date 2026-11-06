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

## Padrão de públicos (definido 06/11/2026)
Nome: `[FONTE] - [SEGMENTO] - O que é - Janela/Data`
- FONTE: `PIXEL` (site), `LISTA RD` (lista de clientes do RD), `ENGAJ` (IG/FB), `SEMELHANTE 1%` (lookalike)
- Janela: `60D`, `180D`… para pixel/engajamento; `Nov/26` (mês do export) para listas.
- Semelhantes: `[SEMELHANTE 1%] - [SEGMENTO DA SEMENTE] - Base: <nome curto da semente> - Nov/26`
Descrição (máx. 300 caracteres, sempre nesta ordem):
`O QUE É: … ORIGEM: … REGRA: … ENVIADOS: … (listas) USO: … CRIADO: dd/mm/aaaa.`

Públicos já padronizados:
| ID | Nome |
|---|---|
| 120253761230230247 | [PIXEL] - [BLACK26] - Cadastrou na página Black - 60D |
| 120253761230320247 | [PIXEL] - [BLACK26] - Visitou a página Black - 60D |
| 120253765428130247 | [LISTA RD] - [BASE COMPLETA] - Todos com consentimento - Nov/26 |
| 120253765428250247 | [LISTA RD] - [CLIENTES] - Alunos e ex-alunos - Nov/26 |
| 120253765428290247 | [LISTA RD] - [ENGAJADOS] - Interagem com o G7 - Nov/26 |
| 120253765428330247 | [LISTA RD] - [LEADS 2026] - Última conversão em 2026 - Nov/26 |
| 120253765428340247 | [LISTA RD] - [BLACKS ANTERIORES] - Black 2020 a 2025 - Nov/26 |
| 120253765428500247 | [LISTA RD] - [ENAM] - Interessados no ENAM - Nov/26 |
| 120253765428570247 | [LISTA RD] - [CARRINHO ABANDONADO] - Não concluíram compra - Nov/26 |
| 120253765428610247 | [LISTA RD] - [CLICOU WHATSAPP] - Botão WhatsApp nas páginas - Nov/26 |

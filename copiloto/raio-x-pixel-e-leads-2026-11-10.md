# Raio-X Pixel + Leads UTM × Gerenciador — 10/11/2026

Pixel principal 1250040671830251 ("Pixel de G7 Jurídico"). Janela do pixel: 03/11–10/11 (7 dias). Comparativo de leads: 06/11–10/11 (dias com campanhas Black gastando).
Números do Gerenciador = declarados (atribuição Meta). Número real = linhas na tabela `leads` do Supabase (página /black).

## 1. Saúde do pixel

Status: ativo, disparando agora no navegador e no servidor (último evento 10/11 ~15h30 BRT). Cookie 1ª parte e correspondência automática avançada ligados. CAPI chega por integração própria (Gateway não usado).

### Volume (7 dias)
| Evento | Total | Observação |
|---|---|---|
| PageView | 230.896 | |
| ViewContent | 75.747 | |
| Lead | 9.132 | navegador 3.149 · servidor 5.983 |
| Scroll25/50/75 | 7.633 / 6.220 / 5.143 | |
| AplicacaoBolsaG7 | 3.347 | |
| Purchase | 384 | navegador 309 · servidor 75 |
| CompleteRegistration | 305 | |
| AddToCart / InitiateCheckout / AddPaymentInfo | 53 / 47 / 47 | |
| gtm.* (4 eventos) + "RD Popup e WhatsApp" | 6 cada | lixo |

### Qualidade de correspondência (EMQ)
| Evento | EMQ hoje | 06/11 | Ponto fraco |
|---|---|---|---|
| Lead | 9,3 | 9,3 | fbc 66,8% (era 62,7%) |
| AplicacaoBolsaG7 | 9,3 | 9,3 | fbc 67% |
| Purchase | 9,3 | 7,5 | fbc 0%, external_id 0% |
| CompleteRegistration | 8,5 | 8,5 | telefone 22,9% |
| SubscribedButtonClick | 8,0 | 7,9 | fbc 10,5% |
| PageView | 6,6 | 7,7 | fbc 15% (caiu) |
| Scroll25/50/75 | 6,5 | 6,5 | normal p/ evento anônimo |
| ViewContent | 6,3 | 6,5 | fbc 29,8% |

### O que melhorou desde 06/11
- localhost e preview da Vercel pararam de disparar no pixel (último em 05/11).
- Purchase subiu de EMQ 7,5 → 9,3 (IP/UA/fbp agora 100%).

### Alertas abertos
1. **Lead no servidor ~2× o real.** O Supabase registrou 2.469 leads da /black desde 05/11 (1 envio CAPI cada, event_id único, meta_status ok). O pixel recebeu ~7.400 Lead em pg.g7juridico.com.br no mesmo período (navegador + servidor). Mesmo descontando o navegador, o servidor manda mais Lead do que existem leads. Hipótese: outra integração (RD/GTM/segunda etapa do formulário) também envia Lead pelo servidor. Conferir no Gerenciador de Eventos → Lead → "Desduplicação" e quais fontes de servidor aparecem. Se a desduplicação estiver ok, o Gerenciador não conta em dobro; se não estiver, o CPL do Gerenciador fica artificialmente baixo.
2. **Purchase em bloco no navegador** continua: 08/11 = 92 no navegador × 10 no servidor; 09/11 = 71 × 27. Mesmo padrão do raio-x de 06/11 (página de obrigado recarregando ou teste). Infla compras "declaradas". Venda real só no gateway.
3. **Purchase sem fbc (0%)** → a Meta não liga a venda ao clique do anúncio. Mandar fbc (cookie _fbc ou fbclid) no evento de compra do servidor.
4. **Eventos lixo** gtm.init/gtm.init_consent/gtm.js/gtm.load/"RD Popup e WhatsApp" ainda chegam (baixo volume). Tirar do GTM.
5. **5 leads com utm_campaign literal "{{campaign.name}}"** → algum link sem substituição de parâmetro dinâmico (provável pré-visualização/compartilhamento de anúncio). Volume irrelevante.

## 2. Leads com UTM (Supabase) × Gerenciador — 06/11 a 10/11

| Campanha | Gasto | Leads Gerenciador | Leads com UTM (real) | Únicos (e-mail) | % real/Gerenciador | CPL Gerenciador | CPL real |
|---|---|---|---|---|---|---|---|
| [01] Quente Públicos Personalizados | R$ 4.540,14 | 917 | 604 | 588 | 66% | R$ 4,95 | R$ 7,72 |
| [02] Quente Listas RD | R$ 3.877,14 | 771 | 504 | 497 | 65% | R$ 5,03 | R$ 7,80 |
| [03] Frio Semelhantes 1% | R$ 2.255,52 | 226 | 142 | 140 | 63% | R$ 9,98 | R$ 16,11 |
| [04] Engajamento Instagram | R$ 294,67 | 8 | 6 | 6 | 75% | R$ 36,83 | R$ 49,11 |
| **Total Black** | **R$ 10.967,47** | **1.922** | **1.256** | **1.231** | **65%** | **R$ 5,71** | **R$ 8,91** |

CPL real = gasto ÷ e-mails únicos com utm_source=MetaAds e utm_campaign da campanha. [05] ativada hoje, ainda sem volume.

### Por dia (Gerenciador × UTM)
| Dia | [01] | [02] | [03] | [04] |
|---|---|---|---|---|
| 06/11 | 412 × 276 | 95 × 58 | 47 × 30 | – |
| 07/11 | 185 × 131 | 180 × 114 | 36 × 17 | – |
| 08/11 | 89 × 52 | 182 × 129 | 62 × 44 | – |
| 09/11 | 171 × 106 | 220 × 133 | 57 × 36 | 1 × 1 |
| 10/11 (parcial) | 60 × 39 | 94 × 70 | 24 × 15 | 7 × 5 |

### Por que o Gerenciador marca ~35% a mais
1. **Clique antigo + cadastro por outro caminho.** 310 leads da /black (06–10/11) chegaram sem UTM da Meta (vieram por e-mail RD, ManyChat, link do Instagram etc.) mas têm cookie fbc, ou seja, clicaram num anúncio antes. A Meta credita esses leads à campanha (janela de 7 dias do clique); a UTM credita à última origem.
2. **Visualização sem clique** (janela de 1 dia de visualização) também conta no Gerenciador e nunca aparece na UTM.
3. **Possível Lead duplicado no servidor** (alerta 1 acima) — se a desduplicação falhar, infla o Gerenciador.

Diferença ~igual nas 3 campanhas principais (63–66%) → a proporção serve de fator de correção: **CPL real ≈ CPL do Gerenciador × 1,55**.

### Leads da /black por origem (05/11–10/11)
| Origem | Leads |
|---|---|
| MetaAds (campanhas Black) | 1.256 |
| Sem UTM | 557 |
| ManyChat | 177 |
| RD Station (e-mails 01, 02, 03) | 274 |
| Instagram orgânico (instagram / ig) | 140 |
| WhatsApp | 59 |
| Outros | 6 |
| **Total** | **2.469** |

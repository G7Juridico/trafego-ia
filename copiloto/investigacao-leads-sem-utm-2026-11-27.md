# Investigação — leads Black sem UTM (27/11)
Base: Supabase leads, funil black-g7, 18–26/11.

## Assinatura de lead Meta Ads (com UTM)
22–26/11: 828 pessoas, 99% com fbclid, 100% com fbc, landing sempre preenchida.

## Leads sem UTM — dois grupos
**A) landing vazia (~17–78/dia, caindo):** maioria com user-agent do navegador interno FB/IG; só 3–18/dia com cookie fbc.
Provável clique Meta/IG (anúncio ou orgânico/bio) em que a página não gravou landing/UTM. Volume pequeno.

| Dia | landing vazia | c/ fbc | UA FB/IG |
|---|---|---|---|
| 22/11 | 44 | 18 | 40 |
| 23/11 | 78 | 18 | 43 |
| 24/11 | 33 | 5 | 17 |
| 25/11 | 17 | 4 | 11 |
| 26/11 | 29 | 3 | 8 |

**B) landing preenchida sem UTM (~25–40/dia até 22/11; 139 em 23/11; 76–114/dia depois):**
URL limpa pg.g7juridico.com.br/black, sem referrer, muito desktop, 0 navegador FB/IG, 0 fbclid.
~116 vieram de www.g7juridico.com.br (site). Resto = link direto (e-mail RD / WhatsApp / grupos).
Pico de 23/11 bate com 150 cadastros whatsapp_api no mesmo dia → disparos para a base com link sem UTM.

## Conclusão
- A queda de leads MetaAds (299→243→140→97→57 de 22 a 26/11) NÃO é perda de UTM: no máximo 10–40/dia sem UTM têm sinal Meta, e também caíram.
- O aumento de "sem UTM" é tráfego de base (e-mail/WhatsApp/site), não Meta.
- A queda Meta é real → saturação do público quente.

## Recomendações
1. Pôr UTM nos links de e-mail RD, WhatsApp e banner do site (ex.: utm_source=rd / whatsapp / site).
2. Página /black: guardar UTMs no 1º carregamento (localStorage) e usar fbc como fallback no navegador interno FB/IG.

# Página https://pg.g7juridico.com.br/ — leitura em 28/10/2026

## O que é
- Vitrine de cursos (cópia da home do www): título "G7 Jurídico | Carreiras Jurídicas". Lista os cursos 2026.2 com "De / Por" (25% OFF) e formas de pagamento (PIX/boleto com 5% à vista, cartão em até 10–12x).
- Exemplos de preço: Magistratura e MP Estaduais R$3.629,25 · Combo I Anual + Complementares R$4.371,75 · Reta Final ENAM R$2.249,25 · Cartórios R$3.974,25 · Delegado R$2.174,25 · Analista (Tribunais) R$1.536,75 · Magistratura Federal R$4.499,25.
- Os botões dos cursos levam para as páginas de produto em `www.g7juridico.com.br/...` (37 links). Checkout e compra acontecem no www, que já tem pixel.
- **Banner do topo** (`assets/img/banner/home1791037666.png`), com alt: "25% OFF em todos os cursos e combos **durante o mês de outubro**, +90 dias extras de acesso e +15% OFF adicional para alunos e ex-alunos".

## Rastreamento
- **Sem pixel da Meta** (sem fbevents.js nem fbq), sem GTM e sem GA4. Confirma os 0 eventos nos dois pixels.
- `js/rastreio.js`: guarda UTMs, fbclid, gclid, referrer e página de entrada no sessionStorage (`g7_*`) e expõe `window.G7Rastreio.dados()` para anexar ao lead.
- `js/visitas.js`: envia cada página vista para a Edge Function `registrar-visita` do Supabase `tzkodhijzreojeswybqu`, com id de sessão, UTMs e domínio de origem. Ignora navegadores automatizados. Não usa cookies.
- Os links para o www **não repassam as UTMs**. No www, a origem só fica preservada pelo cookie do pixel (`_fbc`/`_fbp`, gravado em `.g7juridico.com.br`), e só depois que o pixel estiver instalado na pg.

## Pendências para a campanha 04
1. Instalar o pixel Principal 1250040671830251 (o mesmo da otimização da campanha) com PageView, mais ViewContent no clique dos cursos se possível.
2. Banner diz "durante o mês de outubro": se o desconto seguir depois de 31/10, trocar o banner junto com os anúncios (que agora estão sem prazo).
3. Opcional: repassar UTMs nos links para o www, para não perder a origem fora do pixel.

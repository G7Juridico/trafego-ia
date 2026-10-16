# Análise de conjuntos de venda — setembro e outubro de 2026

Período: 2026-09-01 a 2026-10-16. Fonte: `ads_get_ad_entities` nível conjunto. **Tudo aqui é DECLARADO pelo Gerenciador. Caixa (gateway) desconhecido.**
Valor declarado = purchase_roas × gasto (calculado por mim).

| Conjunto (ID) | Público / config | Otimiz. | Pixel | Gasto | Compras decl. | ROAS decl. | Valor decl./compra | Freq. |
|---|---|---|---|---|---|---|---|---|
| SET26 QUENTE Engajados + DD (120252672423710247) | 18 públicos quentes ∩ interesses de advogado; só IG+Threads; A+A off | VALUE | Backup | 17.321 | 133 | 12,7 | ~1.651 | **14,8** |
| SET26 FRIO "Advantage" (120252762002950247) | sem público; DD servidor/advocacia; posicionamento automático | Conversões | Backup | 14.057 | 87 | 12,0 | ~1.939 | 1,7 |
| OUT26 FRIO-02 "Advantage" (120253160808890247) | idem acima | Conversões | Backup | 8.575 | 39 | 8,0 | ~1.764 | 3,9 |
| OUT26 QUENTE Engajados + DD (120253160205690247) | igual ao SET26 quente | Conversões | **Principal** | 6.284 | 60 | 8,4 | ~879 | **10,4** |
| SET26-06 FRIO Advantage últimos dias (120253010014290247) | igual FRIO Advantage | Conversões | Backup | 2.848 | 19 | 20,0 | ~3.002 | 2,1 |
| OUT26 FRIO-03 Advantage aberto (120253274427080247) | A+A ON + DD | VALUE | Principal | 2.659 | 35 | 4,3 | **~324** | 3,3 |
| OUT26 QUENTE Remarketing 30D (120253261872440247) | 5 públicos 30D ∩ interesses de advogado | Conversões | Principal | 2.171 | 6 | 3,6 | ~1.302 | 5,8 |
| SET26-05 QUENTE Engajados 365 (120252993535650247) | 4 públicos de engajamento 365D | VALUE | Backup | 1.885 | 4 | 4,8 | ~2.282 | 4,7 |
| OUT26 FRIO-03 Semelhante (120253274439360247) | 4 semelhantes 1% ∩ DD | VALUE | Principal | 361 | 8 | 0,5 | **~24** | 2,4 |
| OUT26 FRIO-03 Advantage direcionado (120253274418200247) | DD | VALUE | Principal | 316 | 11 | 0,6 | **~18** | 2,1 |
| SET26 FRIO Campo de Estudos | interesses/formação em Direito | Conversões | Backup | 863 | 0 | — | — | 1,2 |
| SET26-03 FRIO Advantage (LAL Black Friday) | IG apenas, A+A on | Conversões | Principal | 791 | 0 | — | — | 1,9 |
| SET26-02 FRIO Semelhante engajamento | 8 semelhantes, IG apenas | Conversões | Principal | 775 | 0 | — | — | 1,6 |
| SET26 FRIO Cargos + demográficos | — | Conversões | Backup | 319 | 0 | — | — | 1,1 |

## Leitura (declarada)
- Os dois desenhos que concentram quase todo o valor declarado: **QUENTE "Engajados + Direcionamento Detalhado"** e **FRIO "Advantage" (DD servidor público/advocacia, posicionamento automático)**.
- Semelhantes, "Campo de Estudos", "Cargos + demográficos" e Remarketing 30D não se pagaram nem no declarado.

## Problemas de configuração e medição encontrados
1. **Compras de ~R$18–24** nos conjuntos 02 e Semelhante da campanha OUT26-03, e ~R$324 no Advantage aberto. Os cursos custam R$1.536–4.469. Esses "Purchase" não são venda de curso (produto barato, evento disparando errado ou valor errado). Foi isso que fez a OUT26-03 parecer a melhor por CPA (R$63) — por valor ela é a pior.
2. **Pixels misturados:** SET26 otimiza no pixel Backup (513428758397125); OUT26 quente e OUT26-03 no Principal (1250040671830251); OUT26-02 no Backup. Comparação SET×OUT não é homogênea.
3. **Atribuição discorda nos conjuntos OUT26 QUENTE:** `attribution_spec` tem 7d clique + 1d view + **1d engaged video view**, `attribution_setting` = `1d_view_7d_click_1d_ev`, mas `learning_stage_info.attribution_windows` = só 7d_click/1d_view. Os três campos não concordam (armadilha 1).
4. **QUENTE com DD é interseção**, não soma: com A+A desligado, público quente E interesse/empregador de advogado (OAB-CE, OAB-SP, escritório). Isso encolhe o público → frequência 14,8 (SET) e 10,4 (OUT). "Leads Ex alunos" está incluído e excluído ao mesmo tempo (exclusão vence).
5. **FRIO "Advantage" sem `publisher_platforms`** → posicionamento automático com Audience Network efetiva. A+A não gravado (null).
6. AGO26 QUENTE: R$33,66 gastos no período e 8 compras com ROAS 332 — atribuição de quem viu/clicou antes, não venda causada nesse período.

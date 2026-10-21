# Diagnóstico — "hoje não vendeu nada" (21/10/2026)

Fontes: Meta Ads (conta 391713394763358) e pixel Principal 1250040671830251, lidos em 21/10 por volta das 13h (BRT). Compras e ROAS = **DECLARADO**. Caixa: indisponível, porque ainda não há fonte de vendas real.

## 1. O pixel continua recebendo compras
- Evento Purchase por dia (contagem bruta do pixel): 18/10 112 · 19/10 137 · 20/10 79 · 21/10 52 até ~13h.
- Pela quebra navegador × servidor a contagem é menor: 18/10 ~50 · 19/10 ~98 · 20/10 ~36 · 21/10 ~5 até 13h. As duas leituras não batem: há lotes de 16 a 26 compras numa mesma hora, sem origem. Parece envio em lote do checkout ou gateway, a confirmar.
- Conclusão: há compra acontecendo. O que zerou foi a compra **atribuída aos anúncios**: 31 em 19/10, 5 em 20/10 e 0 em 21/10 (parcial). A atribuição de hoje ainda vai entrar nas próximas horas e dias (janela de 7 dias após o clique).

## 2. O que mudou na semana: +60% de verba sem +vendas
| Período | Gasto/dia | Compras/dia (decl.) | Valor/dia (decl.) | CPA (decl.) | ROAS (decl.) |
|---|---|---|---|---|---|
| 07–16/10 | R$1.866 | 11,5 | R$7.223 | R$162 | 3,87 |
| 17–20/10 | R$2.996 | 15,0 | R$6.008 | R$200 | **2,01** |

- 16 e 17/10: entraram a [G7] 01 Frio e a [G7] 02 ENAM, cerca de R$500/dia cada, **sem desligar a OUT26-03**, que mira o mesmo público. Resultado: R$1.130 a mais por dia e o valor declarado por dia caiu.
- 19/10 foi um pico (98 a 137 compras no pixel). Comparar 20/10 com 19/10 exagera a queda; contra 07–16/10, o 20/10 fica abaixo da média, mas não é um zero inédito (11/10 teve 4 compras e R$698).

## 3. Outros sinais
- Compras sem valor ou de valor baixo: a [G7] 01 teve 4 compras sem valor em 20/10, a ENAM tem 14 compras de R$53 em média e a QUENTE uma de R$47. O pixel conta como "compra" produtos baratos (ou eventos de teste), e a otimização por valor fica confusa.
- Taxa de clique em queda de 20 para 21/10 em quase todas as campanhas; QUENTE a 0,22%.
- Nenhuma mudança humana de orçamento, público ou status na semana, segundo o histórico. Só renomeação da ENAM e um anúncio novo na QUE26.
- Os boosts "Post do Instagram" (Black do G7, TJ-MT) estão ACTIVE, mas sem gasto no período. Não influenciam.

## 4. Hipóteses em aberto (precisam do caixa)
- O checkout ou gateway mudou o envio da compra para lotes? Explicaria a atribuição caindo com o pixel ainda recebendo.
- Público esperando a Black Friday: a página da ENAM já menciona bônus de Black.

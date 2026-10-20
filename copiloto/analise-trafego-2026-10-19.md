# Análise de tráfego G7 — 01 a 19/10/2026

Fonte: Meta Ads (conta 391713394763358), leitura em 20/10/2026. **Todos os números de compra e ROAS são DECLARADOS** pelo Ads Manager (atribuição 7d clique / 1d view). O número em caixa (vendas pagas no gateway) segue **indisponível**, porque ainda não há fonte real de vendas.

## Visão geral
| Período | Gasto total | Gasto vendas | Gasto captação | Compras (decl.) | Valor (decl.) | ROAS (decl.) | CPA (decl.) |
|---|---|---|---|---|---|---|---|
| 01–19/10 | R$36.383 | R$28.777 | R$7.606 | 215 | R$168.143 | 5,84 | R$134 |
| 13–19/10 | R$16.501 | R$13.744 | R$2.758 | 106 | R$61.591 | 4,48 | R$130 |

O ROAS declarado caiu: as campanhas OUT26 01 e 02 estavam em ~7,8 em 01–12/10 e caíram para ~5 na última semana.

## Campanhas de vendas (01–19/10, declarado)
| Campanha | Status | Gasto | Compras | Ticket médio | ROAS | 7d ROAS | Freq. | CTR link |
|---|---|---|---|---|---|---|---|---|
| 01 [OUT26] QUENTE | ACTIVE | R$10.278 | 80 | R$849 | 6,61 | 4,62 | **13,3** | 0,38% |
| 02 [OUT26] FRIO | ACTIVE | R$10.317 | 46 | R$1.604 | 7,15 | 5,59 | 2,8 | 0,80% |
| 03 [OUT26] FRIO | ACTIVE | R$5.162 | 61 | R$305 | 3,60 | 4,84 | 3,4 | 0,84% |
| [G7] 01 Frio (16/10) | ACTIVE | R$1.654 | 14 | R$506 | 4,29 | 4,29 | 2,7 | 1,08% |
| [G7] 02 Reta Final ENAM (17/10) | ACTIVE | R$1.366 | 14 | **R$53** | **0,55** | 0,55 | 2,6 | 1,06% |

## Campanhas de captação (sem compra, como esperado)
| Campanha | Gasto mês | 7d | CPM | CTR link | LPV |
|---|---|---|---|---|---|
| [CAD26] Caderno de Atualizações | R$1.905 | R$706 | R$49,81 | 6,54% | 1.707 |
| [ISC26] Desafio | R$2.856 | R$1.029 | R$19,46 | 0,79% | 831 |
| [QUE26] 100 questões | R$2.845 | R$1.023 | R$12,96 | 0,80% | 1.474 |

Leads e cadastros não foram lidos nesta análise; o custo por lead fica pendente.

## Achados
1. **ENAM: as "compras" não são do ENAM.** São 14 compras com valor médio de R$53, e o curso custa R$2.249. Na prática, 0 venda de ENAM declarada com R$1.366 gastos. O pixel está contando outra coisa, o mesmo problema dos R$18–24 da OUT26-03.
2. **ENAM roda com 42 anúncios**, 21 com texto antigo e 21 com o novo. Pausar os antigos foi proposto e aguarda confirmação.
3. **Advantage Aberto engole o orçamento** nas duas campanhas novas: 97% do gasto (01: R$1.605 de R$1.654; ENAM: R$1.323 de R$1.366). Os conjuntos Semelhante e Direcionado não aprendem, porque o CBO decidiu sozinho.
4. **Sobreposição de público:** [G7] 01 é cópia da OUT26-03, e as duas rodam juntas para o mesmo público frio. Somando a 02 FRIO e a ENAM, são 4 campanhas frias disputando o mesmo leilão.
5. **QUENTE saturado:** frequência 13,3 no mês e CTR de 0,38%, o mais baixo da conta. O ROAS declarado caiu de 7,66 para 4,62.
6. **Atribuição ≠ caixa:** campanhas SET26 pausadas, com gasto de R$0,11 a R$1,39, mostram R$3.629 e R$8.677 em "compras". É janela de atribuição, não venda nova. Mais um motivo para medir pelo gateway.

## Recomendações (nada foi alterado no ar)
1. Pausar os 21 anúncios antigos da ENAM (aguarda confirmação).
2. ENAM: verificar o evento de compra do checkout ENAM. Se o pixel não dispara Purchase com o valor de R$2.249, a campanha otimiza para a compra errada. Avaliar com 3–4 dias de dado antes de mexer no orçamento.
3. Decidir entre OUT26-03 e [G7] 01. Manter as duas é pagar duas vezes pelo mesmo público. Sugestão: a [G7] 01 substitui a 03 (que expira com o mês).
4. QUENTE: reduzir verba ou renovar criativos. Frequência 13 é saturação.
5. Fonte de vendas real (gateway) continua prioridade 1.

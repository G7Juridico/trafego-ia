# Estrutura perpétua de vendas — PROPOSTA (nada criado)

Status: proposta de 2026-10-16. Baseada em `analise-set-out-2026.md` (números declarados, sem caixa).

## Princípios
- Duas campanhas de venda permanentes, **frio e quente separados** (armadilha 13), sem data de término e sem mês no nome.
- O que muda todo mês são **os anúncios**, não a campanha. Oferta do mês entra como anúncio novo; a do mês anterior é pausada.
- **Poucos conjuntos**, para juntar conversão (armadilha 14).
- Criativos de teste ficam fora das perpétuas, para não mexer no aprendizado delas a cada mês.

## Conta de aprendizado (declarado — caixa pode ser bem menor)
| Campanha | R$/dia | R$/semana | CPA declarado de referência | Conversões/semana estimadas |
|---|---|---|---|---|
| FRIO | 1.000 | 7.000 | ~R$160–220 (FRIO Advantage SET/OUT) | ~32–44 |
| QUENTE | 500 | 3.500 | ~R$105–130 (QUENTE SET/OUT) | ~27–33 |
Mesmo com 1 conjunto por campanha, nenhuma bate 50/semana. Com 2 conjuntos por campanha cairia para ~15–20 cada. Por isso: **1 conjunto por campanha**.
Soma R$1.500/dia = mesma verba que as 3 campanhas OUT26 de venda somam hoje (500+500+500).

## Campanha 1 — `[PERP] [VEN] [FRIO]`
- Objetivo: OUTCOME_SALES · orçamento de campanha (CBO, uma temperatura só) R$1.000/dia · sem data de fim · nasce PAUSADA.
- Conjunto F1 `[PERP] [FRIO] Servidor + Advocacia`
  - Público: Brasil, 25–65, direcionamento detalhado do vencedor (setores Serviços jurídicos / Serviços administrativos; empregador Escritório de Advocacia; cargos Servidor público no Brasil, Advogado(a) sócio(a)).
  - Exclusões: compradores (todos os Purchase/COMPROU), Base de Clientes, bases de leads, cadastrados SAJ, visitantes 100 questões (as mesmas do vencedor).
  - Otimização: conversões → Purchase no pixel escolhido (pendente: Principal ou Backup).
  - `attribution_spec` 7d clique + 1d view, explícito.
  - `publisher_platforms` explícito (lista do contrato) — **sem Audience Network**. Muda em relação ao vencedor, que rodava em automático.
  - A+A: gravado explícito (decidir 0 ou 1; vencedor estava sem valor gravado).

## Campanha 2 — `[PERP] [VEN] [QUENTE]`
- OUTCOME_SALES · CBO R$500/dia · sem data de fim · nasce PAUSADA.
- Conjunto Q1 `[PERP] [QUENTE] Engajados + Leads + Site`
  - Inclui os públicos quentes do vencedor (INSTAGRAM-90D, SITE-90D, bases de leads, cadastrados SAJ/MMP/Lançamento, AddToCart 90D, visitantes 100 questões).
  - **Sem interseção com interesse de advogado** (era o que deixava a frequência em 10–15).
  - Exclusões: compradores e Base de Clientes. Remover "Leads Ex alunos" da inclusão (estava incluído e excluído).
  - `advantage_audience: 0` (público tem que ser regra) · atribuição 7d/1d explícita, **sem engaged video view** · posicionamentos explícitos.

## Campanha 3 (opcional) — `[PERP] [TESTE] [FRIO] Criativos`
- Verba pequena (ex.: R$150/dia), conjuntos por criativo/conceito. Criativo que vencer vai para F1/Q1 como anúncio novo. Não espera sair do aprendizado — serve para triagem de criativo.

## Anúncios — rotina mensal
- Cada anúncio publicado a partir de **post existente (`object_story_id`)**, para curtidas e comentários acumularem (armadilha 10). UTMs com `{{campaign.name}}`, `{{adset.name}}`, `{{ad.name}}`, `{{placement}}`.
- Nome: `AD0xx - <conceito> - <oferta>` (ex.: `AD007 - ENAM - NOV26`). Sem mês na campanha nem no conjunto.
- Todo dia 1: anúncios da oferta nova entram pausados → conferência → ativação com aprovação; os da oferta anterior são pausados.
- Base fixa (evergreen) de criativos que não citam data: AD09 Autores, AD010 Juiz/Promotor (sem "outubro"), conversas/notas sem prazo.
- Atenção: o Meta trata anúncio novo no conjunto como edição significativa — pode reabrir o aprendizado uma vez por mês. É o custo de ser perpétuo; ainda é menor que recomeçar campanha do zero.

## Pendências antes de criar (bloqueiam)
1. O que se vende depois de 31/10 — os criativos dizem que matrículas 2026 encerram nessa data.
2. Qual pixel é o oficial (Principal `1250040671830251` ou Backup `513428758397125`).
3. O que são as "compras" de R$18–24 (OUT26-03).
4. Aviso "Please authenticate your account" — pode impedir criar anúncios.
5. Fonte de venda real (gateway).

## Fora de escopo
As campanhas SET26/OUT26 existentes não são tocadas. Transição (pausar as OUT26) só com ordem explícita.

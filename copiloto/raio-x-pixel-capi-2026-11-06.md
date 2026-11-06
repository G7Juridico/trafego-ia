# Raio-X Pixel + CAPI — 06/11/2026 (janela: 30/10–06/11)

Datasets: Principal 1250040671830251 ("Pixel de G7 Jurídico") e Backup 513428758397125. Ambos ativos, disparando agora (navegador e servidor), cookie 1ª parte ligado, correspondência automática avançada ligada (em, fn, ln, ph, ge, zp, ct, st). CAPI Gateway: não usado (CAPI chega por outra integração).

## EMQ (pixel principal)
| Evento | EMQ | Pontos fracos |
|---|---|---|
| Lead | 9,3 | fbc 62,7%, ln 81% |
| AplicacaoBolsaG7 | 9,3 | fbc 66% |
| CompleteRegistration | 8,5 | telefone 25% |
| SubscribedButtonClick | 7,9 | tel 13%, nome 20% |
| PageView | 7,7 | fbc 7,6% |
| Purchase | 7,5 | fbc 0%, IP/UA/fbp 66,7% |
| ViewContent | 6,5 | external_id 33,6%, fbc 29% |
| Scroll25/50/75 | 6,5 | e-mail ~13% (normal p/ evento anônimo) |

## Alertas
1. Purchase no navegador com picos em bloco (ex.: 20 Purchase + 7 ATC + 7 IC + 7 AddPaymentInfo na mesma hora, repetindo ~07h e ~23h PST) sem correspondente no servidor → suspeita de disparo de teste/recarga de página de obrigado. Infla compras "declaradas".
2. Pixel disparando em localhost e em preview da Vercel (paginavendas-git-claude-...vercel.app) desde 04/11 → eventos de teste poluindo dados/públicos.
3. Eventos lixo enviados ao pixel: gtm.init, gtm.init_consent, gtm.js, gtm.load, "RD Popup e WhatsApp".
4. Purchase sem fbc (0%) e com IP/UA só em 2/3 → atribuição de venda prejudicada.
5. Servidor envia ~2x mais eventos que navegador (PageView/Lead) → normal se houver bloqueio, mas confirmar desduplicação (event_id) no Gerenciador de Eventos.
6. Dois pixels no mesmo site (Principal + Backup) → ok como backup; campanhas otimizam no Principal.

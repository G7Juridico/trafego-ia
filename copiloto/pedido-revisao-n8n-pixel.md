# Pedido de revisão no n8n — eventos enviados ao Pixel da Meta (G7 Jurídico)

Copie o texto abaixo e cole no chat que tem acesso ao n8n.

---

Preciso de uma auditoria **somente leitura** em todos os workflows do n8n ligados ao G7 Jurídico. **Não altere, não desative e não execute nada.** Só leia e me traga o relatório.

## Contexto
- Pixel / conjunto de dados da Meta: **1250040671830251** ("Pixel de G7 Jurídico"). Existe também um pixel backup, **513428758397125**.
- O pixel está recebendo pelo servidor (API de Conversões) **cerca de 2 a 2,5 vezes mais eventos `Lead`** do que os cadastros reais da página https://pg.g7juridico.com.br/black.
- O único envio legítimo de `Lead` pelo servidor é a função do Supabase `capturar-lead`, que manda **1 Lead por cadastro**, com `event_id` no formato `lead-...` e `content_name` = "Black G7 Especial 10 Anos". Qualquer outro envio de `Lead` para esse pixel está sobrando e não é deduplicado.
- O excesso bate com o número de vezes que cada lead é repassado para a Clint e a RD Station: uma vez no **cadastro** e outra quando a pessoa **responde o concurso de bolsas** (funil `black-g7`, etapa `concurso`).
- Também aparecem compras (`Purchase`) em bloco, de dezenas na mesma hora, quase sem par no servidor e sem `fbc`. Vale checar se algum workflow também envia `Purchase`.

## O que verificar em cada workflow (ativos e inativos)
1. Algum nó envia dados para a Meta? Procure:
   - nós HTTP Request para `graph.facebook.com` com `/events` no caminho;
   - nós "Facebook Graph API", "Meta Conversions API" ou "Facebook Lead Ads";
   - qualquer menção a `1250040671830251` ou `513428758397125`;
   - qualquer menção a `access_token` da Meta.
2. Para cada envio encontrado, anote:
   - nome do workflow;
   - se está ativo;
   - o gatilho (webhook, Clint, RD, checkout, ManyChat, agendamento etc.);
   - o `event_name` enviado (Lead, Purchase, CompleteRegistration, outro);
   - como monta o `event_id`, ou se não manda nenhum;
   - qual `event_source_url` envia;
   - se é chamado 1 ou mais vezes por lead (por exemplo, no cadastro e de novo no concurso);
   - quantas execuções teve nos últimos 7 dias.
3. Workflows que recebem webhook da **Clint**, da **RD Station**, do **ManyChat**, do **checkout do G7** ou do Supabase e repassam para outro lugar. Mesmo que não chamem a Meta diretamente, liste para onde mandam.
4. Envios de teste esquecidos, ou workflows duplicados fazendo a mesma coisa.

## Formato da resposta
- Uma tabela: workflow | ativo? | gatilho | envia para a Meta? | evento | tem event_id? | execuções nos últimos 7 dias.
- Logo abaixo, uma conclusão direta: qual workflow (se houver) está gerando os `Lead` extras e se algum gera os `Purchase` em bloco.
- Uma sugestão de correção para cada problema, sem aplicar. Por exemplo: remover o envio de `Lead`, passar a usar o mesmo `event_id` do site, ou trocar para um evento personalizado.

## Regras
- **Não mostre tokens, chaves ou senhas** na resposta. Se encontrar algum, diga só "token presente no nó X".
- Não copie dados pessoais de leads (e-mail, telefone, nome) para a resposta.
- Somente leitura. Nada de editar, ativar, desativar ou executar workflows.

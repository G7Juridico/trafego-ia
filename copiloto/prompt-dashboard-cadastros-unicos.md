# Prompt — dashboard: mostrar cadastros únicos (para usar no chat que tem o repositório da dashboard)

Copie tudo abaixo da linha e cole no outro chat.

---

Preciso de um ajuste na dashboard da Black do G7 (o card "CADASTROS — Formulário da /black — Meta 15.000"). Hoje ele conta envios do formulário, e quem se cadastra mais de uma vez conta mais de uma vez. Quero que ele conte **pessoas** (cadastros únicos).

## Contexto
- Os dados vêm da Edge Function do Supabase `dashboard-dados` (projeto `tzkodhijzreojeswybqu`). Ela devolve `leadsSite`: uma linha por envio do formulário, com `data`, `hora`, `email`, `pagina`, `funil`, `teste` (true quando é cadastro de teste da equipe), `origem`, `campanha` e `utm`.
- A tela soma as linhas de `leadsSite` para chegar ao número do card. Por isso deu 4.980.
- Em 17/11 às 15h13 o banco tinha 4.997 envios, 4.467 e-mails únicos e 530 envios repetidos (424 pessoas se cadastraram mais de uma vez). O RD Station mostrava 4.447, porque também conta pessoas.

## O que fazer
1. Encontre no código da tela onde o card "CADASTROS" e a barra da "Meta 15.000" são calculados a partir de `leadsSite`.
2. Mude a conta para cadastros únicos:
   - chave da pessoa = `email` em minúsculas e sem espaços (`email.trim().toLowerCase()`);
   - ignore as linhas com `teste === true`, como a tela já faz hoje;
   - aplique os mesmos filtros de período, página e funil que o card já usa;
   - conte cada e-mail uma vez só, no dia do **primeiro** cadastro (importa para o gráfico por dia).
3. No card:
   - número grande = **pessoas** (cadastros únicos);
   - linha menor embaixo = "X envios · Y recadastros" (Y = envios − pessoas);
   - a barra da meta de 15.000 e a porcentagem passam a usar **pessoas**.
4. Não mude nada na Edge Function nem no banco. O ajuste é só na tela.
5. Antes de mexer, liste os outros lugares da tela que também contam leads de `leadsSite`: gráfico por dia, leads por origem ou campanha, taxa de conversão visita → cadastro, CPL. Me diga quais deles você acha que também devem passar a contar pessoas. **Não altere esses outros lugares sem eu confirmar.**

## Como conferir
- Rode a dashboard localmente e compare com o banco:
  ```sql
  select count(*) envios, count(distinct lower(trim(email))) pessoas
  from leads where email is not null and email <> '';
  ```
  O número de pessoas da tela deve ficar igual ou um pouco menor que `pessoas`, porque a tela exclui os testes. Ele deve ficar próximo do número do segmento no RD Station.
- Mostre um print ou o número antes e depois.

## Regras
- Trabalhe em uma branch nova e me mostre a diferença do código antes de publicar.
- Não publique em produção sem a minha confirmação.
- Não coloque senha, chave ou token em arquivo, commit ou chat (o acesso à função usa o cabeçalho `x-dashboard-chave`; não precisa mexer nele).

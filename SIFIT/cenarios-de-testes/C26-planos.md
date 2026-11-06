C26 — Planos

C26-CT01 — Cadastrar plano recorrente

Responsável: Fernando Cardoso dos Santos
Data da execução: 05/11/2026
Tipo: Positivo
Status: Aprovado
Sistema: https://sifitalfa.centrion.com.br/planos

Objetivo

Verificar se o sistema permite cadastrar um plano recorrente e manter seus dados após a atualização da página.

Pré-condições

Estar autenticado no sistema.
Acessar a tela de Planos.
Ter o grupo Teste disponível.
Utilizar dados fictícios com o prefixo QA_FERNANDO.

Dados utilizados

Nome: QA_FERNANDO_REC_01.
Grupo: Teste.
Status: Ativo.
Cobrança: Mensalidade recorrente.
Parcelas: 1.
Valor mensal: R$ 100,00.
Valor da matrícula: R$ 0,00.
Tem personal?: Não.
Dependentes: 0.

Passos

1. Abrir a tela Planos.
2. Clicar em Novo Plano.
3. Preencher o nome QA_FERNANDO_REC_01.
4. Selecionar o grupo Teste.
5. Manter o status como Ativo.
6. Selecionar Mensalidade recorrente.
7. Informar 1 parcela.
8. Informar o valor mensal de R$ 100,00.
9. Manter o valor da matrícula em R$ 0,00.
10. Manter Tem personal? como Não.
11. Manter Dependentes como 0.
12. Clicar em Salvar Plano.
13. Conferir o registro na listagem.
14. Atualizar a página.
15. Reabrir o plano pela lupa.
16. Comparar os dados apresentados com os dados informados.

Resultado esperado

O sistema deve cadastrar o plano recorrente e preservar os dados após atualizar a página e reabrir o cadastro.

Resultado obtido

O plano QA_FERNANDO_REC_01 foi cadastrado com o código 58.

Após atualizar a página e reabrir o cadastro, foram mantidos o nome, o grupo Teste, o status Ativo, a cobrança recorrente, 1 parcela, o valor mensal de R$ 100,00, o valor da matrícula de R$ 0,00, a opção Tem personal? como Não e 0 dependentes.

Status

Aprovado.

Evidência

Parte 1 — preenchimento inicial:
https://jam.dev/c/63995af9-cfc6-45a0-8759-d3602073fe2f

Parte 2 — salvamento, atualização e reabertura:
https://jam.dev/c/06959de7-d69a-4a8d-ac1d-ee9b4c560184

A Parte 1 mostra o preenchimento inicial. Na Parte 2, o nome foi ajustado para QA_FERNANDO_REC_01 antes do salvamento. A mesma gravação mostra a atualização da página e a reabertura do plano.

Verificações comuns aplicadas

G01 — Cadastro válido.
G13 — Persistência após atualizar a página.
G24 — Conferência entre listagem e formulário.

Bug associado

Nenhum identificado neste caso.

Observações

O plano de código 58 deve ser preservado para os testes de matrículas e para o caso C47-CT01.

Os casos C26-CT02 a C26-CT12 permanecem Não executado.


C26-CT02 — Plano por diária

Responsável: Fernando Cardoso dos Santos
Data da execução: 06/11/2026
Tipo: Positivo
Status: Aprovado
Sistema: https://sifitalfa.centrion.com.br/planos

Objetivo

Verificar se o sistema permite cadastrar um plano por diária.

Pré-condições

Estar autenticado no sistema.
Acessar a tela de Planos.
Ter o grupo Teste disponível.

Passos

Clicar em Novo Plano.
Preencher o nome QA_FERNANDO_DIARIA_01.
Selecionar o grupo Teste.
Manter o status como Ativo.
Selecionar Diária no campo Cobrança.
Informar 1 parcela.
Informar o valor diário de R$ 25,00.
Manter Dias na matrícula? como Não.
Manter Tem Personal? como Não.
Manter Dependentes como 0.
Clicar em Salvar Plano.
Atualizar a página.
Localizar o plano cadastrado e abrir pela lupa.

Resultado esperado

O sistema deve permitir o cadastro do plano diário, exibir o registro na listagem e manter os dados após a atualização da página.

Resultado obtido

O plano diário foi salvo com sucesso e apareceu na listagem. Após a atualização da página, o registro continuou disponível e foi aberto pela ação de consulta. Nenhum erro foi exibido.

Evidência

https://jam.dev/c/6aae4b97-2a12-4590-81eb-8156138a7261

Bug associado

Nenhum identificado neste caso.



C26-CT03 — Plano por período fixo

Responsável: Fernando Cardoso dos Santos
Data da execução: 06/11/2026
Tipo: Positivo
Status: Aprovado
Sistema: https://sifitalfa.centrion.com.br/planos

Objetivo

Verificar se o sistema permite cadastrar um plano por período fixo.

Pré-condições

Estar autenticado no sistema.
Acessar a tela de Planos.
Ter o grupo Teste disponível.

Passos

Clicar em Novo Plano.
Preencher o nome QA_FERNANDO_PERIODO_01.
Selecionar o grupo Teste.
Manter o status como Ativo.
Selecionar Período fixo no campo Cobrança.
Informar quantidade de 3.
Manter o período como Mês(es).
Informar 3 parcelas.
Informar o valor mensal de R$ 150,00.
Manter o valor da matrícula como R$ 0,00.
Manter Tem Personal? como Não.
Manter Dependentes como 0.
Clicar em Salvar Plano.
Atualizar a página e consultar o plano cadastrado.

Resultado esperado

O sistema deve permitir o cadastro do plano por período fixo, mantendo sua duração, parcelas e valor após a atualização da página.

Resultado obtido

O plano foi salvo com sucesso. Após a atualização da página, o registro permaneceu disponível para consulta. Nenhum erro foi exibido.

Evidência

https://jam.dev/c/ffd5d0a7-a1a6-4416-ac9b-32f004e4836c

Bug associado

Nenhum identificado neste caso.

C26-CT04 — Nome obrigatório e grupo

Responsável: Fernando Cardoso dos Santos
Data da execução: 06/11/2026
Tipo: Negativo
Status: Aprovado
Sistema: https://sifitalfa.centrion.com.br/planos

Objetivo

Verificar se o sistema impede o cadastro de um plano sem nome ou sem grupo.

Pré-condições

Estar autenticado no sistema.
Acessar a tela de Planos.

Passos

Abrir o formulário Novo Plano.
Deixar o campo Nome vazio.
Selecionar o grupo Teste.
Preencher os demais campos válidos.
Clicar em Salvar Plano.
Fechar o formulário sem salvar.
Abrir Novo Plano novamente.
Informar o nome QA_FERNANDO_SEM_GRUPO_01.
Deixar o campo Grupo sem seleção.
Preencher os demais campos válidos.
Clicar em Salvar Plano.

Resultado esperado

O sistema deve impedir o cadastro quando o nome estiver vazio ou quando o grupo não estiver selecionado.

Resultado obtido

Na primeira tentativa, com o nome vazio, o sistema não salvou o plano e exibiu a mensagem “Erro ao salvar plano”. Na segunda tentativa, com o grupo sem seleção, o sistema exibiu um alerta e também impediu o salvamento. Nenhum plano inválido foi criado.

Evidência

https://jam.dev/c/29cf0588-e14a-466d-9df6-ad7c4d5c720c

Bug associado

Nenhum identificado neste caso.


C26-CT05 — Parcelas e valores inválidos

Responsável: Fernando Cardoso dos Santos
Data da execução: 06/11/2026
Tipo: Limite
Status: Aprovado
Sistema: https://sifitalfa.centrion.com.br/planos

Objetivo

Verificar o comportamento do sistema diante de parcelas e valores inválidos.

Pré-condições

Estar autenticado no sistema.
Acessar a tela de Planos.

Passos

Abrir o formulário Novo Plano.
Preencher um nome de teste e selecionar o grupo Teste.
Informar valores inválidos nos campos de parcelas e valores.
Tentar informar valor negativo no campo de valor mensal.
Clicar em Salvar Plano após cada tentativa.
Conferir se o sistema permite ou impede o salvamento.

Resultado esperado

O sistema deve impedir valores inválidos e não criar planos com parcelas ou valores inconsistentes.

Resultado obtido

O campo de valor não permitiu informar o valor negativo de R$ 100,00, mantendo o valor exibido em R$ 0,00. As tentativas inválidas não geraram um novo plano.

Evidência

https://jam.dev/c/0077add8-e8fd-491b-add7-3442d29a63e7

Bug associado

Nenhum identificado neste caso.


C26-CT06 — Personal e função dos professores

Responsável: Fernando Cardoso dos Santos
Data da execução: 06/11/2026
Tipo: Interação
Status: Aprovado
Sistema: https://sifitalfa.centrion.com.br/planos

Objetivo

Verificar o comportamento dos campos de Personal e função dos professores no cadastro de planos.

Pré-condições

Estar autenticado no sistema.
Acessar a tela de Planos.
Ter o grupo Teste disponível.

Passos

Abrir Novo Plano.
Preencher o nome QA_FERNANDO_PERSONAL_01.
Selecionar o grupo Teste.
Manter o status como Ativo.
Selecionar Mensalidade recorrente.
Informar 1 parcela e valor mensal de R$ 100,00.
Selecionar Tem Personal? como Sim.
Selecionar uma função disponível dos professores.
Manter Dependentes como 0.
Salvar o plano.
Pesquisar o plano e abrir pela lupa.

Resultado esperado

Ao selecionar Personal, o sistema deve disponibilizar a função dos professores e salvar o plano com os dados selecionados.

Resultado obtido

Os campos de Personal e função dos professores foram disponibilizados e selecionados. O plano foi salvo, localizado pela pesquisa e consultado posteriormente sem erro.

Evidência

https://jam.dev/c/73d9290a-1c2a-4ca4-b86d-f28c183b7c51

Bug associado

Nenhum identificado neste caso.

C26-CT07 — Dependentes de 0 a 6

Responsável: Fernando Cardoso dos Santos
Data da execução: 06/11/2026
Tipo: Limite
Status: Aprovado
Sistema: https://sifitalfa.centrion.com.br/planos

Objetivo

Verificar se o campo Dependentes disponibiliza opções de 0 a 6 e mantém o valor escolhido.

Pré-condições

Estar autenticado no sistema.
Acessar a tela de Planos.
Ter o grupo Teste disponível.

Passos

1. Abrir Novo Plano.
2. Preencher o nome QA_FERNANDO_DEPENDENTES_01.
3. Selecionar o grupo Teste.
4. Manter o status Ativo.
5. Selecionar Mensalidade recorrente.
6. Informar 1 parcela e valor mensal de R$ 100,00.
7. Informar valor de matrícula de R$ 0,00.
8. Manter Tem Personal? como Não.
9. Selecionar sequencialmente os dependentes 0, 1, 2, 3, 4, 5 e 6.
10. Salvar o plano.
11. Consultar o plano pela busca e pela lupa.

Resultado esperado

O campo deve disponibilizar as opções de 0 a 6, permitir selecionar o limite 6 e manter o valor escolhido no plano.

Resultado obtido

As opções de dependentes foram percorridas no formulário. O plano foi salvo e consultado novamente pela busca e pela lupa, sem erro visível.

Evidência

https://jam.dev/c/58a1c74e-59b1-451d-b083-7681c0415aaf

Bug associado

Nenhum identificado neste caso.

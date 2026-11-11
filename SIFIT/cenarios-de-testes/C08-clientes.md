C08 — Clientes

C08-CT01 — Cadastro mínimo válido

Responsável: Fernando Cardoso dos Santos
Data da execução: 08/11/2026
Tipo: Positivo
Status: Aprovado
Sistema: https://sifitalfa.centrion.com.br/clientes

Objetivo

Verificar se o sistema permite cadastrar um cliente utilizando somente os campos mínimos obrigatórios.

Requisito relacionado

Cadastro de cliente com dados obrigatórios.

Pré-condições

Estar autenticado no sistema.
Acessar a tela de Clientes.
Estar na tela de cadastro de novo cliente.

Dados utilizados

Nome: QA_FERNANDO_CLIENTE_01
Status: Ativo
Sexo: Masculino
Data de nascimento: 10/05/1995

Passos

1. Acessar a tela de Clientes.
2. Clicar em Novo Cliente.
3. Informar o nome QA_FERNANDO_CLIENTE_01.
4. Selecionar o status Ativo.
5. Selecionar o sexo Masculino.
6. Informar a data de nascimento.
7. Manter os demais campos opcionais sem preenchimento.
8. Clicar em Salvar.
9. Conferir se o cliente aparece na listagem.
10. Abrir o registro pela ação de visualização.

Resultado esperado

O sistema deve salvar o cliente com os campos mínimos preenchidos, exibir o registro na listagem e permitir sua visualização.

Resultado obtido

O cliente foi salvo com sucesso e apareceu na listagem. O registro foi aberto pela ação de visualização, apresentando o ID 410.

Data, navegador e executor

Data: 08/11/2026
Navegador: Google Chrome
Executor: Fernando Cardoso dos Santos

Evidência

https://jam.dev/c/127ed729-7fb2-4bad-ab84-8696bc9109c1

Bug associado

Nenhum identificado neste caso.

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

C08-CT02 — Cadastro completo válido

Responsável: Fernando Cardoso dos Santos
Data da execução: 10/11/2026
Tipo: Positivo
Status: Aprovado
Sistema: https://sifitalfa.centrion.com.br/clientes

Objetivo

Verificar se o sistema permite cadastrar um cliente preenchendo dados pessoais, documentos, contatos, endereço e informações complementares.

Requisito relacionado

Cadastro de cliente com dados completos.

Pré-condições

Estar autenticado no sistema.
Acessar a tela de Clientes.
Estar na tela de cadastro de novo cliente.

Dados utilizados

Nome: Fernando Cardoso
Status: Ativo
Sexo: Masculino
Data de nascimento: 17/09/2008
CPF: 111.111.111-11
RG: QA123456
Celular/WhatsApp: (44) 99812-5510
Telefone fixo: (44) 3363-5193
E-mail: cardosofernando112@gmail.com
CEP: 87485-000
País: Brasil
Estado: Paraná
Cidade: Douradina
Logradouro: Estrada Pereira 3km
Número: 0
Bairro: RURAL
Complemento: CASA
Usuário do aplicativo: Login

Passos

1. Acessar a tela de Clientes.
2. Clicar em Novo Cliente.
3. Preencher os dados pessoais do cliente.
4. Informar CPF e RG.
5. Preencher os dados de contato.
6. Preencher os dados de endereço.
7. Informar os dados complementares e do aplicativo.
8. Clicar em Salvar.
9. Conferir se o cliente aparece na listagem.
10. Abrir o registro pela ação de visualização.

Resultado esperado

O sistema deve salvar o cliente com os dados preenchidos, exibir o registro na listagem e permitir sua visualização.

Resultado obtido

O cliente foi salvo com sucesso, apareceu na listagem e foi aberto pela ação de visualização. O registro apresentou o ID 411.

Data, navegador e executor

Data: 10/11/2026
Navegador: Google Chrome
Executor: Fernando Cardoso dos Santos

Evidência

https://jam.dev/c/7605e2b1-3a5f-4ec8-8549-6460aef113b2

Bug associado

Nenhum identificado neste caso.

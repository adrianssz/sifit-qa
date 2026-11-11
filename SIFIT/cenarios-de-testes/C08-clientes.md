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

C08-CT03 — Nome vazio ou somente espaços

Responsável: Fernando Cardoso dos Santos
Data da execução: 10/11/2026
Tipo: Negativo
Status: Reprovado
Sistema: https://sifitalfa.centrion.com.br/clientes

Objetivo

Verificar se o sistema impede o cadastro de clientes sem nome ou com nome formado apenas por espaços.

Requisito relacionado

O campo Nome deve ser obrigatório e não deve aceitar somente espaços.

Pré-condições

Estar autenticado no sistema.
Acessar a tela de Clientes.
Abrir o formulário de novo cliente.

Dados utilizados

Status: Ativo
Sexo: Masculino
Data de nascimento: 14/06/2025
Nome vazio na primeira tentativa.
Nome contendo somente espaços na segunda tentativa.

Passos

1. Acessar Clientes.
2. Clicar em Novo Cliente.
3. Manter o campo Nome vazio.
4. Preencher os demais campos obrigatórios.
5. Clicar em Salvar.
6. Conferir a mensagem exibida.
7. Repetir o cadastro informando somente espaços no campo Nome.
8. Clicar em Salvar novamente.
9. Conferir o resultado na listagem.

Resultado esperado

O sistema deve impedir as duas tentativas e exigir um nome válido.

Resultado obtido

Na primeira tentativa, com o nome vazio, o sistema exibiu a mensagem “Preencha o nome”.

Na segunda tentativa, com apenas espaços, o sistema permitiu o cadastro e criou o cliente com o ID 412.

Data, navegador e executor

Data: 10/11/2026
Navegador: Google Chrome
Executor: Fernando Cardoso dos Santos

Evidência

https://jam.dev/c/595853db-69f0-4ec3-aae3-19bef2cd297e

Bug associado

BUG-FERNANDO-003 — Sistema permite cadastrar cliente com nome contendo somente espaços.

C08-CT04 — Status e sexo não selecionados

Responsável: Fernando Cardoso dos Santos
Data da execução: 10/11/2026
Tipo: Negativo
Status: Aprovado
Sistema: https://sifitalfa.centrion.com.br/clientes

Objetivo

Verificar se o sistema impede o cadastro quando os campos Status e Sexo não são selecionados.

Requisito relacionado

Os campos Status e Sexo devem ser obrigatórios no cadastro do cliente.

Pré-condições

Estar autenticado no sistema.
Acessar a tela de Clientes.
Abrir o formulário de novo cliente.

Dados utilizados

Nome: QA_FERNANDO_CLIENTE_STATUS_01
Data de nascimento: 17/09/2005
Status: inicialmente não selecionado
Sexo: inicialmente não selecionado

Passos

1. Acessar Clientes.
2. Clicar em Novo Cliente.
3. Informar o nome QA_FERNANDO_CLIENTE_STATUS_01.
4. Informar a data de nascimento.
5. Manter Status e Sexo sem seleção.
6. Clicar em Salvar.
7. Conferir a validação apresentada nos campos obrigatórios.
8. Selecionar as opções necessárias.
9. Clicar novamente em Salvar.
10. Conferir o cadastro na listagem.
11. Abrir o registro pela ação de visualização.

Resultado esperado

O sistema deve impedir o salvamento enquanto Status e Sexo não estiverem selecionados e permitir o cadastro após o preenchimento correto.

Resultado obtido

O sistema destacou os campos obrigatórios quando Status e Sexo não estavam selecionados. Após a seleção das opções, o cliente foi salvo com sucesso, apareceu na listagem e foi aberto pela visualização com o ID 413.

Data, navegador e executor

Data: 10/11/2026
Navegador: Google Chrome
Executor: Fernando Cardoso dos Santos

Evidência

https://jam.dev/c/562fa248-d8d2-4764-946c-a2098c597c88

Bug associado

Nenhum identificado neste caso.

C08-CT05 — Nascimento vazio, impossível ou futuro

Responsável: Fernando Cardoso dos Santos
Data da execução: 11/11/2026
Tipo: Negativo
Status: Reprovado
Sistema: https://sifitalfa.centrion.com.br/clientes

Objetivo

Verificar se o sistema valida corretamente datas de nascimento vazias, impossíveis e futuras.

Requisito relacionado

A data de nascimento deve ser válida e não pode ser futura.

Pré-condições

Estar autenticado no sistema.
Acessar Clientes.
Abrir o cadastro de novo cliente.

Dados utilizados

Nome: teste
Status: Ativo
Sexo: Masculino
Datas testadas: vazia, 31/02/2000 e 01/01/2030

Passos

1. Abrir o cadastro de novo cliente.
2. Informar o nome, status e sexo.
3. Tentar salvar sem informar a data de nascimento.
4. Informar 31/02/2000 e tentar salvar.
5. Informar 01/01/2030 e salvar.
6. Conferir o resultado na listagem e na visualização.

Resultado esperado

O sistema deve bloquear datas vazias, impossíveis e futuras.

Resultado obtido

O sistema bloqueou a data vazia e a data impossível 31/02/2000. Porém, aceitou 01/01/2030 e salvou o cliente, exibindo idade calculada de 4 anos.

Data, navegador e executor

Data: 11/11/2026
Navegador: Google Chrome
Executor: Fernando Cardoso dos Santos

Evidência

https://jam.dev/c/04471001-8a72-4239-b73a-f26df5574a35

Bug associado

BUG-FERNANDO-004 — Sistema permite cadastrar cliente com data de nascimento futura.

C08-CT06 — Nome com acentos, apóstrofo e hífen

Responsável: Fernando Cardoso dos Santos
Data da execução: 11/11/2026
Tipo: Positivo
Status: Aprovado
Sistema: https://sifitalfa.centrion.com.br/clientes

Objetivo

Verificar se o sistema aceita e mantém nomes com acentos, apóstrofo e hífen.

Requisito relacionado

O cadastro deve aceitar nomes válidos com caracteres especiais da língua portuguesa.

Pré-condições

Estar autenticado no sistema.
Acessar Clientes.
Abrir o cadastro de novo cliente.

Dados utilizados

Nome: QA_FERNANDO João D'Ávila-Silva
Status: Ativo
Sexo: Masculino
Data de nascimento: 09/02/2009

Passos

1. Acessar Clientes.
2. Clicar em Novo Cliente.
3. Informar o nome QA_FERNANDO João D'Ávila-Silva.
4. Selecionar o status Ativo.
5. Selecionar o sexo Masculino.
6. Informar a data de nascimento.
7. Clicar em Salvar.
8. Conferir se o cliente aparece na listagem.
9. Abrir o registro pela ação de visualização.
10. Conferir se o nome foi mantido corretamente.

Resultado esperado

O sistema deve aceitar o nome e mantê-lo exatamente como informado no cadastro e na visualização.

Resultado obtido

O cliente foi salvo com sucesso e apareceu na listagem. O registro foi aberto com o ID 413 e o nome QA_FERNANDO João D'Ávila-Silva foi mantido corretamente.

Data, navegador e executor

Data: 11/11/2026
Navegador: Google Chrome
Executor: Fernando Cardoso dos Santos

Evidência

https://jam.dev/c/2944fac4-3418-4720-8d9e-82895b95f279

Bug associado

Nenhum identificado neste caso.

C08-CT07 — CPF do cliente e do responsável

Responsável: Fernando Cardoso dos Santos
Data da execução: 11/11/2026
Tipo: Positivo
Status: Aprovado
Sistema: https://sifitalfa.centrion.com.br/clientes

Objetivo

Verificar o preenchimento dos campos de CPF do cliente e do responsável.

Requisito relacionado

O sistema deve permitir informar os documentos do cliente e do responsável.

Pré-condições

Estar autenticado no sistema.
Acessar Clientes.
Abrir o cadastro de novo cliente.

Dados utilizados

Nome: teste
Status: Ativo
Sexo: Masculino
Data de nascimento: 17/05/1999
CPF do cliente: 111.111.111-11
CPF do responsável: 222.222.222-22

Passos

1. Acessar Clientes.
2. Clicar em Novo Cliente.
3. Informar os dados obrigatórios.
4. Informar o CPF do cliente.
5. Habilitar o cadastro de responsável.
6. Informar o CPF do responsável.
7. Clicar em Salvar.
8. Conferir se o cliente aparece na listagem.
9. Abrir o registro pela visualização.
10. Conferir o cadastro realizado.

Resultado esperado

O sistema deve aceitar os CPFs informados, salvar o cliente e permitir sua visualização.

Resultado obtido

Os CPFs foram informados sem bloqueio. O cliente foi salvo com sucesso, apareceu na listagem e foi aberto pela visualização com o ID 414.

Data, navegador e executor

Data: 11/11/2026
Navegador: Google Chrome
Executor: Fernando Cardoso dos Santos

Evidência

https://jam.dev/c/f6709cf5-f152-4d1d-b6f3-508799f8313b

Bug associado

Nenhum identificado neste caso.

C08-CT08 — RG e tipo sanguíneo

Responsável: Fernando Cardoso dos Santos
Data da execução: 11/11/2026
Tipo: Positivo
Status: Aprovado
Sistema: https://sifitalfa.centrion.com.br/clientes

Objetivo

Verificar se o sistema permite informar e salvar o RG e o tipo sanguíneo do cliente.

Requisito relacionado

O cadastro deve permitir registrar documentos e tipo sanguíneo do cliente.

Pré-condições

Estar autenticado no sistema.
Acessar Clientes.
Abrir o cadastro de novo cliente.

Dados utilizados

Nome: QA_FERNANDO_CLIENTE_RG_01
Status: Ativo
Sexo: Masculino
Data de nascimento: 17/05/1995
RG: 123456
Tipo sanguíneo: O+

Passos

1. Acessar Clientes.
2. Clicar em Novo Cliente.
3. Informar os dados obrigatórios.
4. Informar o RG 123456.
5. Selecionar o tipo sanguíneo O+.
6. Clicar em Salvar.
7. Conferir se o cliente aparece na listagem.
8. Abrir o registro pela visualização.
9. Acessar a edição do cadastro.
10. Conferir o RG e o tipo sanguíneo salvos.

Resultado esperado

O sistema deve salvar o RG e o tipo sanguíneo informados e mantê-los no cadastro do cliente.

Resultado obtido

O cliente foi salvo com sucesso e apareceu na listagem. O registro foi aberto com o ID 415. Na edição, o RG 123456 e o tipo sanguíneo O+ foram exibidos corretamente.

Data, navegador e executor

Data: 11/11/2026
Navegador: Google Chrome
Executor: Fernando Cardoso dos Santos

Evidência

https://jam.dev/c/65242235-5496-4004-a362-6ae4b7c43c6d

Bug associado

Nenhum identificado neste caso.

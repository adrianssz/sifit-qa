# C11 — Contas a Receber

## C11-CT01 — Cadastrar conta válida

**Responsável:** Guilherme  
**Data da execução:** 14/11/2026  
**Tipo:** Positivo  
**Status:** Aprovado  
**Sistema:** https://sifitalfa.centrion.com.br/contas-receber

### Objetivo
Verificar se o sistema permite cadastrar e consultar uma conta a receber.

### Pré-condições
- Estar autenticado no sistema.
- Ter um cliente de teste cadastrado.

### Passos
1. Acessar Contas a Receber e clicar em Nova Conta.
2. Selecionar Pendente e o cliente 419.
3. Informar o valor de R$ 150,00 e conferir título, moeda e vencimento.
4. Salvar e consultar o registro criado.

### Resultado esperado
A conta deve ser cadastrada com os dados informados e permanecer disponível para consulta.

### Resultado obtido
Consegui cadastrar a conta **1623**, vinculada ao cliente **419**, no valor de R$ 150,00, com título Matrícula e status Pendente.

Também confirmei posteriormente a persistência do registro e o comportamento do campo Observação. Essas verificações complementares não constam na gravação.

### Evidência
[Assistir à gravação no Jam](https://jam.dev/c/cb152d23-965e-4a70-9c8c-3e54ed26fe43)

### Bug associado
Nenhum identificado neste caso.

---

## C11-CT02 — Cliente, título e valor ausentes

**Responsável:** Guilherme  
**Data da execução:** A confirmar  
**Tipo:** Negativo  
**Status:** Aprovado  
**Sistema:** https://sifitalfa.centrion.com.br/contas-receber

### Objetivo
Verificar se o sistema impede o cadastro de contas com informações obrigatórias ausentes.

### Pré-condições
- Acesso ao cadastro de Contas a Receber.
- Cliente de teste 419 disponível.

### Passos
1. Tentar salvar uma conta sem selecionar o cliente.
2. Repetir a tentativa com o título vazio.
3. Repetir com o valor não informado.
4. Verificar se o sistema impede cada cadastro.

### Resultado esperado
O sistema não deve permitir o cadastro de contas sem os campos obrigatórios.

### Resultado obtido
Realizei as três tentativas e o sistema bloqueou todos os cadastros incompletos.

### Evidência
[Assistir à gravação no Jam](https://jam.dev/c/a887eb3b-fe29-4659-a8f0-00373b2a33d8)

### Bug associado
Nenhum identificado neste caso.

---

## C11-CT03 — Valores inválidos e casas decimais

**Responsável:** Guilherme  
**Data da execução:** A confirmar  
**Tipo:** Limite  
**Status:** Reprovado  
**Sistema:** https://sifitalfa.centrion.com.br/contas-receber

### Objetivo
Verificar o tratamento de valores inválidos e o cadastro de valores monetários válidos.

### Pré-condições
- Cliente 419 cadastrado.
- Acesso ao formulário de nova conta.

### Passos
1. Testar valor negativo.
2. Testar valor zerado.
3. Tentar informar letras.
4. Testar um valor com mais de duas casas decimais.
5. Tentar cadastrar uma conta válida com R$ 150,50.
6. Consultar a listagem para verificar se o registro foi criado.

### Resultado esperado
O sistema deve tratar valores inválidos e permitir salvar uma conta com valor monetário válido.

### Resultado obtido
O campo não permitiu informar valores negativos nem letras. O sistema também impediu o cadastro com valor zerado.

Ao testar mais de duas casas decimais, houve alteração na formatação do valor.

Na tentativa com **R$ 150,50**, preenchi o cliente 419, o título Matrícula e os demais dados obrigatórios. Mesmo assim, o sistema apresentou **“Erro ao salvar conta a receber”**.

Conferi a listagem e confirmei que a conta não foi criada.

### Evidência
[Assistir à gravação no Jam](https://jam.dev/c/ba89e664-27c9-4e1f-aaba-ea643353cbc3)

### Bug associado
BUG-GUILHERME-001 — Falha ao salvar conta a receber com valor válido.

---

## C11-CT04 — Datas de vencimento e recebimento

**Responsável:** Guilherme  
**Data da execução:** 18/11/2026  
**Tipo:** Negativo  
**Status:** Reprovado  
**Sistema:** https://sifitalfa.centrion.com.br/contas-receber

### Objetivo
Verificar o cadastro de contas com diferentes datas de vencimento e o tratamento das datas financeiras.

### Pré-condições
- Cliente 419 cadastrado.
- Formulário de Contas a Receber disponível.

### Passos
1. Abrir Nova Conta e selecionar Pendente.
2. Informar cliente 419, título Matrícula e valor de R$ 150,00.
3. Tentar salvar com vencimento em 13/11/2026.
4. Repetir com vencimento em 14/11/2026.
5. Repetir com vencimento em 21/11/2026.
6. Conferir se as contas foram criadas.

### Resultado esperado
O sistema deve aceitar datas válidas de vencimento e permitir salvar os registros corretamente.

### Resultado obtido
Realizei as três tentativas com status Pendente. Em todas, o sistema apresentou erro no momento de salvar.

Conferi a listagem e confirmei que nenhuma das três contas foi criada.

A parte relacionada à data de recebimento não pôde ser concluída.

### Evidência
[Assistir à gravação no Jam](https://jam.dev/c/769ee2e7-54ee-4049-9451-f98722be72ce)

### Bug associado
BUG-GUILHERME-001 — Falha ao salvar contas a receber com diferentes datas de vencimento. Pode estar relacionada ao defeito identificado no C11-CT03, mas a causa não foi confirmada.

---

## C11-CT05 — Status Pendente, Recebido e Cancelado

**Responsável:** Guilherme  
**Data da execução:** 18/11/2026  
**Tipo:** Positivo  
**Status:** Bloqueado  
**Sistema:** https://sifitalfa.centrion.com.br/contas-receber

### Objetivo
Verificar o comportamento dos campos e a persistência dos status Pendente, Recebido e Cancelado.

### Pré-condições
- Acesso ao formulário de Contas a Receber.
- Conta 1623 disponível para consulta.

### Passos
1. Consultar a conta 1623 e conferir seu status.
2. Abrir Nova Conta.
3. Alternar entre Pendente, Recebido e Cancelado.
4. Conferir a alteração dos campos.
5. Cancelar o formulário sem salvar.
6. Testar os filtros por status.
7. Consultar novamente a conta 1623.

### Resultado esperado
O formulário deve apresentar os campos correspondentes a cada status. Os filtros devem funcionar corretamente e os registros existentes devem manter seus dados.

### Resultado obtido
Ao alternar entre os três status, confirmei que os campos do formulário mudaram conforme a seleção.

Os filtros por status funcionaram e a conta **1623 permaneceu como Pendente**.

A validação da interface foi satisfatória. Entretanto, a persistência de novos registros nos três status não foi testada, devido às falhas de salvamento identificadas anteriormente.

### Evidência
[Assistir à gravação no Jam](https://jam.dev/c/bce56981-0fe5-4625-ab34-9f86724b64a2)

### Bug associado
Validação completa dependente da correção ou investigação da falha de salvamento identificada nos C11-CT03 e C11-CT04.

---

## C11-CT07 — Recebimento maior que o saldo

**Responsável:** Guilherme  
**Data da execução:** 19/11/2026  
**Tipo:** Negativo  
**Status:** Reprovado  
**Sistema:** https://sifitalfa.centrion.com.br/contas-receber  
**Execução:** Automatizada pelo Chrome DevTools MCP; gravação do Jam iniciada e encerrada manualmente.

### Objetivo
Verificar o que acontece ao tentar receber um valor maior que o saldo de uma conta.

### Pré-condições
- Conta de teste **1667**, com título **QA_GUILHERME_CT07**, vinculada ao cliente **QA_GUILHERME_CLIENTE_001**.
- Conta Pendente, com R$ 52,00 a receber e nenhum valor recebido. Ela foi criada antes da gravação para este caso.

### Passos
1. Abrir a conta 1667 e conferir o valor de R$ 52,00 e o status Pendente.
2. Clicar em Efetuar Recebimento.
3. Informar R$ 53,00 em Valor Recebido.
4. Selecionar Manual SIFIT Pix como tipo de pagamento e Teste como local de recebimento.
5. Clicar em Salvar. Na confirmação sobre o caixa não ser de hoje, clicar em Confirmar.
6. Consultar a conta novamente e comparar o valor a receber, o valor recebido e o status.

### Resultado esperado
O sistema deve tratar o excedente de R$ 1,00 de forma explícita e impedir que a conta fique com valores financeiros inconsistentes. Sem uma regra de excedente apresentada ao usuário, o recebimento acima do saldo deve ser bloqueado.

### Resultado obtido
O sistema apresentou apenas o aviso **“O caixa aberto não é de hoje, deseja continuar?”**. Após a confirmação, aceitou o recebimento de **R$ 53,00** para a conta de **R$ 52,00**.

Na listagem e na consulta posterior, a conta 1667 apareceu como **Recebido**, com **R$ 53,00 recebidos**. O valor recebido ficou **R$ 1,00 acima** do valor a receber. Não foi apresentada uma regra para o excedente. O recebimento foi feito uma única vez.

### Evidência
[Assistir à gravação no Jam](https://jam.dev/c/6417ee9e-5993-4c45-b54d-55d655534a08)

### Bug associado
BUG-GUILHERME-002 — Recebimento acima do valor da conta é aceito.

---

## C11-CT08 — Criar cópias de contas a receber

**Responsável:** Guilherme  
**Data da execução:** 19/11/2026  
**Tipo:** Condicional  
**Status:** Reprovado  
**Sistema:** https://sifitalfa.centrion.com.br/contas-receber  
**Execução:** Automatizada pelo Codex com Chrome DevTools MCP; gravação do Jam iniciada e encerrada manualmente.

### Objetivo
Quis verificar se a opção Criar Cópias gera registros que eu possa conferir pela quantidade e pelos vencimentos, sem duplicidade indevida.

### Pré-condições
- Cliente de teste **419 — QA_GUILHERME_CLIENTE_001** disponível.
- Nenhuma conta com o título **QA_GUILHERME_CT08** aparecia na consulta antes do cadastro.

### Passos
1. Abri Nova Conta e selecionei o status Pendente e o cliente 419.
2. Informei o título QA_GUILHERME_CT08, o valor de R$ 10,00 e mantive o vencimento em 19/11/2026.
3. Marquei Criar Cópias como Sim e salvei uma única vez.
4. Consultei as contas do cliente 419 com o período de vencimento até 31/12/2027.
5. Abri o registro encontrado para conferir código, valor, vencimento e status.

### Resultado esperado
O sistema deve criar as cópias de forma identificável, permitir conferir quantos registros foram gerados e seus vencimentos, e evitar duplicidade indevida. O roteiro não define uma quantidade específica de cópias.

### Resultado obtido
Encontrei somente a conta **1668**, com título **QA_GUILHERME_CT08**, status **Pendente**, valor de **R$ 10,00** e vencimento em **19/11/2026**. Não encontrei outro registro desse teste na consulta até 31/12/2027.

Como a opção não apresentou campos de quantidade ou intervalo de vencimentos, não consegui identificar uma cópia adicional nem conferir uma sequência de datas. Não repeti o salvamento para evitar criar registros duplicados.

### Evidência
[Assistir à gravação no Jam](https://jam.dev/c/f5e5018b-88c8-4f21-bd5c-1fc564ea9746)

### Bug associado
BUG-GUILHERME-003 — Possível falha na criação de cópias de contas a receber.

---

## C11-CT09 — Tipo e local de recebimento

**Responsável:** Guilherme  
**Data da execução:** 19/11/2026  
**Tipo:** Positivo  
**Status:** Reprovado  
**Sistema:** https://sifitalfa.centrion.com.br/contas-receber  
**Execução:** Automatizada pelo Codex com Chrome DevTools MCP; gravação do Jam iniciada e encerrada manualmente.

### Objetivo
Quis conferir se o valor, o tipo e o local de recebimento ficam registrados corretamente e se os campos adicionais aparecem ao escolher Cartão de Crédito.

### Pré-condições
- Criei antes da gravação a conta **1669 — QA_GUILHERME_CT09**, vinculada ao cliente **419 — QA_GUILHERME_CLIENTE_001**.
- A conta estava Pendente, com **R$ 50,00** a receber e nenhum valor recebido.

### Passos
1. Na preparação, abri Efetuar Recebimento e selecionei Cartão de Crédito para observar os campos adicionais, sem salvar.
2. Como Bandeira e Parcelas não ofereceram opções, deixei o formulário com **Manual SIFIT Pix** e local **Teste**.
3. Durante a gravação, conferi o valor recebido de **R$ 50,00** e salvei uma única vez.
4. Confirmei o aviso de que o caixa aberto não era de hoje.
5. Consultei a conta 1669 para conferir valor, status, tipo e local registrados.

### Resultado esperado
Eu esperava encontrar o recebimento de R$ 50,00, o tipo Manual SIFIT Pix e o local Teste na consulta. Para Cartão de Crédito, esperava conseguir escolher bandeira e parcelas ou receber uma explicação clara sobre a indisponibilidade.

### Resultado obtido
**Recebimento Manual SIFIT Pix:** o sistema salvou R$ 50,00, marcou a conta como **Recebido** e mostrou **Manual SIFIT Pix** ao consultar novamente. Não repeti o salvamento.

**Local de recebimento:** selecionei **Teste** antes de salvar, mas a consulta exibiu **“entrada”** em Local de Recebimento. Ao reabrir a edição, o seletor não mostrou um local selecionado. Assim, não consegui confirmar que a referência Teste ficou registrada corretamente.

**Campos condicionais do Cartão de Crédito:** na preparação, Bandeira e Parcelas ficaram sem opções mesmo após selecionar Cartão de Crédito novamente. Os campos de juros e taxa eram somente leitura. Não fiz um recebimento por cartão; essa parte segue pendente de investigação.

Classifiquei o caso como Reprovado porque a consulta não confirmou o local selecionado. A validação do cartão permanece pendente e não foi considerada aprovada.

### Evidência
[Assistir à gravação do recebimento no Jam](https://jam.dev/c/d69137fc-dbfd-474b-8b77-040852b7fb49)

A inspeção das opções de Cartão de Crédito ocorreu antes da gravação.

### Bugs associados
- BUG-GUILHERME-004 — Bandeira e parcelas sem opções no recebimento por cartão; a investigar.
- BUG-GUILHERME-005 — Consulta não confirma o local Teste após o recebimento.

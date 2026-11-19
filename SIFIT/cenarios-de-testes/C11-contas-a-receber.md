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
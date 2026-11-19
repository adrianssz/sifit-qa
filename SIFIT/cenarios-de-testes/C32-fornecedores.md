# C32 — Fornecedores — Testes de Guilherme

**Responsável:** Guilherme
**Fonte:** [Inventário](../../Invent%C3%A1rio.md)
**Estado:** Roteiros pendentes de execução.

---

## C32-CT01 — Cadastrar pessoa física

**Responsável:** Guilherme
**Tipo:** Positivo
**Status:** Pendente

### Objetivo
Conferir o cadastro de fornecedor pessoa física.

### Pré-condições
Dados fictícios QA_GUILHERME e documento de teste adequado ao tipo.

### Passos a executar
1. Escolher Pessoa Física e conferir os campos.
2. Informar nome e documento de teste nos campos exigidos.
3. Salvar e consultar o fornecedor..

### Resultado esperado
O cadastro deve guardar os campos e o documento adequados à pessoa física.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C32-CT02 — Cadastrar pessoa jurídica

**Responsável:** Guilherme
**Tipo:** Positivo
**Status:** Pendente

### Objetivo
Conferir o cadastro de fornecedor pessoa jurídica.

### Pré-condições
Dados fictícios QA_GUILHERME e CNPJ de teste disponível.

### Passos a executar
1. Escolher Pessoa Jurídica e preencher os dados exigidos.
2. Salvar o cadastro.
3. Reabrir e conferir CNPJ e demais informações..

### Resultado esperado
O cadastro deve preservar CNPJ e dados correspondentes à pessoa jurídica.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C32-CT03 — Alternar tipo de pessoa

**Responsável:** Guilherme
**Tipo:** Interação
**Status:** Pendente

### Objetivo
Conferir máscara e validação ao trocar o tipo de fornecedor.

### Pré-condições
Formulário de fornecedor aberto, sem registro de terceiros em edição.

### Passos a executar
1. Alternar entre Pessoa Física e Pessoa Jurídica.
2. Observar os campos e máscaras de CPF e CNPJ.
3. Testar a validação aplicável sem salvar dados inválidos..

### Resultado esperado
Os campos e a validação do documento devem acompanhar o tipo selecionado.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C32-CT04 — Nome e documento inválidos

**Responsável:** Guilherme
**Tipo:** Negativo
**Status:** Pendente

### Objetivo
Verificar obrigatoriedade, formato e possível duplicidade de fornecedor.

### Pré-condições
Formulário acessível e registros de teste próprios para consulta de duplicidade.

### Passos a executar
1. Tentar salvar sem nome.
2. Testar documento em formato inválido.
3. Verificar eventual duplicidade usando apenas dados próprios..

### Resultado esperado
O sistema deve validar nome e documento conforme as regras confirmadas e tratar duplicidade quando aplicável.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C32-CT05 — E-mail e telefones

**Responsável:** Guilherme
**Tipo:** Negativo
**Status:** Pendente

### Objetivo
Conferir validação dos contatos do fornecedor.

### Pré-condições
Formulário de fornecedor e dados próprios de teste.

### Passos a executar
1. Informar e-mail inválido e observar a validação.
2. Testar telefone e celular incompletos separadamente.
3. Conferir se os dados inválidos são recusados ou sinalizados..

### Resultado esperado
Formatos inválidos e números incompletos devem ser tratados conforme as regras dos campos.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C32-CT06 — Estado, cidade e CEP

**Responsável:** Guilherme
**Tipo:** Interação
**Status:** Pendente

### Objetivo
Conferir dependência entre localização e endereço salvo.

### Pré-condições
Fornecedor QA_GUILHERME ou formulário novo disponível.

### Passos a executar
1. Selecionar estado e observar as cidades disponíveis.
2. Informar cidade e CEP de teste.
3. Salvar quando válido e consultar o endereço..

### Resultado esperado
Cidade e endereço devem corresponder ao estado e CEP informados.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C32-CT07 — Status, edição e observação

**Responsável:** Guilherme
**Tipo:** Positivo
**Status:** Pendente

### Objetivo
Conferir persistência de situação e observação do fornecedor.

### Pré-condições
Fornecedor próprio existente e ação de edição disponível.

### Passos a executar
1. Consultar status e observação atuais.
2. Editar somente os campos de teste e confirmar.
3. Reabrir o cadastro e comparar os dados..

### Resultado esperado
Somente alterações confirmadas devem persistir, incluindo status e observação.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C32-CT08 — Vínculo com conta a pagar

**Responsável:** Guilherme
**Tipo:** Integração
**Status:** Pendente

### Objetivo
Conferir seleção do fornecedor em conta a pagar e tratar vínculos.

### Pré-condições
Fornecedor QA_GUILHERME e conta a pagar própria vinculada.

### Passos a executar
1. Selecionar o fornecedor no cadastro da conta e salvar.
2. Consultar o vínculo nos dois módulos.
3. Mapear a regra de exclusão sem apagar dados de terceiros..

### Resultado esperado
A conta deve apontar para o fornecedor correto e operações sobre vínculos devem respeitar dependências.

### Resultado obtido
Não executado.

### Evidência
Pendente.

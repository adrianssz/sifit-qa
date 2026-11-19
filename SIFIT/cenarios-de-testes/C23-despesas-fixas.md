# C23 — Despesas Fixas — Testes de Guilherme

**Responsável:** Guilherme
**Fonte:** [Inventário](../../Invent%C3%A1rio.md)
**Estado:** Roteiros pendentes de execução.

---

## C23-CT01 — Cadastro e edição de despesa

**Responsável:** Guilherme
**Tipo:** Dependência
**Status:** Pendente

### Objetivo
Mapear o formulário de despesa fixa antes de completar o teste funcional.

### Pré-condições
Acesso ao módulo Despesas Fixas e registro próprio descartável, se o formulário permitir.

### Passos a executar
1. Abrir o cadastro e identificar os campos.
2. Preparar uma despesa QA_GUILHERME conforme as exigências observadas.
3. Salvar e reabrir para verificar edição, se as ações estiverem disponíveis..

### Resultado esperado
O formulário e as ações disponíveis devem ser identificados antes de concluir cadastro e edição.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C23-CT02 — Nome, valor e recorrência

**Responsável:** Guilherme
**Tipo:** Dependência
**Status:** Pendente

### Objetivo
Conferir obrigatoriedade e formatos dos campos centrais da despesa.

### Pré-condições
Formulário de inclusão localizado; opções de recorrência identificadas.

### Passos a executar
1. Testar nome ou valor ausente separadamente.
2. Verificar formatos monetários aceitos.
3. Selecionar cada recorrência disponível e conferir os campos dependentes..

### Resultado esperado
Campos obrigatórios e formato monetário devem ser validados; opções de recorrência devem corresponder à tela.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C23-CT03 — Recorrências diária, semanal, mensal, trimestral, semestral e anual

**Responsável:** Guilherme
**Tipo:** Condicional
**Status:** Pendente

### Objetivo
Conferir as datas geradas por cada recorrência disponível.

### Pré-condições
Despesa própria e geração recorrente disponíveis; período de observação definido.

### Passos a executar
1. Preparar cada periodicidade disponível em registros separados.
2. Consultar as datas geradas, incluindo um mês curto.
3. Comparar intervalo e quantidade sem repetir geração..

### Resultado esperado
As datas geradas devem seguir a periodicidade escolhida, inclusive na passagem por mês curto.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C23-CT04 — Status ativo/inativo

**Responsável:** Guilherme
**Tipo:** Integração
**Status:** Pendente

### Objetivo
Conferir o efeito da situação da despesa fixa em lançamentos futuros.

### Pré-condições
Despesa recorrente QA_GUILHERME e próximas ocorrências identificadas.

### Passos a executar
1. Consultar uma despesa ativa e suas ocorrências.
2. Alterar para inativa quando permitido.
3. Conferir a geração de novas despesas e o histórico já existente..

### Resultado esperado
O status deve ter o efeito previsto na geração futura sem alterar indevidamente o histórico.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C23-CT05 — Pesquisa e total listado

**Responsável:** Guilherme
**Tipo:** Filtro
**Status:** Pendente

### Objetivo
Conciliar filtros e soma da listagem de despesas fixas.

### Pré-condições
Despesas próprias com código, nome, status, valor e recorrência conhecidos.

### Passos a executar
1. Pesquisar por código e nome.
2. Aplicar status e recorrência.
3. Somar os valores exibidos e comparar com o total da lista..

### Resultado esperado
A pesquisa deve retornar registros compatíveis e o total listado deve corresponder aos itens mostrados.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C23-CT06 — Geração em contas a pagar

**Responsável:** Guilherme
**Tipo:** Integração
**Status:** Pendente

### Objetivo
Conferir lançamentos gerados por despesas fixas.

### Pré-condições
Despesa recorrente própria e vínculo com Contas a Pagar confirmados.

### Passos a executar
1. Anotar ocorrências da despesa e contas a pagar existentes.
2. Executar ou aguardar uma geração prevista, conforme a função disponível.
3. Comparar títulos, valores, datas e possíveis duplicidades..

### Resultado esperado
Os títulos gerados devem corresponder à despesa e não se repetir indevidamente no mesmo período.

### Resultado obtido
Não executado.

### Evidência
Pendente.

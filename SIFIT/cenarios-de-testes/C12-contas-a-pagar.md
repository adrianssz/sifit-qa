# C12 — Contas a Pagar — Testes de Guilherme

**Responsável:** Guilherme
**Fonte:** [Inventário](../../Invent%C3%A1rio.md)
**Estado:** Roteiros pendentes de execução.

---

## C12-CT01 — Cadastrar conta válida de fornecedor

**Responsável:** Guilherme
**Tipo:** Positivo
**Status:** Pendente

### Objetivo
Verificar o cadastro completo de uma conta a pagar para fornecedor.

### Pré-condições
Fornecedor de teste QA_GUILHERME disponível; documento, valor, vencimento e local definidos.

### Passos a executar
1. Abrir Nova Conta e escolher o fornecedor próprio.
2. Informar título, documento, vencimento, valor e local.
3. Salvar uma vez e consultar o registro..

### Resultado esperado
A conta deve guardar título, fornecedor, documento, vencimento, valor e local informados.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C12-CT02 — Despesa de colaborador

**Responsável:** Guilherme
**Tipo:** Positivo
**Status:** Pendente

### Objetivo
Conferir o formulário quando a despesa é vinculada a um colaborador.

### Pré-condições
Colaborador de teste QA_GUILHERME disponível; formulário de conta a pagar acessível.

### Passos a executar
1. Alternar o tipo para Pagto. Colaborador.
2. Selecionar o colaborador próprio e conferir os campos que mudam.
3. Preencher os campos exigidos e consultar o resultado após salvar..

### Resultado esperado
O colaborador e os campos dependentes devem corresponder ao tipo escolhido.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C12-CT03 — Despesa fixa e variável

**Responsável:** Guilherme
**Tipo:** Positivo
**Status:** Pendente

### Objetivo
Conferir a classificação da despesa e as opções de recorrência, quando existirem.

### Pré-condições
Referência própria para conta a pagar; categorias e tipos de despesa identificados na tela.

### Passos a executar
1. Cadastrar uma despesa variável com a categoria adequada.
2. Preparar uma despesa fixa e verificar se há recorrência.
3. Consultar as contas criadas e comparar tipo, categoria e datas..

### Resultado esperado
A categoria e o tipo devem ser preservados; uma recorrência só deve ser avaliada se a opção existir.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C12-CT04 — Referência, título, documento ou valor ausentes

**Responsável:** Guilherme
**Tipo:** Negativo
**Status:** Pendente

### Objetivo
Verificar os campos exigidos para cada tipo de conta a pagar.

### Pré-condições
Formulário disponível e obrigatoriedade dos campos confirmada na tela.

### Passos a executar
1. Omitir uma referência exigida e tentar salvar.
2. Repetir com título, documento ou valor ausente, um campo por tentativa.
3. Conferir as mensagens e se alguma conta incompleta foi criada..

### Resultado esperado
O sistema deve exigir os campos obrigatórios do tipo escolhido e não gravar conta incompleta.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C12-CT05 — Valores e datas inválidos

**Responsável:** Guilherme
**Tipo:** Negativo
**Status:** Pendente

### Objetivo
Conferir a validação de valores e datas no cadastro ou pagamento.

### Pré-condições
Conta de teste própria e formatos aceitos identificados antes das tentativas.

### Passos a executar
1. Informar valores incompatíveis e verificar a resposta.
2. Testar datas inválidas ou incoerentes nas opções disponíveis.
3. Conferir que nenhum pagamento incorreto foi registrado..

### Resultado esperado
Entradas incompatíveis devem ser rejeitadas sem registrar pagamento incorreto.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C12-CT06 — Status pendente, pago e cancelado

**Responsável:** Guilherme
**Tipo:** Positivo
**Status:** Pendente

### Objetivo
Conferir como saldo e situação mudam após operações permitidas.

### Pré-condições
Contas descartáveis QA_GUILHERME para cada situação; ações disponíveis mapeadas.

### Passos a executar
1. Consultar uma conta pendente e anotar seu saldo.
2. Executar pagamento ou cancelamento somente quando a ação estiver disponível.
3. Reabrir os registros e comparar status e saldo..

### Resultado esperado
Cada operação permitida deve deixar o saldo e o status coerentes.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C12-CT07 — Pagamentos parciais, se disponíveis

**Responsável:** Guilherme
**Tipo:** Condicional
**Status:** Pendente

### Objetivo
Verificar o saldo restante em um pagamento parcial, caso o recurso exista.

### Pré-condições
Conta própria pendente; opção de pagamento parcial confirmada antes de operar.

### Passos a executar
1. Identificar se o formulário aceita valor menor que o saldo.
2. Se aceitar, pagar parcialmente uma única vez.
3. Conferir recebido, restante, status e ausência de duplicidade..

### Resultado esperado
O saldo deve refletir o pagamento parcial sem quitar indevidamente nem duplicar a operação.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C12-CT08 — Filtros por código, pessoa, data e status

**Responsável:** Guilherme
**Tipo:** Filtro
**Status:** Pendente

### Objetivo
Conferir as buscas de contas a pagar, inclusive sem resultados.

### Pré-condições
Contas próprias com códigos, pessoas, datas e situações conhecidas.

### Passos a executar
1. Consultar por código e por fornecedor ou colaborador.
2. Variar tipo de data, intervalo e status.
3. Pesquisar um valor sem correspondência e conferir a lista..

### Resultado esperado
Cada filtro deve retornar registros correspondentes; a busca sem correspondência deve mostrar ausência de resultados.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C12-CT09 — Total a pagar, restante e atrasadas

**Responsável:** Guilherme
**Tipo:** Cálculo
**Status:** Pendente

### Objetivo
Conciliar os indicadores de contas a pagar com a lista do período.

### Pré-condições
Contas de teste com valores, vencimentos e situações conhecidos.

### Passos a executar
1. Definir um período e consultar os registros.
2. Somar valores a pagar e saldos restantes.
3. Comparar os totais e atrasadas com os indicadores exibidos..

### Resultado esperado
Total a pagar, restante e atrasadas devem ser conciliáveis com a consulta e o período.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C12-CT10 — Paginação

**Responsável:** Guilherme
**Tipo:** Lista
**Status:** Pendente

### Objetivo
Verificar a navegação entre páginas da listagem.

### Pré-condições
Quantidade de contas suficiente para mais de uma página ou controle de tamanho disponível.

### Passos a executar
1. Selecionar um tamanho de página disponível.
2. Avançar e voltar quando houver mais páginas.
3. Comparar quantidade mostrada, códigos e total informado..

### Resultado esperado
A paginação deve mostrar a quantidade selecionada sem repetir ou omitir registros.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C12-CT11 — Cancelar e reabrir cadastro

**Responsável:** Guilherme
**Tipo:** Negativo
**Status:** Pendente

### Objetivo
Conferir que cancelar o formulário não grava dados.

### Pré-condições
Formulário acessível e identificador QA_GUILHERME reservado para a tentativa.

### Passos a executar
1. Preencher dados de uma nova conta e cancelar sem salvar.
2. Pesquisar o identificador usado.
3. Reabrir o cadastro e salvar apenas uma alteração confirmada, se aplicável..

### Resultado esperado
O cancelamento não deve criar conta; somente alterações confirmadas devem persistir.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C12-CT12 — Integração com caixa

**Responsável:** Guilherme
**Tipo:** Integração
**Status:** Pendente

### Objetivo
Conferir o efeito de um pagamento no caixa de teste.

### Pré-condições
Conta própria pendente; caixa de teste e vínculo com o local de pagamento confirmados.

### Passos a executar
1. Anotar saldo e movimentos do caixa.
2. Pagar uma conta própria uma única vez.
3. Conferir lançamento de saída, valor, origem e novo saldo..

### Resultado esperado
O pagamento deve gerar a saída prevista e manter o saldo coerente no caixa.

### Resultado obtido
Não executado.

### Evidência
Pendente.

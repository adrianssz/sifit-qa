# C21 — Caixas — Testes de Guilherme

**Responsável:** Guilherme
**Fonte:** [Inventário](../../Invent%C3%A1rio.md)
**Estado:** Roteiros pendentes de execução.

---

## C21-CT01 — Abrir caixa de teste

**Responsável:** Guilherme
**Tipo:** Dependência
**Status:** Pendente

### Objetivo
Mapear e executar a abertura de um caixa próprio.

### Pré-condições
Local e responsável de teste disponíveis; situação inicial do caixa conhecida.

### Passos a executar
1. Abrir o formulário e identificar local, responsável, data e valores exigidos.
2. Informar dados de teste e confirmar a abertura.
3. Consultar o caixa criado e anotar seu código..

### Resultado esperado
A abertura deve registrar os dados exigidos e mostrar o caixa na situação correta.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C21-CT02 — Abertura repetida

**Responsável:** Guilherme
**Tipo:** Regra a confirmar
**Status:** Pendente

### Objetivo
Descobrir como o sistema trata uma segunda abertura no mesmo local.

### Pré-condições
Caixa de teste já aberto e regra de abertura consultada antes da tentativa.

### Passos a executar
1. Anotar o caixa aberto e seu local.
2. Tentar nova abertura no mesmo local com dados próprios.
3. Conferir resposta e quantidade de caixas abertos..

### Resultado esperado
O sistema deve aplicar a regra confirmada para abertura repetida sem criar duplicidade indevida.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C21-CT03 — Movimentos de entrada e saída

**Responsável:** Guilherme
**Tipo:** Integração
**Status:** Pendente

### Objetivo
Conferir movimentos financeiros e saldo do caixa.

### Pré-condições
Caixa próprio aberto; origem dos lançamentos de teste identificada.

### Passos a executar
1. Anotar saldo e movimentos iniciais.
2. Gerar uma entrada e uma saída com dados de teste pelos fluxos permitidos.
3. Conferir origem, valor, saldo e ausência de duplicidade..

### Resultado esperado
Movimentos e saldo devem refletir uma vez cada operação de teste.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C21-CT04 — Fechamento e conferência

**Responsável:** Guilherme
**Tipo:** Dependência
**Status:** Pendente

### Objetivo
Conferir valores calculados e informados no fechamento do caixa.

### Pré-condições
Caixa próprio aberto com movimentos conhecidos; campos de fechamento mapeados.

### Passos a executar
1. Abrir o fechamento e anotar valores calculados.
2. Informar os valores exigidos e concluir, se permitido.
3. Comparar situação final e eventuais divergências..

### Resultado esperado
O fechamento deve apresentar e tratar valores e divergências conforme a regra confirmada.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C21-CT05 — Operar caixa fechado

**Responsável:** Guilherme
**Tipo:** Condicional
**Status:** Pendente

### Objetivo
Verificar restrições de operação após o fechamento.

### Pré-condições
Caixa próprio fechado; regra de reabertura identificada, caso exista.

### Passos a executar
1. Consultar a situação do caixa fechado.
2. Tentar somente ações de teste permitidas nessa situação.
3. Verificar bloqueio, mensagem e opção de reabertura, se disponível..

### Resultado esperado
O sistema deve respeitar a regra de operação e reabertura do caixa fechado.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C21-CT06 — Filtros e paginação

**Responsável:** Guilherme
**Tipo:** Filtro
**Status:** Pendente

### Objetivo
Conferir consulta, indicadores e páginas da lista de caixas.

### Pré-condições
Caixas de teste com datas e situações conhecidas; filtros disponíveis.

### Passos a executar
1. Consultar por período e status.
2. Avançar entre páginas, se houver mais de uma.
3. Comparar registros com indicadores de caixas abertos e fechados..

### Resultado esperado
Filtros e paginação devem mostrar os caixas correspondentes e indicadores coerentes.

### Resultado obtido
Não executado.

### Evidência
Pendente.

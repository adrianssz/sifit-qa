# C47 — Fluxos integrados — Testes de Guilherme

**Responsável:** Guilherme
**Fonte:** [Inventário](../../Invent%C3%A1rio.md)
**Estado:** Roteiros pendentes de execução.

---

## C47-CT02 — Conta recebida/paga → caixa → relatórios

**Responsável:** Guilherme
**Tipo:** Integração
**Status:** Pendente

### Objetivo
Conciliar um fluxo financeiro próprio entre conta, caixa e relatório.

### Pré-condições
Conta a receber ou pagar QA_GUILHERME e caixa de teste identificados.

### Passos a executar
1. Anotar status e valores da conta antes da operação.
2. Executar a operação financeira permitida uma vez.
3. Comparar movimento no caixa e dados do relatório..

### Resultado esperado
Saldo, status e registros financeiros devem ser consistentes nos três módulos.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C47-CT06 — Persistência após atualização e novo login

**Responsável:** Guilherme
**Tipo:** Persistência
**Status:** Pendente

### Objetivo
Conferir se dados confirmados continuam disponíveis depois de atualizar e entrar novamente.

### Pré-condições
Registro próprio salvo e código anotado; acesso de teste para novo login.

### Passos a executar
1. Consultar o registro e anotar campos confirmados.
2. Atualizar a página e fazer novo login autorizado.
3. Reabrir pelo código e comparar os dados..

### Resultado esperado
Os dados confirmados devem continuar disponíveis após a atualização e o novo login.

### Resultado obtido
Não executado.

### Evidência
Pendente.

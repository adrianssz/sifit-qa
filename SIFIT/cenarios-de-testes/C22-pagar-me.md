# C22 — Pagar.me — Testes de Guilherme

**Responsável:** Guilherme
**Fonte:** [Inventário](../../Invent%C3%A1rio.md)
**Estado:** Roteiros pendentes de execução.

---

## C22-CT01 — Carregamento e ausência de integração

**Responsável:** Guilherme
**Tipo:** Investigação
**Status:** Pendente

### Objetivo
Conferir o estado real do painel Pagar.me sem presumir integração ativa.

### Pré-condições
Acesso ao painel; situação da integração conhecida ou identificável na interface.

### Passos a executar
1. Abrir o painel e observar carregamento, valores e mensagens.
2. Verificar o estado exibido quando não houver integração.
3. Distinguir dados reais de valores apenas ilustrativos..

### Resultado esperado
A tela deve comunicar o estado real e qualquer erro de forma compreensível, sem apresentar exemplos como dados reais.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C22-CT02 — Saldos e recebíveis

**Responsável:** Guilherme
**Tipo:** Condicional
**Status:** Pendente

### Objetivo
Comparar saldos e recebíveis quando houver sandbox autorizado.

### Pré-condições
Integração de teste ativa e dados do sandbox acessíveis; nenhuma conta real envolvida.

### Passos a executar
1. Consultar disponível, em processamento, futuro e recebido.
2. Comparar os valores com a fonte autorizada do sandbox.
3. Registrar diferenças sem presumir a causa..

### Resultado esperado
Os valores do painel devem corresponder aos dados do ambiente de teste autorizado.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C22-CT03 — Transações e assinaturas

**Responsável:** Guilherme
**Tipo:** Condicional
**Status:** Pendente

### Objetivo
Conferir informações mostradas nas listas financeiras da integração.

### Pré-condições
Sandbox autorizado com transações e assinaturas de teste.

### Passos a executar
1. Aplicar os períodos disponíveis.
2. Consultar transações e assinaturas.
3. Comparar valor, método e status com os registros de teste..

### Resultado esperado
Valores, métodos, status e períodos devem corresponder aos dados consultados no sandbox.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C22-CT04 — Extrato, relatório e previsão

**Responsável:** Guilherme
**Tipo:** Condicional
**Status:** Pendente

### Objetivo
Verificar os destinos e filtros das consultas da integração.

### Pré-condições
Sandbox autorizado e dados de teste para extrato, relatório ou previsão.

### Passos a executar
1. Abrir cada opção disponível sem fazer transferência.
2. Aplicar filtros de teste.
3. Conferir destino, período e dados apresentados..

### Resultado esperado
Extrato, relatório e previsão devem usar os filtros escolhidos e apresentar dados compatíveis.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C22-CT05 — Nova cobrança

**Responsável:** Guilherme
**Tipo:** Condicional
**Status:** Pendente

### Objetivo
Conferir uma cobrança somente em ambiente seguro de teste.

### Pré-condições
Sandbox autorizado, destinatário de teste e efeito da cobrança delimitado.

### Passos a executar
1. Abrir Nova cobrança e identificar campos exigidos.
2. Informar somente dados de teste.
3. Criar e consultar a cobrança uma vez, se o sandbox permitir..

### Resultado esperado
A cobrança de teste deve ser registrada sem cobrança ou mensagem para cliente real.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C22-CT06 — Saque e configurações da integração

**Responsável:** Guilherme
**Tipo:** Condicional
**Status:** Pendente

### Objetivo
Documentar controles de saque e pré-condições da integração.

### Pré-condições
Acesso de leitura ao painel; sandbox e autorização específica para qualquer operação financeira ainda precisam ser confirmados.

### Passos a executar
1. Localizar as opções de saque e configuração sem executar transferência.
2. Registrar campos, limites e pré-condições visíveis.
3. Planejar execução posterior apenas se houver sandbox e autorização específica..

### Resultado esperado
A existência e as pré-condições devem ficar claras; nenhuma operação de saque é prevista nesta etapa.

### Resultado obtido
Não executado.

### Evidência
Pendente.

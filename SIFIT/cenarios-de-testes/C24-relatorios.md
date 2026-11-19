# C24 — Relatórios — Testes de Guilherme

**Responsável:** Guilherme
**Fonte:** [Inventário](../../Invent%C3%A1rio.md)
**Estado:** Roteiros pendentes de execução.

---

## C24-CT01 — PDF de avaliações

**Responsável:** Guilherme
**Tipo:** Relatório
**Status:** Pendente

### Objetivo
Conferir os dados apresentados no relatório de avaliações.

### Pré-condições
Avaliações de teste identificadas e filtros do relatório conhecidos.

### Passos a executar
1. Selecionar PDF de avaliações e aplicar filtros.
2. Gerar o arquivo.
3. Comparar identificação, período e registros com a consulta de origem..

### Resultado esperado
O PDF deve representar corretamente identificação, período e registros selecionados.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C24-CT02 — PDF de clientes

**Responsável:** Guilherme
**Tipo:** Relatório
**Status:** Pendente

### Objetivo
Comparar o PDF de clientes com a listagem filtrada.

### Pré-condições
Clientes de teste identificados e filtros disponíveis.

### Passos a executar
1. Aplicar os mesmos filtros na listagem e no relatório.
2. Gerar o PDF.
3. Conferir campos, registros e ausência de itens fora do filtro..

### Resultado esperado
O PDF deve corresponder aos filtros e aos clientes da listagem.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C24-CT03 — PDF de colaboradores

**Responsável:** Guilherme
**Tipo:** Relatório
**Status:** Pendente

### Objetivo
Conferir a seleção de colaboradores no PDF.

### Pré-condições
Colaboradores de teste ou amostra autorizada disponíveis; filtros identificados.

### Passos a executar
1. Selecionar PDF de colaboradores e aplicar a seleção.
2. Gerar o arquivo.
3. Comparar equipe e campos com a consulta correspondente..

### Resultado esperado
O PDF deve mostrar os colaboradores e campos da seleção aplicada.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C24-CT04 — PDF de matrículas

**Responsável:** Guilherme
**Tipo:** Relatório
**Status:** Pendente

### Objetivo
Conferir contratos, planos, datas e valores no relatório de matrículas.

### Pré-condições
Matrículas de teste identificadas e período escolhido.

### Passos a executar
1. Consultar as matrículas de referência.
2. Gerar o PDF com filtros correspondentes.
3. Comparar contrato, plano, datas e valores..

### Resultado esperado
Os dados das matrículas no PDF devem corresponder aos registros selecionados.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C24-CT05 — PDF de contas a receber

**Responsável:** Guilherme
**Tipo:** Relatório
**Status:** Pendente

### Objetivo
Conferir os dados financeiros no PDF de contas a receber.

### Pré-condições
Contas próprias com valores e situações conhecidos; filtros do relatório disponíveis.

### Passos a executar
1. Consultar as contas de referência.
2. Gerar o PDF no mesmo período.
3. Comparar status, pagamento, valores e totalizações existentes..

### Resultado esperado
O PDF deve refletir os dados das contas consultadas e suas totalizações existentes.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C24-CT06 — PDF de contas a pagar

**Responsável:** Guilherme
**Tipo:** Relatório
**Status:** Pendente

### Objetivo
Conferir contas e pagamentos no PDF de contas a pagar.

### Pré-condições
Contas próprias com valores e situações conhecidos.

### Passos a executar
1. Aplicar filtros e consultar as contas.
2. Gerar o PDF com a mesma seleção.
3. Comparar despesas, pagamentos e totalizações existentes..

### Resultado esperado
O PDF deve corresponder às contas filtradas e aos valores apresentados no sistema.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C24-CT07 — PDF de caixas normal e detalhado

**Responsável:** Guilherme
**Tipo:** Relatório
**Status:** Pendente

### Objetivo
Comparar os dois formatos de relatório de caixa.

### Pré-condições
Caixa próprio com movimentos conhecidos e ambos os formatos disponíveis.

### Passos a executar
1. Gerar o PDF normal.
2. Gerar o PDF detalhado para o mesmo caixa e período.
3. Comparar movimentos, valores e informações adicionais..

### Resultado esperado
Os formatos disponíveis devem manter valores coerentes e mostrar o detalhamento previsto.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C24-CT08 — Trocar tipo de relatório

**Responsável:** Guilherme
**Tipo:** Interação
**Status:** Pendente

### Objetivo
Conferir como os filtros reagem à mudança de relatório.

### Pré-condições
Tela de relatórios acessível; tipos e exigências visíveis.

### Passos a executar
1. Selecionar um tipo e observar filtros e botão de geração.
2. Trocar para outro tipo.
3. Preencher requisitos e conferir quando a geração fica habilitada..

### Resultado esperado
Filtros e disponibilidade da geração devem acompanhar o tipo selecionado.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C24-CT09 — Datas inválidas ou período vazio

**Responsável:** Guilherme
**Tipo:** Negativo
**Status:** Pendente

### Objetivo
Conferir mensagens para período inválido ou sem registros.

### Pré-condições
Tela de relatório acessível e intervalos de teste definidos.

### Passos a executar
1. Informar datas inválidas ou incoerentes, conforme os controles permitirem.
2. Tentar gerar e observar a validação.
3. Escolher período sem dados e conferir a apresentação..

### Resultado esperado
A tela deve tratar erro de data e ausência de dados de forma clara.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C24-CT10 — Limites de data e grandes listas

**Responsável:** Guilherme
**Tipo:** Limite
**Status:** Pendente

### Objetivo
Verificar fronteiras do período e cobertura de listas grandes.

### Pré-condições
Dados de teste nas datas de fronteira e conjunto suficiente para mais de uma página.

### Passos a executar
1. Gerar PDF com datas que incluam registros no início e no fim.
2. Conferir todas as páginas do arquivo.
3. Comparar quantidade e valores com a consulta..

### Resultado esperado
Registros das fronteiras devem ser incluídos e nenhuma página ou item deve faltar.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C24-CT11 — Layout do PDF

**Responsável:** Guilherme
**Tipo:** Interface
**Status:** Pendente

### Objetivo
Conferir a leitura e integridade visual dos relatórios gerados.

### Pré-condições
PDF de teste com texto acentuado e conteúdo suficiente para quebra de página.

### Passos a executar
1. Gerar um relatório com dados de teste.
2. Inspecionar acentos, cabeçalhos, margens e quebras.
3. Verificar se há texto ou valores cortados..

### Resultado esperado
O PDF deve manter acentos e conteúdo legíveis, sem cortes.

### Resultado obtido
Não executado.

### Evidência
Pendente.

---

## C24-CT12 — Conferência com sistema e banco

**Responsável:** Guilherme
**Tipo:** Consistência
**Status:** Pendente

### Objetivo
Comparar uma amostra controlada do PDF com as fontes disponíveis.

### Pré-condições
Amostra própria identificada; acesso autorizado ao banco e schema real confirmados antes de qualquer consulta.

### Passos a executar
1. Gerar o PDF para a amostra.
2. Comparar registros com o sistema.
3. Se houver acesso autorizado, consultar os mesmos registros no banco..

### Resultado esperado
Os dados devem ser consistentes entre fontes; não atribuir ao PDF total que não conste como requisito.

### Resultado obtido
Não executado.

### Evidência
Pendente.

# C09 — Matrículas

## C09-CT01 — Abrir cadastro e carregar seleções

Responsável: Fernando Cardoso dos Santos
Data da execução: 14/11/2026
Navegador: Google Chrome
Status: Aprovado parcialmente — verificar observação abaixo

### Objetivo

Verificar se o formulário de cadastro de matrícula abre e apresenta seus campos e seleções.

### Requisito relacionado

Acessar o cadastro de matrícula e carregar as opções necessárias ao preenchimento.

### Pré-condições

Estar autenticado no sistema e acessar a tela de Matrículas.

### Dados utilizados

Não houve cadastro de dados.

### Passos

1. Acessar Matrículas.
2. Abrir o cadastro de matrícula.
3. Observar os campos e as seleções disponíveis.

### Resultado esperado

O formulário deve abrir e carregar as opções necessárias ao cadastro.

### Resultado obtido

O formulário de cadastro abriu e apresentou campos como cliente, modalidade, moeda e tipo de pagamento.

Observação: a disponibilidade das opções dentro de todas as listas ainda precisa ser confirmada; a simples exibição dos campos não comprova que todas carregaram.

### Evidência

Vídeo: C09-CT01-abrir-cadastro-matricula.mp4

https://drive.google.com/drive/folders/1WXIX_bcYxrMoYSJwNByS7-DpseLBGiDL

### Bug associado

Nenhum confirmado com os trechos verificados.

---

## C09-CT02 — Selecionar cliente por código ou pesquisa

Responsável: Fernando Cardoso dos Santos
Data da execução: 14/11/2026
Navegador: Google Chrome
Status: Aprovado para a seleção observada

### Objetivo

Verificar se é possível selecionar o cliente correto para uma matrícula.

### Requisito relacionado

Permitir a seleção de um cliente existente no cadastro de matrícula.

### Pré-condições

Estar autenticado e ter um cliente de teste cadastrado.

### Dados utilizados

Cliente: QA_FERNANDO_CLIENTE_CONTATO_01
Código: 410

### Passos

1. Abrir o cadastro de matrícula.
2. Pesquisar o cliente de teste.
3. Selecionar o cliente encontrado.
4. Conferir o código e o nome no formulário.

### Resultado esperado

O código e o nome do cliente selecionado devem aparecer corretamente no formulário.

### Resultado obtido

O formulário apresentou o código 410 e o nome QA_FERNANDO_CLIENTE_CONTATO_01.

Observação: esta evidência confirma a seleção mostrada; outras formas de pesquisa devem ser registradas somente se forem verificadas.

### Evidência

Vídeo: C09-CT02-selecionar-cliente.mp4

https://drive.google.com/drive/folders/1WXIX_bcYxrMoYSJwNByS7-DpseLBGiDL

### Bug associado

Nenhum identificado na seleção observada.

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

## C09-CT07 — Valores inválidos na matrícula

Responsável: Fernando Cardoso dos Santos  
Data da execução: 16/11/2026  
Navegador: Google Chrome  
Tipo: Negativo  
Status: Bloqueado  
Sistema: https://sifitalfa.centrion.com.br/adicionar-matricula

### Objetivo

Verificar como o formulário de matrícula trata valores inválidos.

### Requisito relacionado

Validação dos valores informados no cadastro de matrícula. As regras específicas de valores e descontos precisam ser confirmadas.

### Pré-condições

- Estar autenticado no sistema.
- Acessar a tela de cadastro de matrícula.

### Dados utilizados

- Números negativos.
- Letras nos campos de valores.
- Desconto maior que o valor informado.

### Passos

1. Acessar a tela de cadastro de matrícula.
2. Tentar informar números negativos nos campos de valores.
3. Tentar informar letras nos campos de valores.
4. Informar um desconto maior que o valor.
5. Observar se o sistema apresenta mensagens.
6. Cancelar o cadastro sem salvar.

### Resultado esperado

O sistema deve validar os valores conforme as regras de negócio e impedir o cadastro de dados inválidos.

### Resultado obtido

Segundo o relato da execução, os valores testados puderam ser digitados e nenhuma mensagem de alerta apareceu durante o preenchimento. O cadastro foi cancelado sem clicar em Salvar.

### Justificativa do bloqueio

A validação no momento de salvar não foi verificada. As regras específicas dos campos e do desconto também precisam ser confirmadas antes de concluir o resultado.

### Evidência

[Assistir ao vídeo do C09-CT07](https://drive.google.com/file/d/1LKyKNtguoJfwn2XQgL7tOJwxCsMvwqFu/view?usp=sharing)

### Bug associado

Nenhum bug confirmado até a conclusão da validação.


## C09-CT08 — Dia de vencimento

Responsável: Fernando Cardoso dos Santos  
Data da execução: 16/11/2026  
Navegador: Google Chrome  
Tipo: Positivo e negativo  
Status: Bloqueado  
Sistema: https://sifitalfa.centrion.com.br/adicionar-matricula

### Objetivo

Verificar como o campo Dia Vencimento trata valores dentro e fora do intervalo de dias do mês.

### Requisito relacionado

Validação do dia de vencimento informado na matrícula. A regra específica para os dias permitidos precisa ser confirmada.

### Pré-condições

- Estar autenticado no sistema.
- Acessar a tela de cadastro de matrícula.

### Dados utilizados

Dias de vencimento: 1, 31, 0 e 32.

### Passos

1. Acessar a tela de cadastro de matrícula.
2. Informar o dia 1 no campo Dia Vencimento.
3. Repetir o preenchimento com os dias 31, 0 e 32.
4. Observar se o sistema apresenta mensagens.
5. Cancelar o cadastro sem salvar.

### Resultado esperado

O sistema deve validar o dia informado conforme a regra de negócio e impedir o cadastro de dias inválidos.

### Resultado obtido

Segundo o relato da execução, os dias 1, 31, 0 e 32 puderam ser digitados e nenhuma mensagem de alerta apareceu durante o preenchimento. O cadastro foi cancelado sem clicar em Salvar.

### Justificativa do bloqueio

A validação no momento de salvar não foi verificada. Também é necessário confirmar quais dias de vencimento são permitidos.

### Evidência

[Assistir ao vídeo do C09-CT08](https://drive.google.com/file/d/19cxc8ql-sf1bsqTSnHr47ECtZldRX2J8/view?usp=sharing)

### Bug associado

Nenhum bug confirmado até a conclusão da validação.

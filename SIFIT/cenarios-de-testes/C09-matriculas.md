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

## C09-CT03 — Cadastrar matrícula válida

Responsável: Fernando Cardoso dos Santos  
Data da execução: 14/11/2026  
Navegador: Google Chrome  
Tipo: Positivo  
Status: Aprovado  
Sistema: https://sifitalfa.centrion.com.br/adicionar-matricula

### Objetivo

Verificar se o sistema permite cadastrar uma matrícula e apresentá-la na listagem.

### Requisito relacionado

Cadastro de matrícula vinculada a cliente e modalidade, com datas e condições financeiras.

### Pré-condições

- Estar autenticado no sistema.
- Ter um cliente de teste cadastrado.
- Ter uma modalidade disponível.

### Dados utilizados

- Cliente: QA_FERNANDO_CLIENTE_CONTATO_01.
- Código do cliente: 410.
- Modalidade selecionada no salvamento: Teste Diária.
- Status: Ativo.
- Renovada: Não.
- Pagamento via sistema: Não.
- Tipo de pagamento: Pix.
- Taxa de matrícula informada: R$ 5,00.
- Valor da parcela exibido: R$ 20,00.
- Desconto exibido: R$ 0,00.
- Valor total exibido: R$ 20,00.

### Passos

1. Abrir o cadastro de matrícula.
2. Pesquisar e selecionar o cliente de teste.
3. Selecionar a modalidade Teste Diária.
4. Informar os dados de data e pagamento.
5. Conferir os valores exibidos.
6. Clicar em Salvar.
7. Observar a mensagem apresentada.
8. Conferir a matrícula na listagem.
9. Abrir a visualização da matrícula.

### Resultado esperado

O sistema deve salvar a matrícula com os dados informados e apresentá-la na listagem e na visualização.

### Resultado obtido

O sistema exibiu uma mensagem de pagamento após o salvamento. Em seguida, a matrícula apareceu na listagem com o código 243, o cliente selecionado, a modalidade Teste Diária e o status Ativo. O registro foi aberto pela visualização.

A gravação demonstra o cadastro e a visualização da matrícula. A geração ou o pagamento de conta a receber não foi confirmado neste caso.

### Verificações comuns

- G01 — Cadastro válido.
- G24 — Conferência entre listagem e visualização.

### Evidência

Vídeo: C09-CT03-cadastro-matricula-valida.mp4  
Pasta: https://drive.google.com/drive/folders/1WXIX_bcYxrMoYSJwNByS7-DpseLBGiDL

### Bug associado

Nenhum confirmado neste caso.


## C09-CT04 — Cliente ou modalidade ausente

Responsável: Fernando Cardoso dos Santos  
Data da execução: 14/11/2026  
Navegador: Google Chrome  
Tipo: Negativo  
Status: Aprovado  
Sistema: https://sifitalfa.centrion.com.br/adicionar-matricula

### Objetivo

Verificar se o sistema solicita o cliente e a modalidade antes de permitir o cadastro da matrícula.

### Requisito relacionado

Validação dos vínculos de cliente e modalidade na matrícula.

### Pré-condições

- Estar autenticado no sistema.
- Ter um cliente de teste disponível.

### Dados utilizados

Cliente de teste: QA_FERNANDO_CLIENTE_CONTATO_01, código 410.

### Passos

1. Abrir o cadastro de matrícula.
2. Tentar salvar sem selecionar cliente e modalidade.
3. Observar a mensagem.
4. Selecionar o cliente de teste.
5. Manter a modalidade sem seleção.
6. Tentar salvar novamente.
7. Observar a mensagem.

### Resultado esperado

O sistema deve impedir o cadastro e orientar a seleção do cliente e da modalidade quando estiverem ausentes.

### Resultado obtido

Na tentativa sem cliente, o sistema apresentou um aviso solicitando a seleção do cliente. Após a seleção do cliente, a tentativa sem modalidade apresentou a orientação “Selecione o Plano”.

### Verificação comum

- G02 — Obrigatórios vazios.

### Evidência

Vídeo: C09-CT04-campos-obrigatorios-matricula.mp4  
Pasta: https://drive.google.com/drive/folders/1WXIX_bcYxrMoYSJwNByS7-DpseLBGiDL

### Bug associado

Nenhum identificado nas validações observadas.


## C09-CT05 — Datas, status e renovada

Responsável: Fernando Cardoso dos Santos  
Data da execução: 16/11/2026  
Navegador: Google Chrome  
Tipo: Regra a confirmar  
Status: Não executado  
Sistema: https://sifitalfa.centrion.com.br/adicionar-matricula

### Objetivo

Verificar o comportamento dos campos de datas, status e renovação da matrícula.

### Requisito relacionado

Preenchimento e aplicação das datas, do status e da opção Renovada conforme as regras da matrícula.

### Pré-condições

- Estar autenticado no sistema.
- Ter cliente e plano de teste disponíveis.

### Dados utilizados

- Cliente: QA_FERNANDO_CLIENTE_CONTATO_01, código 410.
- Plano: QA_FERNANDO_EDITADO_01.
- Data inicial informada: 14/12/2026.
- Opção Renovada: alternada entre Sim e Não.

### Passos observados

1. Abrir o cadastro de matrícula.
2. Pesquisar e selecionar o cliente de teste.
3. Selecionar o plano QA_FERNANDO_EDITADO_01.
4. Alterar a data inicial.
5. Alternar a opção Renovada.
6. Observar os campos apresentados.

### Resultado esperado

O sistema deve tratar datas, status e renovação conforme as regras de negócio confirmadas.

### Resultado obtido

O vídeo mostra a seleção do cliente e do plano, a alteração da data inicial e a alternância da opção Renovada. A gravação não demonstra a validação completa dos status, da data final ou dos efeitos de uma renovação salva.

### Justificativa

O caso completo ainda não foi concluído. É necessário confirmar as regras e verificar as demais variações e seus resultados.

### Verificação comum

- G09 — Seleções dependentes, quando aplicável.

### Evidência

Vídeo: C09-CT05-datas-status-renovada.mp4  
Pasta: https://drive.google.com/drive/folders/1WXIX_bcYxrMoYSJwNByS7-DpseLBGiDL

### Bug associado

Nenhum confirmado neste caso.


## C09-CT06 — Taxa, parcela, desconto e total

Responsável: Fernando Cardoso dos Santos  
Data da execução: 16/11/2026  
Navegador: Google Chrome  
Tipo: Cálculo  
Status: Não executado  
Sistema: https://sifitalfa.centrion.com.br/adicionar-matricula

### Objetivo

Verificar o cálculo dos valores da matrícula a partir de taxa, parcela e desconto.

### Requisito relacionado

Cálculo e apresentação dos valores da matrícula conforme as regras financeiras confirmadas.

### Pré-condições

- Estar autenticado no sistema.
- Ter um cliente e um plano de teste disponíveis.
- Confirmar a regra de cálculo esperada.

### Dados utilizados

- Cliente: QA_FERNANDO_CLIENTE_ENDERECO_01, código 412.
- Taxa de matrícula informada: R$ 10,00.
- Desconto informado: R$ 5,00.

### Passos observados

1. Abrir o cadastro de matrícula.
2. Pesquisar e selecionar o cliente de teste.
3. Informar o valor da taxa de matrícula.
4. Informar um desconto.
5. Observar os demais campos financeiros.

### Resultado esperado

O sistema deve apresentar os valores e cálculos conforme a regra financeira confirmada.

### Resultado obtido

O vídeo mostra o preenchimento da taxa de R$ 10,00 e do desconto de R$ 5,00. Não foi demonstrado um cálculo completo com modalidade, parcela e total preenchidos que permita conferir a regra ou o arredondamento.

### Justificativa

O caso ainda não foi concluído. É necessário confirmar a regra de cálculo e repetir a conferência com valores suficientes para comparar o total esperado com o exibido.

### Verificação comum

- G24 — Conferência dos valores entre as telas, quando aplicável.

### Evidência

Vídeo: C09-CT06-valores-matricula.mp4  
Pasta: https://drive.google.com/drive/folders/1WXIX_bcYxrMoYSJwNByS7-DpseLBGiDL

### Bug associado

Nenhum confirmado neste caso.

## C09-CT09 — Meio de pagamento e Pag. Via Sistema

Responsável: Fernando Cardoso dos Santos  
Data da execução: 18/11/2026  
Navegador: Google Chrome  
Tipo: Condicional  
Status: Não executado  
Sistema: https://sifitalfa.centrion.com.br/adicionar-matricula

### Objetivo

Verificar o comportamento dos campos Pag. Via Sistema e Tipo Pagamento no cadastro de matrícula.

### Requisito relacionado

Disponibilização dos meios de pagamento e eventuais campos condicionais conforme a opção Pag. Via Sistema. A regra específica precisa ser confirmada.

### Pré-condições

- Estar autenticado no sistema.
- Acessar o cadastro de matrícula.

### Dados utilizados

- Pag. Via Sistema: Não e Sim.
- Tipos de pagamento testados: Pix, Boleto no Sistema e Crédito Recorrente.

### Passos executados

1. Abrir o cadastro de matrícula.
2. Observar o campo Pag. Via Sistema com a opção Não.
3. Selecionar um tipo de pagamento.
4. Alterar Pag. Via Sistema para Sim.
5. Testar as opções de pagamento.
6. Observar se aparecem novos campos ou mensagens.

### Resultado esperado

Os campos e tipos de pagamento devem se comportar conforme as regras de negócio e da integração.

### Resultado obtido

Ao alternar Pag. Via Sistema entre Não e Sim e testar tipos de pagamento, não foram observados campos adicionais ou mensagens.

A gravação mostra a seleção das opções, sem demonstrar o salvamento da matrícula ou a execução de um pagamento.

### Justificativa

A regra que determina quais campos ou opções devem aparecer ainda precisa ser confirmada. A integração e os efeitos após o salvamento não foram testados.

### Verificação comum

- G09 — Seleções dependentes.

### Evidência

[Assistir ao vídeo do C09-CT09](https://drive.google.com/file/d/1FMn1VZ_Yjy-457mupyOQiOBKvML8gazK/view?usp=drive_link)

### Bug associado

Nenhum confirmado até a verificação da regra.

# C41 — Perguntas de Anamnese

**Responsável:** Renan Oliveira  
**Sistema:** SIFIT — https://sifit.centrion.com.br  
**Requisito:** [RF41 — Perguntas de Anamnese](../contribuicoes/renan/requisitos.md#rf41--perguntas-de-anamnese)

Aqui eu testo o cadastro de perguntas de anamnese, que tem nome, enunciado, número, status e tipo de resposta. Começo as gravações já logado e uso dados fictícios com o prefixo `QA_RENAN`. As três primeiras perguntas que cadastro aqui vão para o modelo (C39) e para a ficha do aluno (C38), então não posso apagá-las. Se o formulário tiver campo de categoria, uso a `QA_RENAN_CAT_01 Saúde`, criada no C40.

O inventário registrou um “Erro no servidor” nesta tela. Se ele aparecer em qualquer caso, gravo a mensagem e trato no CT07.

---

## C41-CT01 — Cadastrar pergunta Sim/Não

**Requisito:** RF41  
**Tipo:** Positivo  
**Status:** Não executado  
**Ordem no planejamento:** 5

### Objetivo

Cadastrar uma pergunta de resposta Sim/Não e depois conferir se, na ficha do aluno, aparecem só essas duas opções.

### Pré-condições

Pesquisar `QA_RENAN_PERG_01` e confirmar que ela ainda não existe. Este caso só fecha depois do C38-CT05, quando vejo a pergunta na ficha aplicada.

### Dados utilizados

- Nome: `QA_RENAN_PERG_01`
- Enunciado: “Você pratica atividade física regularmente?”
- Número: 1
- Status: Ativo
- Tipo de resposta: Sim/Não

### Passos

1. Abrir Perguntas de Anamnese e clicar para criar uma nova.
2. Preencher os dados acima, deixando em branco o que for opcional.
3. Salvar, conferir a mensagem e anotar o código.
4. Atualizar a página, abrir a pergunta e comparar os dados.
5. No C38-CT05, ver na ficha aplicada se a pergunta mostra as opções Sim e Não.

### Resultado esperado

Apresentar as opções corretas na aplicação. A pergunta tem que ficar salva com os acentos do enunciado e, na ficha, mostrar só Sim e Não.

### Verificações comuns aplicadas

- G01 — Cadastro válido.
- G04 — Campos opcionais em branco.
- G07 — Acentos do enunciado preservados.
- G13 — Dados mantidos depois de atualizar a página.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Vídeo: `C41-CT01-pergunta-sim-nao.mp4` (link quando gravar)

### Bug associado

—

---

## C41-CT02 — Cadastrar Sim/Não/Não Sei

**Requisito:** RF41  
**Tipo:** Positivo  
**Status:** Não executado  
**Ordem no planejamento:** 6

### Objetivo

Cadastrar uma pergunta com as respostas Sim, Não e Não Sei e conferir se as três continuam disponíveis.

### Pré-condições

Pesquisar `QA_RENAN_PERG_02` e confirmar que ela ainda não existe. Este caso também só fecha depois do C38-CT05.

### Dados utilizados

- Nome: `QA_RENAN_PERG_02`
- Enunciado: “Tem alguma lesão ou dor nas articulações?”
- Número: 2
- Status: Ativo
- Tipo de resposta: Sim/Não/Não Sei

### Passos

1. Abrir o cadastro de nova pergunta e preencher os dados acima.
2. Salvar e anotar o código.
3. Atualizar a página, abrir a pergunta e conferir o tipo de resposta.
4. No C38-CT05, ver na ficha se aparecem as três respostas e se cada uma pode ser escolhida.

### Resultado esperado

Preservar cada resposta possível. A pergunta fica salva com o tipo certo e, na ficha, Sim, Não e Não Sei aparecem e funcionam.

### Verificações comuns aplicadas

- G01 — Cadastro válido.
- G13 — Dados mantidos depois de atualizar a página.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Vídeo: `C41-CT02-pergunta-sim-nao-nao-sei.mp4` (link quando gravar)

### Bug associado

—

---

## C41-CT03 — Cadastrar Se Sim, qual?

**Requisito:** RF41  
**Tipo:** Interação  
**Status:** Não executado  
**Ordem no planejamento:** 7

### Objetivo

Cadastrar uma pergunta do tipo “Se sim, qual?” e conferir se o campo de complemento aparece só quando a resposta é Sim.

### Pré-condições

Pesquisar `QA_RENAN_PERG_03` e confirmar que ela ainda não existe. Este caso também só fecha depois do C38-CT05.

### Dados utilizados

- Nome: `QA_RENAN_PERG_03`
- Enunciado: “Toma algum medicamento? Se sim, qual?”
- Número: 3
- Status: Ativo
- Tipo de resposta: Se Sim, qual?

### Passos

1. Abrir o cadastro de nova pergunta e preencher os dados acima.
2. Antes de salvar, trocar o tipo de resposta para outro e voltar, para ver se o formulário se ajusta sem guardar lixo da opção anterior.
3. Salvar e anotar o código.
4. Atualizar a página, abrir a pergunta e conferir o tipo de resposta.
5. No C38-CT05, responder Não e ver se o complemento fica escondido; depois responder Sim e ver se ele aparece.

### Resultado esperado

Exibir complemento na condição adequada. O complemento só aparece quando a resposta é Sim, e a pergunta continua com o tipo certo depois de salvar.

### Verificações comuns aplicadas

- G01 — Cadastro válido.
- G09 — Troca do tipo de resposta antes de salvar.
- G13 — Dados mantidos depois de atualizar a página.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Vídeo: `C41-CT03-pergunta-se-sim-qual.mp4` (link quando gravar)

### Bug associado

—

---

## C41-CT04 — Nome ou enunciado vazio

**Requisito:** RF41  
**Tipo:** Negativo  
**Status:** Não executado  
**Ordem no planejamento:** 8

### Objetivo

Ver se o sistema impede salvar uma pergunta sem nome ou sem enunciado.

### Pré-condições

Nenhuma além de estar logado.

### Dados utilizados

- 1ª tentativa: nome vazio, enunciado preenchido
- 2ª tentativa: enunciado vazio, nome preenchido
- 3ª tentativa: nome e enunciado só com espaços
- Para cancelar: `QA_RENAN_PERG_CANCELADA`
- Nas tentativas, número 9, status Ativo e tipo Sim/Não

### Passos

1. Abrir o cadastro de nova pergunta.
2. Deixar o nome vazio, preencher o resto e ir até Salvar usando Tab e Enter.
3. Preencher o nome, apagar o enunciado e tentar salvar.
4. Colocar só espaços nos dois campos e tentar salvar.
5. Abrir um cadastro novo, digitar `QA_RENAN_PERG_CANCELADA` e cancelar sem salvar.
6. Abrir o cadastro de novo e ver se ele volta limpo.
7. Pesquisar `QA_RENAN_PERG` e conferir que nenhuma pergunta inválida ou cancelada foi salva.

### Resultado esperado

Validar conteúdo necessário. Nenhuma das tentativas pode ser salva, o sistema precisa indicar o campo que falta e o cadastro cancelado não pode aparecer na lista nem voltar preenchido.

### Verificações comuns aplicadas

- G02 — Nome e enunciado obrigatórios vazios.
- G03 — Campos só com espaços.
- G10 — Cancelar sem salvar.
- G11 — Formulário limpo ao reabrir.
- G23 — Uso pelo teclado e mensagem indicando o campo.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Vídeo: `C41-CT04-nome-enunciado-vazio.mp4` (link quando gravar)

### Bug associado

—

---

## C41-CT05 — Número negativo, repetido ou fora da sequência

**Requisito:** RF41  
**Tipo:** Limite  
**Status:** Não executado  
**Ordem no planejamento:** 9

### Objetivo

Ver como o campo número se comporta com valores negativos, zero, decimal, repetido e fora da sequência.

### Pré-condições

As perguntas `QA_RENAN_PERG_01` a `_03`, com números 1, 2 e 3, já precisam estar cadastradas.

### Dados utilizados

- Nome das tentativas: `QA_RENAN_PERG_NUM_01`
- Enunciado: “Pergunta de teste do campo número”
- Números testados: -1, 0, 1,5, 2 (já usado pela `QA_RENAN_PERG_02`) e 99 (pula a sequência)

### Passos

1. Abrir o cadastro de nova pergunta e preencher nome, enunciado, status e tipo.
2. Tentar salvar com cada número da lista, um de cada vez, anotando a resposta do sistema.
3. Se algum valor inválido for salvo, anotar o código e corrigir pela edição, sem apagar nada.
4. Se o 99 for aceito, conferir na lista se a pergunta aparece depois das de número 1 a 3.

### Resultado esperado

Confirmar regra de ordem e unicidade. Como o professor não definiu regra, sigo a premissa da seção 8 do planejamento: o número é inteiro maior que zero e não se repete. Então -1, 0, 1,5 e o 2 repetido devem ser recusados com mensagem. O 99 pode ser aceito, desde que a ordem siga os números.

### Verificações comuns aplicadas

- G05 — Número em formato inválido (decimal).
- G06 — Limites: negativo, zero e valor alto.
- G08 — Número repetido.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Vídeo: `C41-CT05-numero-invalido-repetido.mp4` (link quando gravar)

### Bug associado

—

---

## C41-CT06 — Status inativo

**Requisito:** RF41  
**Tipo:** Integração  
**Status:** Não executado  
**Ordem no planejamento:** 28

### Objetivo

Inativar uma pergunta que já foi respondida e ver o que muda nos modelos e na ficha que já estava concluída.

### Pré-condições

Faço este caso só no fim da cadeia da anamnese. A `QA_RENAN_PERG_02` já precisa estar no modelo `QA_RENAN_MOD_01` e respondida numa ficha concluída do aluno de teste.

### Dados utilizados

- Pergunta: `QA_RENAN_PERG_02`
- Novo status: Inativo

### Passos

1. Abrir `QA_RENAN_PERG_02`, mudar o status para Inativo e salvar.
2. Atualizar a página e abrir de novo para ver se ficou Inativo.
3. Começar um modelo novo no montador e ver se a pergunta aparece para ser adicionada. Cancelar sem salvar.
4. Abrir a ficha concluída do aluno de teste e ver se a resposta da `QA_RENAN_PERG_02` continua lá.
5. Abrir o `QA_RENAN_MOD_01` e anotar o que aconteceu com a pergunta.

### Resultado esperado

Conferir disponibilidade nos modelos e preservar histórico. A pergunta inativa não pode aparecer para entrar em modelos novos, e a ficha concluída precisa continuar mostrando a resposta que foi dada. No `QA_RENAN_MOD_01`, que já tinha a pergunta, só registro o comportamento, porque não há regra para isso.

### Verificações comuns aplicadas

- G12 — Mudança de status salva.
- G20 — Ficha e modelo que usam a pergunta.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Vídeo: `C41-CT06-pergunta-inativa.mp4` (link quando gravar)

### Bug associado

—

---

## C41-CT07 — Pesquisa, edição e erro no servidor

**Requisito:** RF41  
**Tipo:** Investigação  
**Status:** Não executado  
**Ordem no planejamento:** 10

### Objetivo

Testar a pesquisa e a edição de perguntas e tentar reproduzir o “Erro no servidor” que o inventário registrou nesta tela.

### Pré-condições

As perguntas `QA_RENAN_PERG_01` a `_03` já precisam estar cadastradas.

### Dados utilizados

- Pesquisa completa: `QA_RENAN_PERG_01`
- Pesquisa parcial: `PERG_0`
- Pesquisa que não existe: `QA_RENAN_NAO_EXISTE`
- Edição do enunciado da `QA_RENAN_PERG_01`: “Você pratica alguma atividade física regularmente?”

### Passos

1. Abrir Perguntas de Anamnese e esperar a lista carregar.
2. Fazer as três pesquisas e ver o que aparece em cada uma.
3. Se a lista tiver mais de uma página, passar as páginas; se as colunas puderem ser ordenadas, clicar em cada uma.
4. Abrir a `QA_RENAN_PERG_01`, trocar o enunciado e salvar.
5. Atualizar a página e abrir de novo para conferir a edição.
6. Se aparecer “Erro no servidor” em qualquer momento, anotar a mensagem, o horário e a tela, recarregar e tentar mais uma vez.

### Resultado esperado

Conferir carregamento e reproduzir a mensagem observada. A lista e o formulário precisam carregar, as pesquisas devem trazer só o que corresponde (ou uma mensagem clara quando não acham nada) e a edição tem que ficar salva. Se o erro aparecer de novo na segunda tentativa, registro bug. O sistema também não pode mostrar sucesso sem ter salvo.

### Verificações comuns aplicadas

- G12 — Edição salva corretamente.
- G13 — Dados mantidos depois de atualizar a página.
- G15 — Pesquisa completa, parcial e sem resultado.
- G17 — Paginação, se houver.
- G18 — Ordenação das colunas, se houver.
- G21 — Erro no servidor.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Vídeo: `C41-CT07-pesquisa-edicao-erro-servidor.mp4` (link quando gravar)

### Bug associado

—

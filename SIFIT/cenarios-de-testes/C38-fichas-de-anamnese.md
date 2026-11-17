# C38 — Fichas de Anamnese

**Responsável:** Renan Oliveira  
**Sistema:** SIFIT — https://sifit.centrion.com.br  
**Requisito:** [RF38 — Fichas de Anamnese](../contribuicoes/renan/requisitos.md#rf38--fichas-de-anamnese)

Aqui eu aplico a anamnese no aluno de teste `QA_RENAN_CLIENTE_01`, que eu mesmo cadastro antes como preparação de dados, usando o modelo `QA_RENAN_MOD_01` do C39. Começo as gravações já logado. Todas as respostas são inventadas e nenhum dado de saúde real aparece nos vídeos. Do CT02 ao CT08 eu sigo uma mesma ficha, na ordem do planejamento, e no fim faço a busca da lista (CT01).

---

## C38-CT01 — Buscar aluno e filtrar status

**Requisito:** RF38  
**Tipo:** Filtro  
**Status:** Não executado  
**Ordem no planejamento:** 25

### Objetivo

Testar a busca por aluno e o filtro de status na lista de fichas.

### Pré-condições

O aluno de teste precisa ter pelo menos uma ficha Pendente e uma Concluída (as do CT06 e do CT07).

### Dados utilizados

- Busca completa: `QA_RENAN_CLIENTE_01`
- Busca parcial: `QA_RENAN`
- Busca que não existe: `QA_RENAN_NAO_EXISTE`
- Filtros: Pendente e Concluído

### Passos

1. Abrir Fichas de Anamnese e esperar a lista carregar.
2. Fazer as três buscas e ver o que aparece em cada uma.
3. Filtrar por Pendente e depois por Concluído, sozinho e junto com a busca do aluno.
4. Limpar busca e filtro e ver se a lista completa volta.
5. Se a lista tiver mais de uma página, passar as páginas; se as colunas puderem ser ordenadas, clicar em cada uma, inclusive a de data.

### Resultado esperado

Retornar fichas corretas e tratar consulta vazia. A busca e o filtro só podem trazer as fichas que combinam, a busca sem resultado precisa mostrar uma mensagem clara e a ordenação por data tem que seguir a data de verdade, não o texto.

### Verificações comuns aplicadas

- G15 — Busca completa, parcial e sem resultado.
- G16 — Filtro de status combinado e limpeza.
- G17 — Paginação, se houver.
- G18 — Ordenação das colunas, se houver.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Vídeo: `C38-CT01-buscar-filtrar-status.mp4` (link quando gravar)

### Bug associado

—

---

## C38-CT02 — Selecionar aluno para nova anamnese

**Requisito:** RF38  
**Tipo:** Positivo  
**Status:** Não executado  
**Ordem no planejamento:** 19

### Objetivo

Começar uma anamnese nova e ver se ela fica ligada só ao aluno que escolhi.

### Pré-condições

O cliente `QA_RENAN_CLIENTE_01` precisa estar cadastrado (preparação P2 do planejamento), com o código anotado.

### Dados utilizados

- Aluno: `QA_RENAN_CLIENTE_01`

### Passos

1. Abrir Fichas de Anamnese e clicar para criar uma nova.
2. Buscar o aluno pelo nome e selecionar.
3. Limpar a seleção e selecionar o aluno de novo, para ver se a tela se ajusta sem ficar com dado antigo.
4. Avançar e conferir o nome e o código do aluno na ficha.

### Resultado esperado

Vincular somente o aluno escolhido. A ficha tem que mostrar exatamente o `QA_RENAN_CLIENTE_01`, com o código certo.

### Verificações comuns aplicadas

- G09 — Troca da seleção do aluno.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Vídeo: `C38-CT02-selecionar-aluno.mp4` (link quando gravar)

### Bug associado

—

---

## C38-CT03 — Aluno ou modelo ausente

**Requisito:** RF38  
**Tipo:** Negativo  
**Status:** Não executado  
**Ordem no planejamento:** 18

### Objetivo

Ver se o sistema impede avançar na anamnese sem escolher o aluno ou o modelo.

### Pré-condições

O aluno de teste e o `QA_RENAN_MOD_01` precisam existir.

### Dados utilizados

- 1ª tentativa: sem aluno
- 2ª tentativa: com o aluno, sem modelo

### Passos

1. Abrir Fichas de Anamnese e clicar para criar uma nova.
2. Sem escolher o aluno, tentar avançar usando Tab e Enter.
3. Escolher o aluno, deixar o modelo sem escolher e tentar avançar.
4. Cancelar a anamnese.
5. Pesquisar o aluno na lista e conferir que nenhuma ficha foi criada por essas tentativas.

### Resultado esperado

Impedir avanço sem pré-condições obrigatórias. O sistema não pode deixar avançar sem aluno ou sem modelo, precisa mostrar o que falta e não pode sobrar ficha criada depois de cancelar.

### Verificações comuns aplicadas

- G02 — Aluno e modelo obrigatórios.
- G10 — Cancelar sem criar ficha.
- G23 — Uso pelo teclado e mensagem indicando o que falta.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Vídeo: `C38-CT03-aluno-modelo-ausente.mp4` (link quando gravar)

### Bug associado

—

---

## C38-CT04 — Aplicar modelo de teste

**Requisito:** RF38  
**Tipo:** Dependência  
**Status:** Não executado  
**Ordem no planejamento:** 20

### Objetivo

Aplicar o `QA_RENAN_MOD_01` no aluno e ver se a ficha mostra as categorias e perguntas do modelo, na ordem configurada.

### Pré-condições

A anamnese do CT02 precisa estar aberta, com o aluno escolhido. O `QA_RENAN_MOD_01` precisa estar com as perguntas na ordem do C39-CT05.

### Dados utilizados

- Modelo: `QA_RENAN_MOD_01 Avaliação inicial`
- Ordem esperada: `QA_RENAN_PERG_03`, `_01` e `_02`

### Passos

1. Escolher o modelo `QA_RENAN_MOD_01`.
2. Conferir a categoria Saúde, se a ficha mostrar categorias, e as três perguntas.
3. Comparar a ordem das perguntas com a do modelo. Com isso eu fecho também o C39-CT05.

### Resultado esperado

Exibir categorias e perguntas configuradas. A ficha tem que mostrar as três perguntas do modelo, com os enunciados certos e na mesma ordem do montador.

### Verificações comuns aplicadas

- G24 — Ficha conferida com o modelo.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Vídeo: `C38-CT04-aplicar-anamnese.mp4` (link quando gravar)

### Bug associado

—

---

## C38-CT05 — Responder tipos de pergunta disponíveis

**Requisito:** RF38  
**Tipo:** Dependência  
**Status:** Não executado  
**Ordem no planejamento:** 21

### Objetivo

Responder os três tipos de pergunta da ficha e ver se as respostas e o complemento do “Se sim, qual?” funcionam e ficam guardados.

### Pré-condições

A ficha do CT04 precisa estar aberta, com o `QA_RENAN_MOD_01` aplicado. Com este caso eu fecho também o C41-CT01, CT02 e CT03.

### Dados utilizados

- `QA_RENAN_PERG_03` (Se sim, qual?): Sim, com o complemento “Suplemento fictício de teste” e, na linha de baixo, “uso diário”
- `QA_RENAN_PERG_01` (Sim/Não): Sim
- `QA_RENAN_PERG_02` (Sim/Não/Não Sei): Não Sei

### Passos

1. Na `QA_RENAN_PERG_03`, marcar Sim e ver se o campo de complemento aparece.
2. Digitar qualquer texto, trocar para Não e ver se o complemento some. Voltar para Sim e digitar o complemento final, com a quebra de linha.
3. Conferir se a `QA_RENAN_PERG_01` mostra só Sim e Não, e marcar Sim.
4. Conferir se a `QA_RENAN_PERG_02` mostra Sim, Não e Não Sei, e marcar Não Sei.
5. Rolar a ficha de cima a baixo (ou voltar uma etapa, se ela tiver etapas) e ver se todas as respostas continuam marcadas.

### Resultado esperado

Preservar respostas e complementos condicionais. Cada pergunta mostra só as opções do seu tipo, o complemento aparece apenas quando a resposta é Sim, e as respostas e o texto do complemento, com acento e quebra de linha, continuam do jeito que preenchi.

### Verificações comuns aplicadas

- G07 — Acentos e quebra de linha no complemento.
- G09 — Complemento aparecendo e sumindo conforme a resposta.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Vídeo: `C38-CT05-responder-perguntas.mp4` (link quando gravar)

### Bug associado

—

---

## C38-CT06 — Finalizar com resposta obrigatória ausente

**Requisito:** RF38  
**Tipo:** Negativo  
**Status:** Não executado  
**Ordem no planejamento:** 22

### Objetivo

Tentar concluir a ficha faltando resposta e ver se o sistema mostra quais perguntas faltam.

### Pré-condições

A ficha do CT05 precisa estar aberta. Se a tela não deixar desmarcar uma resposta, abro uma segunda anamnese do mesmo aluno com o `QA_RENAN_MOD_01` e faço o teste nela. Se o sistema deixar, essa segunda ficha fica salva sem concluir, para servir de Pendente no CT01.

### Dados utilizados

- `QA_RENAN_PERG_01` (obrigatória no modelo): sem resposta
- `QA_RENAN_PERG_02` (não obrigatória): sem resposta
- `QA_RENAN_PERG_03` (obrigatória): Sim, com o complemento só com espaços

### Passos

1. Desmarcar as respostas da `QA_RENAN_PERG_01` e da `QA_RENAN_PERG_02` (ou deixar sem resposta, na segunda ficha).
2. Na `QA_RENAN_PERG_03`, marcar Sim e apagar o complemento, deixando só espaços.
3. Ir até o botão de concluir usando Tab e apertar Enter.
4. Anotar a mensagem e ver se ela aponta só o que é obrigatório e está faltando.
5. Voltar as respostas para as do CT05 antes de seguir.

### Resultado esperado

Orientar quais perguntas faltam. No modelo, marquei a `QA_RENAN_PERG_01` e a `QA_RENAN_PERG_03` como obrigatórias e a `QA_RENAN_PERG_02` não. O sistema não pode concluir a ficha com pergunta obrigatória em branco e precisa mostrar quais faltam; a não obrigatória pode ficar vazia. Para o complemento só com espaços, sigo a premissa da seção 8 do planejamento: com resposta Sim, ele é obrigatório.

### Verificações comuns aplicadas

- G02 — Resposta obrigatória vazia.
- G03 — Complemento só com espaços.
- G23 — Uso pelo teclado e mensagem indicando as perguntas.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Vídeo: `C38-CT06-obrigatoria-ausente.mp4` (link quando gravar)

### Bug associado

—

---

## C38-CT07 — Salvar rascunho e concluir, se disponível

**Requisito:** RF38  
**Tipo:** Dependência  
**Status:** Não executado  
**Ordem no planejamento:** 23

### Objetivo

Salvar a ficha como rascunho, conferir se ela fica Pendente com as respostas guardadas e depois concluir, vendo o status mudar para Concluído.

### Pré-condições

A ficha precisa estar com as respostas do CT05. Se não existir opção de rascunho, registro isso com print e testo só a conclusão.

### Dados utilizados

As respostas do CT05.

### Passos

1. Salvar como rascunho e conferir na lista se a ficha aparece como Pendente.
2. Atualizar a página, abrir a ficha e conferir se todas as respostas e o complemento continuam lá.
3. Clicar duas vezes seguidas em concluir.
4. Conferir na lista se a ficha ficou Concluída e se não apareceu ficha repetida.
5. Atualizar a página e conferir o status de novo.

### Resultado esperado

Conferir transição Pendente/Concluído e persistência. O rascunho fica Pendente com as respostas guardadas, a conclusão muda o status para Concluído, e o clique duplo não cria ficha repetida.

### Verificações comuns aplicadas

- G13 — Respostas e status mantidos depois de atualizar a página.
- G14 — Clique duplo em concluir sem duplicar a ficha.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Vídeo: `C38-CT07-rascunho-concluir.mp4` (link quando gravar)

### Bug associado

—

---

## C38-CT08 — Consultar ficha concluída

**Requisito:** RF38  
**Tipo:** Positivo  
**Status:** Não executado  
**Ordem no planejamento:** 24

### Objetivo

Abrir a ficha concluída e conferir se ela mostra o aluno, o modelo, a data e as respostas certas.

### Pré-condições

A ficha concluída no CT07 precisa existir.

### Dados utilizados

A ficha concluída do `QA_RENAN_CLIENTE_01`, com as respostas do CT05.

### Passos

1. Na lista, localizar a ficha concluída do aluno e anotar o que a lista mostra (aluno, modelo, data e status).
2. Abrir a ficha.
3. Conferir aluno, modelo, data e cada resposta, inclusive o complemento com a quebra de linha.
4. Comparar o que a lista mostra com o que aparece dentro da ficha.

### Resultado esperado

Conferir aluno, modelo, data e respostas sem expor dados de saúde reais nas evidências. A ficha tem que mostrar exatamente o que foi respondido, com a data do dia da aplicação, e a lista e a ficha precisam bater. Só aparecem dados inventados no vídeo.

### Verificações comuns aplicadas

- G24 — Lista conferida com a ficha.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Vídeo: `C38-CT08-consultar-ficha-concluida.mp4` (link quando gravar)

### Bug associado

—

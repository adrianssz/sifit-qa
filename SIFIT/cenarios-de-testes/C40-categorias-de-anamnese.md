# C40 — Categorias de Anamnese

**Responsável:** Renan Oliveira  
**Sistema:** SIFIT — https://sifit.centrion.com.br  
**Requisito:** [RF40 — Categorias de Anamnese](../contribuicoes/renan/requisitos.md#rf40--categorias-de-anamnese)

Aqui eu testo o cadastro de categorias de anamnese, que tem nome, status, ícone e cor. Em todos os casos começo já logado no sistema e uso dados fictícios com o prefixo `QA_RENAN` (lista completa na [massa de dados](../contribuicoes/renan/planejamento.md#4-massa-de-dados)). Sempre anoto o código da categoria criada, para conseguir achar depois.

Os nomes exatos dos botões e o caminho no menu eu ajusto depois de olhar a tela com calma no reconhecimento.

---

## C40-CT01 — Cadastrar categoria válida

**Requisito:** RF40  
**Tipo:** Positivo  
**Status:** Não executado  
**Ordem no planejamento:** 1

### Objetivo

Ver se consigo cadastrar uma categoria com todos os campos preenchidos e se ela continua igual depois de atualizar a página.

### Pré-condições

Antes de começar, pesquisar `QA_RENAN_CAT_01` para ter certeza de que ela ainda não existe.

### Dados utilizados

- Nome: `QA_RENAN_CAT_01 Saúde` (com acento de propósito)
- Status: Ativo
- Ícone: qualquer um disponível
- Cor: `#2E86C1`

### Passos

1. Abrir Categorias de Anamnese e clicar para criar uma nova.
2. Preencher nome, status, ícone e cor. Se tiver algum campo opcional, deixar em branco.
3. Clicar duas vezes seguidas em Salvar, para ver se o sistema não cria a categoria repetida.
4. Conferir a mensagem e a lista e anotar o código.
5. Atualizar a página, pesquisar a categoria e abrir de novo para comparar os dados.

### Resultado esperado

Salvar nome, status, ícone e cor. A categoria tem que aparecer uma vez só na lista, com o acento de “Saúde” certinho e os mesmos dados depois de atualizar a página.

### Verificações comuns aplicadas

- G01 — Cadastro válido.
- G04 — Campos opcionais em branco.
- G07 — Acento preservado.
- G13 — Dados mantidos depois de atualizar a página.
- G14 — Clique duplo em Salvar sem duplicar o registro.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Prints: em `SIFIT/evidencias/renan/`, com o nome começando por `C40-CT01`  
Vídeo (opcional, no fim): `C40-CT01-cadastrar-categoria.mp4`

### Bug associado

—

---

## C40-CT02 — Nome vazio ou repetido

**Requisito:** RF40  
**Tipo:** Negativo  
**Status:** Não executado  
**Ordem no planejamento:** 4

### Objetivo

Ver se o sistema obriga a preencher o nome da categoria e se ele impede um nome que já existe.

### Pré-condições

A categoria `QA_RENAN_CAT_01 Saúde` do CT01 já precisa estar cadastrada.

### Dados utilizados

- 1ª tentativa: nome vazio
- 2ª tentativa: nome só com espaços
- 3ª tentativa: `QA_RENAN_CAT_01 Saúde`, que já existe
- Para cancelar: `QA_RENAN_CAT_CANCELADA`
- Nas tentativas, status, ícone e cor preenchidos normalmente

### Passos

1. Abrir o cadastro de nova categoria.
2. Deixar o nome vazio e preencher o resto. Ir até o botão Salvar usando a tecla Tab e apertar Enter, para ver se dá para usar só o teclado.
3. Tentar salvar com o nome só com espaços.
4. Tentar salvar com o nome `QA_RENAN_CAT_01 Saúde`.
5. Abrir um cadastro novo, digitar `QA_RENAN_CAT_CANCELADA` e cancelar sem salvar.
6. Abrir o cadastro de novo e ver se o formulário volta limpo.
7. Pesquisar `QA_RENAN_CAT` e conferir que só existem as categorias que eu salvei de propósito.

### Resultado esperado

Conferir obrigatoriedade e unicidade. O nome vazio ou só com espaços não pode ser salvo e o sistema precisa mostrar qual campo está errado. O nome repetido também deve ser barrado: como o professor não definiu regra, sigo a premissa da seção 8 do planejamento de que duas categorias com o mesmo nome ficariam iguais na hora de escolher. O cadastro cancelado não pode aparecer na lista nem voltar preenchido.

### Verificações comuns aplicadas

- G02 — Nome obrigatório vazio.
- G03 — Nome só com espaços.
- G08 — Nome repetido.
- G10 — Cancelar sem salvar.
- G11 — Formulário limpo ao reabrir.
- G23 — Uso pelo teclado e mensagem indicando o campo.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Prints: em `SIFIT/evidencias/renan/`, com o nome começando por `C40-CT02`  
Vídeo (opcional, no fim): `C40-CT02-nome-vazio-repetido.mp4`

### Bug associado

—

---

## C40-CT03 — Cor pelo seletor e código

**Requisito:** RF40  
**Tipo:** Interação  
**Status:** Não executado  
**Ordem no planejamento:** 2

### Objetivo

Ver se a cor escolhida no seletor e o código da cor andam juntos e se o sistema recusa um código inválido.

### Pré-condições

Pesquisar `QA_RENAN_CAT_02` e confirmar que ela ainda não existe.

### Dados utilizados

- Nome: `QA_RENAN_CAT_02`
- Status: Ativo
- Ícone: qualquer um disponível
- Código válido: `#1E8449`
- Códigos inválidos: `#GGGGGG`, `#12345` e `azul`

### Passos

1. Abrir o cadastro de nova categoria e preencher nome, status e ícone.
2. Escolher uma cor no seletor e ver se o código muda junto.
3. Digitar `#1E8449` no código e ver se o seletor mostra a mesma cor.
4. Digitar cada código inválido e tentar salvar, anotando o que o sistema responde.
5. Voltar para `#1E8449` e salvar. Se algum código inválido tiver sido salvo, anotar e corrigir pela edição.
6. Atualizar a página, abrir a categoria e conferir a cor na lista e no formulário.

### Resultado esperado

Sincronizar ambos e rejeitar código inválido. O seletor e o código precisam mostrar sempre a mesma cor, nenhum código inválido pode ser salvo e a categoria tem que ficar com `#1E8449`.

### Verificações comuns aplicadas

- G05 — Código de cor em formato inválido.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Prints: em `SIFIT/evidencias/renan/`, com o nome começando por `C40-CT03`  
Vídeo (opcional, no fim): `C40-CT03-cor-seletor-codigo.mp4`

### Bug associado

—

---

## C40-CT04 — Ícone válido e inválido

**Requisito:** RF40  
**Tipo:** Negativo  
**Status:** Não executado  
**Ordem no planejamento:** 3

### Objetivo

Ver se o ícone escolhido aparece certo e o que acontece quando tento usar um ícone inválido.

### Pré-condições

A categoria `QA_RENAN_CAT_02` do CT03 já precisa estar cadastrada.

### Dados utilizados

Depende de como o campo funciona:

- Se for uma lista: escolher um ícone diferente do atual.
- Se for texto: um nome de ícone válido e o nome inventado `icone_inexistente_qa`.
- Se for upload: uma imagem PNG pequena, um arquivo `.txt` e uma imagem grande, de uns 10 MB.

### Passos

1. Abrir `QA_RENAN_CAT_02` para editar.
2. Tirar um print mostrando como o ícone é escolhido.
3. Escolher um ícone válido, salvar e conferir na lista e no formulário.
4. Tentar salvar com o ícone inválido, conforme o tipo do campo, e anotar a resposta.
5. Se for upload, trocar a imagem, testar a imagem grande e cancelar a janela de escolher arquivo.
6. Atualizar a página e conferir o ícone que ficou salvo.

### Resultado esperado

Exibir ícone ou tratamento compreensível. O ícone válido tem que aparecer na lista e no formulário. O inválido deve ser recusado com uma mensagem que dê para entender, sem quebrar a tela nem mostrar caminho interno do servidor. Se o ícone só puder ser escolhido numa lista, não tem como usar um inválido: registro isso com print e avalio só a exibição.

### Verificações comuns aplicadas

- G05 — Ícone em formato inválido.
- G22 — Upload de arquivo, só se o ícone for enviado como arquivo. Se não for, fica Não se aplica, com print.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Prints: em `SIFIT/evidencias/renan/`, com o nome começando por `C40-CT04`  
Vídeo (opcional, no fim): `C40-CT04-icone-valido-invalido.mp4`

### Bug associado

—

---

## C40-CT05 — Filtro, edição e inativação

**Requisito:** RF40  
**Tipo:** Integração  
**Status:** Não executado  
**Ordem no planejamento:** 29

### Objetivo

Testar a pesquisa e os filtros da lista, editar uma categoria e ver se, depois de inativada, ela some das telas de perguntas e modelos.

### Pré-condições

As categorias `QA_RENAN_CAT_01 Saúde` e `QA_RENAN_CAT_02` precisam estar cadastradas. Faço este caso só depois da cadeia da anamnese (ordens 5 a 28), para não atrapalhar os testes anteriores.

### Dados utilizados

- Pesquisa que existe: `QA_RENAN_CAT`
- Pesquisa que não existe: `QA_RENAN_NAO_EXISTE`
- Edição de `QA_RENAN_CAT_02`: nome `QA_RENAN_CAT_02 Editada` e cor `#AF601A`

### Passos

1. Pesquisar `QA_RENAN_CAT` e ver se aparecem as minhas categorias de teste.
2. Pesquisar `QA_RENAN_NAO_EXISTE` e ver o que a lista mostra.
3. Usar cada filtro da lista, sozinho e junto com a pesquisa, e depois limpar.
4. Abrir `QA_RENAN_CAT_02`, mudar nome e cor, salvar e abrir de novo.
5. Mudar o status para Inativo, salvar e conferir na lista.
6. Ir no cadastro de pergunta e no montador de modelos e ver se a categoria inativa ainda aparece para escolher ou filtrar.
7. Conferir se `QA_RENAN_CAT_01 Saúde` e as perguntas dela continuam normais.

### Resultado esperado

Conferir disponibilidade para perguntas/modelos. A pesquisa e os filtros só podem trazer as categorias certas, e a pesquisa sem resultado precisa mostrar uma mensagem clara. A edição tem que ficar salva. Depois de inativa, a categoria não deve aparecer para novas perguntas e modelos, e as outras categorias e perguntas não podem ser afetadas.

### Verificações comuns aplicadas

- G12 — Edição salva corretamente.
- G15 — Pesquisa com e sem resultado.
- G16 — Filtros combinados e limpeza.
- G20 — Inativação sem quebrar os vínculos.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Prints: em `SIFIT/evidencias/renan/`, com o nome começando por `C40-CT05`  
Vídeo (opcional, no fim): `C40-CT05-filtro-edicao-inativacao.mp4`

### Bug associado

—

---

## C40-CT06 — Exclusão com perguntas vinculadas

**Requisito:** RF40  
**Tipo:** Condicional  
**Status:** Não executado  
**Ordem no planejamento:** 30

### Objetivo

Ver o que acontece quando tento excluir uma categoria que já tem pergunta ligada a ela.

### Pré-condições

- Criar antes, só para este teste, a categoria `QA_RENAN_CAT_DESC_01` e a pergunta `QA_RENAN_PERG_DESC_01` ligada a ela.
- A lista de categorias precisa ter a opção de excluir. Se não tiver, o caso fica Não se aplica, com print.
- Não excluir nenhum outro registro.

### Dados utilizados

- Categoria descartável: `QA_RENAN_CAT_DESC_01`
- Pergunta descartável: `QA_RENAN_PERG_DESC_01`

### Passos

1. Em Perguntas de Anamnese, mostrar que `QA_RENAN_PERG_DESC_01` está ligada a `QA_RENAN_CAT_DESC_01`.
2. Em Categorias de Anamnese, clicar para excluir `QA_RENAN_CAT_DESC_01` e cancelar na confirmação.
3. Ver se a categoria continua na lista.
4. Clicar para excluir de novo e, desta vez, confirmar.
5. Anotar o que aconteceu: se o sistema impediu, se excluiu ou outra resposta.
6. Atualizar a página e conferir a lista de categorias.
7. Abrir `QA_RENAN_PERG_DESC_01` e ver se ela abre sem erro e qual categoria aparece nela.

### Resultado esperado

Evitar referências quebradas e perda indevida de estrutura. Cancelar tem que manter a categoria. Ao confirmar, o sistema deve impedir a exclusão com uma mensagem clara ou resolver o vínculo sem deixar a pergunta ligada a uma categoria que não existe mais, e sem apagar a pergunta junto sem avisar. No banco, a tabela de perguntas não tem campo de categoria. Se na tela também não houver jeito de ligar a categoria a uma pergunta ou a um modelo, o caso fica Não se aplica, com print.

### Verificações comuns aplicadas

- G19 — Cancelar e confirmar a exclusão.
- G20 — Pergunta vinculada sem referência quebrada.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Prints: em `SIFIT/evidencias/renan/`, com o nome começando por `C40-CT06`  
Vídeo (opcional, no fim): `C40-CT06-excluir-categoria-vinculada.mp4`

### Bug associado

—

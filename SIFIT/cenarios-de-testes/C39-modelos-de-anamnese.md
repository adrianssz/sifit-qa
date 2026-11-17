# C39 — Modelos de Anamnese

**Responsável:** Renan Oliveira  
**Sistema:** SIFIT Alfa — https://sifitalfa.centrion.com.br  
**Requisito:** [RF39 — Modelos de Anamnese](../contribuicoes/renan/requisitos.md#rf39--modelos-de-anamnese)

Aqui eu testo a criação de modelos de anamnese no montador visual, onde escolho as perguntas cadastradas no C41. Começo as gravações já logado e uso dados fictícios com o prefixo `QA_RENAN`. O modelo `QA_RENAN_MOD_01` é o que vou aplicar no aluno de teste no C38, então não posso apagá-lo.

O inventário registrou um erro de servidor nesta tela. Por isso o primeiro caso que gravo é o CT08, que confere se o montador carrega.

---

## C39-CT01 — Criar modelo válido

**Requisito:** RF39  
**Tipo:** Positivo  
**Status:** Não executado  
**Ordem no planejamento:** 14

### Objetivo

Criar um modelo com nome, status, descrição e as três perguntas de teste e ver se tudo continua igual depois de atualizar a página.

### Pré-condições

As perguntas `QA_RENAN_PERG_01` a `_03` precisam estar cadastradas e ativas. Pesquisar `QA_RENAN_MOD_01` e confirmar que ele ainda não existe.

### Dados utilizados

- Nome: `QA_RENAN_MOD_01 Avaliação inicial`
- Status: Ativo
- Descrição: “Modelo de teste com três perguntas de saúde.”
- Perguntas: `QA_RENAN_PERG_01`, `_02` e `_03`, nessa ordem

### Passos

1. Abrir Modelos de Anamnese e clicar para criar um novo.
2. Preencher nome, status e descrição. Se tiver algum campo opcional além desses, deixar em branco.
3. No montador, adicionar as três perguntas na ordem da lista.
4. Salvar, conferir a mensagem e anotar o código.
5. Atualizar a página, abrir o modelo e conferir os dados e as perguntas.

### Resultado esperado

Salvar nome, status, descrição e perguntas selecionadas. O modelo tem que aparecer na lista com os acentos certos e, ao abrir, mostrar as três perguntas na ordem em que adicionei.

### Verificações comuns aplicadas

- G01 — Cadastro válido.
- G04 — Campos opcionais em branco.
- G07 — Acentos do nome e da descrição.
- G13 — Dados mantidos depois de atualizar a página.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Vídeo: `C39-CT01-criar-modelo.mp4` (link quando gravar)

### Bug associado

—

---

## C39-CT02 — Nome vazio ou modelo sem perguntas

**Requisito:** RF39  
**Tipo:** Negativo  
**Status:** Não executado  
**Ordem no planejamento:** 16

### Objetivo

Ver se o sistema impede salvar um modelo sem nome ou sem nenhuma pergunta.

### Pré-condições

As perguntas de teste do C41 precisam estar cadastradas.

### Dados utilizados

- 1ª tentativa: nome vazio, com uma pergunta adicionada
- 2ª tentativa: nome só com espaços, com uma pergunta adicionada
- 3ª tentativa: nome `QA_RENAN_MOD_VAZIO_01`, sem nenhuma pergunta

### Passos

1. Abrir o cadastro de novo modelo.
2. Adicionar uma pergunta, deixar o nome vazio e ir até Salvar usando Tab e Enter.
3. Colocar só espaços no nome e tentar salvar.
4. Preencher o nome `QA_RENAN_MOD_VAZIO_01`, remover a pergunta e tentar salvar.
5. Fechar sem salvar, abrir o cadastro de novo e ver se ele volta limpo.
6. Pesquisar `QA_RENAN_MOD` e conferir que nenhum modelo inválido foi salvo.

### Resultado esperado

Confirmar regras e impedir estrutura inválida. Como o professor não definiu regra, sigo a premissa da seção 8 do planejamento: o modelo precisa de nome e de pelo menos uma pergunta. Nenhuma das três tentativas pode ser salva, e o sistema precisa mostrar o que falta.

### Verificações comuns aplicadas

- G02 — Nome obrigatório vazio.
- G03 — Nome só com espaços.
- G11 — Formulário limpo ao reabrir.
- G23 — Uso pelo teclado e mensagem indicando o que falta.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Vídeo: `C39-CT02-nome-vazio-sem-perguntas.mp4` (link quando gravar)

### Bug associado

—

---

## C39-CT03 — Buscar pergunta e filtrar categoria

**Requisito:** RF39  
**Tipo:** Filtro  
**Status:** Não executado  
**Ordem no planejamento:** 12

### Objetivo

Testar a busca de perguntas e o filtro por categoria dentro do montador.

### Pré-condições

As perguntas `QA_RENAN_PERG_01` a `_03` e as categorias `QA_RENAN_CAT_01 Saúde` e `QA_RENAN_CAT_02` precisam existir.

### Dados utilizados

- Busca completa: `QA_RENAN_PERG_02`
- Busca parcial: `PERG_0`
- Busca que não existe: `QA_RENAN_NAO_EXISTE`
- Filtros: categoria `QA_RENAN_CAT_01 Saúde` e categoria `QA_RENAN_CAT_02`, que não tem perguntas

### Passos

1. Abrir o cadastro de novo modelo e esperar o montador carregar.
2. Fazer as três buscas e ver o que aparece em cada uma.
3. Filtrar pela categoria Saúde e depois pela `QA_RENAN_CAT_02`.
4. Combinar a busca `PERG_0` com o filtro de categoria.
5. Limpar busca e filtro e ver se a lista completa volta.
6. Fechar sem salvar.

### Resultado esperado

Retornar opções coerentes. A busca e o filtro só podem mostrar as perguntas que combinam com o que escolhi, a categoria sem perguntas precisa mostrar uma mensagem clara de lista vazia, e ao limpar tudo a lista completa tem que voltar.

### Verificações comuns aplicadas

- G09 — Troca de categoria atualizando as opções.
- G15 — Busca completa, parcial e sem resultado.
- G16 — Busca e filtro combinados e limpeza.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Vídeo: `C39-CT03-buscar-pergunta-filtrar-categoria.mp4` (link quando gravar)

### Bug associado

—

---

## C39-CT04 — Adicionar e remover pergunta

**Requisito:** RF39  
**Tipo:** Interação  
**Status:** Não executado  
**Ordem no planejamento:** 13

### Objetivo

Ver se o montador e o resumo do modelo se atualizam quando adiciono e removo perguntas, e se nada fica salvo quando cancelo.

### Pré-condições

As perguntas de teste do C41 precisam estar cadastradas.

### Dados utilizados

- Perguntas: `QA_RENAN_PERG_01` e `QA_RENAN_PERG_02`
- Nome provisório: `QA_RENAN_MOD_CANCELADO`

### Passos

1. Abrir o cadastro de novo modelo e digitar o nome provisório.
2. Adicionar as duas perguntas e conferir o montador e o resumo (quantidade e lista).
3. Remover a `QA_RENAN_PERG_02` e conferir se o montador e o resumo mudam junto.
4. Cancelar sem salvar.
5. Pesquisar `QA_RENAN_MOD_CANCELADO` e conferir que ele não foi criado.

### Resultado esperado

Atualizar montador e resumo corretamente. Cada pergunta adicionada ou removida aparece na hora no montador e no resumo, e o modelo cancelado não é salvo.

### Verificações comuns aplicadas

- G10 — Cancelar sem salvar.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Vídeo: `C39-CT04-adicionar-remover-pergunta.mp4` (link quando gravar)

### Bug associado

—

---

## C39-CT05 — Reordenar perguntas, se disponível

**Requisito:** RF39  
**Tipo:** Dependência  
**Status:** Não executado  
**Ordem no planejamento:** 15

### Objetivo

Mudar a ordem das perguntas do modelo e ver se a nova ordem é mantida, inclusive na ficha aplicada ao aluno.

### Pré-condições

O `QA_RENAN_MOD_01` do CT01 precisa estar salvo. Se o montador não tiver como reordenar, o caso fica Não se aplica, com print. Este caso só fecha depois do C38-CT04, quando vejo a ordem na ficha.

### Dados utilizados

- Modelo: `QA_RENAN_MOD_01 Avaliação inicial`
- Ordem nova: `QA_RENAN_PERG_03`, `_01` e `_02`

### Passos

1. Abrir o `QA_RENAN_MOD_01` para editar.
2. Arrastar ou mover a `QA_RENAN_PERG_03` para o primeiro lugar.
3. Salvar, atualizar a página e abrir de novo para ver se a ordem ficou.
4. No C38-CT04, conferir se a ficha aplicada mostra as perguntas nessa mesma ordem.

### Resultado esperado

Preservar ordem no formulário aplicado. A ordem nova tem que continuar depois de atualizar a página e ser a mesma na ficha do aluno.

### Verificações comuns aplicadas

- G13 — Ordem mantida depois de atualizar a página.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Vídeo: `C39-CT05-reordenar-perguntas.mp4` (link quando gravar)

### Bug associado

—

---

## C39-CT06 — Pergunta duplicada ou inativa

**Requisito:** RF39  
**Tipo:** Negativo  
**Status:** Não executado  
**Ordem no planejamento:** 17

### Objetivo

Ver se o montador deixa colocar a mesma pergunta duas vezes e se uma pergunta inativa aparece para ser escolhida.

### Pré-condições

Antes de gravar, cadastrar no C41 a pergunta `QA_RENAN_PERG_INAT_01` já com status Inativo (isso é só preparação, não conta como caso).

### Dados utilizados

- Nome provisório: `QA_RENAN_MOD_DUP_01`
- Pergunta para duplicar: `QA_RENAN_PERG_01`
- Pergunta inativa: `QA_RENAN_PERG_INAT_01`

### Passos

1. Abrir o cadastro de novo modelo e digitar o nome provisório.
2. Adicionar a `QA_RENAN_PERG_01` e tentar adicioná-la de novo.
3. Se o montador deixar, tentar salvar e anotar o que acontece. Se salvar, anotar o código, sem apagar nada.
4. Buscar `QA_RENAN_PERG_INAT_01` no montador e ver se ela aparece para escolher.
5. Fechar sem salvar, se ainda não tiver salvo.

### Resultado esperado

Aplicar regra de seleção e disponibilidade. Pela premissa da seção 8 do planejamento, a mesma pergunta não pode entrar duas vezes no modelo, e a pergunta inativa não pode aparecer para ser escolhida.

### Verificações comuns aplicadas

- G08 — Mesma pergunta duas vezes.
- G20 — Pergunta inativa fora da seleção.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Vídeo: `C39-CT06-pergunta-duplicada-inativa.mp4` (link quando gravar)

### Bug associado

—

---

## C39-CT07 — Editar modelo já aplicado

**Requisito:** RF39  
**Tipo:** Condicional  
**Status:** Não executado  
**Ordem no planejamento:** 27

### Objetivo

Editar um modelo que já foi usado numa ficha e ver se a ficha antiga continua do jeito que foi respondida.

### Pré-condições

O `QA_RENAN_MOD_01` já precisa ter sido aplicado e concluído numa ficha do aluno de teste (C38-CT07 e CT08).

### Dados utilizados

- Modelo: `QA_RENAN_MOD_01 Avaliação inicial`
- Nova descrição: “Modelo de teste revisado.”
- Pergunta removida: `QA_RENAN_PERG_03`

### Passos

1. Abrir o `QA_RENAN_MOD_01` para editar.
2. Trocar a descrição e remover a `QA_RENAN_PERG_03`.
3. Salvar e anotar a mensagem. Se o sistema não deixar editar um modelo já usado, anotar a mensagem e seguir para o passo 5.
4. Atualizar a página e abrir o modelo para conferir a alteração.
5. Abrir a ficha concluída do aluno e ver se a pergunta `QA_RENAN_PERG_03` e a resposta dada continuam lá.

### Resultado esperado

Conferir preservação do histórico das fichas existentes. Pela premissa da seção 8 do planejamento, editar o modelo não muda as fichas já aplicadas. O sistema pode impedir a edição com uma mensagem clara ou salvar a alteração, mas a ficha antiga precisa continuar com a pergunta e a resposta originais.

### Verificações comuns aplicadas

- G12 — Edição salva no modelo certo.
- G20 — Ficha antiga preservada.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Vídeo: `C39-CT07-editar-modelo-aplicado.mp4` (link quando gravar)

### Bug associado

—

---

## C39-CT08 — Erro no carregamento do montador

**Requisito:** RF39  
**Tipo:** Investigação  
**Status:** Não executado  
**Ordem no planejamento:** 11

### Objetivo

Tentar reproduzir o erro de servidor que o inventário viu no montador e conferir se, com perguntas cadastradas, ele carrega a lista de verdade.

### Pré-condições

As perguntas `QA_RENAN_PERG_01` a `_03` precisam estar cadastradas e ativas, para eu saber que a lista não deveria vir vazia.

### Dados utilizados

Nenhum dado novo; só abro o montador.

### Passos

1. Abrir Modelos de Anamnese e clicar para criar um novo.
2. Esperar o montador carregar e ver se as perguntas de teste aparecem.
3. Se aparecer “Erro no servidor” ou a lista vier vazia, anotar a mensagem, o horário e a tela.
4. Recarregar a página e tentar abrir o montador mais uma vez.
5. Fechar sem salvar.

### Resultado esperado

Reproduzir erro observado e distinguir falha de ausência de perguntas. Com perguntas ativas cadastradas, o montador precisa listar as perguntas. Se aparecer erro ou lista vazia nas duas tentativas, registro bug, porque o sistema não pode tratar uma falha como se não existissem perguntas. O Jam grava as requisições da página, o que ajuda a mostrar a falha.

### Verificações comuns aplicadas

- G21 — Erro no servidor.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Vídeo: `C39-CT08-erro-carregamento-montador.mp4` (link quando gravar)

### Bug associado

—

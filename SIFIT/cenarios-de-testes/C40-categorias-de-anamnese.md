# C40 — Categorias de Anamnese

**Responsável:** Renan Oliveira  
**Sistema:** SIFIT Alfa — https://sifitalfa.centrion.com.br  
**Requisito:** [RF40 — Categorias de Anamnese](../contribuicoes/renan/requisitos.md#rf40--categorias-de-anamnese)  
**Base do inventário:** Formulário inspecionado com nome, status, ícone e cor.  
**Situação:** roteiro preparado; os 6 casos estão Não executados.

Os dados são fictícios, com prefixo `QA_RENAN` ([massa de dados](../contribuicoes/renan/planejamento.md#4-massa-de-dados)). Anotar o código de cada categoria criada. Os passos usam os campos citados no inventário; caminho no menu, nomes de botões e tipo do campo de ícone serão ajustados depois do reconhecimento da tela (P9). A ordem de execução é a da seção 5 do planejamento.

Em "Resultado esperado", a linha "Inventário" reproduz o texto original do caso e a linha "Critério" detalha como julgar o resultado.

---

## C40-CT01 — Cadastrar categoria válida

**Requisito:** RF40  
**Tipo:** Positivo  
**Status:** Não executado  
**Ordem de execução:** 1

### Objetivo

Verificar se uma categoria com dados válidos é salva com nome, status, ícone e cor e continua igual depois de atualizar a página.

### Pré-condições

- Estar autenticado no SIFIT Alfa.
- Pesquisar `QA_RENAN_CAT_01` na listagem e confirmar que ainda não existe.

### Dados utilizados

- Nome: `QA_RENAN_CAT_01 Saúde`
- Status: Ativo
- Ícone: o primeiro da lista ou um nome de ícone válido, conforme o campo
- Cor: `#2E86C1`
- Campos opcionais, se houver: vazios

### Passos

1. Abrir Categorias de Anamnese.
2. Abrir o cadastro de nova categoria.
3. Preencher nome, status, ícone e cor com os dados acima, sem preencher campos opcionais.
4. Clicar duas vezes seguidas em Salvar.
5. Conferir a mensagem exibida e a listagem; anotar o código da categoria.
6. Atualizar a página e pesquisar `QA_RENAN_CAT_01`.
7. Abrir a categoria e comparar cada campo com os dados informados.

### Resultado esperado

- Inventário: Salvar nome, status, ícone e cor.
- Critério: a categoria aparece uma única vez na listagem, com os dados informados, também depois de atualizar a página.

### Verificações comuns aplicadas

- G01 — Cadastro válido: dados salvos exatamente como informados, com confirmação.
- G04 — Opcionais vazios: cadastro aceito sem os campos opcionais.
- G07 — Acentos: “Saúde” aparece igual na listagem e no formulário.
- G13 — Persistência: dados mantidos após atualizar a página.
- G14 — Clique duplo em Salvar: somente uma categoria criada.

### Resultado obtido

—

### Data, navegador e executor

- Data e hora: —
- Navegador: Google Chrome, versão —
- Executor: Renan Oliveira

### Evidência

- Vídeo: `C40-CT01-cadastrar-categoria.mp4` — link pendente
- Prints: —

### Bug associado

—

---

## C40-CT02 — Nome vazio ou repetido

**Requisito:** RF40  
**Tipo:** Negativo  
**Status:** Não executado  
**Ordem de execução:** 4

### Objetivo

Verificar se o sistema exige o nome da categoria e como trata um nome já usado.

### Pré-condições

- Estar autenticado no SIFIT Alfa.
- `QA_RENAN_CAT_01 Saúde` cadastrada em C40-CT01.

### Dados utilizados

- Tentativa 1: nome vazio
- Tentativa 2: nome com três espaços
- Tentativa 3: nome `QA_RENAN_CAT_01 Saúde`, já cadastrado
- Cancelamento: nome `QA_RENAN_CAT_CANCELADA`
- Nas tentativas: status Ativo, ícone e cor válidos

### Passos

1. Abrir o cadastro de nova categoria.
2. Deixar o nome vazio e preencher os demais campos. Chegar ao botão Salvar com a tecla Tab e acioná-lo pelo teclado. Anotar a mensagem e se o campo com problema é indicado.
3. Preencher o nome com três espaços e clicar em Salvar.
4. Preencher o nome `QA_RENAN_CAT_01 Saúde` e clicar em Salvar.
5. Abrir um novo cadastro, preencher o nome `QA_RENAN_CAT_CANCELADA` e cancelar ou fechar sem salvar.
6. Abrir o cadastro novamente e conferir se os campos estão vazios.
7. Pesquisar `QA_RENAN_CAT` e conferir que só existem as categorias salvas de propósito.

### Resultado esperado

- Inventário: Conferir obrigatoriedade e unicidade.
- Critério: nome vazio ou só com espaços não é salvo e o campo é indicado; nome repetido segue a regra de unicidade; o cadastro cancelado não é salvo nem reaparece ao reabrir.
- A regra de unicidade ainda está a confirmar (seção 8 do planejamento). Sem resposta, registrar o comportamento observado no nome repetido e manter o caso Bloqueado, a menos que outra parte do caso já o reprove.

### Verificações comuns aplicadas

- G02 — Obrigatórios vazios: nome vazio recusado, com o campo indicado.
- G03 — Somente espaços: nome só com espaços tratado como vazio.
- G08 — Duplicidade: nome repetido tratado conforme a regra confirmada.
- G10 — Cancelar/fechar: cadastro cancelado não é salvo.
- G11 — Reabrir formulário: formulário volta sem dados antigos.
- G23 — Teclado, foco e mensagens: Salvar funciona pelo teclado e a mensagem identifica o campo.

### Resultado obtido

—

### Data, navegador e executor

- Data e hora: —
- Navegador: Google Chrome, versão —
- Executor: Renan Oliveira

### Evidência

- Vídeo: `C40-CT02-nome-vazio-repetido.mp4` — link pendente
- Prints: —

### Bug associado

—

---

## C40-CT03 — Cor pelo seletor e código

**Requisito:** RF40  
**Tipo:** Interação  
**Status:** Não executado  
**Ordem de execução:** 2

### Objetivo

Verificar se a cor escolhida no seletor e o código de cor ficam sincronizados e se um código inválido é recusado.

### Pré-condições

- Estar autenticado no SIFIT Alfa.
- Pesquisar `QA_RENAN_CAT_02` e confirmar que ainda não existe.

### Dados utilizados

- Nome: `QA_RENAN_CAT_02`
- Status: Ativo
- Ícone: um válido
- Cor pelo seletor: qualquer tom, anotando o código exibido
- Código válido: `#1E8449`
- Códigos inválidos: `#GGGGGG`, `#12345` e `azul`

### Passos

1. Abrir o cadastro de nova categoria e preencher nome, status e ícone.
2. Escolher uma cor no seletor e conferir se o código muda para a mesma cor.
3. Digitar `#1E8449` no código e conferir se o seletor passa a mostrar essa cor.
4. Digitar cada código inválido e tentar salvar, anotando a resposta do sistema.
5. Informar `#1E8449` e salvar; anotar o código da categoria. Se alguma tentativa inválida tiver sido salva, registrar e corrigir pela edição.
6. Atualizar a página, abrir `QA_RENAN_CAT_02` e conferir a cor na listagem e no formulário.

### Resultado esperado

- Inventário: Sincronizar ambos e rejeitar código inválido.
- Critério: seletor e código mostram sempre a mesma cor; nenhum código inválido é salvo; a categoria fica com `#1E8449`.

### Verificações comuns aplicadas

- G05 — Formato inválido: códigos inválidos recusados, com orientação para correção.

### Resultado obtido

—

### Data, navegador e executor

- Data e hora: —
- Navegador: Google Chrome, versão —
- Executor: Renan Oliveira

### Evidência

- Vídeo: `C40-CT03-cor-seletor-codigo.mp4` — link pendente
- Prints: —

### Bug associado

—

---

## C40-CT04 — Ícone válido e inválido

**Requisito:** RF40  
**Tipo:** Negativo  
**Status:** Não executado  
**Ordem de execução:** 3

### Objetivo

Verificar se o ícone escolhido é exibido e como o sistema trata um ícone inválido.

### Pré-condições

- Estar autenticado no SIFIT Alfa.
- `QA_RENAN_CAT_02` cadastrada em C40-CT03.

### Dados utilizados

Conforme o tipo do campo de ícone:

- Lista: um ícone diferente do atual.
- Texto: um nome de ícone válido e o nome inexistente `icone_inexistente_qa`.
- Upload: uma imagem PNG pequena, um arquivo `.txt` e uma imagem grande, de cerca de 10 MB.

### Passos

1. Abrir `QA_RENAN_CAT_02` para edição.
2. Registrar com print como o ícone é informado: lista, texto ou upload.
3. Informar um ícone válido, salvar e conferir na listagem e no formulário.
4. Informar o ícone inválido correspondente ao tipo do campo e tentar salvar; anotar a resposta.
5. Se for upload: trocar a imagem, testar a imagem grande e cancelar a janela de seleção de arquivo.
6. Atualizar a página e conferir o ícone salvo.

### Resultado esperado

- Inventário: Exibir ícone ou tratamento compreensível.
- Critério: o ícone válido aparece na listagem e no formulário; o inválido é recusado com mensagem compreensível, sem quebrar a tela nem mostrar caminho interno.
- Se o ícone só puder ser escolhido em lista, não há como informar valor inválido: registrar isso com print e avaliar a exibição do ícone escolhido.

### Verificações comuns aplicadas

- G05 — Formato inválido: ícone inválido recusado, com orientação.
- G22 — Upload: somente se o ícone for enviado como arquivo; caso contrário, Não se aplica, com print.

### Resultado obtido

—

### Data, navegador e executor

- Data e hora: —
- Navegador: Google Chrome, versão —
- Executor: Renan Oliveira

### Evidência

- Vídeo: `C40-CT04-icone-valido-invalido.mp4` — link pendente
- Prints: —

### Bug associado

—

---

## C40-CT05 — Filtro, edição e inativação

**Requisito:** RF40  
**Tipo:** Integração  
**Status:** Não executado  
**Ordem de execução:** 29

### Objetivo

Verificar a pesquisa e os filtros de categorias, a edição de uma categoria e o efeito da inativação nas telas de perguntas e modelos.

### Pré-condições

- Estar autenticado no SIFIT Alfa.
- `QA_RENAN_CAT_01 Saúde` e `QA_RENAN_CAT_02` cadastradas.
- Executar depois da cadeia da anamnese (ordens 5 a 28), para não interferir nos casos anteriores.

### Dados utilizados

- Pesquisa existente: `QA_RENAN_CAT`
- Pesquisa inexistente: `QA_RENAN_NAO_EXISTE`
- Edição de `QA_RENAN_CAT_02`: nome `QA_RENAN_CAT_02 Editada` e cor `#AF601A`
- Inativação: `QA_RENAN_CAT_02 Editada`

### Passos

1. Pesquisar `QA_RENAN_CAT` e conferir se aparecem as categorias de teste.
2. Pesquisar `QA_RENAN_NAO_EXISTE` e conferir a resposta de lista vazia.
3. Aplicar cada filtro disponível, sozinho e junto com a pesquisa; depois limpar os filtros.
4. Abrir `QA_RENAN_CAT_02`, alterar nome e cor, salvar e reabrir.
5. Alterar o status para Inativo, salvar e conferir na listagem.
6. Abrir o cadastro de pergunta e o montador de modelos e verificar se `QA_RENAN_CAT_02 Editada` ainda aparece para seleção ou filtro.
7. Conferir se `QA_RENAN_CAT_01 Saúde` e as perguntas ligadas a ela continuam disponíveis.

### Resultado esperado

- Inventário: Conferir disponibilidade para perguntas/modelos.
- Critério: pesquisa e filtros retornam apenas as categorias correspondentes; lista vazia tem mensagem compreensível; a edição é mantida; a categoria inativa não é oferecida para novas perguntas e modelos, e as demais categorias e perguntas não são afetadas.

### Verificações comuns aplicadas

- G12 — Editar registro de teste: alteração mantida ao reabrir.
- G15 — Pesquisa existente/inexistente: correspondências ou estado vazio compreensível.
- G16 — Filtros combinados e limpeza: condições respeitadas e consulta restaurada.
- G20 — Referências e dependências: inativação sem quebrar os vínculos existentes.

### Resultado obtido

—

### Data, navegador e executor

- Data e hora: —
- Navegador: Google Chrome, versão —
- Executor: Renan Oliveira

### Evidência

- Vídeo: `C40-CT05-filtro-edicao-inativacao.mp4` — link pendente
- Prints: —

### Bug associado

—

---

## C40-CT06 — Exclusão com perguntas vinculadas

**Requisito:** RF40  
**Tipo:** Condicional  
**Status:** Não executado  
**Ordem de execução:** 30

### Objetivo

Verificar o que acontece ao excluir uma categoria que tem perguntas vinculadas.

### Pré-condições

- Estar autenticado no SIFIT Alfa.
- `QA_RENAN_CAT_DESC_01` cadastrada e `QA_RENAN_PERG_DESC_01` vinculada a ela, ambas criadas só para este caso.
- Ação de excluir disponível na listagem de categorias. Sem ela, o caso é Não se aplica, com print.
- Nenhum outro registro é excluído.

### Dados utilizados

- Categoria descartável: `QA_RENAN_CAT_DESC_01`
- Pergunta descartável: `QA_RENAN_PERG_DESC_01`

### Passos

1. Em Perguntas de Anamnese, conferir que `QA_RENAN_PERG_DESC_01` está ligada a `QA_RENAN_CAT_DESC_01`.
2. Em Categorias de Anamnese, acionar a exclusão de `QA_RENAN_CAT_DESC_01` e cancelar na confirmação.
3. Conferir que a categoria continua na listagem.
4. Acionar a exclusão novamente e confirmar.
5. Anotar a resposta: exclusão impedida, categoria removida ou outra.
6. Atualizar a página e conferir a listagem de categorias.
7. Abrir `QA_RENAN_PERG_DESC_01` e conferir se a pergunta abre sem erro e qual categoria mostra.

### Resultado esperado

- Inventário: Evitar referências quebradas e perda indevida de estrutura.
- Critério: cancelar mantém a categoria; ao confirmar, o sistema impede a exclusão com mensagem clara ou trata o vínculo sem deixar a pergunta apontando para categoria inexistente e sem apagar a pergunta sem aviso.
- Se o vínculo com a categoria for feito no modelo, e não na pergunta, os passos serão ajustados com um modelo descartável depois do reconhecimento (P9).

### Verificações comuns aplicadas

- G19 — Excluir/cancelar exclusão: cancelar preserva o registro; confirmar segue a regra de exclusão.
- G20 — Referências e dependências: a pergunta vinculada não fica com referência quebrada.

### Resultado obtido

—

### Data, navegador e executor

- Data e hora: —
- Navegador: Google Chrome, versão —
- Executor: Renan Oliveira

### Evidência

- Vídeo: `C40-CT06-excluir-categoria-vinculada.mp4` — link pendente
- Prints: —

### Bug associado

—

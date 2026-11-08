# C19 — Categorias Crossfit

**Responsável:** Adrian  
**Data da execução:** 07/11/2026  
**Sistema:** https://sifitalfa.centrion.com.br/login  
**Caminho:** Treinamento → Categorias Crossfit

## C19-CT01 — Cadastrar categoria válida

**Status:** Aprovado

### Objetivo

Cadastrar uma categoria e conferir se ela aparece na lista.

### Resultado esperado

A categoria deve ser salva e exibida com seu código e nome.

### Resultado obtido

Cadastrei `teste_adrian`. O formulário solicitou somente o nome, e a categoria apareceu na lista com o código `5`.

### Evidência

[Gravação do cadastro](https://drive.google.com/file/d/1ziOAa_tRKHzQaxLSHHhZeBkfE7qh6eXC/view?usp=drive_link)

---

## C19-CT02 — Nome vazio, espaços ou duplicado

**Status:** Parcial — vazio e espaços validados; duplicidade não testada

### Objetivo

Conferir a validação do nome ao cadastrar uma categoria.

### Resultado esperado

O sistema deve recusar um nome vazio ou formado só por espaços. A regra para nomes duplicados precisa ser confirmada.

### Resultado obtido

Ao tentar salvar com o nome vazio, o sistema exibiu “Informe o nome da categoria”. Com apenas espaços, exibiu a mesma mensagem. O cadastro de `teste_adrian2` funcionou; esse nome é diferente de `teste_adrian` e não testa duplicidade.

### Evidência

[Gravação das tentativas de cadastro](https://drive.google.com/file/d/1x3jt4X4rxOTFdYWG_W8wlRMV4qQD91Vb/view?usp=drive_link)

---

## C19-CT03 — Pesquisar código e nome

**Status:** Aprovado

### Objetivo

Pesquisar categorias existentes e inexistentes por código e nome.

### Resultado esperado

Mostrar as categorias correspondentes e nenhum registro para uma busca sem correspondência.

### Resultado obtido

A busca pelo código `5` retornou a categoria esperada. A busca por `teste_adrian` também retornou os registros correspondentes. `invalido_teste` não retornou resultados. A lista foi filtrada durante a digitação, sem precisar pressionar Enter.

### Evidência

[Gravação das pesquisas](https://drive.google.com/file/d/1UTGcTQ0vQaTGbfGnumVbbQtgFe_qSt_A/view?usp=drive_link)

---

## C19-CT04 — Editar e cancelar

**Status:** Aprovado

### Objetivo

Conferir se Cancelar descarta uma alteração e se Salvar mantém a edição.

### Resultado esperado

A alteração cancelada não deve persistir. A alteração salva deve permanecer após atualizar a página.

### Resultado obtido

Localizei a categoria pelo código `5`, alterei o nome para `teste_adrian_cancelado` e cliquei em Cancelar. Após F5, a alteração não havia sido salva. Depois alterei para `teste_adrian_editado`, salvei e atualizei a página; o novo nome permaneceu.

### Evidência

[Gravação da edição e do cancelamento](https://drive.google.com/file/d/1jqHEBAUufuykarJlABxseWxDKq90WtJa/view?usp=drive_link)

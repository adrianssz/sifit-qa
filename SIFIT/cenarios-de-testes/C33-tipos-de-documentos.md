# C33 — Tipos de Documentos

**Responsável:** Adrian  
**Data da execução:** 11/11/2026  
**Sistema:** https://sifitalfa.centrion.com.br/login

## C33-CT01 — Cadastrar tipo para fornecedor

**Status:** Parcial

### Objetivo

Cadastrar um tipo de documento para Conta/Fornecedor e conferir se ele fica disponível no fluxo correspondente.

### Resultado esperado

O tipo deve ser salvo, aparecer na lista e ficar disponível no contexto de Conta/Fornecedor.

### Resultado obtido

Cadastrei `teste_adrian_fornecedor` com a aplicação Conta/Fornecedor. O sistema salvou e listou o registro com código `6`. A disponibilidade no fluxo financeiro não foi conferida nesta gravação.

### Evidência

[Gravação do cadastro para fornecedor](https://drive.google.com/file/d/1rEWpK0fDLmwA0XR7WsGe0UWvwOUSkcBZ/view?usp=drive_link)

---

## C33-CT02 — Cadastrar tipo para colaborador

**Status:** Parcial

### Objetivo

Cadastrar um tipo de documento para Colaborador e conferir sua disponibilidade no contexto adequado.

### Resultado esperado

O tipo deve ser salvo, aparecer na lista e ficar disponível no fluxo de colaboradores.

### Resultado obtido

Cadastrei `teste_adrian_colaborador` com a aplicação Colaborador. O sistema salvou e listou o registro com código `7`. Não conferi sua disponibilidade no formulário de colaboradores.

### Evidência

[Gravação do cadastro para colaborador](https://drive.google.com/file/d/1UR10CnGCxhQdho-kpO8v2C2mBGSnz6gZ/view?usp=drive_link)

---

## C33-CT03 — Nome vazio ou repetido

**Status:** Parcial; regra de duplicidade a confirmar

### Objetivo

Verificar o cadastro sem nome e com um nome já utilizado.

### Resultado esperado

O sistema deve impedir o cadastro sem nome. A regra para nomes repetidos precisa ser confirmada.

### Resultado obtido

Tentei cadastrar um tipo para Conta/Fornecedor sem preencher o nome. O sistema impediu o cadastro e exibiu: “Informe o nome do tipo de documento.”

Depois cadastrei novamente `teste_adrian_fornecedor`. O sistema aceitou o mesmo nome e criou outro registro, com código `8`. A duplicidade foi observada, mas depende da confirmação da regra para ser classificada como defeito. O teste com nome formado apenas por espaços não foi realizado.

### Evidência

[Gravação da validação do nome](https://drive.google.com/file/d/1aZhOO9wsgcVjEnw9Nce2QsuqeolnYy3-/view?usp=drive_link)

---

## C33-CT04 — Pesquisar e filtrar aplicação

**Status:** Aprovado para os critérios testados

### Objetivo

Conferir a pesquisa dos tipos de documentos por nome, código e aplicação.

### Resultado esperado

A lista deve retornar os registros compatíveis com a pesquisa e não mostrar resultados para um termo inexistente.

### Resultado obtido

A pesquisa por `teste_adrian` retornou os registros correspondentes. A pesquisa pelo código `6` e pela aplicação Conta/Fornecedor também retornou os resultados esperados. Ao pesquisar `inexistente_teste`, nenhum registro foi listado.

### Evidência

[Gravação da pesquisa e do filtro](https://drive.google.com/file/d/17cvVsaXcLstdC5UHiSjJOHkWjNUlY4Up/view?usp=drive_link)

---

## C33-CT05 — Editar, cancelar e excluir com vínculo

**Status:** Parcial; vínculo não testado

### Objetivo

Conferir o cancelamento e a persistência da edição, além da exclusão de um tipo de documento. Verificar o comportamento com documentos vinculados quando houver um registro adequado para isso.

### Resultado esperado

Cancelar não deve salvar alterações. Salvar deve manter as alterações após atualizar a página. A exclusão deve remover o registro de teste e preservar eventuais documentos vinculados.

### Resultado obtido

Editei `teste_adrian_colaborador` para `teste_adrian_cancelado` e cliquei em Cancelar. A alteração não foi salva, inclusive após atualizar a página.

Depois alterei o nome para `teste_adrian_editado` e a aplicação para Conta/Fornecedor. Salvei, atualizei a página e confirmei que as alterações permaneceram. Excluí esse registro e atualizei a página novamente; a exclusão funcionou. Não testei a exclusão de um tipo com documentos ou lançamentos vinculados.

### Evidência

[Gravação da edição, cancelamento e exclusão](https://drive.google.com/file/d/1-ZgKcRjFalQDcLIHuWdH84RhdIVD92Z8/view?usp=drive_link)

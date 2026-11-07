# C16 — Objetivos de Treino

**Responsável:** Adrian  
**Data da execução:** 07/11/2026  
**Sistema:** https://sifitalfa.centrion.com.br/login  
**Caminho:** Treinamento → Objetivos Treino

## C16-CT01 — Cadastrar objetivo válido

**Status:** Reprovado na exibição da descrição. Disponibilidade na ficha não confirmada.

### Passos e resultado esperado

Cadastrar um objetivo com nome e descrição, conferir os dados na listagem e verificar se o objetivo fica disponível na ficha de treino.

### Resultado obtido

Preenchi o nome e a descrição com `teste_adrian`. O objetivo apareceu na lista com o nome correto, mas no lugar da descrição apareceu “Sem descricao cadastrada”.

Em Fichas de Treino, encontrei uma ficha já cadastrada. Na tela consultada, não identifiquei onde selecionar o objetivo, então não consegui confirmar essa parte.

### Evidência

[Cadastro e conferência na listagem](https://drive.google.com/file/d/1e0w_zBlMO0WQR9iCkGAwElR7cHlIaYBH/view?usp=drive_link)

---

## C16-CT02 — Nome vazio, espaços e duplicidade

**Status:** Parcial — cadastro sem nome aceito; regra de obrigatoriedade a confirmar.

### Passos executados

Testar o cadastro com campos vazios e conferir como os registros aparecem na lista.

### Resultado obtido

O sistema permitiu cadastrar sem descrição e também sem nome. Na lista, o registro sem nome ficou com o campo em branco. Os registros consultados apareceram sem descrição.

Não confirmei se a descrição é obrigatória. Nome contendo apenas espaços e nome duplicado ficaram sem verificação nesta execução.

### Evidência

[Cadastro com campos vazios](https://drive.google.com/file/d/1AMSqIUZPen4Vl9tED1TXrzHpzTUnvnF9/view?usp=drive_link)

---

## C16-CT03 — Texto longo e caracteres válidos

**Status:** Reprovado na exibição da descrição; nome preservado.

### Passos e resultado esperado

Cadastrar o mesmo texto no nome e na descrição, atualizar a página e conferir se os dois campos continuam exibindo o conteúdo informado.

### Resultado obtido

Usei `teste_adrian00000000000???0000000???000000` nos dois campos. Depois de pressionar F5, o nome continuou aparecendo com os números e sinais de interrogação. A descrição mostrou “Sem descricao cadastrada”, repetindo o comportamento do CT01.

O teste confirmou o que aparece na lista. Não foi possível determinar se a descrição deixou de ser salva ou se apenas não está sendo exibida.

### Evidência

[Texto informado e resultado após atualizar](https://drive.google.com/file/d/14JKoGviD8FEVi4oMXMFok4fDQl3Briqh/view?usp=drive_link)

---

## C16-CT04 — Pesquisar código e nome

**Status:** Aprovado

### Passos e resultado esperado

Pesquisar por nome e código existentes, repetir com valores inexistentes e limpar a busca. A lista deve mostrar as correspondências e voltar ao total quando o campo for limpo.

### Resultado obtido

As buscas por `teste_adrian2` e pelo código `2` retornaram os resultados esperados. As buscas por `teste_inexistente` e pelo código `222` não retornaram registros. Ao limpar o campo, a lista completa voltou automaticamente, sem precisar clicar em Buscar.

### Evidência

[Pesquisa por nome e código](https://drive.google.com/file/d/1pRowVw885ZHxhOlT_Z2vU1RlIbURIYOz/view?usp=drive_link)

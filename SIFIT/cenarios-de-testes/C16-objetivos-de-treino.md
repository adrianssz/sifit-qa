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

---

## C16-CT05 — Editar, cancelar e excluir

**Status:** Reprovado

### Objetivo

Conferir o cancelamento, a edição e a exclusão de um objetivo de treino de teste.

### Passos

1. Abrir o objetivo `teste_adrian`, código `3`.
2. Alterar o nome para `teste_adrian_cancelado` e cancelar.
3. Reabrir o objetivo e conferir o nome.
4. Alterar o nome para `teste_adrian_editado`, preencher a descrição e salvar.
5. Reabrir o objetivo e conferir o código, o nome e a descrição.
6. Tentar excluir o objetivo.

### Resultado esperado

Cancelar deve descartar a alteração. Salvar deve manter o nome e a descrição informados no mesmo registro. A exclusão deve ser concluída ou informar claramente o motivo do bloqueio.

### Resultado obtido

Ao cancelar, a alteração do nome não foi salva. Depois, o nome `teste_adrian_editado` foi salvo e o código `3` permaneceu. A descrição preenchida nas tentativas de edição continuou vazia ao reabrir o registro, repetindo o problema observado nos CT01 e CT03.

Ao tentar excluir, o sistema exibiu “Erro ao deletar Objetivo”. Não foi possível identificar pela mensagem o motivo da falha.

### Evidência

[Assistir à gravação no Drive](https://drive.google.com/file/d/1GApHavxd8CM0Az8u3RxD2aaT4ww8QzLG/view?usp=drive_link)

### Ocorrências para o relatório de bugs

- Descrição não aparece após cadastrar ou editar objetivo — observada nos CT01, CT03 e CT05.
- Exclusão do objetivo código `3` retornou “Erro ao deletar Objetivo”; verificar se existe algum vínculo que impeça a exclusão.

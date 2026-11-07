# C15 — Grupos Musculares

**Responsável:** Adrian  
**Data da execução:** 07/11/2026  
**Sistema:** https://sifitalfa.centrion.com.br/login  
**Caminho:** Treinamento → Grupos Musculares

## C15-CT01 — Pesquisar código e nome

**Status:** Aprovado com observação

### Passos e resultado esperado

Pesquisar um grupo pelo nome e depois pelo código. A lista deve mostrar os registros que correspondem à busca.

### Resultado obtido

A pesquisa filtrou os registros. Ao pesquisar pelo código `2`, apareceram os códigos `2` e `12`. A busca aceitou uma correspondência parcial nesse exemplo. Falta confirmar se a pesquisa por código deveria ser exata.

### Evidência

[Pesquisa por nome e código](https://drive.google.com/file/d/1uJLYWyK2GiOfGOQKoET7o5UIvWcHwhQ3/view?usp=drive_link)

---

## C15-CT02 — Filtrar por classificação

**Status:** Aprovado com observação

### Passos e resultado esperado

Selecionar as classificações disponíveis no filtro Tipo Membro e comparar as listas com a opção Todos. Cada filtro deve mostrar os grupos da classificação escolhida.

### Resultado obtido

Os filtros funcionaram para as classificações disponíveis. Um grupo exibido com o nome `-` apareceu somente em Todos. Não havia uma opção `-` no filtro. Não confirmei qual classificação estava cadastrada nesse grupo.

### Evidência

[Filtro por classificação](https://drive.google.com/file/d/1paZDwXAubTIFgHOMsF4gdiusG72pngz_/view?usp=drive_link)

---

## C15-CT03 — Abrir inclusão e cadastrar grupo

**Status:** Falha na primeira tentativa; aprovado na segunda

### Passos e resultado esperado

Abrir a inclusão, informar o nome `teste_adrian`, selecionar Superiores, escolher uma imagem e salvar. O sistema deve cadastrar o grupo.

### Resultado obtido

Na primeira tentativa, o sistema exibiu uma mensagem de erro ao salvar. Na segunda tentativa, consegui cadastrar o grupo. A causa da falha inicial não foi identificada.

### Evidências

- [Primeira tentativa — erro ao salvar](https://drive.google.com/file/d/1KQeJzuwyaM0q4uqQvGZf3DkONuSr33Zt/view?usp=drive_link)
- [Segunda tentativa — cadastro realizado](https://drive.google.com/file/d/1sr7P9bINAH781m6_N2NwOrAMLmU3PUu1/view?usp=drive_link)

---

## C15-CT04 — Validar nome e classificação vazios

**Status:** Reprovado no roteiro de validação

### Passos e resultado esperado

Tentar salvar primeiro sem nome e depois preenchendo somente o nome. Quando faltar um campo obrigatório, o sistema deve impedir o cadastro e indicar o que precisa ser preenchido.

### Resultado obtido

1. **Sem nome:** o sistema permitiu criar o grupo com o nome vazio. A obrigatoriedade do nome precisa ser confirmada.
2. **Somente com o nome:** preenchi `teste_adrian` e tentei salvar. O sistema exibiu “Erro ao salvar grupo”, sem indicar qual campo precisava ser preenchido. Como somente o nome estava preenchido, não dá para atribuir o erro especificamente à classificação.

### Evidências

- [Cadastro aceito sem nome](https://drive.google.com/file/d/10cedlYriO-hmZdbXDz0RaIBm3urd-NCQ/view?usp=drive_link)
- [Erro ao salvar somente com o nome](https://drive.google.com/file/d/1BhAImqexUXEfemJjAodGePPQT-1xq1Xx/view?usp=drive_link)

---

## C15-CT05 — Edição, exclusão e vínculo a exercícios

**Status:** Parcial — edição e exclusão aprovadas

### Passos e resultado esperado

Editar o nome e o tipo de membro de um grupo de teste, salvar e excluir o registro. Conferir também o comportamento de grupos vinculados a exercícios, quando houver um vínculo de teste disponível.

### Resultado obtido

Consegui alterar o nome de `teste_adrian_teste` para `teste_adrian` e o tipo de membro de Superiores para Aeróbio. A exclusão também funcionou. O comportamento de um grupo vinculado a exercício não foi confirmado nesta execução.

### Evidência

[Edição e exclusão do grupo](https://drive.google.com/file/d/1jXxYPuCH5lrpjlfVfCvDPpSYfSYhJHhY/view?usp=drive_link)

---

## C15-CT06 — Contadores e paginação

**Status:** Aprovado

### Passos e resultado esperado

1. Conferir o total de grupos e a quantidade de cada classificação.
2. Com 10 registros por página, avançar para a segunda página.
3. Alterar para 20 registros por página. Os 15 grupos devem aparecer juntos.

### Resultado obtido

O indicador mostrou 15 grupos, e os contadores por classificação bateram com as listas filtradas. Com 10 registros por página, consegui avançar para a segunda página. Ao selecionar 20 registros por página, os 15 grupos apareceram em uma única página.

### Evidência

[Assistir à gravação no Drive](https://drive.google.com/file/d/1-BSEk7o6rSathpUjO8HQUTAsXCz2tXaN/view?usp=drive_link)

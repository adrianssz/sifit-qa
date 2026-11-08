# C28 — Tipos de Pagamento

**Responsável:** Adrian  
**Data da execução:** 08/11/2026  
**Sistema:** https://sifitalfa.centrion.com.br/login

## C28-CT01 — Cadastrar tipo válido

**Status:** Aprovado

### Objetivo

Cadastrar um tipo de pagamento e conferir sua apresentação na lista.

### Resultado esperado

Salvar o nome e as opções escolhidas, exibindo o cadastro na listagem.

### Resultado obtido

O formulário apresentou Nome, Escolher Bandeira, Tipo e Pagamento Pelo Sistema. Cadastrei `teste_adrian`, com Escolher Bandeira em Sim, Tipo em Crédito e Pagamento Pelo Sistema em Sim. O cadastro foi salvo e listado com o código `13`.

### Evidência

[Gravação do cadastro](https://drive.google.com/file/d/1st_3rcNECz3iyrIlhBcEdFMhufhnjK9z/view?usp=drive_link)

---

## C28-CT02 — Nome vazio e duplicidade

**Status:** Reprovado quanto ao nome vazio; duplicidade a confirmar

### Objetivo

Verificar o cadastro sem nome e com um nome já utilizado.

### Resultado esperado

Um tipo de pagamento sem nome deve ser recusado. A aceitação de nomes repetidos depende da regra de unicidade do sistema.

### Resultado obtido

O sistema permitiu criar um tipo de pagamento com o nome vazio e o exibiu na lista sem nome. Também permitiu criar outro tipo com o nome `teste_adrian`, já utilizado no CT01. Nas duas tentativas, as demais opções eram iguais às do cadastro de código `13`.

A aceitação de nome duplicado foi observada, mas ainda não foi classificada como defeito por falta de confirmação da regra.

### Evidência

[Gravação das duas tentativas](https://drive.google.com/file/d/1G8O2uCluE1X8xTlZwecc13MklBRAQk_G/view?usp=drive_link)

---

## C28-CT03 — Escolher Bandeira Sim/Não

**Status:** Parcial — opções de cadastro verificadas

### Objetivo

Conferir a apresentação e o salvamento das opções Sim e Não em Escolher Bandeira.

### Resultado esperado

O formulário deve aceitar a opção escolhida. A exigência de selecionar uma bandeira durante um pagamento deve ser verificada em um fluxo de pagamento de teste.

### Resultado obtido

Cadastrei `teste_bandeira_adrian` com Escolher Bandeira em Sim e `teste_bandeira_adrian2` com Não. Nos dois casos, selecionei Tipo Débito e Pagamento Pelo Sistema em Sim. A troca entre Sim e Não não mostrou campos adicionais; ambos os cadastros foram salvos e listados.

Não foi realizado um pagamento para conferir o efeito dessa opção no fluxo relacionado.

### Evidência

[Gravação das opções de bandeira](https://drive.google.com/file/d/1POzPpd_ydzeusfaH-ELje0NuMHqRLtP3/view?usp=drive_link)

---

## C28-CT04 — Pagamento Pelo Sistema Sim/Não

**Status:** Parcial — apresentação e cadastro verificados

### Objetivo

Conferir os campos apresentados e o salvamento das opções Sim e Não em Pagamento Pelo Sistema.

### Resultado esperado

O sistema deve salvar a opção escolhida e apresentar os campos adicionais necessários, caso existam.

### Resultado obtido

Cadastrei `teste_pagamento_adrian` e `teste_pagamento_adrian2` com Sim, e `teste_pagamento_adrian_n` com Não. Nos três cadastros, Escolher Bandeira ficou em Não e Tipo em Débito. A mudança da opção não abriu campos adicionais. Os três registros foram salvos e listados.

Não foi executado pagamento nem verificada uma integração com gateway; portanto, o efeito da configuração fora do cadastro continua pendente.

### Evidência

[Gravação das opções de pagamento pelo sistema](https://drive.google.com/file/d/11w5FTl3kH4eHiVuek8VNaiAGtC4zK56Z/view?usp=drive_link)

---

## C28-CT05 — Filtros, edição e status

**Status:** Parcial — filtros, edição e exclusão verificados

### Objetivo

Conferir a pesquisa, a edição e as ações disponíveis para um tipo de pagamento de teste.

### Resultado esperado

As buscas devem retornar os registros correspondentes. Uma edição salva deve permanecer após atualizar a página. Uma exclusão confirmada deve retirar o registro da lista, conforme a regra do sistema.

### Resultado obtido

A pesquisa pelo código `13` retornou o registro correto e filtrou durante a digitação. As pesquisas por `teste_adrian` e pelo tipo Crédito também retornaram resultados.

Editei o registro de código `13` para `teste_adrian_editado`, salvei e confirmei após F5 que a alteração permaneceu. Depois confirmei a exclusão. Ao pesquisar novamente pelo código `13`, o registro não apareceu.

Não foi conferida a alteração de status nem o efeito da exclusão sobre pagamentos históricos, pois não foi apresentado um pagamento de teste vinculado a esse registro.

### Evidência

[Gravação da pesquisa, edição e exclusão](https://drive.google.com/file/d/162RBEv_tI62u43RQbyvLGbWbbfkHPNRE/view?usp=drive_link)

# Bugs — Adrian

## BUG-ADRIAN-001 — Login não é enviado pela tecla Enter

**Caso relacionado:** C01-CT08  
**Data:** 05/11/2026  
**Responsável:** Adrian  
**Severidade sugerida:** Baixa — é possível entrar pelo botão.  
**Status:** Aberto  

### Pré-condições

Estar na tela de login com usuário e senha válidos preenchidos.

### Passos para reproduzir

1. Acessar https://sifitalfa.centrion.com.br/login.
2. Preencher as credenciais válidas.
3. Manter o foco no campo Senha.
4. Pressionar Enter no teclado.

### Resultado esperado

Enviar o formulário e autenticar a conta, assim como ocorre pelo botão Entrar.

### Resultado obtido

Nada aconteceu ao pressionar Enter.

Em uma conferência adicional, sem gravação, o clique no botão Entrar com os mesmos dados realizou o login normalmente.

### Evidências

- [Tentativa pela tecla Enter](https://jam.dev/c/b3b4eead-d508-472e-bef5-e5f861bd4ca4)
- [Login pelo botão — C01-CT01](https://jam.dev/c/03a7848e-2c13-4a70-b4db-fde9ee100fb8)

### Reteste

Ainda não realizado após correção.


---

## BUG-ADRIAN-002 — Link Esqueci minha senha sem resposta visível

**Caso relacionado:** C01-CT10  
**Data:** 05/11/2026  
**Responsável:** Adrian  
**Severidade sugerida:** Média — impede iniciar a recuperação pela tela de login.  
**Status:** Aberto  

### Pré-condições

Estar na tela de login, sem sessão autenticada.

### Passos para reproduzir

1. Acessar https://sifitalfa.centrion.com.br/login.
2. Clicar em Esqueci minha senha.
3. Aguardar a resposta da interface.

### Resultado esperado

Abrir o fluxo de recuperação de senha ou apresentar orientações para recuperar o acesso.

### Resultado obtido

Nada aconteceu após o clique. Nenhuma tela ou orientação foi apresentada.

### Evidência

[Assistir à gravação no Jam](https://jam.dev/c/de8511c8-eab7-4b1d-b079-dc9ae6675cc2)

### Reteste

Ainda não realizado após correção.

---

## BUG-ADRIAN-003 — Destaque do filtro permanece em Tudo

**Caso relacionado:** C02-CT05  
**Data:** 06/11/2026  
**Responsável:** Adrian  
**Severidade sugerida:** Baixa — indicação visual incorreta da seleção.  
**Status:** Aberto  

### Pré-condições

- Estar autenticado no sistema.
- Estar com o painel de notificações aberto.

### Passos para reproduzir

1. Clicar em Tudo.
2. Clicar em Não lidas.
3. Observar o destaque dos botões.

### Resultado esperado

O destaque visual deve acompanhar o filtro selecionado.

### Resultado obtido

Ao clicar em Não lidas, o destaque azul permaneceu em Tudo.

### Limitação

A lista permaneceu igual, mas todas as notificações exibidas aparentavam estar não lidas. Não foi confirmado se a filtragem dos registros funciona.

### Evidência

[Assistir à gravação no Jam](https://jam.dev/c/1fa7ebe9-51a6-4d06-809d-d0899960ba35)

### Reteste

Ainda não realizado após correção.

---

## BUG-ADRIAN-004 — Menu lateral volta ao topo após navegar

**Caso relacionado:** C02-CT01  
**Data do registro:** 11/11/2026  
**Responsável:** Adrian  
**Severidade sugerida:** Baixa — exige rolar o menu novamente.  
**Status:** Aberto

### Passos para reproduzir

1. Rolar o menu lateral até uma opção mais abaixo.
2. Abrir essa opção.
3. Observar a posição do menu na página aberta.

### Resultado esperado

Manter a posição da rolagem para facilitar a navegação pelas opções próximas.

### Resultado obtido

A tela abriu, mas a rolagem do menu voltou ao topo. Para acessar a próxima opção, precisei rolar novamente.

### Evidência

[Gravação da navegação pelo menu](https://drive.google.com/file/d/1lAlZXcNVD5HLZxF79hrz9D4RjABr3jv6/view?usp=drive_link)

### Reteste

Ainda não realizado após correção.

---

## BUG-ADRIAN-005 — Títulos do Dashboard ficam ilegíveis no modo claro

**Caso relacionado:** C02-CT10  
**Data do registro:** 11/11/2026  
**Responsável:** Adrian  
**Severidade sugerida:** Média — dificulta a leitura do Dashboard.  
**Status:** Aberto

### Passos para reproduzir

1. Abrir o Dashboard.
2. Ativar o modo claro.
3. Observar os títulos das seleções.

### Resultado esperado

Os títulos devem ter contraste suficiente para serem lidos nos dois temas.

### Resultado obtido

No modo claro, o fundo e os títulos das seleções ficaram brancos, dificultando a leitura. No modo escuro, o conteúdo ficou visível.

### Evidência

[Gravação do Dashboard](https://drive.google.com/file/d/1AFljR3BzuDHGxGkq5DXoerL1rxZVN486/view?usp=drive_link)

### Reteste

Ainda não realizado após correção.

---

## BUG-ADRIAN-006 — Descrição do objetivo não aparece após salvar

**Casos relacionados:** C16-CT01, C16-CT03 e C16-CT05  
**Data do registro:** 11/11/2026  
**Responsável:** Adrian  
**Severidade sugerida:** Média — a descrição informada não fica disponível para consulta.  
**Status:** Aberto

### Passos para reproduzir

1. Cadastrar ou editar um objetivo de treino preenchendo nome e descrição.
2. Salvar e conferir o registro na lista.
3. Atualizar a página ou reabrir o objetivo.

### Resultado esperado

A descrição informada deve continuar disponível após salvar.

### Resultado obtido

O nome foi salvo, mas a lista mostrou “Sem descricao cadastrada”. Na edição, a descrição preenchida também não apareceu ao reabrir o registro. Não foi possível determinar se a descrição deixou de ser salva ou se apenas não está sendo exibida.

### Evidências

- [Cadastro do objetivo](https://drive.google.com/file/d/1e0w_zBlMO0WQR9iCkGAwElR7cHlIaYBH/view?usp=drive_link)
- [Conferência após atualizar](https://drive.google.com/file/d/14JKoGviD8FEVi4oMXMFok4fDQl3Briqh/view?usp=drive_link)
- [Edição do objetivo](https://drive.google.com/file/d/1GApHavxd8CM0Az8u3RxD2aaT4ww8QzLG/view?usp=drive_link)

### Reteste

Ainda não realizado após correção.

---

## BUG-ADRIAN-007 — Exclusão de objetivo retorna erro genérico

**Caso relacionado:** C16-CT05  
**Data do registro:** 11/11/2026  
**Responsável:** Adrian  
**Severidade sugerida:** Média — impede a exclusão e não informa o motivo.  
**Status:** Aberto

### Passos para reproduzir

1. Localizar o objetivo de teste de código `3`.
2. Clicar para excluir.
3. Observar a resposta.

### Resultado esperado

Excluir o objetivo, se permitido, ou explicar por que a exclusão foi impedida.

### Resultado obtido

O sistema exibiu “Erro ao deletar Objetivo”. A gravação não permitiu identificar a causa da falha nem confirmar se existia algum vínculo impedindo a exclusão.

### Evidência

[Gravação da tentativa de exclusão](https://drive.google.com/file/d/1GApHavxd8CM0Az8u3RxD2aaT4ww8QzLG/view?usp=drive_link)

### Reteste

Ainda não realizado após correção.

---

## BUG-ADRIAN-008 — Tipo de pagamento é cadastrado sem nome

**Caso relacionado:** C28-CT02  
**Data do registro:** 11/11/2026  
**Responsável:** Adrian  
**Severidade sugerida:** Média — cria um registro sem identificação na lista.  
**Status:** Aberto

### Passos para reproduzir

1. Abrir o cadastro de tipo de pagamento.
2. Deixar o campo Nome vazio.
3. Preencher as demais opções e salvar.

### Resultado esperado

Impedir o cadastro e solicitar o preenchimento do nome.

### Resultado obtido

O sistema permitiu criar o tipo de pagamento e o exibiu na lista com o nome em branco.

### Evidência

[Gravação da validação do nome](https://drive.google.com/file/d/1G8O2uCluE1X8xTlZwecc13MklBRAQk_G/view?usp=drive_link)

### Reteste

Ainda não realizado após correção.

---

## BUG-ADRIAN-009 — Cadastro de bandeira falha com dados de teste

**Casos relacionados:** C29-CT01, C29-CT03 e C29-CT04  
**Caso impedido pela falha:** C29-CT05  
**Data do registro:** 11/11/2026  
**Responsável:** Adrian  
**Severidade sugerida:** Média — impede o cadastro e os testes que dependem de uma bandeira salva.  
**Status:** Aberto

### Passos para reproduzir

1. Abrir Bandeiras de Cartão e clicar em Nova Bandeira.
2. Informar um nome e valores para Taxa Adicional e Taxa Débito.
3. Clicar em Salvar e conferir a lista, inclusive após atualizar a página.

### Resultado esperado

Salvar e listar a bandeira ou informar claramente qual dado precisa ser corrigido.

### Resultado obtido

As tentativas não produziram uma bandeira na lista. Nas tentativas com parcelas, o sistema exibiu “Erro ao cadastrar bandeira”. O campo Código não permitiu preenchimento na segunda tentativa de cadastro. Sem uma bandeira salva, o C29-CT05 ficou bloqueado.

### Evidências

- [Primeira tentativa de cadastro](https://drive.google.com/file/d/1ZjC4j0QTBqv0LcnX4FkilHu-QBjN-ip2/view?usp=drive_link)
- [Segunda tentativa de cadastro](https://drive.google.com/file/d/19Eyn8VgUT0nzc18okMBiFx6pcDg9r9JF/view?usp=drive_link)
- [Tentativa com parcela e mensagem de erro](https://drive.google.com/file/d/1_pX4HVbHz_PdniSM7daCu2OfAdFoNDKg/view?usp=drive_link)

### Reteste

Ainda não realizado após correção.

---

## BUG-ADRIAN-010 — Função aceita nome formado apenas por espaços

**Caso relacionado:** C31-CT02  
**Data do registro:** 11/11/2026  
**Responsável:** Adrian  
**Severidade sugerida:** Baixa — permite cadastrar uma função sem nome legível.  
**Status:** Aberto

### Passos para reproduzir

1. Abrir o cadastro de função.
2. Preencher o Nome somente com espaços.
3. Selecionar as demais opções e salvar.

### Resultado esperado

Tratar espaços como nome vazio e solicitar um nome válido.

### Resultado obtido

O sistema criou a função com o nome formado apenas por espaços.

### Evidência

[Gravação da validação do nome](https://drive.google.com/file/d/1CsEN8lVcZjGdyDizDMfJREJ_i1tJgryZ/view?usp=drive_link)

### Reteste

Ainda não realizado após correção.

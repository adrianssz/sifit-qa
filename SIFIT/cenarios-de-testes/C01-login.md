# C01 — Autenticação e sessão

## C01-CT01 — Login com dados corretos

**Responsável:** Adrian  
**Data da execução:** 05/11/2026  
**Tipo:** Positivo  
**Status:** Aprovado  
**Sistema:** https://sifitalfa.centrion.com.br/login

### Objetivo

Verificar se o sistema permite entrar com credenciais válidas.

### Pré-condições

- Estar na tela de login, sem sessão autenticada.
- Ter uma conta válida para acessar o sistema.

### Passos

1. Preencher o campo Login com o usuário da conta de teste.
2. Preencher o campo Senha com a senha válida, mantendo-a mascarada.
3. Deixar a opção Manter conectado desmarcada.
4. Clicar em Entrar.
5. Aguardar o carregamento da página inicial.

### Resultado esperado

O sistema deve autenticar a conta e abrir a página inicial.

### Resultado obtido

O login foi realizado com sucesso e o sistema abriu a página inicial, exibindo a saudação “Boa tarde, Jair!”.

A correspondência entre a conta utilizada e o nome exibido será verificada separadamente no C01-CT14.

### Evidência

[Assistir à gravação no Jam](https://jam.dev/c/03a7848e-2c13-4a70-b4db-fde9ee100fb8)

### Bug associado

Nenhum identificado neste caso.



---

## C01-CT02 — Login com senha incorreta

**Responsável:** Adrian  
**Data da execução:** 05/11/2026  
**Tipo:** Negativo  
**Status:** Aprovado  
**Sistema:** https://sifitalfa.centrion.com.br/login

### Objetivo

Verificar se o sistema recusa o acesso com usuário válido e senha incorreta.

### Pré-condições

- Estar na tela de login, sem sessão autenticada.
- Ter um usuário válido para o teste.

### Passos

1. Preencher Login com o usuário válido.
2. Preencher Senha com uma senha incorreta.
3. Deixar Manter conectado desmarcado.
4. Clicar em Entrar.
5. Conferir a resposta do sistema.

### Resultado esperado

O sistema deve recusar a autenticação e informar que as credenciais estão incorretas.

### Resultado obtido

O sistema recusou o login e exibiu a mensagem: “O nome de usuário e senha não correspondem.”

### Evidência

[Assistir à gravação no Jam](https://jam.dev/c/631962eb-718e-4bf4-87a1-d122b98c92ca)

### Bug associado

Nenhum identificado neste caso.

---

## C01-CT03 — Login com usuário inexistente

**Responsável:** Adrian  
**Data da execução:** 05/11/2026  
**Tipo:** Negativo  
**Status:** Aprovado  
**Sistema:** https://sifitalfa.centrion.com.br/login

### Objetivo

Verificar se o sistema recusa o acesso com um usuário não cadastrado.

### Pré-condições

- Estar na tela de login, sem sessão autenticada.
- Utilizar um usuário de teste não cadastrado.

### Passos

1. Preencher Login com qa_usuario_inexistente_05112026.
2. Preencher Senha com Teste123!.
3. Deixar Manter conectado desmarcado.
4. Clicar em Entrar.
5. Conferir a resposta do sistema.

### Resultado esperado

O sistema deve recusar a autenticação e informar que as credenciais são inválidas.

### Resultado obtido

O sistema recusou o login e exibiu a mensagem: “O nome de usuário e senha não correspondem.”

### Evidência

[Assistir à gravação no Jam](https://jam.dev/c/eb95bdee-7830-4147-91a0-74cd769562f0)

### Bug associado

Nenhum identificado neste caso.

---

## C01-CT04 — Login e senha vazios

**Responsável:** Adrian  
**Data da execução:** 05/11/2026  
**Tipo:** Negativo  
**Status:** Reprovado  

### Objetivo

Verificar a validação do login com os dois campos vazios.

### Pré-condições

- Estar na tela de login, sem sessão autenticada.

### Passos

1. Deixar Login e Senha vazios.
2. Deixar Manter conectado desmarcado.
3. Clicar em Entrar.
4. Conferir a resposta do sistema.

### Resultado esperado

Impedir a autenticação e orientar o preenchimento dos campos obrigatórios.

### Resultado obtido

O sistema recusou o login e exibiu: “O nome de usuário e senha não correspondem.”

O bloqueio do acesso funcionou, mas a mensagem não indicou que os campos estavam vazios.

### Evidência

[Assistir à gravação no Jam](https://jam.dev/c/ce9dece8-08fb-4983-8ee3-e6dcc3ee73db)

### Observação

Divergência em relação ao resultado esperado do roteiro. Confirmar a regra de validação antes de consolidar como defeito no relatório de bugs.

---

## C01-CT05 — Login vazio e senha preenchida

**Responsável:** Adrian  
**Data da execução:** 05/11/2026  
**Tipo:** Negativo  
**Status:** Reprovado  

### Objetivo

Verificar a validação quando apenas o campo Login está vazio.

### Pré-condições

- Estar na tela de login, sem sessão autenticada.
- Ter a senha válida da conta de teste.

### Passos

1. Deixar Login vazio.
2. Preencher Senha com a senha válida, mantendo-a mascarada.
3. Deixar Manter conectado desmarcado.
4. Clicar em Entrar.
5. Conferir a resposta do sistema.

### Resultado esperado

Impedir a autenticação e orientar o preenchimento do campo Login.

### Resultado obtido

O sistema recusou o login e exibiu: “O nome de usuário e senha não correspondem.”

O bloqueio do acesso funcionou, mas a mensagem não indicou que o campo Login estava vazio.

### Evidência

[Assistir à gravação no Jam](https://jam.dev/c/e309fabf-e968-418c-91f6-f17a1dd16995)

### Observação

Divergência em relação ao resultado esperado do roteiro. Confirmar a regra de validação antes de consolidar como defeito no relatório de bugs.

---

## C01-CT06 — Login preenchido e senha vazia

**Responsável:** Adrian  
**Data da execução:** 05/11/2026  
**Tipo:** Negativo  
**Status:** Reprovado  

### Objetivo

Verificar a validação quando apenas o campo Senha está vazio.

### Pré-condições

- Estar na tela de login, sem sessão autenticada.
- Ter um usuário válido para o teste.

### Passos

1. Preencher Login com o usuário válido.
2. Deixar Senha vazia.
3. Deixar Manter conectado desmarcado.
4. Clicar em Entrar.
5. Conferir a resposta do sistema.

### Resultado esperado

Impedir a autenticação e orientar o preenchimento do campo Senha.

### Resultado obtido

O sistema recusou o login e exibiu: “O nome de usuário e senha não correspondem.”

O bloqueio do acesso funcionou, mas a mensagem não indicou que o campo Senha estava vazio.

### Evidência

[Assistir à gravação no Jam](https://jam.dev/c/36f47754-9508-4b3b-8b85-c27c0fe6abec)

### Observação

Divergência em relação ao resultado esperado do roteiro. Confirmar a regra de validação antes de consolidar como defeito no relatório de bugs.

---

## C01-CT07 — Senha mascarada

**Responsável:** Adrian  
**Data da execução:** 05/11/2026  
**Tipo:** Interface  
**Status:** Aprovado  

### Objetivo

Verificar se os caracteres da senha ficam mascarados.

### Pré-condições

- Estar na tela de login.
- Deixar o campo Senha vazio antes do teste.

### Passos

1. Clicar no campo Senha.
2. Digitar a senha fictícia TesteVisual123!.
3. Observar os caracteres durante a digitação.
4. Clicar fora do campo.
5. Conferir se a senha permanece mascarada.

### Resultado esperado

A senha deve permanecer mascarada durante a digitação e após sair do campo.

### Resultado obtido

Os caracteres ficaram mascarados durante a digitação e permaneceram assim após sair do campo.

### Evidência

[Assistir à gravação no Jam](https://jam.dev/c/0f2efdda-4128-4af8-9d28-b364e43d4f88)

### Bug associado

Nenhum identificado neste caso.

---

## C01-CT08 — Entrar pelo botão e pela tecla Enter

**Responsável:** Adrian  
**Data da execução:** 05/11/2026  
**Tipo:** Interação  
**Status:** Reprovado  

### Objetivo

Verificar o envio do login pelo botão Entrar e pela tecla Enter.

### Pré-condições

- Estar na tela de login, sem sessão autenticada.
- Preencher usuário e senha válidos.

### Passos

1. Preencher as credenciais válidas.
2. Deixar Manter conectado desmarcado.
3. Manter o foco no campo Senha.
4. Pressionar Enter no teclado.
5. Observar a resposta.
6. Clicar no botão Entrar com os mesmos dados para comparação.

### Resultado esperado

As duas formas de envio devem autenticar a conta e abrir a página inicial.

### Resultado obtido

Ao pressionar Enter no campo Senha, nada aconteceu.

Ao clicar no botão Entrar com os mesmos dados, o login funcionou normalmente.

### Evidências

- [Tentativa pela tecla Enter](https://jam.dev/c/b3b4eead-d508-472e-bef5-e5f861bd4ca4)
- [Login pelo botão registrado no C01-CT01](https://jam.dev/c/03a7848e-2c13-4a70-b4db-fde9ee100fb8)

A conferência adicional pelo botão, após a tentativa pelo teclado, foi realizada sem nova gravação.

### Bug associado

BUG-ADRIAN-001 — Login não é enviado pela tecla Enter no campo Senha.

---

## C01-CT09 — Manter conectado marcado e desmarcado

**Responsável:** Adrian  
**Data da execução:** 05/11/2026  
**Tipo:** Sessão  
**Status:** Pendente de validação da regra  
**Sistema:** https://sifitalfa.centrion.com.br/login

### Objetivo

Comparar a persistência da sessão após fechar e reabrir o navegador, com Manter conectado marcado e desmarcado.

### Pré-condições

- Ter uma conta válida.
- Utilizar o mesmo navegador e perfil nas duas condições.
- Encerrar a sessão anterior antes de preparar cada condição.

### Passos

1. Realizar login com Manter conectado marcado.
2. Fechar todas as janelas do navegador sem clicar em Sair.
3. Reabrir o navegador e acessar /dashboard sem informar as credenciais novamente.
4. Atualizar a página e observar o acesso.
5. Encerrar a sessão pelo botão Sair.
6. Realizar novo login com Manter conectado desmarcado.
7. Repetir o fechamento, a reabertura e o acesso direto a /dashboard.
8. Atualizar a página e comparar os resultados.

### Resultado esperado

A persistência deve seguir a regra definida para cada opção. A duração da sessão e o efeito de Manter conectado ainda precisam ser confirmados.

### Resultado obtido

A área interna permaneceu acessível após reabrir o navegador nas duas condições, sem informar novamente as credenciais.

O acesso direto a /login exibiu o formulário, mas isso não significou encerramento da sessão: /dashboard continuou acessível.

### Evidências

- [Login com a opção marcada](https://jam.dev/c/f008cbed-2614-4c21-804e-f6232863b168)
- [Área interna após reabertura — opção marcada](https://jam.dev/c/2e9d0eb7-92fa-469f-9c63-1b4fe0c7dc53)
- [Área interna após reabertura — opção desmarcada](https://jam.dev/c/d6ebac89-f0cb-445a-a2f5-d85ea2381f0f)

O fechamento e a reabertura do navegador ocorreram fora das gravações.

### Observação

O teste foi executado, mas a conclusão depende da confirmação da regra de sessão. Não foi realizado teste de expiração por tempo. Nenhum defeito foi confirmado neste caso.

---

## C01-CT10 — Abertura da recuperação de senha

**Responsável:** Adrian  
**Data da execução:** 05/11/2026  
**Tipo:** Condicional  
**Status:** Reprovado  
**Sistema:** https://sifitalfa.centrion.com.br/login

### Objetivo

Verificar se o link Esqueci minha senha abre o fluxo de recuperação ou apresenta orientações.

### Pré-condições

- Estar na tela de login, sem sessão autenticada.

### Passos

1. Clicar em Esqueci minha senha.
2. Aguardar e observar a resposta da interface.

### Resultado esperado

Abrir o fluxo de recuperação de senha ou apresentar orientações para recuperar o acesso.

### Resultado obtido

Ao clicar em Esqueci minha senha, nada aconteceu. Nenhuma tela ou orientação foi apresentada.

### Evidência

[Assistir à gravação no Jam](https://jam.dev/c/de8511c8-eab7-4b1d-b079-dc9ae6675cc2)

### Limitação

Não foi possível avançar para o envio da solicitação. Nenhuma senha foi alterada.

### Bug associado

BUG-ADRIAN-002 — Link Esqueci minha senha sem resposta visível.

---

## C01-CT11 — Atualizar a página autenticada

**Responsável:** Adrian  
**Data da execução:** 05/11/2026  
**Tipo:** Sessão  
**Status:** Aprovado  
**Sistema:** https://sifitalfa.centrion.com.br/login

### Objetivo

Verificar se a sessão permanece ativa após atualizar a página.

### Pré-condições

- Estar autenticado no sistema.
- Estar na página inicial.

### Passos

1. Pressionar F5.
2. Aguardar o carregamento.
3. Conferir se a área interna permanece acessível.

### Resultado esperado

Manter a sessão ativa, sem solicitar novo login.

### Resultado obtido

A página carregou normalmente e a sessão permaneceu ativa, sem solicitar as credenciais novamente.

### Evidência

[Assistir à gravação no Jam](https://jam.dev/c/d3b0590f-fe36-4b52-98c2-2f0af011e75f)

### Bug associado

Nenhum identificado neste caso.

---

## C01-CT12 — Logout e retorno pelo botão Voltar

**Responsável:** Adrian  
**Data da execução:** 05/11/2026  
**Tipo:** Sessão  
**Status:** Aprovado  
**Sistema:** https://sifitalfa.centrion.com.br/login

### Objetivo

Verificar se o botão Voltar permite recuperar o acesso após sair da conta.

### Pré-condições

- Estar autenticado no sistema.

### Passos

1. Abrir o menu do usuário e clicar em Sair.
2. Aguardar a tela de login.
3. Clicar no botão Voltar do navegador.
4. Conferir se a área interna volta a ficar acessível.

### Resultado esperado

Manter o acesso à área interna bloqueado após encerrar a sessão.

### Resultado obtido

Após sair e clicar em Voltar, o sistema permaneceu na tela de login e não retornou à área interna.

### Evidência

[Assistir à gravação no Jam](https://jam.dev/c/6026f419-2596-4e46-be61-0dd093845a96)

### Bug associado

Nenhum identificado neste caso.

---

## C01-CT13 — Acesso direto sem sessão

**Responsável:** Adrian  
**Data da execução:** 05/11/2026  
**Tipo:** Negativo  
**Status:** Aprovado  
**Sistema:** https://sifitalfa.centrion.com.br/login

### Objetivo

Verificar se uma página interna fica protegida quando não há sessão autenticada.

### Pré-condições

- Ter saído da conta pelo botão Sair.
- Estar sem sessão autenticada.

### Passos

1. Acessar diretamente https://sifitalfa.centrion.com.br/dashboard.
2. Não informar credenciais.
3. Aguardar o carregamento e observar o resultado.

### Resultado esperado

Impedir o acesso à área interna e solicitar login.

### Resultado obtido

O sistema solicitou login e não abriu a área interna.

### Evidência

[Assistir à gravação no Jam](https://jam.dev/c/17b5a3e2-388a-467c-b9c8-35fb0bc41172)

### Bug associado

Nenhum identificado neste caso.

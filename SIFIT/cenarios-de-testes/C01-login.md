# C01 — Autenticação e sessão

## C01-CT01 — Login com dados corretos

**Responsável:** Adrian  
**Data da execução:** 05/11/2026  
**Tipo:** Positivo  
**Status:** Aprovado  
**Sistema:** https://sifit.centrion.com.br/login

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
**Sistema:** https://sifit.centrion.com.br/login

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
**Sistema:** https://sifit.centrion.com.br/login

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

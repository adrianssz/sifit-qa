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

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

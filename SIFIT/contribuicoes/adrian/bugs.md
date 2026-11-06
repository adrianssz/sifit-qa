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

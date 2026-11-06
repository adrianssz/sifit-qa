# C02 — Navegação e comportamento geral

## C02-CT03 — Rolagem do menu lateral

**Responsável:** Adrian  
**Data da execução:** 05/11/2026  
**Tipo:** Interface  
**Status:** Aprovado  
**Sistema:** https://sifitalfa.centrion.com.br/login

### Objetivo

Verificar se a rolagem permite visualizar todas as opções do menu lateral.

### Pré-condições

- Estar autenticado no sistema.
- Estar com o menu lateral aberto.

### Passos

1. Posicionar o menu no início.
2. Posicionar o mouse sobre o menu lateral.
3. Rolar até o final, observando as opções.
4. Rolar de volta até o início.

### Resultado esperado

Permitir percorrer todo o menu, sem opções inacessíveis ou cortadas.

### Resultado obtido

A rolagem funcionou normalmente até o final e no retorno ao início. Todas as opções puderam ser visualizadas.

### Evidência

[Assistir à gravação no Jam](https://jam.dev/c/e6dc57f3-0747-4d26-8730-55f4d51ee5dc)

### Bug associado

Nenhum identificado neste caso.

---

## C02-CT04 — Alternar tema claro e escuro

**Responsável:** Adrian  
**Data da execução:** 06/11/2026  
**Tipo:** Interface  
**Status:** Aprovado  
**Sistema:** https://sifitalfa.centrion.com.br/login

### Objetivo

Verificar a alternância dos temas, a legibilidade e a persistência da preferência após atualizar a página.

### Pré-condições

- Estar autenticado no sistema.
- Ter acesso ao botão de alternância de tema.

### Passos

1. Clicar no botão de sol/lua do menu lateral.
2. Conferir a legibilidade dos textos, ícones e botões.
3. Pressionar F5.
4. Conferir se o tema escolhido permanece.
5. Alternar novamente para o tema anterior.

### Resultado esperado

Alternar entre os temas mantendo a interface legível e preservar a preferência após atualizar a página.

### Resultado obtido

A alternância funcionou normalmente. Os dois temas ficaram legíveis e o tema escolhido permaneceu após atualizar a página.

### Evidência

[Assistir à gravação no Jam](https://jam.dev/c/1930eb1c-1111-4134-93f5-813ef759960b)

### Bug associado

Nenhum identificado neste caso.

---

## C02-CT05 — Abrir e fechar notificações

**Responsável:** Adrian  
**Data da execução:** 06/11/2026  
**Tipo:** Interação  
**Status:** Aprovado  
**Sistema:** https://sifitalfa.centrion.com.br/login

### Objetivo

Verificar a abertura, a apresentação e o fechamento do painel de notificações.

### Pré-condições

- Estar autenticado no sistema.

### Passos

1. Clicar no sino no canto superior direito.
2. Aguardar a abertura do painel.
3. Conferir o conteúdo apresentado.
4. Clicar fora do painel para fechá-lo.

### Resultado esperado

Abrir e fechar o painel normalmente, exibindo notificações ou uma indicação compreensível de lista vazia.

### Resultado obtido

O painel abriu normalmente, sem problemas na apresentação, e fechou ao clicar fora dele.

### Evidência

[Assistir à gravação no Jam](https://jam.dev/c/d02da9df-b08e-4912-8bf5-cf5abfe3131a)

### Bug associado

Nenhum identificado neste caso.

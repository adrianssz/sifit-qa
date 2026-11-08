# C29 — Bandeiras de Cartão

**Responsável:** Adrian  
**Data da execução:** 08/11/2026  
**Sistema:** https://sifitalfa.centrion.com.br/login

## C29-CT01 — Cadastrar bandeira e taxas válidas

**Status:** Reprovado

### Objetivo

Cadastrar uma bandeira com nome e taxas válidas e conferir sua presença na lista.

### Resultado esperado

A bandeira deve ser salva e aparecer na listagem com os valores informados.

### Resultado obtido

Na primeira tentativa, informei `teste_adrian`, Taxa Adicional `2,50` e Taxa Débito `1,00`. Após clicar em Salvar, a lista continuou sem registros, inclusive depois de F5.

Na segunda tentativa, usei `teste_adrian_9001` e informei novamente as taxas. O campo Código não permitiu preenchimento. Após Salvar, a bandeira também não apareceu na lista. Não foi gerado um registro que pudesse ser usado nos testes de edição.

### Evidências

- [Primeira tentativa de cadastro](https://drive.google.com/file/d/1ZjC4j0QTBqv0LcnX4FkilHu-QBjN-ip2/view?usp=drive_link)
- [Segunda tentativa de cadastro](https://drive.google.com/file/d/19Eyn8VgUT0nzc18okMBiFx6pcDg9r9JF/view?usp=drive_link)

---

## C29-CT02 — Taxas negativas, texto e limites

**Status:** Parcial — entrada negativa verificada

### Objetivo

Conferir a aceitação de valores inválidos nos campos de taxa.

### Resultado esperado

Os campos devem impedir ou orientar a correção de valores que não sejam válidos.

### Resultado obtido

Tentei digitar o sinal negativo nos campos Taxa Adicional e Taxa Débito, mas os campos não aceitaram o caractere. A gravação foi encerrada após essa verificação.

Texto, valores altos, limites e arredondamento não foram verificados nesta execução.

### Evidência

[Gravação da tentativa com valor negativo](https://drive.google.com/file/d/1UzpJPFo0vEtcJu-ecFysSkij49EielqH/view?usp=drive_link)

---

## C29-CT03 — Adicionar e remover parcela

**Status:** Parcial — interação aprovada; persistência bloqueada

### Objetivo

Verificar a inclusão e a remoção de uma parcela no formulário de bandeira.

### Resultado esperado

A parcela adicionada deve aparecer no formulário e desaparecer quando removida. Ao salvar a bandeira, as parcelas restantes devem ser preservadas.

### Resultado obtido

Preenchi o nome `teste_adrian` e taxas de `1,00`. Adicionei uma parcela de teste com valor `1,50`, que apareceu na lista do formulário. Ao clicar para excluir essa parcela, ela foi removida corretamente.

Ao tentar salvar a nova bandeira, o sistema exibiu “Erro ao cadastrar bandeira”. Por isso, não foi possível conferir parcelas após reabrir um cadastro salvo.

### Evidência

[Gravação da inclusão, remoção e tentativa de salvar](https://drive.google.com/file/d/1_pX4HVbHz_PdniSM7daCu2OfAdFoNDKg/view?usp=drive_link)

---

## C29-CT04 — Multiplicar taxa adicional por mês

**Status:** Inconclusivo quanto ao cálculo; falha ao salvar observada

### Objetivo

Comparar o comportamento da opção Multiplica taxa adicional por mês com parcelas de teste.

### Resultado esperado

A opção deve seguir a regra de cálculo definida para as parcelas e permitir salvar uma configuração válida.

### Resultado obtido

Preenchi o formulário com nome de teste e taxas de `1,00`, adicionei uma parcela e marquei Multiplica taxa adicional por mês. Uma tentativa de adicionar outra parcela com o mesmo nome não foi concluída; com outro nome e valor `2,00`, a parcela foi adicionada.

Ao tentar salvar a bandeira, ocorreu erro de cadastro. Não houve uma configuração salva nem um resultado de cálculo confirmado que permitisse validar o efeito da opção.

### Evidência

[Gravação das parcelas, opção de multiplicação e erro](https://drive.google.com/file/d/1-jUTqNMUuBExFnKdWzrskQ99A8j-KH_i/view?usp=drive_link)

---

## C29-CT05 — Pesquisa, edição e dependências

**Status:** Bloqueado — sem bandeira de teste cadastrada

### Objetivo

Pesquisar e editar uma bandeira de teste e verificar seus vínculos com tipos de pagamento.

### Pré-condição

Ter uma bandeira de teste salva no sistema.

### Resultado obtido

As tentativas de cadastro dos CT01, CT03 e CT04 não produziram uma bandeira salva. Por isso, não havia registro de teste para pesquisar, editar ou vincular a um tipo de pagamento. O CT05 não foi executado.

### Evidências relacionadas

- [Tentativa de cadastro do CT01](https://drive.google.com/file/d/1ZjC4j0QTBqv0LcnX4FkilHu-QBjN-ip2/view?usp=drive_link)
- [Erro ao cadastrar no CT03](https://drive.google.com/file/d/1_pX4HVbHz_PdniSM7daCu2OfAdFoNDKg/view?usp=drive_link)

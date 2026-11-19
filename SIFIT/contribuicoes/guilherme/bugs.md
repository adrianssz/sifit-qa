# Bugs — Guilherme

## BUG-GUILHERME-001 — Erro ao salvar conta a receber com dados válidos

**Casos relacionados:** C11-CT03 e C11-CT04  
**Data:** 18/11/2026  
**Responsável:** Guilherme  
**Severidade sugerida:** Média — impede o cadastro nos cenários testados.  
**Status:** Aberto

### Pré-condições

- Estar autenticado no SIFIT.
- Acessar Financeiro → Contas a Receber.
- Ter o cliente 419 cadastrado.

### Passos para reproduzir

1. Acessar Contas a Receber e clicar em Nova Conta.
2. Selecionar o status Pendente.
3. Selecionar o cliente 419 e manter o título Matrícula.
4. Informar o valor de R$ 150,50 e preencher os demais campos obrigatórios.
5. Clicar em Salvar.
6. Repetir com R$ 150,00 e vencimentos em 13/11/2026, 14/11/2026 e 21/11/2026.
7. Conferir se os registros foram criados.

### Resultado esperado

O sistema deve permitir salvar contas a receber com dados válidos e apresentar os registros na listagem.

### Resultado obtido

No C11-CT03, tentei cadastrar uma conta no valor de R$ 150,50, mas o sistema apresentou a mensagem **"Erro ao salvar conta a receber"**. Conferi a listagem e o registro não foi criado.

No C11-CT04, tentei cadastrar contas com três datas diferentes de vencimento, mantendo o status Pendente e o valor de R$ 150,00. Todas as tentativas apresentaram erro ao salvar.

Confirmei que nenhuma das contas foi criada.

Os dois testes apresentaram falhas de salvamento semelhantes, mas a causa técnica ainda não foi identificada.

### Evidências

- [C11-CT03 — Valores e casas decimais](https://jam.dev/c/ba89e664-27c9-4e1f-aaba-ea643353cbc3)
- [C11-CT04 — Datas de vencimento](https://jam.dev/c/769ee2e7-54ee-4049-9451-f98722be72ce)

### Reteste

Pendente após investigação ou correção do problema.

---

## BUG-GUILHERME-002 — Recebimento acima do valor da conta é aceito

**Caso relacionado:** C11-CT07  
**Data do registro:** 19/11/2026  
**Responsável:** Guilherme  
**Severidade sugerida:** Alta — permite registrar um valor recebido maior que o valor da conta.  
**Status:** Aberto  
**Execução:** Automatizada pelo Chrome DevTools MCP.

### Pré-condições
Conta de teste 1667, com título QA_GUILHERME_CT07, vinculada ao cliente QA_GUILHERME_CLIENTE_001. Antes da tentativa, estava Pendente, com R$ 52,00 a receber e nenhum valor recebido.

### Passos para reproduzir
1. Abrir a conta 1667 em Contas a Receber e clicar em Efetuar Recebimento.
2. Informar R$ 53,00 em Valor Recebido.
3. Selecionar Manual SIFIT Pix e o local Teste.
4. Clicar em Salvar e confirmar o aviso de que o caixa aberto não é de hoje.
5. Conferir os valores e o status da conta na listagem e na consulta.

### Resultado esperado
Tratar o excedente de R$ 1,00 de forma explícita ou impedir o recebimento acima do saldo, sem deixar valores inconsistentes na conta.

### Resultado obtido
O sistema aceitou a operação. A conta passou a constar como Recebido, com R$ 52,00 a receber e R$ 53,00 recebidos. O único aviso apresentado tratava da data do caixa, não do valor excedente.

A ocorrência foi observada em uma tentativa. Nenhum segundo recebimento foi realizado.

### Evidência
[Gravação do C11-CT07 no Jam](https://jam.dev/c/6417ee9e-5993-4c45-b54d-55d655534a08)

### Reteste
Pendente após investigação ou correção. Usar outra conta de teste para não repetir o recebimento na conta 1667.

---

## BUG-GUILHERME-003 — Possível falha na criação de cópias de contas a receber

**Caso relacionado:** C11-CT08  
**Data do registro:** 19/11/2026  
**Responsável:** Guilherme  
**Severidade sugerida:** Média — a opção de cópia não produziu um registro adicional visível na consulta realizada.  
**Status:** Em análise  
**Execução:** Automatizada pelo Codex com Chrome DevTools MCP.

### Pré-condições
Usei o cliente de teste 419, QA_GUILHERME_CLIENTE_001. Antes do cadastro, não havia conta com o título QA_GUILHERME_CT08 na consulta.

### Passos para reproduzir
1. Abri Nova Conta e selecionei Pendente e o cliente 419.
2. Informei o título QA_GUILHERME_CT08, R$ 10,00 e vencimento em 19/11/2026.
3. Selecionei Criar Cópias → Sim e salvei uma única vez.
4. Busquei as contas do cliente 419 com vencimentos até 31/12/2027.

### Resultado esperado
Eu deveria conseguir identificar as cópias geradas e conferir seus códigos, valores e vencimentos, sem duplicidade indevida. O roteiro não estabelece quantas cópias devem ser criadas.

### Resultado obtido
Encontrei apenas a conta **1668**, Pendente, de R$ 10,00, com vencimento em 19/11/2026. Não encontrei outro registro com o título QA_GUILHERME_CT08 no período consultado. A tela não ofereceu campos para definir quantidade ou intervalo entre vencimentos.

Observei o comportamento em um único salvamento. Ainda preciso confirmar a regra exata da opção Criar Cópias antes de concluir a causa da falha.

### Evidência
[Gravação do C11-CT08 no Jam](https://jam.dev/c/f5e5018b-88c8-4f21-bd5c-1fc564ea9746)

### Reteste
Pendente após esclarecer a regra de cópias. Usar uma nova conta de teste para não alterar o registro 1668.

---

## BUG-GUILHERME-004 — Bandeira e parcelas sem opções no recebimento por cartão

**Caso relacionado:** C11-CT09 — preparação  
**Data do registro:** 19/11/2026  
**Responsável:** Guilherme  
**Severidade sugerida:** A definir — preciso confirmar se há bandeiras disponíveis para este tipo de pagamento.  
**Status:** Em análise  
**Inspeção:** Realizada pelo Codex com Chrome DevTools MCP, sem salvar o recebimento.

### Pré-condições
Criei a conta de teste **1669 — QA_GUILHERME_CT09** para o cliente 419. Ela está Pendente, com R$ 50,00 a receber.

### Passos para reproduzir
1. Abri Efetuar Recebimento na conta 1669.
2. Selecionei Cartão de Crédito e o local Teste.
3. Conferi o seletor Escolher Bandeira e o campo Parcelas.
4. Alternei para Dinheiro e selecionei Cartão de Crédito novamente.

### Resultado esperado
Se o recebimento por cartão estiver disponível, espero conseguir escolher uma bandeira e as parcelas aplicáveis, ou receber uma explicação clara caso falte alguma configuração.

### Resultado obtido
O seletor de Bandeira e o campo Parcelas continuaram sem opções após a nova seleção de Cartão de Crédito. O valor de R$ 50,00 e o local Teste já estavam informados. Não encontrei na tela uma indicação de outro campo anterior obrigatório que liberasse essas opções.

Não confirmei nenhum recebimento por cartão. Ainda preciso verificar se a ausência decorre de configuração ou de falha no formulário.

### Evidência
Inspeção de preparação pelo Chrome DevTools MCP, antes da gravação do recebimento Manual SIFIT Pix. O vídeo desse recebimento não demonstra a tentativa por cartão.

### Reteste
Pendente após confirmar quais bandeiras deveriam estar disponíveis. A conta 1669 já foi recebida; usar outra conta de teste para validar o cartão.

---

## BUG-GUILHERME-005 — Consulta não confirma o local Teste após o recebimento

**Caso relacionado:** C11-CT09  
**Data do registro:** 19/11/2026  
**Responsável:** Guilherme  
**Severidade sugerida:** Média — não consigo confirmar na consulta o local escolhido para o recebimento.  
**Status:** Em análise  
**Execução:** Automatizada pelo Codex com Chrome DevTools MCP.

### Pré-condições
Usei a conta de teste **1669 — QA_GUILHERME_CT09**, Pendente e com R$ 50,00 a receber.

### Passos para reproduzir
1. Abri Efetuar Recebimento na conta 1669.
2. Mantive Valor Recebido em R$ 50,00, selecionei Manual SIFIT Pix e o local Teste.
3. Salvei uma única vez e confirmei o aviso sobre a data do caixa.
4. Consultei a conta novamente e conferi os dados do recebimento.

### Resultado esperado
Eu esperava ver o local **Teste** na consulta, junto com o valor e o tipo de pagamento salvos.

### Resultado obtido
O valor de R$ 50,00 e o tipo Manual SIFIT Pix apareceram na consulta, mas o campo Local de Recebimento mostrou **“entrada”**. Ao abrir a edição, o seletor de local não mostrava uma opção selecionada. Não determinei se o local foi salvo incorretamente ou se a tela o exibe de forma errada.

Não repeti o recebimento na conta 1669.

### Evidência
[Gravação do C11-CT09 no Jam](https://jam.dev/c/d69137fc-dbfd-474b-8b77-040852b7fb49)

### Reteste
Pendente após investigação. Usar outra conta de teste para não alterar o recebimento já registrado na conta 1669.

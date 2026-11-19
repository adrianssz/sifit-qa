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
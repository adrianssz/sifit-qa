# C07 — SifitBox — Aulas — Victor

**Responsável:** Victor  
**Estado:** roteiros iniciais; todos Não executados.  
**Fonte:** [Inventário](../../Invent%C3%A1rio.md), blob `d3885feed1a1909bc57ee56f4041b18facb5b813`.  
**Requisito:** [RF07](../contribuicoes/victor/requisitos.md).  
**Registros:** [resultados](../contribuicoes/victor/resultados.md) e [bugs](../contribuicoes/victor/bugs.md).

## Preparação e julgamento

Vou usar uma sessão autorizada no ambiente de referência https://sifit.centrion.com.br/login, unidade identificada e dados próprios QA_VICTOR. Registrar códigos reais, data de preparação e estado inicial. As dependências e regras pendentes constam no [planejamento](../contribuicoes/victor/planejamento.md). Ainda preciso conferir os controles na tela antes das gravações.

Antes da gravação, vou reconhecer a tela e completar os campos/limites/ações ainda desconhecidos. Preservar os IDs e descrições abaixo. Cada variação recebe sufixo A/B/C e evidência própria ou intervalo no vídeo. Não aprovar o caso principal com variações pendentes. Critérios do inventário são propostos; confirmar regras necessárias antes de reprovar. Falta de regra ou acesso exige registro de pendência/bloqueio concreto, sem bug confirmado automático.

Gravar também sucessos. Não mostrar credenciais, tokens, conexões ou dados reais de terceiros. Nas ações de exclusão usar somente descartáveis próprios e cumprir a confirmação aplicável no momento da execução. Importações/geração devem ter efeito delimitado.

## C07-CT01 — Consultar aulas por período

| Campo | Conteúdo |
|---|---|
| ID | C07-CT01 |
| Descrição original | Consultar aulas por período |
| Tipo original | Filtro |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF07 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C07_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Buscar intervalo com aula própria conhecida e outro sem aulas; comparar dias e vigência. |
| ENTÃO — critério original | Listar somente aulas do intervalo, com mensagem clara quando vazio. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G15, G16, G17 e G18 se o controle existir; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C07-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |

## C07-CT02 — Período inválido

| Campo | Conteúdo |
|---|---|
| ID | C07-CT02 |
| Descrição original | Período inválido |
| Tipo original | Negativo |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF07 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C07_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Buscar com datas invertidas e uma extremidade ausente, em variações separadas. |
| ENTÃO — critério original | Rejeitar datas invertidas ou incompletas. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G02, G03, G05, G06 e G08 conforme campo/regra confirmados; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C07-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |

## C07-CT03 — Gerar aulas de turma recorrente

| Campo | Conteúdo |
|---|---|
| ID | C07-CT03 |
| Descrição original | Gerar aulas de turma recorrente |
| Tipo original | Condicional |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF07 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C07_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Usar recorrência própria de C20-CT02; anotar dias, horários e vigência; gerar período delimitado e comparar aulas resultantes. |
| ENTÃO — critério original | Criar as aulas conforme dias, horários e vigência configurados. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G01, G10, G11, G12 e G13 conforme ações disponíveis; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C07-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |

## C07-CT04 — Gerar novamente o mesmo período

| Campo | Conteúdo |
|---|---|
| ID | C07-CT04 |
| Descrição original | Gerar novamente o mesmo período |
| Tipo original | Negativo |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF07 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C07_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Anotar IDs e contagem das aulas de C07-CT03; gerar novamente o mesmo período da mesma recorrência; comparar duplicidade. |
| ENTÃO — critério original | Verificar prevenção de aulas duplicadas. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G02, G03, G05, G06 e G08 conforme campo/regra confirmados; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C07-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |

## C07-CT05 — Detalhar aula gerada

| Campo | Conteúdo |
|---|---|
| ID | C07-CT05 |
| Descrição original | Detalhar aula gerada |
| Tipo original | Dependência |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF07 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C07_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Abrir detalhe de aula QA_VICTOR gerada; registrar campos, participantes, vagas e ações visíveis; complementar roteiro antes de testar ações. |
| ENTÃO — critério original | Mapear participantes, vagas e ações que surgirem após existir aula de teste. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G01, G10, G11, G12 e G13 conforme ações disponíveis; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C07-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |

## C07-CT06 — Reserva, cancelamento e lotação, se disponíveis

| Campo | Conteúdo |
|---|---|
| ID | C07-CT06 |
| Descrição original | Reserva, cancelamento e lotação, se disponíveis |
| Tipo original | Dependência |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF07 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C07_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Após C07-CT05, confirmar ações de reserva/cancelamento e regra de lotação; criar variações para reservar, cancelar e atingir limite somente com alunos controlados. |
| ENTÃO — critério original | Verificar regras de inscrição e vagas; expandir em casos após abrir aula. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G01, G10, G11, G12 e G13 conforme ações disponíveis; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C07-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |


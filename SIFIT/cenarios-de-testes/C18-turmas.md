# C18 — Turmas — Meus testes

**Responsável:** Victor  
**Estado:** C18-CT01 e C18-CT02 executados parcialmente, com julgamento pendente; demais casos não executados.  
**Fonte:** [Inventário](../../Invent%C3%A1rio.md), blob `d3885feed1a1909bc57ee56f4041b18facb5b813`.  
**Requisito:** [RF18](../contribuicoes/victor/requisitos.md).  
**Registros:** [resultados](../contribuicoes/victor/resultados.md) e [bugs](../contribuicoes/victor/bugs.md).

## Preparação e julgamento

Operei a interface com automação assistida nesta sessão autenticada como Jair, em https://sifit.centrion.com.br/turmas. Não confirmei a unidade. Pesquisei QA_VICTOR; a consulta retornou nenhuma turma. Abri o formulário para reconhecer os campos e cancelei sem salvar. Ainda preciso de um plano de teste próprio e da unidade identificada para concluir um cadastro válido.

Antes da gravação, vou reconhecer a tela e completar os campos/limites/ações ainda desconhecidos. Preservar os IDs e descrições abaixo. Cada variação recebe sufixo A/B/C e evidência própria ou intervalo no vídeo. Não aprovar o caso principal com variações pendentes. Critérios do inventário são propostos; confirmar regras necessárias antes de reprovar. Falta de regra ou acesso exige registro de pendência/bloqueio concreto, sem bug confirmado automático.

Gravar também sucessos. Não mostrar credenciais, tokens, conexões ou dados reais de terceiros. Nas ações de exclusão usar somente descartáveis próprios e cumprir a confirmação aplicável no momento da execução. Importações/geração devem ter efeito delimitado.

## C18-CT01 — Cadastrar turma válida

| Campo | Conteúdo |
|---|---|
| ID | C18-CT01 |
| Descrição original | Cadastrar turma válida |
| Tipo original | Positivo |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF18 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | Pesquisa QA_VICTOR na listagem, sem resultados; nenhum dado de turma foi criado. Não havia plano próprio confirmado. |
| DADO | Que a listagem de Turmas está acessível e a busca QA_VICTOR não encontrou registros. A unidade não foi confirmada. |
| QUANDO — roteiro | Abri Cadastrar Turma, observei os campos e cancelei sem salvar, pois não havia plano QA_VICTOR confirmado. |
| ENTÃO — critério original | Gravar nome, plano, dias, horários e demais opções. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G01, G10, G11, G12 e G13 conforme ações disponíveis; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C18-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | O formulário exibiu Nome, Status, Plano, Aula Experimental, Tempo (meses), Hora Inicial, Hora Final, Tem Personal e Dias da Semana. Cancelei sem salvar; não encontrei dados QA_VICTOR e não confirmei um plano próprio. |
| Status | Execução parcial; julgamento pendente até obter plano próprio e confirmar a unidade. |
| Data/hora e fuso | 19/11/2026, aproximadamente 03:46 (America/Sao_Paulo). |
| Executor real | Operei a interface com automação assistida nesta sessão autenticada como Jair. |
| Ambiente | https://sifit.centrion.com.br/turmas; unidade não confirmada; versão do SIFIT não exposta; Chrome 157.0.8103.78, Windows 11 (x86). |
| Vídeo e tempos | [Jam exclusivo C18-CT01, 24 s](https://jam.dev/c/490a7c3d-2968-4d35-923a-657cc36b3cb1?s=mcp); gravação de tela sem logs. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Critério original do inventário. A unidade não foi identificada e não encontrei turma nem plano QA_VICTOR; preciso confirmar referência própria para testar o cadastro válido. Não abri bug. |

## C18-CT02 — Nome, plano e dias ausentes

| Campo | Conteúdo |
|---|---|
| ID | C18-CT02 |
| Descrição original | Nome, plano e dias ausentes |
| Tipo original | Negativo |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF18 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | Pesquisei QA_VICTOR; a listagem não encontrou turmas. Não preenchi dados nem criei registros. |
| DADO | Que a listagem de Turmas está acessível e a busca QA_VICTOR não encontrou registros. |
| QUANDO — roteiro | Tentei salvar o formulário totalmente vazio. Depois do aviso, fechei a mensagem e cancelei sem salvar. Não executei separadamente plano e dias ausentes. |
| ENTÃO — critério original | Validar regras obrigatórias confirmadas. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G02, G03, G05, G06 e G08 conforme campo/regra confirmados; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C18-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ao salvar sem preencher, a tela exibiu “Informe o nome da turma.” Fechei o aviso e cancelei; a contagem da listagem continuou em 12 e não encontrei QA_VICTOR. Verifiquei apenas a variação sem nome; as variações sem plano e sem dias continuam pendentes porque não havia plano próprio confirmado. |
| Status | Execução parcial; julgamento pendente até executar as variações sem plano e sem dias com dados de teste próprios. |
| Data/hora e fuso | 19/11/2026, aproximadamente 03:52 (America/Sao_Paulo). |
| Executor real | Operei a interface com automação assistida nesta sessão autenticada como Jair. |
| Ambiente | https://sifit.centrion.com.br/turmas; unidade não confirmada; versão do SIFIT não exposta; Chrome 157.0.8103.78, Windows 11 (x86). |
| Vídeo e tempos | [Jam exclusivo C18-CT02, 23 s](https://jam.dev/c/3ff04937-9bdb-48ac-be36-1bb1e01ca710?s=mcp); gravação de tela sem logs. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Critério original do inventário. A mensagem observada foi “Informe o nome da turma.”; ainda preciso testar as variações de plano e dias ausentes e confirmar a unidade. Não abri bug. |

## C18-CT03 — Horário final igual ou anterior ao inicial

| Campo | Conteúdo |
|---|---|
| ID | C18-CT03 |
| Descrição original | Horário final igual ou anterior ao inicial |
| Tipo original | Limite |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF18 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C18_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Testar fim igual ao início e fim anterior ao início, separadamente; comparar com política confirmada de duração/passagem de dia. |
| ENTÃO — critério original | Aplicar regra de duração e eventual passagem de dia. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G02, G03, G05, G06 e G08 conforme campo/regra confirmados; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C18-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |

## C18-CT04 — Tempo em meses inválido

| Campo | Conteúdo |
|---|---|
| ID | C18-CT04 |
| Descrição original | Tempo em meses inválido |
| Tipo original | Limite |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF18 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C18_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Testar meses zero, negativo, texto e acima do máximo confirmado; separar variações e registrar validação. |
| ENTÃO — critério original | Tratar zero, negativos, texto e valores além do limite. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G02, G03, G05, G06 e G08 conforme campo/regra confirmados; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C18-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |

## C18-CT05 — Selecionar vários dias

| Campo | Conteúdo |
|---|---|
| ID | C18-CT05 |
| Descrição original | Selecionar vários dias |
| Tipo original | Interação |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF18 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C18_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Selecionar múltiplos dias, salvar e reabrir; comparar exatamente os dias marcados. |
| ENTÃO — critério original | Preservar exatamente os dias escolhidos. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G01, G10, G11, G12 e G13 conforme ações disponíveis; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C18-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |

## C18-CT06 — Aula experimental e Tem Personal

| Campo | Conteúdo |
|---|---|
| ID | C18-CT06 |
| Descrição original | Aula experimental e Tem Personal |
| Tipo original | Interação |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF18 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C18_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Alternar Aula experimental e Tem Personal, isoladas e combinadas; conferir campos habilitados e valores persistidos. |
| ENTÃO — critério original | Conferir campos condicionais e efeito das opções. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G01, G10, G11, G12 e G13 conforme ações disponíveis; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C18-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |

## C18-CT07 — Status ativo/inativo e filtros

| Campo | Conteúdo |
|---|---|
| ID | C18-CT07 |
| Descrição original | Status ativo/inativo e filtros |
| Tipo original | Positivo |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF18 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C18_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Alterar status da turma própria, salvar e consultar filtros ativo/inativo; verificar disponibilidade conforme regra. |
| ENTÃO — critério original | Conferir disponibilidade e listagem após mudança. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G01, G10, G11, G12 e G13 conforme ações disponíveis; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C18-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |

## C18-CT08 — Conflito de turma/horário

| Campo | Conteúdo |
|---|---|
| ID | C18-CT08 |
| Descrição original | Conflito de turma/horário |
| Tipo original | Regra a confirmar |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF18 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C18_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Preparar duas turmas próprias com professor/horário em sobreposição; confirmar política e tentar cadastro controlado. |
| ENTÃO — critério original | Confirmar regra para sobreposição e professor. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G02, G03, G05, G06 e G08 conforme campo/regra confirmados; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C18-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |

## C18-CT09 — Cancelar, editar e excluir

| Campo | Conteúdo |
|---|---|
| ID | C18-CT09 |
| Descrição original | Cancelar, editar e excluir |
| Tipo original | Condicional |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF18 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C18_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Usar turma descartável própria; cancelar edição e conferir preservação; editar e reabrir; testar cancelamento de exclusão e exclusão somente com política e vínculos conhecidos. |
| ENTÃO — critério original | Conferir persistência e vínculos com matrículas/aulas. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G01, G10, G11, G12 e G13 conforme ações disponíveis; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C18-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |


# C14 — Exercícios — Meus testes

**Responsável:** Victor  
**Estado:** C14-CT01 e C14-CT05 investigados parcialmente, com julgamento pendente; demais casos não executados.  
**Fonte:** [Inventário](../../Invent%C3%A1rio.md), blob `d3885feed1a1909bc57ee56f4041b18facb5b813`.  
**Requisito:** [RF14](../contribuicoes/victor/requisitos.md).  
**Registros:** [resultados](../contribuicoes/victor/resultados.md) e [bugs](../contribuicoes/victor/bugs.md).

## Preparação e julgamento

Usei a sessão disponível no ambiente de referência https://sifit.centrion.com.br/. Não confirmei a unidade; não criei, editei ou excluí exercícios nesta investigação. As dependências e regras pendentes constam no [planejamento](../contribuicoes/victor/planejamento.md). Já reconheci a biblioteca; C14-CT01 foi registrado como investigação parcial e gravei o carregamento separadamente.

Antes da gravação, vou reconhecer a tela e completar os campos/limites/ações ainda desconhecidos. Preservar os IDs e descrições abaixo. Cada variação recebe sufixo A/B/C e evidência própria ou intervalo no vídeo. Não aprovar o caso principal com variações pendentes. Critérios do inventário são propostos; confirmar regras necessárias antes de reprovar. Falta de regra ou acesso exige registro de pendência/bloqueio concreto, sem bug confirmado automático.

Gravar também sucessos. Não mostrar credenciais, tokens, conexões ou dados reais de terceiros. Nas ações de exclusão usar somente descartáveis próprios e cumprir a confirmação aplicável no momento da execução. Importações/geração devem ter efeito delimitado.

## C14-CT01 — Carregamento da biblioteca

| Campo | Conteúdo |
|---|---|
| ID | C14-CT01 |
| Descrição original | Carregamento da biblioteca |
| Tipo original | Investigação |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF14 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | Não criei, editei ou excluí dados. Observei a biblioteca existente, que exibiu 11 exercícios em 4 grupos. |
| DADO | Que a página https://sifit.centrion.com.br/exercicios estava acessível na sessão autenticada exibida como Jair. |
| QUANDO — roteiro | Abri a biblioteca de exercícios, aguardei o carregamento e recarreguei a página uma vez; conferi a contagem apresentada. |
| ENTÃO — critério original | Distinguir biblioteca vazia de falha no servidor; reproduzir erro observado. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G21; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C14-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | A biblioteca carregou 11 exercícios distribuídos em 4 grupos; após recarregar, a mesma contagem apareceu. Não observei erro de servidor nem mensagem de falha nesta execução. O inventário informa que havia um erro de servidor na inspeção-base, mas não consegui reproduzi-lo nesta sessão; por isso, a investigação não está concluída. |
| Status | Investigação parcial; julgamento pendente |
| Data/hora e fuso | 19/11/2026, aproximadamente 03:20–03:22 (America/Sao_Paulo), conforme Jam criado às 06:20 UTC. |
| Executor real | Operei a interface com automação do assistente Codex, na sessão autenticada exibida como Jair. |
| Ambiente | https://sifit.centrion.com.br/exercicios; unidade e versão não identificadas; Chrome 157.0.8103.78, Windows 11 (x86), conforme sessão/Jam. |
| Vídeo e tempos | [Jam C14-CT01](https://jam.dev/c/4ee24160-d9b3-465d-b283-2b3dc4f2ae8f?s=mcp), 24 s; mostra o carregamento/recarregamento da biblioteca. Captura de tela, sem logs de console/rede. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | O critério do inventário é distinguir biblioteca vazia de falha e reproduzir o erro observado na inspeção-base. Nesta execução a biblioteca carregou, então não pude reproduzir nem caracterizar aquele erro. Mantenho a investigação parcial; isso não confirma bug nem correção definitiva. |

## C14-CT02 — Importar biblioteca padrão

| Campo | Conteúdo |
|---|---|
| ID | C14-CT02 |
| Descrição original | Importar biblioteca padrão |
| Tipo original | Condicional |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF14 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C14_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Confirmar escopo autorizado de importação e contagens iniciais; importar biblioteca padrão apenas no conjunto delimitado; comparar grupos/exercícios criados. |
| ENTÃO — critério original | Conferir grupos e exercícios criados em conjunto de teste autorizado. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G01, G10, G11, G12 e G13 conforme ações disponíveis; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C14-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |

## C14-CT03 — Repetir importação

| Campo | Conteúdo |
|---|---|
| ID | C14-CT03 |
| Descrição original | Repetir importação |
| Tipo original | Condicional |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF14 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C14_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | No mesmo conjunto autorizado de C14-CT02, repetir importação; comparar IDs e contagens para identificar duplicidade. |
| ENTÃO — critério original | Verificar prevenção de duplicação de biblioteca. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G01, G10, G11, G12 e G13 conforme ações disponíveis; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C14-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |

## C14-CT04 — Cadastro manual

| Campo | Conteúdo |
|---|---|
| ID | C14-CT04 |
| Descrição original | Cadastro manual |
| Tipo original | Dependência |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF14 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C14_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Abrir caminho de cadastro manual e grupos musculares; mapear campos reais de exercício; complementar roteiro com referência própria antes de salvar. |
| ENTÃO — critério original | Abrir o caminho para grupos musculares e mapear cadastro de exercício quando disponível. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G01, G10, G11, G12 e G13 conforme ações disponíveis; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C14-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |

## C14-CT05 — Pesquisa, filtros e visualização de exercícios

| Campo | Conteúdo |
|---|---|
| ID | C14-CT05 |
| Descrição original | Pesquisa, filtros e visualização de exercícios |
| Tipo original | Dependência |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF14 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | A biblioteca exibiu 11 exercícios em 4 grupos. Consultei a visualização do exercício AA (código 11) somente para leitura e fechei sem salvar. |
| DADO | Que a página de Exercícios estava acessível e a biblioteca mostrava 11 exercícios em 4 grupos; não vi campos gerais de pesquisa ou filtros. |
| QUANDO — roteiro | Conferi a listagem visível e abri a visualização de AA (código 11); observei os campos do formulário e fechei por Cancelar, sem salvar. Pesquisa/filtro e busca de termo inexistente ficaram sem executar por falta de controles gerais visíveis. |
| ENTÃO — critério original | Detalhar os controles que aparecerem com biblioteca carregada. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G01, G10, G11, G12 e G13 conforme ações disponíveis; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C14-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | A tela não apresentou campo geral de pesquisa ou filtro. A ação de visualização abriu o formulário do exercício AA (código 11), com Nome e opções de imagem/vídeo; a seção de vídeo mostrou “Não foi possível abrir a mídia”. Fechei por Cancelar sem alterar o registro. |
| Status | Execução parcial; julgamento pendente: pesquisa e filtros não disponíveis na tela observada; validação da visualização depende de regra/esperado confirmado. |
| Data/hora e fuso | 19/11/2026, aproximadamente 03:34 (America/Sao_Paulo). |
| Executor real | Operei a interface com automação assistida nesta sessão autenticada como Jair. |
| Ambiente | https://sifit.centrion.com.br/exercicios; unidade não confirmada; versão do SIFIT não exposta; Chrome 157.0.8103.78, Windows 11 (x86). |
| Vídeo e tempos | [Jam exclusivo C14-CT05, 31 s](https://jam.dev/c/0010fdc5-489a-42a1-82eb-1a9bd38dd537?s=mcp); captura de tela, sem logs de console/rede. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | O critério do inventário pede detalhar os controles disponíveis. Não observei pesquisa/filtros gerais. A mídia de vídeo não abriu, mas não há critério confirmado sobre mídia nem modelo conhecido para verificar o conteúdo esperado; mantenho a execução parcial e não abri bug. |

## C14-CT06 — Associar exercício à ficha

| Campo | Conteúdo |
|---|---|
| ID | C14-CT06 |
| Descrição original | Associar exercício à ficha |
| Tipo original | Dependência |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF14 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C14_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Associar exercício próprio a ficha QA_VICTOR; salvar e reabrir; comparar vínculo e conteúdo da biblioteca original. |
| ENTÃO — critério original | Conferir vínculo e preservação da biblioteca de origem. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G01, G10, G11, G12 e G13 conforme ações disponíveis; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C14-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |


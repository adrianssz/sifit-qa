# C45 — Modelos de Ficha — Meus testes

**Responsável:** Victor  
**Estado:** C45-CT01 e C45-CT02 executados parcialmente, com julgamento pendente; demais casos não executados.  
**Fonte:** [Inventário](../../Invent%C3%A1rio.md), blob `d3885feed1a1909bc57ee56f4041b18facb5b813`.  
**Requisito:** [RF45](../contribuicoes/victor/requisitos.md).  
**Registros:** [resultados](../contribuicoes/victor/resultados.md) e [bugs](../contribuicoes/victor/bugs.md).

## Preparação e julgamento

Na consulta realizada, os filtros disponíveis eram Código, Título e Criador. Os indicadores exibiram 0 modelos, 0 criadores, 0 listados e 0 sem criador. Como não encontrei modelo próprio, mantive C45-CT01 parcial; a listagem vazia, sozinha, não confirma defeito.

Usei a sessão disponível no ambiente de referência https://sifit.centrion.com.br/. Não confirmei a unidade; consultei somente a tela e usei termos de busca QA_VICTOR, sem criar ou alterar registros. As dependências e regras pendentes constam no [planejamento](../contribuicoes/victor/planejamento.md). Ainda preciso conferir os controles na tela antes das gravações.

Antes da gravação, vou reconhecer a tela e completar os campos/limites/ações ainda desconhecidos. Preservar os IDs e descrições abaixo. Cada variação recebe sufixo A/B/C e evidência própria ou intervalo no vídeo. Não aprovar o caso principal com variações pendentes. Critérios do inventário são propostos; confirmar regras necessárias antes de reprovar. Falta de regra ou acesso exige registro de pendência/bloqueio concreto, sem bug confirmado automático.

Gravar também sucessos. Não mostrar credenciais, tokens, conexões ou dados reais de terceiros. Nas ações de exclusão usar somente descartáveis próprios e cumprir a confirmação aplicável no momento da execução. Importações/geração devem ter efeito delimitado.

## C45-CT01 — Buscar código, título e criador

| Campo | Conteúdo |
|---|---|
| ID | C45-CT01 |
| Descrição original | Buscar código, título e criador |
| Tipo original | Filtro |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF45 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C45_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Buscar modelo próprio por código, título e criador separadamente; testar termo inexistente e limpar. |
| ENTÃO — critério original | Exibir somente modelos correspondentes. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G15, G16, G17 e G18 se o controle existir; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C45-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Consultei separadamente código `QA_VICTOR_CODIGO_INEXISTENTE`, título `QA_VICTOR_TITULO_INEXISTENTE` e criador `QA_VICTOR`. Em cada busca, a tela exibiu “Nenhum modelo de ficha encontrado” e 0 registros, sem erro visível. Não encontrei modelo próprio para confirmar correspondência positiva. |
| Status | Parcial; julgamento pendente por ausência de modelo próprio para validar correspondência positiva. |
| Data/hora e fuso | 19/11/2026, aproximadamente 03:23–03:26 (America/Sao_Paulo). |
| Executor real | Operei a interface com automação assistida nesta sessão autenticada como Jair. |
| Ambiente | `https://sifit.centrion.com.br/fichas-treino-modelo`; unidade não confirmada; versão do SIFIT não exposta; Chrome 157.0.8103.78 em Windows 11 x86, conforme ambiente do navegador. |
| Vídeo e tempos | Não produzido: o Jam não iniciou captura utilizável nesta tentativa; sem link para registrar. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Critério original do inventário. Resultado inconclusivo para correspondência positiva porque não localizei modelo próprio; confirmar se há cadastro QA_VICTOR ou dados autorizados para completar. Não abri bug. |

## C45-CT02 — Abrir criação e mapear editor

| Campo | Conteúdo |
|---|---|
| ID | C45-CT02 |
| Descrição original | Abrir criação e mapear editor |
| Tipo original | Dependência |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF45 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | A listagem inicial apresentava 0 modelos. Abri o formulário vazio e não preenchi dados nem criei registros. |
| DADO | Que a tela Modelos de Ficha estava acessível e exibia 0 modelos; a unidade não foi confirmada. |
| QUANDO — roteiro | Abri Novo Modelo de Ficha, observei os campos e ações exibidos e cliquei Cancelar sem salvar. |
| ENTÃO — critério original | Identificar campos e controles efetivos antes do roteiro. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G01, G10, G11, G12 e G13 conforme ações disponíveis; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C45-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | O formulário Novo Modelo de Ficha mostrou Nome do Modelo, seleção de Personal, Cancelar e Criar Modelo. Cancelei sem preencher; a listagem voltou a 0 modelos. O editor completo e campos/limites seguintes não foram alcançados. |
| Status | Execução parcial; julgamento pendente até mapear o editor após um modelo QA_VICTOR. |
| Data/hora e fuso | 19/11/2026, aproximadamente 03:39 (America/Sao_Paulo). |
| Executor real | Operei a interface com automação assistida nesta sessão autenticada como Jair. |
| Ambiente | https://sifit.centrion.com.br/fichas-treino-modelo; unidade não confirmada; versão do SIFIT não exposta; Chrome 157.0.8103.78, Windows 11 (x86). |
| Vídeo e tempos | [Jam exclusivo C45-CT02, 35 s](https://jam.dev/c/3afaed3e-9de5-4403-a212-b15a2751ed2c?s=mcp); captura de tela, sem logs de console/rede. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Critério do inventário: identificar os campos e controles efetivos. Mapeei apenas a primeira tela; para abrir o editor posterior é necessário existir um modelo próprio. Não confirmei obrigatoriedade de Nome ou Personal e não classifiquei ausência de dados como bug. |

## C45-CT03 — Título vazio e modelo sem exercícios

| Campo | Conteúdo |
|---|---|
| ID | C45-CT03 |
| Descrição original | Título vazio e modelo sem exercícios |
| Tipo original | Dependência |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF45 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C45_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Após mapear editor, tentar título vazio e modelo sem exercícios em variações distintas; comparar com regra confirmada. |
| ENTÃO — critério original | Conferir regras obrigatórias após acesso ao editor. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G01, G10, G11, G12 e G13 conforme ações disponíveis; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C45-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |

## C45-CT04 — Editar, duplicar ou excluir, se disponíveis

| Campo | Conteúdo |
|---|---|
| ID | C45-CT04 |
| Descrição original | Editar, duplicar ou excluir, se disponíveis |
| Tipo original | Dependência |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF45 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C45_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Mapear ações de editar/duplicar/excluir; usar modelos descartáveis próprios e um vinculado; expandir variações antes de executar, respeitando política de preservação. |
| ENTÃO — critério original | Mapear ações e preservar modelos vinculados. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G01, G10, G11, G12 e G13 conforme ações disponíveis; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C45-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |

## C45-CT05 — Usar modelo em ficha de aluno

| Campo | Conteúdo |
|---|---|
| ID | C45-CT05 |
| Descrição original | Usar modelo em ficha de aluno |
| Tipo original | Integração |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF45 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C45_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Aplicar modelo QA_VICTOR em ficha do aluno controlado; comparar conteúdo e vínculos e reabrir modelo original para conferir preservação. |
| ENTÃO — critério original | Copiar conteúdo sem modificar o original e manter vínculos corretos. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G13, G20 e G24 conforme vínculos acessíveis; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C45-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |

## C45-CT06 — Conferir indicadores

| Campo | Conteúdo |
|---|---|
| ID | C45-CT06 |
| Descrição original | Conferir indicadores |
| Tipo original | Consistência |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF45 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C45_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Consultar indicadores de modelos, criadores, listados e sem criador; comparar com base acessível e período/filtros iguais; não inferir total global a partir de amostra. |
| ENTÃO — critério original | Validar modelos, criadores, listados e sem criador. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G13, G20 e G24 conforme vínculos acessíveis; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C45-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |


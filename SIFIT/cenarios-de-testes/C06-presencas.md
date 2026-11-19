# C06 — Presenças — Meus testes

**Responsável:** Victor; **Estado:** roteiros iniciais; C06-CT05 parcialmente executado, demais casos não executados.  
**Fonte:** [Inventário](../../Invent%C3%A1rio.md), blob `d3885feed1a1909bc57ee56f4041b18facb5b813`.  
**Requisito:** [RF06](../contribuicoes/victor/requisitos.md).  
**Registros:** [resultados](../contribuicoes/victor/resultados.md) e [bugs](../contribuicoes/victor/bugs.md).

## Preparação e julgamento

Vou usar uma sessão autorizada no ambiente de referência https://sifit.centrion.com.br/, unidade identificada e dados próprios QA_VICTOR. Registrar códigos reais, data de preparação e estado inicial. As dependências e regras pendentes constam no [planejamento](../contribuicoes/victor/planejamento.md). Ainda preciso conferir os controles na tela antes das gravações.

Antes da gravação, vou reconhecer a tela e completar os campos/limites/ações ainda desconhecidos. Preservar os IDs e descrições abaixo. Cada variação recebe sufixo A/B/C e evidência própria ou intervalo no vídeo. Não aprovar o caso principal com variações pendentes. Critérios do inventário são propostos; confirmar regras necessárias antes de reprovar. Falta de regra ou acesso exige registro de pendência/bloqueio concreto, sem bug confirmado automático.

Gravar também sucessos. Não mostrar credenciais, tokens, conexões ou dados reais de terceiros. Nas ações de exclusão usar somente descartáveis próprios e cumprir a confirmação aplicável no momento da execução. Importações/geração devem ter efeito delimitado.

## C06-CT01 — Busca por cliente existente e inexistente

| Campo | Conteúdo |
|---|---|
| ID | C06-CT01 |
| Descrição original | Busca por cliente existente e inexistente |
| Tipo original | Filtro |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF06 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C06_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Buscar cliente QA_VICTOR com presença conhecida; repetir com cliente inexistente e limpar busca. |
| ENTÃO — critério original | Listar somente presenças correspondentes ou estado vazio. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G15, G16, G17 e G18 se o controle existir; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C06-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |

## C06-CT02 — Atalhos de período

| Campo | Conteúdo |
|---|---|
| ID | C06-CT02 |
| Descrição original | Atalhos de período |
| Tipo original | Filtro |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF06 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C06_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Acionar Hoje, Esta semana e Este mês separadamente; registrar limites preenchidos e comparar registros pelo mesmo fuso. |
| ENTÃO — critério original | Hoje, semana e mês devem preencher o intervalo e buscar corretamente. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G15, G16, G17 e G18 se o controle existir; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C06-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |

## C06-CT03 — Período personalizado

| Campo | Conteúdo |
|---|---|
| ID | C06-CT03 |
| Descrição original | Período personalizado |
| Tipo original | Limite |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF06 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C06_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Definir intervalo com presenças conhecidas nos dois limites e fora deles; buscar e comparar inclusão conforme regra de horário confirmada. |
| ENTÃO — critério original | Incluir registros dos limites inicial e final conforme regra de horário. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G02, G03, G05, G06 e G08 conforme campo/regra confirmados; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C06-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |

## C06-CT04 — Datas vazias, inválidas ou invertidas

| Campo | Conteúdo |
|---|---|
| ID | C06-CT04 |
| Descrição original | Datas vazias, inválidas ou invertidas |
| Tipo original | Negativo |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF06 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C06_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Testar De/Até vazios, datas inválidas quando o controle permitir e início posterior ao fim; registrar validações. |
| ENTÃO — critério original | Orientar correção, sem erro técnico. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G02, G03, G05, G06 e G08 conforme campo/regra confirmados; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C06-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |

## C06-CT05 — Total, alunos distintos, média e dias

| Campo | Conteúdo |
|---|---|
| ID | C06-CT05 |
| Descrição original | Total, alunos distintos, média e dias |
| Tipo original | Consistência |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF06 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C06_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Selecionar período controlado; contar presenças e alunos distintos; calcular média/dias pela definição confirmada; repetir em intervalo sem registros. |
| ENTÃO — critério original | Recalcular indicadores corretamente, inclusive em intervalo sem presenças. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G13, G20 e G24 conforme vínculos acessíveis; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C06-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Em 19/11/2026, consultei 13/11/2026 a 19/11/2026. A tela mostrou Total no período=0, Alunos distintos=0, Média por dia=0 e Dias no período=7, além de “Nenhuma presença encontrada”. Ainda não comparei com um período com presenças; esta execução cobre apenas o intervalo vazio. |
| Status | Execução parcial; julgamento pendente |
| Data/hora e fuso | 19/11/2026, aproximadamente 02:39 (America/Sao_Paulo), conforme horário de criação do Jam. |
| Executor real | Registrei a observação com apoio de automação de interface (Codex), na sessão autenticada exibida como Jair. |
| Ambiente | https://sifit.centrion.com.br/presencas; unidade não identificada; versão do sistema, navegador e SO não observados. |
| Vídeo e tempos | [Captura Jam C06-CT05](https://jam.dev/c/ba6d7c6f-417b-478e-bdb6-42a2243a0f28?s=mcp), duração aproximada de 1min57s. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |

## C06-CT06 — Check-in refletido na consulta

| Campo | Conteúdo |
|---|---|
| ID | C06-CT06 |
| Descrição original | Check-in refletido na consulta |
| Tipo original | Integração |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF06 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C06_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Usar entrada criada em C05-CT04; consultar cliente/período/unidade e comparar código, data e hora com a evidência da entrada. |
| ENTÃO — critério original | Entrada registrada deve aparecer com cliente, unidade, data e hora corretos. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G13, G20 e G24 conforme vínculos acessíveis; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C06-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |


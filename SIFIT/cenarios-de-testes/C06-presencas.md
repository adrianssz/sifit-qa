# C06 — Presenças — Meus testes

**Responsável:** Victor; **Estado:** C06-CT01 executado parcialmente, com julgamento pendente; C06-CT02 executado com julgamento pendente; C06-CT04 executado parcialmente, com julgamento pendente; C06-CT05 parcialmente executado; demais casos não executados.  
**Fonte:** [Inventário](../../Invent%C3%A1rio.md), blob `d3885feed1a1909bc57ee56f4041b18facb5b813`.  
**Requisito:** [RF06](../contribuicoes/victor/requisitos.md).  
**Registros:** [resultados](../contribuicoes/victor/resultados.md) e [bugs](../contribuicoes/victor/bugs.md).

## Preparação e julgamento

Vou usar uma sessão autorizada no ambiente de referência https://sifit.centrion.com.br/, unidade identificada e dados próprios QA_VICTOR. Registrar códigos reais, data de preparação e estado inicial. As dependências e regras pendentes constam no [planejamento](../contribuicoes/victor/planejamento.md). Já reconheci os filtros de período na tela e gravei C06-CT01, C06-CT02 e C06-CT04 separadamente.

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
| Dados | Consultei o texto QA_VICTOR e a busca negativa QA_VICTOR_CLIENTE_INEXISTENTE_999; não criei nem alterei registros. |
| DADO | Que a tela Presenças estava no intervalo 13/11/2026–19/11/2026, sem presenças no estado inicial. |
| QUANDO — roteiro | Busquei QA_VICTOR, depois QA_VICTOR_CLIENTE_INEXISTENTE_999 e, por fim, limpei a busca. |
| ENTÃO — critério original | Listar somente presenças correspondentes ou estado vazio. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G15, G16, G17 e G18 se o controle existir; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C06-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Na consulta semanal de 13/11/2026 a 19/11/2026, QA_VICTOR e QA_VICTOR_CLIENTE_INEXISTENTE_999 exibiram 0 presenças, total 0, alunos distintos 0, média 0 e 7 dias. A busca vazia também permaneceu sem resultados. O filtro foi consultado sem erro técnico visível. Não localizei um cliente com presença conhecida para concluir a variação positiva; portanto, não consigo confirmar a busca por cliente existente nem fechar o julgamento. |
| Status | Execução parcial; julgamento pendente |
| Data/hora e fuso | 19/11/2026, aproximadamente 03:13–03:17 (America/Sao_Paulo), conforme Jam criado às 06:16 UTC. |
| Executor real | Operei a interface com automação do assistente Codex, na sessão autenticada exibida como Jair. |
| Ambiente | https://sifit.centrion.com.br/presencas; unidade e versão não identificadas; Chrome 157.0.8103.78, Windows 11 (x86), conforme sessão/Jam. |
| Vídeo e tempos | [Jam C06-CT01](https://jam.dev/c/9e7c5e4c-0b39-4884-b847-265993fc4194?s=mcp), 28 s; mostra as buscas por QA_VICTOR e cliente inexistente. Captura de tela, sem logs de console/rede. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | O critério original prevê listar presenças correspondentes ou estado vazio. Confirmei estado vazio para as duas buscas, mas não localizei uma presença conhecida para validar correspondência positiva. Julgamento pendente de dados QA_VICTOR elegíveis; sem bug confirmado. |

## C06-CT02 — Atalhos de período

| Campo | Conteúdo |
|---|---|
| ID | C06-CT02 |
| Descrição original | Atalhos de período |
| Tipo original | Filtro |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF06 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | Consultei os atalhos na unidade disponível; não criei nem alterei registros. Nenhum registro de presença foi retornado. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Acionar Hoje, Esta semana e Este mês separadamente; registrar limites preenchidos e comparar registros pelo mesmo fuso. |
| ENTÃO — critério original | Hoje, semana e mês devem preencher o intervalo e buscar corretamente. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G15, G16, G17 e G18 se o controle existir; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C06-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Em 19/11/2026, acionei os três atalhos. Hoje preencheu 19/11/2026–19/11/2026 (1 dia); Esta semana, 13/11/2026–19/11/2026 (7 dias); Este mês, 21/10/2026–19/11/2026 (30 dias). Cada atalho atualizou a consulta sem erro visível; os três intervalos mostraram total 0, alunos distintos 0, média 0 e “Nenhuma presença encontrada”. A tela registrou as datas e buscou automaticamente. A janela de 30 dias não coincide com mês civil; não havia presenças para validar quais registros cada consulta retorna. |
| Status | Executado; julgamento pendente de confirmação da definição de semana/mês |
| Data/hora e fuso | 19/11/2026, aproximadamente 02:55–02:56 (America/Sao_Paulo), conforme envio do Jam. |
| Executor real | Automação de interface operada pelo assistente Codex, na sessão autenticada exibida como Jair. |
| Ambiente | https://sifit.centrion.com.br/presencas; unidade e versão do sistema não identificadas; Chrome 157.0.8103.78, Windows 11 (x86), conforme metadados do Jam. |
| Vídeo e tempos | [Jam C06-CT02](https://jam.dev/c/0ce05096-3bf9-4a13-a149-a57277c6b30c?s=mcp), 59 s; mostra os três atalhos e intervalos. Captura simples de tela, sem logs de console/rede. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | O inventário define preencher o intervalo e buscar, mas não esclarece se semana/mês são períodos civis ou janelas móveis. O mês observado abrange 30 dias. Sem dados de presença, não pude validar os registros retornados. Mantenho o julgamento pendente; sem bug confirmado. |

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
| Pré-condições | Sessão/unidade identificadas; intervalo de datas definido; regras indispensáveis confirmadas antes do julgamento. |
| Dados | Não criei nem alterei registros. Para a variação invertida, usei 21/10/2026 no campo De e 20/10/2026 no campo Até. |
| DADO | Que o módulo Presenças estava acessível e exibia inicialmente o intervalo de 21/10/2026 a 19/11/2026. |
| QUANDO — roteiro | Alterei a data Até pelo seletor de calendário para 20/10/2026, deixando o início em 21/10/2026, e acionei Buscar. Não executei as variações de datas vazias ou inválidas. |
| ENTÃO — critério original | Orientar correção, sem erro técnico. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G02, G03, G05, G06 e G08 conforme campo/regra confirmados; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C06-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Em 19/11/2026, consultei o intervalo invertido (De 21/10/2026; Até 20/10/2026). A tela terminou a consulta e manteve os valores informados; continuou exibindo 0 presenças, 0 alunos distintos, média 0, 1 dia no período e “Nenhuma presença encontrada”, sem mensagem de validação ou erro técnico visível. Não testei campos vazios nem data inválida. |
| Status | Execução parcial; julgamento pendente |
| Data/hora e fuso | 19/11/2026, aproximadamente 03:06–03:10 (America/Sao_Paulo), conforme gravação Jam criada às 06:08 UTC. |
| Executor real | Operação da interface feita por automação do assistente Codex, na sessão autenticada exibida como Jair. |
| Ambiente | https://sifit.centrion.com.br/presencas; unidade e versão do sistema não identificadas; Chrome 157.0.8103.78, Windows 11 (x86), conforme sessão/Jam. |
| Vídeo e tempos | [Jam C06-CT04](https://jam.dev/c/45aa9710-d82d-4882-b33c-0be67a4c2c79?s=mcp), 1min44s; gravação da consulta com intervalo invertido. Captura de tela, sem logs de console/rede. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | O inventário diz “Orientar correção, sem erro técnico”, mas não define a resposta esperada para intervalo invertido. A consulta terminou sem mensagem de validação aparente; faltam as variações vazia e inválida e a confirmação da regra. Não concluo falha nem bug confirmado. |

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


## Print do SIFIT — C06-CT01

Anexei a captura da busca por QA_VICTOR no período de 13/11/2026 a 19/11/2026. A tela exibiu estado vazio; ainda não localizei uma presença conhecida para validar correspondência positiva.

<img width="1920" height="939" alt="clipboard" src="https://github.com/user-attachments/assets/56b022b5-b810-4348-bc0a-93ca2cb7911a" />

# C34 — Atividades — Meus testes

**Responsável:** Victor  
**Estado:** roteiros iniciais; todos Não executados.  
**Fonte:** [Inventário](../../Invent%C3%A1rio.md), blob `d3885feed1a1909bc57ee56f4041b18facb5b813`.  
**Requisito:** [RF34](../contribuicoes/victor/requisitos.md).  
**Registros:** [resultados](../contribuicoes/victor/resultados.md) e [bugs](../contribuicoes/victor/bugs.md).

## Preparação e julgamento

Vou usar uma sessão autorizada no ambiente de referência https://sifitalfa.centrion.com.br, unidade identificada e dados próprios QA_VICTOR. Registrar códigos reais, data de preparação e estado inicial. As dependências e regras pendentes constam no [planejamento](../contribuicoes/victor/planejamento.md). Ainda preciso conferir os controles na tela antes das gravações.

Antes da gravação, vou reconhecer a tela e completar os campos/limites/ações ainda desconhecidos. Preservar os IDs e descrições abaixo. Cada variação recebe sufixo A/B/C e evidência própria ou intervalo no vídeo. Não aprovar o caso principal com variações pendentes. Critérios do inventário são propostos; confirmar regras necessárias antes de reprovar. Falta de regra ou acesso exige registro de pendência/bloqueio concreto, sem bug confirmado automático.

Gravar também sucessos. Não mostrar credenciais, tokens, conexões ou dados reais de terceiros. Nas ações de exclusão usar somente descartáveis próprios e cumprir a confirmação aplicável no momento da execução. Importações/geração devem ter efeito delimitado.

## C34-CT01 — Cadastrar atividade com pontuação

| Campo | Conteúdo |
|---|---|
| ID | C34-CT01 |
| Descrição original | Cadastrar atividade com pontuação |
| Tipo original | Positivo |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF34 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C34_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Cadastrar atividade QA_VICTOR com pontuação válida e descrição fictícia; salvar e reabrir. |
| ENTÃO — critério original | Persistir nome, valor e descrição. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G01, G10, G11, G12 e G13 conforme ações disponíveis; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C34-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |

## C34-CT02 — Atividade sem pontuação

| Campo | Conteúdo |
|---|---|
| ID | C34-CT02 |
| Descrição original | Atividade sem pontuação |
| Tipo original | Regra a confirmar |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF34 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C34_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Confirmar regra para ausência e zero; cadastrar duas atividades próprias distintas nessas condições e comparar indicadores. |
| ENTÃO — critério original | Confirmar se ausência e zero são aceitos e como são contados. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G02, G03, G05, G06 e G08 conforme campo/regra confirmados; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C34-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |

## C34-CT03 — Pontuação negativa, decimal ou texto

| Campo | Conteúdo |
|---|---|
| ID | C34-CT03 |
| Descrição original | Pontuação negativa, decimal ou texto |
| Tipo original | Limite |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF34 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C34_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Informar pontuação negativa, decimal e texto separadamente; comparar com formato/faixa confirmados. |
| ENTÃO — critério original | Aplicar regra numérica confirmada. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G02, G03, G05, G06 e G08 conforme campo/regra confirmados; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C34-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |

## C34-CT04 — Nome vazio e texto longo

| Campo | Conteúdo |
|---|---|
| ID | C34-CT04 |
| Descrição original | Nome vazio e texto longo |
| Tipo original | Negativo |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF34 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C34_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Testar nome vazio, espaços e textos no limite e acima do limite confirmado para nome/descrição; separar variações. |
| ENTÃO — critério original | Validar nome e limite da descrição. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G02, G03, G05, G06 e G08 conforme campo/regra confirmados; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C34-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |

## C34-CT05 — Pesquisar, editar e conferir indicadores

| Campo | Conteúdo |
|---|---|
| ID | C34-CT05 |
| Descrição original | Pesquisar, editar e conferir indicadores |
| Tipo original | Consistência |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF34 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_C34_AAAAMMDD_NNN; substituir pela data real e registrar IDs gerados e valores de cada variação antes da execução. |
| DADO | Que o módulo está acessível e o estado inicial dos registros próprios foi anotado. |
| QUANDO — roteiro | Pesquisar atividade própria; editar pontuação/descrição e reabrir; conferir indicadores com/sem pontuação e descrição conforme definição. |
| ENTÃO — critério original | Conferir com/sem pontuação e com descrição. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G13, G20 e G24 conforme vínculos acessíveis; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C34-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | Ainda não observei; vou preencher após executar. |
| Status | Não executado |
| Data/hora e fuso | Não registrado; preencher na execução. |
| Executor real | Ainda não registrado; vou informar quem operou a interface e eventual assistência utilizada. |
| Ambiente | Registrar URL, unidade, versão do sistema se exposta, navegador/versão e SO reais. |
| Vídeo e tempos | Não produzido. |
| Prints | Não produzidos. |
| Bug associado | Ainda não confirmei nenhum nesta etapa. |
| Fonte da regra / pendências | Confirmar antes do julgamento; registrar fonte e decisão concreta aqui. |


# C34 — Atividades — Meus testes

**Responsável:** Victor  
**Estado:** C34-CT01 e C34-CT02 aprovados; demais casos ainda Não executados.
**Fonte:** [Inventário](../../Invent%C3%A1rio.md), blob `d3885feed1a1909bc57ee56f4041b18facb5b813`.  
**Requisito:** [RF34](../contribuicoes/victor/requisitos.md).  
**Registros:** [resultados](../contribuicoes/victor/resultados.md) e [bugs](../contribuicoes/victor/bugs.md).

## Preparação e julgamento

Vou usar uma sessão autorizada no ambiente de referência https://sifit.centrion.com.br/, unidade identificada e dados próprios QA_VICTOR. Registrar códigos reais, data de preparação e estado inicial. As dependências e regras pendentes constam no [planejamento](../contribuicoes/victor/planejamento.md). Ainda preciso conferir os controles na tela antes das gravações.

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
| Dados | Código gerado: 10; nome: QA_VICTOR_ATIVIDADE_20261119_001; pontuação: 10; descrição: “Registro de teste QA_VICTOR para validar cadastro de atividade com pontuação.” |
| DADO | Que o módulo Atividades estava acessível e havia 6 atividades, 5 com pontuação, 1 sem pontuação e 3 com descrição antes do cadastro. |
| QUANDO — roteiro | Cadastrei a atividade de teste, salvei, pesquisei pelo nome completo e reabri o registro. |
| ENTÃO — critério original | Persistir nome, valor e descrição. |
| Aceitação | O nome, a pontuação e a descrição persistiram após salvar e reabrir o registro. |
| Verificações comuns propostas | G01, G10, G11, G12 e G13 conforme ações disponíveis; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C34-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | O sistema gerou o código 10. A busca pelo nome completo retornou 1 registro com pontuação 10; ao reabrir o detalhe confirmei o nome, o valor e a descrição completos. |
| Status | Aprovado |
| Data/hora e fuso | 18/11/2026, aproximadamente 23:22–23:23 (America/Sao_Paulo). |
| Executor real | O assistente Codex operou a interface sob minha solicitação; eu iniciei a gravação de tela Jam. |
| Ambiente | https://sifit.centrion.com.br/; perfil exibido: Jair; Chrome 158.0.8127.36 em Windows 11. Unidade ativa não confirmada. |
| Vídeo e tempos | [Gravação Jam de 53 s](https://jam.dev/c/fd1150c0-707d-4180-9144-96291e954ee2). Busca em 0:32 (POST buscar-atividades status 200); abertura do detalhe em 0:38 (OPTIONS 204 e POST 200); fechamento em 0:44; gravação encerrada em 0:53. Sem áudio/transcrição (microfone desativado). |
| Prints | Captura da lista filtrada salva localmente como C34-CT01-20261118.jpg; sem link publicado. |
| Bug associado | Nenhum; o resultado observado atendeu ao critério original. |
| Fonte da regra / pendências | Critério original do Inventário. Executei somente o cadastro com uma pontuação positiva e descrição; formatos/limites pertencem aos demais casos C34. |

## C34-CT02 — Atividade sem pontuação

| Campo | Conteúdo |
|---|---|
| ID | C34-CT02 |
| Descrição original | Atividade sem pontuação |
| Tipo original | Regra a confirmar |
| Objetivo | Verificar o critério deste caso com dados próprios e evidência rastreável. |
| Requisito | RF34 |
| Pré-condições | Sessão/unidade identificadas; dados e referências do roteiro abaixo preparados; regras indispensáveis confirmadas. Se depender de editor, mapear os controles antes de concluir o roteiro. |
| Dados | QA_VICTOR_ATIVIDADE_20261119_002 (código 11, pontuação vazia, descrição "QA_VICTOR teste sem pontuacao") e QA_VICTOR_ATIVIDADE_20261119_003 (código 12, pontuação 0, descrição "QA_VICTOR teste pontuacao zero"). |
| DADO | Que o módulo Atividades estava acessível e havia 7 atividades, 6 com pontuação, 1 sem pontuação e 4 com descrição antes dos cadastros. |
| QUANDO — roteiro | Cadastrei duas atividades próprias, uma com pontuação vazia e outra com pontuação 0, salvei, conferi a lista e os indicadores e reabri a atividade com pontuação 0. |
| ENTÃO — critério original | Confirmar se ausência e zero são aceitos e como são contados. |
| Aceitação | Comparar o obtido com o critério acima e com a regra confirmada registrada; verificar todas as variações aplicáveis. Não presumir texto exato de mensagem. |
| Verificações comuns propostas | G02, G03, G05, G06 e G08 conforme campo/regra confirmados; G21 para erro e G23 para teclado/foco/mensagens quando aplicáveis. Identificar aplicação como C34-Gyy-CAMPO e justificar não aplicabilidade. |
| Resultado obtido | O sistema salvou as duas atividades sem exibir aviso. Na lista, as duas aparecem com "-" na coluna de pontuação. Os indicadores finais foram 9 total, 6 com pontuação, 3 sem pontuação e 6 com descrição, então as duas foram contadas como sem pontuação. Ao reabrir a atividade 003, o campo Pontuação mostrou 0. |
| Status | Aprovado |
| Data/hora e fuso | 19/11/2026, aproximadamente 00:15–00:21 (America/Sao_Paulo); gravações Jam criadas às 00:15 e às 00:19. |
| Executor real | Victor operou a interface e iniciou a gravação Jam. O assistente Claude apoiou com o roteiro e a leitura do resultado, sem operar a interface do SIFIT. |
| Ambiente | https://sifit.centrion.com.br/; Chrome (a extensão Jam é do Chrome); versão do navegador, perfil exibido e unidade ativa não conferidos nesta execução. |
| Vídeo e tempos | Duas gravações Jam: [primeira, criada às 00:15](https://jam.dev/c/186f9430-ca1d-49e6-b5c8-87ccf1562132) e [segunda, criada às 00:19](https://jam.dev/c/8d53721f-db47-4ebd-9718-adf69c1e5f05). A segunda é a referência deste resultado. Tempos de cada ação não anotados. Acesso do professor ainda não conferido. |
| Prints | Não produzidos. |
| Bug associado | Nenhum confirmado. A lista e os indicadores tratam a pontuação 0 como "sem pontuação", embora o campo guarde 0; não há regra escrita dizendo como o zero deve ser contado. |
| Fonte da regra / pendências | Critério original do Inventário (confirmar se ausência e zero são aceitos e como são contados), atendido por observação. Pendente confirmar com Adrian ou com o professor se o zero deve contar como "com pontuação". As verificações Gxx de formato e limite ficam para C34-CT03 e C34-CT04. |

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


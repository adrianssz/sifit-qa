# Resultados dos testes — Meus testes

**Estado:** 2 casos aprovados; 13 aguardam julgamento (3 de C34, 4 de C06, 2 de C14, 2 de C45 e 2 de C18); 51 casos não iniciados. Concluí cinco execuções de C34 e iniciei C06-CT01, C06-CT04, C06-CT05, C14-CT01, C14-CT05, C45-CT01, C45-CT02, C18-CT01 e C18-CT02; executei C06-CT02 com julgamento pendente.

Base: 66 casos — 64 dos módulos e 2 de C47 (CT03 e CT04). [Planejamento](planejamento.md).

| Planejados | Não executados | Aprovados | Julgamento pendente | Reprovados | Bloqueados constatados | Não se aplica |
|---:|---:|---:|---:|---:|---:|---:|
| 66 | 51 | 2 | 13 | 0 | 0 | 0 |

Cobertura com julgamento concluído: 2/66 = 3,03%. Aprovação entre julgados: 2/2 = 100%. Concluí C34-CT01 e C34-CT02; C34-CT03, C34-CT04 e C34-CT05 aguardam confirmação de regra. Executei C06-CT02: Hoje retornou 19/11/2026, Esta semana 13/11–19/11 e Este mês 21/10–19/11 (30 dias), sem presenças nos intervalos. O julgamento aguarda definição de períodos civis ou móveis e dados para comparar. C06-CT01 segue parcial: busquei QA_VICTOR e um texto inexistente, ambos sem resultados; falta validar uma presença conhecida. C06-CT04 segue parcial: o intervalo invertido foi consultado sem aviso visível; faltam as variações vazia/inválida e confirmar a regra. C06-CT05 segue parcial, aguardando comparação com período com presenças. Em C14-CT01, a biblioteca carregou, mas não reproduzi o erro documentado na inspeção-base; a investigação permanece pendente. C14-CT05 está parcial: não vi filtros gerais e o detalhe de AA (código 11) mostrou falha ao abrir mídia de vídeo; sem regra confirmada, não abri bug. C45-CT01 também está parcial: consultas por código, título e criador não encontraram registros; falta um modelo próprio para confirmar correspondência positiva. C45-CT02 está parcial: abri Novo Modelo de Ficha, observei Nome do Modelo e Personal, cancelei sem salvar; o editor completo depende de um modelo próprio. [Jam exclusivo, 35 s](https://jam.dev/c/3afaed3e-9de5-4403-a212-b15a2751ed2c?s=mcp). C18-CT01 está parcial: a busca QA_VICTOR não encontrou turma. Mapeei o formulário Cadastrar Turma e cancelei sem salvar por falta de plano próprio confirmado e unidade identificada. C18-CT02 está parcial: salvei o formulário vazio e a tela pediu o nome da turma. Cancelei sem salvar; a lista permaneceu com 12 turmas, sem QA_VICTOR. As validações sem plano e sem dias ainda não foram conferidas. [Jam exclusivo, 24 s](https://jam.dev/c/490a7c3d-2968-4d35-923a-657cc36b3cb1?s=mcp). Outros 51 casos não foram iniciados; C45-CT01, C45-CT02, C14-CT05, C18-CT01 e C18-CT02 foram iniciados parcialmente. Nenhuma pendência foi contada como bug confirmado ou bloqueio constatado.

## Registro por caso

| ID | Descrição original | Status | Evidência / resultado |
|---|---|---|---|
| [C05-CT01](../../cenarios-de-testes/C05-check-in.md) | Buscar por nome, código e plano | Não executado | Não produzido / não observado. |
| [C05-CT02](../../cenarios-de-testes/C05-check-in.md) | Alternar abas de presença | Não executado | Não produzido / não observado. |
| [C05-CT03](../../cenarios-de-testes/C05-check-in.md) | Filtros e seleção de unidade | Não executado | Não produzido / não observado. |
| [C05-CT04](../../cenarios-de-testes/C05-check-in.md) | Check-in manual de cliente elegível | Não executado | Não produzido / não observado. |
| [C05-CT05](../../cenarios-de-testes/C05-check-in.md) | Código vazio, inexistente ou inválido | Não executado | Não produzido / não observado. |
| [C05-CT06](../../cenarios-de-testes/C05-check-in.md) | Check-in repetido | Não executado | Não produzido / não observado. |
| [C05-CT07](../../cenarios-de-testes/C05-check-in.md) | Cliente inativo, sem matrícula ou inadimplente | Não executado | Não produzido / não observado. |
| [C05-CT08](../../cenarios-de-testes/C05-check-in.md) | QR Code | Não executado | Não produzido / não observado. |
| [C05-CT09](../../cenarios-de-testes/C05-check-in.md) | Indicadores e presentes agora | Não executado | Não produzido / não observado. |
| [C06-CT01](../../cenarios-de-testes/C06-presencas.md) | Busca por cliente existente e inexistente | Execução parcial; julgamento pendente | Busquei QA_VICTOR e QA_VICTOR_CLIENTE_INEXISTENTE_999 no período 13/11–19/11/2026; ambos retornaram estado vazio. Não encontrei cliente com presença conhecida para validar a busca positiva. [Jam C06-CT01](https://jam.dev/c/9e7c5e4c-0b39-4884-b847-265993fc4194?s=mcp). |
| [C06-CT02](../../cenarios-de-testes/C06-presencas.md) | Atalhos de período | Julgamento pendente | [Jam C06-CT02](https://jam.dev/c/0ce05096-3bf9-4a13-a149-a57277c6b30c?s=mcp): hoje 19/11; semana 13/11–19/11; mês 21/10–19/11 (30 dias). Os três intervalos exibiram zero presenças. |
| [C06-CT03](../../cenarios-de-testes/C06-presencas.md) | Período personalizado | Não executado | Não produzido / não observado. |
| [C06-CT04](../../cenarios-de-testes/C06-presencas.md) | Datas vazias, inválidas ou invertidas | Execução parcial; julgamento pendente | Consultei De 21/10/2026 e Até 20/10/2026; a tela concluiu a consulta sem mensagem de validação aparente e manteve estado vazio. As variações vazia e inválida não foram executadas; não confirmei bug. [Jam C06-CT04](https://jam.dev/c/45aa9710-d82d-4882-b33c-0be67a4c2c79?s=mcp). |
| [C06-CT05](../../cenarios-de-testes/C06-presencas.md) | Total, alunos distintos, média e dias | Execução parcial; julgamento pendente | Consulta de 13/11 a 19/11/2026: total 0, alunos distintos 0, média 0, dias no período 7; faltou comparar período com presenças. [Jam C06-CT05](https://jam.dev/c/ba6d7c6f-417b-478e-bdb6-42a2243a0f28?s=mcp). |
| [C06-CT06](../../cenarios-de-testes/C06-presencas.md) | Check-in refletido na consulta | Não executado | Não produzido / não observado. |
| [C07-CT01](../../cenarios-de-testes/C07-sifitbox-aulas.md) | Consultar aulas por período | Não executado | Não produzido / não observado. |
| [C07-CT02](../../cenarios-de-testes/C07-sifitbox-aulas.md) | Período inválido | Não executado | Não produzido / não observado. |
| [C07-CT03](../../cenarios-de-testes/C07-sifitbox-aulas.md) | Gerar aulas de turma recorrente | Não executado | Não produzido / não observado. |
| [C07-CT04](../../cenarios-de-testes/C07-sifitbox-aulas.md) | Gerar novamente o mesmo período | Não executado | Não produzido / não observado. |
| [C07-CT05](../../cenarios-de-testes/C07-sifitbox-aulas.md) | Detalhar aula gerada | Não executado | Não produzido / não observado. |
| [C07-CT06](../../cenarios-de-testes/C07-sifitbox-aulas.md) | Reserva, cancelamento e lotação, se disponíveis | Não executado | Não produzido / não observado. |
| [C13-CT01](../../cenarios-de-testes/C13-ficha-de-treino.md) | Criar ficha com aluno, personal e objetivo | Não executado | Não produzido / não observado. |
| [C13-CT02](../../cenarios-de-testes/C13-ficha-de-treino.md) | Aluno ou referência obrigatória ausente | Não executado | Não produzido / não observado. |
| [C13-CT03](../../cenarios-de-testes/C13-ficha-de-treino.md) | Data final anterior à inicial | Não executado | Não produzido / não observado. |
| [C13-CT04](../../cenarios-de-testes/C13-ficha-de-treino.md) | Observação e persistência | Não executado | Não produzido / não observado. |
| [C13-CT05](../../cenarios-de-testes/C13-ficha-de-treino.md) | Usar Modelo de Ficha | Não executado | Não produzido / não observado. |
| [C13-CT06](../../cenarios-de-testes/C13-ficha-de-treino.md) | Editor de exercícios | Não executado | Não produzido / não observado. |
| [C13-CT07](../../cenarios-de-testes/C13-ficha-de-treino.md) | Limites de séries, repetições e cargas | Não executado | Não produzido / não observado. |
| [C13-CT08](../../cenarios-de-testes/C13-ficha-de-treino.md) | Status, vencimento e indicadores | Não executado | Não produzido / não observado. |
| [C13-CT09](../../cenarios-de-testes/C13-ficha-de-treino.md) | Busca e paginação | Não executado | Não produzido / não observado. |
| [C13-CT10](../../cenarios-de-testes/C13-ficha-de-treino.md) | Cancelar criação | Não executado | Não produzido / não observado. |
| [C14-CT01](../../cenarios-de-testes/C14-exercicios.md) | Carregamento da biblioteca | Investigação parcial; julgamento pendente | A biblioteca carregou 11 exercícios em 4 grupos e manteve a contagem após recarregar, sem erro visível. Não reproduzi o erro de servidor descrito na inspeção-base; não concluo correção nem bug. [Jam C14-CT01](https://jam.dev/c/4ee24160-d9b3-465d-b283-2b3dc4f2ae8f?s=mcp). |
| [C14-CT02](../../cenarios-de-testes/C14-exercicios.md) | Importar biblioteca padrão | Não executado | Não produzido / não observado. |
| [C14-CT03](../../cenarios-de-testes/C14-exercicios.md) | Repetir importação | Não executado | Não produzido / não observado. |
| [C14-CT04](../../cenarios-de-testes/C14-exercicios.md) | Cadastro manual | Não executado | Não produzido / não observado. |
| [C14-CT05](../../cenarios-de-testes/C14-exercicios.md) | Pesquisa, filtros e visualização de exercícios | Execução parcial; julgamento pendente | Não encontrei pesquisa/filtros gerais visíveis; abri a visualização do exercício AA (código 11), que exibiu “Não foi possível abrir a mídia” no vídeo. Fechei sem salvar. Não há regra confirmada para classificar a mídia como bug. [Jam exclusivo, 31 s](https://jam.dev/c/0010fdc5-489a-42a1-82eb-1a9bd38dd537?s=mcp).
| [C14-CT06](../../cenarios-de-testes/C14-exercicios.md) | Associar exercício à ficha | Não executado | Não produzido / não observado. |
| [C18-CT01](../../cenarios-de-testes/C18-turmas.md) | Cadastrar turma válida | Execução parcial; julgamento pendente | Busquei QA_VICTOR e não encontrei turma. O formulário mostrou Nome, Status, Plano, Aula Experimental, Tempo (meses), Hora Inicial, Hora Final, Tem Personal e Dias da Semana. Cancelei sem salvar; falta plano próprio e confirmação da unidade. [Jam exclusivo, 24 s](https://jam.dev/c/490a7c3d-2968-4d35-923a-657cc36b3cb1?s=mcp). |
| [C18-CT02](../../cenarios-de-testes/C18-turmas.md) | Nome, plano e dias ausentes | Execução parcial; julgamento pendente | Com o formulário vazio, ao salvar, a tela exibiu “Informe o nome da turma.” Cancelei sem salvar; a lista permaneceu com 12 turmas e QA_VICTOR sem resultado. Verifiquei somente nome ausente; plano/dias pendentes. [Jam C18-CT02](https://jam.dev/c/3ff04937-9bdb-48ac-be36-1bb1e01ca710?s=mcp). |
| [C18-CT03](../../cenarios-de-testes/C18-turmas.md) | Horário final igual ou anterior ao inicial | Não executado | Não produzido / não observado. |
| [C18-CT04](../../cenarios-de-testes/C18-turmas.md) | Tempo em meses inválido | Não executado | Não produzido / não observado. |
| [C18-CT05](../../cenarios-de-testes/C18-turmas.md) | Selecionar vários dias | Não executado | Não produzido / não observado. |
| [C18-CT06](../../cenarios-de-testes/C18-turmas.md) | Aula experimental e Tem Personal | Não executado | Não produzido / não observado. |
| [C18-CT07](../../cenarios-de-testes/C18-turmas.md) | Status ativo/inativo e filtros | Não executado | Não produzido / não observado. |
| [C18-CT08](../../cenarios-de-testes/C18-turmas.md) | Conflito de turma/horário | Não executado | Não produzido / não observado. |
| [C18-CT09](../../cenarios-de-testes/C18-turmas.md) | Cancelar, editar e excluir | Não executado | Não produzido / não observado. |
| [C20-CT01](../../cenarios-de-testes/C20-sifitbox-turmas.md) | Cadastrar modalidade | Não executado | Não produzido / não observado. |
| [C20-CT02](../../cenarios-de-testes/C20-sifitbox-turmas.md) | Cadastrar turma recorrente | Não executado | Não produzido / não observado. |
| [C20-CT03](../../cenarios-de-testes/C20-sifitbox-turmas.md) | Modalidade, nome ou dias ausentes | Não executado | Não produzido / não observado. |
| [C20-CT04](../../cenarios-de-testes/C20-sifitbox-turmas.md) | Vagas zero, negativas, decimais ou excessivas | Não executado | Não produzido / não observado. |
| [C20-CT05](../../cenarios-de-testes/C20-sifitbox-turmas.md) | Horários inválidos e sobreposição | Não executado | Não produzido / não observado. |
| [C20-CT06](../../cenarios-de-testes/C20-sifitbox-turmas.md) | Ativar/inativar modalidade e turma | Não executado | Não produzido / não observado. |
| [C20-CT07](../../cenarios-de-testes/C20-sifitbox-turmas.md) | Gerar aulas a partir da recorrência | Não executado | Não produzido / não observado. |
| [C34-CT01](../../cenarios-de-testes/C34-atividades.md) | Cadastrar atividade com pontuação | Aprovado | Código 10; nome QA_VICTOR_ATIVIDADE_20261119_001; pontuação 10; nome, valor e descrição confirmados após busca e reabertura. Detalhes em [C34-CT01](../../cenarios-de-testes/C34-atividades.md#c34-ct01--cadastrar-atividade-com-pontua%C3%A7%C3%A3o). Captura local C34-CT01-20261118.jpg; [gravação Jam de 53 s](https://jam.dev/c/fd1150c0-707d-4180-9144-96291e954ee2); registra busca (0:32), abertura do detalhe (0:38), fechamento (0:44) e fim (0:53). |
| [C34-CT02](../../cenarios-de-testes/C34-atividades.md) | Atividade sem pontuação | Aprovado | Atividade 002 (código 11, pontuação vazia) e atividade 003 (código 12, pontuação 0) salvas sem aviso; a lista mostra "-" nas duas e os indicadores finais (9, 6, 3 e 6) contaram as duas como sem pontuação; ao reabrir a 003, o campo mostrou 0. Regra do zero a confirmar; sem bug confirmado. Gravações Jam: [primeira](https://jam.dev/c/186f9430-ca1d-49e6-b5c8-87ccf1562132) e [segunda, referência](https://jam.dev/c/8d53721f-db47-4ebd-9718-adf69c1e5f05). |
| [C34-CT03](../../cenarios-de-testes/C34-atividades.md) | Pontuação negativa, decimal ou texto | Julgamento pendente de regra | Observei -1 salvo como -1 ponto; 1.5 informado e exibido como 1 ponto; abc aceito no campo e listado sem pontuação. Indicadores finais: 12 total, 7 com e 5 sem pontuação, 6 com descrição. Regra pendente; nenhum bug confirmado. [Jam, 4min19s](https://jam.dev/c/58c5bb4e-0f2c-41e5-aab8-8d25db6080ea?s=mcp). |
| [C34-CT04](../../cenarios-de-testes/C34-atividades.md) | Nome vazio e texto longo | Julgamento pendente de regra | O nome vazio foi salvo com código 16; QA_VICTOR_ATIVIDADE_20261119_007_LONG foi salva com descrição de 1.800 caracteres (código 17). Após os cadastros: 14 atividades, 7 com pontuação, 7 sem e 7 com descrição; ao reabrir o código 17, a descrição estava visível e Pontuação mostrou 0 embora o campo tivesse ficado vazio. Regra e limite pendentes; sem bug confirmado. [Jam exclusivo, 3min15s](https://jam.dev/c/f25eee59-00c4-482b-bf6f-b20c0360d3e3?s=mcp). |
| [C34-CT05](../../cenarios-de-testes/C34-atividades.md) | Pesquisar, editar e conferir indicadores | Julgamento pendente de regra | Pesquisei o código 17 (QA_VICTOR), alterei a pontuação de 0 para 10 e confirmei a persistência; os indicadores mudaram de 15/8/7/8 para 15/9/6/8. Restaurei 0 e os indicadores voltaram. Nesta leitura, a descrição tinha 255 caracteres. A interpretação do zero e o limite da descrição seguem sem regra confirmada; nenhum bug confirmado. [Jam exclusivo C34-CT05, 2min49s](https://jam.dev/c/a5750574-2ab8-4b46-9d3f-ef2734ceff31?s=mcp).
| [C45-CT01](../../cenarios-de-testes/C45-modelos-de-ficha.md) | Buscar código, título e criador | Julgamento pendente | Consultei os filtros Código, Título e Criador com termos QA_VICTOR; a tela permaneceu vazia, sem erro visível. Não havia modelo próprio para validar correspondência positiva. Jam não iniciou gravação utilizável; sem link. Sem bug confirmado. |
| [C45-CT02](../../cenarios-de-testes/C45-modelos-de-ficha.md) | Abrir criação e mapear editor | Execução parcial; julgamento pendente | Abri Novo Modelo de Ficha, observei Nome do Modelo, Personal, Cancelar e Criar Modelo; cancelei sem preencher ou salvar. O editor posterior depende de modelo próprio. [Jam exclusivo, 35 s](https://jam.dev/c/3afaed3e-9de5-4403-a212-b15a2751ed2c?s=mcp). |
| [C45-CT03](../../cenarios-de-testes/C45-modelos-de-ficha.md) | Título vazio e modelo sem exercícios | Não executado | Não produzido / não observado. |
| [C45-CT04](../../cenarios-de-testes/C45-modelos-de-ficha.md) | Editar, duplicar ou excluir, se disponíveis | Não executado | Não produzido / não observado. |
| [C45-CT05](../../cenarios-de-testes/C45-modelos-de-ficha.md) | Usar modelo em ficha de aluno | Não executado | Não produzido / não observado. |
| [C45-CT06](../../cenarios-de-testes/C45-modelos-de-ficha.md) | Conferir indicadores | Não executado | Não produzido / não observado. |
| [C47-CT03](../../cenarios-de-testes/C47-victor.md) | Turma recorrente → aula → check-in → presença | Não executado | Não produzido / não observado. |
| [C47-CT04](../../cenarios-de-testes/C47-victor.md) | Grupo muscular → exercício → modelo → ficha | Não executado | Não produzido / não observado. |

## Atualização após execução

Atualizar caso e esta tabela com resultado real, data/hora/fuso, executor, ambiente, unidade, IDs QA_VICTOR e links revisados. Variações e retestes ficam no histórico do mesmo caso. Somar aprovados/reprovados somente com julgamento concluído. Separar bloqueios, dúvidas, investigações e não aplicabilidade justificada. Vincular defeitos reproduzidos a [bugs.md](bugs.md) e ao relatório geral. Não declarar cobertura completa com casos pendentes.

## Conclusão atual

Tenho evidência de que C34-CT01 e C34-CT02 atenderam aos critérios registrados. C34-CT03, C34-CT04 e C34-CT05 aguardam confirmação das regras. Executei parcialmente C06-CT01 e C06-CT02. Em C06-CT01, as buscas retornaram vazio; falta validar uma presença conhecida. Em C06-CT02, registrei as datas preenchidas pelos três atalhos; o mês resultou em uma janela de 30 dias, cuja definição precisa ser confirmada. Os intervalos consultados estavam vazios, então a conferência de registros permanece pendente. C06-CT05 também está parcial: falta comparar indicadores com um período que contenha presenças. Os outros 52 casos ainda não foram iniciados. C18-CT01 e C18-CT02 também foram iniciados parcialmente; nenhum bug foi confirmado. C45-CT01 e C45-CT02 e C14-CT05 seguem parciais; não confirmei bug.

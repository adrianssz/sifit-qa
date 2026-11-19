# Planejamento dos testes — Meus testes

**Responsável:** Victor  
**Data de elaboração:** 18/11/2026  
**Tipo:** testes funcionais manuais  
**Sistema de referência:** https://sifit.centrion.com.br/  
**Versão do sistema, navegador/versão e sistema operacional:** a registrar na execução; não verificados nesta etapa.  
**Fontes:** [Inventário](../../../Invent%C3%A1rio.md), [requisitos dos meus testes](requisitos.md) e [plano do modelo do professor](https://github.com/Adnyslougansilva/extensao-qa/blob/main/OrangeHRM/2-plano%20de%20testes.md).  
**Estado inicial:** 66 casos planejados, todos Não executados; nenhuma evidência de execução produzida nesta etapa.

## 1. Objetivo e escopo

Vou verificar os módulos que ficaram sob minha responsabilidade e registrar os resultados reais e as dependências, mantendo a ligação com o inventário. Preservar exatamente os IDs e as descrições dos casos. Os RFxx de requisitos.md seguem o número dos cenários.

| Cenário | Módulo | Casos planejados | Prioridade proposta | Arquivo previsto em SIFIT/cenarios-de-testes/ |
|---|---|---:|---|---|
| C05 | Check-in | 9 | Alta | `C05-check-in.md` |
| C06 | Presenças | 6 | Alta | `C06-presencas.md` |
| C07 | SifitBox — Aulas | 6 | Alta | `C07-sifitbox-aulas.md` |
| C13 | Ficha de Treino | 10 | Alta | `C13-ficha-de-treino.md` |
| C14 | Exercícios | 6 | Alta | `C14-exercicios.md` |
| C18 | Turmas | 9 | Alta | `C18-turmas.md` |
| C20 | SifitBox — Turmas | 7 | Alta | `C20-sifitbox-turmas.md` |
| C34 | Atividades | 5 | Média | `C34-atividades.md` |
| C45 | Modelos de Ficha | 6 | Alta | `C45-modelos-de-ficha.md` |
| C47 | Fluxos integrados — CT03 e CT04 | 2 | Alta | `C47-victor.md` |
| **Total** | **64 casos de módulos + 2 casos do C47** | **66** | | |

Prioridade Alta indica dependência entre módulos, persistência ou fluxo de presença/treino; a investigação histórica de Exercícios também merece atenção inicial. A prioridade é de planejamento, não severidade de bug.

C47-CT01, C47-CT02 e C47-CT05 ficam como referência de outros módulos, fora das 66 execuções dos meus testes. C47-CT06 a C47-CT10 (persistência, banco e ambiente compartilhado) pertencem a outros responsáveis na divisão vigente e não entram na minha contagem.

As alterações no repositório ficam restritas a `SIFIT/contribuicoes/victor/requisitos.md`, `planejamento.md`, `bugs.md`, `resultados.md`, aos dez arquivos de cenário acima e a `SIFIT/3-relatorio-de-bugs.md`. Não editar inventário, README ou arquivos de colegas. O arquivo de C47 de outro integrante não será substituído.

Não incluir carga, exploração de vulnerabilidades, transações reais ou alterações em registros de outras pessoas.

## 2. Etapas e pontos de acompanhamento

| Etapa | Entrega | Ponto de parada |
|---|---|---|
| 1 — Preparação documental | Conferir a versão atual, criar requisitos.md e planejamento.md em commits pequenos na main. | Parar após conferir os dois arquivos publicados. |
| 2 — Roteiros e registros | Criar os dez cenários, bugs.md e resultados.md, sem resultados fictícios; inicializar a seção dos meus testes no relatório geral se necessário. | Parar com os roteiros disponíveis para revisão, antes de executar. |
| 3 — Preparação do ambiente | Confirmar ambiente, acesso, gravação, dados e dependências; reconhecer os controles sem concluir casos formais. | Parar antes do primeiro conjunto de testes com gravação. |
| 4 — Execução por cenário | Executar um conjunto pequeno, revisar evidências, atualizar cenário/bugs/resultados e publicar. | Parar entre cenários ou fluxos importantes. |
| 5 — Integrações e fechamento | Conferir C47, retestes, links, contagens e limitações reais. | Apresentar conclusão apoiada nas evidências. |

Concluí a preparação documental e os roteiros. Até 19/11/2026, registrei cinco execuções de C34 (duas aprovadas e três aguardando regra), C06-CT02 com julgamento pendente e execuções parciais de C06-CT01, C06-CT04, C06-CT05 e C14-CT01. O balanço atual é 2 aprovados, 14 pendentes de julgamento (incluindo C13-CT10 parcial) e 50 não iniciados, de uma base de 66. Ainda faltam os demais cenários, a verificação MySQL planejada e os fluxos integrados C47.

Antes de cada edição, reler a versão atual do arquivo e conferir a main. Criar arquivos apenas se continuarem ausentes. Em caso de alteração concorrente, reler e reconciliar sem sobrescrever trabalho novo. Após cada commit, conferir os caminhos e o conteúdo publicado.

## 3. Preparação e dependências

| Dependência | Uso | Situação nesta etapa |
|---|---|---|
| Acesso ao SIFIT e identificação do perfil/unidade | Todos os módulos; limitar a cobertura ao perfil realmente disponível. | Acessei Presenças em https://sifit.centrion.com.br/ na sessão exibida como Jair; a unidade e a versão do sistema não ficaram identificadas. Não registrar credenciais. |
| Gravação e compartilhamento | Jam para navegador; gravação local/Drive quando necessário. | Gravei C06-CT02 e C06-CT04 individualmente pelo link Jam. Os vídeos são capturas de tela sem logs de console/rede. Gravação foi confirmada nesta sessão; pasta SIFIT-QA-Victor e Workbench ainda não conferidos. |
| Cliente e matrícula de teste | Check-in, presença e ficha de treino. | Ainda preciso localizar cliente QA_VICTOR elegível e seus IDs; não encontrei presenças nos intervalos consultados. Dependência de módulos C08/C09. |
| Plano de teste | Turmas e elegibilidade. | Confirmar referência válida do C26 sem alterar registros de colegas. |
| Personal e objetivo de treino | Ficha de treino e opções de turma. | Confirmar referências disponíveis de C30/C16. |
| Grupo muscular e biblioteca | Exercício → modelo → ficha. | Dependência do C15 e do carregamento de C14; não presumir biblioteca vazia diante de erro. |
| Modalidade e turma recorrente | Geração de aulas e fluxo integrado. | Preparar pelos C20-CT01/CT02 com dados próprios. |
| Câmera/dispositivo e QR controlado | C05-CT08. | Dependência condicional; verificar disponibilidade antes do caso. |
| Regras de negócio pendentes | Casos listados em requisitos.md. | Registrar fonte e confirmação antes de reprovar comportamento. |

Vou usar referências de outros módulos como pré-condições. Se precisar preparar dados fora dos meus módulos, vou identificar essa preparação e usar registros próprios, preservando os arquivos e registros dos colegas.

A falta de uma dependência na fase documental não marca automaticamente um caso como Bloqueado. O bloqueio será registrado quando constatado na preparação ou tentativa de execução, com motivo concreto.

## 4. Dados de teste

Usar o padrão `QA_VICTOR_<ENTIDADE>_<AAAAMMDD>_<SEQUENCIA>`. Substituir a data pela data real de preparação e anotar o ID efetivamente gerado. Os nomes abaixo são propostas, não cadastros já realizados.

| Entidade | Exemplo de prefixo | Finalidade |
|---|---|---|
| Cliente | QA_VICTOR_CLIENTE | Presença e ficha de treino. |
| Plano/referência de apoio | QA_VICTOR_PLANO | Apenas se for necessário preparar referência própria. |
| Turma | QA_VICTOR_TURMA | C18; usar registros separados para edição, inativação e exclusão. |
| Modalidade | QA_VICTOR_MODALIDADE | C20 e aulas correspondentes. |
| Turma recorrente | QA_VICTOR_RECORRENCIA | C20 → C07 → C05 → C06. |
| Grupo muscular/exercício | QA_VICTOR_GRUPO / QA_VICTOR_EXERCICIO | Referências controladas para a cadeia de treino. |
| Modelo de ficha | QA_VICTOR_MODELO | Modelo original a comparar antes e depois da aplicação. |
| Ficha | QA_VICTOR_FICHA | Identificação em campo disponível, sem presumir que exista um campo de título. |
| Atividade | QA_VICTOR_ATIVIDADE | C34 e respectivas validações/indicadores. |
| Registro descartável | QA_VICTOR_DESCARTAVEL | Cancelamento, exclusão e análise de dependências. |

Quando não houver nome livre, relacionar o ID real ao registro QA_VICTOR de origem. Registrar módulo, código, data/hora, unidade e caso que criou/usou o dado. Não inventar IDs do sistema.

Dados inválidos devem variar um campo por vez. Escolher números válidos e limites somente após confirmar a regra; não presumir que zero, decimal, nome repetido ou horário sobreposto seja proibido. Incluir espaços, acentos e limites de texto onde aplicáveis.

## 5. Sequência proposta de execução

A sequência pode mudar por dependências constatadas; cada pausa preserva o acompanhamento solicitado.

1. Conferir sessão, unidade, ambiente e gravação. Reconhecer Exercícios e o editor de Modelos de Ficha para definir os roteiros dependentes sem inventar controles.
2. Preparar cliente/matrícula, plano, personal, objetivo e grupo muscular controlados, quando necessários. Registrar os IDs e a origem das referências.
3. Executar C34 e depois C18, em conjuntos separados, com dados próprios.
4. Executar C20 para criar modalidade/recorrência; executar C07 para consultar e gerar aulas controladas. Retomar C20-CT06/CT07 conforme as aulas estiverem disponíveis.
5. Executar C05 com cliente elegível e C06 para conferir o reflexo da entrada. Avaliar C47-CT03 com a cadeia completa e evidência identificada.
6. Executar C14, C45 e C13 conforme a biblioteca, os modelos e as fichas forem preparados. Retomar C14-CT06 e C45-CT05 após existir a ficha. Avaliar C47-CT04.
8. Fazer retestes e fechamento, mantendo as tentativas anteriores e registrando limitações.

Os casos C07-CT05/CT06, C13-CT06/CT07, C14-CT04/CT05 e C45-CT02/CT03/CT04 exigem reconhecimento do editor/detalhe antes de um roteiro completo. Sua descrição original será mantida, com controles efetivos documentados depois.

## 6. Técnicas e verificações comuns

Aplicar caminho feliz, testes negativos, partição de equivalência, valores limite, transições de status, filtros e conferência cruzada. O reconhecimento exploratório prepara o roteiro e não substitui execução formal.

Usar G01–G24 conforme o inventário: cadastro, campos, formatos/limites, cancelamento, persistência, filtros, navegação, exclusão, dependências, erros e evidências. Cada cenário lista seus Gxx aplicáveis, sem mudar a descrição original nem inflar a contagem base de 66 casos.

Casos com múltiplas variações terão sufixos A/B/C e resultado por variação. Um caso principal só poderá ser aprovado quando todas as variações aplicáveis e os critérios confirmados tiverem sido verificados. Retestes mantêm o ID original, com número da tentativa/data em campo próprio.

## 7. Status e contagem

| Status | Critério |
|---|---|
| Não executado | Ainda não houve execução formal documentada; inclui os 66 casos desta etapa. |
| Aprovado | Execução concluída e evidenciada; todos os critérios confirmados aplicáveis foram atendidos. |
| Reprovado | Divergência reproduzida contra critério confirmado, com resultado real e evidência. |
| Bloqueado | Uma dependência, acesso, regra indispensável ou falha de carregamento constatada impede concluir/julgar; registrar motivo e o que foi observado. |
| Não se aplica | Recurso ou condição comprovadamente não aplicável ao ambiente/escopo, com justificativa e evidência. |

Tentativa iniciada mas inconclusa deve ser descrita, sem aprovação artificial. Regra desconhecida fica pendente de confirmação; não é bug. Não se aplica não é usado só porque faltou acesso ou dados.

- Base planejada: 66 casos (64 + 2).
- Execuções concluídas com julgamento: Aprovados + Reprovados.
- Não executados, Bloqueados e Não se aplica são contados separadamente.
- Cobertura com julgamento: (Aprovados + Reprovados) ÷ 66. Registrar alterações futuras de escopo antes de mudar o denominador.
- Aprovação entre os julgados: Aprovados ÷ (Aprovados + Reprovados); sem execuções, informar “não calculável”.
- Variações, tentativas e Gxx têm contagem auxiliar; não criam silenciosamente novos casos principais.

## 8. Evidências e execução

Cada caso terá objetivo/requisito, descrição original, tipo, pré-condições, dados, passos em DADO/QUANDO/ENTÃO, critérios de aceitação, resultado obtido, status, data/hora com fuso, executor real, navegador/versão, sistema operacional, URL/unidade, vídeo, prints e bug associado quando houver.

Sou responsável pelo trabalho. Vou registrar no campo executor quem operou a interface e a assistência utilizada.

Gravar casos aprovados e reprovados. Preferir um vídeo por caso simples; fluxos integrados podem usar vídeo contínuo com tempos inicial/final para cada caso. Usar somente links efetivamente gerados e conferir seu acesso. A pasta SIFIT-QA-Victor pode receber gravações exportadas; não presumir que o compartilhamento já esteja correto.

Revisar vídeos, capturas e eventuais logs antes de publicar: não incluir senhas, tokens, strings de conexão ou dados pessoais reais. Não reproduzir as credenciais do material acadêmico.

Capturas serão armazenadas em local de evidências autorizado e referenciadas por link; este planejamento não amplia os caminhos de arquivos do repositório autorizados.

## 9. Registro de bugs, investigações e bloqueios

Manter em bugs.md somente defeitos confirmados por reprodução e critério fundamentado; usar IDs próprios `BUG-VICTOR-NNN` após conferir duplicidades. Registrar título, caso, pré-condições, passos mínimos, esperado com fonte, obtido, frequência, ambiente, data/hora, severidade justificada, evidências, estado e causa apenas quando demonstrada.

Investigações e bloqueios terão seções separadas, sem numeração de bug confirmado. O erro histórico em Exercícios exige nova observação; não importar como bug dos meus testes.

Atualizar `SIFIT/3-relatorio-de-bugs.md` apenas com a contribuição dos meus testes e links rastreáveis, preservando todo conteúdo alheio. Se o relatório ainda estiver ausente, inicializar uma seção claramente identificada, sem afirmar que não há bugs no projeto. Nenhum bug será criado para preencher um modelo.

## 10. Banco, integridade e ambiente compartilhado

Os casos de banco (C47-CT07 a CT09), persistência (CT06) e alterações de colegas (CT10) não fazem parte da minha divisão vigente de 66 casos. Mantenho apenas o cuidado de usar somente registros QA_VICTOR, sem alterar nem apagar registros ou evidências de outros integrantes.

## 11. Critérios de entrada, saída e riscos

**Entrada por caso:** roteiro revisado, critérios suficientes para julgamento, ambiente identificado, dados preparados, dependências disponíveis e captura configurada. Se faltar condição, registrar a pendência sem forçar execução.

**Saída:** todos os casos têm estado real; as execuções concluídas têm evidências acessíveis; bloqueios e dúvidas estão explícitos; bugs confirmados e retestes estão vinculados; contagens e links foram conferidos. Casos bloqueados ou não executados impedem declarar cobertura completa.

| Risco | Tratamento |
|---|---|
| Ambiente compartilhado muda durante o caso | Registrar IDs e horários, comparar a mesma unidade e repetir apenas quando necessário. |
| Dependência indisponível ou tela com erro | Documentar condição e impacto, preservando a distinção entre investigação e bug. |
| Regra desconhecida | Solicitar confirmação com exemplo concreto; não adotar premissa como requisito obrigatório. |
| Importação ou geração com efeito amplo | Delimitar turma, período e conjunto próprio; só prosseguir com escopo de teste conhecido. |
| Evidência sem gravação ou link acessível | Registrar a limitação e complementar a evidência, sem inventar vídeo ou conclusão. |

## 12. Entregáveis e continuidade

Preparei requisitos.md, planejamento.md, os dez cenários indicados, bugs.md, resultados.md e minha seção no relatório geral. Estou executando os cenários em etapas curtas, com vídeos Jam separados por teste. Após cada execução, atualizo o cenário e resultados com observações reais, link efetivo, contagem e limitações.

A documentação inicial não certifica o funcionamento do SIFIT.

## 13. Preparação do ambiente — 18/11/2026

Acessei o painel de https://sifit.centrion.com.br/ com a sessão disponível e fiz somente o reconhecimento das telas abaixo. Não gravei execuções formais nem salvei cadastros nesta preparação; mantenho os 71 casos como Não executados.

- Em Atividades, encontrei pesquisa por Código e Nome, indicadores de total/com pontuação/sem pontuação/com descrição e a ação Nova Atividade. O formulário contém Código, Nome, Pontuação, Descrição, Salvar e Cancelar. Ainda preciso confirmar obrigatoriedade, formatos e limites por execução controlada.
- Em Exercícios, a biblioteca carregou grupos e exercícios nesta visita. Vi ações Adicionar, Visualizar e Deletar. O erro histórico do inventário não apareceu nesta visita; isso não conclui C14-CT01 nem prova correção definitiva.
- Em Modelos de Ficha, encontrei busca por Código, Título e Criador. Ao abrir Novo Modelo de Ficha, vi Nome do Modelo, Personal, Cancelar e Criar Modelo. Cancelei sem criar; o editor posterior continua dependente de um modelo próprio.
- A anotação anterior registra consulta somente de leitura à estrutura do banco, mas não confirma que o cliente era MySQL nem que essa base corresponde à interface SIFIT. A verificação MySQL e a correspondência por IDs QA_VICTOR continuam pendentes; não fiz escrita.

Concluí cinco execuções de C34: C34-CT01 e C34-CT02 foram aprovados; C34-CT03, C34-CT04 e C34-CT05 aguardam confirmação de regra. Iniciei C06-CT05 no ambiente de referência; a consulta de 13/11 a 19/11/2026 mostrou total 0, alunos distintos 0, média 0 e 7 dias. Falta comparar com um período que tenha presenças. Esse registro descreve a etapa de 18/11; a atualização atual de execução está na seção 15.

## 14. Correção de escopo — 19/11/2026

A divisão vigente substitui a anterior e tem 66 casos: 64 dos módulos C05, C06, C07, C13, C14, C18, C20, C34 e C45, mais C47-CT03 e C47-CT04. Os registros de 18/11/2026 acima citam 71 casos pela divisão anterior; vale o total de 66.

## 15. Atualização da execução — 19/11/2026

Em C45-CT01, consultei a tela de Modelos de Ficha e pesquisei separadamente por código, título e criador usando termos QA_VICTOR. A listagem ficou vazia (0 modelos, 0 criadores, 0 listados e 0 sem criador) e não houve erro visível. Não localizei modelo próprio para validar correspondência positiva; mantive julgamento pendente, sem bug confirmado. Em C45-CT02, abri Novo Modelo de Ficha, vi Nome do Modelo, Personal, Cancelar e Criar Modelo, e cancelei sem criar registro. O editor completo depende de modelo próprio; gravei este caso separadamente: https://jam.dev/c/3afaed3e-9de5-4403-a212-b15a2751ed2c?s=mcp. Gravei um vídeo exclusivo de 31 s para C14-CT05; o Jam está vinculado no cenário e nos resultados.

Executei parcialmente C06-CT01 e gravei um vídeo Jam individual. Busquei QA_VICTOR e QA_VICTOR_CLIENTE_INEXISTENTE_999 no período 13/11–19/11/2026; ambos retornaram estado vazio, sem erro visível. Não localizei uma presença conhecida para validar a busca positiva, então mantive o julgamento pendente. Também executei C06-CT02 e gravei esse caso separadamente. Os atalhos preencheram Hoje 19/11/2026, Esta semana 13/11–19/11 e Este mês 21/10–19/11; os intervalos consultados estavam vazios e a definição de semana/mês segue pendente. Em C06-CT04, consultei o intervalo invertido 21/10/2026–20/10/2026; a tela terminou a consulta sem mensagem visível de validação, mas não executei as variações vazia e inválida. Mantive os dois casos com julgamento pendente e não declarei bug. C06-CT05 permanece parcial por falta de comparação com presenças existentes. Em C14-CT01, a biblioteca carregou 11 exercícios em 4 grupos, mas não reproduzi o erro de servidor descrito na inspeção-base; a investigação continua pendente. Em C14-CT05, não encontrei pesquisa ou filtros gerais; a visualização de AA (código 11) mostrou “Não foi possível abrir a mídia” para o vídeo e foi fechada sem salvar. Gravei o caso em Jam separado; sem regra confirmada, não abri bug.

Em C18-CT01, pesquisei QA_VICTOR na listagem de Turmas, sem encontrar registros. Abri Cadastrar Turma, mapeei Nome, Status, Plano, Aula Experimental, Tempo (meses), Hora Inicial, Hora Final, Tem Personal e Dias da Semana e cancelei sem salvar. A unidade não foi confirmada e não havia plano QA_VICTOR disponível; o caso segue parcial até preparar referência própria. Gravei uma captura exclusiva de tela de 24 s: https://jam.dev/c/490a7c3d-2968-4d35-923a-657cc36b3cb1?s=mcp.

Em C13-CT10, cancelei a ficha sem preencher e a lista permaneceu com 0 fichas; falta testar fechar o modal. Vídeo Jam individual: https://jam.dev/c/890e412b-387f-444c-a0b5-0adb6d4847d9?s=mcp. Em C18-CT02, ao salvar o formulário vazio, observei a mensagem “Informe o nome da turma.” Cancelei sem salvar; a lista permaneceu com 12 turmas. Registrei o vídeo individual: https://jam.dev/c/3ff04937-9bdb-48ac-be36-1bb1e01ca710?s=mcp. O resultado consolidado está em resultados.md: 66 planejados, 50 não iniciados, 2 aprovados, 14 com julgamento pendente; nenhum reprovado, bloqueado ou não aplicável. Ainda preciso executar os outros casos, conferir MySQL conforme o escopo autorizado e completar C47.

# SIFIT — Inventário inicial de casos de teste e guia de evidências

**Responsável pela execução:** Adrian  
**Data do levantamento:** 12/10/2026  
**Sistema:** https://sifit.centrion.com.br/login  
**Repositório do trabalho:** https://github.com/adrianssz/sifit-qa  
**Modelo consultado:** https://github.com/Adnyslougansilva/extensao-qa

## 1. O que este inventário representa

Foram identificadas 44 entradas no menu do perfil acessível e abertas as respectivas telas. Também foram inspecionados diversos formulários de inclusão, sem salvar cadastros ou executar pagamentos, exclusões ou envios. O login funcionou e o sistema apresentou o nome **Jair**; é necessário confirmar com o professor o vínculo desse perfil com o acesso fornecido.

Este documento reúne **382 itens de verificação específicos em 47 blocos**, incluindo autenticação, navegação geral e fluxos integrados, além de **24 verificações comuns** reutilizáveis. É um inventário inicial de cobertura funcional, não uma garantia de esgotar todos os estados possíveis do sistema. Alguns itens agrupam variações que deverão ser separadas em subcasos na execução (por exemplo, um caso para cada campo obrigatório).

**Todos os casos formais permanecem “Não executados”.** O acesso e a inspeção exploratória desta sessão não equivalem a uma execução gravada e documentada por Adrian. Não foram feitas gravações no Jam nem conferências no banco.

### Como interpretar as marcações

- **Observado:** o controle ou campo foi visto; seu funcionamento não está automaticamente validado.
- **Dependência:** exige dados de teste, abertura de detalhes ou outra etapa para concluir o mapeamento.
- **Condicional:** depende de recurso, integração, equipamento, conta controlada ou autorização específica.
- **Regra a confirmar:** o resultado esperado é uma hipótese de teste; deve ser confirmado com o professor ou documentação do sistema antes de registrar reprovação.
- **Investigação:** ocorrência exploratória a reproduzir com evidência; ainda não é um bug formal.
- A ausência do atributo HTML “required” não prova que o campo é opcional; a indicação visual e a validação do servidor também precisam ser conferidas.
- A presença de “Carregando...” e de contadores zero durante carregamento não prova ausência de registros.

### Limitações observadas

1. A rota Dashboard (/dash) apresentou o título “Despesas Fixas”, embora o conteúdo exibisse gráficos de gestão. Reproduzir com gravação.
2. Algumas telas/formulários apresentaram **“Erro no servidor — Erro interno inesperado”**, incluindo exercícios, perguntas de anamnese e cadastros de matrícula/modelos. Não foi investigada a causa; não atribuir a banco, código ou permissão sem evidência.
3. A biblioteca de exercícios exibiu caminho para importar a biblioteca padrão ou cadastrar grupos; dados carregados com erro não devem ser tratados como lista vazia confirmada.
4. Editores e detalhes dependentes de registros não foram esgotados: realização da avaliação, exercícios de uma ficha, participantes de aulas, alguns formulários de inclusão e conteúdo interno das abas de configurações.
5. O banco não foi acessado. Nomes de tabelas, colunas e relacionamentos deverão ser obtidos do schema real.
6. A cobertura de permissões está limitada ao perfil fornecido. Outros papéis exigem contas de teste autorizadas.
7. Não inclui teste de carga, exploração de vulnerabilidades ou execução de transações reais. QR Code/biometria e integração Pagar.me dependem de ambiente adequado.
8. Este levantamento não cria uma exigência acadêmica nova: o PDF pede que o trabalho individual siga o modelo. O escopo completo abaixo atende ao pedido de mapear o site; a profundidade da entrega pode ser ajustada à orientação do professor.

## 2. Regras comuns para cada tela aplicável

Cada Gxx deve ser associado ao módulo e ao campo correspondente. Exemplo: **C08-G02-NOME** para nome obrigatório em Clientes. Marcar “Não se aplica” somente quando o controle/regra não existir, explicando o motivo.

| ID | Verificação | Como exercitar | Resultado esperado proposto |
|---|---|---|---|
| G01 | Cadastro válido | Executar um cadastro mínimo e outro completo com dados fictícios controlados. | Salvar exatamente os dados informados e apresentar confirmação. |
| G02 | Obrigatórios vazios | Esvaziar um campo por vez e, depois, todos os obrigatórios. | Indicar a pendência e não persistir registro inválido. |
| G03 | Somente espaços | Usar espaços em campos textuais obrigatórios. | Não aceitar texto vazio disfarçado. |
| G04 | Opcionais vazios | Deixar campos opcionais sem preenchimento. | Permitir a operação quando os obrigatórios estiverem válidos. |
| G05 | Formato inválido | Testar cada documento, e-mail, telefone, data e número conforme o campo. | Aplicar validação confirmada e orientar correção. |
| G06 | Valores limite | Após confirmar mínimo/máximo, testar abaixo, no limite e acima; incluir tamanho de texto. | Aceitar limites permitidos e tratar excesso sem truncamento silencioso. |
| G07 | Acentos e caracteres legítimos | Usar nomes com acentos, hífen e apóstrofo; observações com quebra de linha. | Preservar conteúdo sem quebrar a tela. |
| G08 | Duplicidade | Repetir identificador que deva ser único, conforme regra confirmada. | Impedir duplicidade proibida; não tratar homônimos como erro sem requisito. |
| G09 | Seleções dependentes | Alternar tipo/status/opção que habilita outros campos. | Exibir opções coerentes e não salvar valores antigos ocultos indevidamente. |
| G10 | Cancelar/fechar | Preencher sem salvar e cancelar ou fechar o diálogo. | Não persistir os dados cancelados. |
| G11 | Reabrir formulário | Após cancelar, abrir novamente. | Repor o estado previsto, sem dados antigos indevidos. |
| G12 | Editar registro de teste | Alterar um campo, salvar e reabrir. | Persistir a alteração no registro correto. |
| G13 | Persistência | Atualizar a página e repetir consulta; quando aplicável, sair e entrar. | Manter somente operações confirmadas. |
| G14 | Clique duplo em Salvar | Enviar uma única operação com clique duplo controlado. | Evitar registros ou lançamentos duplicados. |
| G15 | Pesquisa existente/inexistente | Buscar por cada campo exposto, incluindo texto parcial quando suportado. | Exibir correspondências ou estado vazio compreensível. |
| G16 | Filtros combinados e limpeza | Aplicar cada filtro isolado, combinar filtros e limpar. | Respeitar todas as condições e restaurar consulta corretamente. |
| G17 | Paginação | Trocar páginas e tamanho; repetir após filtro. | Não omitir, repetir ou contar incorretamente os registros. |
| G18 | Ordenação, se disponível | Alternar cada coluna ordenável, incluindo datas e números. | Ordenar pelo tipo real do dado, não apenas pelo texto. |
| G19 | Excluir/cancelar exclusão | Somente em registro descartável, com ação de exclusão realmente disponível. | Cancelar preserva o registro; confirmar segue a regra de exclusão e dependências. |
| G20 | Referências e dependências | Tentar operação sobre cadastro usado em outro módulo. | Bloquear, preservar ou atualizar vínculos conforme regra confirmada. |
| G21 | Erro no servidor | Registrar mensagem, horário e caminho; reproduzir uma vez em nova tentativa controlada. | Não apresentar sucesso falso nem perder silenciosamente dados já confirmados. |
| G22 | Upload, onde existir | Arquivo válido, inválido, tamanho limite, troca e cancelamento. | Respeitar formatos/limites e não expor caminhos internos. |
| G23 | Teclado, foco e mensagens | Percorrer controles e ler mensagens de validação. | Operar ações principais por teclado e identificar o campo com erro. |
| G24 | Conferência cruzada | Comparar lista, detalhes, indicadores, relatório e banco quando aplicável. | Manter consistência para o mesmo registro e período. |

## 3. Casos específicos por módulo

Os IDs Cxx-CTyy são estáveis para esta versão. Não reutilizar um ID excluído para outro caso. Para variações, acrescentar sufixos (A, B, C) ou criar novos IDs ao final do cenário.

### C01 — Autenticação e sessão

**Base da inspeção:** Tela de login observada; acesso autenticado confirmado. Demais comportamentos ainda não executados.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C01-CT01 | Login válido|Redirecionar para a área interna com sessão autenticada.|Positivo |
| C01-CT02 | Senha incorreta|Recusar acesso com mensagem compreensível, sem revelar dados internos.|Negativo |
| C01-CT03 | Usuário inexistente|Recusar acesso sem abrir a área interna.|Negativo |
| C01-CT04 | Login e senha vazios|Informar os campos necessários e impedir autenticação.|Negativo |
| C01-CT05 | Somente login vazio|Impedir autenticação e orientar preenchimento.|Negativo |
| C01-CT06 | Somente senha vazia|Impedir autenticação e orientar preenchimento.|Negativo |
| C01-CT07 | Senha mascarada|Não mostrar a senha em texto aberto durante a digitação.|Interface |
| C01-CT08 | Entrar por clique e pela tecla Enter|Verificar ambas as formas de envio e seus resultados.|Interação |
| C01-CT09 | Manter conectado marcado e desmarcado|Comparar persistência após fechar e reabrir o navegador; confirmar a regra de sessão.|Sessão |
| C01-CT10 | Esqueci minha senha|Verificar abertura do fluxo e orientações; envio depende de conta de teste controlada.|Condicional |
| C01-CT11 | Atualizar página autenticada|Manter sessão válida sem perder acesso indevidamente.|Sessão |
| C01-CT12 | Logout e retorno pelo botão Voltar|Encerrar a sessão e impedir novas operações autenticadas.|Sessão |
| C01-CT13 | Abrir URL interna sem sessão|Solicitar autenticação e impedir leitura ou alteração protegida.|Negativo |
| C01-CT14 | Identidade exibida após login|Conferir o vínculo da conta fornecida com o nome Jair exibido; divergência não é bug sem confirmar cadastro.|Investigação |

### C02 — Navegação e comportamento geral

**Base da inspeção:** Controles do menu, temas, notificações, usuário e Academy Assistant observados.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C02-CT01 | Abrir as 44 entradas do menu|Cada link deve abrir o módulo correspondente, sem página vazia ou erro persistente.|Navegação |
| C02-CT02 | Título da tela e item selecionado|Nome, conteúdo e destaque devem corresponder ao módulo; revisar Dashboard exibindo título Despesas Fixas.|Interface |
| C02-CT03 | Rolagem do menu|Permitir acessar todos os módulos sem esconder ações.|Interface |
| C02-CT04 | Alternar tema claro e escuro|Manter contraste, legibilidade e controles utilizáveis; verificar persistência da preferência.|Interface |
| C02-CT05 | Abrir e fechar notificações|Apresentar conteúdo ou estado vazio de forma coerente.|Interação |
| C02-CT06 | Abrir menu do usuário|Verificar opções realmente disponíveis e seus destinos.|Interação |
| C02-CT07 | Abrir e fechar Academy Assistant|Exibir o painel sem quebrar a navegação; envio de mensagens será avaliado separadamente.|Interação |
| C02-CT08 | Teclado e foco|Tab, Shift+Tab e Enter devem permitir operar formulários; conferir foco em mensagens e diálogos.|Acessibilidade |
| C02-CT09 | Botões apenas com ícones|Conferir identificação da ação, dica e nome acessível.|Acessibilidade |
| C02-CT10 | Carregamento e erro|Distinguir carregando, lista vazia e falha; permitir orientação ou recuperação sem falso sucesso.|Negativo |
| C02-CT11 | Redimensionamento e zoom|Verificar menus, campos, tabelas e botões sem sobreposição ou perda de acesso.|Interface |

### C03 — Página Inicial

**Base da inspeção:** Resumo, período, cartões, gráficos, pendências, agenda e atalhos observados.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C03-CT01 | Período padrão|Exibir período e data de referência coerentes.|Positivo |
| C03-CT02 | Período personalizado e vazio|Atualizar indicadores com dados do intervalo; tratar ausência de registros.|Filtro |
| C03-CT03 | Intervalo invertido ou datas inválidas|Orientar correção sem resultados enganosos.|Negativo |
| C03-CT04 | Cartões de clientes e matrículas|Comparar ativos, ausentes, sem matrícula, personais, desistências e renovações com as listas de origem.|Consistência |
| C03-CT05 | Pendências e avaliações|Conferir totais e detalhamento com os registros correspondentes.|Consistência |
| C03-CT06 | Gráficos por horário e dia|Conferir filtros, legendas, valores e período considerado.|Consistência |
| C03-CT07 | Agenda, últimas entradas e aniversariantes|Conferir datas, horários, ordenação e estado sem resultados.|Positivo |
| C03-CT08 | Atalhos Ver detalhes, Ver todas e Ver agenda|Abrir o detalhamento correto sem links sem efeito.|Navegação |
| C03-CT09 | Cobrar agora, Enviar mensagem e Cobrar todos|Documentar destinatários, confirmação e resultado somente com contatos de teste; não enviar a alunos existentes.|Condicional |
| C03-CT10 | Inteligência de retenção e análise completa|Conferir atualização, contagens e abertura dos detalhes.|Consistência |

### C04 — Dashboard

**Base da inspeção:** Tela /dash aberta; exibe gráficos e título Despesas Fixas, a reproduzir.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C04-CT01 | Correspondência do título|Verificar e gravar se Dashboard continua exibindo título de outro módulo.|Investigação |
| C04-CT02 | Gráficos de clientes|Conferir frequência, idade e sexo com dados de teste conhecidos.|Consistência |
| C04-CT03 | Gráficos de matrículas|Conferir agrupamentos por mês e por plano.|Consistência |
| C04-CT04 | Gráficos financeiros e cancelamentos|Conferir período, totais e distribuição por meio de pagamento.|Consistência |
| C04-CT05 | Gráficos de avaliações|Conferir agrupamento por mês e personal.|Consistência |
| C04-CT06 | Gráficos sem dados e atualização|Evitar valores inventados ou gráficos antigos após alterações.|Negativo |
| C04-CT07 | Ver Inteligência|Abrir a área de inteligência correspondente.|Navegação |

### C05 — Check-in

**Base da inspeção:** Busca, abas, unidade, filtros, entrada rápida e check-in manual observados.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C05-CT01 | Buscar por nome, código e plano|Retornar os clientes correspondentes e tratar busca sem resultado.|Filtro |
| C05-CT02 | Alternar abas de presença|Filtrar Todos, Presentes agora, Não compareceram e Check-in pendente corretamente.|Filtro |
| C05-CT03 | Filtros e seleção de unidade|Restringir registros e indicadores à seleção.|Filtro |
| C05-CT04 | Check-in manual de cliente elegível|Registrar uma entrada e refletir presença e horário.|Positivo |
| C05-CT05 | Código vazio, inexistente ou inválido|Impedir entrada inválida e exibir orientação.|Negativo |
| C05-CT06 | Check-in repetido|Aplicar a regra de duplicidade sem multiplicar entradas por clique duplo.|Negativo |
| C05-CT07 | Cliente inativo, sem matrícula ou inadimplente|Conferir a regra de liberação definida para cada situação.|Regra a confirmar |
| C05-CT08 | QR Code|Verificar leitura válida, inválida e permissão de câmera negada; exige dispositivo.|Condicional |
| C05-CT09 | Indicadores e presentes agora|Conferir atualização e consistência com Presenças.|Consistência |

### C06 — Presenças

**Base da inspeção:** Busca por cliente e períodos De/Até, Hoje, Esta semana e Este mês observados.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C06-CT01 | Busca por cliente existente e inexistente|Listar somente presenças correspondentes ou estado vazio.|Filtro |
| C06-CT02 | Atalhos de período|Hoje, semana e mês devem preencher o intervalo e buscar corretamente.|Filtro |
| C06-CT03 | Período personalizado|Incluir registros dos limites inicial e final conforme regra de horário.|Limite |
| C06-CT04 | Datas vazias, inválidas ou invertidas|Orientar correção, sem erro técnico.|Negativo |
| C06-CT05 | Total, alunos distintos, média e dias|Recalcular indicadores corretamente, inclusive em intervalo sem presenças.|Consistência |
| C06-CT06 | Check-in refletido na consulta|Entrada registrada deve aparecer com cliente, unidade, data e hora corretos.|Integração |

### C07 — SifitBox — Aulas

**Base da inspeção:** Período, Buscar e Gerar aulas observados; sem aulas exibidas no período consultado.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C07-CT01 | Consultar aulas por período|Listar somente aulas do intervalo, com mensagem clara quando vazio.|Filtro |
| C07-CT02 | Período inválido|Rejeitar datas invertidas ou incompletas.|Negativo |
| C07-CT03 | Gerar aulas de turma recorrente|Criar as aulas conforme dias, horários e vigência configurados.|Condicional |
| C07-CT04 | Gerar novamente o mesmo período|Verificar prevenção de aulas duplicadas.|Negativo |
| C07-CT05 | Detalhar aula gerada|Mapear participantes, vagas e ações que surgirem após existir aula de teste.|Dependência |
| C07-CT06 | Reserva, cancelamento e lotação, se disponíveis|Verificar regras de inscrição e vagas; expandir em casos após abrir aula.|Dependência |

### C08 — Clientes

**Base da inspeção:** Listagem e formulário de novo cliente inspecionados.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C08-CT01 | Cadastro mínimo válido|Salvar com nome, status, sexo e nascimento, indicados como obrigatórios na tela.|Positivo |
| C08-CT02 | Cadastro completo válido|Persistir documentos, contatos, endereço, responsável e observações.|Positivo |
| C08-CT03 | Nome vazio ou só espaços|Rejeitar ausência de nome sem criar registro incompleto.|Negativo |
| C08-CT04 | Status e sexo não selecionados|Validar obrigatoriedade indicada na interface.|Negativo |
| C08-CT05 | Nascimento vazio, impossível ou futuro|Aplicar regra de data e idade; confirmar limites de idade com o professor.|Negativo |
| C08-CT06 | Nome com acentos, apóstrofo e hífen|Preservar nomes legítimos sem quebra da interface.|Positivo |
| C08-CT07 | CPF do cliente e do responsável|Testar máscara, formato, dígitos inválidos e eventual unicidade em casos separados.|Negativo |
| C08-CT08 | RG e tipo sanguíneo|Confirmar formatos aceitos, campos opcionais e preservação dos valores.|Regra a confirmar |
| C08-CT09 | Telefone, celular e emergência|Testar máscara, número incompleto, texto e extensão aceita.|Negativo |
| C08-CT10 | E-mail válido e inválido|Aceitar formato válido e orientar correção de formato inválido.|Negativo |
| C08-CT11 | CEP e endereço|Testar CEP válido/inválido, endereço manual e eventual preenchimento automático.|Positivo/negativo |
| C08-CT12 | País, estado e cidade|Atualizar seleções dependentes e impedir combinação geográfica incoerente.|Interação |
| C08-CT13 | Foto JPG, PNG e GIF|Aceitar formatos anunciados e exibir imagem após reabrir o cadastro.|Upload |
| C08-CT14 | Foto inválida, grande e cancelamento|Tratar formato não permitido, limite de tamanho a confirmar e seleção cancelada.|Negativo |
| C08-CT15 | Código do leitor e Sempre Liberado|Verificar formato, eventual duplicidade e efeito na liberação com regra confirmada.|Condicional |
| C08-CT16 | Acesso ao aplicativo|Verificar campos, unicidade e funcionamento com usuário de teste; credenciais não entram nas evidências públicas.|Condicional |
| C08-CT17 | Dados do responsável|Persistir nome, telefone, profissão e CPF; confirmar exigência para menores.|Regra a confirmar |
| C08-CT18 | Estado civil, profissão, observação e complemento|Preservar textos, acentos e quebras de linha dentro dos limites confirmados.|Positivo |
| C08-CT19 | Filtros da listagem|Testar código, nome, status, situação, plano e personal isolados e combinados.|Filtro |
| C08-CT20 | Paginação e quantidade por página|Verificar Anterior, Próxima e opções 20, 50 e 100 sem repetir ou omitir registros.|Lista |
| C08-CT21 | Visualizar e editar cliente de teste|Conferir dados e se alterações persistem após atualizar a página.|Cadastro |
| C08-CT22 | Excluir e cancelar exclusão|Usar somente registro descartável e conferir dependências antes da exclusão.|Condicional |
| C08-CT23 | Cancelar novo cadastro|Voltar sem criar cliente nem gravar alterações.|Negativo |

### C09 — Matrículas

**Base da inspeção:** Listagem e cadastro inspecionados; ocorreu erro de servidor no cadastro.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C09-CT01 | Abrir cadastro e carregar seleções|Carregar moedas, modalidades e pagamentos; reproduzir erro observado antes de registrar bug.|Investigação |
| C09-CT02 | Selecionar cliente por código ou pesquisa|Vincular a matrícula ao cliente correto.|Positivo |
| C09-CT03 | Cadastrar matrícula válida|Gravar cliente, modalidade/plano, datas, status e condições financeiras.|Positivo |
| C09-CT04 | Cliente ou modalidade ausente|Impedir matrícula sem os vínculos exigidos.|Negativo |
| C09-CT05 | Datas, status e renovada|Validar datas e aplicação de Ativo, Inativo, Finalizado e renovação.|Regra a confirmar |
| C09-CT06 | Taxa, parcela, desconto e total|Conferir cálculo e arredondamento com valores conhecidos.|Cálculo |
| C09-CT07 | Valores negativos, texto e desconto excessivo|Rejeitar ou tratar entradas incompatíveis com a regra confirmada.|Negativo |
| C09-CT08 | Dia do vencimento|Testar limites, mês curto e valores fora de faixa.|Limite |
| C09-CT09 | Meio de pagamento e Pag. Via Sistema|Verificar campos condicionais; integração somente em ambiente de teste.|Condicional |
| C09-CT10 | Matrícula duplicada ou sobreposta|Conferir a regra para aluno com matrícula existente.|Regra a confirmar |
| C09-CT11 | Pesquisa, período e paginação|Conferir filtros e contagens da listagem.|Filtro |
| C09-CT12 | Renovação, edição e cancelamento, se disponíveis|Mapear ações após criar registro de teste e conferir efeitos em clientes e financeiro.|Dependência |
| C09-CT13 | Cancelar formulário|Sair sem gerar matrícula ou cobrança.|Negativo |
| C09-CT14 | Integração com contas a receber|Comparar títulos, parcelas, datas e valores efetivamente gerados.|Integração |

### C10 — Avaliações

**Base da inspeção:** Listagem e modal de cadastro inspecionados; medidas da realização ainda dependem de avaliação de teste.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C10-CT01 | Buscar por código, nome e status|Filtrar Pendente e Realizado corretamente.|Filtro |
| C10-CT02 | Agendar avaliação válida|Vincular aluno, personal, data e horário corretos.|Positivo |
| C10-CT03 | Aluno, personal, data ou hora ausentes|Validar campos obrigatórios conforme regra confirmada.|Negativo |
| C10-CT04 | Data e horário inválidos|Rejeitar valores impossíveis sem erro técnico.|Negativo |
| C10-CT05 | Conflito de agenda|Conferir regra de avaliações simultâneas para mesmo personal ou aluno.|Regra a confirmar |
| C10-CT06 | Realizar avaliação de teste|Mapear cada medida, unidade e cálculo no formulário de realização.|Dependência |
| C10-CT07 | Medidas negativas, zero e fora dos limites|Testar cada campo numérico após confirmar a fórmula e faixa aceitáveis.|Dependência |
| C10-CT08 | Salvar, reabrir e editar avaliação|Preservar medidas e atualizar status e resultados coerentemente.|Dependência |
| C10-CT09 | Imprimir e relatório completo PDF|Conferir identificação, datas, medidas, cálculos e layout.|Relatório |
| C10-CT10 | Link de avaliação e demais ações por ícone|Identificar função e destinatário antes de usar; evitar exposição de dados reais.|Condicional |
| C10-CT11 | Cancelar e excluir registro de teste|Confirmar efeito e preservação dos registros relacionados.|Condicional |

### C11 — Contas a Receber

**Base da inspeção:** Listagem e cadastro inspecionados.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C11-CT01 | Cadastrar conta válida|Gravar cliente, título, valor, vencimento, moeda e observação.|Positivo |
| C11-CT02 | Cliente, título e valor ausentes|Aplicar campos obrigatórios confirmados e não criar conta incompleta.|Negativo |
| C11-CT03 | Valor negativo, zero, texto ou casas decimais|Validar regra monetária e arredondamento.|Limite |
| C11-CT04 | Datas de vencimento e recebimento|Validar formatos e coerência entre datas e status.|Negativo |
| C11-CT05 | Status pendente, recebido e cancelado|Refletir status coerente na listagem e no resumo financeiro.|Positivo |
| C11-CT06 | Recebimento parcial e resíduo|Comparar recebido, saldo restante e eventual título residual.|Cálculo |
| C11-CT07 | Recebimento maior que saldo|Aplicar regra de excedente e impedir inconsistência financeira.|Negativo |
| C11-CT08 | Criar cópias|Conferir quantidade, vencimentos e ausência de duplicidade indevida.|Condicional |
| C11-CT09 | Tipo e local de recebimento|Salvar as referências corretas e conferir campos condicionais.|Positivo |
| C11-CT10 | Filtros e atalhos de datas|Testar código, cliente, tipo de data, intervalo, status e períodos rápidos.|Filtro |
| C11-CT11 | Entradas, saídas, líquido e pendências|Conciliar resumo e registros exibidos no período.|Cálculo |
| C11-CT12 | Editar, cancelar e eventual estorno|Mapear ações disponíveis e seus efeitos em caixa, somente em dados de teste.|Condicional |

### C12 — Contas a Pagar

**Base da inspeção:** Listagem e cadastro inspecionados.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C12-CT01 | Cadastrar conta válida de fornecedor|Gravar título, fornecedor, documento, vencimento, valor e local.|Positivo |
| C12-CT02 | Despesa de colaborador|Alternar o tipo e conferir seleção do colaborador e campos dependentes.|Positivo |
| C12-CT03 | Despesa fixa e variável|Aplicar a categoria correta e eventual recorrência.|Positivo |
| C12-CT04 | Referência, título, documento ou valor ausentes|Validar os campos exigidos pelo tipo escolhido.|Negativo |
| C12-CT05 | Valores e datas inválidos|Rejeitar entradas incompatíveis sem registrar pagamento incorreto.|Negativo |
| C12-CT06 | Status pendente, pago e cancelado|Conferir saldo e situação após cada operação permitida.|Positivo |
| C12-CT07 | Pagamentos parciais, se disponíveis|Conferir saldo e impedir duplicidade ou quitação indevida.|Condicional |
| C12-CT08 | Filtros por código, pessoa, data e status|Retornar registros correspondentes, inclusive ausência de resultados.|Filtro |
| C12-CT09 | Total a pagar, restante e atrasadas|Conciliar totais com a lista e o período.|Cálculo |
| C12-CT10 | Paginação|Conferir troca de páginas e quantidade exibida.|Lista |
| C12-CT11 | Cancelar e reabrir cadastro|Não salvar no cancelamento e persistir somente alterações confirmadas.|Negativo |
| C12-CT12 | Integração com caixa|Conferir lançamento de saída e saldo com dados de teste.|Integração |

### C13 — Ficha de Treino

**Base da inspeção:** Listagem e modal inicial inspecionados; editor de exercícios depende de ficha criada.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C13-CT01 | Criar ficha com aluno, personal e objetivo|Vincular corretamente os dados iniciais.|Positivo |
| C13-CT02 | Aluno ou referência obrigatória ausente|Impedir ficha inválida com mensagem clara.|Negativo |
| C13-CT03 | Data final anterior à inicial|Impedir período incoerente conforme regra confirmada.|Negativo |
| C13-CT04 | Observação e persistência|Preservar texto e datas após salvar e reabrir.|Positivo |
| C13-CT05 | Usar Modelo de Ficha|Selecionar modelo e conferir conteúdo copiado sem alterar o original.|Dependência |
| C13-CT06 | Editor de exercícios|Mapear inclusão, remoção, ordem, séries, repetições e cargas que estiverem disponíveis.|Dependência |
| C13-CT07 | Limites de séries, repetições e cargas|Testar vazios, zero, negativos e decimais conforme cada campo disponível.|Dependência |
| C13-CT08 | Status, vencimento e indicadores|Conferir ativas, vencendo em 7 dias e inativas/canceladas.|Consistência |
| C13-CT09 | Busca e paginação|Conferir código, aluno, status e navegação da tabela.|Filtro |
| C13-CT10 | Cancelar criação|Não criar ficha ao fechar ou cancelar o modal.|Negativo |

### C14 — Exercícios

**Base da inspeção:** Biblioteca e opções de importar padrão/cadastrar manualmente observadas; erro de servidor exibido.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C14-CT01 | Carregamento da biblioteca|Distinguir biblioteca vazia de falha no servidor; reproduzir erro observado.|Investigação |
| C14-CT02 | Importar biblioteca padrão|Conferir grupos e exercícios criados em conjunto de teste autorizado.|Condicional |
| C14-CT03 | Repetir importação|Verificar prevenção de duplicação de biblioteca.|Condicional |
| C14-CT04 | Cadastro manual|Abrir o caminho para grupos musculares e mapear cadastro de exercício quando disponível.|Dependência |
| C14-CT05 | Pesquisa, filtros e visualização de exercícios|Detalhar os controles que aparecerem com biblioteca carregada.|Dependência |
| C14-CT06 | Associar exercício à ficha|Conferir vínculo e preservação da biblioteca de origem.|Dependência |

### C15 — Grupos Musculares

**Base da inspeção:** Listagem, filtro Tipo Membro e botão de inclusão observados; formulário não confirmado.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C15-CT01 | Pesquisar código e nome|Retornar correspondências e estado vazio.|Filtro |
| C15-CT02 | Filtrar Inferiores, Superiores e Aeróbio|Exibir grupos da classificação selecionada.|Filtro |
| C15-CT03 | Abrir inclusão e cadastrar grupo|Confirmar funcionamento do botão e mapear campos do formulário.|Dependência |
| C15-CT04 | Nome e classificação inválidos ou vazios|Aplicar validação conforme campos efetivamente disponíveis.|Dependência |
| C15-CT05 | Edição, exclusão e vínculo a exercícios|Mapear ações e preservar referências existentes.|Condicional |
| C15-CT06 | Contadores e paginação|Conferir total e quantidades por classificação.|Consistência |

### C16 — Objetivos de Treino

**Base da inspeção:** Formulário com código, nome e descrição inspecionado.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C16-CT01 | Cadastrar objetivo válido|Salvar nome e descrição e disponibilizar na ficha de treino.|Positivo |
| C16-CT02 | Nome vazio, espaços e duplicidade|Conferir obrigatoriedade e regra de unicidade.|Negativo |
| C16-CT03 | Texto longo e caracteres válidos|Preservar conteúdo dentro do limite confirmado.|Limite |
| C16-CT04 | Pesquisar código e nome|Retornar resultados correspondentes.|Filtro |
| C16-CT05 | Editar, cancelar e excluir, se disponível|Conferir persistência e efeitos sobre fichas vinculadas.|Condicional |

### C17 — Grupos

**Base da inspeção:** Formulário de grupo comercial/caixa inspecionado; não confundir com grupos musculares.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C17-CT01 | Cadastrar grupo válido|Salvar nome, status, Mostrar Home, Tipo Caixa e descrição.|Positivo |
| C17-CT02 | Nome obrigatório|Rejeitar vazio e somente espaços.|Negativo |
| C17-CT03 | Mostrar Home Sim/Não|Conferir o efeito da opção no local previsto pelo sistema.|Regra a confirmar |
| C17-CT04 | Caixa interno e externo|Conferir classificação e uso nos fluxos financeiros.|Integração |
| C17-CT05 | Filtros e edição|Conferir código, nome, status, tipo e persistência.|Filtro |
| C17-CT06 | Excluir grupo vinculado|Verificar tratamento de planos ou registros dependentes em dados de teste.|Condicional |

### C18 — Turmas

**Base da inspeção:** Formulário inspecionado com plano, dias, horários, tempo, experimental e personal.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C18-CT01 | Cadastrar turma válida|Gravar nome, plano, dias, horários e demais opções.|Positivo |
| C18-CT02 | Nome, plano e dias ausentes|Validar regras obrigatórias confirmadas.|Negativo |
| C18-CT03 | Horário final igual ou anterior ao inicial|Aplicar regra de duração e eventual passagem de dia.|Limite |
| C18-CT04 | Tempo em meses inválido|Tratar zero, negativos, texto e valores além do limite.|Limite |
| C18-CT05 | Selecionar vários dias|Preservar exatamente os dias escolhidos.|Interação |
| C18-CT06 | Aula experimental e Tem Personal|Conferir campos condicionais e efeito das opções.|Interação |
| C18-CT07 | Status ativo/inativo e filtros|Conferir disponibilidade e listagem após mudança.|Positivo |
| C18-CT08 | Conflito de turma/horário|Confirmar regra para sobreposição e professor.|Regra a confirmar |
| C18-CT09 | Cancelar, editar e excluir|Conferir persistência e vínculos com matrículas/aulas.|Condicional |

### C19 — Categorias Crossfit

**Base da inspeção:** Formulário com código e nome inspecionado.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C19-CT01 | Cadastrar categoria válida|Salvar e listar categoria.|Positivo |
| C19-CT02 | Nome vazio, espaços ou duplicado|Conferir obrigatoriedade e unicidade.|Negativo |
| C19-CT03 | Pesquisar código e nome|Exibir somente correspondências.|Filtro |
| C19-CT04 | Editar e cancelar|Persistir somente alterações salvas.|Positivo |
| C19-CT05 | Excluir categoria vinculada|Tratar dependências de exercícios sem dados órfãos.|Condicional |

### C20 — SifitBox — Turmas

**Base da inspeção:** Campos de modalidade e turma recorrente observados diretamente na tela.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C20-CT01 | Cadastrar modalidade|Salvar nome, descrição e status.|Positivo |
| C20-CT02 | Cadastrar turma recorrente|Vincular modalidade, horário, dias e vagas.|Positivo |
| C20-CT03 | Modalidade, nome ou dias ausentes|Validar referências e campos necessários.|Negativo |
| C20-CT04 | Vagas zero, negativas, decimais ou excessivas|Aplicar limite e tipo numérico confirmados.|Limite |
| C20-CT05 | Horários inválidos e sobreposição|Tratar intervalos e conflitos conforme regra.|Negativo |
| C20-CT06 | Ativar/inativar modalidade e turma|Conferir efeito na geração e disponibilidade das aulas.|Integração |
| C20-CT07 | Gerar aulas a partir da recorrência|Conferir correspondência com SifitBox — Aulas.|Integração |

### C21 — Caixas

**Base da inspeção:** Listagem, filtros de data/status e Abrir Caixa observados; movimentação não executada.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C21-CT01 | Abrir caixa de teste|Mapear local, responsável, data e valores exigidos antes da execução.|Dependência |
| C21-CT02 | Abertura repetida|Conferir regra para caixa já aberto no mesmo local.|Regra a confirmar |
| C21-CT03 | Movimentos de entrada e saída|Conferir origem, valor, saldo e duplicidade com dados de teste.|Integração |
| C21-CT04 | Fechamento e conferência|Mapear valores calculados, informados e divergências.|Dependência |
| C21-CT05 | Operar caixa fechado|Verificar bloqueios e regra de reabertura, se existente.|Condicional |
| C21-CT06 | Filtros e paginação|Conferir período, status e indicadores de abertos/fechados.|Filtro |

### C22 — Pagar.me

**Base da inspeção:** Painel e ações de saque, cobrança, extrato e configuração observados; integração não validada.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C22-CT01 | Carregamento e ausência de integração|Mostrar estado real e erro compreensível; não confundir valores ilustrativos com dados reais.|Investigação |
| C22-CT02 | Saldos e recebíveis|Comparar disponível, processamento, futuro e recebido com ambiente sandbox autorizado.|Condicional |
| C22-CT03 | Transações e assinaturas|Conferir valores, métodos, status e períodos.|Condicional |
| C22-CT04 | Extrato, relatório e previsão|Verificar destinos e filtros sem executar transferência.|Condicional |
| C22-CT05 | Nova cobrança|Testar somente no sandbox, sem cobrança ou mensagem para cliente real.|Condicional |
| C22-CT06 | Saque e configurações da integração|Documentar existência e pré-condições; execução fora do escopo inicial até haver sandbox e autorização específica.|Condicional |

### C23 — Despesas Fixas

**Base da inspeção:** Listagem, filtros e recorrências observados; formulário de inclusão não confirmado.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C23-CT01 | Cadastro e edição de despesa|Abrir formulário e mapear campos antes de elaborar roteiro de execução.|Dependência |
| C23-CT02 | Nome, valor e recorrência|Validar obrigatoriedade, formato monetário e opções disponíveis.|Dependência |
| C23-CT03 | Recorrências diária, semanal, mensal, trimestral, semestral e anual|Conferir datas geradas, inclusive mês curto.|Condicional |
| C23-CT04 | Status ativo/inativo|Conferir efeito na geração de próximas despesas.|Integração |
| C23-CT05 | Pesquisa e total listado|Conferir código, nome, status, recorrência e somatória.|Filtro |
| C23-CT06 | Geração em contas a pagar|Conferir títulos e evitar geração duplicada no mesmo período.|Integração |

### C24 — Relatórios

**Base da inspeção:** Sete tipos de PDF observados; não foram gerados arquivos.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C24-CT01 | PDF de avaliações|Conferir identificação, período, registros e dados apresentados.|Relatório |
| C24-CT02 | PDF de clientes|Conferir filtros, campos e correspondência com a listagem.|Relatório |
| C24-CT03 | PDF de colaboradores|Conferir equipe, campos e seleção aplicada.|Relatório |
| C24-CT04 | PDF de matrículas|Conferir contratos, planos, datas e valores apresentados.|Relatório |
| C24-CT05 | PDF de contas a receber|Conferir status, pagamento, valores e totalizações existentes.|Relatório |
| C24-CT06 | PDF de contas a pagar|Conferir despesas, pagamentos, filtros e totalizações existentes.|Relatório |
| C24-CT07 | PDF de caixas normal e detalhado|Comparar movimentos, valores e detalhamento; executar cada formato disponível.|Relatório |
| C24-CT08 | Trocar tipo de relatório|Atualizar filtros e habilitar geração quando requisitos estiverem preenchidos.|Interação |
| C24-CT09 | Datas inválidas ou período vazio|Tratar erro e ausência de dados claramente.|Negativo |
| C24-CT10 | Limites de data e grandes listas|Incluir registros de fronteira e conferir todas as páginas do PDF.|Limite |
| C24-CT11 | Layout do PDF|Conferir acentos, quebras, cabeçalhos, margens e ausência de cortes.|Interface |
| C24-CT12 | Conferência com sistema e banco|Comparar amostra controlada; não atribuir ao PDF total que o sistema não apresenta como requisito.|Consistência |

### C25 — Prospecção

**Base da inspeção:** Cadastro de lead inspecionado.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C25-CT01 | Cadastrar lead válido|Salvar nome, estágio, e-mail, telefone e observação.|Positivo |
| C25-CT02 | Nome vazio e contatos inválidos|Validar os campos exigidos e formatos.|Negativo |
| C25-CT03 | Alterar estágio|Preservar o lead e refletir a nova etapa nas consultas.|Positivo |
| C25-CT04 | Pesquisar nome, e-mail, telefone ou código|Retornar os contatos correspondentes.|Filtro |
| C25-CT05 | Combinar estágio com pesquisa e Limpar|Restringir consulta e restaurar estado inicial.|Filtro |
| C25-CT06 | Duplicidade de contato|Confirmar a regra para e-mail/telefone repetidos.|Regra a confirmar |
| C25-CT07 | Cancelar, editar e excluir lead de teste|Conferir persistência e remoção somente do registro indicado.|Condicional |

### C26 — Planos

**Base da inspeção:** Formulário inspecionado com tipos de cobrança, parcelas, valores, personal e dependentes.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C26-CT01 | Cadastrar plano recorrente|Salvar nome, grupo, status, parcelas e valores coerentes.|Positivo |
| C26-CT02 | Plano por diária|Conferir campos e cálculo específicos desse tipo.|Positivo |
| C26-CT03 | Plano por período fixo|Conferir duração, datas/parcelas e valor aplicável.|Positivo |
| C26-CT04 | Nome obrigatório e grupo|Rejeitar nome vazio e confirmar regra de vínculo a grupo.|Negativo |
| C26-CT05 | Parcelas e valores inválidos|Testar zero, negativos, texto, decimais e limites.|Limite |
| C26-CT06 | Personal e função dos professores|Conferir seleções condicionais e uso na matrícula.|Interação |
| C26-CT07 | Dependentes de 0 a 6|Conferir cada limite e reflexo no cadastro da matrícula.|Limite |
| C26-CT08 | Status ativo/inativo|Conferir disponibilidade para novas matrículas e preservação do histórico.|Integração |
| C26-CT09 | Ranking de planos e receita estimada|Conciliar quantidades e cálculo com matrículas consideradas.|Cálculo |
| C26-CT10 | Pesquisar e editar plano|Conferir código, nome, status e persistência dos valores.|Filtro |
| C26-CT11 | Salvar também na Pagar.me|Testar somente com integração sandbox autorizada.|Condicional |
| C26-CT12 | Excluir plano vinculado|Tratar matrículas existentes sem perder histórico.|Condicional |

### C27 — Modelos de Contrato

**Base da inspeção:** Editor, formatação, variáveis e preview observados.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C27-CT01 | Criar modelo com nome e conteúdo|Salvar texto e status corretamente.|Positivo |
| C27-CT02 | Nome ou conteúdo vazios|Conferir campos obrigatórios.|Negativo |
| C27-CT03 | Formatação do texto|Testar títulos, parágrafo, negrito, itálico, sublinhado e tachado.|Interação |
| C27-CT04 | Inserir variáveis|Testar dados do aluno, plano, academia e contrato sem corromper o texto.|Interação |
| C27-CT05 | Atualizar preview|Conferir renderização e tratamento de variáveis sem dados.|Positivo |
| C27-CT06 | Editar, cancelar e reabrir|Preservar formatação somente após salvar.|Positivo |
| C27-CT07 | Aplicar modelo a contrato de teste|Conferir substituição de variáveis sem assinar contrato real.|Condicional |

### C28 — Tipos de Pagamento

**Base da inspeção:** Formulário inspecionado.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C28-CT01 | Cadastrar tipo válido|Salvar nome, status, débito/crédito e opções do sistema.|Positivo |
| C28-CT02 | Nome vazio e duplicidade|Conferir obrigatoriedade e unicidade.|Negativo |
| C28-CT03 | Escolher Bandeira Sim/Não|Conferir exigência de bandeira nos fluxos relacionados.|Interação |
| C28-CT04 | Pagamento pelo sistema Sim/Não|Conferir campos e dependência de gateway.|Condicional |
| C28-CT05 | Filtros, edição e status|Conferir disponibilidade e preservação de pagamentos históricos.|Integração |

### C29 — Bandeiras

**Base da inspeção:** Formulário inspecionado com taxas e Adicionar Parcela.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C29-CT01 | Cadastrar bandeira e taxas válidas|Persistir nome e parâmetros financeiros.|Positivo |
| C29-CT02 | Taxas negativas, texto e limites|Conferir validação e arredondamento.|Limite |
| C29-CT03 | Adicionar e remover parcela, se disponível|Salvar condições de cada faixa sem duplicação indevida.|Interação |
| C29-CT04 | Multiplicar taxa adicional por mês|Conferir cálculo com opção marcada e desmarcada.|Cálculo |
| C29-CT05 | Pesquisa, edição e dependências|Conferir código/nome e vínculos a meios de pagamento.|Integração |

### C30 — Colaboradores

**Base da inspeção:** Cadastro inspecionado; inclui tipos Admin, Normal e Sem login.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C30-CT01 | Cadastrar colaborador sem login|Persistir dados pessoais, documentos, contato e endereço.|Positivo |
| C30-CT02 | Nome, nascimento e sexo|Aplicar obrigatoriedade e validade conforme regras confirmadas.|Negativo |
| C30-CT03 | CPF, RG e CREF|Verificar formato, opcionalidade e eventual unicidade.|Negativo |
| C30-CT04 | E-mail e telefones|Testar formatos válidos, inválidos e incompletos.|Negativo |
| C30-CT05 | País, estado, cidade e CEP|Conferir seleções dependentes e persistência do endereço.|Interação |
| C30-CT06 | Tipos Admin, Normal e Sem login|Documentar campos e permissões; criação de acessos depende de autorização específica.|Condicional |
| C30-CT07 | Login repetido e autenticação|Executar apenas com contas de teste autorizadas e registrar resultado sem expor senhas.|Condicional |
| C30-CT08 | Status ativo/inativo|Conferir regras de acesso e disponibilidade como personal/avaliador.|Condicional |
| C30-CT09 | Biometria e observação|Conferir formato e persistência; equipamento exige teste acompanhado.|Condicional |
| C30-CT10 | Busca, paginação e indicadores|Conferir código, nome, ativos e personais.|Filtro |

### C31 — Funções

**Base da inspeção:** Formulário inspecionado com tipo de funcionário, Personal e Avaliador.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C31-CT01 | Cadastrar função válida|Salvar nome, interno/externo, personal e avaliador.|Positivo |
| C31-CT02 | Nome obrigatório|Rejeitar vazio e espaços; confirmar duplicidade.|Negativo |
| C31-CT03 | Combinações de Personal e Avaliador|Conferir disponibilidade de colaboradores nos módulos relacionados.|Integração |
| C31-CT04 | Filtro por tipo e pesquisa|Retornar as funções correspondentes.|Filtro |
| C31-CT05 | Edição e exclusão com vínculo|Preservar integridade de colaboradores existentes.|Condicional |

### C32 — Fornecedores

**Base da inspeção:** Formulário inspecionado com pessoa física/jurídica, documentos, contatos e endereço.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C32-CT01 | Cadastrar pessoa física|Conferir campos e documento adequados ao tipo.|Positivo |
| C32-CT02 | Cadastrar pessoa jurídica|Conferir CNPJ e dados cadastrais correspondentes.|Positivo |
| C32-CT03 | Alternar tipo de pessoa|Atualizar máscara e validação do documento.|Interação |
| C32-CT04 | Nome e documento inválidos|Testar obrigatoriedade, formato e eventual duplicidade.|Negativo |
| C32-CT05 | E-mail e telefones|Validar formatos e números incompletos.|Negativo |
| C32-CT06 | Estado, cidade e CEP|Conferir dependências e endereço salvo.|Interação |
| C32-CT07 | Status, edição e observação|Persistir somente alterações confirmadas.|Positivo |
| C32-CT08 | Vínculo com conta a pagar|Selecionar fornecedor correto e tratar exclusão com dependências.|Integração |

### C33 — Tipos de Documentos

**Base da inspeção:** Formulário inspecionado com aplicação Conta/Fornecedor ou Colaborador.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C33-CT01 | Cadastrar tipo para fornecedor|Disponibilizar tipo no fluxo financeiro correspondente.|Positivo |
| C33-CT02 | Cadastrar tipo para colaborador|Disponibilizar somente nos contextos adequados.|Positivo |
| C33-CT03 | Nome vazio ou repetido|Conferir obrigatoriedade e unicidade.|Negativo |
| C33-CT04 | Pesquisar e filtrar aplicação|Retornar registros compatíveis.|Filtro |
| C33-CT05 | Editar, cancelar e excluir com vínculo|Preservar documentos e lançamentos existentes.|Condicional |

### C34 — Atividades

**Base da inspeção:** Formulário inspecionado com nome, pontuação e descrição.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C34-CT01 | Cadastrar atividade com pontuação|Persistir nome, valor e descrição.|Positivo |
| C34-CT02 | Atividade sem pontuação|Confirmar se ausência e zero são aceitos e como são contados.|Regra a confirmar |
| C34-CT03 | Pontuação negativa, decimal ou texto|Aplicar regra numérica confirmada.|Limite |
| C34-CT04 | Nome vazio e texto longo|Validar nome e limite da descrição.|Negativo |
| C34-CT05 | Pesquisar, editar e conferir indicadores|Conferir com/sem pontuação e com descrição.|Consistência |

### C35 — Pontuação

**Base da inspeção:** Formulário inspecionado com tipo Mensal/Período e produtos de resgate.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C35-CT01 | Cadastrar pontuação mensal|Salvar nome, status e regras mensais.|Positivo |
| C35-CT02 | Cadastrar pontuação por período|Salvar intervalo e conferir vigência.|Positivo |
| C35-CT03 | Datas invertidas ou incompletas|Impedir vigência incoerente.|Negativo |
| C35-CT04 | Adicionar produto de resgate|Vincular produto correto e mapear quantidade/pontos que surgirem.|Interação |
| C35-CT05 | Produto duplicado ou indisponível|Aplicar regra de resgate e duplicidade.|Negativo |
| C35-CT06 | Ativar, inativar e editar|Conferir efeito na vigência e preservar histórico.|Integração |
| C35-CT07 | Pesquisa e indicadores|Conferir total, ativas, mensais e por período.|Consistência |

### C36 — Produtos

**Base da inspeção:** Formulário inspecionado com Venda/Pontuação, preço e arquivo.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C36-CT01 | Cadastrar produto de venda|Salvar nome, status, descrição, preço e imagem.|Positivo |
| C36-CT02 | Cadastrar produto de pontuação|Conferir campos condicionais e disponibilidade para resgate.|Positivo |
| C36-CT03 | Nome vazio ou duplicado|Conferir obrigatoriedade e unicidade.|Negativo |
| C36-CT04 | Preço negativo, zero, texto e decimais|Validar regra monetária e arredondamento.|Limite |
| C36-CT05 | Upload válido e inválido|Confirmar formatos/tamanho, visualização e cancelamento da seleção.|Upload |
| C36-CT06 | Pesquisar por código, nome, tipo e status|Conferir filtros isolados e combinados.|Filtro |
| C36-CT07 | Editar, inativar e excluir com vínculo|Preservar histórico de vendas/resgates quando aplicável.|Condicional |

### C37 — Enquetes

**Base da inspeção:** Formulário inspecionado com nome, status, pergunta e resposta inicial.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C37-CT01 | Cadastrar enquete válida|Salvar nome, pergunta e alternativas permitidas.|Positivo |
| C37-CT02 | Nome, pergunta e resposta vazios|Conferir campos obrigatórios e quantidade mínima de alternativas.|Negativo |
| C37-CT03 | Adicionar/remover alternativas, se disponível|Conferir ordem e ausência de respostas vazias.|Dependência |
| C37-CT04 | Alternativas duplicadas e texto longo|Aplicar validações confirmadas.|Negativo |
| C37-CT05 | Ativar/inativar e disponibilidade no aplicativo|Conferir período e visibilidade conforme regras.|Condicional |
| C37-CT06 | Resultados e contagem de respostas|Usar votos de teste e comparar total por alternativa.|Dependência |
| C37-CT07 | Pesquisar e editar enquete respondida|Verificar preservação das respostas e restrições de alteração.|Condicional |

### C38 — Fichas de Anamnese

**Base da inspeção:** Listagem e seleção de aluno para aplicação inspecionadas; perguntas dependem de modelo.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C38-CT01 | Buscar aluno e filtrar status|Retornar fichas corretas e tratar consulta vazia.|Filtro |
| C38-CT02 | Selecionar aluno para nova anamnese|Vincular somente o aluno escolhido.|Positivo |
| C38-CT03 | Aluno ou modelo ausente|Impedir avanço sem pré-condições obrigatórias.|Negativo |
| C38-CT04 | Aplicar modelo de teste|Exibir categorias e perguntas configuradas.|Dependência |
| C38-CT05 | Responder tipos de pergunta disponíveis|Preservar respostas e complementos condicionais.|Dependência |
| C38-CT06 | Finalizar com resposta obrigatória ausente|Orientar quais perguntas faltam.|Negativo |
| C38-CT07 | Salvar rascunho e concluir, se disponível|Conferir transição Pendente/Concluído e persistência.|Dependência |
| C38-CT08 | Consultar ficha concluída|Conferir aluno, modelo, data e respostas sem expor dados de saúde reais nas evidências.|Positivo |

### C39 — Modelos de Anamnese

**Base da inspeção:** Formulário de novo modelo e montador visual inspecionados; erro de servidor observado.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C39-CT01 | Criar modelo válido|Salvar nome, status, descrição e perguntas selecionadas.|Positivo |
| C39-CT02 | Nome vazio ou modelo sem perguntas|Confirmar regras e impedir estrutura inválida.|Negativo |
| C39-CT03 | Buscar pergunta e filtrar categoria|Retornar opções coerentes.|Filtro |
| C39-CT04 | Adicionar e remover pergunta|Atualizar montador e resumo corretamente.|Interação |
| C39-CT05 | Reordenar perguntas, se disponível|Preservar ordem no formulário aplicado.|Dependência |
| C39-CT06 | Pergunta duplicada ou inativa|Aplicar regra de seleção e disponibilidade.|Negativo |
| C39-CT07 | Editar modelo já aplicado|Conferir preservação do histórico das fichas existentes.|Condicional |
| C39-CT08 | Erro no carregamento do montador|Reproduzir erro observado e distinguir falha de ausência de perguntas.|Investigação |

### C40 — Categorias de Anamnese

**Base da inspeção:** Formulário inspecionado com nome, status, ícone e cor.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C40-CT01 | Cadastrar categoria válida|Salvar nome, status, ícone e cor.|Positivo |
| C40-CT02 | Nome vazio ou repetido|Conferir obrigatoriedade e unicidade.|Negativo |
| C40-CT03 | Cor pelo seletor e código|Sincronizar ambos e rejeitar código inválido.|Interação |
| C40-CT04 | Ícone válido e inválido|Exibir ícone ou tratamento compreensível.|Negativo |
| C40-CT05 | Filtro, edição e inativação|Conferir disponibilidade para perguntas/modelos.|Integração |
| C40-CT06 | Exclusão com perguntas vinculadas|Evitar referências quebradas e perda indevida de estrutura.|Condicional |

### C41 — Perguntas de Anamnese

**Base da inspeção:** Formulário inspecionado com nome, pergunta, número, status e tipo de resposta.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C41-CT01 | Cadastrar pergunta Sim/Não|Apresentar as opções corretas na aplicação.|Positivo |
| C41-CT02 | Cadastrar Sim/Não/Não Sei|Preservar cada resposta possível.|Positivo |
| C41-CT03 | Cadastrar Se Sim, qual?|Exibir complemento na condição adequada.|Interação |
| C41-CT04 | Nome ou enunciado vazio|Validar conteúdo necessário.|Negativo |
| C41-CT05 | Número negativo, repetido ou fora da sequência|Confirmar regra de ordem e unicidade.|Limite |
| C41-CT06 | Status inativo|Conferir disponibilidade nos modelos e preservar histórico.|Integração |
| C41-CT07 | Pesquisa, edição e erro no servidor|Conferir carregamento e reproduzir a mensagem observada.|Investigação |

### C42 — Inteligência & Automação

**Base da inspeção:** Central aberta; risco de evasão e aniversariantes observados; outras automações indicadas em desenvolvimento.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C42-CT01 | Carregar automações e atualizar|Exibir estado real, última execução, frequência e canal.|Positivo |
| C42-CT02 | Configurar automação|Mapear campos e validações sem ativar envios reais.|Condicional |
| C42-CT03 | Ativar/desativar e persistir|Executar apenas em configuração de teste autorizada, confirmando frequência e destinatários.|Condicional |
| C42-CT04 | Executar agora|Validar resultado e evitar repetição/envio duplicado em ambiente de teste.|Condicional |
| C42-CT05 | Ver resultados e atividade recente|Relacionar a execução ao registro correto.|Consistência |
| C42-CT06 | Funcionalidades em desenvolvimento|Documentar indisponibilidade; não classificá-las automaticamente como defeito.|Escopo |
| C42-CT07 | Falha ou ausência de canal configurado|Orientar o usuário sem indicar execução bem-sucedida.|Negativo |

### C43 — Resultados IA

**Base da inspeção:** Filtros Hoje/7/30/90 dias e indicadores observados.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C43-CT01 | Alternar períodos|Atualizar resultados e indicadores pelo intervalo escolhido.|Filtro |
| C43-CT02 | Período sem execuções|Exibir estado vazio coerente.|Negativo |
| C43-CT03 | Conferir contagens|Comparar execuções, relatórios, riscos, aniversários e demais indicadores com suas origens.|Consistência |
| C43-CT04 | Conferir achados e eficiência|Associar detalhes à automação e data corretas.|Consistência |
| C43-CT05 | Atualização após execução de teste|Refletir nova execução sem duplicar registros.|Condicional |
| C43-CT06 | Tratar falha de carregamento|Não confundir erro com zero resultados ou conclusão automática.|Negativo |

### C44 — Configurações

**Base da inspeção:** Abas Home, Biometria, Avaliação, Aniversário, Pagamento, Integrações e Design observadas; campos internos ainda a detalhar.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C44-CT01 | Abrir todas as sete abas|Carregar campos corretos e preservar navegação entre abas.|Interação |
| C44-CT02 | Home|Mapear opções e validar efeito no painel em ambiente de teste.|Dependência |
| C44-CT03 | Biometria|Mapear modo de presença e parâmetros; teste depende de hardware quando aplicável.|Dependência |
| C44-CT04 | Avaliação|Mapear método e parâmetros; conferir repercussão nos cálculos.|Dependência |
| C44-CT05 | Aniversário|Mapear configuração e destinatários; qualquer envio exige conta controlada.|Condicional |
| C44-CT06 | Pagamento e Integrações|Mapear campos e mensagens; não registrar chaves ou alterar integração real.|Condicional |
| C44-CT07 | Design|Testar campos visuais e legibilidade após alteração autorizada.|Dependência |
| C44-CT08 | Salvar, cancelar e reabrir|Conferir persistência e descarte das alterações em configuração de teste.|Condicional |

### C45 — Modelos de Ficha

**Base da inspeção:** Listagem com código, título, criador e botão de inclusão observada; editor não confirmado.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C45-CT01 | Buscar código, título e criador|Exibir somente modelos correspondentes.|Filtro |
| C45-CT02 | Abrir criação e mapear editor|Identificar campos e controles efetivos antes do roteiro.|Dependência |
| C45-CT03 | Título vazio e modelo sem exercícios|Conferir regras obrigatórias após acesso ao editor.|Dependência |
| C45-CT04 | Editar, duplicar ou excluir, se disponíveis|Mapear ações e preservar modelos vinculados.|Dependência |
| C45-CT05 | Usar modelo em ficha de aluno|Copiar conteúdo sem modificar o original e manter vínculos corretos.|Integração |
| C45-CT06 | Conferir indicadores|Validar modelos, criadores, listados e sem criador.|Consistência |

### C46 — Aplicativo

**Base da inspeção:** Painéis de notificações, postagens e denúncias observados; não foram enviados avisos.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C46-CT01 | Listar e detalhar notificações|Conferir código, mensagem, data e ações.|Positivo |
| C46-CT02 | Criar notificação válida|Mapear conteúdo, público e confirmação; envio somente a conta de teste autorizada.|Condicional |
| C46-CT03 | Notificação vazia ou longa|Conferir obrigatoriedade e limite antes de enviar.|Negativo |
| C46-CT04 | Ver todas e filtrar postagens pendentes|Conferir navegação e filtros.|Filtro |
| C46-CT05 | Moderação de postagens|Mapear aprovação/rejeição e executar somente sobre postagem de teste.|Condicional |
| C46-CT06 | Consultar e tratar denúncia|Conferir postagem, motivo e ação disponível sem alterar casos de terceiros.|Condicional |
| C46-CT07 | Indicadores e estado vazio|Conferir usuários ativos, novos posts e ausência de registros.|Consistência |

### C47 — Fluxos integrados e conferência no banco

**Base da inspeção:** Planejados; banco não acessado nesta inspeção.

**Status inicial de todos os itens:** Não executado.

| ID | Caso a documentar | Resultado esperado / critério proposto | Tipo |
|---|---|---|---|
| C47-CT01 | Cliente → plano → matrícula → conta a receber|Conferir identificadores, datas e valores ao longo do fluxo.|Integração |
| C47-CT02 | Conta recebida/paga → caixa → relatórios|Conciliar saldo, status e registros financeiros.|Integração |
| C47-CT03 | Turma recorrente → aula → check-in → presença|Conferir dias, vagas, aluno e horários.|Integração |
| C47-CT04 | Grupo muscular → exercício → modelo → ficha|Conferir vínculos e preservar conteúdo original.|Integração |
| C47-CT05 | Categoria → pergunta → modelo → anamnese|Conferir seleção, ordem, respostas e histórico.|Integração |
| C47-CT06 | Persistência após atualização e novo login|Dados confirmados devem continuar disponíveis.|Persistência |
| C47-CT07 | Conferência por SELECT no banco|Após identificar o schema real, comparar somente registros de teste; nunca inventar nomes de tabelas.|Banco |
| C47-CT08 | Cancelar operação e conferir banco|Não criar/alterar registros quando o fluxo foi cancelado.|Banco |
| C47-CT09 | Dependências e exclusões|Verificar integridade referencial e regra de preservação com registros descartáveis.|Banco |
| C47-CT10 | Alterações de colegas no ambiente compartilhado|Registrar data, horário e IDs próprios para não atribuir mudanças de terceiros ao teste.|Controle |

## 4. Ordem sugerida de execução

1. **Preparar documentação e evidências:** criar esta lista no GitHub, estabelecer os IDs, registrar navegador/SO e preparar o Jam.
2. **Login e navegação:** C01–C04. Gravar login válido, inválido e campos vazios separadamente.
3. **Cadastros básicos necessários:** grupos, planos, tipos de pagamento, funções, objetivos e demais referências usadas no fluxo escolhido.
4. **Clientes e matrículas:** C08–C09. Usar nomes como “QA_ADRIAN_20261012_001” e anotar o ID realmente gerado.
5. **Financeiro e relatórios:** contas a receber/pagar, caixa e PDFs, utilizando somente dados de teste.
6. **Treinamento, turmas e presença:** preparar referências, criar ficha/turma de teste e conferir os efeitos.
7. **Saúde:** categorias → perguntas → modelos → anamnese; avaliações com medidas fictícias.
8. **Módulos complementares:** prospecção, produtos, atividades, pontuação, enquetes e modelos de contrato.
9. **Aplicativo, automações e configurações:** avaliar somente fluxos disponíveis; envios e integrações devem usar ambiente/controlados de teste.
10. **Conferência cruzada e fechamento:** completar C47, registrar bloqueios, revisar links e atualizar o relatório final.

Não executar centenas de casos de uma vez. Trabalhar por um cenário pequeno, gravar, documentar e fazer commit antes de iniciar o próximo.

## 5. Como gravar com a extensão Jam

O PDF do professor indica **Jam**:
https://chromewebstore.google.com/detail/jam/iohjgamcilhbgmhbnllfolmkmmekfmci

A página oficial descreve gravação, captura de tela e compartilhamento por link:
https://jam.dev/capture

### Preparação

1. Instalar a extensão pelo endereço indicado e concluir sua configuração.
2. Fixar o ícone no navegador, se desejar.
3. Abrir apenas a tela necessária ao caso de teste.
4. Preparar os dados fictícios e o roteiro antes de iniciar.
5. Preferir captura da aba para fluxos dentro do SIFIT. Se for necessário mostrar outra janela, como banco de dados, selecionar a captura de janela/tela disponibilizada pela extensão.
6. Fechar outras abas/janelas com dados particulares. O Jam pode incluir logs e requisições: revisar o que será compartilhado, especialmente em testes de login. Senhas, chaves, dados de saúde e contatos reais não devem aparecer em evidências públicas.

### Um vídeo por caso simples

1. Identificar o caso: **C01-CT02 — Login com senha incorreta**.
2. Iniciar a gravação na extensão.
3. Mostrar a condição inicial.
4. Executar exatamente o roteiro, com cliques e digitação visíveis.
5. Mostrar a mensagem ou resultado final tempo suficiente para leitura.
6. Encerrar a gravação e revisar.
7. Dar ao vídeo o mesmo ID do caso e uma descrição curta.
8. Copiar o link de compartilhamento efetivamente gerado.
9. Confirmar que o professor consegue abrir o link com as permissões escolhidas.
10. Inserir o link no caso de teste e no relatório de execução.

Um único vídeo pode cobrir um fluxo integrado maior, mas cada caso deverá apontar seu trecho por tempo inicial/final. Evitar vídeo longo sem identificação das ações.

**Gravar também os testes que passam.** Um teste negativo passa quando o sistema rejeita corretamente uma entrada inválida. “Negativo” não significa “reprovado”.

O PDF vincula explicitamente prints passo a passo até o banco e vídeo no Google Drive ao trabalho em grupo do TCC. Para o SIFIT individual, ele orienta seguir o repositório de exemplo, que referencia evidências no Jam. Como combinado nesta atividade, vamos registrar as execuções do SIFIT em vídeo também. Usar Drive se houver orientação complementar ou necessidade de disponibilizar arquivos exportados; não presumir que todo vídeo do SIFIT obrigatoriamente precisa estar nas duas plataformas.

## 6. Organização no GitHub conforme o modelo do professor

A estrutura abaixo adapta os quatro documentos principais e a pasta de cenários do modelo, acrescentando o inventário e as evidências.

| Caminho proposto | Conteúdo |
|---|---|
| README.md | Apresentação, objetivo, índice e progresso real |
| SIFIT/0-inventario-casos.md | Este inventário e suas revisões |
| SIFIT/1-analise-de-requisitos.md | RFs, fontes, regras confirmadas e dúvidas |
| SIFIT/2-plano-de-testes.md | Objetivo, escopo, ambiente, técnicas, prioridades, cronograma e limitações |
| SIFIT/3-relatorio-de-bugs.md | Defeitos reproduzidos, severidade, passos e evidências |
| SIFIT/4-relatorio-dos-testes.md | Execuções, resultados, cobertura e conclusão baseada em evidências |
| SIFIT/cenarios-de-testes/C01-login.md | Casos do cenário de login; repetir por cenário |
| SIFIT/evidencias/C01/C01-CT02-resultado.png | Prints com o mesmo ID do caso |
| Links Jam dentro dos casos | Vídeos correspondentes; não substituir o roteiro pelo link |

**Não copiar resultados, bugs ou conclusões do OrangeHRM.** O exemplo fornece o formato, não evidência sobre o SIFIT.

### Como atualizar pelo navegador

1. Abrir https://github.com/adrianssz/sifit-qa.
2. Usar **Add file → Create new file** para documentos Markdown, informando a pasta no nome.
3. Colar o conteúdo preparado e revisar a prévia.
4. Usar **Commit changes** com mensagem referente ao que foi realmente feito.
5. Para prints, usar **Add file → Upload files** dentro da pasta de evidências.
6. Para vídeos, inserir o link real do Jam no Markdown.
7. Abrir o arquivo salvo e testar os links.

Exemplos de commits:
- `docs: adiciona inventario inicial de testes do SIFIT`
- `docs: adiciona cenarios de login`
- `test: registra execucao e evidencias de login`
- `docs: registra BUG-001 com evidencia`

**Ao final de cada etapa, atualizar o GitHub antes de passar à seguinte.** Nenhum arquivo foi enviado ao repositório durante este levantamento.

## 7. Modelo de caso de teste

O modelo do professor usa cenário, ID, descrição, pré-condições, passos em DADO/QUANDO/ENTÃO e critérios de aceitação. Acrescentamos resultado obtido, execução e links para rastrear as evidências.

### C01-CT02 — Login com senha incorreta

| Campo | Conteúdo |
|---|---|
| Requisito | RF01 — Autenticação (vínculo proposto) |
| Tipo | Negativo |
| Pré-condições | Conta de teste existente e tela de login acessível |
| Dados de teste | Usuário de teste fornecido pelo professor; senha propositalmente incorreta, sem publicar credenciais |
| DADO | Que estou na tela de login do SIFIT |
| E | Informo usuário existente e uma senha incorreta |
| QUANDO | Aciono Entrar |
| ENTÃO | O acesso deve ser recusado com mensagem compreensível |
| Critério de aceitação | Não abrir área protegida nem criar sessão autenticada |
| Resultado obtido | Preencher após executar; transcrever a mensagem real |
| Status | Não executado |
| Data/hora | A preencher |
| Executor | Adrian |
| Ambiente | Registrar navegador/versão e sistema operacional reais |
| Vídeo | Inserir link real do Jam após gravar |
| Print | Inserir caminho do print, se necessário |
| Bug associado | Nenhum registrado; preencher apenas se houver falha reproduzida |

Não inventar o texto exato da mensagem esperada: ele será registrado quando observado ou confirmado como requisito.

## 8. Modelo de registro de bug

| Campo | Preencher |
|---|---|
| ID | BUG-001 |
| Título | Resumo objetivo do problema observado |
| Caso associado | ID do caso executado |
| Pré-condições | Estado do sistema e dados fictícios usados |
| Passos para reproduzir | Sequência mínima e numerada |
| Resultado esperado | Regra confirmada ou comportamento funcional esperado |
| Resultado obtido | Comportamento efetivamente observado |
| Frequência | Sempre, intermitente ou apenas uma ocorrência |
| Ambiente e data/hora | Navegador, SO, URL e horário reais |
| Severidade | Justificar impacto, sem exagerar |
| Evidência | Link do vídeo e print |
| Causa | Não determinada, salvo evidência técnica suficiente |
| Status | Aberto / em análise / corrigido / retestado |

Uma tela não carregada pode bloquear outros testes: registrar a ocorrência e marcar os casos dependentes como **Bloqueados**, sem contabilizá-los como aprovados.

## 9. Atualização após cada gravação

- [ ] Roteiro e resultado esperado preparados antes do teste.
- [ ] Execução feita com dados fictícios identificáveis.
- [ ] Vídeo revisado e identificado com o ID.
- [ ] Print incluído quando ajudar a evidenciar o resultado.
- [ ] Link acessível ao professor e sem dados sensíveis indevidos.
- [ ] Resultado obtido e status preenchidos.
- [ ] Bug registrado quando houver falha reproduzida.
- [ ] Relatório de execução e contagens atualizados.
- [ ] README atualizado somente com etapas realmente concluídas.
- [ ] Commit feito e links conferidos.

## 10. Fontes e estado do trabalho

- PDF fornecido: **AULA 1 — 2 BIM — 6º — Apresentação Extensão QA 2 Bimestre**, lido nesta sessão. As credenciais contidas nele não foram reproduzidas neste documento.
- Modelo: https://github.com/Adnyslougansilva/extensao-qa — documentos de análise, plano, cenário de login e relatório de testes consultados.
- Repositório do aluno: https://github.com/adrianssz/sifit-qa — README consultado. Há um “4.” isolado ao final, que pode ser removido na próxima edição.
- Sistema: inspeção exploratória pela interface em 12/10/2026.
- Jam: https://jam.dev/capture e extensão oficial indicada acima.

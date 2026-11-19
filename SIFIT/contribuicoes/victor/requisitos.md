# Análise de requisitos — Meus testes

**Responsável:** Victor  
**Data de elaboração:** 18/11/2026  
**Sistema de referência:** https://sifitalfa.centrion.com.br  
**Fonte:** [Inventário do SIFIT](../../../Invent%C3%A1rio.md)  
**Versão consultada do inventário:** blob `d3885feed1a1909bc57ee56f4041b18facb5b813`, na [revisão 68f918b](https://github.com/adrianssz/sifit-qa/blob/68f918bd39c942c2d3141877724ab8ffac0219d0/Invent%C3%A1rio.md).  
**Modelo de estrutura:** [Análise de requisitos do professor](https://github.com/Adnyslougansilva/extensao-qa/blob/main/OrangeHRM/1-Analise%20de%20requisitos.md).  
**Estado:** preparação documental; nenhum teste executado por mim nesta etapa.

## 1. Fonte, rastreabilidade e limites

Organizei os requisitos RFxx abaixo como vínculos de documentação propostos, com o número do cenário correspondente. Não substituem especificação oficial. Preservei nas tabelas os IDs, as descrições, os critérios propostos e os tipos do inventário; as sínteses de cada RF apenas organizam esse conteúdo.

Usei como base a inspeção anterior registrada por Adrian no inventário. Ainda preciso conferir o funcionamento atual nas minhas execuções. Os critérios continuam propostos até que a regra necessária seja confirmada por documentação, orientação do responsável pelo sistema ou configuração observável e registrada.

São 64 casos específicos em C05, C06, C07, C13, C14, C18, C20, C34 e C45. No C47, o recorte operacional dos meus testes abrange CT03, CT04 e CT06 a CT10, aplicado aos meus dados: 7 casos integrados/transversais, totalizando 71 casos planejados. CT01, CT02 e CT05 aparecem somente para preservar a referência do inventário e explicitar a divisão com os outros módulos; não integram a contagem nem a execução dos meus testes. A divisão do C47 pode ser ajustada se houver atribuição expressa diferente do grupo, sem renumerar casos.

## 2. Requisitos por cenário

### RF05 — Check-in

**Síntese proposta:** Verificar busca, filtros, entrada manual e consistência do check-in, condicionando QR Code e regras de liberação às respectivas dependências.

| ID | Descrição original do inventário | Resultado esperado / critério proposto original | Tipo original |
|---|---|---|---|
| C05-CT01 | Buscar por nome, código e plano | Retornar os clientes correspondentes e tratar busca sem resultado. | Filtro |
| C05-CT02 | Alternar abas de presença | Filtrar Todos, Presentes agora, Não compareceram e Check-in pendente corretamente. | Filtro |
| C05-CT03 | Filtros e seleção de unidade | Restringir registros e indicadores à seleção. | Filtro |
| C05-CT04 | Check-in manual de cliente elegível | Registrar uma entrada e refletir presença e horário. | Positivo |
| C05-CT05 | Código vazio, inexistente ou inválido | Impedir entrada inválida e exibir orientação. | Negativo |
| C05-CT06 | Check-in repetido | Aplicar a regra de duplicidade sem multiplicar entradas por clique duplo. | Negativo |
| C05-CT07 | Cliente inativo, sem matrícula ou inadimplente | Conferir a regra de liberação definida para cada situação. | Regra a confirmar |
| C05-CT08 | QR Code | Verificar leitura válida, inválida e permissão de câmera negada; exige dispositivo. | Condicional |
| C05-CT09 | Indicadores e presentes agora | Conferir atualização e consistência com Presenças. | Consistência |

### RF06 — Presenças

**Síntese proposta:** Verificar consultas por cliente e período e a correspondência entre presenças, indicadores e entradas registradas.

| ID | Descrição original do inventário | Resultado esperado / critério proposto original | Tipo original |
|---|---|---|---|
| C06-CT01 | Busca por cliente existente e inexistente | Listar somente presenças correspondentes ou estado vazio. | Filtro |
| C06-CT02 | Atalhos de período | Hoje, semana e mês devem preencher o intervalo e buscar corretamente. | Filtro |
| C06-CT03 | Período personalizado | Incluir registros dos limites inicial e final conforme regra de horário. | Limite |
| C06-CT04 | Datas vazias, inválidas ou invertidas | Orientar correção, sem erro técnico. | Negativo |
| C06-CT05 | Total, alunos distintos, média e dias | Recalcular indicadores corretamente, inclusive em intervalo sem presenças. | Consistência |
| C06-CT06 | Check-in refletido na consulta | Entrada registrada deve aparecer com cliente, unidade, data e hora corretos. | Integração |

### RF07 — SifitBox — Aulas

**Síntese proposta:** Verificar consultas e geração de aulas a partir de recorrências controladas; mapear detalhes e ações somente quando estiverem disponíveis.

| ID | Descrição original do inventário | Resultado esperado / critério proposto original | Tipo original |
|---|---|---|---|
| C07-CT01 | Consultar aulas por período | Listar somente aulas do intervalo, com mensagem clara quando vazio. | Filtro |
| C07-CT02 | Período inválido | Rejeitar datas invertidas ou incompletas. | Negativo |
| C07-CT03 | Gerar aulas de turma recorrente | Criar as aulas conforme dias, horários e vigência configurados. | Condicional |
| C07-CT04 | Gerar novamente o mesmo período | Verificar prevenção de aulas duplicadas. | Negativo |
| C07-CT05 | Detalhar aula gerada | Mapear participantes, vagas e ações que surgirem após existir aula de teste. | Dependência |
| C07-CT06 | Reserva, cancelamento e lotação, se disponíveis | Verificar regras de inscrição e vagas; expandir em casos após abrir aula. | Dependência |

### RF13 — Ficha de Treino

**Síntese proposta:** Verificar criação, consulta e persistência de fichas de treino, referências, exercícios, modelos e indicadores.

| ID | Descrição original do inventário | Resultado esperado / critério proposto original | Tipo original |
|---|---|---|---|
| C13-CT01 | Criar ficha com aluno, personal e objetivo | Vincular corretamente os dados iniciais. | Positivo |
| C13-CT02 | Aluno ou referência obrigatória ausente | Impedir ficha inválida com mensagem clara. | Negativo |
| C13-CT03 | Data final anterior à inicial | Impedir período incoerente conforme regra confirmada. | Negativo |
| C13-CT04 | Observação e persistência | Preservar texto e datas após salvar e reabrir. | Positivo |
| C13-CT05 | Usar Modelo de Ficha | Selecionar modelo e conferir conteúdo copiado sem alterar o original. | Dependência |
| C13-CT06 | Editor de exercícios | Mapear inclusão, remoção, ordem, séries, repetições e cargas que estiverem disponíveis. | Dependência |
| C13-CT07 | Limites de séries, repetições e cargas | Testar vazios, zero, negativos e decimais conforme cada campo disponível. | Dependência |
| C13-CT08 | Status, vencimento e indicadores | Conferir ativas, vencendo em 7 dias e inativas/canceladas. | Consistência |
| C13-CT09 | Busca e paginação | Conferir código, aluno, status e navegação da tabela. | Filtro |
| C13-CT10 | Cancelar criação | Não criar ficha ao fechar ou cancelar o modal. | Negativo |

### RF14 — Exercícios

**Síntese proposta:** Verificar carregamento e operações disponíveis da biblioteca, distinguindo falha de carregamento de ausência de registros.

| ID | Descrição original do inventário | Resultado esperado / critério proposto original | Tipo original |
|---|---|---|---|
| C14-CT01 | Carregamento da biblioteca | Distinguir biblioteca vazia de falha no servidor; reproduzir erro observado. | Investigação |
| C14-CT02 | Importar biblioteca padrão | Conferir grupos e exercícios criados em conjunto de teste autorizado. | Condicional |
| C14-CT03 | Repetir importação | Verificar prevenção de duplicação de biblioteca. | Condicional |
| C14-CT04 | Cadastro manual | Abrir o caminho para grupos musculares e mapear cadastro de exercício quando disponível. | Dependência |
| C14-CT05 | Pesquisa, filtros e visualização de exercícios | Detalhar os controles que aparecerem com biblioteca carregada. | Dependência |
| C14-CT06 | Associar exercício à ficha | Conferir vínculo e preservação da biblioteca de origem. | Dependência |

### RF18 — Turmas

**Síntese proposta:** Verificar cadastro e manutenção de turmas, dias, horários, opções condicionais e vínculos, conforme regras confirmadas.

| ID | Descrição original do inventário | Resultado esperado / critério proposto original | Tipo original |
|---|---|---|---|
| C18-CT01 | Cadastrar turma válida | Gravar nome, plano, dias, horários e demais opções. | Positivo |
| C18-CT02 | Nome, plano e dias ausentes | Validar regras obrigatórias confirmadas. | Negativo |
| C18-CT03 | Horário final igual ou anterior ao inicial | Aplicar regra de duração e eventual passagem de dia. | Limite |
| C18-CT04 | Tempo em meses inválido | Tratar zero, negativos, texto e valores além do limite. | Limite |
| C18-CT05 | Selecionar vários dias | Preservar exatamente os dias escolhidos. | Interação |
| C18-CT06 | Aula experimental e Tem Personal | Conferir campos condicionais e efeito das opções. | Interação |
| C18-CT07 | Status ativo/inativo e filtros | Conferir disponibilidade e listagem após mudança. | Positivo |
| C18-CT08 | Conflito de turma/horário | Confirmar regra para sobreposição e professor. | Regra a confirmar |
| C18-CT09 | Cancelar, editar e excluir | Conferir persistência e vínculos com matrículas/aulas. | Condicional |

### RF20 — SifitBox — Turmas

**Síntese proposta:** Verificar modalidades, turmas recorrentes e correspondência com as aulas geradas.

| ID | Descrição original do inventário | Resultado esperado / critério proposto original | Tipo original |
|---|---|---|---|
| C20-CT01 | Cadastrar modalidade | Salvar nome, descrição e status. | Positivo |
| C20-CT02 | Cadastrar turma recorrente | Vincular modalidade, horário, dias e vagas. | Positivo |
| C20-CT03 | Modalidade, nome ou dias ausentes | Validar referências e campos necessários. | Negativo |
| C20-CT04 | Vagas zero, negativas, decimais ou excessivas | Aplicar limite e tipo numérico confirmados. | Limite |
| C20-CT05 | Horários inválidos e sobreposição | Tratar intervalos e conflitos conforme regra. | Negativo |
| C20-CT06 | Ativar/inativar modalidade e turma | Conferir efeito na geração e disponibilidade das aulas. | Integração |
| C20-CT07 | Gerar aulas a partir da recorrência | Conferir correspondência com SifitBox — Aulas. | Integração |

### RF34 — Atividades

**Síntese proposta:** Verificar atividades, pontuação, descrição e indicadores, confirmando as regras numéricas antes do julgamento.

| ID | Descrição original do inventário | Resultado esperado / critério proposto original | Tipo original |
|---|---|---|---|
| C34-CT01 | Cadastrar atividade com pontuação | Persistir nome, valor e descrição. | Positivo |
| C34-CT02 | Atividade sem pontuação | Confirmar se ausência e zero são aceitos e como são contados. | Regra a confirmar |
| C34-CT03 | Pontuação negativa, decimal ou texto | Aplicar regra numérica confirmada. | Limite |
| C34-CT04 | Nome vazio e texto longo | Validar nome e limite da descrição. | Negativo |
| C34-CT05 | Pesquisar, editar e conferir indicadores | Conferir com/sem pontuação e com descrição. | Consistência |

### RF45 — Modelos de Ficha

**Síntese proposta:** Verificar consulta e editor de modelos de ficha, ações efetivamente disponíveis e aplicação sem alterar o modelo original.

| ID | Descrição original do inventário | Resultado esperado / critério proposto original | Tipo original |
|---|---|---|---|
| C45-CT01 | Buscar código, título e criador | Exibir somente modelos correspondentes. | Filtro |
| C45-CT02 | Abrir criação e mapear editor | Identificar campos e controles efetivos antes do roteiro. | Dependência |
| C45-CT03 | Título vazio e modelo sem exercícios | Conferir regras obrigatórias após acesso ao editor. | Dependência |
| C45-CT04 | Editar, duplicar ou excluir, se disponíveis | Mapear ações e preservar modelos vinculados. | Dependência |
| C45-CT05 | Usar modelo em ficha de aluno | Copiar conteúdo sem modificar o original e manter vínculos corretos. | Integração |
| C45-CT06 | Conferir indicadores | Validar modelos, criadores, listados e sem criador. | Consistência |

### RF47 — Fluxos integrados e conferência no banco

**Síntese proposta:** Conferir os fluxos de presença e treino dos meus testes, a persistência e a integridade dos meus dados controlados; conferência no banco somente por leitura autorizada e após identificar o schema real.

**Recorte:** CT03, CT04 e CT06–CT10 nos meus módulos e registros. CT01 (cliente/matrícula/financeiro), CT02 (financeiro/relatórios) e CT05 (anamnese) são referências externas ao meu escopo de execução.

| ID | Descrição original do inventário | Resultado esperado / critério proposto original | Tipo original |
|---|---|---|---|
| C47-CT01 | Cliente → plano → matrícula → conta a receber | Conferir identificadores, datas e valores ao longo do fluxo. | Integração |
| C47-CT02 | Conta recebida/paga → caixa → relatórios | Conciliar saldo, status e registros financeiros. | Integração |
| C47-CT03 | Turma recorrente → aula → check-in → presença | Conferir dias, vagas, aluno e horários. | Integração |
| C47-CT04 | Grupo muscular → exercício → modelo → ficha | Conferir vínculos e preservar conteúdo original. | Integração |
| C47-CT05 | Categoria → pergunta → modelo → anamnese | Conferir seleção, ordem, respostas e histórico. | Integração |
| C47-CT06 | Persistência após atualização e novo login | Dados confirmados devem continuar disponíveis. | Persistência |
| C47-CT07 | Conferência por SELECT no banco | Após identificar o schema real, comparar somente registros de teste; nunca inventar nomes de tabelas. | Banco |
| C47-CT08 | Cancelar operação e conferir banco | Não criar/alterar registros quando o fluxo foi cancelado. | Banco |
| C47-CT09 | Dependências e exclusões | Verificar integridade referencial e regra de preservação com registros descartáveis. | Banco |
| C47-CT10 | Alterações de colegas no ambiente compartilhado | Registrar data, horário e IDs próprios para não atribuir mudanças de terceiros ao teste. | Controle |

## 3. Regras e dependências ainda a confirmar

| Tema | Casos relacionados | Confirmação necessária antes de julgar o resultado |
|---|---|---|
| Elegibilidade e duplicidade de check-in | C05-CT04 a C05-CT08 | Cliente controlado e elegível, unidade, regra de repetição, inadimplência/inatividade e condições de QR Code. |
| Períodos e indicadores | C06-CT02 a C06-CT05; C05-CT09 | Fuso e inclusão dos limites de data/hora, definição de média e dias, e base comparável sem mudanças de terceiros. |
| Aulas e recorrência | C07-CT03 a C07-CT06; C20-CT02 a C20-CT07 | Vigência, geração, duplicidade, vagas, conflitos, participantes e ações realmente disponíveis. |
| Referências e editor de treino | C13-CT01 a C13-CT08; C14-CT04 a C14-CT06 | Aluno, personal, objetivo, grupo muscular, campos reais do editor e limites de séries, repetições e cargas. |
| Importação de biblioteca | C14-CT01 a C14-CT03 | Carregamento atual e possibilidade de limitar a importação a um conjunto autorizado de teste; não aplicar importação global sem delimitar seu efeito. |
| Turmas | C18-CT02 a C18-CT04; C18-CT06 a C18-CT09 | Obrigatoriedade, duração, passagem de dia, meses, conflitos, opções condicionais e política de exclusão com vínculos. |
| Atividades e pontuação | C34-CT02 a C34-CT04 | Ausência versus zero, negativos, decimais, limites e obrigatoriedade; não assumir fórmula ou faixa numérica. |
| Modelos de ficha | C45-CT02 a C45-CT05 | Campos e ações do editor, título obrigatório, modelo sem exercícios e política de alteração de modelos vinculados. |
| Banco e ambiente | C47-CT07 a C47-CT09 | Acesso de leitura, schema real e correspondência do banco com o mesmo ambiente e os mesmos IDs de teste da interface. |

A ausência de uma regra permanece uma dúvida documentada. Uma dependência indisponível pode bloquear o caso após a tentativa de preparação; não é automaticamente um bug. O erro de servidor mencionado no inventário em Exercícios é uma investigação histórica a reproduzir, e não um defeito confirmado por mim.

## 4. Verificações comuns

Aplicar G01 a G24 do inventário apenas aos controles existentes e pertinentes ao caso. Preservar seus IDs e textos; registrar a associação como `Cxx-Gyy-CAMPO`, por exemplo `C18-G02-NOME`. Variações de campos e dados usam sufixos nos casos originais, sem substituir sua descrição.

Na etapa dos roteiros, explicitar a associação de cada Gxx, os dados, as pré-condições, os passos e a regra que permite julgar o resultado. Uma regra não confirmada não se torna obrigatória por ter sido incluída no roteiro.

## 5. Critério de evidência

Toda conclusão exige resultado observado, ambiente real, data/hora, executor e evidência revisada. Teste negativo aprovado significa que a entrada inválida recebeu o tratamento esperado confirmado.

Usar somente dados identificados por `QA_VICTOR`. Credenciais, tokens, strings de conexão e dados pessoais reais não entram em arquivos, mensagens de commit ou evidências. Não copiar os resultados do modelo OrangeHRM nem atribuir a mim execuções de colegas.

# Análise de requisitos — Renan

**Responsável:** Renan Oliveira  
**Data:** 16/11/2026  
**Sistema:** SIFIT Alfa — https://sifitalfa.centrion.com.br  
**Fonte:** [Inventário](../../../Invent%C3%A1rio.md) e telas inspecionadas pelo grupo

Não temos documentação oficial de requisitos do SIFIT, então montei os requisitos abaixo a partir do inventário e das telas. Cada RF tem o mesmo número do cenário. Como o professor não definiu regras de negócio, onde faltava regra deixei a premissa que uso para julgar o resultado (detalhes na [seção 8 do planejamento](planejamento.md#8-premissas-adotadas)).

Entre parênteses está o caso que testa cada funcionalidade.

---

## RF10 — Avaliações

**Descrição:** agendar avaliações físicas de alunos com um personal, registrar a realização com medidas e cálculos e emitir impressão e relatório em PDF.  
**Base do inventário:** Listagem e modal de cadastro inspecionados; medidas da realização ainda dependem de avaliação de teste.

**Funcionalidades esperadas:**

- Buscar por código, nome e status, filtrando Pendente e Realizado. (C10-CT01)
- Agendar avaliação vinculando aluno, personal, data e horário. (C10-CT02)
- Exigir os campos obrigatórios do agendamento. (C10-CT03)
- Rejeitar data e horário impossíveis sem erro técnico. (C10-CT04)
- Tratar avaliações simultâneas do mesmo personal ou aluno conforme a regra. (C10-CT05)
- Registrar a realização com cada medida, unidade e cálculo. (C10-CT06)
- Validar medidas negativas, zeradas ou fora das faixas aceitas. (C10-CT07)
- Preservar as medidas ao salvar, reabrir e editar, atualizando status e resultados. (C10-CT08)
- Imprimir e gerar relatório completo em PDF com identificação, datas, medidas e cálculos. (C10-CT09)
- Oferecer link de avaliação e demais ações por ícone sem expor dados reais. (C10-CT10)
- Cancelar e excluir avaliação preservando os registros relacionados. (C10-CT11)

**Premissa:** aluno, personal, data e horário são obrigatórios; o mesmo personal ou aluno não tem duas avaliações no mesmo dia e horário; medidas não aceitam zero, negativo nem valor impossível; IMC = peso ÷ altura².

---

## RF37 — Enquetes

**Descrição:** cadastrar enquetes com pergunta e alternativas, disponibilizá-las no aplicativo e apurar as respostas.  
**Base do inventário:** Formulário inspecionado com nome, status, pergunta e resposta inicial.

**Funcionalidades esperadas:**

- Cadastrar enquete com nome, pergunta e alternativas permitidas. (C37-CT01)
- Exigir nome, pergunta, resposta e a quantidade mínima de alternativas. (C37-CT02)
- Adicionar e remover alternativas, mantendo a ordem e sem respostas vazias, se disponível. (C37-CT03)
- Validar alternativas duplicadas e texto longo. (C37-CT04)
- Ativar e inativar, respeitando período e visibilidade no aplicativo. (C37-CT05)
- Apresentar o total de respostas por alternativa. (C37-CT06)
- Pesquisar e editar enquete já respondida, preservando as respostas e aplicando as restrições de alteração. (C37-CT07)

**Premissa:** pelo menos duas alternativas, sem repetição; texto acima do limite é barrado com aviso; depois de haver respostas, pergunta e alternativas não mudam sem aviso.  
**Restrição:** ativar somente com conta controlada do aplicativo, sem exposição a alunos reais.

---

## RF38 — Fichas de Anamnese

**Descrição:** aplicar a um aluno uma anamnese baseada em um modelo, registrar as respostas e consultar as fichas.  
**Base do inventário:** Listagem e seleção de aluno para aplicação inspecionadas; perguntas dependem de modelo.

**Funcionalidades esperadas:**

- Buscar por aluno e filtrar por status, tratando consulta vazia. (C38-CT01)
- Vincular a nova anamnese somente ao aluno escolhido. (C38-CT02)
- Impedir o avanço sem aluno ou sem modelo. (C38-CT03)
- Exibir as categorias e perguntas configuradas no modelo aplicado. (C38-CT04)
- Registrar cada tipo de resposta disponível, com os complementos condicionais. (C38-CT05)
- Indicar quais perguntas obrigatórias faltam ao finalizar. (C38-CT06)
- Salvar rascunho e concluir, com a transição Pendente/Concluído mantida, se disponível. (C38-CT07)
- Consultar a ficha concluída com aluno, modelo, data e respostas. (C38-CT08)

**Premissa:** a ficha só é concluída com todas as perguntas respondidas, e o complemento de “Se sim, qual?” é obrigatório quando a resposta é Sim.  
**Restrição:** somente aluno fictício; nenhum dado de saúde real nas evidências.

---

## RF39 — Modelos de Anamnese

**Descrição:** montar modelos de anamnese com as perguntas cadastradas, para aplicação nas fichas.  
**Base do inventário:** Formulário de novo modelo e montador visual inspecionados; erro de servidor observado.

**Funcionalidades esperadas:**

- Criar modelo com nome, status, descrição e perguntas selecionadas. (C39-CT01)
- Impedir modelo sem nome ou sem perguntas, conforme a regra. (C39-CT02)
- Buscar perguntas e filtrar por categoria no montador. (C39-CT03)
- Adicionar e remover perguntas, atualizando montador e resumo. (C39-CT04)
- Reordenar perguntas e manter a ordem no formulário aplicado, se disponível. (C39-CT05)
- Aplicar a regra para pergunta duplicada ou inativa. (C39-CT06)
- Editar modelo já aplicado preservando o histórico das fichas existentes. (C39-CT07)
- Carregar o montador sem erro e distinguir falha de ausência de perguntas. (C39-CT08)

**Premissa:** o modelo precisa de nome e de pelo menos uma pergunta, sem repetir pergunta; editar o modelo não muda as fichas já aplicadas.

---

## RF40 — Categorias de Anamnese

**Descrição:** cadastrar as categorias que agrupam as perguntas de anamnese.  
**Base do inventário:** Formulário inspecionado com nome, status, ícone e cor.

**Funcionalidades esperadas:**

- Cadastrar categoria com nome, status, ícone e cor. (C40-CT01)
- Exigir o nome e tratar nome repetido conforme a regra de unicidade. (C40-CT02)
- Sincronizar a cor do seletor com o código e rejeitar código inválido. (C40-CT03)
- Exibir o ícone escolhido ou tratar ícone inválido de forma compreensível. (C40-CT04)
- Filtrar, editar e inativar, refletindo a disponibilidade para perguntas e modelos. (C40-CT05)
- Excluir categoria com perguntas vinculadas sem quebrar referências nem perder estrutura indevidamente. (C40-CT06)

**Premissa:** nome único; cor pelo seletor ou pelo código `#RRGGBB`, recusando outro texto; ícone só entre as opções que o sistema exibe.

---

## RF41 — Perguntas de Anamnese

**Descrição:** cadastrar as perguntas usadas nos modelos, com enunciado, número, status e tipo de resposta.  
**Base do inventário:** Formulário inspecionado com nome, pergunta, número, status e tipo de resposta.

**Funcionalidades esperadas:**

- Cadastrar pergunta Sim/Não, com as opções corretas na aplicação. (C41-CT01)
- Cadastrar pergunta Sim/Não/Não Sei, preservando cada resposta possível. (C41-CT02)
- Cadastrar pergunta Se Sim, qual?, exibindo o complemento na condição adequada. (C41-CT03)
- Exigir nome e enunciado. (C41-CT04)
- Aplicar a regra de ordem e unicidade do número. (C41-CT05)
- Inativar pergunta, refletindo a disponibilidade nos modelos e preservando o histórico. (C41-CT06)
- Pesquisar e editar com carregamento correto, sem erro no servidor. (C41-CT07)

**Premissa:** o número define a ordem, é inteiro maior que zero e não se repete; saltos na numeração são aceitos.

---

## RF42 — Inteligência & Automação

**Descrição:** central de automações, como risco de evasão e aniversariantes, com configuração, ativação, execução manual e acompanhamento dos resultados.  
**Base do inventário:** Central aberta; risco de evasão e aniversariantes observados; outras automações indicadas em desenvolvimento.

**Funcionalidades esperadas:**

- Listar automações com estado real, última execução, frequência e canal. (C42-CT01)
- Configurar automação com campos validados. (C42-CT02)
- Ativar e desativar, mantendo o estado escolhido. (C42-CT03)
- Executar agora sem repetição nem envio duplicado. (C42-CT04)
- Relacionar resultados e atividade recente à execução correta. (C42-CT05)
- Identificar as automações em desenvolvimento, que não são classificadas como defeito. (C42-CT06)
- Orientar o usuário em falha ou ausência de canal, sem indicar execução bem-sucedida. (C42-CT07)

**Restrição:** ativar e executar somente com envio para contas de teste controladas.

---

## RF43 — Resultados IA

**Descrição:** painel com os resultados das automações e indicadores por período.  
**Base do inventário:** Filtros Hoje/7/30/90 dias e indicadores observados.

**Funcionalidades esperadas:**

- Atualizar resultados e indicadores conforme o período escolhido. (C43-CT01)
- Exibir estado vazio coerente em período sem execuções. (C43-CT02)
- Apresentar execuções, relatórios, riscos, aniversários e demais indicadores coerentes com suas origens. (C43-CT03)
- Associar achados e eficiência à automação e à data corretas. (C43-CT04)
- Refletir nova execução sem duplicar registros. (C43-CT05)
- Distinguir falha de carregamento de resultado zero. (C43-CT06)

---

## RF47 — Fluxos integrados e conferência no banco

**Descrição:** conferir de ponta a ponta a cadeia da anamnese e a gravação dos registros de teste no banco de dados. Os demais casos de C47 são de outros integrantes.  
**Base do inventário:** Planejados; banco não acessado nesta inspeção.

**Funcionalidades esperadas:**

- Percorrer categoria → pergunta → modelo → anamnese, preservando seleção, ordem, respostas e histórico. (C47-CT05)
- Conferir por SELECT, no schema real, somente os registros de teste. (C47-CT07)
- Não criar nem alterar registros quando a operação é cancelada. (C47-CT08)
- Manter a integridade referencial em dependências e exclusões, conforme a regra de preservação. (C47-CT09)

**Restrição:** somente consultas de leitura, com acesso autorizado; nomes de tabelas só a partir do schema real.

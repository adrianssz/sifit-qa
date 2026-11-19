# Planejamento dos testes — Renan

**Responsável e executor:** Renan Oliveira  
**Data do planejamento:** 16/11/2026  
**Base:** [Inventário](../../../Invent%C3%A1rio.md), com IDs e descrições preservados  
**Ambiente:** SIFIT — `https://sifit.centrion.com.br`, o site indicado nos slides do professor e o único com acesso ao banco. Troquei do SIFIT Alfa em 17/11/2026, antes de começar os testes, porque o banco que recebemos não corresponde ao sifitalfa, onde Adrian e Fernando testaram.  
**Navegador e sistema operacional:** Google Chrome, com a versão anotada em cada execução; Windows 11  
**Situação:** os 64 casos estão **Não executados**.

## 1. Objetivo e escopo

Verificar manualmente, com evidência em vídeo, os 64 casos atribuídos a Renan: cadastros, validações, filtros, integrações entre módulos e consistência dos dados de teste.

| Cenário | Módulo | Casos | Prioridade | Arquivo em `SIFIT/cenarios-de-testes/` |
|---|---|---:|---|---|
| C10 | Avaliações | 11 | Alta | `C10-avaliacoes.md` |
| C37 | Enquetes | 7 | Média | `C37-enquetes.md` |
| C38 | Fichas de Anamnese | 8 | Alta | `C38-fichas-de-anamnese.md` |
| C39 | Modelos de Anamnese | 8 | Alta | `C39-modelos-de-anamnese.md` |
| C40 | Categorias de Anamnese | 6 | Média | `C40-categorias-de-anamnese.md` |
| C41 | Perguntas de Anamnese | 7 | Alta | `C41-perguntas-de-anamnese.md` |
| C42 | Inteligência & Automação | 7 | Média | `C42-inteligencia-e-automacao.md` |
| C43 | Resultados IA | 6 | Baixa | `C43-resultados-ia.md` |
| C47 | Fluxos integrados: CT05, CT07, CT08 e CT09 | 4 | Alta | `C47-renan.md` |
| | **Total** | **64** | | |

Prioridade Alta: dados de saúde, medidas e cálculos, integridade entre módulos ou erro já observado no inventário. Média: cadastro de apoio ou função que envia mensagens ou aparece no aplicativo. Baixa: somente consulta de indicadores.

Os requisitos estão em [requisitos.md](requisitos.md), como RF10, RF37 a RF43 e RF47, com o mesmo número do cenário, como nos arquivos `CT_RF` do repositório.

**Técnicas:** caminho feliz, testes negativos, partição de equivalência, valor limite, transição de status, conferência cruzada e reconhecimento exploratório das telas (P9).

**Fora do escopo:** os demais casos de C47 e os outros cenários, atribuídos aos colegas; carga, segurança, transações reais e envio de mensagens a pessoas reais.

## 2. Regras de registro

| Status | Quando usar |
|---|---|
| Não executado | Ainda não foi executado. |
| Aprovado | Todos os critérios do caso, incluindo as verificações Gxx aplicadas nele, foram atendidos. |
| Reprovado | Um critério do caso ou uma premissa da seção 8 não foi atendido e a falha foi reproduzida; o caso aponta o bug. |
| Bloqueado | Falta uma pré-condição externa: acesso, conta controlada, autorização ou tela com erro. Justificar e registrar o que já foi observado. |
| Não se aplica | O controle ou a regra não existe no sistema; comprovar com print. |

- Executados = Aprovados + Reprovados. Bloqueado e Não se aplica ficam fora dessa soma e nunca contam como aprovação.
- Ressalvas vão no texto do resultado obtido; não usar status como “Parcial”.
- Reteste usa o mesmo ID com sufixo `-R1`, `-R2`, sem criar caso novo.
- Verificação extra usa `Cxx-Gyy-CAMPO` (ex.: `C40-G06-NOME`) e é contada à parte dos 64.
- Bug: reproduzir a falha mais uma vez e registrar em `bugs.md` como `BUG-RENAN-NNN`, com caso relacionado, passos, resultado esperado e obtido, ambiente, data, severidade sugerida (Crítica, Alta, Média ou Baixa) e evidência, no formato de `contribuicoes/adrian/bugs.md`.

## 3. Preparação

Nada desta etapa conta como execução.

| # | Ação | Com quem | Libera |
|---|---|---|---|
| P1 | Ambiente: sifit.centrion.com.br, no lugar do SIFIT Alfa, porque só ele tem banco acessível — concluído em 17/11/2026 | Renan | Todos |
| P2 | Cadastrar no sifit.centrion o cliente `QA_RENAN_CLIENTE_01` como preparação de dados (não conta no C08) e avisar o Fernando: ativo, sem telefone ou e-mail de terceiros, código anotado. Se anamnese ou avaliação exigirem matrícula, pedir ajuda ao Fernando | Renan e Fernando | C38, C10, C47-CT05 |
| P3 | Confirmar um colaborador com função de personal ou avaliador | Grupo | C10 |
| P4 | Acesso ao banco recebido nos slides do professor e testado em 17/11/2026, só com consultas de leitura. Credenciais não entram no repositório nem nos vídeos — concluído | Renan | C47-CT07 a CT09 |
| P5 | Ver se o cliente de teste consegue entrar no aplicativo e se uma enquete ativa apareceria para alunos reais | Grupo | C37-CT05 a CT07 |
| P6 | Ver na configuração das automações (C42-CT02, sem ativar) o canal e quem recebe; só seguir se os destinatários forem contas de teste | Renan | C42-CT03, CT04 e CT07; C43-CT05 |
| P7 | O professor não definiu regras; premissas registradas na seção 8 — concluído | Renan | Casos que dependiam de regra |
| P8 | Prints com a Ferramenta de Captura (Win + Shift + S). Vídeo só no fim, se der tempo, na pasta `SIFIT-QA-Renan` do Drive, com acesso do professor conferido | Renan | Evidências |
| P9 | Reconhecimento das oito telas, sem salvar nada (detalhes abaixo) | Renan | Roteiros |

No reconhecimento (P9), anotar campos, indicação de obrigatório, botões e mensagens de erro, e responder:

- A pergunta se liga à categoria no cadastro da pergunta ou no modelo?
- A ficha tem resposta obrigatória e opção de rascunho?
- O ícone da categoria é escolhido em lista ou enviado por upload? A cor aceita código hexadecimal?
- Quais medidas, unidades e cálculos existem na realização da avaliação?
- O que faz cada ícone da listagem de avaliações? Ler a dica, sem acionar envio.
- Quais automações existem, com que canal e para quem enviam?

## 4. Massa de dados

Prefixo `QA_RENAN`. Anotar no caso o código gerado de cada registro; as conferências no banco usarão somente esses códigos.

| Dado | Uso |
|---|---|
| `QA_RENAN_CAT_01 Saúde` | Categoria principal; o acento cobre G07 |
| `QA_RENAN_CAT_02` | Cor, ícone, edição e inativação (C40-CT03, CT04 e CT05) |
| `QA_RENAN_PERG_01`, `_02` e `_03` | Perguntas Sim/Não, Sim/Não/Não Sei e Se Sim, qual?, com números 1, 2 e 3 |
| `QA_RENAN_PERG_INAT_01` | Pergunta criada inativa (C39-CT06) |
| `QA_RENAN_MOD_01` | Modelo com as três perguntas, aplicado em C38 |
| `QA_RENAN_CLIENTE_01` | Aluno das anamneses e avaliações (P2) |
| `QA_RENAN_CAT_FLUXO_01`, `QA_RENAN_PERG_FLUXO_01` e `_02`, `QA_RENAN_MOD_FLUXO_01` | Cadeia nova do fluxo integrado (C47-CT05) |
| `QA_RENAN_CAT_DESC_01` + `QA_RENAN_PERG_DESC_01` | Descartáveis para exclusão com vínculo (C40-CT06) |
| `QA_RENAN_CAT_DESC_02` + `QA_RENAN_PERG_DESC_02` | Descartáveis para conferir antes e depois no banco (C47-CT09) |
| `QA_RENAN_ENQ_01` | Enquete válida, salva inativa até liberar P5 |
| Avaliação extra do cliente de teste | Descartável para cancelar e excluir (C10-CT11) |

## 5. Ordem de execução

“Conclui após” indica que o status só é fechado depois do caso citado. A coluna Gxx lista as verificações comuns aplicadas dentro do caso, como em `C26-planos.md`. A coluna Vídeo dá o nome do arquivo caso a gente grave no fim; os prints usam o mesmo ID.

### Fase 1 — Cadeia da anamnese (casos 1 a 30)

| # | ID | Caso | Pré-requisito ou observação | Gxx | Vídeo (.mp4) |
|---:|---|---|---|---|---|
| 1 | C40-CT01 | Cadastrar categoria válida | Cria CAT_01 | G01 G04 G07 G13 G14 | C40-CT01-cadastrar-categoria |
| 2 | C40-CT03 | Cor pelo seletor e código | Cria CAT_02 | G05 | C40-CT03-cor-seletor-codigo |
| 3 | C40-CT04 | Ícone válido e inválido | Usa CAT_02 | G05 G22¹ | C40-CT04-icone-valido-invalido |
| 4 | C40-CT02 | Nome vazio ou repetido | Repete o nome de CAT_01; no fim, cancelar e reabrir | G02 G03 G08 G10 G11 G23 | C40-CT02-nome-vazio-repetido |
| 5 | C41-CT01 | Cadastrar pergunta Sim/Não | Cria PERG_01; conclui após C38-CT05 | G01 G04 G07 G13 | C41-CT01-pergunta-sim-nao |
| 6 | C41-CT02 | Cadastrar Sim/Não/Não Sei | Cria PERG_02; conclui após C38-CT05 | G01 G13 | C41-CT02-pergunta-sim-nao-nao-sei |
| 7 | C41-CT03 | Cadastrar Se Sim, qual? | Cria PERG_03; conclui após C38-CT05 | G01 G09 G13 | C41-CT03-pergunta-se-sim-qual |
| 8 | C41-CT04 | Nome ou enunciado vazio | No fim, cancelar e reabrir | G02 G03 G10 G11 G23 | C41-CT04-nome-enunciado-vazio |
| 9 | C41-CT05 | Número negativo, repetido ou fora da sequência | Usa os números 1 a 3 já gravados | G05 G06 G08 | C41-CT05-numero-invalido-repetido |
| 10 | C41-CT07 | Pesquisa, edição e erro no servidor | Perguntas QA_RENAN existentes | G12 G13 G15 G17 G18 G21 | C41-CT07-pesquisa-edicao-erro-servidor |
| 11 | C39-CT08 | Erro no carregamento do montador | Com perguntas existentes, separa falha de lista vazia | G21 | C39-CT08-erro-carregamento-montador |
| 12 | C39-CT03 | Buscar pergunta e filtrar categoria | — | G09 G15 G16 | C39-CT03-buscar-pergunta-filtrar-categoria |
| 13 | C39-CT04 | Adicionar e remover pergunta | Sem salvar; no fim, cancelar | G10 | C39-CT04-adicionar-remover-pergunta |
| 14 | C39-CT01 | Criar modelo válido | Cria MOD_01 com PERG_01 a 03 | G01 G04 G07 G13 | C39-CT01-criar-modelo |
| 15 | C39-CT05 | Reordenar perguntas, se disponível | Usa MOD_01; conclui após C38-CT04 | G13 | C39-CT05-reordenar-perguntas |
| 16 | C39-CT02 | Nome vazio ou modelo sem perguntas | No fim, reabrir o formulário | G02 G03 G11 G23 | C39-CT02-nome-vazio-sem-perguntas |
| 17 | C39-CT06 | Pergunta duplicada ou inativa | PERG_INAT_01 criada inativa antes | G08 G20 | C39-CT06-pergunta-duplicada-inativa |
| 18 | C38-CT03 | Aluno ou modelo ausente | No fim, cancelar | G02 G10 G23 | C38-CT03-aluno-modelo-ausente |
| 19 | C38-CT02 | Selecionar aluno para nova anamnese | Requer P2 | G09 | C38-CT02-selecionar-aluno |
| 20 | C38-CT04 | Aplicar modelo de teste | MOD_01; fecha C39-CT05 | G24 | C38-CT04-aplicar-anamnese |
| 21 | C38-CT05 | Responder tipos de pergunta disponíveis | Fecha C41-CT01 a CT03 | G07 G09 | C38-CT05-responder-perguntas |
| 22 | C38-CT06 | Finalizar com resposta obrigatória ausente | Inclui complemento só com espaços | G02 G03 G23 | C38-CT06-obrigatoria-ausente |
| 23 | C38-CT07 | Salvar rascunho e concluir, se disponível | — | G13 G14 | C38-CT07-rascunho-concluir |
| 24 | C38-CT08 | Consultar ficha concluída | — | G24 | C38-CT08-consultar-ficha-concluida |
| 25 | C38-CT01 | Buscar aluno e filtrar status | Requer fichas Pendente e Concluído | G15 G16 G17 G18 | C38-CT01-buscar-filtrar-status |
| 26 | C47-CT05 | Categoria → pergunta → modelo → anamnese | Dados FLUXO novos, em vídeo contínuo | G01 G13 G24 | C47-CT05-fluxo-anamnese |
| 27 | C39-CT07 | Editar modelo já aplicado | MOD_01 já aplicado | G12 G20 | C39-CT07-editar-modelo-aplicado |
| 28 | C41-CT06 | Status inativo | Inativa PERG_02, já respondida na ficha concluída | G12 G20 | C41-CT06-pergunta-inativa |
| 29 | C40-CT05 | Filtro, edição e inativação | Usa CAT_02 | G12 G15 G16 G20 | C40-CT05-filtro-edicao-inativacao |
| 30 | C40-CT06 | Exclusão com perguntas vinculadas | CAT_DESC_01 com PERG_DESC_01 | G19 G20 | C40-CT06-excluir-categoria-vinculada |

¹ G22 só se o ícone for enviado por upload; se for escolhido em lista, registrar G22 como Não se aplica, com print.

### Fase 2 — Avaliações (casos 31 a 41)

| # | ID | Caso | Pré-requisito ou observação | Gxx | Vídeo (.mp4) |
|---:|---|---|---|---|---|
| 31 | C10-CT03 | Aluno, personal, data ou hora ausentes | No fim, cancelar e reabrir | G02 G10 G11 G23 | C10-CT03-obrigatorios-ausentes |
| 32 | C10-CT04 | Data e horário inválidos | — | G05 G06 | C10-CT04-data-horario-invalidos |
| 33 | C10-CT02 | Agendar avaliação válida | Requer P2 e P3 | G01 G04 G13 G14 | C10-CT02-agendar-avaliacao |
| 34 | C10-CT05 | Conflito de agenda | Mesmo horário do #33; premissa da seção 8 | G08 | C10-CT05-conflito-agenda |
| 35 | C10-CT06 | Realizar avaliação de teste | Medidas fictícias | G01 G13 | C10-CT06-realizar-avaliacao |
| 36 | C10-CT07 | Medidas negativas, zero e fora dos limites | Premissa da seção 8 | G05 G06 | C10-CT07-medidas-invalidas |
| 37 | C10-CT08 | Salvar, reabrir e editar avaliação | — | G12 G13 | C10-CT08-salvar-reabrir-editar |
| 38 | C10-CT01 | Buscar por código, nome e status | Requer uma Pendente e uma Realizada | G15 G16 G17 G18 | C10-CT01-buscar-filtrar-status |
| 39 | C10-CT09 | Imprimir e relatório completo PDF | — | G24 | C10-CT09-imprimir-pdf |
| 40 | C10-CT10 | Link de avaliação e demais ações por ícone | Ler a dica antes; nada enviado a terceiros | G23 | C10-CT10-link-acoes-icone |
| 41 | C10-CT11 | Cancelar e excluir registro de teste | Avaliação descartável | G19 G20 | C10-CT11-cancelar-excluir |

### Fase 3 — Enquetes (casos 42 a 48)

| # | ID | Caso | Pré-requisito ou observação | Gxx | Vídeo (.mp4) |
|---:|---|---|---|---|---|
| 42 | C37-CT02 | Nome, pergunta e resposta vazios | No fim, cancelar e reabrir | G02 G03 G10 G11 G23 | C37-CT02-campos-vazios |
| 43 | C37-CT01 | Cadastrar enquete válida | Salvar inativa | G01 G04 G07 G13 | C37-CT01-cadastrar-enquete |
| 44 | C37-CT03 | Adicionar/remover alternativas, se disponível | — | G13 | C37-CT03-adicionar-remover-alternativas |
| 45 | C37-CT04 | Alternativas duplicadas e texto longo | — | G06 G08 | C37-CT04-duplicadas-texto-longo |
| 46 | C37-CT05 | Ativar/inativar e disponibilidade no aplicativo | Requer P5 | G13 | C37-CT05-ativar-inativar-app |
| 47 | C37-CT06 | Resultados e contagem de respostas | Requer P5 e votos de teste | G24 | C37-CT06-resultados-contagem |
| 48 | C37-CT07 | Pesquisar e editar enquete respondida | Depende do #47 | G12 G15 G20 | C37-CT07-editar-enquete-respondida |

### Fase 4 — Inteligência & Automação e Resultados IA (casos 49 a 61)

Primeiro o que só lê. Ativar e executar somente depois do P6, e só se os destinatários forem contas de teste.

| # | ID | Caso | Pré-requisito ou observação | Gxx | Vídeo (.mp4) |
|---:|---|---|---|---|---|
| 49 | C42-CT01 | Carregar automações e atualizar | Somente leitura | G13 G21 | C42-CT01-carregar-atualizar |
| 50 | C42-CT06 | Funcionalidades em desenvolvimento | Documentar, sem classificar como defeito | — | C42-CT06-em-desenvolvimento |
| 51 | C42-CT02 | Configurar automação | Mapear e cancelar, sem ativar | G02 G05 G09 G10 G11 | C42-CT02-configurar-automacao |
| 52 | C42-CT05 | Ver resultados e atividade recente | Execuções já existentes | G24 | C42-CT05-resultados-atividade |
| 53 | C42-CT07 | Falha ou ausência de canal configurado | Só se observável sem envio real (P6) | G21 | C42-CT07-falha-sem-canal |
| 54 | C43-CT01 | Alternar períodos | — | G16 | C43-CT01-alternar-periodos |
| 55 | C43-CT02 | Período sem execuções | — | — | C43-CT02-periodo-sem-execucoes |
| 56 | C43-CT03 | Conferir contagens | Comparar com C42 | G24 | C43-CT03-conferir-contagens |
| 57 | C43-CT04 | Conferir achados e eficiência | — | G24 | C43-CT04-achados-eficiencia |
| 58 | C43-CT06 | Tratar falha de carregamento | Se a falha não ocorrer sozinha, simular rede offline no DevTools | G21 | C43-CT06-falha-carregamento |
| 59 | C42-CT03 | Ativar/desativar e persistir | Requer P6 | G13 | C42-CT03-ativar-desativar |
| 60 | C42-CT04 | Executar agora | Requer P6 e destinatários controlados | G14 | C42-CT04-executar-agora |
| 61 | C43-CT05 | Atualização após execução de teste | Depende do #60 | G24 | C43-CT05-atualizacao-pos-execucao |

### Fase 5 — Conferência no banco (casos 62 a 64)

Somente `SELECT`, com acesso autorizado, schema real e os códigos QA_RENAN anotados. Sem acesso, os três ficam Bloqueados, citando a resposta recebida.

| # | ID | Caso | Pré-requisito ou observação | Gxx | Vídeo (.mp4) |
|---:|---|---|---|---|---|
| 62 | C47-CT07 | Conferência por SELECT no banco | Requer P4 | G24 | C47-CT07-select-banco |
| 63 | C47-CT08 | Cancelar operação e conferir banco | Requer P4; contar antes e depois do cancelamento | G10 G13 G24 | C47-CT08-cancelar-conferir-banco |
| 64 | C47-CT09 | Dependências e exclusões | Requer P4; usa CAT_DESC_02 e PERG_DESC_02 | G19 G20 G24 | C47-CT09-dependencias-exclusoes |

## 6. Verificações complementares

Pertinentes, mas sem caso próprio. Executar se houver tempo e registrar à parte dos 64:

- `C40-G06-NOME`, `C41-G06-ENUNCIADO`, `C39-G06-NOME`: tamanho máximo do texto.
- `C41-G14`, `C39-G14`, `C37-G14`: clique duplo em Salvar.
- Outras Gxx que o reconhecimento revelar, como upload em telas ainda não mapeadas.

## 7. Evidências

O professor informou que prints bastam. Cada caso é registrado com prints, e o vídeo fica opcional, para o fim.

- Prints da condição inicial, das ações principais e do resultado, normalmente de 2 a 4 por caso, tirados com a Ferramenta de Captura (Win + Shift + S).
- Nome do print: ID do caso, número e o que ele mostra (ex.: `C40-CT02-01-nome-vazio.png`), em `SIFIT/evidencias/renan/`.
- Antes do print, filtrar a lista pelos registros `QA_RENAN` ou recortar só a parte do teste, porque o sistema tem dados de pessoas reais. Nunca mostrar senha, tela de login preenchida nem os acessos do banco.
- Anotar em cada execução: data e hora, versão do Chrome, códigos gerados e mensagens exatas.
- Vídeo opcional no fim: nome da coluna Vídeo + `.mp4`, na pasta `SIFIT-QA-Renan` do Drive, conferindo o acesso do professor antes de colar o link.

## 8. Premissas adotadas

O professor não definiu regras de negócio para estes módulos e não há documentação do sistema. Para nenhum caso ficar sem veredito por falta de regra, adotei as premissas abaixo, com base no que é comum nesse tipo de cadastro e no que as outras telas do SIFIT já fazem. Quando o sistema contrariar uma premissa, o caso fica Reprovado e o bug cita a premissa usada.

| Cenário | Premissa |
|---|---|
| C40 | Não pode haver duas categorias com o mesmo nome, porque elas ficariam iguais na hora de escolher. A cor aceita o seletor e código hexadecimal `#RRGGBB`; qualquer outro texto é recusado. O ícone só aceita opções que o sistema consegue exibir. |
| C41 | O número define a ordem de exibição, é inteiro maior que zero e não se repete. Saltos na numeração são aceitos, desde que a ordem siga os números. |
| C39 | O modelo precisa de nome e de pelo menos uma pergunta, e a mesma pergunta não entra duas vezes. Editar um modelo não muda as fichas já aplicadas. |
| C38 | Vale a obrigatoriedade marcada em cada pergunta do modelo (o banco guarda isso em `modelo_perguntas_anamnese.obrigatoria`): pergunta obrigatória sem resposta impede concluir a ficha, e as não obrigatórias podem ficar em branco. Em “Se sim, qual?”, o complemento é obrigatório quando a resposta é Sim. |
| C10 | Aluno, personal, data e horário são obrigatórios. O mesmo personal ou o mesmo aluno não pode ter duas avaliações no mesmo dia e horário. Medidas físicas não aceitam zero nem valor negativo, e valores impossíveis, como 5 m de altura, são recusados ou geram alerta. O IMC é calculado como peso ÷ altura². |
| C37 | A enquete precisa de pelo menos duas alternativas, sem repetição. Texto acima do limite é barrado com aviso, sem corte silencioso. Depois que há respostas, a pergunta e as alternativas não mudam sem aviso. |

## 9. Riscos

| Risco | Efeito | Tratamento |
|---|---|---|
| Limite de 500 conexões por hora no usuário do banco, que o site e a turma compartilham. Em 19/11 todas as telas deram “Erro no servidor” no mesmo minuto em que o banco recusou conexão por esse limite | Sistema inteiro fora até a hora virar | Testar em horário de pouco uso, manter uma conexão só no Workbench e, se o erro aparecer, anotar o horário (G21) e repetir depois |
| Erro no servidor em Perguntas ou Modelos, já visto no inventário | Trava C39, C38 e C47-CT05 | Registrar com print, abrir bug e marcar dependentes como Bloqueados |
| As tabelas novas da anamnese não têm chave estrangeira no banco | Só o sistema impede vínculo quebrado | Foco do C47-CT09, com registros descartáveis |
| Automação ou link enviar mensagem a pessoa real | Dano a terceiros | Executar só com P6; cliente sem contatos de terceiros |
| Enquete ativa visível para alunos reais | Exposição indevida | Salvar inativa; ativar só com P5 |
| Ambiente compartilhado com colegas e alunos de outras turmas | Alteração de terceiros confundida com resultado | Prefixo, códigos, data e hora em cada caso |
| Print mostrar dado de pessoa real | Exposição indevida | Filtrar por `QA_RENAN` ou recortar antes de salvar; cada print é revisado antes do commit |

## 10. Critérios de saída

- Os 64 casos com status final; Bloqueado e Não se aplica justificados.
- Cada caso executado com prints, resultado obtido, data, navegador e executor.
- Falhas reproduzidas registradas em `bugs.md` como `BUG-RENAN-NNN` e ligadas aos casos.
- `resultados.md` com os totais e `SIFIT/4-relatorio-dos-testes.md` atualizado.

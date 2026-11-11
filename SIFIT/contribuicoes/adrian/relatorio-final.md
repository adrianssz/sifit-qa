# Relatório final dos testes — Adrian

**Sistema:** SIFIT Alfa — https://sifitalfa.centrion.com.br/login  
**Responsável:** Adrian  
**Período dos registros:** 05/11/2026 a 11/11/2026  
**Tipo de teste:** Manual, com gravações no Jam e no Drive

## Escopo

Este relatório reúne somente os casos atribuídos a Adrian. Os resultados dos outros integrantes do grupo devem ser consolidados separadamente.

Foram documentados 61 casos em nove áreas: autenticação, navegação, grupos musculares, objetivos de treino, categorias Crossfit, tipos de pagamento, bandeiras de cartão, funções e tipos de documentos.

## Resultado geral

| Situação registrada | Casos |
|---|---:|
| Aprovados | 28 |
| Reprovados | 13 |
| Parciais | 15 |
| Pendente de validação da regra | 1 |
| Inconclusivo | 1 |
| Impedidos ou bloqueados | 3 |
| **Total** | **61** |

**58 dos 61 casos tiveram alguma execução (95,1%).** Os outros três não puderam ser executados por falta da condição necessária ou da ação na interface. Um caso parcial confirma apenas os passos descritos no próprio registro; não significa que todas as integrações previstas foram verificadas.

| Área | Total | Aprovados | Reprovados | Parciais | Outros |
|---|---:|---:|---:|---:|---:|
| C01 — Autenticação e sessão | 14 | 8 | 5 | 0 | 1 pendente de regra |
| C02 — Navegação | 11 | 9 | 1 | 1 | 0 |
| C15 — Grupos musculares | 6 | 4 | 1 | 1 | 0 |
| C16 — Objetivos de treino | 5 | 1 | 3 | 1 | 0 |
| C19 — Categorias Crossfit | 5 | 3 | 0 | 1 | 1 bloqueado |
| C28 — Tipos de pagamento | 5 | 1 | 1 | 3 | 0 |
| C29 — Bandeiras de cartão | 5 | 0 | 1 | 2 | 1 inconclusivo e 1 bloqueado |
| C31 — Funções | 5 | 1 | 1 | 2 | 1 impedido |
| C33 — Tipos de documentos | 5 | 1 | 0 | 4 | 0 |

As situações acima seguem o status escrito em cada caso de teste. Um caso aprovado pode conter uma observação ou uma falha encontrada em uma verificação complementar; os detalhes estão nos registros individuais.

## Principais resultados

O login com dados válidos funcionou, assim como a recusa de credenciais incorretas, o logout e o bloqueio de acesso à área interna sem sessão. A tecla Enter não enviou o login, e o link Esqueci minha senha não apresentou resposta visível.

A navegação pelas telas e a maior parte das interações verificadas funcionaram. Foram observados o retorno da rolagem do menu lateral ao topo, o destaque incorreto do filtro Não lidas e títulos difíceis de ler no Dashboard em modo claro.

Nos cadastros, pesquisas e edições, houve resultados diferentes conforme a área. Em Objetivos de Treino, a descrição informada não apareceu após salvar, e uma tentativa de exclusão retornou erro genérico. Em Tipos de Pagamento, foi possível criar um registro sem nome. Em Funções, foi aceito um nome formado apenas por espaços. As tentativas de cadastrar Bandeiras de Cartão não produziram um registro salvo.

Os passos, resultados e links das gravações estão nos [casos de teste](../../cenarios-de-testes). As dez ocorrências abertas, com passos para reprodução e evidências, estão no [relatório de bugs](bugs.md).

## Casos impedidos

- **C19-CT05 — Excluir categoria Crossfit vinculada:** o formulário de exercício consultado não apresentou um campo para vincular Categoria Crossfit. Sem esse vínculo de teste, a exclusão nessa condição não foi executada.
- **C29-CT05 — Pesquisa, edição e dependências de bandeira:** as tentativas de cadastro não produziram uma bandeira salva. Não havia registro de teste para pesquisar, editar ou vincular.
- **C31-CT05 — Edição e exclusão de função com vínculo:** para a função consultada, a tela apresentou apenas Visualizar e Permissões. Não foi possível executar edição ou exclusão por essa interface.

Esses três casos não foram classificados como aprovados ou reprovados. O motivo e as evidências disponíveis constam nos respectivos registros.

## Limites da verificação

Alguns casos ficaram parciais porque o cadastro ou a pesquisa funcionou, mas não foi conferido o efeito em outro módulo, como o uso de uma função no cadastro de colaboradores ou de um tipo de documento no fluxo financeiro.

Também ficaram sem confirmação algumas regras de negócio: aceitação de nomes duplicados, comportamento esperado de Manter conectado e certas validações de campos. Essas observações não foram tratadas como bugs confirmados sem uma regra definida.

O C29-CT04 ficou inconclusivo quanto ao cálculo da taxa por mês, pois a bandeira não pôde ser salva. Nenhum bug deste relatório foi retestado após correção.

## Encerramento

A parte de Adrian está documentada com o resultado observado em cada um dos 61 casos e com dez bugs registrados. Os casos impedidos, as verificações parciais e as regras ainda não confirmadas permanecem identificados para uma próxima rodada de testes. Este relatório não representa o resultado consolidado dos seis integrantes do grupo.

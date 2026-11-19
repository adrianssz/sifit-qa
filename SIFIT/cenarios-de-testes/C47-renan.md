# C47 — Fluxos integrados e conferência no banco (parte do Renan)

**Responsável:** Renan Oliveira  
**Sistema:** SIFIT — https://sifit.centrion.com.br  
**Requisito:** [RF47 — Fluxos integrados e conferência no banco](../contribuicoes/renan/requisitos.md#rf47--fluxos-integrados-e-conferência-no-banco)

Estes são os meus quatro casos do C47; os outros são dos colegas. O CT05 percorre a cadeia da anamnese de ponta a ponta pela tela. O CT07, o CT08 e o CT09 conferem no banco os registros que criei, usando o MySQL Workbench com o acesso indicado nos slides do professor (Aula 1, pág. 8). Os dados de acesso não aparecem aqui nem nos prints.

Regras para os casos de banco:

- Só consultas `SELECT`, sempre filtradas pelos meus registros `QA_RENAN`. O banco tem dados de pessoas reais, que não podem aparecer nos prints.
- Os nomes de tabelas e colunas abaixo são os que existem no banco: `categorias_anamnese`, `perguntas_anamnese`, `modelos_anamnese`, `modelo_perguntas_anamnese` (ligação entre modelo e pergunta, com `ordem` e `obrigatoria`), `anamneses_alunos` (ficha aplicada) e `anamneses_respostas`.
- O usuário do banco tem limite de 500 conexões por hora, dividido com o site e com a turma. Abro uma conexão só e deixo aberta enquanto trabalho.

---

## C47-CT05 — Categoria → pergunta → modelo → anamnese

**Requisito:** RF47  
**Tipo:** Integração  
**Status:** Não executado  
**Ordem no planejamento:** 26

### Objetivo

Fazer a cadeia inteira com dados novos, da categoria até a ficha concluída, e conferir se a seleção, a ordem das perguntas e as respostas chegam certas no fim.

### Pré-condições

O cliente `QA_RENAN_CLIENTE_01` precisa estar cadastrado. Faço tudo numa sequência só, depois dos casos do C38.

### Dados utilizados

- Categoria: `QA_RENAN_CAT_FLUXO_01`
- Perguntas: `QA_RENAN_PERG_FLUXO_01` (“Já fez musculação antes?”, nº 1, Sim e Não) e `QA_RENAN_PERG_FLUXO_02` (“Tem alguma restrição médica? Se sim, qual?”, nº 2, Se Sim, qual?)
- Modelo: `QA_RENAN_MOD_FLUXO_01`, com a `PERG_FLUXO_02` primeiro e as duas obrigatórias
- Respostas: `PERG_FLUXO_02` = Sim, complemento “Restrição fictícia de teste”; `PERG_FLUXO_01` = Não

### Passos

1. Em Categorias, criar a `QA_RENAN_CAT_FLUXO_01`.
2. Em Perguntas, criar as duas perguntas do fluxo. O formulário de pergunta não tem campo de categoria, então anoto como o sistema liga (ou não liga) a categoria às perguntas.
3. Em Modelos, clicar em Novo Modelo, filtrar o montador pela `QA_RENAN_CAT_FLUXO_01` e ver se as perguntas do fluxo aparecem.
4. Adicionar a `PERG_FLUXO_02` e depois a `PERG_FLUXO_01`, ligar as duas como obrigatórias e salvar o modelo.
5. Em Fichas Anamnese, abrir uma anamnese nova para o `QA_RENAN_CLIENTE_01` com o `QA_RENAN_MOD_FLUXO_01`.
6. Conferir se as perguntas aparecem na ordem do modelo, responder e concluir.
7. Abrir a ficha concluída e conferir aluno, modelo, ordem e respostas.

### Resultado esperado

Conferir seleção, ordem, respostas e histórico. Cada etapa usa o que foi criado na anterior: o modelo mostra as perguntas escolhidas na ordem que montei, a ficha segue essa ordem e a ficha concluída guarda exatamente as respostas dadas. O filtro por categoria precisa trazer as perguntas da categoria do fluxo; se a pergunta não tiver como se ligar à categoria, registro isso como observação do fluxo.

### Verificações comuns aplicadas

- G01 — Cadastros válidos em cada etapa.
- G13 — Dados mantidos depois de atualizar a página.
- G24 — Conferência entre modelo, ficha e ficha concluída.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome —  
**Executor:** Renan Oliveira

### Evidência

Prints: em `SIFIT/evidencias/renan/`, com o nome começando por `C47-CT05`  
Vídeo (opcional, no fim): `C47-CT05-fluxo-anamnese.mp4`

### Bug associado

—

---

## C47-CT07 — Conferência por SELECT no banco

**Requisito:** RF47  
**Tipo:** Banco  
**Status:** Não executado  
**Ordem no planejamento:** 62

### Objetivo

Conferir no banco se os registros de teste que criei pela tela foram gravados com os mesmos dados que aparecem no sistema.

### Pré-condições

Os casos de C40, C41, C39 e C38 já executados, com a ficha do `QA_RENAN_CLIENTE_01` concluída. MySQL Workbench conectado ao banco do SIFIT.

### Dados utilizados

Consultas de leitura, filtradas pelos meus registros:

```sql
SELECT id, nome, cor, icone, status
FROM categorias_anamnese WHERE nome LIKE 'QA\_RENAN\_%';

SELECT id, nome, pergunta, numero, status, resposta
FROM perguntas_anamnese WHERE nome LIKE 'QA\_RENAN\_%';

SELECT m.id, m.nome, mp.ordem, mp.obrigatoria, p.nome AS pergunta
FROM modelos_anamnese m
JOIN modelo_perguntas_anamnese mp ON mp.modelo_id = m.id
JOIN perguntas_anamnese p ON p.id = mp.pergunta_id
WHERE m.nome LIKE 'QA\_RENAN\_MOD\_01%'
ORDER BY mp.ordem;

SELECT a.id, a.aluno_id, a.status, a.created_at
FROM anamneses_alunos a
JOIN modelos_anamnese m ON m.id = a.modelo_id
WHERE m.nome LIKE 'QA\_RENAN\_MOD\_01%';

SELECT r.anamnese_id, p.nome AS pergunta, r.resposta
FROM anamneses_respostas r
JOIN perguntas_anamnese p ON p.id = r.pergunta_id
WHERE p.nome LIKE 'QA\_RENAN\_PERG\_%';
```

### Passos

1. Abrir o Workbench e conectar uma vez só.
2. Rodar cada consulta e tirar print da consulta com o resultado.
3. Comparar com o que a tela mostra: nome, cor e ícone das categorias; enunciado, número, tipo e status das perguntas; ordem e obrigatoriedade no modelo; aluno, status e respostas da ficha.

### Resultado esperado

Após identificar o schema real, comparar somente registros de teste; nunca inventar nomes de tabelas. O banco tem que guardar exatamente o que a tela mostra para os mesmos registros, e as consultas só podem trazer linhas `QA_RENAN`.

### Verificações comuns aplicadas

- G24 — Conferência entre tela e banco.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome — e MySQL Workbench  
**Executor:** Renan Oliveira

### Evidência

Prints: em `SIFIT/evidencias/renan/`, com o nome começando por `C47-CT07`  
Vídeo (opcional, no fim): `C47-CT07-select-banco.mp4`

### Bug associado

—

---

## C47-CT08 — Cancelar operação e conferir banco

**Requisito:** RF47  
**Tipo:** Banco  
**Status:** Não executado  
**Ordem no planejamento:** 63

### Objetivo

Cancelar cadastros e uma edição pela tela e confirmar no banco que nada foi criado nem alterado.

### Pré-condições

A categoria `QA_RENAN_CAT_02` cadastrada. Workbench conectado.

### Dados utilizados

- Nomes que não podem existir no banco: `QA_RENAN_CAT_CANC_02`, `QA_RENAN_PERG_CANC_02` e `QA_RENAN_MOD_CANC_02`
- Edição cancelada: cor da `QA_RENAN_CAT_02` trocada para `#000000` e não salva

```sql
SELECT
  (SELECT COUNT(*) FROM categorias_anamnese WHERE nome LIKE 'QA\_RENAN\_CAT\_CANC%') AS categorias,
  (SELECT COUNT(*) FROM perguntas_anamnese WHERE nome LIKE 'QA\_RENAN\_PERG\_CANC%') AS perguntas,
  (SELECT COUNT(*) FROM modelos_anamnese WHERE nome LIKE 'QA\_RENAN\_MOD\_CANC%') AS modelos,
  (SELECT cor FROM categorias_anamnese WHERE nome LIKE 'QA\_RENAN\_CAT\_02%' LIMIT 1) AS cor_cat_02;
```

### Passos

1. Rodar a consulta e tirar print do resultado de antes.
2. Na tela, abrir Nova Categoria, digitar `QA_RENAN_CAT_CANC_02` e clicar em Cancelar.
3. Abrir Nova Pergunta, preencher `QA_RENAN_PERG_CANC_02` e clicar em Cancelar.
4. Abrir Novo Modelo, preencher `QA_RENAN_MOD_CANC_02`, adicionar uma pergunta e clicar em Cancelar.
5. Abrir o lápis da `QA_RENAN_CAT_02`, trocar a cor para `#000000` e clicar em Cancelar.
6. Rodar a mesma consulta de novo e tirar print do resultado de depois.

### Resultado esperado

Não criar/alterar registros quando o fluxo foi cancelado. As contagens de antes e de depois continuam zero e a cor da `QA_RENAN_CAT_02` continua a mesma.

### Verificações comuns aplicadas

- G10 — Cancelar sem salvar.
- G13 — Nada muda depois de atualizar a consulta.
- G24 — Conferência entre tela e banco.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome — e MySQL Workbench  
**Executor:** Renan Oliveira

### Evidência

Prints: em `SIFIT/evidencias/renan/`, com o nome começando por `C47-CT08`  
Vídeo (opcional, no fim): `C47-CT08-cancelar-conferir-banco.mp4`

### Bug associado

—

---

## C47-CT09 — Dependências e exclusões

**Requisito:** RF47  
**Tipo:** Banco  
**Status:** Não executado  
**Ordem no planejamento:** 64

### Objetivo

Excluir pela tela uma pergunta descartável que está dentro de um modelo descartável e conferir no banco se o vínculo entre os dois ficou quebrado.

### Pré-condições

Criar antes, só para este caso, a pergunta `QA_RENAN_PERG_DESC_02` e o modelo `QA_RENAN_MOD_DESC_02` com essa pergunta. No banco, a pergunta não tem campo de categoria e as tabelas novas da anamnese não têm chave estrangeira: o vínculo real é a linha de `modelo_perguntas_anamnese`, e só o sistema impede que ela fique apontando para uma pergunta apagada.

### Dados utilizados

```sql
-- vínculo do modelo descartável
SELECT mp.id, mp.modelo_id, mp.pergunta_id, p.nome AS pergunta
FROM modelo_perguntas_anamnese mp
JOIN modelos_anamnese m ON m.id = mp.modelo_id
LEFT JOIN perguntas_anamnese p ON p.id = mp.pergunta_id
WHERE m.nome LIKE 'QA\_RENAN\_MOD\_DESC\_02%';
```

### Passos

1. Rodar a consulta e tirar print: deve aparecer o vínculo com a `QA_RENAN_PERG_DESC_02`.
2. Na tela, em Perguntas, buscar a `QA_RENAN_PERG_DESC_02`, clicar no X e cancelar na confirmação, se houver. Conferir que ela continua.
3. Clicar no X de novo e confirmar. Anotar a mensagem.
4. Rodar a consulta de novo e tirar print.
5. Abrir o `QA_RENAN_MOD_DESC_02` pelo Editar e ver como ele ficou.

### Resultado esperado

Verificar integridade referencial e regra de preservação com registros descartáveis. O sistema deve impedir a exclusão de uma pergunta usada em modelo, com mensagem clara, ou excluir sem deixar vínculo quebrado. Se a consulta mostrar uma linha com `pergunta_id` apontando para uma pergunta que não existe mais (coluna `pergunta` vazia), o vínculo ficou órfão e registro bug.

### Verificações comuns aplicadas

- G19 — Cancelar e confirmar a exclusão.
- G20 — Modelo que usa a pergunta.
- G24 — Conferência entre tela e banco.

### Resultado obtido

Ainda não executado.

**Data:** —  
**Navegador:** Google Chrome — e MySQL Workbench  
**Executor:** Renan Oliveira

### Evidência

Prints: em `SIFIT/evidencias/renan/`, com o nome começando por `C47-CT09`  
Vídeo (opcional, no fim): `C47-CT09-dependencias-exclusoes.mp4`

### Bug associado

—

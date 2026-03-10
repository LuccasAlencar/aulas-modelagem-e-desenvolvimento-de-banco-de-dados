---
title: "Aula 14 — BCNF: O Refinamento Final para Especialistas"
layout: default
---

## 🎯 Objetivo da Aula
Entender situações raras onde a 3NF falha e aprender a aplicar a BCNF em tabelas com múltiplas chaves candidatas sobrepostas.

---

## 1. O que é a BCNF?
A BCNF (Boyce-Codd Normal Form) é uma versão mais forte da 3NF. Ela foi criada para resolver anomalias que a 3NF não consegue capturar quando uma tabela tem várias chaves candidatas que compartilham colunas.

**A Regra de Ouro:**
*"Toda determinante deve ser uma chave candidata."*
(Determinante é qualquer coluna que determina o valor de outra).

## 2. O Caso do Sistema de Tutorias
Imagine uma escola onde:
1. Um Aluno pode ter vários Tutores.
2. Cada Tutor ensina apenas uma Disciplina.
3. Uma Disciplina pode ter vários Tutores.

Tabela `Tutoria`:
- `ID_Aluno`
- `Professor`
- `Disciplina`

**Análise:**
- A Chave Composta é (`ID_Aluno`, `Disciplina`).
- Mas o `Professor` determina a `Disciplina` (pois ele só dá uma).
- O `Professor` é um determinante, mas **não é uma chave candidata** sozinho.
- **Resultado:** Se o professor mudar de disciplina, temos que alterar em todos os alunos. Viola a BCNF.

## 3. Como Resolver?
Separamos o determinante em sua própria tabela.
- Tabela `Especialidade`: (`Professor` [PK], `Disciplina`).
- Tabela `Tutoria`: (`ID_Aluno`, `Professor` [FK]).

## 🕵️ Discussão em Sala: Quando usar?
A BCNF é necessária apenas em sistemas com regras de negócio muito rígidas. Na maioria das vezes, se você aplicou bem a 3NF, seu banco já está ótimo. A BCNF é para quando a integridade é o fator número 1 (Sistemas bancários, aviação, saúde).

## ✍️ Exercício Rápido (15 min)
Explique com suas palavras: Qual a diferença entre um campo que depende da chave (3NF) e um campo que "manda" em parte da chave (BCNF)?

---
**O que fica desta aula:**
- BCNF é a "3.5NF".
- Resolve problemas de chaves candidatas sobrepostas.
- Garante que não haja dependências funcionais ocultas.
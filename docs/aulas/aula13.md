---
title: "Aula 13 — Terceira Forma Normal (3NF): Fim das Dependências Indiretas"
layout: default
---

## 🎯 Objetivo da Aula
Eliminar dependências transitivas, garantindo que colunas não-chave não tenham "poder" sobre outras colunas na mesma tabela.

---

## 1. O que é a Terceira Forma Normal (3NF)?
Dizemos que uma tabela está na 3NF se:
1.  Ela já está na **2NF**.
2.  Não existem **Dependências Transitivas**.

### O que é Dependência Transitiva?
É quando um campo A depende da Chave, e um campo B depende do campo A. 
Ou seja: **Chave -> Campo A -> Campo B**.
Pela regra da 3NF, o Campo B não deveria estar ali, pois sua relação com a chave é indireta.



## 2. Exemplo Clássico: Endereços e CEP
Tabela `Funcionarios`:
- `ID_Func` (PK)
- `Nome`
- `CEP`
- `Cidade`
- `Estado`

**A Análise:**
- O `Nome` depende do `ID`? Sim.
- O `CEP` depende do `ID`? Sim.
- A `Cidade` depende do `ID`? Sim, mas... se eu souber o `CEP`, eu já sei a `Cidade`!
- Logo, `Cidade` e `Estado` dependem do `ID` **através** do `CEP`. Isso é uma Dependência Transitiva.

## 3. Como Resolver?
Removemos a "escadinha". Criamos uma tabela de referência para o CEP.
- **Tabela `Funcionarios`**: `ID_Func`, `Nome`, `CEP` (FK).
- **Tabela `Enderecos`**: `CEP` (PK), `Cidade`, `Estado`.

## ✍️ Atividade: Identificando o "Intruso" (20 min)
Dada a tabela `Vendas`:
`NF_Numero (PK) | Data | ID_Vendedor | Nome_Vendedor | Percentual_Comissao`

**Responda:**
1. Quem é o intruso que causa dependência transitiva?
2. Por que o `Percentual_Comissao` não deve ficar na tabela de Vendas?
3. Proponha a solução em duas tabelas.

## 💡 O Mantra da 3NF
Para decorar e nunca mais esquecer:
*"Os dados devem depender da Chave (1NF), da Chave Toda (2NF) e de **Nada além da Chave** (3NF)."*

---
**O que fica desta aula:**
- A 3NF limpa campos que "se explicam sozinhos" através de outros campos.
- Evita erros de digitação (ex: escrever "Sáo Paulo" em uma linha e "São Paulo" em outra).
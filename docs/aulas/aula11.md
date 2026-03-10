---
title: "Aula 11 — Segunda Forma Normal (2NF): Eliminando Dependências Parciais"
layout: default
---

## 🎯 Objetivo da Aula
Dominar a identificação de dependências parciais e aprender a decompor tabelas que utilizam chaves compostas para garantir a integridade total dos dados.

---

## 1. O que é a Segunda Forma Normal (2NF)?
Uma tabela entra na 2NF quando cumpre dois requisitos fundamentais:
1.  Já está na **Primeira Forma Normal (1NF)**.
2.  Não possui **Dependências Parciais**.

### O que é Dependência Parcial?
Isso ocorre apenas em tabelas com **Chaves Compostas** (PK formada por mais de uma coluna). Existe uma dependência parcial quando um atributo não-chave depende de apenas *parte* da chave primária, e não dela inteira.



## 2. Exemplo Prático: O Problema do Carrinho de Compras
Imagine uma tabela chamada `Itens_Pedido`:
- **Chave Composta:** `ID_Pedido` + `ID_Produto`.
- **Atributos:** `Quantidade`, `Preco_Unitario`, `Nome_Produto`.

**Análise de Dependência:**
- `Quantidade`: Depende do pedido e do produto (Dependência Total). ✅
- `Nome_Produto`: Depende **apenas** do `ID_Produto`. Ele não precisa do `ID_Pedido` para existir. (Dependência Parcial). ❌ **Viola a 2NF!**

**O risco:** Se o nome do produto mudar, você terá que atualizar milhares de linhas de pedidos antigos. Se esquecer uma, o banco fica inconsistente.

## 3. Como Corrigir (A Técnica da Decomposição)
Para normalizar, removemos os atributos "rebeldes" e os colocamos em uma nova tabela onde a chave que eles dependiam seja a Chave Primária única.

**Nova Estrutura:**
1.  Tabela `Produtos`: (`ID_Produto` [PK], `Nome_Produto`, `Preco_Base`).
2.  Tabela `Itens_Pedido`: (`ID_Pedido` [PK], `ID_Produto` [PK], `Quantidade`).

## ✍️ Atividade Prática: Sistema Escolar (20 min)
Analise a tabela `Matriculas`:
- **Chave:** `RA_Aluno` + `Cod_Disciplina`.
- **Campos:** `Nota_Final`, `Nome_Aluno`, `Nome_Disciplina`.

**Tarefa:**
1. Identifique as duas dependências parciais.
2. Desenhe como ficariam as 3 tabelas resultantes após a 2NF.

## 💡 Dúvida Comum
*"Se minha tabela tem uma Chave Primária simples (apenas um ID), ela já está na 2NF?"*
**Sim!** Se a chave não é composta, é impossível depender de "parte" dela. Portanto, toda tabela em 1NF com PK simples já está automaticamente na 2NF.

---
**O que fica desta aula:**
- 2NF foca em Chaves Compostas.
- Cada dado deve depender da chave inteira.
- Evita redundância em tabelas de relacionamento N:N.
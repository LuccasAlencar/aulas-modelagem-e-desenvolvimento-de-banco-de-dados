---
title: "Aula 10 — Primeira Forma Normal (1NF): Atomicidade e Estrutura"
layout: default
---

## 🎯 Objetivo da Aula
Aprender a "quebrar" dados complexos em valores atômicos e estruturar tabelas que permitam buscas rápidas e precisas.

---

## 1. Regras da 1NF
Para uma tabela estar na Primeira Forma Normal, ela deve seguir 4 regras rígidas:

1. **Atomicidade:** Cada campo deve conter apenas um valor. Nada de listas (ex: "Telefones: 11-999, 11-888").
2. **Valores na Coluna:** Todos os valores em uma coluna devem ser do mesmo tipo.
3. **Nomes Únicos:** Não pode haver colunas repetidas (ex: `Tel1`, `Tel2`, `Tel3`).
4. **Chave Primária:** Cada tabela deve ter um identificador único para suas linhas.

## 2. Por que listas são perigosas?
Imagine buscar o telefone "11-999" em uma coluna que tem 5 números juntos. O SQL teria que ler o texto inteiro de todas as linhas, o que é extremamente lento. Com a 1NF, o SQL vai direto ao ponto.

## 3. Como Corrigir a Violação da 1NF?
**Caso A: Campos Multivalorados (Listas)**
- *Solução:* Crie uma nova linha para cada valor ou, preferencialmente, uma nova tabela relacionada.

**Caso B: Colunas Repetitivas (Tel1, Tel2)**
- *Solução:* Crie uma tabela de "Telefones" onde cada linha é um número, ligada ao ID do dono.

## 💻 Exemplo Prático (Antes vs. Depois)

**Errado (Não está na 1NF):**
| ID | Nome | Disciplinas |
|----|------|-------------|
| 1  | Ana  | SQL, Java   |

**Certo (1NF):**
| ID | Nome | Disciplina |
|----|------|------------|
| 1  | Ana  | SQL        |
| 1  | Ana  | Java       |

## 📝 Exercício de Fixação (20 min)
Temos uma tabela de **Produtos**:
`Cod_Prod | Nome | Cores_Disponiveis | Preco`
Ex: `101 | Camiseta | Azul, Verde, Preto | 29.90`

**Tarefa:**
1. Explique por que ela viola a 1NF.
2. Desenhe como ficaria a estrutura correta separando em duas tabelas (`Produtos` e `Cores_Produto`).

---
**O que fica desta aula:**
- 1NF significa dados indivisíveis (atômicos).
- Tabelas na 1NF eliminam colunas "repetitivas" e facilitam filtros (WHERE).
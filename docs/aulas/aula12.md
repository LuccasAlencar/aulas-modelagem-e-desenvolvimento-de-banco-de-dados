---
title: "Aula 12 — Workshop: Normalização do Zero ao SQL"
layout: default
---

## 🎯 Objetivo da Aula
Aplicar os conceitos de 1NF e 2NF em um cenário "sujo" da vida real, transformando uma planilha caótica em um esquema de banco de dados profissional.

---

## 1. O Cenário: A Planilha do PetShop "Amigo Fiel"
O dono do PetShop usa esta planilha para controlar os banhos:
`Data | Nome_Cliente | CPF_Cliente | Celular | Nome_Pet | Raca_Pet | Servico | Valor`

**Problemas Visíveis:**
- Se o cliente tem 3 cães, o CPF e Celular repetem 3 vezes.
- Se o pet faz 10 banhos, a raça repete 10 vezes.
- Se um cliente ainda não trouxe o pet, não conseguimos cadastrá-lo.

## 2. Passo 1: Aplicando a 1NF (Atomicidade)
Primeiro, garantimos que cada célula tenha um valor único e criamos IDs.
- Criamos `ID_Cliente`, `ID_Pet`, `ID_Servico`.
- Verificamos se não há listas de serviços na mesma célula.

## 3. Passo 2: Aplicando a 2NF (Independência)
Vamos separar as entidades para que cada uma cuide do seu "quadrado".

**Estrutura Final Resultante:**
- **Tabela `Clientes`**: `ID_Cliente` (PK), `Nome`, `CPF`, `Celular`.
- **Tabela `Pets`**: `ID_Pet` (PK), `Nome`, `Raca`, `ID_Cliente` (FK).
- **Tabela `Servicos`**: `ID_Servico` (PK), `Descricao`, `Preco_Padrao`.
- **Tabela `Agendamentos`**: `ID_Agendamento` (PK), `Data`, `ID_Pet` (FK), `ID_Servico` (FK).

## 🕵️ Desafio de Lógica: O Banco de Dados de um RPG (25 min)
Imagine uma tabela única para um jogo:
`Nick_Jogador | Nivel | Item_Inventario | Dano_Item | Raridade_Item`

**Instruções para os alunos:**
1. Onde está a 1NF sendo violada (dica: Inventário)?
2. Como separar os dados do Jogador dos dados dos Itens?
3. Crie a tabela intermediária `Inventario` para ligar Jogador e Itens.

## 🚀 Insight para o Desenvolvedor
No seu site do GitHub Pages, se você usar um banco não normalizado, cada busca por "Itens do Jog
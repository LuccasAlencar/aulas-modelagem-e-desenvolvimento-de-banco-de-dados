---
title: "Aula 15 — Masterclass: Desafio Final de Arquitetura de Dados"
layout: default
---

## 🎯 Objetivo da Aula
Consolidar todo o conhecimento de normalização (1NF até BCNF) através de um projeto prático complexo e discutir o equilíbrio entre teoria e performance.

---

## 1. O Grande Desafio: Sistema de E-Commerce Global
Você foi contratado para arrumar o banco de dados de uma loja tipo a Amazon. Eles têm uma tabela gigante chamada `LOGISTICA`:

`ID_Pedido | Data | ID_Cliente | Nome_Cliente | Email_Cliente | ID_Produto | Nome_Prod | Categoria_Prod | ID_Armazem | Localizacao_Armazem | Quantidade | Status_Entrega`

**Missão do Aluno:**
Divida esta tabela única em pelo menos 5 tabelas seguindo a 3NF.



[Image of Database relational schema example]


## 2. Guia de Resolução (Passo a Passo sugerido)
1. **Entidade Cliente:** (ID, Nome, Email) -> 3NF garantida.
2. **Entidade Produto:** (ID, Nome, Categoria) -> 2NF/3NF.
3. **Entidade Armazém:** (ID, Localizacao) -> 3NF.
4. **Entidade Pedido:** (ID, Data, ID_Cliente).
5. **Entidade Itens_Pedido:** (ID_Pedido, ID_Produto, ID_Armazem, Quantidade).

## 3. Debate: Desnormalização (O mundo real)
Às vezes, empresas grandes como Facebook ou Netflix **"desnormalizam"** o banco de propósito. 
**Por quê?** Para ganhar velocidade. Fazer 10 `JOINs` para mostrar um comentário no post pode ser lento. Às vezes, repetir o "Nome do Usuário" em várias tabelas economiza tempo de processamento.

**Pergunta para a turma:** "É melhor ter um banco 100% organizado e lento, ou um banco com um pouco de repetição mas que carrega instantaneamente?"

## ✍️ Atividade Final: Documentação para o GitHub Pages
Escreva um pequeno guia (3 parágrafos) para o seu site explicando para um leitor leigo por que a normalização de dados salvou o projeto do PetShop (Aula 12).

---
**O que fica desta aula:**
- A teoria (3NF/BCNF) serve para evitar erros.
- A prática exige bom senso sobre performance.
- Projetar bancos de dados é uma arte de equilíbrio.
---
title: "Aula 17 — Introdução ao SQL"
layout: default
---

## Antes de começar

Quando você usa redes sociais ou apps de jogos, sabia que tudo isso está baseado em bancos de dados? Eles guardam todas as informações importantes como suas mensagens, amigos e pontuações. Mas como esses dados são organizados e acessados?

## O que você vai aprender nesta aula

- Entender o conceito básico do SQL (Structured Query Language) e sua importância.
- Criar tabelas e inserir registros em um banco de dados usando DDL e DML.
- Executar consultas simples para recuperar informações.

## SQL e sua Importância

Quando você usa redes sociais ou apps de jogos, sabia que tudo isso está baseado em bancos de dados? Eles guardam todas as informações importantes como suas mensagens, amigos e pontuações. Mas como esses dados são organizados e acessados?

SQL (Structured Query Language) é a linguagem padrão para interagir com bancos de dados relacionais, ajudando-nos a organizar, buscar e modificar informações. Quando você faz uma pesquisa no Facebook ou vê atualizações recentes, o SQL está por trás disso.

### Consultas Complexas

Com SQL, não somente podemos recuperar dados simples como "quem são meus amigos?", mas também perguntas mais complexas tipo "Quantos posts recebi nas últimas 24 horas?" ou "Quais foram as minhas interações com determinado amigo?"

> 🤔 **Para refletir:** Se você quisesse saber a quantidade de vezes que postou algo em sua rede social favorita durante o último mês, como faria isso usando SQL?

### Segurança e Integridade

SQL também ajuda na segurança dos dados. Ele pode garantir que as informações sejam acessadas apenas por quem tem permissão para tanto e garante a consistência das informações armazenadas.

## Navegando nos Comandos SQL: DDL, DML, DQL, DCL e TCL

Quando você está no Instagram, sabe que precisa criar uma conta primeiro antes de começar a postar fotos ou seguir amigos, certo? Na verdade, você está fazendo algo semelhante ao usar o DDL (Data Definition Language) do SQL!

### Definindo Estruturas com DDL
DDL é usado para criar e modificar as estruturas dos dados. Você define tabelas, índices e outras configurações que formam a base da sua "rede social de dados". Por exemplo:
```sql
CREATE TABLE usuarios (id INT PRIMARY KEY, nome VARCHAR(100));
```
> 🤔 **Para refletir:** Como seria a criação do Instagram se você não pudesse definir as tabelas para armazenar informações sobre usuários, fotos e comentários?

Agora que você tem uma tabela de usuários criada, como você manipularia os dados dentro dela? Aqui entra o DML (Data Manipulation Language).

### Manipulando Dados com DML
Com DML, você pode inserir novos registros, atualizar existentes e excluir itens desnecessários. Por exemplo:
```sql
INSERT INTO usuarios VALUES (1, 'João Silva');
UPDATE usuarios SET nome = 'Maria Silva' WHERE id = 2;
DELETE FROM usuarios WHERE id = 3;
```
> 🤔 **Para refletir:** Em um app de jogos, como você usaria o DML para adicionar novos usuários e atualizar pontuações?

### Atividade Prática
Vamos criar uma tabela chamada `games` com colunas para ID do jogo (chave primária), nome do jogo e data de lançamento. Depois disso, insira um novo jogo na tabela:
```sql
CREATE TABLE games (id_game INT PRIMARY KEY, nome VARCHAR(250), lancamento DATE);
INSERT INTO games VALUES (1, 'Super Mario Odyssey', '2017-10-27');
```
> 🤔 **Para refletir:** Como você usaria o DML para atualizar a data de lançamento do jogo caso haja um erro?

## Exemplos Práticos de Comandos SQL

Olá pessoal! Vamos começar falando sobre coisas que vocês usam todo dia, como redes sociais e aplicativos. Essas ferramentas armazenam muitos dados sobre vocês.

### Criação de uma tabela com comando DDL
Quer ver um exemplo real? Digamos que estamos criando uma tabela para guardar informações dos usuários de um site fictício. A tabela se chama `clientes`. Vai ter campos como ID, nome, e-mail e telefone. Aqui está o comando:

```sql
CREATE TABLE clientes (
    id_cliente INT PRIMARY KEY,
    nome VARCHAR(100),
    email VARCHAR(100),
    telefone VARCHAR(20)
);
```

### Inserção de um registro em uma tabela com comando DML
Agora que temos a tabela, vamos adicionar alguém nela. Suponha que queremos incluir Maria Oliveira como cliente número 1:

```sql
INSERT INTO clientes (id_cliente, nome, email, telefone)
VALUES (1, 'Maria Oliveira', 'maria@email.com', '123456789');
```

> 🤔 **Para refletir:** Como você acha que esses comandos SQL ajudam empresas a entender melhor seus clientes?

Vamos praticar! Faça o mesmo comando para adicionar um novo cliente, mas desta vez use os detalhes de alguém próximo a você.

## Para fechar — com as suas palavras

Escreva uma breve descrição do que aprendeu hoje sobre SQL e como ele pode ser usado em situações da vida real. Use suas próprias palavras para descrever o que achou mais interessante ou útil nesta aula.

## O que fica desta aula
```sql
-- DDL: CREATE TABLE, ALTER TABLE, DROP TABLE
-- DML: INSERT INTO, UPDATE, DELETE FROM
```

## Para ir além

- [SQL Tutorial for Beginners](https://www.w3schools.com/sql/)
- [SQL Exercises and Practice Problems](https://sqlbolt.com/)

## Referências

- W3Schools. (2021). SQL Tutorial for Beginners.
- SQLBolt. (2021). SQL Exercises and Practice Problems.
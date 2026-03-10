---
title: "Aula 19 — Comandos de criação (CREATE)"
layout: default
---

## Antes de começar

Pensou em quantas vezes por dia você interage com bancos de dados sem perceber? Seus apps de redes sociais, jogos online e até mesmo os serviços na nuvem usam esses sistemas para armazenar informações importantes. Hoje vamos explorar como criar estruturas básicas no banco de dados.

## O que você vai aprender nesta aula

- Como usar comandos `CREATE` para definir novas tabelas.
- Decidir quais colunas e tipos de dados são necessários ao criar uma tabela.
- Aplicar restrições, como chaves primárias (PRIMARY KEY), para garantir a integridade dos dados.

## Comandos de Criação (CREATE)

Olá! Já pensou em quantas vezes por dia você interage com bancos de dados, mesmo sem perceber? Seus apps de redes sociais, jogos online e até mesmo os serviços na nuvem usam esses sistemas para armazenar informações importantes.

### Os Comandos CREATE

Os comandos `CREATE` são como a chave para criar novas estruturas no banco de dados. Imagine que você quer construir um novo jogo — antes de adicionar personagens e níveis, primeiro precisa definir o esqueleto do jogo.

> 🤔 **Para refletir:** Como seria criar uma nova tabela em um banco de dados se você estivesse organizando os itens da sua coleção favorita?

Vamos praticar: Vou pedir que criem uma tabela chamada `alunos`. Essa tabela deve ter colunas para `nome`, `idade` e `matrícula`.

```sql
CREATE TABLE alunos (
    nome VARCHAR(100),
    idade INT,
    matricula INT PRIMARY KEY
);
```

Agora, vocês criaram a estrutura básica para armazenar informações sobre os estudantes! 🎉

### Definindo Colunas e Tipos de Dados em SQL

Imagine que você está criando um perfil no Instagram. Você precisa decidir quais informações incluir sobre si mesmo, como sua idade e localização. No mundo do SQL, fazemos algo parecido ao criar uma tabela.

Ao criar uma tabela, você decide o que cada coluna representará. Por exemplo, se você está criando um campo para a idade de alguém na tabela:

```sql
CREATE TABLE usuarios (
    idade INTEGER
);
```

Isso significa que no banco de dados, a coluna `idade` armazenará números inteiros como 18, 23 ou 75.

> 🤔 **Para refletir:** Se você tivesse uma tabela chamada "Livros", quais colunas e tipos de dados você usaria para representar o título e a data de publicação?

### Atividade Prática: Crie sua Tabela
Vamos criar uma tabela simples juntos. Suponha que estamos criando uma tabela para um jogo online onde cada jogador tem uma pontuação.

```sql
CREATE TABLE jogadores (
    nome TEXT,
    pontos INTEGER
);
```

Agora, tente adicionar outra coluna chamada `nivel` ao seu banco de dados. Que tipo de dado você usaria? Por que?

**Pergunta:** Como você decidiria o tipo de dado para a coluna `idade` em uma tabela onde os registros são de pessoas que participam de um clube?

### Aplicação de Constraints

Imagine que você está jogando um jogo online e tenta criar dois personagens com os mesmos IDs — provavelmente irá receber uma mensagem dizendo que o ID já existe. Isso é algo parecido com o que fazemos quando definimos chaves primárias (PRIMARY KEY) em nossas tabelas de banco de dados.

> 🤔 **Para refletir:** Como isso pode ajudar a evitar erros na sua base de dados?

Outro exemplo prático seria garantir que não possa adicionar um aluno à tabela 'alunos' sem uma matrícula válida. Vamos estabelecer então uma chave primária para a coluna `matrícula` nesta tabela, pois ela deve ser única e identificar unicamente cada estudante.

Agora, tente criar um exemplo simples em que você cria uma tabela chamada 'cursos' onde o campo `curso_id` é a chave primária. Como isso ajudaria na integridade dos dados?

Quais outras tabelas poderiam beneficiar de chaves estrangeiras (FOREIGN KEY) para garantir a consistência entre as informações?

## Para fechar — com as suas palavras

Escreva em suas próprias palavras o que você aprendeu sobre como criar e definir tabelas no SQL, incluindo os tipos de dados e restrições.

## O que fica desta aula
```sql
CREATE TABLE alunos (
    nome VARCHAR(100),
    idade INT,
    matricula INT PRIMARY KEY
);
```
- **Comandos CREATE**: Permite criar novas tabelas no banco de dados.
- **Tipos de Dados**: Define o tipo de informação que cada coluna armazenará (por exemplo, `VARCHAR`, `INTEGER`).
- **Restrições**: Garante a integridade dos dados através de chaves primárias e estrangeiras.

## Para ir além
1. [SQL Tutorial](https://www.w3schools.com/sql/) - Um tutorial interativo para aprender SQL.
2. [Banco de Dados: Conceitos Básicos](https://pt.wikipedia.org/wiki/Banco_de_dados) - Artigo da Wikipédia sobre conceitos básicos de banco de dados.

## Referências
- "SQL Tutorial for Beginners" — W3Schools
- "Introduction to Relational Database Management Systems (RDBMS)" — Oracle Corporation
# Aula 3 — Modelo Entidade-Relacionamento (ER)

> **Componente:** Modelagem e Desenvolvimento de Banco de Dados  
> **Unidade:** Levantamento de Dados e Conceitos Fundamentais  
> **Duração:** ~50 minutos

---

## 🎯 O que você vai aprender hoje

Nas aulas anteriores você conheceu o que é um banco de dados, viu o Excel como exemplo de tabela e explorou os tipos de dados. Agora chegou a hora de aprender **como planejar** um banco de dados antes de criá-lo — e para isso existe o **Modelo Entidade-Relacionamento (ER)**.

Ao final desta aula você vai saber:

- O que são **entidades**, **atributos** e **relacionamentos**
- O que é uma **chave primária** e por que ela é essencial
- Como montar um **Diagrama ER** no caderno

---

## 📌 Por que planejar antes de criar?

Imagine que você vai construir uma casa. Você começa a comprar tijolos aleatoriamente, ou antes faz uma **planta**?

Com bancos de dados é igual. Antes de criar as tabelas no computador, fazemos um **rascunho visual** chamado de **Diagrama Entidade-Relacionamento (DER)**. Ele serve para:

- Entender **quais informações** precisam ser guardadas
- Enxergar como essas informações **se conectam**
- Evitar erros e retrabalho

---

## 🧱 Entidade

Uma **entidade** é qualquer coisa do mundo real sobre a qual queremos guardar informações.

**Exemplos:**

| Contexto | Entidades |
|---|---|
| Biblioteca | Livro, Usuário, Empréstimo |
| Escola | Aluno, Professor, Disciplina |
| Pet shop | Animal, Tutor, Consulta |

> 💡 **Regra prática:** se você consegue listar coisas daquele tipo (ex: vários livros, vários alunos), é uma entidade.

No diagrama, entidades são representadas por **retângulos**.

```
┌─────────┐
│  Livro  │
└─────────┘
```

---

## 🏷️ Atributo

**Atributos** são as características que descrevem uma entidade — ou seja, as informações que queremos guardar sobre ela.

**Exemplo — Entidade "Livro":**
- Título
- Autor
- ISBN
- Ano de publicação

> 📝 Pense assim: se a entidade fosse uma ficha de cadastro, os atributos seriam os campos dessa ficha.

No diagrama, atributos são representados por **elipses** ligadas à entidade.

```
      (Título)
         |
┌─────────┐    (Autor)
│  Livro  │───
└─────────┘    (ISBN)
         |
    (Ano_publicacao)
```

---

## 🔑 Chave Primária (PK)

Dentro de uma entidade, precisamos de um atributo capaz de **identificar cada registro de forma única**. Esse atributo se chama **chave primária** (ou *Primary Key* — PK).

**Características obrigatórias:**
- Deve ser **única** — dois registros não podem ter o mesmo valor
- Deve ser **não nula** — não pode ficar em branco

**Exemplos:**

| Entidade | Chave primária |
|---|---|
| Livro | ISBN (todo livro tem um ISBN único no mundo) |
| Aluno | Número de matrícula |
| Produto | Código de barras |
| Pessoa | CPF |

No diagrama, a chave primária é indicada **sublinhando** o nome do atributo.

```
      (<u>ISBN</u>)
         |
┌─────────┐    (Título)
│  Livro  │───
└─────────┘    (Autor)
```

---

## 🔗 Relacionamento

Um **relacionamento** é a ligação entre duas entidades. Ele descreve como elas interagem.

**Exemplo:** Um *Usuário* **realiza** um *Empréstimo* de um *Livro*.

No diagrama, relacionamentos são representados por **losangos** conectando as entidades.

```
┌─────────┐       ◇         ┌─────────┐
│ Usuário │────< realiza >────│  Livro  │
└─────────┘                  └─────────┘
```

### Cardinalidade

A cardinalidade define **quantos** de cada lado participam do relacionamento.

| Tipo | Significado | Exemplo |
|---|---|---|
| **1 para 1** (1:1) | Um registro se relaciona com exatamente um outro | Uma pessoa possui um CPF |
| **1 para Muitos** (1:N) | Um registro se relaciona com vários do outro lado | Um professor ministra várias disciplinas |
| **Muitos para Muitos** (N:M) | Vários de um lado com vários do outro | Alunos se matriculam em várias disciplinas, disciplinas têm vários alunos |

---

## 🗺️ Diagrama ER — Resumo visual

Os três componentes principais do diagrama:

```
RETÂNGULO = Entidade        ELIPSE = Atributo        LOSANGO = Relacionamento

┌──────────┐               ( atributo )                  ◇
│ Entidade │                                          relaciona
└──────────┘
```

### Exemplo completo — Sistema de Biblioteca

```
(nome)  (email)                           (título)  (<u>ISBN</u>)
   \      /                                   \      /
┌──────────┐          ◇              ┌──────────┐
│ Usuário  │──── < realiza > ────────│   Livro  │
└──────────┘          ◇              └──────────┘
    <u>matrícula</u>        |                   (autor)
                   ┌──────────┐
                   │Empréstimo│
                   └──────────┘
                  (<u>id_emprestimo</u>)
                  (data_inicio)
                  (data_devolucao)
```

> **Leitura:** Um usuário realiza um empréstimo. Um empréstimo envolve um livro.

---

## ✏️ Atividade — Faça no caderno

**Contexto:** Você foi contratado por uma biblioteca para ajudar a organizar o sistema de dados deles.

**Tarefa:** Monte um Diagrama ER no seu caderno seguindo os passos abaixo.

**Passo 1 — Entidades**  
Desenhe três retângulos com os nomes: `Livro`, `Usuário` e `Empréstimo`.

**Passo 2 — Atributos**  
Para cada entidade, acrescente pelo menos 3 atributos em elipses:
- **Livro:** ISBN, título, autor (e mais um que você escolher)
- **Usuário:** matrícula, nome, email (e mais um que você escolher)
- **Empréstimo:** id_emprestimo, data_inicio, data_devolucao

**Passo 3 — Chave primária**  
Sublinhe o atributo que será a chave primária de cada entidade.

**Passo 4 — Relacionamentos**  
Conecte as entidades com losangos e dê um nome ao relacionamento (ex: "realiza", "inclui").

**Passo 5 — Cardinalidade**  
Pense e anote ao lado de cada relacionamento: é 1:1, 1:N ou N:M?  
- Um usuário pode pegar vários livros emprestados?
- Um livro pode ser emprestado para vários usuários ao mesmo tempo?

---

## 🤔 Desafio extra

Pense em um sistema diferente — pode ser um **pet shop**, uma **escola**, uma **loja de games**, ou qualquer outro contexto que você goste.

No caderno, crie um mini-diagrama ER com:
- Pelo menos **2 entidades**
- **3 atributos** por entidade (com chave primária sublinhada)
- **1 relacionamento** entre elas com a cardinalidade indicada

---

## 📝 Resumindo

| Conceito | O que é | Como aparece no diagrama |
|---|---|---|
| **Entidade** | Objeto do mundo real com informações a guardar | Retângulo |
| **Atributo** | Característica de uma entidade | Elipse |
| **Chave Primária** | Atributo que identifica cada registro de forma única | Atributo sublinhado |
| **Relacionamento** | Ligação entre entidades | Losango |
| **Cardinalidade** | Quantos de cada lado participam do relacionamento | 1:1, 1:N, N:M |

---

## 📚 Quer saber mais?

- [MER e DER: definições e exemplos — Alura](https://www.alura.com.br/artigos/mer-e-der-funcoes)
- [MER e DER: modelagem de bancos de dados — DevMedia](https://www.devmedia.com.br/mer-e-der-modelagem-de-bancos-de-dados/14332)

---

*Na próxima aula vamos ver as ferramentas que os profissionais usam para montar esses diagramas no computador!* 🚀

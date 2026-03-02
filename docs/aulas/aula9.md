---
title: "Aula 9 — Normalização de dados"
layout: default
---

## Antes de começar

Você já reparou que quando você cria um novo grupo no WhatsApp para seus amigos, não precisa repetir todos os detalhes sobre cada amigo? Você só adiciona quem não está lá. Isso é uma forma simples de normalização de dados.

## O que você vai aprender nesta aula
- Entender o conceito de normalização e como ela ajuda na organização dos dados.
- Conhecer as primeiras duas formas normais (1NF e 2NF) em bancos de dados.
- Identificar os benefícios da normalização nos sistemas de banco de dados.

## Normalização de Dados

Você já reparou que quando você cria um novo grupo no WhatsApp para seus amigos, não precisa repetir todos os detalhes sobre cada amigo? Você só adiciona quem não está lá. Isso é uma forma simples de normalização de dados.

A normalização é como organizar sua playlist no Spotify ou seu feed de notícias no Instagram. Ela ajuda a evitar duplicações desnecessárias e mantém tudo bem organizado e sem confusões.

### O que é Normalização?

Normalização é um processo que organiza os dados em tabelas relacionadas para reduzir redundância e inconsistências. É como ter um só lugar onde você guarda todas as informações importantes sobre seus amigos, mas não precisa repeti-las toda vez que adiciona alguém a uma nova lista.

> 🤔 **Para refletir:** Como seria seu feed do Instagram se cada post fosse duplicado várias vezes em diferentes tópicos?

### Exemplo Prático: Escola de Idiomas

Imagine você gerenciando uma escola de idiomas. Quando cria um novo curso, não precisa listar todos os detalhes dos alunos matriculados se ainda não há ninguém inscrito. Isso economiza espaço e mantém o sistema limpo.

### Atividade Prática: Organize sua Biblioteca

Pense em sua coleção de livros como dados em uma base. Faça um esquema simples onde você tem uma tabela para os títulos dos livros, outra para os autores e mais uma que relaciona ambos (relações entre eles). Isso ajuda a evitar repetir informações.

> 🤔 **Para refletir:** Como isso poderia ajudar na gestão de um clube ou grupo escolar?

### Próxima Pergunta

Agora, pense: como você aplicaria esse conceito para organizar suas notas e tarefas da escola?

## Primeira Forma Normal (1NF)

Vamos pensar em um aplicativo de redes sociais que você usa diariamente. Já parou pra pensar como os dados são organizados por trás das telas? Pois bem, hoje vamos aprender sobre a **Primeira Forma Normal**, ou 1NF, uma parte fundamental da forma como estruturamos e gerenciamos nossos bancos de dados.

A 1NF garante que todos os atributos em uma tabela sejam atômicos, ou seja, indivisíveis. Isso significa que cada campo deve conter apenas um valor simples – nada de listas ou conjuntos dentro dos campos!

Imagine um sistema de pedidos online na sua loja favorita. Se você adiciona vários itens no carrinho e o campo **Itens** contém uma lista de produtos, isso violaria a 1NF porque os dados não estão organizados corretamente.

> 🤔 **Para refletir:** Como seria um sistema que seguisse as regras da 1NF?

Vamos fazer algo rápido juntos: pense em uma tabela simples chamada **Pedidos** e liste algumas colunas que ela pode ter. Agora, analise se cada coluna contém apenas valores atômicos.

E aí? Já tem alguma ideia de como estruturar melhor essa tabela para seguir as regras da 1NF?

## Segunda Forma Normal (2NF)

Já parou pra pensar no quanto dependemos de aplicativos todos os dias? Se você usa um app de delivery, ele precisa saber exatamente o que cada item do cardápio é, sem confusão. Vamos entender como a Segunda Forma Normal ajuda nisso.

A 2NF elimina redundâncias em nossos bancos de dados técnicos. Isso significa remover informações desnecessárias e duplicadas ligadas à chave primária que não são absolutamente essenciais para cada registro individual.

Imagine um sistema de pedidos online. A descrição do produto, por exemplo, não deve mudar com a combinação de cliente e data — ela é única e independente dessas informações. Se o cardápio do restaurante muda, a descrição do prato precisa ser atualizada em apenas um lugar, garantindo que todos os pedidos futuros fiquem consistentes.

> 🤔 **Para refletir:** Como você pode aplicar a 2NF na organização de seus próprios dados pessoais ou em apps que usa?

Vamos praticar com um exemplo: pense num banco de dados para uma biblioteca. Qual campo seria redundante se não estiver diretamente relacionado à chave primária (como o ID do livro)?

E agora, como você acha que isso conecta com a Terceira Forma Normal?

## Benefícios da Normalização

Vamos começar pensando nos apps de rede social que você usa. Todo dia, você atualiza suas informações pessoais para garantir que tudo esteja em dia e correto. Agora, imagine ter que fazer isso em cinco ou seis lugares diferentes cada vez... seria bem chato, né?

A normalização no mundo dos bancos de dados serve exatamente para evitar esse tipo de problema. Ela ajuda a organizar os dados de uma maneira que torna tudo mais fácil e eficiente. Vamos ver alguns benefícios específicos da normalização:

### Redução de redundância
Com a normalização, você não precisa repetir informações em várias tabelas. Imagine ter só um lugar onde guardar o endereço do cliente e usar essa informação sempre que necessário.

### Integridade dos dados
A normalização também ajuda a manter os seus registros consistentes e livres de erros. Quando tudo está bem organizado, é menos provável que haja conflitos ou incoerências nos seus dados.

### Melhora o desempenho
Organizar os dados corretamente pode fazer com que as consultas no banco de dados sejam mais rápidas e eficientes. Isso significa que quando você precisa buscar informações, elas vêm mais rápido!

> 🤔 **Para refletir:** Como isso poderia ajudar um sistema de pedidos a funcionar melhor?

Agora, pegue um exemplo simples: em um sistema de pedidos, se o endereço de um cliente mudou, você só precisa atualizar esse dado uma vez. Não é incrível como isso simplifica as coisas? 

Como esses benefícios afetam sistemas maiores e mais complexos?

## Para fechar — com as suas palavras

Escreva em suas próprias palavras o que a normalização de dados significa para você.

## O que fica desta aula
```markdown
- Normalização é um processo que organiza os dados em tabelas relacionadas, reduzindo redundância e inconsistências.
- Primeira Forma Normal (1NF) garante que todos os atributos sejam indivisíveis.
- Segunda Forma Normal (2NF) elimina redundâncias ligadas à chave primária.
```

## Para ir além
- [Artigo sobre normalização de dados](https://www.geeksforgeeks.org/database-normalization/)
- [Vídeo explicativo sobre formas normais](https://www.youtube.com/watch?v=example_video_id)

## Referências
- GeeksforGeeks. (2023). Database Normalization. Recuperado em 15 de março de 2023, de https://www.geeksforgeeks.org/database-normalization/
---
title: "Aula 12 — Casos práticos de normalização"
layout: default
---

## Antes de começar

Antes de mergulharmos nos detalhes da normalização de dados, pense em um aplicativo que você usa regularmente. Como ele gerencia as informações dos usuários? Você já parou para pensar no quanto essas informações precisam ser organizadas e eficientes?

## O que você vai aprender nesta aula

- Entender o conceito de normalização de dados.
- Aprender sobre a Primeira Forma Normal (1NF) e como ela elimina redundâncias.
- Compreender a Segunda Forma Normal (2NF) e suas implicações em tabelas sem dependências parciais.
- Aplicar os conceitos aprendidos em casos práticos de normalização.

## Normalização de Dados

Quando você usa apps sociais e jogos, notou que tudo funciona melhor quando as coisas estão em ordem? A normalização de dados é exatamente isso, mas para bancos de dados.

- Torna os dados mais eficientes.
- Elimina a redundância.

Por exemplo, imagine uma tabela de pedidos onde cada item do pedido está em sua própria linha, ao invés de serem listados como um único valor. Isso ajuda muito na organização e na manipulação dos dados.

### Prática: Reorganize

Vamos pensar em um banco de dados de alunos. Se você tem uma tabela com todas as informações de cada aluno (nome, endereço, telefones), como você a dividiria para melhorar sua eficiência? Tente reestruturar essa tabela mentalmente!

> 🤔 **Para refletir:** Como a normalização pode ajudar em um jogo online que gerencia muitos jogadores e seus dados?

## Primeira Forma Normal (1NF)

Olha só, você já parou pra pensar no quanto seu app de rede social é cheio de informações? E-mails duplicados, endereços repetidos... Isso tudo quebra regras importantes em banco de dados. Vamos aprender a estruturar corretamente!

### Regras Básicas da 1NF

A Primeira Forma Normal (1NF) diz que cada valor deve ser atômico e único dentro de uma tabela. Em outras palavras, não pode ter duplicidade de dados ou grupos de valores em um campo.

🤔 **Para refletir:** Se o seu aplicativo tivesse alunos registrados com informações repetidas em seus perfis, isso seria problema?

### Exemplo no Contexto Escolar

Imagine que cada aluno da sua escola tem um cadastro único e exclusivo. O sistema de registros não pode ter dois cadastros para o mesmo estudante ou duplicar dados como nome, endereço ou telefone.

**Pequena Atividade:** Anote os campos que você acha importantes em seu perfil do Facebook ou Instagram. Agora, pense se esses campos estariam corretamente estruturados seguindo a 1NF?

### Conclusão

Entender a 1NF é crucial para evitar confusão e garantir que cada dado seja único e irrepetível.

🤔 **Para refletir:** Como aplicar as regras da 1NF na criação de um sistema escolar sem erros?

## Entendendo a Segunda Forma Normal (2NF)

Olha, você já reparou quantas informações sobre os seus produtos favoritos aparecem na sua timeline do Instagram? Agora vamos pensar nisso de um jeito mais técnico.

### O que é 2NF?

Vamos começar com o básico: A Segunda Forma Normal, ou 2NF, é alcançada quando uma tabela já está em Primeira Forma Normal (1NF) e não possui dependências parciais. Isso significa que cada informação na tabela deve estar diretamente relacionada à chave primária.

### Exemplo no Mundo Real

Imagine um sistema de vendas. Você tem uma tabela chamada **Produtos**, onde cada produto é identificado por sua ID única (chave primária). Agora, pense em detalhes como o nome do fabricante e a descrição do produto — esses detalhes devem estar diretamente relacionados à chave primária da tabela.

### Prática: Verifique uma Tabela

Pegue um exemplo de tabela com os seguintes campos:

- **ID_Produto**
- **Nome_Fabricante**
- **Descrição**

Verifique se cada campo está adequadamente vinculado à chave primária, que é a **ID_Produto**. Se o nome do fabricante ou a descrição estiverem dependendo de outras informações além da ID do produto, sua tabela não está em 2NF.

> 🤔 **Para refletir:** Como saber se um campo está corretamente vinculado à chave primária? Você pode fazer perguntas como: "Se eu remover essa informação, minha chave primária ainda identifica única e completamente o registro?"

## Aplicação Prática

Olá pessoal! Hoje vamos dar um salto e aplicar tudo que aprendemos sobre 1NF (Primeira Forma Normal) e 2NF (Segunda Forma Normal) em situações reais. Vocês já se pegaram pensando como as redes sociais ou jogos online guardam todas essas informações? Pois bem, hoje vamos explorar um pouquinho disso.

Vamos começar com uma situação hipotética: imagine que vocês estão trabalhando num projeto de gerenciamento de uma rede social. Essa rede tem tabelas de usuários, posts e comentários. Agora, pense nessa base de dados quando ela começa a ficar cheia de repetições desnecessárias e informações inconsistentes.

### Normalizando Dados

Vamos analisar um caso prático onde vocês terão que normalizar uma tabela com problemas de redundância e inconsistência. Imagine que na sua rede social, os usuários podem fazer postagens várias vezes por dia, e cada vez que eles postam, as informações sobre o usuário são repetidas (nome, sobrenome, cidade).

Vamos criar um exemplo rápido:
```sql
CREATE TABLE posts (
  id INT,
  usuario_id INT,
  nome_usuario VARCHAR(255),
  sobrenome_usuario VARCHAR(255),
  cidade_usuario VARCHAR(255),
  texto_post VARCHAR(1000)
);
```

Agora, o desafio é transformar essa tabela em algo mais organizado e eficiente.

🤔 **Para refletir:** Se vocês normalizarem a tabela de posts para a 2NF (removendo redundâncias parciais), quais novas tabelas criariam?

### Atividade

Vamos lá, peguem essa tabela e a transformem em algo mais limpo. **Dica:** Comecem dividindo o que é duplicado.

Depois de fazer isso, vamos discutir como cada nova tabela funciona melhor para nosso projeto e quais problemas ela resolve.

Como vocês acham que podemos aplicar o mesmo processo ao banco de dados de um jogo online? Vamos pensar nisso na próxima aula!

## Para fechar — com as suas palavras

Escreva em suas próprias palavras sobre como a normalização de dados pode melhorar a eficiência e a organização dos bancos de dados.

## O que fica desta aula
```markdown
- Primeira Forma Normal (1NF): cada valor deve ser atômico e único dentro da tabela.
- Segunda Forma Normal (2NF): elimina dependências parciais, mantendo apenas informações diretamente relacionadas à chave primária.
- Aplicação prática: normalização de tabelas com redundâncias e inconsistências para melhorar a eficiência do banco de dados.
```

## Para ir além

1. **Artigo:** [Normalização de Dados em SQL](https://www.geeksforgeeks.org/sql-normalization/)
2. **Vídeo:** [Entendendo a Normalização de Dados com Exemplos Práticos](https://www.youtube.com/watch?v=example_video_id)

## Referências

- GeeksforGeeks, "SQL Normalization". Disponível em: https://www.geeksforgeeks.org/sql-normalization/
- YouTube, "Entendendo a Normalização de Dados com Exemplos Práticos". Disponível em: https://www.youtube.com/watch?v=example_video_id
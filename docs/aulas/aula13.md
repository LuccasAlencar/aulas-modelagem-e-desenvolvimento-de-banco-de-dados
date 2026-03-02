---
title: "Aula 13 — Terceira Forma Normal (3NF)"
layout: default
---

## Antes de começar

Você já parou para pensar em quantas vezes o mesmo dado é repetido nas redes sociais ou em jogos online? Essa redundância pode causar problemas significativos na manutenção e integridade dos dados. Hoje, vamos explorar como a **Terceira Forma Normal (3NF)** ajuda a evitar esses problemas.

## O que você vai aprender nesta aula

- Entender o conceito de 3NF e sua importância em bancos de dados.
- Como identificar redundâncias desnecessárias e eliminar delas.
- Praticar a criação de tabelas que seguem as diretrizes da 3NF.

## Primeira Forma Normal (1NF)

A **Primeira Forma Normal** é sobre fazer as coisas de forma mais simples e prática. Imagine um banco de dados onde cada informação precisa ser única e não pode ser dividida ainda mais, sem duplicação e com valores únicos em cada campo.

### Cada Campo É Atômico
Cada informação deve ser única e indivisível. Por exemplo, se você tem um campo chamado "Endereço", ele deve conter apenas uma string completa de endereço e não partes separadas como "rua" ou "número".

### Sem Duplicação
Imagine ter várias linhas na tabela com o mesmo nome de aluno. Isso é ineficiente e confuso, certo? Na 1NF, cada registro precisa ser único.

### Valores Únicos
Aqui, cada campo deve conter apenas um valor e esse valor não pode ser nulo (a menos que seja expressamente permitido).

> 🤔 **Para refletir:** Se você pudesse escolher uma rede social onde cada informação fosse única e atômica, quais seriam as vantagens disso?

Agora pense comigo: como seria criar um cadastro de alunos seguindo a 1NF? Vamos colocar em prática! Abra um editor de texto ou um banco de dados e crie uma tabela simples onde cada nome do aluno apareça apenas uma vez.

E aí, já entendeu o básico da 1NF? E agora, como você aplicaria isso para garantir que outras informações pessoais também sigam essa regra?

## Segunda Forma Normal (2NF)

A **Segunda Forma Normal** é alcançada quando a tabela está na Primeira Forma Normal e não tem dependências funcionais parciais. Isso significa que todos os atributos, ou colunas, devem depender completamente da chave primária.

### A 2NF: Melhorando a Organização

Vamos dar um exemplo prático. Imagine que temos uma tabela `Vendas` com os seguintes campos: ID_Venda, Produto_ID, Nome_Produto, Preço_Produto, Data_Venda.

Agora, pense no campo `Preço_Produto`. Ele só faz sentido se sabemos sobre o produto específico, certo? Então, na verdade, o preço não depende apenas da venda, mas também do produto em si. Para seguir a 2NF corretamente, precisaríamos criar uma nova tabela, como `Produtos`, com os campos `Produto_ID` e `Preço`.

### Atividade Prática

Vamos fazer um exercício rápido: Se você tiver uma tabela de `Pedidos_Clientes` com dados como ID_Pedido, Nome_Cliente, Endereço_Cliente, Item_Identificador, Quantidade_Item, preço_item... Qual campo (ou campos) não está seguindo a 2NF?

Entender a 2NF é crucial para criar bancos de dados eficientes e bem estruturados. Vocês estão prontos para aprender sobre a Terceira Forma Normal agora?

## Benefícios da Normalização

A normalização ajuda a eliminar redundâncias e garantir a integridade dos dados, tornando o sistema mais organizado e livre de erros.

### Exemplo Prático: Sistema de Estoque Sem E Com Normalização

Vamos imaginar um exemplo concreto. Suponha que você está trabalhando em um sistema de estoque para uma loja de eletrônicos. Em cada vez que um novo modelo de smartphone é adicionado, o nome do fabricante é inserido várias vezes em diferentes tabelas ao longo do tempo.

> 🤔 **Para refletir:** Por que seria ruim ter o mesmo dado repetido várias vezes?

**Atividade Prática:**
Pense numa situação onde você precisa alterar a descrição de um produto. Se esse produto estiver listado em vários lugares, você precisará fazer essa mudança em cada lugar individualmente. Agora, como isso ficaria mais fácil se pudéssemos centralizar as informações?

E o que acontece quando uma informação se torna obsoleta? Como podemos garantir que ela não cause confusão no sistema de dados da empresa?

Vamos continuar explorando esses conceitos na próxima aula. Você já parou para pensar em como os bancos de dados mantêm as informações atualizadas e precisas?

## Terceira Forma Normal (3NF)

A **Terceira Forma Normal** é um nível mais avançado de normalização que ajuda a eliminar redundâncias desnecessárias nos bancos de dados. Ela garante que todos os atributos não-chave dependam diretamente da chave primária.

### Como Funciona?

Vamos imaginar uma situação real: você está criando um sistema para gerenciar cursos e alunos. Se o nome do curso é armazenado separadamente para cada aluno, fica fácil perceber que se houver 100 alunos em um mesmo curso, o nome do curso será repetido 100 vezes.

> 🤔 **Para refletir:** Como isso poderia causar problemas na manutenção de dados?

### Exemplo Prático

Considere uma tabela chamada `Alunos_Cursos` com os campos `ID_Aluno`, `Nome_Aluno`, `ID_Curso`, e `Nome_Curso`. Agora, vamos criar duas tabelas separadas: uma para armazenar informações sobre alunos e outra para cursos.

- **Tabela Alunos:** `ID_Aluno`, `Nome_Aluno`
- **Tabela Cursos:** `ID_Curso`, `Nome_Curso`

Na tabela que relaciona os dois, teremos apenas os campos de chave estrangeira:

- **Alunos_Cursos:** `ID_Aluno` (chave estrangeira para Alunos) e `ID_Curso` (chave estrangeira para Cursos).

### Atividade: O Que Você Faria?

Suponha que você está criando um sistema de matrículas online. Como você garantiria que o nome do curso não seja duplicado quando um aluno se matricula em vários cursos? Escreva como dividiria as tabelas.

## Próxima Pergunta

Prontos para aplicar isso na prática? Na próxima aula, veremos exemplos de como implementar 3NF em bancos de dados reais. Vocês estarão preparados?

Qual exemplo vocês acham que seria mais complexo implementar sem seguir as diretrizes da 3NF?

## Para fechar — com as suas palavras

Escreva, por favor, o que você aprendeu sobre a Terceira Forma Normal (3NF) e como ela pode ser aplicada em um sistema de banco de dados.

## O que fica desta aula
```markdown
- 1NF: Cada campo é atômico, sem duplicação e com valores únicos.
- 2NF: Elimina dependências funcionais parciais.
- 3NF: Garante que todos os atributos não-chave dependam diretamente da chave primária.
```

## Para ir além

1. [Artigo sobre Normalização de Dados](https://www.geeksforgeeks.org/database-normalization/)
2. [Guia Prático para a Terceira Forma Normal (3NF)](https://www.tutorialspoint.com/dbms/dbms_third_normal_form.htm)

## Referências

- GeeksforGeeks, "Database Normalization". Disponível em: https://www.geeksforgeeks.org/database-normalization/
- Tutorialspoint, "DBMS Third Normal Form (3NF)". Disponível em: https://www.tutorialspoint.com/dbms/dbms_third_normal_form.htm
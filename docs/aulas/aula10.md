---
title: "Aula 10 — Primeira Forma Normal (1NF)"
layout: default
---

## Antes de começar

🤔 **Para refletir:** Como você poderia representar vários números de telefone para um cliente sem violar a Primeira Forma Normal?

## O que você vai aprender nesta aula

- Entender o conceito da Primeira Forma Normal (1NF) e sua importância na modelagem de bancos de dados.
- Identificar valores atômicos em tabelas existentes.
- Criar estruturas de tabela adequadas para evitar violações da 1NF.

## Primeira Forma Normal (1NF)

Olá pessoal! Hoje vamos falar sobre um conceito importante na modelagem de bancos de dados, chamado **Primeira Forma Normal** (1NF). Imagina que você está usando o Instagram e quer adicionar vários números de telefone para contato. Na vida real do banco de dados, isso seria problemático!

### Garantindo Valores Atômicos
A Primeira Forma Normal exige que cada coluna em uma tabela contenha apenas valores atômicos. Em outras palavras, cada campo deve conter um único valor e não combinações ou listas separadas por vírgula.

🤔 **Para refletir:** Como você poderia representar vários números de telefone para um cliente sem violar a 1NF?

Vamos usar um exemplo prático: suponha que temos uma tabela chamada `Clientes` com o campo `TELEFONES_CLIENTE`, onde cada cliente pode ter múltiplos telefones. O que acontece se tentarmos adicionar um novo número para um cliente? > 🤔 **Para refletir:** Por que essa situação não atende aos requisitos da 1NF?

A solução é criar uma nova tabela, chamada `Telefones_Cliente`, onde cada linha representa um telefone associado a um determinante único do cliente. Assim, mantemos os dados limpos e organizados!

### Atividade Prática
Crie duas tabelas: `Clientes` (com campos como ID_CLIENTE, NOME_CLIENTE) e `Telefones_Cliente` (que inclui ID_CLIENTE, NUMERO_TELEFONE). Insira alguns registros para entender a estrutura.

Como você gostaria de continuar explorando a normalização de bancos de dados? Vamos falar sobre a Segunda Forma Normal na próxima aula!

## Dependência Funcional

Olá pessoal! Já repararam que cada vez que vocês abrem um app de redes sociais, os posts aparecem na ordem certa? É como se o aplicativo soubesse exatamente quais são as suas preferências. Bem, isso tem muito a ver com dependência funcional!

Quando falamos em bancos de dados, uma dependência funcional é quando um conjunto de atributos determina exclusivamente o valor de outro conjunto. Por exemplo, pense numa tabela de clientes onde cada cliente tem um código único.

### Exemplo: Código do Cliente e Nome do Cliente

Imagine que vocês estão criando um sistema para a biblioteca da escola. Cada aluno tem um número de matrícula exclusivo. Esse número determina o nome do estudante, certo? > 🤔 **Para refletir:** E se dois alunos tivessem o mesmo número de matrícula? Como isso afetaria a relação entre número e nome?

Agora, tentem pensar: em sua tabela de clientes (ou alunos), como vocês certificariam que cada código é único? 

### Atividade

Peguem papel e caneta. Façam uma breve tabela com alguns números de matrícula e nomes correspondentes.

Pronto? Agora, vamos pensar: o que aconteceria se adicionássemos mais informações sobre os alunos, como telefones ou endereços?

O que vocês acham? Como essa nova informação afetaria a dependência funcional entre número de matrícula e nome?

## Entendendo Chaves Primárias e Estrangeiras

Imagine você navegando pelo Instagram. Cada post que você vê tem um ID único, certo? Isso é parecido com o conceito de chave primária em uma tabela do banco de dados.

### O Que É Uma Chave Primária?

Uma chave primária identifica cada registro de forma única numa tabela. Por exemplo, na tabela Produtos, **ID_Produto** é a chave primária. Cada produto tem seu próprio número exclusivo.

> 🤔 **Para refletir:** Como você garantiria que todos os produtos em uma loja online têm IDs únicos?

### Chave Estrangeira: Referenciando Outros

Agora, pense nas suas compras online. Quando você compra um produto e registra o pedido, a tabela Pedidos tem um campo chamado **ID_Cliente**. Este ID referencia a tabela Clientes, tornando-o uma chave estrangeira.

> 🤔 **Para refletir:** Por que é importante ter uma chave estrangeira referenciando outra tabela?

### Atividade Rápida

Imagine você está criando um sistema para gerenciar livros em uma biblioteca. Crie um exemplo onde:
- A tabela Livro tem como chave primária o **ID_Livro**.
- Na tabela Emprestimo, há um campo chamado **ID_Leitor**, que é a chave estrangeira referenciando a tabela Leitores.

### Próxima Reflexão

Como você usaria chaves primárias e estrangeiras para conectar tabelas em um sistema de gerenciamento escolar?

## Para fechar — com as suas palavras
Escreva, usando suas próprias palavras, o que aprendeu sobre a Primeira Forma Normal (1NF), dependência funcional e chaves primárias e estrangeiras.

## O que fica desta aula

```markdown
- **Primeira Forma Normal (1NF):** Garante que cada coluna em uma tabela contenha apenas valores atômicos.
- **Dependência Funcional:** Um conjunto de atributos determina exclusivamente o valor de outro conjunto.
- **Chave Primária:** Identifica registros de forma única numa tabela.
- **Chave Estrangeira:** Referencia outra tabela, estabelecendo uma relação entre tabelas.
```

## Para ir além
1. [W3Schools - SQL Normalization](https://www.w3schools.com/sql/sql_normalization.asp)
2. [GeeksforGeeks - First Normal Form (1NF)](https://www.geeksforgeeks.org/first-normal-form-1nf-in-dbms/)

## Referências
- W3Schools, "SQL Normalization". Disponível em: https://www.w3schools.com/sql/sql_normalization.asp.
- GeeksforGeeks, "First Normal Form (1NF) in DBMS". Disponível em: https://www.geeksforgeeks.org/first-normal-form-1nf-in-dbms/.
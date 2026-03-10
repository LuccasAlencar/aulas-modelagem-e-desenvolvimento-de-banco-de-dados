---
title: "Aula 16 — Resumo e revisão das formas normais"
layout: default
---

## Antes de começar

Você já parou para pensar em quantas vezes você precisa digitar seu nome completo naquele aplicativo novo que acabou de instalar? Pois é, o mesmo princípio usado por esses apps também se aplica à base de dados. Hoje, vamos revisar as formas normais e entender como elas ajudam a organizar nossos bancos de dados.

## O que você vai aprender nesta aula

- Entender e aplicar a Primeira Forma Normal (1NF) para garantir unicidade de dados.
- Aprender sobre a Segunda Forma Normal (2NF) e como remover dependências parciais.
- Compreender a Terceira Forma Normal (3NF) e eliminar redundâncias transitivas.
- Verificar tabelas usando a forma normal de Boyce-Codd (BCNF).

## Primeira Forma Normal (1NF)

Olá, pessoal! Você já parou pra pensar em quantas vezes você precisa digitar seu nome completo naquele aplicativo novo que acabou de instalar? Pois é, o mesmo princípio usado por esses apps também se aplica à base de dados.

### Eliminando redundâncias

Vamos falar sobre como garantir que cada entrada seja única em uma tabela. Isso significa que se temos um campo para nomes, não podemos ter duplicatas como "João Silva" repetido várias vezes. Cada aluno só aparece uma vez na tabela.

> 🤔 **Para refletir:** Se você fosse responsável por manter essa lista de alunos, quais problemas poderiam surgir com nomes duplicados?

### Exemplo: Tabela de Alunos

Vamos criar juntos uma tabela simples de alunos para ilustrar isso:

```markdown
| ID | NOME        |
|----|------------|
| 1  | João Silva |
| 2  | Maria Souza|
| 3  | Ana Costa  |
```

Agora, imagine se tivéssemos duplicado o nome de "João Silva". A tabela ficaria confusa e difícil de gerir.

**Atividade:** Tente adicionar mais dois alunos nessa tabela sem repetir nomes.

### Conclusão

Lembrando que cada entrada deve ser única ajuda a manter nossas tabelas limpas e fáceis de entender, não é mesmo?

E vocês, já notaram algum lugar na vida cotidiana onde a ideia da unicidade de dados seria útil?

---

## Segunda Forma Normal (2NF)

Olá pessoal! Já pararam para pensar em quantos apps vocês usam todos os dias? Cada um deles armazena informações diferentes sobre você — desde fotos até amigos. Agora, imagine que cada aplicativo fosse uma grande tabela onde tudo é misturado juntos. A Segunda Forma Normal (2NF) nos ajuda a organizar essas tabelas de forma mais lógica e eficiente.

### Removendo Dependências Parciais

A ideia por trás da 2NF é garantir que as informações não estejam espalhadas desnecessariamente. Imagine você tem uma tabela para aluguéis de carros onde estão todos os dados: clientes, endereços, modelos e marcas dos carros, datas de locação, etc.

> 🤔 **Para refletir:** Como a informação sobre diferentes partes da operação (cliente, carro) pode ser prejudicada se tudo estiver juntos em uma única tabela?

Vamos criar um exemplo prático. Se tivéssemos uma tabela com todas essas informações sobre aluguéis de carros, e quiséssemos apenas alterar o endereço do cliente, precisaríamos atualizar várias linhas da tabela. Isso seria complicado e mais propenso a erros.

### Dividindo em Tabelas Mais Específicas

A solução é separar esses dados em tabelas menores que fazem sentido individualmente. Então teríamos uma tabela para os **clientes** com seus respectivos endereços, outra para as informações sobre os **carros**, e uma **tabela de aluguéis** que conecta essas duas.

> 🤔 **Para refletir:** Como a separação dos dados em tabelas mais específicas facilitaria o gerenciamento das informações?

Agora é a vez de vocês! Pensem numa tabela que contém várias informações misturadas e sugira como poderíamos dividi-la para atender à 2NF. Escreva isso no papel ou num documento.

---

## Terceira Forma Normal (3NF)

Olá, pessoal! Já pararam pra pensar em quantas informações vocês armazenam todos os dias nos aplicativos de celular? Desde compras no app do cartão até notas nas suas redes sociais educacionais. Agora, imagine se cada nota fosse repetida várias vezes, como ficaria a sua experiência?

Vamos falar sobre um jeito de organizar dados para que eles não se tornem redundantes e confusos. A **Terceira Forma Normal (3NF)** é uma regra do desenho de banco de dados que nos ajuda nisso, garantindo que os nossos registros estejam sempre limpos e eficientes.

### Eliminando dependências transitivas

A ideia principal aqui é remover informações que já podem ser inferidas a partir de outras. Por exemplo, na tabela de aluguéis, uma coluna chamada 'Valor Total' poderia ser removida porque o valor total pode ser calculado somando o preço por mês e multiplicando pela duração do contrato.

> 🤔 **Para refletir:** Se você tivesse que criar um banco de dados para registrar todas as suas compras, quais colunas seriam redundantes?

### Prática: Removendo a coluna 'Valor Total'

Vamos colocar isso em prática. Imagina uma tabela de aluguéis onde cada linha representa um contrato e inclui o preço por mês e a duração do contrato. Agora, remova a coluna 'Valor Total' da sua tabela fictícia e pense como você poderia calcular este valor quando necessário.

### Próximo passo

Agora que entendemos a importância de remover redundâncias, como podemos aplicar esses conceitos para melhorar outros tipos de bancos de dados?

Qual banco de dados do seu cotidiano você gostaria de organizar melhor usando o 3NF?

---

## Forma Normal de Boyce-Codd (BCNF)

Quando você está jogando um jogo e quer coletar itens específicos, precisa saber exatamente o que fazer sem confusão, certo? Na programação de banco de dados, temos algo parecido com a forma normal de Boyce-Codd (BCNF), que ajuda a garantir que nossas tabelas estejam bem organizadas e livres de problemas.

### Verificando Dependências Funcionais

Vamos pensar nos grupos de amigos em redes sociais. Se uma pessoa aceitar um convite, todos os seus amigos também devem ser notificados automaticamente? Isso poderia criar confusão se não estiver bem definido quem manda as notificações.

Na BCNF, nós verificamos que cada dependência funcional tem como determinante (ou causa) uma superchave. Uma superchave é aquela que pode identificar exclusivamente todas as linhas de nossa tabela sem precisar de ajuda de outras colunas.

> 🤔 **Para refletir:** Como você garantiria que um convite em uma rede social seja processado corretamente para todos os membros do grupo?

### Exemplo Prático

Vamos imaginar que temos uma tabela chamada "Postagens" onde cada postagem pertence a um usuário. Se tentarmos adicionar detalhes sobre o perfil de quem fez o post na mesma linha, isso poderia causar duplicação desnecessária ou inconsistências.

### Atividade: Verificação BCNF

Vamos analisar uma tabela simplificada chamada "Amizades". Ela tem três colunas: `ID_Usuario1`, `ID_Usuario2` e `TipoRelacao`. O tipo de relação pode ser "amigo", "conhecido" ou "inimigo".

Pergunta: Se `ID_Usuario1` e `ID_Usuario2` juntos formarem uma superchave, como podemos garantir que a tabela está em BCNF? Verifique se cada dependência funcional (por exemplo, `(ID_Usuario1, ID_Usuario2) -> TipoRelacao`) tem um determinante que é uma superchave.

### Ponto Final

Depois de verificar e ajustar nossa tabela para BCNF, nós reduzimos a chance de anomalias em operações de inserção, atualização ou exclusão. Isso faz com que nossos bancos de dados funcionem suavemente, assim como um jogo bem projetado.

E agora, pense: Como seria garantir essa consistência se tivéssemos múltiplas tabelas interligadas?

## Ponto Final

Hoje, revisamos as formas normais e vimos como elas ajudam a organizar nossos bancos de dados. Agora você pode aplicar esses princípios para criar sistemas mais eficientes e consistentes.

---

## Escreva o que aprendeu hoje

- **Primeira Forma Normal (1NF):** Garante unicidade de dados.
- **Segunda Forma Normal (2NF):** Remove dependências parciais.
- **Terceira Forma Normal (3NF):** Elimina redundâncias transitivas.
- **Forma Normal de Boyce-Codd (BCNF):** Verifica dependências funcionais com superchaves.

---

## Perguntas para reflexão

1. Como você aplicaria a 2NF em um banco de dados que contém informações sobre funcionários e departamentos?
2. Que tipo de redundância poderia ser removida usando a 3NF em um sistema de vendas online?

---

Esperamos que esta revisão tenha ajudado você a entender melhor as formas normais e como elas são fundamentais para o design eficiente de bancos de dados. Continue praticando e aplicando esses conceitos!
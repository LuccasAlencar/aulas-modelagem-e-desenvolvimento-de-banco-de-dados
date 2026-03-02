---
title: "Aula 5 — Relacionamentos um-para-um"
layout: default
---

## Antes de começar

Você já usou apps de namoro que pareiam você com uma única pessoa perfeita? Esse conceito é parecido com o tipo de relacionamento que vamos aprender hoje.

## O que você vai aprender nesta aula

- Entender e aplicar o conceito de relacionamentos um-para-um.
- Definir chaves primárias e estrangeiras em bancos de dados.
- Criar diagramas entidade-relacionamento (DER) para visualizar relacionamentos.
- Identificar exemplos práticos de relacionamentos um-para-um no mundo real.

## Relacionamentos um-para-um

Você já usou apps de namoro que pareiam você com uma única pessoa perfeita? Esse conceito é parecido com o tipo de relacionamento que vamos aprender hoje.

Um relacionamento um-para-um é quando cada item em uma lista está ligado a exatamente um item na outra lista, e vice-versa. No mundo da tecnologia, isso pode ser como um paciente tendo um prontuário médico exclusivo. Nenhum outro paciente pode usar esse mesmo prontuário.

Vamos pensar nisso com algo mais familiar: cada pessoa em seu Instagram tem apenas uma conta. Não compartilhamos contas; você tem a sua, eu tenho a minha. Isso é um exemplo de relacionamento um-para-um.

> 🤔 **Para refletir:** Como esse conceito se aplica às redes sociais além da conta única?

Agora vamos criar uma tabela simples em que cada aluno esteja associado a apenas uma carteira na sala de aula. Crie essa estrutura e pense nas regras desse relacionamento.

E agora, como aplicaríamos esse mesmo conceito para ligar um livro a sua capa única? Como isso muda nossa compreensão do que é um relacionamento um-para-um?

Qual exemplo você gostaria de explorar mais na próxima aula?

## Implementação de Relacionamentos 1:1

Quando você usa um aplicativo de rede social, cada perfil está conectado ao seu próprio histórico de postagens. Isso é um exemplo de relacionamento um-para-um.

### Definindo Chaves Primárias e Estrangeiras
Para criar essa conexão em um banco de dados, precisamos definir chaves primárias e estrangeiras entre as tabelas envolvidas. No caso do sistema hospitalar:
- A chave primária da tabela 'Paciente' é o ID.
- Esse mesmo ID se torna a chave estrangeira na tabela 'Histórico Médico'.

### Exemplo Prático
Vamos criar uma situação prática: imagine que você está desenvolvendo um app de fitness. Crie duas tabelas, ‘Usuário’ e ‘Dieta’. A chave primária da tabela Usuário será a chave estrangeira na tabela Dieta.

> 🤔 **Para refletir:** Como o relacionamento entre 'Usuário' e 'Dieta' poderia ser diferente se você quisesse permitir que múltiplos usuários compartilhassem uma dieta?

### Próximo Passo
Agora que entendemos como definir um relacionamento 1:1, vamos explorar mais exemplos práticos. Como seria a implementação de um sistema bancário onde cada conta tem um único titular?

## Diagramas Entidade-Relacionamento (DER)

Vamos começar pensando no seu perfil do Instagram. Quando você segue alguém, essa pessoa também precisa te seguir de volta para que seja um amigo? Ou é suficiente apenas uma das partes seguir?

> 🤔 **Para refletir:** Como você descreveria a relação entre "você" e "pessoas que você segue" no Instagram? É sempre mutuamente exclusivo?

### Relacionamentos Um-para-Um

Na verdade, em muitos casos do mundo real — como quando duas contas de redes sociais se tornam amigas ou em um sistema onde cada usuário tem apenas uma conta bancária associada a ele — o relacionamento é simétrico e exclusivo. Isso é chamado de **relacionamento um-para-um**.

### Visualizando com DER

Um diagrama entidade-relacionamento (DER) nos ajuda a visualizar esses tipos de relacionamentos. Para representar um relacionamento um-para-um, usamos uma linha simples ou dupla que conecta duas entidades no nosso desenho, indicando que cada instância da primeira entidade está vinculada a exatamente uma instância da segunda e vice-versa.

### Atividade Prática

Vamos criar um exemplo simples. Considere as entidades "Aluno" e "Cartão Alimentação". Em muitos sistemas, cada aluno tem um cartão alimentação exclusivo para uso na cantina escolar. Como você representaria essa relação em um DER?

- Desenhe duas caixas retangulares: uma rotulada como "Aluno", a outra como "Cartão Alimentação".
- Agora, conecte as duas entidades com uma linha dupla. Por que você acha que usamos uma linha dupla aqui?

### Ponto de Reflexão

Agora pense em outras situações do seu cotidiano onde um relacionamento um-para-um pode ser aplicado. Você poderia pensar em um exemplo envolvendo jogos? Como seria o DER para essa situação?

## Aplicações Práticas de Relacionamentos Um-Para-Um

Você já parou pra pensar no quão simples é cadastrar um novo perfil num aplicativo ou site? Cada vez que você cria uma conta em algum lugar, seja para comprar algo online ou interagir numa rede social, está usando um sistema de relacionamento um-para-um. Isso quer dizer que cada usuário tem **exatamente um** perfil único.

### Relacionamentos Um-Para-Um no Mundo Real

Em um hospital, por exemplo, cada paciente precisa ter um registro médico exclusivo. Não dá para misturar informações de pacientes diferentes, certo? Essa é uma aplicação direta do conceito que estamos estudando hoje.

> 🤔 **Para refletir:** Como você acha que essa lógica pode ajudar em sistemas de gerenciamento de clientes?

Agora, vamos fazer um exercício rápido: pense num serviço ou produto online que você usa regularmente e identifique onde o sistema usa relacionamentos um-para-um. Por exemplo, cada pedido na sua conta do Uber Eats tem que ser exclusivo para você.

E como isso se aplica a outras áreas da vida? Como seria gerenciar essas informações sem essa estrutura de dados?

Qual desses exemplos te fez pensar mais sobre como sistemas reais funcionam?

## Para fechar — com as suas palavras

Escreva um parágrafo descrevendo o que você aprendeu hoje sobre relacionamentos um-para-um, usando suas próprias palavras.

## O que fica desta aula
```markdown
1. Relacionamento um-para-um: cada item em uma lista está ligado a exatamente um item na outra lista e vice-versa.
2. Chaves primárias e estrangeiras são usadas para definir relacionamentos entre tabelas em bancos de dados.
3. Diagramas entidade-relacionamento (DER) ajudam a visualizar e entender os tipos de relacionamentos existentes.
```

## Para ir além
- [Diagrama Entidade-Relacionamento](https://www.tutorialspoint.com/dbms/dbms_er_model.htm)
- [Relacionamentos em Bancos de Dados](https://www.guru99.com/database-normalization-tutorial.html)

## Referências
- Tutorial Point. (2021). ER Model in DBMS.
- Guru99. (2021). Database Normalization Tutorial.
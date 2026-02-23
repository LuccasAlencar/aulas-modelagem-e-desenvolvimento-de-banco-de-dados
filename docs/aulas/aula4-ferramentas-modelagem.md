# Aula 4 — Ferramentas de Modelagem de Banco de Dados

> **Componente:** Modelagem e Desenvolvimento de Banco de Dados  
> **Unidade:** Levantamento de Dados e Conceitos Fundamentais  
> **Duração:** ~50 minutos

---

## 🎯 O que você vai aprender hoje

Na aula anterior você aprendeu a montar um Diagrama ER no papel. Hoje vamos descobrir:

- Quais **ferramentas digitais** os profissionais usam para criar esses diagramas
- O que são o **MySQL Server** e o **MySQL Workbench** e como eles se relacionam
- Como pensar na **coleta de requisitos** antes de sair modelando qualquer coisa
- Uma atividade de reflexão sobre como trabalhar em equipe num projeto real

---

## 🛠️ Ferramentas de modelagem — para que servem?

Fazer o diagrama no papel é ótimo para aprender e para rascunhar ideias. Mas no dia a dia profissional, usamos **ferramentas digitais** que:

- Deixam o diagrama mais organizado e fácil de editar
- Permitem **exportar o modelo diretamente para o banco de dados** (geram o código SQL automaticamente!)
- Facilitam o trabalho em equipe — todo mundo acessa e edita o mesmo arquivo

Vamos conhecer as duas principais.

---

## 🐬 MySQL Workbench

O **MySQL Workbench** é uma ferramenta **gratuita e visual** para trabalhar com bancos de dados MySQL. Com ela você consegue:

- Criar e editar **Diagramas ER** arrastando elementos na tela
- Gerenciar o banco de dados (criar tabelas, inserir dados, rodar consultas)
- **Exportar** o diagrama e gerar automaticamente o script SQL para criar as tabelas

> 💡 **Analogia:** pense no Workbench como o Word do banco de dados — uma interface amigável para você trabalhar visualmente sem precisar digitar tudo na linha de comando.

### MySQL Server vs MySQL Workbench — qual é a diferença?

Essa confusão é muito comum! Veja a diferença:

| | MySQL **Server** | MySQL **Workbench** |
|---|---|---|
| **O que é** | O motor do banco de dados — é ele que armazena e gerencia os dados de verdade | A interface gráfica para você interagir com o Server |
| **Analogia** | O motor de um carro | O painel e o volante do carro |
| **Sem o outro** | Funciona, mas você só acessa pela linha de comando | Não funciona sozinho — precisa se conectar ao Server |

> **Resumindo:** o **Server** é o banco de dados em si. O **Workbench** é a ferramenta que você usa para *conversar* com ele de forma visual.

---

## 🏢 ER/Studio

O **ER/Studio** é uma ferramenta **comercial** (paga) usada em empresas maiores. Tem recursos mais avançados, como:

- Suporte a vários tipos de banco de dados (não só MySQL)
- Repositório compartilhado para equipes grandes
- Recursos avançados de documentação do banco de dados

### Comparativo rápido

| Característica | MySQL Workbench | ER/Studio |
|---|---|---|
| Custo | Gratuito | Pago |
| Banco de dados | MySQL | Vários |
| Facilidade de uso | Alta | Alta |
| Recursos avançados | Moderados | Avançados |
| Indicado para | Aprendizado e projetos | Grandes empresas |

> 📌 Para o nosso curso, trabalharemos com o **MySQL Workbench**, por ser gratuito e amplamente usado no mercado.

---

## 📋 Antes de modelar: Levantamento de Requisitos

Sabe o que todo bom desenvolvedor faz **antes** de abrir qualquer ferramenta e criar qualquer tabela? Ele conversa com o cliente.

Esse processo se chama **levantamento de requisitos** e é a etapa mais importante de qualquer projeto de software.

**O que são requisitos?**  
São todas as informações, regras e funcionalidades que o sistema precisa ter para atender às necessidades do cliente.

**Por que isso importa para o banco de dados?**  
Porque só depois de entender o que o sistema precisa fazer, você consegue saber:
- Quais **entidades** existem
- Quais **atributos** cada entidade precisa ter
- Quais **relacionamentos** existem entre elas

Se você pular essa etapa e sair modelando "no chute", vai precisar refazer tudo quando descobrir que esqueceu algo importante.

---

## ✏️ Atividade 1 — Faça no caderno (individual)

**Contexto:** Você foi contratado por um pet shop para desenvolver um sistema de gestão. Antes de criar qualquer tabela, você precisa levantar os requisitos conversando com o dono.

**Tarefa:** Escreva no mínimo **8 perguntas** que você faria ao dono do pet shop para entender o que o sistema precisa ter.

**Dica — pense em:**
- Quais informações sobre os **animais** precisam ser registradas?
- Como funciona o **agendamento** de banho, tosa ou consulta?
- Como são controlados os **produtos** da loja?
- Como os **clientes** são cadastrados?
- O sistema precisa gerar algum tipo de **relatório**?

---

**Exemplo de perguntas para te inspirar:**

> - "Quais dados do animal precisam ser registrados (nome, espécie, raça, peso...)?"
> - "Um cliente pode ter mais de um animal cadastrado?"
> - "Como funciona o pagamento — à vista, cartão, parcelado?"

---

## ✏️ Atividade 2 — Faça no caderno (reflexão)

Imagine que você faz parte de uma equipe de 4 pessoas. Vocês têm **2 dias** para levantar os requisitos de um sistema para o pet shop e apresentar um esboço do diagrama ER para o cliente.

Responda no caderno:

1. **Empatia:** Como você colocaria em prática a empatia ao conversar com o dono do pet shop? O que você faria para realmente entender o dia a dia dele, e não só "fazer o trabalho"?

2. **Comunicação em equipe:** Como você garantiria que todos os 4 membros da equipe entenderam o mesmo coisa após as entrevistas com o cliente? Que estratégias você usaria?

3. **Pressão e prazo:** Com apenas 2 dias, como você organizaria o trabalho para não se sentir perdido? Como dividiria as tarefas?

---

## 🗺️ Do requisito ao diagrama — o fluxo completo

Agora você já conhece todas as etapas. Veja como elas se conectam:

```
1. Conversar com o cliente
        ↓
2. Levantar os requisitos
   (o que o sistema precisa fazer/guardar)
        ↓
3. Identificar as entidades e atributos
        ↓
4. Montar o Diagrama ER (no papel ou na ferramenta)
        ↓
5. Exportar para o banco de dados
   (criar as tabelas de verdade)
```

---

## 🧩 Atividade 3 — Desafio no caderno

Com base nas perguntas que você criou na Atividade 1 para o pet shop, agora monte um **Diagrama ER inicial** no caderno.

Requisitos mínimos do diagrama:
- Pelo menos **3 entidades** (ex: Animal, Tutor, Agendamento)
- Pelo menos **3 atributos** por entidade, com a chave primária **sublinhada**
- Pelo menos **2 relacionamentos** com a **cardinalidade** indicada (1:1, 1:N ou N:M)

> 💬 **Não existe resposta única!** Dependendo das perguntas que você criou, seu diagrama pode ser diferente do do colega — e ambos podem estar corretos.

---

## 📝 Resumindo a aula

| Conceito | O que você precisa lembrar |
|---|---|
| **MySQL Server** | O banco de dados em si — armazena e gerencia os dados |
| **MySQL Workbench** | Ferramenta visual gratuita para criar diagramas ER e gerenciar o MySQL |
| **ER/Studio** | Ferramenta profissional (paga) com recursos avançados |
| **Levantamento de requisitos** | Conversa com o cliente para entender o que o sistema precisa antes de modelar |
| **Fluxo de trabalho** | Requisitos → Entidades → Diagrama ER → Banco de dados |

---

## 🔢 Quiz rápido — Teste seus conhecimentos

Responda no caderno (V para Verdadeiro, F para Falso):

1. ( ) O MySQL Workbench funciona sem precisar do MySQL Server instalado.
2. ( ) O MySQL Workbench é uma ferramenta gratuita.
3. ( ) O levantamento de requisitos é feito **depois** de criar as tabelas no banco.
4. ( ) A chave primária de uma entidade pode se repetir entre dois registros.
5. ( ) O ER/Studio suporta vários tipos de banco de dados, não só MySQL.

**Gabarito:** 1-F, 2-V, 3-F, 4-F, 5-V

---

## 📚 Quer saber mais?

- [Como instalar MySQL Server e Workbench — Hostinger (YouTube)](https://youtu.be/zpssr3u1EO8?t=41)
- [Criando um banco de dados no MySQL Workbench — Edukati (YouTube)](https://youtu.be/WChjp21gReI?t=14)
- [Ferramentas CASE e qualidade dos dados — DevMedia](https://www.devmedia.com.br/ferramentas-case-e-qualidade-dos-dados-o-paradigma-da-boa-modelagem/6905)

---

*Nas próximas aulas, vamos colocar a mão na massa e criar nosso primeiro banco de dados de verdade usando o MySQL Workbench!* 💻🚀

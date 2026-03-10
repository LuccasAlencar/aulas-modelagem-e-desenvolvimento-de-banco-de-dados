---

### Arquivo: `aula9.md`
**Título (CSV):** Aula 1: Introdução à normalização

```markdown
---
title: "Aula 9 — Introdução à Normalização: O Fim da Bagunça"
layout: default
---

## 🎯 Objetivo da Aula
Entender por que bancos de dados profissionais não parecem planilhas de Excel e aprender a identificar os riscos de um banco mal projetado.

---

## 1. O que é Normalização?
É um processo matemático e lógico para organizar as colunas e tabelas de um banco de dados para minimizar a **redundância** (repetição) e a **dependência incoerente**.

## 2. O Inimigo: As Anomalias de Dados
Se não normalizamos, sofremos três grandes problemas:

1. **Anomalia de Inserção:** Você não consegue cadastrar um novo curso se não tiver alunos matriculados ainda (porque a tabela exige os dois juntos).
2. **Anomalia de Exclusão:** Você deleta um aluno e, por acidente, apaga a única cópia da informação de que o curso de "SQL Avançado" custa R$ 500.
3. **Anomalia de Atualização:** O cliente muda de endereço. Você altera em 3 linhas, mas esquece a 4ª. Agora o banco tem duas verdades diferentes.

## 3. O Conceito de Dependência Funcional
A normalização baseia-se em entender quem "manda" em quem.
- Se eu sei o seu **CPF**, eu obrigatoriamente sei o seu **Nome**.
- Dizemos que `Nome` é funcionalmente dependente de `CPF`.
- Símbolo: `CPF -> Nome`.

## 4. O Fluxo de Trabalho
A normalização ocorre em etapas chamadas **Formas Normais (FN)**. Cada uma resolve um problema específico:
- **1FN:** Resolve problemas de estrutura e repetição simples.
- **2FN:** Resolve problemas de dados que dependem apenas de "metade" da chave.
- **3FN:** Resolve problemas de dados que dependem de outros dados que não são chaves.

## 🕵️ Atividade: Detetive de Redundância (15 min)
Olhe para esta tabela de um sistema de Biblioteca:
`Cod_Livro | Titulo | Autor | Nacionalidade_Autor | Data_Emprestimo | Nome_Leitor`

**Responda:**
1. Se o mesmo autor escrever 10 livros, o que acontece com a "Nacionalidade"?
2. Se um livro nunca for emprestado, onde guardamos o título dele?

---
**O que fica desta aula:**
- Normalizar = Eficiência + Integridade.
- Um banco normalizado ocupa menos espaço e evita erros catastróficos de atualização.
# 🗂️ Aula 13: Estrutura de Dados (Matrizes e Registros)

Vetores organizam dados em **linha**. Mas o mundo real muitas vezes é uma **tabela** (linhas e colunas) ou uma **ficha** com vários campos diferentes. Nesta aula ampliamos nossas ferramentas de organização com **matrizes** e **registros**.

---

## 🔲 Matrizes (vetores de duas dimensões)

Uma matriz é como uma **tabela**: tem linhas e colunas. Pense num tabuleiro de xadrez, numa planilha ou nas notas de vários alunos em várias provas.

```
        col 1   col 2   col 3
lin 1 [  8.0  |  7.5  |  9.0 ]
lin 2 [  6.0  |  5.5  |  7.0 ]
```

### Declaração e acesso

```
Var
    notas: vetor[1..2, 1..3] de real   // 2 linhas, 3 colunas
Inicio
    notas[1, 1] <- 8.0   // linha 1, coluna 1
    notas[2, 3] <- 7.0   // linha 2, coluna 3
```

### Percorrendo com laços aninhados

```
Algoritmo "Matriz_Notas"
Var
    notas: vetor[1..2, 1..3] de real
    i, j: inteiro
Inicio
    Para i de 1 ate 2 faca
        Para j de 1 ate 3 faca
            Escreva("Nota do aluno ", i, ", prova ", j, ": ")
            Leia(notas[i, j])
        FimPara
    FimPara

    // Exibindo
    Para i de 1 ate 2 faca
        Para j de 1 ate 3 faca
            Escreva(notas[i, j], " ")
        FimPara
        Escreval("")
    FimPara
FimAlgoritmo
```

!!! info "Regra do laço aninhado"
    O laço **externo** controla as linhas; o **interno** controla as colunas. Para cada linha, percorremos todas as colunas.

---

## 🗃️ Registros (agrupando campos diferentes)

Um vetor guarda vários dados **do mesmo tipo**. Um **registro** guarda vários campos de **tipos diferentes** que descrevem uma mesma entidade.

```
Var
    produto: registro
        nome: caractere
        preco: real
        quantidade: inteiro
    FimRegistro
Inicio
    produto.nome <- "Teclado"
    produto.preco <- 120.00
    produto.quantidade <- 15

    Escreval("Produto: ", produto.nome)
    Escreval("Total em estoque: R$ ", produto.preco * produto.quantidade)
```

Cada campo é acessado com um **ponto**: `produto.nome`, `produto.preco`.

---

## 🧩 Vetor de Registros (o melhor dos dois mundos)

E se você tem **100 produtos**? Um vetor de registros!

```
Var
    estoque: vetor[1..100] de registro
        nome: caractere
        preco: real
    FimRegistro
Inicio
    estoque[1].nome <- "Mouse"
    estoque[1].preco <- 80.00
    estoque[2].nome <- "Monitor"
    estoque[2].preco <- 900.00
```

Essa combinação é a base de praticamente todo sistema real (um cadastro de clientes, um catálogo, uma agenda...).

Para **percorrer** um vetor de registros, use um laço e acesse os campos com o ponto — é assim que se monta a **Agenda de Contatos** (Exercício 4):

```
Para i de 1 ate 5 faca
    Escreva("Nome do contato ", i, ": ")
    Leia(agenda[i].nome)
    Escreva("Telefone: ")
    Leia(agenda[i].telefone)
FimPara

Escreval("--- Lista de Contatos ---")
Para i de 1 ate 5 faca
    Escreval(agenda[i].nome, " - ", agenda[i].telefone)
FimPara
```

---

## ➕ Somando e Buscando numa Matriz

Percorrer uma matriz para **somar tudo** (Exercício 1) segue o mesmo esqueleto do laço aninhado, só que acumulando:

```
soma <- 0
Para i de 1 ate 3 faca
    Para j de 1 ate 3 faca
        soma <- soma + matriz[i, j]
    FimPara
FimPara
Escreval("Soma total: ", soma)
```

Para achar o **maior valor e sua posição** (Exercício 5), guardamos também os índices `i` e `j` onde ele foi encontrado:

```
maior <- matriz[1, 1]
linhaMaior <- 1
colMaior <- 1
Para i de 1 ate 2 faca
    Para j de 1 ate 2 faca
        Se (matriz[i, j] > maior) entao
            maior <- matriz[i, j]
            linhaMaior <- i
            colMaior <- j
        FimSe
    FimPara
FimPara
Escreval("Maior: ", maior, " na posição [", linhaMaior, ",", colMaior, "]")
```

---

## ↘️ A Diagonal Principal

A **diagonal principal** de uma matriz quadrada é formada pelas células em que **a linha é igual à coluna** (`[1,1]`, `[2,2]`, `[3,3]`...). Reconhecer isso resolve o Exercício 2 sem precisar de dois laços:

```
Para i de 1 ate 3 faca
    Escreva(matriz[i, i], " ")   // linha = coluna = i
FimPara
```

!!! info "Por que só um laço?"
    Como na diagonal `linha = coluna`, um único índice `i` já identifica a célula `matriz[i, i]`. O laço aninhado só é necessário quando precisamos visitar **todas** as células.

---

## 📝 Desafios

??? abstract "Exercício 1: Soma de Matriz"
    Leia uma matriz 3x3 de inteiros e exiba a soma de todos os seus elementos.

??? abstract "Exercício 2: Diagonal Principal"
    Leia uma matriz 3x3 e exiba apenas os elementos da diagonal principal (onde linha = coluna).

??? abstract "Exercício 3: Ficha de Aluno (Registro)"
    Crie um registro `aluno` com nome, matrícula e média. Leia os dados e exiba um "boletim" formatado.

??? abstract "Exercício 4: Agenda de Contatos"
    Use um vetor de 5 registros (nome e telefone). Preencha e depois liste todos os contatos.

??? abstract "Exercício 5: Maior da Matriz"
    Leia uma matriz 2x2 e informe qual é o maior valor e em qual posição (linha, coluna) ele está.

---

## 📚 Referências

- **ASCENCIO, A. F. G.; CAMPOS, E. A. V. de.** *Fundamentos da Programação de Computadores.* 3. ed. Pearson, 2012. — Matrizes e registros.
- **TENENBAUM, A. M.; LANGSAM, Y.; AUGENSTEIN, M. J.** *Estruturas de Dados Usando C.* Pearson, 1995.
- **CORMEN, T. H. et al.** *Algoritmos: Teoria e Prática.* 3. ed. Elsevier, 2012. — Introdução às estruturas de dados.
- Wikipédia (PT): [Matriz (programação)](https://pt.wikipedia.org/wiki/Array#Vetores_multidimensionais) · [Estrutura de dados](https://pt.wikipedia.org/wiki/Estrutura_de_dados).

---

!!! tip "Próxima Parada"
    Chegamos ao paradigma que domina o mercado: a **Programação Orientada a Objetos (POO)**. Resolva a **[Lista 13](../listas/13-lista.md)**!

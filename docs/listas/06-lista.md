# 🚀 Lista 06 — Tipos de Dados Primitivos e Compostos

Escolher o tipo certo evita bugs sutis (como o zero à esquerda de um CEP que some). Nesta lista você vai praticar tipos primitivos, registros e vetores simples.

---

## 🛠️ O Algoritmo da Entrega

1. Resolva os exercícios no **Portugol Studio**.
2. Crie o repositório público `una-algprog-lista06`.
3. No `README.md`, explique a diferença entre um **vetor** e um **registro**.

---

## 📝 Lista de Exercícios

??? abstract "Exercício 1: Classificando Dados"
    Para cada dado, informe o tipo mais adequado (inteiro, real, caractere ou logico): número de filhos, salário, e-mail, "possui CNH?", temperatura, CEP. Justifique cada escolha no `README.md`.

??? abstract "Exercício 2: Ficha do Cliente (Registro)"
    Crie um registro `cliente` com: nome (caractere), idade (inteiro), limite de crédito (real) e ativo (logico). Preencha e exiba todos os campos.

??? abstract "Exercício 3: Soma de Vetor"
    Crie um vetor de 5 posições do tipo real, leia 5 valores e exiba a soma deles.

??? abstract "Exercício 4: Cadastro de Produto"
    Crie um registro `produto` (nome, preco, quantidade). Leia os dados e calcule o valor total em estoque (`preco * quantidade`).

??? abstract "Exercício 5: O Perigo da Conversão"
    Explique, com um exemplo em pseudocódigo, o que aconteceria se você guardasse um número de telefone como `inteiro` em vez de `caractere`.

---

## 📂 Estrutura Sugerida

```text
una-algprog-lista06/
├── README.md
└── algoritmos/
    ├── 02_ficha_cliente.por
    ├── 03_soma_vetor.por
    └── 04_cadastro_produto.por
```

---

## ⚠️ Checklist de Qualidade

!!! check "Critérios de Aceite"
    - [ ] Cada dado do Exercício 1 tem tipo justificado?
    - [ ] Os campos do registro usam tipos adequados?
    - [ ] O vetor respeita o tamanho declarado?
    - [ ] O `README.md` explica vetor vs. registro?

# 🚀 Lista 08 — Estruturas de Controle: SWITCH-CASE

Quando há **muitas opções fixas**, o `Escolha/Caso` deixa o código mais limpo que um monte de `Se` encadeado. Vamos praticar menus e seleções.

---

## 🛠️ O Algoritmo da Entrega

1. Resolva os exercícios no **Portugol Studio**.
2. Crie o repositório público `una-algprog-lista08`.
3. No `README.md`, explique quando usar `Escolha` e quando usar `Se`.

---

## 📝 Lista de Exercícios

??? abstract "Exercício 1: Calculadora Simples"
    Leia dois números e um operador (1=soma, 2=subtração, 3=multiplicação, 4=divisão). Use `Escolha` para executar a operação. Trate a divisão por zero.

??? abstract "Exercício 2: Menu de Conversão"
    Menu: 1) Real→Dólar, 2) Real→Euro, 3) Real→Libra. Leia o valor e a opção e faça a conversão (use cotações fixas).

??? abstract "Exercício 3: Estações do Ano"
    Leia um número de 1 a 4 e exiba a estação (1=Verão, 2=Outono, 3=Inverno, 4=Primavera). Trate valores inválidos com `OutroCaso`.

??? abstract "Exercício 4: Dia da Semana"
    Leia um número de 1 a 7 e exiba o nome do dia correspondente.

??? abstract "Exercício 5: Conceito Escolar"
    Leia uma letra (A, B, C, D, F) e exiba a mensagem do conceito (ex: A = "Excelente").

---

## 📂 Estrutura Sugerida

```text
una-algprog-lista08/
├── README.md
└── algoritmos/
    ├── 01_calculadora.por
    ├── 02_menu_conversao.por
    ├── 03_estacoes.por
    ├── 04_dia_semana.por
    └── 05_conceito_escolar.por
```

---

## ⚠️ Checklist de Qualidade

!!! check "Critérios de Aceite"
    - [ ] Todos os `Escolha` tratam o `OutroCaso` (entrada inválida)?
    - [ ] Você escolheu `Escolha` (e não `Se`) porque compara uma variável com valores fixos?
    - [ ] A calculadora trata a divisão por zero?
    - [ ] O código está organizado e indentado?

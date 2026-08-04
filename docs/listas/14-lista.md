# 🚀 Lista 14 — Introdução à POO (Classes e Objetos)

Hora de modelar o mundo real em código. Nesta lista você vai criar classes, instanciar objetos e aplicar o encapsulamento.

!!! note "Sobre o ambiente"
    O Portugol tem suporte limitado a POO. Escreva as classes em **pseudocódigo** (como nos exemplos da aula). Quem quiser pode implementar em uma linguagem real (Java, Python ou C#) como desafio extra.

---

## 🛠️ O Algoritmo da Entrega

1. Escreva as soluções (pseudocódigo ou linguagem real).
2. Crie o repositório público `una-algprog-lista14`.
3. No `README.md`, explique com suas palavras: o que é uma **classe**, o que é um **objeto** e o que é **encapsulamento**.

---

## 📝 Lista de Exercícios

??? abstract "Exercício 1: Classe Pessoa"
    Modele uma classe `Pessoa` com atributos `nome` e `idade`, e um método `apresentar()` que exibe "Olá, meu nome é ... e tenho ... anos".

??? abstract "Exercício 2: Classe Retangulo"
    Crie a classe `Retangulo` com `base` e `altura`, e os métodos `calcularArea()` e `calcularPerimetro()`.

??? abstract "Exercício 3: Classe Lampada"
    Modele uma `Lampada` com o atributo `ligada` (logico) e os métodos `acender()`, `apagar()` e `estaLigada()`.

??? abstract "Exercício 4: Conta Bancária (Encapsulamento)"
    Crie a classe `ContaBancaria` com `saldo` (protegido) e os métodos `depositar(valor)`, `sacar(valor)` (só permite se houver saldo) e `consultarSaldo()`.

---

## 📂 Estrutura Sugerida

```text
una-algprog-lista14/
├── README.md
└── classes/
    ├── 01_pessoa.txt
    ├── 02_retangulo.txt
    ├── 03_lampada.txt
    └── 04_conta_bancaria.txt
```

---

## ⚠️ Checklist de Qualidade

!!! check "Critérios de Aceite"
    - [ ] Cada classe separa claramente **atributos** e **métodos**?
    - [ ] No Exercício 4, o saque valida o saldo antes de subtrair (encapsulamento)?
    - [ ] Você criou pelo menos um objeto (instância) de cada classe para testar?
    - [ ] O `README.md` define classe, objeto e encapsulamento?

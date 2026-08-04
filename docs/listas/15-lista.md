# 🚀 Lista 15 — POO na Prática (Herança e Polimorfismo)

A lista final! Aqui você junta tudo: classes, herança e polimorfismo em um pequeno projeto. É o seu projeto de encerramento da disciplina.

!!! note "Sobre o ambiente"
    Escreva em **pseudocódigo** (como na aula) ou implemente em uma linguagem real (Java, Python ou C#) como desafio extra — altamente recomendado para o portfólio.

---

## 🛠️ O Algoritmo da Entrega

1. Desenvolva as soluções.
2. Crie o repositório público `una-algprog-lista15`.
3. No `README.md`, explique **herança** e **polimorfismo** com exemplos próprios, e resuma os **4 pilares da POO**.

---

## 📝 Lista de Exercícios

??? abstract "Exercício 1: Formas Geométricas"
    Crie uma classe `Forma` com o método `calcularArea()`. Crie as subclasses `Circulo` e `Quadrado`, cada uma com sua fórmula de área (polimorfismo).

??? abstract "Exercício 2: Veículos"
    Crie a classe `Veiculo` (marca, velocidade) e as subclasses `Carro` e `Moto`. Sobrescreva um método `descrever()` em cada uma.

??? abstract "Exercício 3: Funcionários"
    Crie `Funcionario` com `calcularSalario()`. Crie `Gerente` (herda de `Funcionario`) que adiciona 20% de bônus ao salário (polimorfismo).

??? abstract "Exercício 4: Projeto — Sistema de Biblioteca"
    Modele `Livro` (título, autor, disponível) e `Usuario` (nome). Crie métodos `emprestar()` e `devolver()` que alteram a disponibilidade do livro aplicando as regras de negócio (encapsulamento).

---

## 📂 Estrutura Sugerida

```text
una-algprog-lista15/
├── README.md
└── classes/
    ├── 01_formas.txt
    ├── 02_veiculos.txt
    ├── 03_funcionarios.txt
    └── 04_biblioteca.txt
```

---

## ⚠️ Checklist de Qualidade

!!! check "Critérios de Aceite"
    - [ ] As subclasses usam herança da superclasse corretamente?
    - [ ] O mesmo método se comporta de forma diferente em cada subclasse (polimorfismo)?
    - [ ] O `README.md` resume os 4 pilares da POO?
    - [ ] O projeto da biblioteca aplica regras de negócio nos métodos?

---

!!! tip "Parabéns!"
    Você concluiu a jornada de Algoritmos e Programação. O pensamento lógico que você construiu aqui serve para **qualquer linguagem**. Continue praticando e publicando no GitHub. Bons códigos! 🚀

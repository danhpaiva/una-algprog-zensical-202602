# 🚀 Lista 05 — Boas Práticas na Construção de Algoritmos

Código que funciona é o mínimo. Nesta lista o foco é **qualidade**: nomes claros, indentação, teste de mesa e caça a bugs.

---

## 🛠️ O Algoritmo da Entrega

1. Resolva os exercícios no **Portugol Studio**.
2. Crie o repositório público `una-algprog-lista05`.
3. No `README.md`, liste 3 boas práticas que você aprendeu e por que elas importam.

---

## 📝 Lista de Exercícios

??? abstract "Exercício 1: Refatoração"
    Reescreva o algoritmo abaixo com nomes de variáveis claros e indentação correta:
    ```
    Var
    a,b,c:real
    Inicio
    Leia(a)
    Leia(b)
    c<-(a+b)/2
    Escreva(c)
    ```

??? abstract "Exercício 2: Teste de Mesa"
    Monte a tabela de teste de mesa do algoritmo abaixo para `n = 5` e informe a saída:
    ```
    dobro <- n * 2
    triplo <- n * 3
    resultado <- dobro + triplo
    Escreva(resultado)
    ```

??? abstract "Exercício 3: Caça ao Bug"
    O algoritmo deveria calcular a média de duas notas, mas está errado. Encontre e corrija:
    ```
    media <- nota1 + nota2 / 2
    ```

??? abstract "Exercício 4: Constantes"
    Reescreva um algoritmo que calcula a área do círculo (`area <- 3.14159 * raio * raio`) deixando claro, por comentário ou nome de variável, o significado do valor de PI.

??? abstract "Exercício 5: Documentação"
    Pegue um algoritmo da Lista 03 ou 04 e adicione comentários que expliquem o **porquê** das decisões (não o óbvio).

---

## 📂 Estrutura Sugerida

```text
una-algprog-lista05/
├── README.md
└── algoritmos/
    ├── 01_refatoracao.por
    ├── 02_teste_de_mesa.md
    ├── 03_caca_ao_bug.por
    ├── 04_area_circulo.por
    └── 05_documentacao.por
```

---

## ⚠️ Checklist de Qualidade

!!! check "Critérios de Aceite"
    - [ ] Todos os códigos estão indentados corretamente?
    - [ ] Os nomes das variáveis contam o que elas guardam?
    - [ ] O teste de mesa do Exercício 2 está em formato de tabela?
    - [ ] Os comentários explicam o "porquê", não o óbvio?

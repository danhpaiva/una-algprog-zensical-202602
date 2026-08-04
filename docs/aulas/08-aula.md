# 🔀 Aula 08: Estruturas de Controle — SWITCH / CASE

Imagine um menu de restaurante com 10 opções. Escrever 10 `Se ... Senao Se` funciona, mas fica feio e difícil de ler. Para escolher entre **muitos valores fixos**, existe a estrutura de seleção múltipla: o `Escolha ... Caso` (o famoso *switch-case*).

---

## 🎛️ A Estrutura `Escolha ... Caso`

Ela testa **uma única variável** contra vários valores possíveis.

```
Escolha (variavel)
    Caso valor1
        // ações
    Caso valor2
        // ações
    OutroCaso
        // se não bateu com nenhum
FimEscolha
```

---

## 🍔 Exemplo: Menu de Lanchonete

```
Algoritmo "Menu_Lanchonete"
Var
    opcao: inteiro
Inicio
    Escreval("1 - Hambúrguer")
    Escreval("2 - Pizza")
    Escreval("3 - Refrigerante")
    Escreva("Escolha: ")
    Leia(opcao)

    Escolha (opcao)
        Caso 1
            Escreva("Você pediu Hambúrguer - R$ 20,00")
        Caso 2
            Escreva("Você pediu Pizza - R$ 35,00")
        Caso 3
            Escreva("Você pediu Refrigerante - R$ 8,00")
        OutroCaso
            Escreva("Opção inválida!")
    FimEscolha
FimAlgoritmo
```

---

## ⚔️ SWITCH-CASE vs. IF-ELSE: quando usar cada um?

| Use `Escolha` (switch)                      | Use `Se` (if)                                  |
| :------------------------------------------ | :--------------------------------------------- |
| Comparar **uma variável** com valores fixos | Testar **faixas** ou condições complexas       |
| Menus, dias da semana, códigos, opções      | `nota >= 7`, `idade entre 18 e 65`             |
| Valores exatos e discretos                  | Comparações com `>`, `<`, `e`, `ou`            |

!!! info "Regra prática"
    Se você está comparando **a mesma variável** com vários valores exatos → `Escolha`. Se está testando **intervalos** ou combinando condições → `Se`.

---

## 🗓️ Exemplo: Dia da Semana

```
Algoritmo "Dia_Semana"
Var
    dia: inteiro
Inicio
    Escreva("Digite um número de 1 a 7: ")
    Leia(dia)

    Escolha (dia)
        Caso 1
            Escreva("Domingo")
        Caso 2
            Escreva("Segunda-feira")
        Caso 3
            Escreva("Terça-feira")
        Caso 4
            Escreva("Quarta-feira")
        Caso 5
            Escreva("Quinta-feira")
        Caso 6
            Escreva("Sexta-feira")
        Caso 7
            Escreva("Sábado")
        OutroCaso
            Escreva("Dia inválido")
    FimEscolha
FimAlgoritmo
```

!!! tip "Sempre trate o `OutroCaso`"
    Ele é a sua rede de segurança para entradas inesperadas — equivale ao `Senao` final do `Se`.

---

## 🔤 `Escolha` com Letras e Vários Valores por Caso

O `Escolha` não serve só para números: ele funciona muito bem com **caracteres**, o que resolve o **Conceito por Letra** (Exercício 4):

```
Escolha (conceito)
    Caso "A"
        Escreva("Excelente")
    Caso "B"
        Escreva("Bom")
    Caso "C"
        Escreva("Regular")
    Caso "D", "F"          // dois valores no mesmo caso
        Escreva("Insuficiente")
    OutroCaso
        Escreva("Conceito inválido")
FimEscolha
```

Repare no `Caso "D", "F"`: quando **vários valores levam à mesma ação**, você pode agrupá-los, evitando repetição.

---

## 🧮 Combinando `Escolha` com Cálculos

Na **Calculadora Simples** (Exercício 1) e no **Menu de Conversão** (Exercício 2), cada caso executa uma operação diferente sobre os mesmos dados lidos:

```
Escolha (operador)
    Caso 1
        resultado <- a + b
    Caso 2
        resultado <- a - b
    Caso 3
        resultado <- a * b
    Caso 4
        Se (b <> 0) entao
            resultado <- a / b
        Senao
            Escreva("Erro: divisão por zero!")
        FimSe
    OutroCaso
        Escreva("Operação inválida")
FimEscolha
```

!!! warning "Divisão por zero"
    Toda vez que houver uma divisão, verifique antes se o divisor é diferente de zero. Dividir por zero é um erro que derruba o programa em qualquer linguagem.

---

## 📝 Desafios

??? abstract "Exercício 1: Calculadora Simples"
    Leia dois números e um operador (1=soma, 2=subtração, 3=multiplicação, 4=divisão). Use `Escolha` para executar a operação escolhida.

??? abstract "Exercício 2: Menu de Conversão"
    Crie um menu: 1) Real para Dólar, 2) Real para Euro, 3) Real para Libra. Leia o valor e a opção, e faça a conversão correspondente (use cotações fixas).

??? abstract "Exercício 3: Estações do Ano"
    Leia um número de 1 a 4 e exiba a estação do ano correspondente (1=Verão, 2=Outono, 3=Inverno, 4=Primavera). Trate valores inválidos.

??? abstract "Exercício 4: Conceito por Letra"
    Leia uma letra (A, B, C, D, F) e exiba a mensagem correspondente ao conceito escolar.

---

## 📚 Referências

- **FORBELLONE, A. L. V.; EBERSPÄCHER, H. F.** *Lógica de Programação.* 3. ed. Pearson, 2005. — Estrutura de seleção múltipla.
- **ASCENCIO, A. F. G.; CAMPOS, E. A. V. de.** *Fundamentos da Programação de Computadores.* 3. ed. Pearson, 2012.
- **DEITEL, P.; DEITEL, H.** *Java: Como Programar.* 10. ed. Pearson, 2016. — A instrução `switch`.
- Wikipédia (PT): [Switch (programação)](https://pt.wikipedia.org/wiki/Switch_(programa%C3%A7%C3%A3o)).

---

!!! tip "Próxima Parada"
    E se precisarmos **repetir** uma ação muitas vezes? Entram em cena as **estruturas de repetição**, começando por **WHILE e DO-WHILE**. Resolva a **[Lista 08](../listas/08-lista.md)**!

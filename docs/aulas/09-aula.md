# 🔁 Aula 09: Estruturas de Repetição — WHILE e DO-WHILE

Computadores são incansáveis: eles repetem uma tarefa milhões de vezes sem reclamar. As estruturas de repetição (ou *loops*) são o que permitem, por exemplo, processar uma planilha com 10 mil linhas. Hoje veremos os laços **condicionais**: `Enquanto` e `Repita`.

---

## ♻️ O Laço `Enquanto` (while)

Repete um bloco **enquanto** uma condição for verdadeira. Ele testa **antes** de executar — então pode rodar **zero** vezes.

```
Enquanto (condicao) faca
    // bloco repetido
FimEnquanto
```

Exemplo — contando de 1 a 5:

```
Algoritmo "Contador"
Var
    i: inteiro
Inicio
    i <- 1
    Enquanto (i <= 5) faca
        Escreval("Número: ", i)
        i <- i + 1   // MUITO importante: atualiza a condição!
    FimEnquanto
FimAlgoritmo
```

!!! danger "O terror do Loop Infinito"
    Se você esquecer o `i <- i + 1`, a condição `i <= 5` nunca fica falsa e o programa trava para sempre. **Todo laço precisa caminhar em direção ao seu fim.**

---

## 🔂 O Laço `Repita` (do-while)

Repete o bloco e **só depois** testa a condição. Por isso ele executa **pelo menos uma vez**, mesmo que a condição já comece falsa. Perfeito para menus e validação de entrada.

```
Repita
    // bloco repetido
Ate (condicao)
```

Exemplo — validando entrada:

```
Algoritmo "Valida_Idade"
Var
    idade: inteiro
Inicio
    Repita
        Escreva("Digite uma idade válida (0 a 120): ")
        Leia(idade)
    Ate (idade >= 0) e (idade <= 120)

    Escreva("Idade registrada: ", idade)
FimAlgoritmo
```

---

## ⚖️ Enquanto vs. Repita

| `Enquanto` (while)              | `Repita` (do-while)                     |
| :------------------------------ | :-------------------------------------- |
| Testa **antes** de executar     | Testa **depois** de executar            |
| Pode rodar **0 vezes**          | Roda **no mínimo 1 vez**                |
| "Enquanto houver fila, atenda"  | "Peça a senha, repita até acertar"      |

---

## 🧮 Padrões Clássicos com Laços

=== "Acumulador (soma)"
    ```
    soma <- 0
    i <- 1
    Enquanto (i <= 5) faca
        Leia(valor)
        soma <- soma + valor
        i <- i + 1
    FimEnquanto
    Escreva("Total: ", soma)
    ```

=== "Contador com condição"
    ```
    pares <- 0
    i <- 1
    Enquanto (i <= 20) faca
        Se (i % 2 = 0) entao
            pares <- pares + 1
        FimSe
        i <- i + 1
    FimEnquanto
    Escreva("Quantidade de pares: ", pares)
    ```

=== "Sentinela (parar por valor)"
    ```
    Leia(numero)
    Enquanto (numero <> 0) faca
        Escreva("Você digitou: ", numero)
        Leia(numero)     // 0 encerra o laço
    FimEnquanto
    ```

---

## 🔧 A Anatomia de Todo Laço

Independentemente da estrutura, um laço que funciona sempre tem **três ingredientes**. Esquecer qualquer um deles é a fonte da maioria dos bugs de repetição:

1. **Inicialização** — preparar a variável de controle *antes* do laço (`i <- 1`, `soma <- 0`).
2. **Condição de parada** — a pergunta que decide se continua (`i <= 10`, `numero <> 0`).
3. **Atualização** — o passo que aproxima o laço do fim, *dentro* do bloco (`i <- i + 1`, ou ler um novo valor).

!!! example "Localize os três na tabuada (Exercício 1)"
    ```
    i <- 1                                  // 1. inicialização
    Enquanto (i <= 10) faca                 // 2. condição
        Escreval(numero, " x ", i, " = ", numero * i)
        i <- i + 1                          // 3. atualização
    FimEnquanto
    ```

---

## ✅ Validação de Entrada com `Repita`

Quando você precisa **insistir** até o usuário digitar algo válido, o `Repita` é a escolha natural: ele pergunta pelo menos uma vez e só sai quando o dado for aceitável. É o coração dos exercícios de **Menu** (Ex. 3) e **Validação de Nota** (Ex. 4):

```
Repita
    Escreva("Digite uma nota de 0 a 10: ")
    Leia(nota)
    Se (nota < 0) ou (nota > 10) entao
        Escreval("Valor inválido! Tente de novo.")
    FimSe
Ate (nota >= 0) e (nota <= 10)
```

!!! tip "Menu que repete até 'Sair'"
    O mesmo padrão monta um menu: repita a exibição das opções e a leitura da escolha **até** o usuário selecionar a opção de sair.

---

## 📝 Desafios

??? abstract "Exercício 1: Tabuada"
    Leia um número e exiba sua tabuada de 1 a 10 usando `Enquanto`.

??? abstract "Exercício 2: Soma até parar"
    Leia números do usuário e vá somando. Pare quando ele digitar `0`. No final, exiba a soma total (padrão sentinela).

??? abstract "Exercício 3: Menu com Repita"
    Crie um menu que fica repetindo até o usuário escolher a opção "Sair". Use `Repita ... Ate`.

??? abstract "Exercício 4: Validação de Nota"
    Peça uma nota de 0 a 10. Enquanto o valor for inválido, peça novamente.

---

## 📚 Referências

- **FORBELLONE, A. L. V.; EBERSPÄCHER, H. F.** *Lógica de Programação.* 3. ed. Pearson, 2005. — Cap. 5 (Estruturas de repetição).
- **ASCENCIO, A. F. G.; CAMPOS, E. A. V. de.** *Fundamentos da Programação de Computadores.* 3. ed. Pearson, 2012. — Laços condicionais.
- **DEITEL, P.; DEITEL, H.** *Java: Como Programar.* 10. ed. Pearson, 2016. — `while` e `do...while`.
- Wikipédia (PT): [Laço (programação)](https://pt.wikipedia.org/wiki/La%C3%A7o_(programa%C3%A7%C3%A3o)).

---

!!! tip "Próxima Parada"
    Quando sabemos **exatamente quantas vezes** repetir, existe um laço mais elegante: o **FOR (Para)**. Resolva a **[Lista 09](../listas/09-lista.md)**!

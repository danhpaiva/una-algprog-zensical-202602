# 🔢 Aula 10: Estruturas de Repetição — FOR e FOREACH

O `Enquanto` é ótimo, mas exige três coisas escritas em lugares diferentes: iniciar o contador, testar e incrementar. Quando sabemos **quantas vezes** vamos repetir, o laço `Para` (for) junta tudo isso em uma linha só — mais limpo e menos sujeito a erros.

---

## 🎯 O Laço `Para` (for)

```
Para variavel de inicio ate fim [passo valor] faca
    // bloco repetido
FimPara
```

Exemplo — contar de 1 a 5:

```
Algoritmo "Contagem_For"
Var
    i: inteiro
Inicio
    Para i de 1 ate 5 faca
        Escreval("Número: ", i)
    FimPara
FimAlgoritmo
```

Repare: o contador `i` é **iniciado, testado e incrementado automaticamente**. Você não precisa escrever `i <- i + 1`.

---

## 👣 O `passo` (incremento personalizado)

Por padrão o `Para` anda de 1 em 1, mas você pode mudar isso.

=== "De 2 em 2"
    ```
    Para i de 0 ate 10 passo 2 faca
        Escreval(i)   // 0, 2, 4, 6, 8, 10
    FimPara
    ```

=== "Contagem regressiva"
    ```
    Para i de 5 ate 1 passo -1 faca
        Escreval(i)   // 5, 4, 3, 2, 1
    FimPara
    ```

---

## 🔄 FOR vs. WHILE: quando usar?

| Use `Para` (for)                          | Use `Enquanto` (while)                         |
| :---------------------------------------- | :--------------------------------------------- |
| Você **sabe** o número de repetições      | O número de repetições **depende** de algo     |
| Percorrer um vetor de tamanho conhecido   | Ler dados até o usuário digitar "sair"         |
| "Repita 10 vezes"                         | "Repita enquanto houver saldo"                 |

!!! info "Os dois resolvem tudo"
    Todo `Para` pode ser reescrito como `Enquanto` e vice-versa. Escolha o que deixa o código **mais claro** para o problema.

---

## 📚 O `Para Cada` (foreach)

Quando percorremos uma **coleção** (como um vetor), muitas linguagens oferecem o *foreach*: ele passa por **cada elemento** sem você precisar controlar o índice.

Ideia (pseudocódigo):

```
Para cada item Em lista faca
    Escreva(item)
FimPara
```

No Portugol trabalhamos o percurso com índice; a ideia do *foreach* ficará mais concreta com vetores (próxima aula) e nas linguagens de mercado (Java, Python, C#).

```
// Percorrendo um vetor com Para (equivalente prático ao foreach)
Para i de 1 ate 5 faca
    Escreva(numeros[i])
FimPara
```

---

## 🧮 Padrões Clássicos

=== "Somatório"
    ```
    soma <- 0
    Para i de 1 ate 100 faca
        soma <- soma + i
    FimPara
    Escreva("Soma de 1 a 100: ", soma)   // 5050
    ```

=== "Fatorial"
    ```
    fat <- 1
    Para i de 1 ate n faca
        fat <- fat * i
    FimPara
    Escreva(n, "! = ", fat)
    ```

=== "Laço aninhado (tabela)"
    ```
    Para i de 1 ate 3 faca
        Para j de 1 ate 3 faca
            Escreva(i * j, " ")
        FimPara
        Escreval("")
    FimPara
    ```

---

## 🔄 De `Enquanto` para `Para` (e vice-versa)

Como todo `Para` guarda os três ingredientes do laço numa linha só, converter um `Enquanto` em `Para` é quase mecânico — útil para reescrever a **tabuada** (Exercício 1):

=== "Com Enquanto"
    ```
    i <- 1
    Enquanto (i <= 10) faca
        Escreval(numero, " x ", i, " = ", numero * i)
        i <- i + 1
    FimEnquanto
    ```

=== "Com Para (mais enxuto)"
    ```
    Para i de 1 ate 10 faca
        Escreval(numero, " x ", i, " = ", numero * i)
    FimPara
    ```

A inicialização (`i <- 1`), a condição (`i <= 10`) e a atualização (`i <- i + 1`) foram todas absorvidas pelo cabeçalho do `Para`.

---

## 👣 Usando o `passo` para os Pares

Para a **Soma dos Pares** (Exercício 2), há duas estratégias equivalentes:

=== "Testando cada número"
    ```
    soma <- 0
    Para i de 1 ate 100 faca
        Se (i % 2 = 0) entao
            soma <- soma + i
        FimSe
    FimPara
    ```

=== "Andando de 2 em 2 (mais direto)"
    ```
    soma <- 0
    Para i de 2 ate 100 passo 2 faca
        soma <- soma + i
    FimPara
    ```

---

## 🔳 Entendendo Laços Aninhados

Num laço aninhado, o laço **interno completa todas as suas voltas** para *cada* volta do externo. É por isso que ele desenha "tabelas": o externo escolhe a linha, o interno preenche as colunas. Essa é a chave da **Tabuada Completa** (Exercício 5):

```
Para tabua de 1 ate 5 faca              // escolhe qual tabuada
    Escreval("--- Tabuada do ", tabua, " ---")
    Para i de 1 ate 10 faca             // percorre 1 a 10
        Escreval(tabua, " x ", i, " = ", tabua * i)
    FimPara
FimPara
```

!!! info "Conta rápida"
    Um laço externo de 5 voltas com um interno de 10 executa o bloco de dentro **5 × 10 = 50** vezes.

---

## 📝 Desafios

??? abstract "Exercício 1: Tabuada com For"
    Reescreva a tabuada da aula anterior usando `Para` em vez de `Enquanto`.

??? abstract "Exercício 2: Soma dos Pares"
    Some todos os números pares de 1 a 100 e exiba o resultado.

??? abstract "Exercício 3: Fatorial"
    Leia um número `n` e calcule seu fatorial (`n! = 1 * 2 * ... * n`).

??? abstract "Exercício 4: Contagem Regressiva"
    Faça uma contagem regressiva de 10 até 0 e no final exiba "Lançar!".

??? abstract "Exercício 5: Tabuada Completa (aninhado)"
    Use laços aninhados para exibir as tabuadas de 1 a 5, todas de uma vez.

---

## 📚 Referências

- **FORBELLONE, A. L. V.; EBERSPÄCHER, H. F.** *Lógica de Programação.* 3. ed. Pearson, 2005. — Estrutura de repetição com variável de controle.
- **ASCENCIO, A. F. G.; CAMPOS, E. A. V. de.** *Fundamentos da Programação de Computadores.* 3. ed. Pearson, 2012. — Laço `para` e laços aninhados.
- **DEITEL, P.; DEITEL, H.** *Java: Como Programar.* 10. ed. Pearson, 2016. — `for` e `for-each` (`enhanced for`).
- Wikipédia (PT): [Estrutura de repetição](https://pt.wikipedia.org/wiki/Estrutura_de_repeti%C3%A7%C3%A3o).

---

!!! tip "Próxima Parada"
    Chegou a hora de guardar **muitos dados** de forma organizada. Bem-vindo aos **Vetores**! Resolva a **[Lista 10](../listas/10-lista.md)**!

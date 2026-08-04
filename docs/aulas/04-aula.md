# ⚖️ Aula 04: Operadores Relacionais e Lógicos

Já sabemos guardar dados e fazer contas. Agora vamos ensinar o computador a **comparar** valores e **combinar** condições. É aqui que os algoritmos começam a "tomar decisões inteligentes".

---

## 🔎 Operadores Relacionais (Comparação)

Servem para comparar dois valores. O resultado é sempre **verdadeiro** ou **falso** (um valor lógico).

| Operador | Significado          | Exemplo      | Resultado   |
| :------: | :------------------- | :----------- | :---------- |
| `=`      | Igual a              | `5 = 5`      | verdadeiro  |
| `<>`     | Diferente de         | `5 <> 3`     | verdadeiro  |
| `>`      | Maior que            | `5 > 8`      | falso       |
| `<`      | Menor que            | `5 < 8`      | verdadeiro  |
| `>=`     | Maior ou igual a     | `5 >= 5`     | verdadeiro  |
| `<=`     | Menor ou igual a     | `3 <= 2`     | falso       |

!!! warning "Cuidado clássico"
    Comparar (`=`) é diferente de atribuir (`<-`). `idade <- 18` **coloca** 18 na variável. `idade = 18` **pergunta** se a idade vale 18.

---

## 🔗 Operadores Lógicos (Combinação)

Servem para juntar duas ou mais comparações em uma única condição.

=== "E (conjunção)"
    Só é verdadeiro quando **as duas** condições são verdadeiras.

    *Exemplo: "Só entra na balada se tiver 18 anos **E** estiver na lista."*

    | A          | B          | A E B       |
    | :--------- | :--------- | :---------- |
    | verdadeiro | verdadeiro | verdadeiro  |
    | verdadeiro | falso      | falso       |
    | falso      | qualquer   | falso       |

=== "OU (disjunção)"
    É verdadeiro quando **pelo menos uma** condição é verdadeira.

    *Exemplo: "Ganha desconto se for estudante **OU** idoso."*

    | A          | B          | A OU B      |
    | :--------- | :--------- | :---------- |
    | verdadeiro | qualquer   | verdadeiro  |
    | falso      | verdadeiro | verdadeiro  |
    | falso      | falso      | falso       |

=== "NAO (negação)"
    Inverte o valor lógico.

    *Exemplo: "**NÃO** chovendo → posso sair sem guarda-chuva."*

    | A          | NAO A       |
    | :--------- | :---------- |
    | verdadeiro | falso       |
    | falso      | verdadeiro  |

---

## 🛠️ Exemplo Prático: Aprovação com duas condições

Um aluno só é aprovado se a **média for maior ou igual a 7** *e* tiver **frequência maior ou igual a 75%**.

```
Algoritmo "Aprovacao_Final"
Var
    media, frequencia: real
    aprovado: logico
Inicio
    Escreva("Digite a média: ")
    Leia(media)
    Escreva("Digite a frequência (%): ")
    Leia(frequencia)

    aprovado <- (media >= 7.0) e (frequencia >= 75.0)

    Escreva("Aluno aprovado? ", aprovado)
FimAlgoritmo
```

---

## 🧮 Precedência: quem decide primeiro?

Quando misturamos tudo, o Portugol resolve nesta ordem:

1. Parênteses `()`
2. Operadores matemáticos (`*`, `/`, `+`, `-`)
3. Operadores relacionais (`>`, `<`, `=`, ...)
4. Operadores lógicos (`nao`, depois `e`, depois `ou`)

!!! info "Dica de Sênior"
    Na dúvida, **use parênteses**. `(idade >= 18) e (temIngresso)` é muito mais legível — e menos sujeito a bugs — do que confiar de cabeça na ordem de precedência.

---

## 🔢 Divisibilidade com o Resto (`%`)

Muitas condições dependem de saber se um número é **divisível** por outro. O truque é: `a` é divisível por `b` quando o **resto** da divisão é zero.

```
(numero % 2 = 0)     // verdadeiro se numero for par
(ano % 4 = 0)        // verdadeiro se o ano for múltiplo de 4
```

Combinando isso com os operadores lógicos, resolvemos a regra do **Ano Bissexto** (Exercício 1):

```
ehBissexto <- ((ano % 4 = 0) e (ano % 100 <> 0)) ou (ano % 400 = 0)
```

!!! info "Leia como uma frase"
    "É bissexto se for múltiplo de 4 **e** não de 100, **ou** se for múltiplo de 400." Os parênteses agrupam o `e` antes do `ou`, garantindo que a leitura em português bata com a lógica.

---

## 🚫 Negando Condições (e as Leis de De Morgan)

Às vezes o mais natural é descrever o que **não** deve acontecer. O `nao` inverte um valor lógico:

```
liberado <- (renda > 2000) e (nao nome_sujo)
```

Isso resolve o **Empréstimo** (Exercício 2): aprova quem tem renda alta **e** *não* está com nome sujo.

Quando você precisa negar uma condição composta, valem as **Leis de De Morgan**:

| Expressão original      | Equivale a                      |
| :---------------------- | :------------------------------ |
| `nao (A e B)`           | `(nao A) ou (nao B)`            |
| `nao (A ou B)`          | `(nao A) e (nao B)`             |

!!! tip "Faixa 'fora do normal'"
    O alarme da estufa (Exercício 3) toca quando a temperatura está **fora** da faixa ideal. Duas formas equivalentes de escrever isso:

    ```
    alarme <- (temp < 18) ou (temp > 30)          // "abaixo ou acima"
    alarme <- nao ((temp >= 18) e (temp <= 30))   // "não está dentro da faixa"
    ```

---

## 📝 Desafios

??? abstract "Exercício 1: Ano Bissexto"
    Um ano é bissexto se for divisível por 4 **e** não por 100, **ou** se for divisível por 400. Leia um ano e diga se ele é bissexto (use `%` e operadores lógicos).

??? abstract "Exercício 2: Liberação de Empréstimo"
    Um banco libera empréstimo se o cliente tem renda maior que R$ 2000 **e** não tem nome sujo. Leia a renda e um valor lógico (nome sujo?) e informe se o empréstimo foi aprovado.

??? abstract "Exercício 3: Faixa de Temperatura Ideal"
    Uma estufa deve acender o alarme se a temperatura estiver **abaixo de 18** *ou* **acima de 30** graus. Leia a temperatura e diga se o alarme deve tocar.

---

## 📚 Referências

- **FORBELLONE, A. L. V.; EBERSPÄCHER, H. F.** *Lógica de Programação.* 3. ed. Pearson, 2005. — Cap. 3 (Expressões lógicas e relacionais).
- **ASCENCIO, A. F. G.; CAMPOS, E. A. V. de.** *Fundamentos da Programação de Computadores.* 3. ed. Pearson, 2012. — Operadores relacionais e lógicos.
- **GERSTING, J. L.** *Fundamentos Matemáticos para a Ciência da Computação.* LTC. — Lógica proposicional, tabelas-verdade e Leis de De Morgan.
- Wikipédia (PT): [Álgebra booleana](https://pt.wikipedia.org/wiki/%C3%81lgebra_booliana) · [Leis de De Morgan](https://pt.wikipedia.org/wiki/Leis_de_De_Morgan).

---

!!! tip "Próxima Parada"
    Você já sabe comparar e combinar condições. Antes de partir para as grandes estruturas, vamos falar sobre como escrever um código **limpo e profissional** na aula de **Boas Práticas**. Resolva a **[Lista 04](../listas/04-lista.md)**!

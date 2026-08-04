# 📊 Aula 11: Vetores (Arrays)

Até agora, cada variável guardava **um valor**. Mas e se você precisar armazenar as notas de 40 alunos? Criar `nota1`, `nota2`, ..., `nota40` é inviável. A solução é o **vetor**: uma única variável que guarda **vários valores** organizados por posição.

---

## 🧱 O que é um Vetor?

Imagine um prédio com vários apartamentos. O prédio tem **um nome** (a variável) e cada apartamento tem **um número** (o índice). Dentro de cada apartamento mora **um valor**.

```
notas:  [ 7.0 | 8.5 | 6.0 | 9.0 | 5.5 ]
índice:    1     2     3     4     5
```

### Declaração

```
Var
    notas: vetor[1..5] de real
```

Isso cria um vetor chamado `notas` com **5 posições** (de 1 a 5), cada uma guardando um número real.

---

## ✍️ Preenchendo e Lendo um Vetor

Usamos o índice entre colchetes para acessar cada posição.

```
Algoritmo "Notas_Turma"
Var
    notas: vetor[1..5] de real
    i: inteiro
Inicio
    // Preenchendo
    Para i de 1 ate 5 faca
        Escreva("Digite a nota ", i, ": ")
        Leia(notas[i])
    FimPara

    // Lendo
    Escreval("--- Notas digitadas ---")
    Para i de 1 ate 5 faca
        Escreval("Aluno ", i, ": ", notas[i])
    FimPara
FimAlgoritmo
```

!!! danger "Estouro de índice"
    Se o vetor vai de 1 a 5, tentar acessar `notas[6]` é um erro grave (estouro de limites). Sempre respeite o tamanho declarado.

---

## 🧮 Operações Comuns com Vetores

=== "Somar todos"
    ```
    soma <- 0
    Para i de 1 ate 5 faca
        soma <- soma + notas[i]
    FimPara
    media <- soma / 5
    ```

=== "Encontrar o maior"
    ```
    maior <- notas[1]
    Para i de 2 ate 5 faca
        Se (notas[i] > maior) entao
            maior <- notas[i]
        FimSe
    FimPara
    Escreva("Maior nota: ", maior)
    ```

=== "Buscar um valor"
    ```
    Leia(procurado)
    achou <- falso
    Para i de 1 ate 5 faca
        Se (notas[i] = procurado) entao
            achou <- verdadeiro
        FimSe
    FimPara
    Escreva("Encontrado? ", achou)
    ```

---

## 🔤 Vetores de Texto

Vetores não são só de números. Você pode guardar nomes, produtos, etc.

```
Var
    alunos: vetor[1..3] de caractere
Inicio
    alunos[1] <- "Ana"
    alunos[2] <- "Bruno"
    alunos[3] <- "Carla"

    Para i de 1 ate 3 faca
        Escreval(alunos[i])
    FimPara
```

---

## 🔽 Percorrendo na Ordem Inversa

Para exibir os elementos "de trás para frente" (**Vetor Invertido**, Exercício 3), basta percorrer o índice em ordem decrescente com `passo -1`:

```
Para i de 5 ate 1 passo -1 faca
    Escreval(numeros[i])
FimPara
```

---

## 🔢 Contando com uma Condição

Muitos problemas pedem "quantos elementos satisfazem uma regra". A técnica é manter um **contador** que só cresce quando a condição é verdadeira — a base da **Contagem de Aprovados** (Exercício 4):

```
aprovados <- 0
reprovados <- 0
Para i de 1 ate 10 faca
    Se (notas[i] >= 7) entao
        aprovados <- aprovados + 1
    Senao
        reprovados <- reprovados + 1
    FimSe
FimPara
Escreval("Aprovados: ", aprovados, " | Reprovados: ", reprovados)
```

---

## 🎯 Maior e Menor ao Mesmo Tempo

Dá para achar o **maior e o menor** num único percurso (Exercício 2). Comece supondo que o primeiro elemento é os dois, e vá ajustando:

```
maior <- numeros[1]
menor <- numeros[1]
Para i de 2 ate 8 faca
    Se (numeros[i] > maior) entao
        maior <- numeros[i]
    FimSe
    Se (numeros[i] < menor) entao
        menor <- numeros[i]
    FimSe
FimPara
Escreval("Maior: ", maior, " | Menor: ", menor)
```

---

## 🔎 Busca com Posição

Na **Busca** (Exercício 5) não basta dizer "achou": queremos **em qual posição**. Guardamos o índice quando encontramos:

```
Leia(procurado)
posicao <- 0                     // 0 = "ainda não achei"
Para i de 1 ate 6 faca
    Se (numeros[i] = procurado) entao
        posicao <- i
    FimSe
FimPara

Se (posicao > 0) entao
    Escreval("Encontrado na posição ", posicao)
Senao
    Escreval("Não está no vetor")
FimSe
```

!!! info "Sentinela para 'não encontrado'"
    Usar `posicao <- 0` como valor inicial é um truque comum: como o vetor começa no índice 1, o zero nunca é uma posição válida — logo, se ele permanecer 0 no final, sabemos que o valor não foi achado.

---

## 📝 Desafios

??? abstract "Exercício 1: Média da Turma"
    Leia 10 notas em um vetor, calcule e exiba a média da turma.

??? abstract "Exercício 2: Maior e Menor"
    Leia 8 números em um vetor e exiba o maior e o menor deles.

??? abstract "Exercício 3: Vetor Invertido"
    Leia 5 números e exiba-os na ordem inversa da digitação.

??? abstract "Exercício 4: Contagem de Aprovados"
    Leia 10 notas. Exiba quantos alunos foram aprovados (nota >= 7) e quantos reprovados.

??? abstract "Exercício 5: Busca"
    Leia 6 números em um vetor. Depois pergunte um número ao usuário e informe se ele está no vetor (e em qual posição).

---

## 📚 Referências

- **ASCENCIO, A. F. G.; CAMPOS, E. A. V. de.** *Fundamentos da Programação de Computadores.* 3. ed. Pearson, 2012. — Cap. sobre vetores (variáveis compostas homogêneas).
- **FORBELLONE, A. L. V.; EBERSPÄCHER, H. F.** *Lógica de Programação.* 3. ed. Pearson, 2005. — Estruturas de dados homogêneas.
- **CORMEN, T. H. et al.** *Algoritmos: Teoria e Prática.* 3. ed. Elsevier, 2012. — Arrays e busca linear.
- Wikipédia (PT): [Vetor (informática)](https://pt.wikipedia.org/wiki/Vetor_(inform%C3%A1tica)) · [Busca linear](https://pt.wikipedia.org/wiki/Busca_linear).

---

!!! tip "Próxima Parada"
    Seu código está crescendo. Para organizá-lo em blocos reutilizáveis, vamos aprender **Funções e Procedimentos**. Resolva a **[Lista 11](../listas/11-lista.md)**!

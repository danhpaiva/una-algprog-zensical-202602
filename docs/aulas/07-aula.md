# 🚦 Aula 07: Estruturas de Controle — IF / ELSE

Chegamos ao coração da lógica: fazer o programa **escolher caminhos**. Um sistema que não decide nada é só uma calculadora. Com o `Se` (if) e o `Senao` (else), seu código ganha inteligência.

---

## 🧭 A Estrutura `Se` Simples

Executa um bloco **apenas se** a condição for verdadeira.

```
Se (condicao) entao
    // executa se verdadeiro
FimSe
```

Exemplo:

```
Se (saldo >= valor_compra) entao
    Escreva("Compra aprovada!")
FimSe
```

---

## ↔️ A Estrutura `Se ... Senao`

Escolhe entre **dois** caminhos.

```
Algoritmo "Maioridade"
Var
    idade: inteiro
Inicio
    Escreva("Digite sua idade: ")
    Leia(idade)

    Se (idade >= 18) entao
        Escreva("Maior de idade")
    Senao
        Escreva("Menor de idade")
    FimSe
FimAlgoritmo
```

```mermaid
graph TD
    A([Início]) --> B[/Ler idade/]
    B --> C{idade >= 18?}
    C -- Sim --> D[/Maior de idade/]
    C -- Não --> E[/Menor de idade/]
    D --> F([Fim])
    E --> F
```

---

## 🪜 O Encadeamento `Se ... Senao Se` (múltiplas faixas)

Quando existem **várias possibilidades**, encadeamos as condições. Só entra em uma faixa se as anteriores forem falsas.

```
Algoritmo "Boletim"
Var
    media: real
Inicio
    Leia(media)

    Se (media >= 9.0) entao
        Escreva("Conceito A - Excelente")
    Senao Se (media >= 7.0) entao
        Escreva("Conceito B - Aprovado")
    Senao Se (media >= 5.0) entao
        Escreva("Conceito C - Recuperação")
    Senao
        Escreva("Conceito D - Reprovado")
    FimSe
FimAlgoritmo
```

!!! info "A ordem importa!"
    Sempre teste do mais restritivo para o mais amplo. Se você testasse `media >= 5` primeiro, uma nota 9 cairia na faixa errada, pois 9 também é maior que 5.

---

## 🧩 Condições Compostas (revisão)

Lembre-se dos operadores lógicos da Aula 04. Você pode combinar testes:

```
Se (idade >= 18) e (possui_habilitacao) entao
    Escreva("Pode dirigir")
Senao
    Escreva("Não pode dirigir")
FimSe
```

---

## 🏆 Encontrando o Maior entre Vários Valores

Descobrir "quem é o maior" é um padrão que aparece o tempo todo (inclusive no **Maior de Três**, Exercício 2). Há duas estratégias:

=== "Comparações encadeadas"
    ```
    Se (a >= b) e (a >= c) entao
        Escreva("Maior: ", a)
    Senao Se (b >= c) entao
        Escreva("Maior: ", b)
    Senao
        Escreva("Maior: ", c)
    FimSe
    ```

=== "Variável 'campeã' (escala melhor)"
    ```
    maior <- a
    Se (b > maior) entao
        maior <- b
    FimSe
    Se (c > maior) entao
        maior <- c
    FimSe
    Escreva("Maior: ", maior)
    ```

!!! tip "Por que a segunda forma é preferível"
    A ideia de "guardar o campeão e desafiá-lo" funciona para 3 ou para 3000 valores — basta um laço. Você vai reencontrá-la ao percorrer vetores (Aula 11).

---

## 📦 Faixas de Classificação (revisão aplicada)

Problemas como o **IMC** (Exercício 3) pedem que o resultado caia em **uma entre várias faixas**. A receita é o encadeamento `Se ... Senao Se`, sempre do limite **menor para o maior** (ou vice-versa), sem sobreposição:

```
Se (imc < 18.5) entao
    Escreva("Abaixo do peso")
Senao Se (imc <= 24.9) entao
    Escreva("Peso normal")
Senao Se (imc <= 29.9) entao
    Escreva("Sobrepeso")
Senao
    Escreva("Obesidade")
FimSe
```

Como cada faixa está num `Senao`, quando uma condição é verdadeira as demais nem são testadas — o valor cai em **exatamente uma** categoria.

---

## ⚠️ Erros Clássicos

!!! danger "Cuidado"
    - Confundir `=` (comparação) com `<-` (atribuição).
    - Esquecer o `FimSe`.
    - Testar faixas na ordem errada no encadeamento.
    - Colocar a segunda condição fora de um `Senao` quando ela deveria ser exclusiva (gerando testes redundantes).

---

## 📝 Desafios

??? abstract "Exercício 1: Par ou Ímpar"
    Leia um número inteiro e informe se ele é **par** ou **ímpar** (dica: `numero % 2 = 0`).

??? abstract "Exercício 2: Maior de Três"
    Leia três números diferentes e informe qual é o **maior**.

??? abstract "Exercício 3: Classificação de IMC"
    Calcule o IMC (peso / altura²) e classifique: abaixo de 18.5 (abaixo do peso), entre 18.5 e 24.9 (normal), entre 25 e 29.9 (sobrepeso), 30 ou mais (obesidade).

??? abstract "Exercício 4: Login Simples"
    Leia usuário e senha. Se usuário for "admin" **e** senha for "1234", exiba "Acesso liberado"; senão, "Acesso negado".

---

## 📚 Referências

- **FORBELLONE, A. L. V.; EBERSPÄCHER, H. F.** *Lógica de Programação.* 3. ed. Pearson, 2005. — Cap. 4 (Estruturas de seleção).
- **ASCENCIO, A. F. G.; CAMPOS, E. A. V. de.** *Fundamentos da Programação de Computadores.* 3. ed. Pearson, 2012. — Estruturas de decisão.
- **DEITEL, P.; DEITEL, H.** *Java: Como Programar.* 10. ed. Pearson, 2016. — Estruturas de controle de seleção.
- Wikipédia (PT): [Estrutura de controle](https://pt.wikipedia.org/wiki/Estrutura_de_controle).

---

!!! tip "Próxima Parada"
    Quando há **muitas opções fixas** (como um menu), o `Se` encadeado fica cansativo. Existe algo melhor: o **SWITCH-CASE**. Resolva a **[Lista 07](../listas/07-lista.md)**!

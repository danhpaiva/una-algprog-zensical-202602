# 🧩 Aula 12: Funções e Procedimentos

Quando um programa cresce, ele vira uma bagunça se tudo ficar no bloco principal. A solução é **dividir para conquistar**: quebrar o código em pequenos blocos com nome próprio, que fazem uma tarefa específica. Esses blocos são as **funções** e **procedimentos**.

---

## 🎯 Por que usar funções?

* **Reuso:** escreva uma vez, use quantas vezes quiser.
* **Organização:** cada bloco tem uma responsabilidade clara.
* **Manutenção:** se há um bug no cálculo, você conserta em **um** lugar só.
* **Legibilidade:** `calcularMedia()` diz mais do que 10 linhas de contas.

!!! quote "Princípio DRY"
    *Don't Repeat Yourself* — "Não se repita". Se você copiou e colou um trecho, provavelmente ele deveria ser uma função.

---

## 🔧 Procedimento (não retorna valor)

Um procedimento **executa uma ação**, mas não devolve um resultado.

```
Algoritmo "Saudacao"

Procedimento saudar()
Inicio
    Escreval("=================")
    Escreval(" Bem-vindo(a)!  ")
    Escreval("=================")
FimProcedimento

Inicio
    saudar()   // chamada do procedimento
    saudar()   // pode ser reutilizado
FimAlgoritmo
```

---

## 🧮 Função (retorna um valor)

Uma função **calcula e devolve** um resultado que pode ser usado em outra parte do código.

```
Algoritmo "Calculadora"

Funcao somar(a: real, b: real): real
Inicio
    Retorne a + b
FimFuncao

Var
    resultado: real
Inicio
    resultado <- somar(10, 5)
    Escreva("A soma é: ", resultado)   // 15
FimAlgoritmo
```

---

## 📥 Parâmetros: enviando dados para a função

Os valores entre parênteses são os **parâmetros** — as informações que a função precisa para trabalhar.

```
Funcao calcularArea(base: real, altura: real): real
Inicio
    Retorne (base * altura) / 2
FimFuncao
```

Aqui `base` e `altura` são parâmetros. Ao chamar `calcularArea(6, 4)`, a função recebe esses valores e retorna `12`.

---

## 🌐 Escopo de Variáveis (local vs. global)

* **Local:** existe só **dentro** da função. Nasce quando a função começa e morre quando ela termina.
* **Global:** declarada fora, visível em todo o programa.

!!! info "Boa prática"
    Prefira variáveis **locais** e a comunicação por **parâmetros** e **retorno**. Isso evita que uma função altere algo que outra não esperava — um dos bugs mais difíceis de caçar.

---

## 🛠️ Exemplo Completo: Verificando Par

```
Algoritmo "Verifica_Par"

Funcao ehPar(numero: inteiro): logico
Inicio
    Se (numero % 2 = 0) entao
        Retorne verdadeiro
    Senao
        Retorne falso
    FimSe
FimFuncao

Var
    n: inteiro
Inicio
    Escreva("Digite um número: ")
    Leia(n)

    Se (ehPar(n)) entao
        Escreva(n, " é par")
    Senao
        Escreva(n, " é ímpar")
    FimSe
FimAlgoritmo
```

---

## 📄 O "Contrato" de uma Função

Antes de escrever o corpo, pense na **assinatura** — o contrato que a função promete cumprir. Ele responde a três perguntas:

| Pergunta                    | Onde aparece            | Exemplo (`media`)         |
| :-------------------------- | :---------------------- | :------------------------ |
| O que ela **recebe**?       | parâmetros              | `n1, n2, n3: real`        |
| O que ela **devolve**?      | tipo de retorno         | `: real`                  |
| Como se **chama**?          | nome                    | `media`                   |

```
Funcao media(n1: real, n2: real, n3: real): real
Inicio
    Retorne (n1 + n2 + n3) / 3
FimFuncao
```

Pensar no contrato primeiro deixa claro o que a função precisa **antes** de você se preocupar com *como* ela calcula — exatamente o que os exercícios de **Dobro**, **Maior de Dois** e **Média** pedem.

---

## 🔁 Função vs. Procedimento: qual escolher?

A pergunta decisiva é: **"eu preciso de um resultado de volta?"**

=== "Precisa de resultado → Função"
    Calcular e devolver um valor que será usado depois. Ex.: `dobro(n)`, `maior(a, b)`, `celsiusParaFahrenheit(c)`.
    ```
    temp_f <- celsiusParaFahrenheit(37)   // guardo o retorno
    ```

=== "Só executa uma ação → Procedimento"
    Fazer algo visível (imprimir, desenhar um menu) sem devolver valor. Ex.: `exibirMenu()`.
    ```
    exibirMenu()   // só chama; não há retorno para guardar
    ```

!!! tip "Chamando dentro de um laço"
    No **Procedimento Menu** (Exercício 4), o `exibirMenu()` é chamado **dentro** de um `Repita`/`Enquanto`, mostrando as opções a cada volta. Um mesmo bloco, escrito uma vez, reutilizado sempre — o princípio DRY em ação.

---

## 📥 Como os Argumentos Chegam à Função

Quando você chama `dobro(5)`, o valor `5` é **copiado** para o parâmetro `n` dentro da função. Alterar `n` lá dentro **não** muda a variável original de fora (isso se chama *passagem por valor* e é o comportamento padrão).

!!! info "Por isso funções são seguras"
    Como a função trabalha com uma cópia, ela não estraga acidentalmente os dados de quem a chamou. A comunicação acontece de forma controlada: entra por **parâmetros**, sai por **retorno**.

---

## 📝 Desafios

??? abstract "Exercício 1: Função Dobro"
    Crie uma função `dobro(n)` que recebe um número e retorna o dobro dele. Teste com três valores.

??? abstract "Exercício 2: Maior de Dois"
    Crie uma função `maior(a, b)` que retorna o maior entre dois números.

??? abstract "Exercício 3: Média com Função"
    Crie uma função `media(n1, n2, n3)` que recebe três notas e retorna a média.

??? abstract "Exercício 4: Procedimento Menu"
    Crie um procedimento `exibirMenu()` que imprime as opções de um menu, e chame-o dentro de um laço.

??? abstract "Exercício 5: Conversor Reutilizável"
    Crie uma função `celsiusParaFahrenheit(c)` e use-a para converter três temperaturas diferentes.

---

## 📚 Referências

- **FORBELLONE, A. L. V.; EBERSPÄCHER, H. F.** *Lógica de Programação.* 3. ed. Pearson, 2005. — Cap. sobre modularização, funções e procedimentos.
- **ASCENCIO, A. F. G.; CAMPOS, E. A. V. de.** *Fundamentos da Programação de Computadores.* 3. ed. Pearson, 2012. — Sub-rotinas, escopo e passagem de parâmetros.
- **HUNT, A.; THOMAS, D.** *O Programador Pragmático.* Bookman, 2010. — Princípio DRY.
- Wikipédia (PT): [Sub-rotina](https://pt.wikipedia.org/wiki/Sub-rotina) · [Escopo (computação)](https://pt.wikipedia.org/wiki/Escopo_(computa%C3%A7%C3%A3o)).

---

!!! tip "Próxima Parada"
    Vamos organizar dados mais complexos com **Matrizes e Registros** na aula de **Estrutura de Dados**. Resolva a **[Lista 12](../listas/12-lista.md)**!

# ✨ Aula 05: Boas Práticas na Construção de Algoritmos

Um código pode estar "funcionando" e mesmo assim ser ruim. Nesta aula, o foco não é *fazer o computador entender* — ele entende quase qualquer coisa — mas *fazer o ser humano entender*. Afinal, você vai ler seu próprio código daqui a seis meses e precisa se reconhecer nele.

!!! quote
    "Qualquer tolo escreve código que um computador entende. Bons programadores escrevem código que humanos entendem." — Martin Fowler

---

## 🏷️ 1. Nomes que Contam uma História

O nome de uma variável deve dizer o que ela guarda, sem precisar de comentário.

=== "❌ Ruim"
    ```
    Var
        x, y, z: real
    Inicio
        z <- x * y
    ```

=== "✅ Bom"
    ```
    Var
        base, altura, area: real
    Inicio
        area <- base * altura
    ```

---

## 📐 2. Indentação (Recuo)

Indentar é deslocar o código para a direita para mostrar o que está "dentro" de quê. Blocos dentro de `Se`, `Enquanto` e `Para` devem ser recuados.

=== "❌ Sem indentação"
    ```
    Se (idade >= 18) entao
    Escreva("Maior de idade")
    Senao
    Escreva("Menor de idade")
    FimSe
    ```

=== "✅ Com indentação"
    ```
    Se (idade >= 18) entao
        Escreva("Maior de idade")
    Senao
        Escreva("Menor de idade")
    FimSe
    ```

---

## 💬 3. Comentários com Moderação

Comentário bom explica o **porquê**, não o **o quê**. O código já diz o que faz.

```
// Aplica 10% de desconto para clientes do plano premium (regra da promoção de aniversário)
preco_final <- preco * 0.9
```

!!! warning "Evite comentário óbvio"
    `soma <- a + b // soma a com b` não ajuda ninguém. Prefira um nome de variável claro a um comentário que apenas repete o código.

---

## 🔎 4. Teste de Mesa (a arma secreta)

Antes de rodar, simule o algoritmo **na mão**, linha por linha, anotando o valor de cada variável. É assim que se caça um bug sem depender de sorte.

Considere:

```
Var
    a, b, soma: inteiro
Inicio
    a <- 3
    b <- 4
    soma <- a + b
    Escreva(soma)
FimAlgoritmo
```

| Passo | a | b | soma | Saída |
| :---- | :-: | :-: | :--: | :---- |
| a <- 3    | 3 | - | -  |     |
| b <- 4    | 3 | 4 | -  |     |
| soma <- a+b | 3 | 4 | 7  |     |
| Escreva   | 3 | 4 | 7  | 7   |

---

## 🧱 5. Constantes para Valores Fixos

Se um número "mágico" se repete, dê um nome a ele. Fica mais legível e fácil de mudar.

```
Algoritmo "Circunferencia"
Var
    raio, perimetro: real
Inicio
    Leia(raio)
    perimetro <- 2 * 3.14159 * raio  // 3.14159 é o PI
    Escreva(perimetro)
FimAlgoritmo
```

---

## 🐞 6. Erros de Precedência (o bug silencioso)

O bug mais traiçoeiro não é o que trava o programa — é o que **roda e dá o resultado errado**. O campeão dessa categoria é esquecer os parênteses numa fórmula:

=== "❌ Errado"
    ```
    media <- nota1 + nota2 / 2
    ```
    Como `/` tem prioridade sobre `+`, o computador calcula `nota2 / 2` **primeiro** e só depois soma `nota1`. Para notas 8 e 6 o resultado é `8 + 3 = 11` — impossível!

=== "✅ Correto"
    ```
    media <- (nota1 + nota2) / 2
    ```
    Os parênteses forçam a soma a acontecer antes da divisão: `(8 + 6) / 2 = 7`.

!!! danger "Como esse bug se esconde"
    O programa não acusa erro nenhum: ele apenas devolve um número **plausível, mas errado**. É exatamente o cenário do Exercício 3 (Caça ao Bug). A defesa é fazer o **teste de mesa** com um exemplo cujo resultado você já conhece.

---

## 🧹 7. Como Refatorar um Código

*Refatorar* é melhorar a forma **sem** mudar o que o código faz. Um roteiro prático (útil no Exercício 1):

1. **Entenda** o que o código faz (leia e faça o teste de mesa).
2. **Renomeie** variáveis para nomes que contam a história.
3. **Indente** os blocos para revelar a estrutura.
4. **Confirme** que o resultado continua o mesmo com os mesmos dados de entrada.

!!! info "Regra de ouro da refatoração"
    Mude **uma coisa de cada vez** e verifique. Se você renomeia e reindenta tudo de uma vez e o resultado muda, fica difícil saber o que quebrou.

---

## ✅ Checklist do Código Limpo

!!! check "Antes de considerar um algoritmo 'pronto'"
    - [ ] Os nomes das variáveis são claros?
    - [ ] O código está indentado corretamente?
    - [ ] Fiz o teste de mesa com pelo menos dois exemplos?
    - [ ] Removi comentários inúteis e mantive só os que explicam o "porquê"?
    - [ ] Usei parênteses para deixar a ordem dos cálculos explícita?
    - [ ] Todos os caminhos do algoritmo têm um fim?

---

## 📝 Desafios

??? abstract "Exercício 1: Refatore este código"
    Reescreva o algoritmo abaixo com nomes claros e indentação correta:
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
    Faça o teste de mesa (tabela) do algoritmo abaixo para `n = 5`:
    ```
    dobro <- n * 2
    triplo <- n * 3
    resultado <- dobro + triplo
    Escreva(resultado)
    ```

??? abstract "Exercício 3: Caça ao Bug"
    O algoritmo deveria calcular a média de duas notas, mas está errado. Encontre e corrija o erro:
    ```
    media <- nota1 + nota2 / 2
    ```

---

## 📚 Referências

- **MARTIN, R. C.** *Código Limpo: Habilidades Práticas do Agile Software.* Rio de Janeiro: Alta Books, 2009. — Leitura de referência sobre nomes, funções e legibilidade.
- **FOWLER, M.** *Refatoração: Aperfeiçoando o Design de Códigos Existentes.* 2. ed. Novatec, 2020.
- **HUNT, A.; THOMAS, D.** *O Programador Pragmático.* Bookman, 2010. — Princípios DRY e boas práticas.
- **FORBELLONE, A. L. V.; EBERSPÄCHER, H. F.** *Lógica de Programação.* 3. ed. Pearson, 2005. — Teste de mesa.

---

!!! tip "Próxima Parada"
    Agora que sabemos escrever bem, vamos nos aprofundar nos **Tipos de Dados Primitivos e Compostos**. Resolva a **[Lista 05](../listas/05-lista.md)**!

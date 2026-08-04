# 🧱 Aula 14: Introdução à Programação Orientada a Objetos (POO)

Até agora programamos de forma **estruturada**: dados de um lado, funções de outro. A **Programação Orientada a Objetos** propõe algo diferente: juntar os dados e as ações que operam sobre eles numa mesma unidade, o **objeto**. É o paradigma mais usado no mercado (Java, C#, Python, Kotlin...).

---

## 💡 A Grande Ideia: modelar o mundo real

Olhe ao seu redor: tudo são objetos. Um **carro** tem características (cor, marca, velocidade) e comportamentos (acelerar, frear). A POO nos deixa representar isso no código quase da mesma forma.

| Mundo real          | POO                        |
| :------------------ | :------------------------- |
| Características      | **Atributos** (dados)      |
| Comportamentos      | **Métodos** (ações)        |
| "Um carro"          | **Objeto**                 |
| A "planta" do carro | **Classe**                 |

---

## 🏭 Classe vs. Objeto

* **Classe** é o **molde** (a receita, a planta). Define o que todo objeto daquele tipo terá.
* **Objeto** é uma **instância** criada a partir do molde (o bolo pronto).

*De uma classe `Carro` você cria vários objetos: o carro do João, o carro da Maria...*

```
Classe Carro
    // Atributos (características)
    marca: caractere
    cor: caractere
    velocidade: inteiro

    // Métodos (comportamentos)
    Procedimento acelerar()
    Inicio
        velocidade <- velocidade + 10
    FimProcedimento

    Procedimento frear()
    Inicio
        velocidade <- velocidade - 10
    FimProcedimento
FimClasse
```

!!! info "Comparação com o que já sabemos"
    Um **registro** (Aula 13) só guardava dados. Uma **classe** guarda dados **e** as ações que mexem neles, tudo junto. É a evolução natural do registro.

---

## 🔨 Criando e Usando Objetos

```
Var
    meuCarro: Carro
Inicio
    // Instanciando (criando) o objeto
    meuCarro <- novo Carro()

    // Definindo atributos
    meuCarro.marca <- "Fiat"
    meuCarro.cor <- "Vermelho"
    meuCarro.velocidade <- 0

    // Chamando métodos (comportamentos)
    meuCarro.acelerar()
    meuCarro.acelerar()

    Escreva("Velocidade atual: ", meuCarro.velocidade)   // 20
```

O ponto (`.`) é usado tanto para acessar atributos (`meuCarro.cor`) quanto para chamar métodos (`meuCarro.acelerar()`).

---

## 🔒 Encapsulamento (o primeiro pilar)

Encapsular é **proteger** os dados internos de um objeto, expondo-os apenas por métodos controlados. Assim, ninguém coloca um valor inválido diretamente.

*Exemplo: em vez de deixar qualquer um fazer `conta.saldo <- -5000`, obrigamos a passar pelo método `sacar()`, que valida se há saldo suficiente.*

```
Classe ContaBancaria
    saldo: real  // privado: só a própria classe mexe

    Procedimento depositar(valor: real)
    Inicio
        Se (valor > 0) entao
            saldo <- saldo + valor
        FimSe
    FimProcedimento

    Funcao consultarSaldo(): real
    Inicio
        Retorne saldo
    FimFuncao
FimClasse
```

!!! tip "Analogia"
    Você não mexe direto no motor do carro para acelerar; você pisa no pedal. O pedal é a "interface pública"; o motor é o dado "encapsulado".

---

## 🔦 O Estado de um Objeto

Cada objeto carrega seu próprio **estado** — os valores atuais de seus atributos. Os métodos são justamente o que **lê** ou **altera** esse estado ao longo do tempo. Uma `Lampada` (Exercício 3) é o exemplo mais claro:

```
Classe Lampada
    ligada: logico

    Procedimento acender()
    Inicio
        ligada <- verdadeiro
    FimProcedimento

    Procedimento apagar()
    Inicio
        ligada <- falso
    FimProcedimento

    Funcao estaLigada(): logico
    Inicio
        Retorne ligada
    FimFuncao
FimClasse
```

Repare na divisão de tarefas:

- `acender()` e `apagar()` **mudam** o estado (não retornam nada → *procedimentos*).
- `estaLigada()` apenas **consulta** o estado (retorna um valor → *função*).

Essa mesma distinção aparece na `Pessoa` (`apresentar()` só age) e no `Retangulo` (`calcularArea()` devolve um número).

---

## 🧮 Métodos que Calculam a partir dos Atributos

Um método pode usar os atributos do próprio objeto para produzir um resultado, sem precisar receber tudo por parâmetro. É o caso do `Retangulo` (Exercício 2):

```
Classe Retangulo
    base: real
    altura: real

    Funcao calcularArea(): real
    Inicio
        Retorne base * altura         // usa os atributos do objeto
    FimFuncao

    Funcao calcularPerimetro(): real
    Inicio
        Retorne 2 * (base + altura)
    FimFuncao
FimClasse
```

!!! info "De onde vêm base e altura?"
    Dentro do método, `base` e `altura` referem-se aos atributos **daquele objeto**. Se você criar dois retângulos com medidas diferentes, cada `calcularArea()` usa as medidas do seu próprio objeto — cada um tem seu estado.

---

## 🔒 Validação: o "porquê" do Encapsulamento

Encapsular só faz sentido se os métodos **protegem** o objeto de estados inválidos. Na `ContaBancaria` (Exercício 4), o método `sacar()` é o guardião do saldo:

```
Procedimento sacar(valor: real)
Inicio
    Se (valor > 0) e (valor <= saldo) entao
        saldo <- saldo - valor
    Senao
        Escreval("Saque negado: valor inválido ou saldo insuficiente")
    FimSe
FimProcedimento
```

Sem esse método, qualquer trecho do programa poderia fazer `conta.saldo <- -9999`. Com ele, **toda alteração passa por uma regra** — é isso que torna o sistema confiável.

---

## 📝 Desafios

??? abstract "Exercício 1: Classe Pessoa"
    Modele uma classe `Pessoa` com atributos `nome` e `idade`, e um método `apresentar()` que exibe "Olá, meu nome é ... e tenho ... anos".

??? abstract "Exercício 2: Classe Retangulo"
    Crie uma classe `Retangulo` com `base` e `altura`, e métodos `calcularArea()` e `calcularPerimetro()`.

??? abstract "Exercício 3: Classe Lampada"
    Modele uma `Lampada` com o atributo `ligada` (logico) e os métodos `acender()`, `apagar()` e `estaLigada()`.

??? abstract "Exercício 4: Conta Bancária"
    Amplie a classe `ContaBancaria` do exemplo com um método `sacar(valor)` que só permite o saque se houver saldo suficiente (encapsulamento na prática).

---

## 📚 Referências

- **DEITEL, P.; DEITEL, H.** *Java: Como Programar.* 10. ed. Pearson, 2016. — Classes, objetos e encapsulamento.
- **BARNES, D. J.; KÖLLING, M.** *Programação Orientada a Objetos com Java.* Pearson. — Abordagem prática com BlueJ.
- **SEBESTA, R. W.** *Conceitos de Linguagens de Programação.* 11. ed. Bookman, 2018. — Fundamentos de POO.
- Wikipédia (PT): [Programação orientada a objetos](https://pt.wikipedia.org/wiki/Programa%C3%A7%C3%A3o_orientada_a_objetos) · [Encapsulamento (programação)](https://pt.wikipedia.org/wiki/Encapsulamento_(programa%C3%A7%C3%A3o)).

---

!!! tip "Próxima Parada"
    Na última aula, vamos ver os outros pilares da POO — **Herança e Polimorfismo** — e juntar tudo num exemplo completo. Resolva a **[Lista 14](../listas/14-lista.md)**!

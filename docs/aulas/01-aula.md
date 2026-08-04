# 🧠 Aula 01: Pensamento Computacional e Lógica

Bem-vindos à base de tudo! Antes de digitarmos uma única linha de código, precisamos aprender a "ensinar" uma máquina a pensar. Spoiler: máquinas são muito rápidas, mas incrivelmente literais (fazem exatamente o que mandamos, nem mais, nem menos).

---

## 🧐 O que é Lógica de Programação?

A lógica de programação é a organização coerente de uma sequência de passos para atingir um objetivo. No ensino superior, não queremos apenas que você decore comandos, mas que desenvolva a habilidade de **decompor problemas complexos**.

!!! quote "Pensamento do Dia"
    "Programar não é sobre o que você sabe; é sobre o que você consegue descobrir." — Chris Pine

---

## 🧩 Os Pilares do Pensamento Computacional

Para resolver qualquer problema na nossa área, usamos quatro pilares:

=== "1. Decomposição"
    Dividir um problema complexo em partes menores e mais gerenciáveis.
    *Exemplo: Para fazer um café, você precisa moer o grão, esquentar a água, filtrar, etc.*

=== "2. Reconhecimento de Padrões"
    Identificar similaridades entre problemas já resolvidos.
    *Exemplo: O processo de validar um CPF é muito parecido com o de validar um CNPJ.*

=== "3. Abstração"
    Focar apenas nos detalhes importantes e ignorar o que é irrelevante.
    *Exemplo: Para um GPS, não importa a cor do seu carro, apenas a sua coordenada.*

=== "4. Algoritmos"
    Criar o passo a passo definitivo (a receita) para resolver o problema.

---

## 🧠 Pensamento Algorítmico Incremental

Construa algoritmos passo a passo:

1. Resolver manualmente
2. Escrever em linguagem natural
3. Transformar em pseudocódigo
4. Testar com exemplos
5. Melhorar

---

## 🤖 Desafio Prático: O Algoritmo do "Mestre Cuca"

Vamos analisar como um computador interpretaria uma instrução simples.

!!! example "Instrução Humana vs. Instrução Computacional"
    **Humano:** "Frite um ovo."

    **Computador (Algoritmo):**

    1. Pegue a frigideira no armário.
    2. Coloque a frigideira no fogão.
    3. Acenda o fogo.
    4. Adicione uma colher de óleo.
    5. **Se** o óleo estiver quente:
        * Quebre o ovo na frigideira.
    6. **Senão**:
        * Espere 30 segundos e volte ao passo 5.

---

## 🛠️ Experimentando com Pseudocódigo

Abaixo está um exemplo de como estruturamos essa lógica usando uma linguagem "quase humana" (Portugol):

```
Algoritmo "Verificador_de_Idade"
Var
   idade: inteiro
Inicio
   Escreva("Digite sua idade: ")
   Leia(idade)

   Se (idade >= 18) entao
      Escreva("Acesso permitido: Você é maior de idade.")
   Senao
      Escreva("Acesso negado: Conteúdo restrito.")
   FimSe
FimAlgoritmo
```

## 🔎 Teste de Mesa (Simulação)

Antes de executar, simule o algoritmo manualmente.

| idade | Resultado  |
| :---- | :--------- |
| 10    | Negado     |
| 18    | Permitido  |
| 30    | Permitido  |

---

## 🧱 As 3 Estruturas que Formam Todo Algoritmo

Por mais complexo que um programa pareça, ele é sempre construído com a combinação de apenas **três** tipos de estrutura. Guarde bem estes nomes, pois eles vão reaparecer no curso inteiro:

=== "1. Sequência"
    Um passo depois do outro, de cima para baixo, sem desvios.
    *Exemplo: "pesquisar o celular → validar o vendedor → confirmar o saldo → finalizar a compra".*

=== "2. Decisão (Seleção)"
    O fluxo escolhe um caminho conforme uma condição ("se... então... senão").
    *Exemplo: "**se** o frete for grátis, selecione-o; **senão**, avalie o prazo".*

=== "3. Repetição (Laço)"
    Um trecho é executado várias vezes até que uma condição seja satisfeita.
    *Exemplo: "**enquanto** você não atravessar a catraca, continue caminhando".*

!!! tip "Ligue a teoria aos desafios"
    Repare que os três exercícios desta aula usam exatamente essas estruturas: a **travessia do rio** é uma *sequência* de passos com restrições; a **compra online** mistura *sequência* e *decisões*; e a **navegação até o metrô** só termina quando uma condição é atingida — uma *repetição*.

---

## 🗺️ Estado, Restrições e Invariantes

Nem todo problema se resolve "só seguindo em frente". Alguns exigem que você acompanhe o **estado** — a fotografia da situação em cada momento — e respeite **restrições** que nunca podem ser violadas.

No **desafio da travessia**, o estado é *quem está em cada margem do rio*. A cada viagem esse estado muda, e existe uma regra que precisa valer o tempo todo (uma *invariante*):

> "O lobo nunca pode ficar sozinho com a cabra, e a cabra nunca pode ficar sozinha com a couve."

!!! example "Pensando por estados"
    | Margem esquerda        | Barco →        | Margem direita     |
    | :--------------------- | :------------- | :----------------- |
    | lobo, cabra, couve     | (início)       | —                  |
    | lobo, couve            | leva a cabra → | cabra              |
    | ...                    | ...            | ...                |

    A cada linha, pergunte-se: **"alguma restrição foi violada?"** Se sim, esse passo é inválido e você precisa voltar atrás.

Essa ideia de "testar se uma regra continua válida a cada passo" é a semente da **validação** que você fará em código (por exemplo, checar o saldo antes de confirmar a compra).

---

## ⚠️ Erros Comuns de Lógica

!!! danger "Cuidado com o Loop Infinito"
    Um erro clássico é esquecer de dar uma condição de parada para o computador.
    *Exemplo: "Ande para frente enquanto não bater na parede", mas você está em um campo aberto.*

!!! danger "Passos ambíguos ou fora de ordem"
    O computador é literal: "coloque o ovo na frigideira" antes de "acenda o fogo" produz um resultado bem diferente. Ao escrever seu algoritmo, garanta que **cada passo tenha um único sentido** e que a **ordem** faça sentido.

---

## 📝 Atividade de Fixação

??? abstract "Exercício: O Desafio da Travessia"
    Um fazendeiro precisa levar um lobo, uma cabra e um maço de couve para o outro lado do rio.
    Ele tem um barco que só permite levar ele e mais um item.

    **Regras:**

    - Se o lobo ficar sozinho com a cabra, ele a come.
    - Se a cabra ficar sozinha com a couve, ela a come.

    **Tarefa:** Escreva no seu caderno o passo a passo (algoritmo) para atravessar todos em segurança.

??? abstract "Exercício: Logística de E-commerce"
    Você decidiu comprar um novo celular, mas precisa garantir que a compra seja segura, econômica e bem-sucedida.

    **Regras:**

    - Verifique se o vendedor é confiável (loja oficial).
    - O saldo no cartão deve ser validado antes de confirmar.
    - Se o frete for grátis, selecione-o; caso contrário, avalie o prazo.

    **Tarefa:** Escreva no seu caderno o passo a passo (algoritmo) para realizar a compra, da pesquisa até o checkout.

??? abstract "Exercício: Algoritmo de Navegação"
    Você está em sua localização atual e precisa chegar à estação de metrô para não perder o horário da aula.

    **Regras:**

    - Se a distância for menor que 1km, vá a pé.
    - Se estiver chovendo, utilize um transporte por aplicativo.
    - O algoritmo só termina quando você atravessar a catraca da estação.

    **Tarefa:** Escreva o passo a passo detalhando o trajeto e as decisões que você deve tomar no caminho.

---

## 📚 Referências

Para aprofundar os conceitos desta aula, consulte:

- **FORBELLONE, A. L. V.; EBERSPÄCHER, H. F.** *Lógica de Programação: A Construção de Algoritmos e Estruturas de Dados.* 3. ed. São Paulo: Pearson Prentice Hall, 2005. — Cap. 1 (Introdução à lógica e ao conceito de algoritmo).
- **ASCENCIO, A. F. G.; CAMPOS, E. A. V. de.** *Fundamentos da Programação de Computadores.* 3. ed. São Paulo: Pearson, 2012. — Cap. 1.
- **WING, J. M.** "Computational Thinking." *Communications of the ACM*, v. 49, n. 3, 2006. — Artigo que popularizou o termo *pensamento computacional*.
- **PINE, C.** *Learn to Program.* 2. ed. Pragmatic Bookshelf, 2009. — Leitura introdutória e leve.
- Wikipédia (PT): [Algoritmo](https://pt.wikipedia.org/wiki/Algoritmo) · [Pensamento computacional](https://pt.wikipedia.org/wiki/Pensamento_computacional).

---

!!! tip "Próximos Passos"
    Na próxima aula, transformaremos essa lógica em desenhos: os **Fluxogramas**. Não esqueça de revisar este material e de fazer a **[Lista 01](../listas/01-lista.md)**!

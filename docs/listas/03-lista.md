# 🚀 Lista 03 — Variáveis e Operadores Matemáticos

Variáveis são os recipientes da nossa lógica e os operadores são as ferramentas que transformam dados brutos em informação útil. No desenvolvimento, **código limpo e cálculos precisos separam os amadores dos profissionais.**

---

## 🛠️ O Algoritmo da Entrega

### 1. Codificar com Precisão

Resolva os exercícios abaixo no **Portugol Studio**. Comente seu código explicando o que cada variável armazena.

### 2. Organizar o Repositório

Crie o repositório `una-algprog-lista03`.

### 3. Documentação (o diferencial)

No `README.md`, explique brevemente a importância de escolher o **tipo de dado correto** (inteiro vs. real) para evitar erros de arredondamento em sistemas financeiros.

---

## 📝 Lista de Exercícios

??? abstract "Exercício 1: O Fechamento do Caixa"
    Leia o nome de um produto, o preço unitário e a quantidade comprada. Calcule o total e exiba: `"O produto [nome] custou total de R$ [valor_total]"`.

??? abstract "Exercício 2: Conversor de Temperatura"
    Leia uma temperatura em **Celsius** e converta para **Fahrenheit**.
    **Fórmula:** $F = (C \cdot 1.8) + 32$

??? abstract "Exercício 3: Média Ponderada"
    A Prova A tem peso 4 e a Prova B peso 6. Leia as duas notas e calcule a média ponderada.
    **Dica:** $Média = \frac{(NotaA \cdot 4) + (NotaB \cdot 6)}{10}$

??? abstract "Exercício 4: O Consumo do Automóvel"
    Leia a distância percorrida (km) e o combustível gasto (litros). Calcule e exiba o consumo médio (km/l).

??? abstract "Exercício 5: Cálculo de Desconto"
    Leia o valor original de um produto e o percentual de desconto (ex: 15). Calcule o valor do desconto em reais e o preço final.

---

## 📂 Estrutura Sugerida

```text
una-algprog-lista03/
├── README.md
└── algoritmos/
    ├── 01_fechamento_caixa.por
    ├── 02_conversor_temp.por
    ├── 03_media_ponderada.por
    ├── 04_consumo_carro.por
    └── 05_calculo_desconto.por
```

---

## ⚠️ Checklist de Qualidade

!!! check "Critérios de Aceite"
    - [ ] As variáveis têm nomes significativos (`preco_final` em vez de `pf`)?
    - [ ] O Exercício 2 usa o tipo **real** para as temperaturas?
    - [ ] A precedência matemática (parênteses) foi aplicada corretamente?
    - [ ] O `README.md` contém seu nome e uma breve descrição da lista?

---

!!! info "Dica de Sênior"
    Comece a pensar como um **QA**: o que acontece se o usuário digitar uma letra onde deveria ser um número? Prever erros de entrada é marca de profissional.

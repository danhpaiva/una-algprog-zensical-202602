# 🚀 Lista 07 — Estruturas de Controle: IF-ELSE

Dominar o `Se/Senao` é o que permite criar sistemas de segurança, filtros e regras de negócio. O foco aqui não é só o cálculo, mas **qual caminho o código deve seguir**.

---

## 🛠️ O Algoritmo da Entrega

1. Resolva os exercícios no **Portugol Studio**.
2. Crie o repositório público `una-algprog-lista07`.
3. No `README.md`, explique a diferença entre `Se` simples, `Se/Senao` e `Se/Senao Se` encadeado.

---

## 📝 Lista de Exercícios

??? abstract "Exercício 1: Par ou Ímpar"
    Leia um número inteiro e informe se ele é **par** ou **ímpar** (`numero % 2 = 0`).

??? abstract "Exercício 2: Maior de Três"
    Leia três números diferentes e informe qual é o **maior**.

??? abstract "Exercício 3: Classificação de IMC"
    Calcule o IMC (peso / altura²) e classifique: abaixo de 18.5 (abaixo do peso), 18.5 a 24.9 (normal), 25 a 29.9 (sobrepeso), 30 ou mais (obesidade).

??? abstract "Exercício 4: Login Simples"
    Leia usuário e senha. Se usuário = "admin" **e** senha = "1234", exiba "Acesso liberado"; senão, "Acesso negado".

??? abstract "Exercício 5: Radar de Velocidade"
    O limite é 80 km/h. Leia a velocidade; se ultrapassar, calcule a multa (R$ 7,00 por km acima do limite). Se estiver dentro, exiba "Boa viagem!".

---

## 📂 Estrutura Sugerida

```text
una-algprog-lista07/
├── README.md
└── algoritmos/
    ├── 01_par_impar.por
    ├── 02_maior_de_tres.por
    ├── 03_classificacao_imc.por
    ├── 04_login_simples.por
    └── 05_radar_velocidade.por
```

---

## ⚠️ Checklist de Qualidade

!!! check "Critérios de Aceite"
    - [ ] Você usou `Senao Se` para evitar múltiplos `Se` soltos no Exercício 3?
    - [ ] As faixas do IMC foram testadas na ordem correta?
    - [ ] Você evitou testes redundantes (ex: testar `> 10` e depois `<= 10`)?
    - [ ] O código está indentado?

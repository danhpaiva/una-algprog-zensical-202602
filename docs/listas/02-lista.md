# 🚀 Lista 02 — Fluxogramas e Estruturas de Decisão

Você já aprendeu a desenhar a lógica e a visualizar o fluxo dos dados. Agora, como um(a) verdadeiro(a) desenvolvedor(a), vamos documentar e versionar esse conhecimento.

No mundo real, **"se não está no GitHub, não existe"**. Vamos transformar seus fluxogramas em mais um marco do seu portfólio.

---

## 📝 Exercícios

??? abstract "Exercício 1: O Sensor de Estacionamento"
    Desenhe (ou descreva) o fluxo para um sensor de ré de um carro:

    - O sensor lê a distância.
    - **Se** a distância for menor que 0.5m: Tocar bipe contínuo e exibir "PARE".
    - **Se** estiver entre 0.5m e 2m: Tocar bipe intermitente.
    - **Senão**: Não emitir som.

??? abstract "Exercício 2: O Filtro de Foto"
    Crie a lógica (fluxograma) para um filtro de foto:

    1. O usuário escolhe uma foto.
    2. Pergunta: "Aplicar filtro P&B?" Se sim, transforma em cinza.
    3. Pergunta: "Postar agora?" Se sim, envia ao servidor; se não, salva na galeria.

??? abstract "Exercício 3: O Caixa Eletrônico"
    Desenhe o fluxo de um saque:

    - Ler o `valor_saque`.
    - Se `valor_saque <= saldo_disponivel`: subtrair do saldo e entregar as notas.
    - Senão: exibir "Saldo Insuficiente".

---

## 🛠️ O Algoritmo da Entrega

### 1. Refinar a Arte

Você pode tirar uma **foto nítida** do seu caderno ou usar ferramentas digitais como o [Lucidchart](https://www.lucidchart.com/), [Whimsical](https://whimsical.com/) ou o [Mermaid Live Editor](https://mermaid.live/).

### 2. Organizar o Repositório

Crie um repositório público chamado `una-algprog-lista02`. Adicione um `README.md` como "capa" do projeto.

### 3. Upload

Suba os fluxogramas (`.png`, `.jpg` ou código Mermaid) e os pseudocódigos (`.txt` ou `.md`).

### 4. Commit da Vitória

Escreva uma mensagem clara, como:
`feat: adicionado fluxograma do caixa eletronico e sensor de re`

---

## 📂 Estrutura Sugerida

```text
una-algprog-lista02/
├── README.md
├── fluxogramas/
│   ├── sensor_re.png
│   └── caixa_eletronico.png
└── algoritmos/
    └── filtro_foto.txt
```

---

## ⚠️ Checklist de Qualidade

!!! check "Critérios de Aceite"
    - [ ] O repositório está **público**?
    - [ ] Os fluxogramas usam os símbolos corretos (losango para decisão, etc.)?
    - [ ] O link enviado no Classroom leva direto ao repositório?
    - [ ] O `README.md` descreve brevemente os exercícios?

---

!!! info "Desafio Extra"
    Tente usar a sintaxe **Mermaid** dentro do `README.md` para renderizar um fluxograma direto no GitHub. Isso deixa seu perfil com nível técnico altíssimo!

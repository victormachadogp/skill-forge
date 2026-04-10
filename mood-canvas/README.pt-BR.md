# Mood Canvas

Mood Canvas é um projeto de artes visuais interativas onde cada peça é construída a partir de uma frase emocional.

O objetivo não é apenas exibir algo bonito, mas traduzir um sentimento em uma experiência visual e interativa.

## 🎯 Objetivo

Aprender e experimentar criando artes usando Three.js ou outros frameworks visuais. A IA gera as artes com base em um prompt emocional. Uma peça completa é a combinação da frase emocional com os efeitos visuais renderizados na mesma tela.

---

## 🎨 Conceitos Artísticos

### Emoção → Mapeamento Visual

> "Cada emoção define regras de comportamento visual."

Cada emoção se traduz em um conjunto de comportamentos visuais — não apenas cores, mas movimento, ritmo e peso.

| Emoção | Comportamento |
|---|---|
| `grief` | lento, fade, repetição, tons frios |
| `anxiety` | jitter, tremor, loops rápidos |
| `joy` | expansão, cores quentes, movimento leve |
| `nostalgia` | blur, fade, delay |

### 🌫️ Sistema de Atmosfera

A cena não é só visual — ela tem clima.

- Paleta de cores
- Iluminação e sombra
- Densidade visual
- Contraste e saturação

### ⏳ Comportamento Temporal

O tempo é um elemento de primeira classe em cada peça.

- Coisas aparecem devagar
- Desaparecem
- Repetem
- Aceleram ou desaceleram

> `grief finds me again` → repetição visual como recorrência emocional

> "Eu não desenho — eu defino como o sistema se comporta."

---

## 🧱 Camada Técnica

### 🤖 Prompt como DSL

> O prompt não é só texto — ele é uma linguagem de configuração.

```json
{
  "emotion": "grief",
  "intensity": 0.8,
  "recurrence": true,
  "motion": "slow",
  "visual": "fireworks",
  "text": "As soon as I think I am healing..."
}
```

Isso permite:

- Padronização entre as peças
- Geração automática de cenas
- Integração com IA
- Separação entre intenção e implementação

> "O usuário descreve sentimento — o sistema interpreta comportamento."

### 🧩 Peça como Unidade Isolada

Cada arte é uma unidade completamente independente.

```
pieces/{tipo}--{nome}--{lib}--{framework}/
```

Sem estado compartilhado, sem dependências globais. Cada pasta é autocontida e pode ser executada por conta própria.

---

## Padrões do Projeto

### Estrutura de Pastas

Cada peça visual vive em sua própria pasta dentro de `pieces/`:

```
mood-canvas/
└── pieces/
    └── {tipo}--{nome-da-arte}--{lib}--{framework}/
```

### Convenção de Nomenclatura de Pastas

Padrão: `{tipo}--{nome-da-arte}--{lib}--{framework}`

Cada segmento usa kebab-case. Dois traços separam os segmentos para evitar ambiguidade, já que os nomes das artes podem conter hífens.

| Segmento | Exemplos |
|---|---|
| `tipo` | `scene`, `particle`, `shader`, `interactive` |
| `nome-da-arte` | `ocean-breathing`, `inner-fire`, `falling-thoughts` |
| `lib` | `threejs`, `p5js`, `canvas2d`, `pixijs` |
| `framework` | `react`, `vanilla`, `svelte` |

**Exemplo:** `particle--falling-thoughts--threejs--react`

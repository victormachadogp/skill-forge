# Mood Canvas

Mood Canvas é um projeto de artes visuais interativas onde cada peça é construída a partir de uma frase emocional.

O objetivo não é apenas exibir algo bonito, mas traduzir um sentimento em uma experiência visual e interativa.

## 🎯 Objetivo

Aprender e experimentar criando artes usando Three.js ou outros frameworks visuais. A IA gera as artes com base em um prompt emocional. Uma peça completa é a combinação da frase emocional com os efeitos visuais renderizados na mesma tela.

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

# Mood Canvas

Mood Canvas é um projeto de artes visuais interativas onde cada peça nasce de uma frase emocional. O objetivo é traduzir sentimento em experiência, visual, sonora, enquanto exploro conceitos reais de engenharia de software, arquitetura e ferramentas do ecossistema frontend.

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

Cada arte é uma unidade completamente independente — sem estado compartilhado, sem dependências globais. Cada pasta é autocontida e pode ser executada por conta própria.

---

## Padrões do Projeto

### Estrutura de Pastas

Cada peça visual vive em sua própria pasta diretamente dentro de `mood-canvas/`:

```
mood-canvas/
└── {tipo}--{nome-da-arte}--{lib}--{framework}/
    ├── index.html
    ├── meta.json
    └── LEARNINGS.md
```

### Convenção de Nomenclatura de Pastas

Padrão: `{tipo}--{nome-da-arte}--{lib}--{framework}`

Cada segmento usa kebab-case. Dois traços separam os segmentos para evitar ambiguidade, já que os nomes das artes podem conter hífens.

| Segmento | Exemplos |
|---|---|
| `tipo` | `scene`, `particle`, `shader`, `interactive` |
| `nome-da-arte` | `ocean-breathing`, `inner-fire`, `falling-thoughts` |
| `lib` | `threejs`, `p5js`, `canvas2d`, `pixijs`, `vanilla` |
| `framework` | `react`, `vanilla`, `svelte` |

**Exemplo:** `particle--falling-thoughts--threejs--react`

> Quando nenhuma biblioteca visual ou framework é utilizado, ambos os segmentos são `vanilla`.
> **Exemplo:** `scene--is-war-as-old-as-gravity--vanilla--vanilla`

### Nomenclatura de branches

Cada peça é desenvolvida em sua própria branch:

```
feat/mood-canvas/{nome-da-arte}
```

### Cada peça deve conter

- `index.html` — a peça em si
- `meta.json` — metadados (emoção, intensidade, movimento, visual, texto, etc.)
- `LEARNINGS.md` — o que foi explorado e aprendido

---

## Peças

| Peça | Ver | Tech |
|---|---|---|
| Is War as Old as Gravity | [ver ↗](https://victormachadogp.github.io/skill-forge/mood-canvas/scene--is-war-as-old-as-gravity--vanilla--vanilla/) | vanilla |

---

## Backlog

Ideias e evoluções que podem fazer sentido à medida que o projeto cresce. Nada aqui é prioridade — são direções possíveis, não compromissos.

### Galeria e apresentação

- [ ] **Galeria web** — uma página index que lista todas as peças com preview (screenshot ou GIF) e link para abrir cada uma
- [ ] **Deploy automático** — cada peça publicada via GitHub Pages ou similar, acessível por URL direta
- [ ] **Thumbnails automáticos** — script que abre cada peça em headless browser, tira screenshot e salva como preview

### Ferramentas e automação

- [ ] **CLI de scaffolding** — um comando que cria a estrutura de uma peça nova (pasta, `meta.json`, `LEARNINGS.md`, arquivo base) a partir de um template
- [ ] **Validação de estrutura** — lint que verifica se cada peça tem `meta.json`, `LEARNINGS.md` e segue a convenção de nomenclatura
- [ ] **Catálogo de peças** — JSON gerado automaticamente a partir dos `meta.json` de cada peça, servindo como índice do projeto

### Evolução técnica

- [ ] **Shaders como foco** — uma série de peças dedicadas a aprender GLSL/WebGL shaders do zero
- [ ] **Responsividade como constraint** — peças que funcionam bem em mobile, explorando touch events e orientação do dispositivo
- [ ] **Performance budgets** — definir limites de FPS e memória por peça e medir com DevTools

### Processo e aprendizado

- [ ] **Evolução do meta.json para DSL** — se surgir um padrão claro entre peças, formalizar o `meta.json` como linguagem de configuração para geração semi-automática de cenas
- [ ] **Comparação de abordagens** — mesma frase emocional implementada com libs diferentes para comparar ergonomia, performance e resultado visual
- [ ] **Colaboração** — permitir que outras pessoas submetam frases e/ou peças via PR

### Infra e CI

- [ ] **Revisitar estratégia de deploy** — avaliar GitHub Pages vs Vercel/Netlify conforme o número de peças cresce
- [ ] **CI no Skill Forge** — pipeline que roda validação de estrutura, gera thumbnails e faz deploy da galeria automaticamente
- [ ] **Testes visuais** — snapshot testing das peças para detectar regressões visuais acidentais

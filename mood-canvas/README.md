# Mood Canvas

Mood Canvas is an interactive visual arts project where each piece is born from an emotional phrase. The goal is to translate feeling into experience — visual, sonic — while exploring real software engineering concepts, architecture, and frontend ecosystem tools.

The goal is not just to display something beautiful, but to translate a feeling into a visual and interactive experience.

## 🎯 Objective

Learn and experiment creating visual art using Three.js or other visual frameworks. AI generates the artwork based on an emotional prompt. A complete piece combines the emotional phrase and visual effects rendered together on the same screen.

---

## 🎨 Artistic Concepts

### Emotion → Visual Mapping

> "Each emotion defines rules of visual behavior."

Each emotion translates into a set of visual behaviors — not just colors, but motion, rhythm, and weight.

| Emotion | Behavior |
|---|---|
| `grief` | slow, fade, repetition, cold tones |
| `anxiety` | jitter, tremor, fast loops |
| `joy` | expansion, warm colors, light movement |
| `nostalgia` | blur, fade, delay |

### 🌫️ Atmosphere System

A scene is not just visual — it has a climate.

- Color palette
- Lighting and shadow
- Visual density
- Contrast and saturation

### ⏳ Temporal Behavior

Time is a first-class element in every piece.

- Things appear slowly
- They disappear
- They repeat
- They accelerate or decelerate

> "I don't draw — I define how the system behaves."

---

## 🧱 Technical Layer

### 🤖 Prompt as DSL

> The prompt is not just text — it is a configuration language.

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

This enables:

- Standardization across pieces
- Automatic scene generation
- AI integration
- Separation between intent and implementation

> "The user describes feeling — the system interprets behavior."

### 🧩 Piece as Isolated Unit

Each piece of art is a fully independent unit — no shared state, no global dependencies. Each folder is self-contained and can be run on its own.

---

## Project Standards

### Folder Structure

Each visual piece lives in its own folder directly inside `mood-canvas/`:

```
mood-canvas/
└── {type}--{art-name}--{lib}--{framework}/
    ├── index.html
    ├── meta.json
    └── LEARNINGS.md
```

### Folder Naming Convention

Pattern: `{type}--{art-name}--{lib}--{framework}`

Each segment uses kebab-case. Double dashes separate segments to avoid ambiguity, since art names may themselves contain hyphens.

| Segment | Examples |
|---|---|
| `type` | `scene`, `particle`, `shader`, `interactive` |
| `art-name` | `ocean-breathing`, `inner-fire`, `falling-thoughts` |
| `lib` | `threejs`, `p5js`, `canvas2d`, `pixijs`, `vanilla` |
| `framework` | `react`, `vanilla`, `svelte` |

**Example:** `particle--falling-thoughts--threejs--react`

> When no visual library or framework is used, both segments are `vanilla`.
> **Example:** `scene--is-war-as-old-as-gravity--vanilla--vanilla`

### Branch naming

Each piece is developed on its own branch:

```
feat/mood-canvas/{art-name}
```

### Each piece must contain

- `index.html` — the piece itself
- `meta.json` — metadata (emotion, intensity, motion, visual, text, etc.)
- `LEARNINGS.md` — what was explored and learned

---

## Pieces

- **Is War as Old as Gravity** — [view](https://victormachadogp.github.io/skill-forge/mood-canvas/scene--is-war-as-old-as-gravity--vanilla--vanilla/) *(vanilla)*

---

## Backlog

Ideas and evolutions that may make sense as the project grows. Nothing here is a priority — these are possible directions, not commitments.

### Gallery and presentation

- [ ] **Web gallery** — an index page listing all pieces with a preview (screenshot or GIF) and a link to open each one
- [ ] **Automatic deploy** — each piece published via GitHub Pages or similar, accessible by a direct URL
- [ ] **Automatic thumbnails** — a script that opens each piece in a headless browser, takes a screenshot, and saves it as a preview

### Tooling and automation

- [ ] **Scaffolding CLI** — a command that creates the structure of a new piece (folder, `meta.json`, `LEARNINGS.md`, base file) from a template
- [ ] **Structure validation** — a lint that checks whether each piece has `meta.json`, `LEARNINGS.md`, and follows the naming convention
- [ ] **Piece catalog** — a JSON automatically generated from each piece's `meta.json`, serving as the project index

### Technical evolution

- [ ] **Shaders as focus** — a series of pieces dedicated to learning GLSL/WebGL shaders from scratch
- [ ] **Responsiveness as constraint** — pieces that work well on mobile, exploring touch events and device orientation
- [ ] **Performance budgets** — define FPS and memory limits per piece and measure with DevTools

### Process and learning

- [ ] **Evolving meta.json into DSL** — if a clear pattern emerges across pieces, formalize `meta.json` as a configuration language for semi-automatic scene generation
- [ ] **Approach comparison** — the same emotional phrase implemented with different libs to compare ergonomics, performance, and visual output
- [ ] **Collaboration** — allow other people to submit phrases and/or pieces via PR

### Infra and CI

- [ ] **Revisit deploy strategy** — evaluate GitHub Pages vs Vercel/Netlify as the number of pieces grows
- [ ] **CI on Skill Forge** — pipeline that runs structure validation, generates thumbnails, and deploys the gallery automatically
- [ ] **Visual tests** — snapshot testing of pieces to detect accidental visual regressions

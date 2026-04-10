# Mood Canvas

Mood Canvas is an interactive visual arts project where each piece is built from an emotional phrase.

The goal is not just to display something beautiful, but to translate a feeling into a visual and interactive experience.

## 🎯 Objective

Learn and experiment creating visual art using Three.js or other visual frameworks. AI generates the artwork based on an emotional prompt. A complete piece combines the emotional phrase and visual effects rendered together on the same screen.

---

## 🎨 Artistic Concepts

### Emotion → Visual Mapping

> "Each emotion defines rules of visual behavior."

Every emotion maps to a set of visual behaviors — not just colors, but motion, rhythm, and weight.

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

> `grief finds me again` → visual repetition as emotional recurrence

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

Each piece of art is a fully independent unit.

```
pieces/{type}--{name}--{lib}--{framework}/
```

No shared state, no global dependencies. Each folder is self-contained and can be run on its own.

---

## Project Standards

### Folder Structure

Each visual piece lives in its own folder inside `pieces/`:

```
mood-canvas/
└── pieces/
    └── {type}--{art-name}--{lib}--{framework}/
```

### Folder Naming Convention

Pattern: `{type}--{art-name}--{lib}--{framework}`

Each segment uses kebab-case. Double dashes separate segments to avoid ambiguity, since art names may themselves contain hyphens.

| Segment | Examples |
|---|---|
| `type` | `scene`, `particle`, `shader`, `interactive` |
| `art-name` | `ocean-breathing`, `inner-fire`, `falling-thoughts` |
| `lib` | `threejs`, `p5js`, `canvas2d`, `pixijs` |
| `framework` | `react`, `vanilla`, `svelte` |

**Example:** `particle--falling-thoughts--threejs--react`

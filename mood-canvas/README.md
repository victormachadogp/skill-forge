# Mood Canvas

Mood Canvas is an interactive visual arts project where each piece is built from an emotional phrase.

The goal is not just to display something beautiful, but to translate a feeling into a visual and interactive experience.

## 🎯 Objective

Learn and experiment creating visual art using Three.js or other visual frameworks. AI generates the artwork based on an emotional prompt. A complete piece combines the emotional phrase and visual effects rendered together on the same screen.

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

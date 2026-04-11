# Mood Canvas

Mood Canvas is an interactive visual arts project where each piece is born from an emotional phrase. The goal is to translate feeling into experience — visual, sonic — while exploring real software engineering concepts, architecture, and frontend ecosystem tools.

The goal is not just to display something beautiful, but to translate a feeling into a visual and interactive experience.

## Why this project exists

I learn best by building things I care about. Instead of todo-lists and generic CRUDs, each piece in this project is a pretext to explore a new technical concept — whether it's an architecture pattern, a lib I've never used, or a different rendering approach.

Art is the vehicle. Engineering is the destination.

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

### Each piece is an isolated unit

No shared state, no global dependencies. Each folder is self-contained and can be run on its own. This is intentional: it allows experimenting with completely different stacks between pieces without conflict.

### meta.json and LEARNINGS.md

Each piece includes these two files. The format and what to write in each is documented in the "How to create a new piece" section below.

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

## How to create a new piece

### The prompt

Every piece starts from three ingredients. The first two are required:

1. **The phrase** — an emotional phrase that carries an idea, not just a feeling. "Is war as old as gravity?" works better than "war is sad" because it has a concept inside (inevitability) that guides the mechanic.
2. **The visual reference** — an image, screenshot, named aesthetic, or real object that defines the visual universe. This is what prevents the AI from inventing generic shapes. Examples: Windows XP alert screenshot, TV static photo, military radar aesthetic, VHS with lost tracking, MSN Messenger chat screen.
3. **Technical direction** _(optional)_ — a specific lib or technique you want to explore. If not specified, the AI picks something different from the last piece.

Prompt template:

```
Phrase: "[your phrase]"
Reference: [describe the aesthetic or attach image]
Technique (optional): [lib or concept you want to explore]
```

Real examples:

```
Phrase: "Is war as old as gravity?"
Reference: [Windows XP alert screenshot]
→ Result: XP dialog that won't close, scales into a bug, BSOD, infinite loop
```

```
Phrase: "The silence after someone leaves a room"
Reference: MSN Messenger chat screen with contact offline
Technique: I want to experiment with pure CSS, no canvas
```

```
Phrase: "I keep rebuilding what I keep burning down"
Reference: DOS terminal aesthetic with blinking cursor
Technique: Canvas 2D
```

### The core principle

**The interaction mechanic must embody the phrase.** If the phrase is about inevitability, the system must be inevitable (clicking "OK" makes it worse). If it's about loss, something must disappear and not come back. If it's about repetition, the system must loop. Interaction is not decoration — it's the metaphor.

### Files for each piece

Every piece produces three files inside `pieces/{type}--{name}--{lib}--{framework}/`:

**`index.html`** (or framework entry point)
- Complete and self-contained code, ready to run by opening the file
- The phrase visually integrated into the composition (not just thrown on top with a generic position absolute)
- No local dependencies — external libs via CDN

**`meta.json`** — piece record, not generation config.
```json
{
  "name": "Piece Name",
  "phrase": "The full phrase",
  "emotion": "primary emotion",
  "date": "YYYY-MM-DD",
  "lib": "threejs | vanilla | p5js | ...",
  "framework": "vanilla | react | svelte | ...",
  "techniques": ["list of techniques used"],
  "learned": ["short list of what was learned"],
  "atmosphere": {
    "palette": "palette description",
    "movement": "how things move",
    "density": "how much is on screen"
  }
}
```

**`LEARNINGS.md`** — what I learned building this. Structure:
```markdown
# Learnings: Piece Name

## Technical focus
One line saying what this piece explored.

## What I learned
Technical concepts organized by topic. Not a tutorial —
it's a record of concrete discoveries with examples from the code.

## What I'd do differently
What I'd improve if I did it again.

## References
Useful links that helped or that go deeper on the topic.
```

---

## Guide for the AI

This section is directed at the AI that will help create new pieces.

### Context

You are helping create interactive visual art. Each piece is an emotional experience translated into code. The author is learning, so each piece should be an opportunity to explore something new technically.

### What you receive

A phrase + visual reference + optionally technical direction (see "How to create a new piece" section above).

### What you deliver

The three files (`index.html`, `meta.json`, `LEARNINGS.md`) following the formats described above.

### Principles

- **The mechanic embodies the phrase.** The user's interaction must reinforce what the phrase says. Ask: "what happens when the user clicks/moves/waits, and does it reflect the emotion?"
- **Visual reference as anchor.** Don't invent aesthetics from scratch. Recreate a real aesthetic (system UI, analog media, known interface) and subvert it with the phrase's emotion.
- **Don't generate complex shapes procedurally.** If the piece needs a specific symbol or shape, ask for an SVG or PNG as input. Generating mathematical coordinates for shapes you can't see results in something unrecognizable.
- **Technical variety.** Don't repeat the same stack between consecutive pieces.
- **The phrase is part of the composition.** It must be visually integrated — in the right context, with the right typography, reacting to the piece's state when it makes sense.
- **High visual quality.** Attention to detail: animation easing, cohesive palette, balanced visual density.
- **Code as learning.** Prioritize clarity. Comment non-obvious decisions. Highlight interesting techniques in LEARNINGS.md.

### What to avoid

- Inventing complex shapes/symbols with mathematical functions — the result will be unrecognizable
- Phrase thrown with `position: absolute; top/bottom: X%` without integration with the scene
- Particles or random effects unrelated to the emotion
- Interactions that don't reinforce the phrase's metaphor
- Generic "technical demo" or "tutorial example" aesthetic

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

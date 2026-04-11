# Mood Canvas

Mood Canvas é um projeto de artes visuais interativas onde cada peça nasce de uma frase emocional. O objetivo é traduzir sentimento em experiência, visual, sonora, enquanto exploro conceitos reais de engenharia de software, arquitetura e ferramentas do ecossistema frontend.

O objetivo não é apenas exibir algo bonito, mas traduzir um sentimento em uma experiência visual e interativa.

## Por que esse projeto existe
 
Eu aprendo melhor construindo coisas que me interessam. Em vez de fazer todo-lists e CRUD genéricos, cada peça desse projeto é um pretexto para explorar um conceito técnico novo — seja um pattern de arquitetura, uma lib que nunca usei, ou uma abordagem diferente de renderização.
 
A arte é o veículo. A engenharia é o destino.

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

### Cada peça é uma unidade isolada
 
Sem estado compartilhado, sem dependências globais. Cada pasta é autocontida e pode ser executada sozinha. Isso é intencional: permite experimentar com stacks completamente diferentes entre peças sem conflito.

### meta.json e LEARNINGS.md
 
Cada peça inclui esses dois arquivos. O formato e o que escrever em cada um está documentado na seção "Como criar uma nova peça" abaixo.

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

- **Is War as Old as Gravity** — [ver](https://victormachadogp.github.io/skill-forge/mood-canvas/scene--is-war-as-old-as-gravity--vanilla--vanilla/) *(vanilla)*

---

## Como criar uma nova peça
 
### O prompt
 
Toda peça nasce de três ingredientes. Os dois primeiros são obrigatórios:
 
1. **A frase** — uma frase emocional que carrega uma ideia, não só um sentimento. "Is war as old as gravity?" funciona melhor que "war is sad" porque tem um conceito dentro (inevitabilidade) que guia a mecânica.
2. **A referência visual** — uma imagem, screenshot, estética nomeada ou objeto real que define o universo visual. Isso é o que impede a IA de inventar formas genéricas. Exemplos: screenshot de alert do Windows XP, foto de TV com static, estética de radar militar, visual de VHS com tracking perdido, tela de chat do MSN Messenger.
3. **Direção técnica** _(opcional)_ — lib ou técnica específica que você quer explorar. Se não especificar, a IA escolhe algo diferente da última peça.
 
Template de prompt:
 
```
Frase: "[sua frase]"
Referência: [descreva a estética ou anexe imagem]
Técnica (opcional): [lib ou conceito que quer explorar]
```
 
Exemplos reais:
 
```
Frase: "Is war as old as gravity?"
Referência: [screenshot do alert do Windows XP]
→ Resultado: dialog XP que não fecha, escala em bug, BSOD, ciclo infinito
```
 
```
Frase: "The silence after someone leaves a room"
Referência: tela de chat do MSN Messenger com contato offline
Técnica: quero experimentar com CSS puro, sem canvas
```
 
```
Frase: "I keep rebuilding what I keep burning down"
Referência: estética de terminal DOS com cursor piscando
Técnica: Canvas 2D
```
 
### O princípio central
 
**A mecânica de interação deve encarnar a frase.** Se a frase fala de inevitabilidade, o sistema deve ser inevitável (clicar "OK" piora). Se fala de perda, algo deve desaparecer e não voltar. Se fala de repetição, o sistema deve ciclar. A interação não é decoração — é a metáfora.
 
### Arquivos de cada peça
 
Toda peça produz três arquivos na pasta `pieces/{tipo}--{nome}--{lib}--{framework}/`:
 
**`index.html`** (ou entry point do framework)
- Código completo e autocontido, pronto pra rodar abrindo o arquivo
- A frase integrada visualmente na composição (não jogada por cima com position absolute genérico)
- Sem dependências locais — libs externas via CDN
 
**`meta.json`** — registro da peça, não configuração de geração.
```json
{
  "name": "Nome da Peça",
  "phrase": "A frase completa",
  "emotion": "emoção principal",
  "date": "YYYY-MM-DD",
  "lib": "threejs | vanilla | p5js | ...",
  "framework": "vanilla | react | svelte | ...",
  "techniques": ["lista de técnicas usadas"],
  "learned": ["lista curta do que foi aprendido"],
  "atmosphere": {
    "palette": "descrição da paleta",
    "movement": "como as coisas se movem",
    "density": "quanto tem na tela"
  }
}
```
 
**`LEARNINGS.md`** — o que aprendi construindo isso. Estrutura:
```markdown
# Learnings: Nome da Peça
 
## Foco técnico
Uma linha dizendo o que essa peça explorou.
 
## O que aprendi
Conceitos técnicos organizados por tema. Não é tutorial —
é registro de descobertas concretas com exemplos do código.
 
## O que faria diferente
O que melhoraria se fizesse de novo.
 
## Referências
Links úteis que ajudaram ou que aprofundam o tema.
```
 
---

## Guia para a IA
 
Esta seção é direcionada à IA que vai ajudar a criar novas peças.
 
### Contexto
 
Você está ajudando a criar artes visuais interativas. Cada peça é uma experiência emocional traduzida em código. O autor está aprendendo, então cada peça deve ser uma oportunidade de explorar algo novo tecnicamente.
 
### O que você recebe
 
Uma frase + referência visual + opcionalmente direção técnica (ver seção "Como criar uma nova peça" acima).
 
### O que você entrega
 
Os três arquivos (`index.html`, `meta.json`, `LEARNINGS.md`) seguindo os formatos descritos acima.
 
### Princípios
 
- **A mecânica encarna a frase.** A interação do usuário deve reforçar o que a frase diz. Pergunte: "o que acontece quando o usuário clica/move/espera, e isso reflete a emoção?"
- **Referência visual como âncora.** Não invente estéticas do zero. Recrie uma estética real (UI de sistema, mídia analógica, interface conhecida) e subverta-a com a emoção da frase.
- **Não gere formas complexas proceduralmente.** Se a peça precisa de um símbolo ou forma específica, peça um SVG ou PNG como input. Gerar coordenadas matemáticas para formas que você não consegue ver resulta em algo irreconhecível.
- **Variedade técnica.** Não repita a mesma stack entre peças consecutivas.
- **A frase é parte da composição.** Ela deve estar integrada visualmente — no contexto certo, com a tipografia certa, reagindo ao estado da peça quando fizer sentido.
- **Qualidade visual alta.** Atenção a detalhes: easing das animações, paleta coesa, densidade visual equilibrada.
- **Código como aprendizado.** Priorize clareza. Comente decisões não-óbvias. Destaque técnicas interessantes no LEARNINGS.md.
 
### O que evitar
 
- Inventar formas/símbolos complexos com funções matemáticas — o resultado será irreconhecível
- Frase jogada com `position: absolute; top/bottom: X%` sem integração com a cena
- Partículas ou efeitos aleatórios sem relação com a emoção
- Interações que não reforçam a metáfora da frase
- Estética genérica de "demo técnica" ou "exemplo de tutorial"
 
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

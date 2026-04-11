# Learnings: Is War as Old as Gravity? (XP Alert)

## Foco técnico
Recriação pixel-art de UI real (Windows XP) com CSS puro, sistema de estado escalável baseado em interação do usuário, e efeitos de glitch usando apenas DOM + CSS.

## O que aprendi

### CSS como ferramenta de pixel art
- Gradientes lineares empilhados recriam a estética XP com precisão surpreendente — a titlebar azul, o botão Start verde, os botões com borda 3D
- `box-shadow` com `inset` simula as bordas chanfradas que dão o visual "3D" do Windows clássico
- A taskbar, o tray com relógio, o botão Start — tudo é CSS puro, sem imagens

### Estado escalável como narrativa
- O `bugLevel` funciona como uma state machine implícita: cada faixa de nível muda o comportamento dos cliques
- Níveis baixos: o dialog treme e spawna um novo (incômodo leve)
- Níveis médios: cascade de dialogs com filtros CSS (corrupt, invert, redshift)
- Nível crítico: BSOD como clímax narrativo
- Essa escalação cria uma curva emocional — o usuário começa achando engraçado e termina sobrecarregado

### Glitch sem canvas
- Barras de glitch são só `div`s com cor, `mix-blend-mode: screen` e remoção por timeout
- Screen tear é um gradiente translúcido com `translateX` para simular deslocamento horizontal
- `clipPath: inset()` nos dialogs simula corrupção de renderização
- `filter: hue-rotate()` + `saturate()` + `sepia()` empilhados criam distorção cromática convincente

### BSOD como recurso narrativo
- O BSOD não é só easter egg — é o ponto onde o sistema "quebra" sob o peso da pergunta
- O flicker antes de estabilizar (alternando display none/block) vende a sensação de crash real
- O restart limpa tudo e recomeça com o dialog original — o ciclo se repete, como a frase sugere

## O que faria diferente
- Adicionar som: o "ding" do Windows XP no primeiro dialog, e sons de erro cada vez mais distorcidos conforme o bug level sobe
- Implementar drag nos dialogs para que o usuário possa tentar organizá-los (e falhar)
- O BSOD poderia ter um "memory dump" animado que conta uma história em vez de texto estático

## Referências
- [Windows XP UI reference](https://guidebookgallery.org/screenshots/winxp)
- [CSS-only Windows XP](https://botoxparty.github.io/XP.css/)

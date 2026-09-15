# Changelog

## 1.3 — compatibilidade iOS e publicação

- Removidos `color-mix()`, `inset`, `clamp()` sem fallback; guardas em `localStorage`; bloqueio de zoom por gesto; faixa de erro na tela.
- Pacote `dist/neon-breakout-itch.zip` e instruções para itch.io.
- Documentação completa em `docs/`.

## 1.2 — arquivo único e desempenho

- Desktop e mobile no mesmo `index.html`, com detecção automática e troca de layout por `data-mode`.
- Render reescrito: sprites pré-renderizados com glow, fundo em textura, canvas opaco, sem `shadowBlur` por frame.
- Qualidade adaptativa em 3 tiers (DPR e partículas) baseada no tempo de frame.
- Teste AABB antes da colisão circular; teto de textos flutuantes.
- Medido com ~115 blocos em emulação DPR 3: p95 de 12,2 ms para 6,4 ms.

## 1.1 — mobile

- Versão touch separada (`mobile.html`, depois fundida na 1.2): arraste relativo, botões de habilidade na base, freio por toque segurado, safe areas, vibração, pausa automática ao trocar de aba.

## 1.0 — habilidades e visual

- Barra de energia com 3 segmentos carregada por pontos.
- Pulso (1), Plasma (2), Overdrive (3) e freio temporal.
- Blocos destruídos por habilidade não carregam energia nem sobem nível.
- Layout em dois painéis, tipografia Orbitron + Rajdhani, HUD e overlays em DOM.

## 0.1 — protótipo (`v1.html`)

- Núcleo do Breakout com muro descendo, linha de morte, combo ×8, raquete que encolhe, blocos blindados, áudio sintetizado, fundo synthwave em canvas.
- Calibração do muro de 16 + 5·nível para 6 + 2·nível px/s após testes automatizados.

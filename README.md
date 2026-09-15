# Neon Breakout

Recriação do Breakout (Atari, 1976) em estilo synthwave, com uma regra nova: o muro de blocos desce sem parar e a bola precisa acompanhar o ritmo. Um único arquivo HTML, sem dependências, roda em desktop e celular direto no navegador.

![Neon Breakout](docs/img/desktop.png)

## Jogar

- Abra `index.html` no navegador, ou publique a pasta em qualquer host estático (GitHub Pages, itch.io, Netlify).
- O jogo detecta o dispositivo e escolhe o layout: teclado e mouse no desktop, toque no celular. Para forçar: `index.html?desktop` ou `index.html?mobile`.

| Ação | Desktop | Mobile |
|---|---|---|
| Mover raquete | mouse, ← → ou A D | arrastar o dedo em qualquer ponto do campo |
| Lançar / iniciar | espaço ou clique | toque |
| Pulso · Plasma · Overdrive | 1 · 2 · 3 (ou Q · E · R) | botões na base |
| Freio temporal | segurar Shift ou botão direito | segurar FREIO |
| Pausa · som | P · M | botão II |

## Regras em uma frase cada

- Perde vida se a bola cai ou se um bloco cruza a linha tracejada acima da raquete.
- Cada vida perdida encolhe a raquete em 20 % (mínimo 50 px, de 120).
- Blocos rebatidos em sequência, sem tocar a raquete, multiplicam pontos até ×8.
- Pontos carregam a barra de energia (3 segmentos). Energia paga Pulso (1), Plasma (2), Overdrive (3) e o freio temporal.
- A cada 15 blocos destruídos pela bola sobe um nível: o muro desce mais rápido, a bola acelera 5 %, aparecem blocos blindados.

## Documentação

| Arquivo | Conteúdo |
|---|---|
| [docs/game-design.md](docs/game-design.md) | Conceito, pilares, sistemas, economia de energia, decisões de design e o que foi descartado |
| [docs/technical.md](docs/technical.md) | Arquitetura do arquivo, loop, física, render por sprites, qualidade adaptativa, entrada, detecção de dispositivo |
| [docs/visual-identity.md](docs/visual-identity.md) | Paleta, tipografia, layout, motion, som sintetizado |
| [docs/balancing.md](docs/balancing.md) | Todos os números ajustáveis, onde ficam no código e o que cada um muda |
| [docs/compatibility.md](docs/compatibility.md) | Navegadores, iOS Safari, desempenho em 90 Hz, publicação no itch.io |
| [CHANGELOG.md](CHANGELOG.md) | Histórico das versões |

## Estrutura

```
index.html      jogo completo (HTML + CSS + JS, ~46 KB)
v1.html         primeira versão, sem habilidades, só para referência histórica
docs/           documentação
dist/           pacote pronto para itch.io (zip com index.html)
```

## Desenvolvimento

Não há build. Edite `index.html` e recarregue. Para testar no celular na mesma rede:

```
python -m http.server 8080
# no celular: http://<ip-do-pc>:8080/
```

No console do navegador, `__G` expõe o estado do jogo, `__Q` a qualidade atual e `__useSkill('pulse'|'plasma'|'overdrive')` dispara habilidades. Útil para testar sem jogar.

## Licença

MIT. Veja [LICENSE](LICENSE).

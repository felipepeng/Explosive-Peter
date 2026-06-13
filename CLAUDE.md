# CLAUDE.md

Guia para o Claude Code (e qualquer agente) trabalhar neste projeto.

## O que é

**Explosive Peter** — uma página web interativa de **arquivo único** (`index.html`).
O boneco **Pedro** fica no centro com um cronômetro de 10s; quando zera, a sorte decide
o destino dele e o caos toma conta da tela.

- **Live:** https://felipepeng.github.io/Explosive-Peter/
- **Repo:** https://github.com/felipepeng/Explosive-Peter

## Stack e princípios

- HTML + CSS + JavaScript **puro**, tudo dentro de `index.html`. **Sem dependências, sem build, sem npm.**
- Personagens (Pedro, Vinícius, JP, CRIPTÆON) são desenhados **inteiramente em CSS** (divs), nunca imagens.
- Efeitos visuais (partículas, poeira, estrelas, ondas de choque) usam `<canvas>` + `requestAnimationFrame`.
- Tremores e animações de personagem usam **keyframes CSS**.
- Todo o JS fica num **IIFE** dentro de um único `<script>` no fim do arquivo.

> Regra de ouro: **manter tudo em `index.html`.** Não adicionar arquivos JS/CSS externos
> nem ferramentas de build sem o usuário pedir explicitamente.

## Como rodar / testar

Basta abrir `index.html` no navegador:

```bash
start index.html      # Windows
```

Não há testes automatizados — a validação é visual no navegador.

## Fluxo do jogo (`decide()`)

Aos 0s, `Math.random()` ramifica em cinco caminhos com a **mesma chance (20% cada)**:

| Chance | Função | Resultado |
|---|---|---|
| 20% | `saveByVinicius()` | Vinícius, o Estoico, assume a bomba (sub-twist: ~55% dud / ~45% explode nele, mas ele fica imóvel). Falas bem espaçadas; termina com botão de reiniciar (`#stoic-restart`). |
| 20% | `dudThenJP()` | A bomba falha; JP from the South chega pela esquerda e elimina Pedro a tiro. |
| 20% | `michaEvent()` | Começa a chover, o pavio apaga e **Micha dos Mares** (estética Steve/Minecraft) emerge, fala, arremessa o tridente e um raio fulmina Pedro. |
| 20% | `grandBattle()` | **Guerra de todos contra todos** (tema de luta anime: speed lines, auras de ki, palavras de impacto mangá, fundo dramático): JP e Michas vêm pela morte do Pedro, Vinícius se junta a ele; no auge do choque desce **Felipe, o Rei Labubu**, que congela a luta e **reseta o universo** → tela final "Universo Puro" (todos amigos, amanhecer épico). |
| 20% | `explode()` | Explosão completa → redireciona pro cenário galáctico do **CRIPTÆON**. |

- **CRIPTÆON** só aparece no caminho da explosão. Pergunta sobre vida/verdade/universo → responde `42`; senão, um aforismo aleatório.
- **JP** leva a uma tela de eliminação própria (faroeste), **não** ao CRIPTÆON.
- **Micha dos Mares** tem 5 fases (chuva → chegada andando → fala → arremesso do tridente + raio → tela final própria em azul/verde/dourado com confete de diamante).
- **Felipe, o Rei Labubu** (orelhas pontudas, dentinhos serrilhados, coroa — tudo em CSS via `.lb-*`) só aparece no caminho da guerra (`grandBattle`). Inimigos (`#jp`, `#michas`) entram com `.battle` pela esquerda; aliados (`#vinicius.battle`) à direita, ao lado do Pedro — posições bem espaçadas para não sobrepor. As falas são **sequenciais e espaçadas** (uma de cada vez, com tempo de leitura). A luta usa `#animefx` (speed lines), `.fighting`/`.ki` (auras de ki por personagem), `impactWord()` (palavras de impacto) e `body.battle-bg` (fundo dramático). Felipe desce (`#felipe.descend`), tudo recebe `.frozen`, um clarão dourado (`#pureflash`) cobre a tela e abre o `#pure-end` — fileira que **reaproveita as figuras CSS** de todos, com confete de corações.

## Estrutura interna do `<script>`

- Refs aos elementos do DOM + `resize()`.
- Countdown via `setInterval` (`tick`) que chama `decide()` quando o tempo zera.
- Sistema de partículas: `spawnExplosion`, `spawnDust`, `shockwave`, `animate`, `ensureLoop`.
- `rainDebris(qtd)` — detritos caindo.
- Galáxia: `enterGalaxy`, `initStars`, `startStars`, `animStars`, `divine(q)`, arrays `APHORISMS` e `STOIC`.
- Funções de desfecho por personagem (`saveByVinicius`, `dudThenJP`, `jpFinishes`, `explode`).
- Micha dos Mares: chuva (`startRain`/`stopRain`/`rainTick`), `michaEvent` (fases 1-3), `michaThrow` (fase 4), `lightningStrike` + `drawBolt`, `michaFinal` + `pixelConfetti` (fase 5).
- Guerra final (anime): `impactWord` (palavra de impacto mangá), `grandBattle` (chegada + falas espaçadas), `battleClash` (speed lines, auras de ki, palavras de impacto), `felipeDescends` (Rei Labubu desce, tudo congela), `universeReset` (clarão + troca de tela), `enterPure` + `heartsConfetti` (tela "Universo Puro").

## Camadas (z-index) — referência rápida

dust(45) · animefx/speed-lines(46) · rain(47) · flash(40) · shock(48) · partículas fx(50) · vinicius(52) · jp(53) ·
michas(54) · cracks(55) · fly-trident(56) · bolt/raio(57) · felipe(58) · impact-word(59) · destroyed(60) · quote(62) ·
eliminated(70) · micha-end(72) · pureflash(78) · pure-end(79) · galaxy(80) · corações do reset(81)

## Convenções

- O usuário se comunica em **português (PT-BR)**; responda em português.
- Ambiente **Windows / PowerShell**; atenção a avisos de CRLF/LF no git (inofensivos).
- Commits são feitos como **Peng / felipepeng**.
- Ao mexer em posicionamento de personagens, lembrar que `#jp` e `#vinicius` são `fixed`
  e ficam **fora** do `#scene` — por isso o tremor (`shake`) é aplicado só no `#scene`,
  deixando o estoico imóvel enquanto o mundo treme.

# 💣 Explosive Peter

Uma página interativa de arquivo único (`index.html`) — sem dependências, sem build, sem nada pra instalar. É só abrir no navegador.

O **Pedro** está no centro da tela com um cronômetro regressivo. Quando o tempo acaba, o destino dele é decidido na sorte… e o caos começa.

## ▶️ Como rodar

Abra o `index.html` no navegador. Pelo terminal:

```bash
# Windows
start index.html

# macOS
open index.html

# Linux
xdg-open index.html
```

> 💡 Dá pra hospedar grátis no **GitHub Pages** (*Settings → Pages → Branch: `main` → `/root`*) e jogar direto pelo link.

## 🎬 O que acontece

1. **Contagem regressiva (10s)** — nos últimos 3 segundos o número fica vermelho, a tela começa a tremer e um pavio 🧨 aparece no Pedro.
2. **Aos 0 segundos, a sorte decide:**

| Resultado | Chance | O que rola |
|---|---|---|
| 💥 **Pedro explode** | **60%** | Explosão completa: partículas, poeira, ondas de choque e um terremoto que despedaça o site. |
| 🗿 **Vinícius salva** | **40%** | O rival estoico surge e assume a bomba. |

## 🗿 Vinícius, o Estoico

O maior rival do Pedro. Imperturbável. Quando ele aparece, **não solta a bomba na hora** — segura na própria mão numa mini-contagem 3‑2‑1, sem piscar. Aí vem o *twist*:

- **~55%** — a bomba **falha** (dud). Pedro salvo, Vinícius nem reage.
- **~45%** — a bomba **explode nele**. O mundo inteiro treme… **mas o Vinícius, não.** Sai coberto de fuligem, intacto, e solta uma frase estoica enquanto o Pedro entra em pânico.

## 🪙 CRIPTÆON, o Ser-Criptomoeda

O ser mais poderoso do universo. **Só aparece quando o Pedro explode.**

Após a destruição, a tela é puxada para um cenário galáctico — campo de estrelas, uma moeda dourada girando em 3D e pulsando energia. Ali, o Pedro transcendido pode fazer **uma pergunta sobre a vida, a verdade e o universo**:

- Perguntas sobre sentido / vida / universo / verdade → a resposta é o clássico **`42`** (homenagem ao *Guia do Mochileiro das Galáxias*).
- Qualquer outra pergunta → um dos aforismos cripto‑filosóficos do Ser.

## 🛠️ Detalhes técnicos

- **Stack:** HTML + CSS + JavaScript puro, tudo em um arquivo só.
- **Personagens:** desenhados inteiramente em CSS (sem imagens).
- **Efeitos:** partículas, poeira/fumaça, estrelas e ondas de choque renderizados em `<canvas>`; tremores e animações em CSS.

---

*Feito por diversão. Coitado do Pedro.* 😬

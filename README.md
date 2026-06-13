# 💣 Explosive Peter

### 🎮 [**Jogar agora →**](https://felipepeng.github.io/Explosive-Peter/)

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

> 💡 Também já está no ar via **GitHub Pages**: **https://felipepeng.github.io/Explosive-Peter/**

## 🎬 O que acontece

1. **Contagem regressiva (10s)** — nos últimos 3 segundos o número fica vermelho, a tela começa a tremer e um pavio 🧨 aparece no Pedro.
2. **Aos 0 segundos, a sorte decide:**

| Resultado | Chance | O que rola |
|---|---|---|
| 🗿 **Vinícius salva** | **40%** | O rival estoico surge e assume a bomba. |
| 🤠 **A bomba falha + JP** | **30%** | O pavio apaga… mas JP from the South chega pra terminar o serviço. |
| 💥 **Pedro explode** | **30%** | Explosão completa: partículas, poeira, ondas de choque e um terremoto que despedaça o site. |

## 🗿 Vinícius, o Estoico

O maior rival do Pedro. Imperturbável. Quando ele aparece, **não solta a bomba na hora** — segura na própria mão numa mini-contagem 3‑2‑1, sem piscar. Aí vem o *twist*:

- **~55%** — a bomba **falha** (dud). Pedro salvo, Vinícius nem reage.
- **~45%** — a bomba **explode nele**. O mundo inteiro treme… **mas o Vinícius, não.** Sai coberto de fuligem, intacto, e solta uma frase estoica enquanto o Pedro entra em pânico.

## 🤠 JP from the South

Quando a bomba **falha**, o Pedro acha que escapou… mas pouco depois um pistoleiro se aproxima do Sul. **JP from the South** — cowboy magro de chapéu de aba larga, bigode e poncho listrado — entra pela esquerda e declara:

> *"Vim em busca do último Mantuani."*

Então saca o **revólver** (desenhado em CSS, com clarão de disparo, coice e fumaça), dá o tiro — e o Pedro tomba com os olhos em **✕ ✕**. Fim de linha para o último Mantuani.

> ⚠️ Como nesse caminho a bomba **não** explode, ele leva a uma tela de eliminação faroeste própria — e **não** ao CRIPTÆON.

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

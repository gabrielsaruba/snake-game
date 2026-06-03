# 🐍 Snake Game — Projeto Educacional

Projeto desenvolvido como exercício prático de lógica de programação, utilizando **Python via Brython** (Python rodando diretamente no navegador), HTML5 Canvas e CSS3.

---

## 📁 Estrutura do Projeto snake-game/
├── v1-simplificado/
│   └── index.html          # Versão inicial — foco na lógica base
├── v2-chaos-edition/
│   └── index.html          # Versão avançada — UI completa + efeitos
├── docs/
│   └── decisoes-tecnicas.md  # Documentação das escolhas do projeto
└── README.md

---

## 🎮 Versões

### V1 — Versão Simplificada
- Cobra se move em grid 27×27
- 4 tipos de maçã com efeitos diferentes
- Timer de 7 segundos por maçã
- Controles: `WASD` ou setas do teclado

### V2 — Chaos Edition ✨
- Interface estilo cyberpunk (fontes Orbitron + Rajdhani)
- Barra de tempo animada (verde → amarelo → vermelho)
- Maçãs com gradiente radial + glow
- Cobra com bordas arredondadas e fade de cor
- Sistema de recorde salvo na sessão
- Game Over sem `alert()` nativo

---

## 🍎 Tipos de Maçã

| Maçã | Cor | Pontos | Efeito |
|------|-----|--------|--------|
| 🔴 Normal | Vermelha | +1 | Nenhum |
| 🟡 Turbo | Dourada | +2 | Velocidade dobrada por 5s |
| 🔵 Giga | Azul | +4 | Bônus de pontos |
| 🟢 Hacker | Verde Neon | +1 | Remove efeitos + corta o rabo |

---

## 🛠️ Tecnologias

| Tecnologia | Uso |
|------------|-----|
| **Python 3** (via Brython) | Lógica do jogo inteira |
| **HTML5 Canvas API** | Renderização dos gráficos |
| **CSS3** | Layout, animações e temas |

---

## ▶️ Como Executar

Abra o arquivo `index.html` da versão desejada em qualquer navegador moderno. Não precisa instalar nada.

---

## 📈 Evolução entre as Versões

| Aspecto | V1 | V2 |
|---------|----|----|
| Interface | Básica | Cyberpunk com glow |
| Game Over | `alert()` nativo | Overlay customizado |
| Maçã | Quadrado colorido | Círculo com gradiente |
| Cobra | Retângulo simples | Bordas arredondadas + fade |
| Recorde | Não tem | Salvo na sessão |
| Timer | Número de texto | Barra animada |
| Bug inversão | Presente | Corrigido |

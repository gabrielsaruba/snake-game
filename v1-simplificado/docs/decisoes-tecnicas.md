# Decisões Técnicas

## Por que Brython?

O Brython permite escrever Python puro no navegador, sem precisar de servidor ou instalação. Isso facilita rodar o projeto diretamente abrindo o `.html`, ideal para fins educacionais.

---

## Estrutura de Loop do Jogo

O jogo usa `timer.set_interval()` (equivalente ao `setInterval` do JavaScript) para criar o loop principal. A cada tick:

1. A direção atual é aplicada à cabeça da cobra
2. Colisões são verificadas (parede e corpo)
3. Se comeu a maçã, aplica o efeito e gera uma nova
4. Se não comeu, remove o último segmento do rabo
5. O canvas é redesenhado do zero

```python
# Padrão de loop usado na V2
timer_id = timer.set_interval(loop, VEL_NORMAL)  # 130ms por tick
```

---

## Sistema de Direção com Buffer

Na V2, foi implementado um buffer de direção (`proxima_direcao`) separado da direção atual (`direcao`). Isso evita o bug clássico onde pressionar duas teclas rapidamente no mesmo frame faz a cobra se morder.

```python
# Entrada do teclado só altera proxima_direcao
proxima_direcao = [0, -1]

# O loop aplica no início de cada tick
direcao = proxima_direcao[:]
```

---

## Renderização no Canvas

Na V2, cada frame redesenha o canvas inteiro:

1. **Fundo** — retângulo escuro + grid de linhas sutis
2. **Maçã** — círculo com `createRadialGradient` + `shadowBlur` para glow
3. **Cobra** — segmentos com `quadraticCurveTo` para cantos arredondados, cor com fade proporcional ao índice

---

## Correção de Bug (V1 → V2)

Na V1, a linha de inversão de controles tinha erro de sintaxe Python:
```python
# ERRADO (V1)
cima, baixo, esquerda, direita = baixo, cima, direita, whistles = esquerda
```
```python
# CORRETO (V2)
if direcao[1] != 1: proxima_direcao = [0, -1]
```

---

## Timers Simultâneos

A V2 roda **dois timers em paralelo**:

| Timer | Intervalo | Função |
|-------|-----------|--------|
| `timer_id` | 130ms (normal) / 55ms (turbo) | Loop principal do jogo |
| `timer_barra_id` | 100ms | Atualiza barra de tempo da maçã |

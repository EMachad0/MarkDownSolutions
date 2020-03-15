# Super Feijoes

Polycarp acabou de resolver o problema URI 2791 - Feijão, um problema classico da maratona de programação, no entanto Polycarp nao ficou satisfeito com a dificuldade do problema, e entao teve a seguinte ideia, e se os copos fossem trocados de lugar?

Dados os quatro copos, a posiçao inicial do feijão  e a lista de copos trocados, responda, aonde esta o feijão?

### Entrada :
Na primeira linha seguirão quatro inteiros, $C1$, $C2$, $C3$ e $C4$ separados por um espaço. O valor $Ci=1$ indica que o feijão estava no copo na posição $i$, e $Ci=0$ indica que o $i$-ésimo copo esta vazio. 

Em seguida, segue um numero $N$, o numero de trocas realizadas. As proximas $N, N \le 10^5$ linhas contem dois inteiros $i, j$, $1 \le i, j \le 4$ representando que o  $i$-ésimo copo foi trocado de lugar com o  $j$-ésimo copo.
Haverá sempre exatamente um copo com o feijão.

### Saida
Baseando-se nas trocas feitas, imprima um numero $i$, indicando que ao final das trocas o feijão esta no  $i$-ésimo copo.

Haverá sempre exatamente um copo com o feijão.

| Exemplo de entrada | Exemplo de entrada |
|--|--|
| 0 0 0 1 | 1 |
| 7 |
| 4 3 |
| 3 3 |
| 3 2 |
| 3 2 |
| 1 2 |
| 2 3 |
| 1 2 |

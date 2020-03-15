# Super Feijoes

Polycarp é fã de shows de mágica, ele já foi em tantos que conhece todos os truques. Porém ele sempre se perde quando o mágico resolve fazer o truque dos feijões, no qual ele coloca um feijão embaixo de um dos quatro copos e os embaralha para perguntar à plateia onde o feijão foi parar. 

Por isso ela resolveu pedir sua ajuda pra criar um programa que dado a posição inicial do feijão e todas as trocas realizadas, diga em qual copo o feijão está no final do truque.

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

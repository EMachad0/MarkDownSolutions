 # Solução Xadrez Aleatório

<details>
<br>

Devemos imprimir a quantidade de estados válidos, observe que um estado difere de outro baseado na posição do rei e torres, assim, ignorando os peões, a quantidade de estados validos é a quantidade de maneiras diferentes que podemos posicionar o rei e as torres, dito isso, vamos começar dividimos o problema em 3 casos:
- **Nenhuma torre**:
	Nesse caso, apenas podemos colocar o rei em uma posição qualquer, como temos $N$ posições, teremos $N$ estados válidos.
- **Uma torre**:
	Nesse caso, colocando o rei em uma posição qualquer, teremos $N-1$ posições para a torre, assim a quantidade de estados validos é $$N * (N-1)$$.
	Observe que $N * N-1 = \frac{N!}{(N-2)!} =  A^{N}_{2}$, ou seja, para casos assim, basta o arranjo da quantidade de espaços pela quantidade de peças. (Importante para o terceiro caso).
- **Duas torres**:
	Nesse caso, poderiamos continuar a ideia do caso anterior e supor que a quantidade de estados é $A^{N}_{3}$, no entanto temos a restrição que o rei deve estar entre as duas torre.
	Escolheremos uma das permutações possiveis dentro do $A^{N}_{3}$, por exemplo $a, b, c$ tal que  $0 \le a, b, c < N$, observe que $a, b, c$ não estão nescessariamente em ordem, no entanto escolheremos o menor e o maior valor para serem colocadas as torres e o outro valor será colocado o rei, assim, satisfazemos a condição.
	No entanto o que difere a permutação acima de $a, c, b$? absolutamente nada, o maior e o menor número, que são os mesmos, ainda serão torres e o outro número o rei. (observe que as duas permutações são validas e diferentes dentro do arranjo devido a ordem diferente dos fatores). 
	Portanto, basta eliminarmos as permutações nos quais os números se repetem, o que é feito pela combinação.
	Logo o número de casos possiveis é $C^{N}_{3} = \frac{N!}{3! * (N-3)!} = \frac{N * (N-1) * (N-2)}{6}$.

### Código:

<details>
<summary>C++</summary>
<br>
	
``` C++
#include <bits/stdc++.h>
using namespace std;

#define ll long long

int main() {
    ll n, t;
    cin >> n >> t;

    if (t == 0) cout << n << endl;
    else if (t == 1) cout << n * (n-1) << endl;
    else if (t == 2) cout << (n * (n-1) * (n-2))/6 << endl;
}
```

</details>

</details>


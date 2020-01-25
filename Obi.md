 # Solução Xadrez Aleatório

<details>
<br>

Devemos imprimir a quantidade de estados válidos, observe que um estado difere de outro baseado na posição do rei e torres, assim, ignorando os peões, a quantidade de estados validos é a quantidade de maneiras diferentes que podemos posicionar o rei e as torres, dito isso, vamos começar dividimos o problema em 3 casos:
- **Nenhuma torre**:
	Nesse caso, apenas podemos colocar o rei em uma posição qualquer, como temos <img src="/tex/f9c4988898e7f532b9f826a75014ed3c.svg?invert_in_darkmode&sanitize=true" align=middle width=14.99998994999999pt height=22.465723500000017pt/> posições, teremos <img src="/tex/f9c4988898e7f532b9f826a75014ed3c.svg?invert_in_darkmode&sanitize=true" align=middle width=14.99998994999999pt height=22.465723500000017pt/> estados válidos.
- **Uma torre**:
	Nesse caso, colocando o rei em uma posição qualquer, teremos <img src="/tex/e35caf405a5e9b4afd75a0d338c4dc12.svg?invert_in_darkmode&sanitize=true" align=middle width=43.31036984999999pt height=22.465723500000017pt/> posições para a torre, assim a quantidade de estados validos é <p align="center"><img src="/tex/6c4153591263d16bf1a8694e05d2c5e4.svg?invert_in_darkmode&sanitize=true" align=middle width=86.62073805pt height=16.438356pt/></p>.
	Observe que <img src="/tex/d289bde2b2c3cb2780f6e35a7e373cc4.svg?invert_in_darkmode&sanitize=true" align=middle width=188.05890014999997pt height=28.92634470000001pt/>, ou seja, para casos assim, basta o arranjo da quantidade de espaços pela quantidade de peças. (Importante para o terceiro caso).
- **Duas torres**:
	Nesse caso, poderiamos continuar a ideia do caso anterior e supor que a quantidade de estados é <img src="/tex/7aa64964a527ae5da6a95a0d52d8c3d3.svg?invert_in_darkmode&sanitize=true" align=middle width=23.974960349999986pt height=27.6567522pt/>, no entanto temos a restrição que o rei deve estar entre as duas torre.
	Escolheremos uma das permutações possiveis dentro do <img src="/tex/7aa64964a527ae5da6a95a0d52d8c3d3.svg?invert_in_darkmode&sanitize=true" align=middle width=23.974960349999986pt height=27.6567522pt/>, por exemplo <img src="/tex/c7511ce56cd9c8457f7a29917f39df8d.svg?invert_in_darkmode&sanitize=true" align=middle width=37.46952164999999pt height=22.831056599999986pt/> tal que  <img src="/tex/a0df3e69d81102c043d9e2195f1242e2.svg?invert_in_darkmode&sanitize=true" align=middle width=104.52398219999998pt height=22.831056599999986pt/>, observe que <img src="/tex/c7511ce56cd9c8457f7a29917f39df8d.svg?invert_in_darkmode&sanitize=true" align=middle width=37.46952164999999pt height=22.831056599999986pt/> não estão nescessariamente em ordem, no entanto escolheremos o menor e o maior valor para serem colocadas as torres e o outro valor será colocado o rei, assim, satisfazemos a condição.
	No entanto o que difere a permutação acima de <img src="/tex/e3a0397c492933cfe6ce5a1d9dc585db.svg?invert_in_darkmode&sanitize=true" align=middle width=37.46952164999999pt height=22.831056599999986pt/>? absolutamente nada, o maior e o menor número, que são os mesmos, ainda serão torres e o outro número o rei. (observe que as duas permutações são validas e diferentes dentro do arranjo devido a ordem diferente dos fatores). 
	Portanto, basta eliminarmos as permutações nos quais os números se repetem, o que é feito pela combinação.
	Logo o número de casos possiveis é <img src="/tex/c9b1b58e3ec66037be0f2879e47a7432.svg?invert_in_darkmode&sanitize=true" align=middle width=237.23312414999998pt height=33.20539859999999pt/>.

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


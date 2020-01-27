Prova:
https://olimpiada.ic.unicamp.br/static/extras/obi2019/provas/ProvaOBI2019_f3pu.pdf

# Solução Xadrez Aleatório

<details>
<br>

Devemos imprimir a quantidade de estados válidos, observe que um estado difere de outro baseado na posição do rei e torres, assim, ignorando os peões, a quantidade de estados validos é a quantidade de maneiras diferentes que podemos posicionar o rei e as torres, dito isso, vamos começar dividimos o problema em 3 casos:

- **Nenhuma torre**:

	Nesse caso, apenas podemos colocar o rei em uma posição qualquer, como temos $N$ posições, teremos $N$ estados válidos.
	
- **Uma torre**:

	Nesse caso, colocando o rei em uma posição qualquer, teremos $N-1$ posições para a torre, assim a quantidade de estados validos é $N * (N-1)$.
	
	Observe que $N * (N-1) = \frac{N!}{(N-2)!} =  A^{N}_{2}$, ou seja, para casos assim, basta o arranjo da quantidade de espaços pela quantidade de peças. (Importante para o terceiro caso).
	
- **Duas torres**:

	Nesse caso, poderiamos continuar a ideia do caso anterior e supor que a quantidade de estados é $A^{N}_{3}$, no entanto temos a restrição que o rei deve estar entre as duas torres.
	
	Escolheremos uma das permutações possiveis dentro do $A^{N}_{3}$, por exemplo $a, b, c$ tal que  $0 \le a, b, c < N$, observe que $a, b, c$ não estão necessariamente em ordem, no entanto escolheremos o menor e o maior valor para serem colocadas as torres e o outro valor será colocado o rei, assim, satisfazemos a condição.
	
	
 	 No entanto, se escolhermos qualquer permutação dos valores {$a, b, c$}, por exemplo {$a, c, b$}, obteremos os mesmos restultados, o menor e o maior valor serão as torres e o outro valor será o rei, assim, estamos contando o mesmo estado válido diversas vezes.
 	 
	Portanto, basta eliminarmos as permutações nos quais os números se repetem, como são 3 peças, temos $3! = 6$ permutações repetidas de cada permutação possivel, basta então dividir o arranjo por 6.
	
	Logo o número de casos possiveis é $\frac{A^{N}_{3}}{6} = \frac{N!}{6 * (N-3)!} = \frac{N * (N-1) * (N-2)}{6}$.

	Note que $\frac{A^{N}_{3}}{6} = C^{N}_{3}$, pois a combinação tem o papel de tirar as permutações repetidas do arranjo.

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
<details>
<summary>Python3</summary>
<br>

``` python
n, t = map(int, input().split())

if t == 0:
	print(n)
else if t == 1:
	print(n * (n-1))
else if t == 2:
	print((n * (n-1) * (n-2))/6)
```

</details>

</details>

#  Solução Mesa Redonda

<details>
<br>

Começando pela Ana:

Para resolver basta notarmos que, com 3 cadeiras, a cada 3 cadeiras ela da uma volta e volta para posição 0, ou seja, a cadeira a qual ela vai sentar será $A \% 3$.

Para Beatriz a ideia é a mesma, ela sentara na cadeira $B \% 3$, a menos que a cadeira ja esteja ocupada, nesse caso, sentara na cadeira $(B+1) \% 3$.

Assim, o resultado é o valor diferente dos dois.

### Código:

<details>
<summary>Python3</summary>
<br>

``` python
a = int(input())  
b = int(input())  
  
a %= 3  
b = (b+1)%3 if b%3 == a else b%3  
  
for i in range(3):  
   if a != i != b:  
      print(i)
```

</details>


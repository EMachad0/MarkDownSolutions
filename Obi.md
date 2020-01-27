Prova:
https://olimpiada.ic.unicamp.br/static/extras/obi2019/provas/ProvaOBI2019_f3pu.pdf

# Solução Xadrez Aleatório

<details>
<br>

Devemos imprimir a quantidade de estados válidos, observe que um estado difere de outro baseado na posição do rei e torres, assim, ignorando os peões, a quantidade de estados validos é a quantidade de maneiras diferentes que podemos posicionar o rei e as torres, dito isso, vamos começar dividimos o problema em 3 casos:

- **Nenhuma torre**:

	Nesse caso, apenas podemos colocar o rei em uma posição qualquer, como temos <img src="/tex/f9c4988898e7f532b9f826a75014ed3c.svg?invert_in_darkmode&sanitize=true" align=middle width=14.99998994999999pt height=22.465723500000017pt/> posições, teremos <img src="/tex/f9c4988898e7f532b9f826a75014ed3c.svg?invert_in_darkmode&sanitize=true" align=middle width=14.99998994999999pt height=22.465723500000017pt/> estados válidos.
	
- **Uma torre**:

	Nesse caso, colocando o rei em uma posição qualquer, teremos <img src="/tex/e35caf405a5e9b4afd75a0d338c4dc12.svg?invert_in_darkmode&sanitize=true" align=middle width=43.31036984999999pt height=22.465723500000017pt/> posições para a torre, assim a quantidade de estados validos é <img src="/tex/87499f70deb8975cc8badca4a42f3ae5.svg?invert_in_darkmode&sanitize=true" align=middle width=86.62073804999999pt height=24.65753399999998pt/>.
	
	Observe que <img src="/tex/301c6d035d65cf6cf11f43746b34896d.svg?invert_in_darkmode&sanitize=true" align=middle width=200.8443327pt height=28.92634470000001pt/>, ou seja, para casos assim, basta o arranjo da quantidade de espaços pela quantidade de peças. (Importante para o terceiro caso).
	
- **Duas torres**:

	Nesse caso, poderiamos continuar a ideia do caso anterior e supor que a quantidade de estados é <img src="/tex/7aa64964a527ae5da6a95a0d52d8c3d3.svg?invert_in_darkmode&sanitize=true" align=middle width=23.974960349999986pt height=27.6567522pt/>, no entanto temos a restrição que o rei deve estar entre as duas torres.
	
	Escolheremos uma das permutações possiveis dentro do <img src="/tex/7aa64964a527ae5da6a95a0d52d8c3d3.svg?invert_in_darkmode&sanitize=true" align=middle width=23.974960349999986pt height=27.6567522pt/>, por exemplo <img src="/tex/c7511ce56cd9c8457f7a29917f39df8d.svg?invert_in_darkmode&sanitize=true" align=middle width=37.46952164999999pt height=22.831056599999986pt/> tal que  <img src="/tex/a0df3e69d81102c043d9e2195f1242e2.svg?invert_in_darkmode&sanitize=true" align=middle width=104.52398219999998pt height=22.831056599999986pt/>, observe que <img src="/tex/c7511ce56cd9c8457f7a29917f39df8d.svg?invert_in_darkmode&sanitize=true" align=middle width=37.46952164999999pt height=22.831056599999986pt/> não estão necessariamente em ordem, no entanto escolheremos o menor e o maior valor para serem colocadas as torres e o outro valor será colocado o rei, assim, satisfazemos a condição.
	
	
 	 No entanto, se escolhermos qualquer permutação dos valores {<img src="/tex/c7511ce56cd9c8457f7a29917f39df8d.svg?invert_in_darkmode&sanitize=true" align=middle width=37.46952164999999pt height=22.831056599999986pt/>}, por exemplo {<img src="/tex/e3a0397c492933cfe6ce5a1d9dc585db.svg?invert_in_darkmode&sanitize=true" align=middle width=37.46952164999999pt height=22.831056599999986pt/>}, obteremos os mesmos restultados, o menor e o maior valor serão as torres e o outro valor será o rei, assim, estamos contando o mesmo estado válido diversas vezes.
 	 
	Portanto, basta eliminarmos as permutações nos quais os números se repetem, como são 3 peças, temos <img src="/tex/85913a56dd00b08a2a4c65184b3d106f.svg?invert_in_darkmode&sanitize=true" align=middle width=42.92227334999999pt height=22.831056599999986pt/> permutações repetidas de cada permutação possivel, basta então dividir o arranjo por 6.
	
	Logo o número de casos possiveis é <img src="/tex/8e180176df5d47ca52e86d8f8c9aaac2.svg?invert_in_darkmode&sanitize=true" align=middle width=230.5368813pt height=37.92139230000001pt/>.

	Note que <img src="/tex/4831d697d5774b209c2ea98e7921a804.svg?invert_in_darkmode&sanitize=true" align=middle width=68.90635784999999pt height=37.92139230000001pt/>, pois a combinação tem o papel de tirar as permutações repetidas do arranjo.

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

Para resolver basta notarmos que, com 3 cadeiras, a cada 3 cadeiras ela da uma volta e volta para posição 0, ou seja, a cadeira a qual ela vai sentar será <img src="/tex/a204ed0a7c28aada4c044c6ffe6d92f5.svg?invert_in_darkmode&sanitize=true" align=middle width=34.24668059999999pt height=24.65753399999998pt/>.

Para Beatriz a ideia é a mesma, ela sentara na cadeira <img src="/tex/e7d9b8078b41d41936a28d376454b1c5.svg?invert_in_darkmode&sanitize=true" align=middle width=35.211285449999984pt height=24.65753399999998pt/>, a menos que a cadeira ja esteja ocupada, nesse caso, sentara na cadeira <img src="/tex/e10baf53a81ae0da1438688465be87c6.svg?invert_in_darkmode&sanitize=true" align=middle width=76.30711934999998pt height=24.65753399999998pt/>.

Assim, o resultado é o valor diferente dos dois.

### Código:

<details>
<summary>Python3</summary>
<br>

```
a = int(input())  
b = int(input())  
  
a %= 3  
b = (b+1)%3 if b%3 == a else b%3  
  
for i in range(3):  
   if a != i != b:  
      print(i)
```

</details>


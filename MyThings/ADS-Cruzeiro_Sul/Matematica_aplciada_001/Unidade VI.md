
# Matrizes e Sistemas Lineares

Define-se por Matriz de m × n a um conjunto de m × n (lê-se m por n) elementos que são dispostos em m linhas e n colunas. Os elementos da matriz são localizados pelos dois índices: i (linha) e j (coluna).

### Elementos das Diagonais

#### Diagonal principal (P)
Chamamos de Diagonal Principal (P) a diagonal da matriz quadrada composta pelos elementos aij, onde i = j, isto é, no caso de uma matriz quadrada de ordem 3, a diagonal principal será composta pelos elementos de posição: a11, a22 e a33.

#### Diagonal secundária (S)
Já a Diagonal Secundária (S) é a diagonal composta pelos elementos aij, onde i + j = n + 1; no caso da matriz quadrada de ordem 3, a diagonal secundária será composta pelos elementos a31, a22 e a13

![[Pasted image 20240820185201.png]]

## Classificação de Matrizes

As matrizes são classificadas de acordo com o número de linhas e colunas. 

• Matriz linha: quando temos uma matriz m = 1, composta por uma única linha; 

• Matriz coluna: quando temos uma matriz n = 1, composta por uma única coluna; 

• Matriz nula: quando temos uma matriz cujos elementos são todos iguais a zero; 

• Matriz quadrada: trata-se da matriz m × n, na qual m = n, ou seja, igual número de linhas e colunas. Importante destacar que em toda matriz m × n quadrada temos duas diagonais que são chamadas: diagonal principal e diagonal secundária; 

• Matriz triangular superior: quando temos uma matriz quadrada n × n, na qual todos os elementos a seguir da diagonal principal são nulos.

## Operações Básicas com Matrizes

#### Soma e Subtração de Matrizes

Considerando duas matrizes A = (aij) mxn e B = (bij) mxn, a matriz C = (cij) mxn será a matriz soma, das matrizes A + B, na qual os elementos cij serão obtidos por cij = aij + bij.

Cada elemento cij da matriz soma C será o resultado da soma entre os elementos correspondentes de A e B. Chamamos de correspondentes os termos que possuírem os mesmos índices ij.

![[Pasted image 20240820185612.png]]
A soma ou subtração de matrizes somente ocorre entre matrizes de mesma ordem, ou seja, o número de linhas de uma matriz deve ser igual ao número de linhas da outra matriz, assim como o número de colunas.

#### Multiplicação de Matrizes

Dadas duas matrizes A = (aij) mxn e B = (bij) mxn, a multiplicação entre as matrizes A e B gerará uma nova matriz C na qual: Todo elemento cij é calculado multiplicando-se ordenadamente os elementos da linha i, da matriz A, pelos elementos da coluna j, da matriz B, e somando-se os produtos obtidos.

Só definimos o produto AB de duas matrizes quando o número de colunas da matriz A for igual ao número de linhas de B. Além disso, notamos que a matriz produto AB possui o número de linhas de A e o número de colunas de B.

![[Pasted image 20240820190038.png]]


## Determinantes de Matrizes Quadradas até Ordem 3

Uma matriz quadrada tem, associado a ela, um número real chamado determinante da matriz (Det), obtido por meio de operações que envolvem os elementos da matriz.

#### Determinante de Matriz Quadrada de Ordem 1

Para matriz quadrada de ordem 1, indicada por A = [a11] , por definição, o determinante da matriz será igual ao número do elemento de posição a11.

#### Determinante da Matriz Quadrada de Ordem 2

Para as matrizes quadradas de ordem 2, calculamos o determinante fazendo o produto dos elementos da diagonal principal menos o produto dos elementos da diagonal secundária.

![[Pasted image 20240820190628.png]]
P = produto da diagonal principal: 2x4 = 8 
S = produto da diagonal secundária 3x1 = 3 
P – S = 8 – 3 = 5. Logo, det(M) = 5

#### Determinante da Matriz Quadrada de Ordem N = 3

REGRA DE SARRUS, consiste em copiar as duas primeiras colunas da matriz original, e incluindo, após a terceira coluna, novamente as duas primeiras colunas
![[Pasted image 20240820190924.png]]

![[Pasted image 20240820190937.png]]

A seguir, somamos os produtos obtidos nas três diagonais principais e dessa soma subtrairemos a soma dos três produtos obtidos nas três diagonais secundárias.

![[Pasted image 20240820191012.png]]

Das diagonais principais (P), temos: 0 – 4 + 20 = 16. 
Das diagonais secundárias (S), temos: 0 – 8 – 3 = -11.
16 – (-11) = 16 + 11 = 27 
Det(A) = 27

## Sistemas Lineares

![[Pasted image 20240820191405.png]]

#### Método de Cramer
Considere o sistema a seguir: 
2x + 1y = 3 
1x – 3y = -2

![[Pasted image 20240820191851.png]]
A seguir, calcularemos os determinantes das matrizes chamados de: det A, det Ax e det Ay
Para calcular det Ax , basta trocar os elementos da primeira coluna da matriz A (que correspondem aos coeficientes de x), pelos elementos que compõem a matriz B. 
Da mesma forma, para calcular o valor do det Ay , basta trocar os elementos da segunda coluna da A (que correspondem aos coeficientes de y) pelos elementos que compõem a coluna da matriz B, como vemos na figura a seguir:

![[Pasted image 20240820191957.png]]
![[Pasted image 20240820192019.png]]
![[Pasted image 20240820192039.png]]
Portanto, a solução de nosso sistema será x = 1 e y = 1.

Se tivermos um sistema cuja matriz seja quadrada de ordem três, resolveremos det A , det Ax , det Ay e det Az que deverão ser calculados conforme vimos na Regra de Sarrus e os valores de x, y e z será, respectivamente:

![[Pasted image 20240820192109.png]]

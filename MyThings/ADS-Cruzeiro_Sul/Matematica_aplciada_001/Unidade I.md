
## Conjuntos e Intervalos Reais

#### Conjunto
Na matemática, chamamos de conjunto uma abstração para expressar uma delimitação (ou agrupamento) de objetos ou elementos. Dessa forma, um conjunto pode ser uma coleção de objetos quaisquer, inclusive outros conjuntos.
Dentre as formas de representação para indicar um conjunto, apresentamos inicialmente um par de chaves { , }. Para deixar clara a ideia de conjunto, usamos as chaves e, normalmente, o nome do conjunto é indicado por uma letra maiúscula. 
A = { v, x, z }, 
B = { 0, 1, 2, 4 }

Um elemento pode ou não “pertencer” a um determinado conjunto, e para a relação de pertencimento utilizamos o símbolo ∈ (pertence) ou ∉ (não pertence).
u ∈ A 
v ∉ A

Um conjunto pode ser formado por elementos, mas também tratamos da relação entre dois ou mais conjuntos. E, quando tratamos de um conjunto a respeito de um outro conjunto, dizemos que este está contido (usamos o símbolo ⊂) ou não está contido (nesse caso o símbolo ⊄).

Exemplo: o conjunto A das vogais A { a, e, i, o , u } está contido no conjunto B das letras do alfabeto B { a, b, c, d, e, f, g, h, ..., z }, então temos que A ⊂ B. Também podemos dizer que o conjunto A é um subconjunto de B.

Dentre os diversos tipos de conjuntos, descreveremos, nesta disciplina, os conjuntos matemáticos mais usados, que são:
- N − Naturais  
	- N = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12 ... }
- Z − Inteiros 
	- Z = {. . . , −5, −4, −3, −2, −1, 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, ....}
- Q − Racionais 
	- é composto por qualquer número que possa ser escrito como a divisão de dois números inteiros a e b, sendo que b deve, necessariamente, ser diferente de zero.
	- Porém, existem números como 2 , 5 e π dentre outros, que não são possíveis de serem escritos na forma fracionária a/b. Eles possuem infinitos dígitos e não formam períodos, são chamados de números irracionais. Importante destacar que os irracionais não pertencem ao conjunto dos racionais.
- R − Reais 
	- conjunto de todos os números racionais e do conjunto dos irracionais.
- C − Complexos
	- formado a partir a unidade imaginária i, a qual, por definição, temos que raíz quadrade de  -1 =  i, logo, a partir dessa definição, temos o complexo que pode ser escrito como a + bi.


### Representação dos Conjuntos

Representação pela citação: 
A = { 2, 4, 6, 8, 10, 12 }; B = { 1, 2, 3, 4, 5 }, 

Representação por uma propriedade comum: 
A = {x ∈ N|2 ≤ x ≤ 12 e x é par}; B = {x ∈ N|1 ≤ x < 6}

Representação por diagramas

### Subconjuntos
Na teoria dos conjuntos, temos que para cada conjunto existe uma coleção de conjuntos que contém entre seus elementos todos os subconjuntos do conjunto dado.
Com isso, temos uma nova relação, agora não mais entre elemento e conjunto, mas entre conjuntos, a chamada de Relação de Inclusão.

### Cardinalidade
Considerando um conjunto qualquer A, temos que o número de elementos de A, que chamamos de cardinalidade, é representada por #A ou n(A) ou ainda |A|. Exemplo: O conjunto D dos números primos entre 6 e 20 tem sua cardinalidade igual a 5, representada por #D ou n ( D ) ou |D| = 5, já que o conjunto em questão é formado por D = {7, 11, 13, 17 e 19}.
Importante destacar que a cardinalidade do conjunto vazio { } é 1, ou seja, # { } = 1, pois consideramos que dentro de qualquer conjunto vazio existe um outro conjunto vazio, ou seja, o conjunto vazio { } é um subconjunto de qualquer outro conjunto. 
Já a cardinalidade dos conjuntos numéricos N, Z, Q, R e C é infinita, logo: 
#N = #Z = #Q = #R = #C = ∞ 
Temos ainda que: se o conjunto tem um só elemento, ele é chamado de unitário, se tem dois elementos, é binário etc. 
Se um conjunto é a referência para a formação dos demais, ele é chamado de **conjunto Universo.**

### Operações entre conjuntos

**Igualdade:** Dois conjuntos A e B são iguais quando todo elemento de A pertence a B e, reciprocamente, todo elemento de B pertence a A. 

**União:** A União de dois conjuntos A e B é dada por: A ∪ B = {x|x ∈ A ou x ∈ B}, podemos utilizar a letra v no lugar de ou assim temos A ∪ B = {x|x ∈ A v x ∈ B}.

**Intersecção:** A intersecção entre os conjuntos A e B será um novo conjunto dado pelos elementos que existem concomitantemente nestes dois conjuntos, isto é, que estão nos dois conjuntos ao mesmo tempo. A ∩ B = {x|x ∈ A e x ∈ B} ou (trocando e por ∧) A ∩ B = {x|x ∈ A ∧ x ∈ B} 

**Diferença:** A diferença entre os conjuntos A e B será um novo conjunto formado pelos elementos que existem no conjunto A, mas não estão no conjunto B.

**Complementar:** chama-se complementar de B em relação a A, o conjunto de elementos de A que não pertence a B

**Produto Cartesiano:** Dados dois conjuntos A e B, o Produto Cartesiano é formado por todos os pares ordenados (x,y) formados com um primeiro elemento de A e com o segundo elemento de B. 
A × B = {( x, y ) | x ∈ A e y ∈ B} 
Exemplo: considere os seguintes conjuntos: X = {1, 2, 3} e Y = {a, b}. 
O produto cartesiano entre eles é dado por: 
X × Y = {(1, a), (1, b), (2, a), (2, b), (3, a), (3, b)} e 
Y × X = {(a, 1), (a, 2), (a, 3), (b, 1), (b, 2), (b, 3)} 

X × ∅ = ∅ 
Y × ∅ = ∅ 

## Propriedades das Operações entre Conjuntos

#### União 
1. A ∪ ∅ = A , ou seja, a união de qualquer conjunto com o conjunto vazio será o próprio conjunto. 
2. Comutatividade de A ∪ B = B ∪ A , a união é comutativa, ou seja, A ∪ B é igual a B ∪ A. 
3. Independência de A ∪ A = A , a união de um conjunto com ele próprio resulta no próprio conjunto. 
4. Associatividade de (A ∪ B) ∪ C = A ∪ (B ∪ C) , ao realizar a união entre mais de dois conjuntos, podemos associá-los de diferentes formas que o resultado será o mesmo. 
5. A ⊂ B se e somente se A ∪ B = B , neste caso, A somente pode estar contido em B se a união entre eles é o próprio B.

#### Intersecção 
1. A ∩ ∅ = ∅ , a intersecção entre um conjunto qualquer com o conjunto vazio será o conjunto vazio. O vazio é um subconjunto de qualquer outro conjunto.  
2. Comutatividade A ∩ B = B ∩ A , a intersecção é comutativa, ou seja, a ordem dos conjuntos para a realização da intersecção não altera o resultado da mesma. 
3. Independência A ∩ A = A, a intersecção de um conjunto com ele mesmo resulta no próprio conjunto. 
4. Associatividade (A ∩ B) ∩ C = A ∩ (B ∩ C), ao realizar a intersecção entre mais de dois conjuntos, podemos associá-los de diferentes formas que o resultado será o mesmo. 
5. A ⊂ B se e somente se A ∩ B = A, neste caso, se o conjunto A está contido no conjunto B , então a intersecção de A com B será o conjunto A. 

A propriedade comutativa vale tanto para a União como para a Intersecção, mas não vale para a Diferença entre dois conjuntos e para o produto cartesiano, assim como a propriedade de Associatividade não se aplica para a Diferença e o Produto Cartesiano.

#### Propriedades Distributivas 
Sejam A, B e C conjuntos quaisquer. 
1. Distributiva da União perante a Intersecção 
	1. A ∪ (B ∩ C) = (A ∪ B) ∩ (A ∪ C) 
	
2. Distributiva da Intersecção perante a União 
	1. A ∩ (B ∪ C) = (A ∩ B) ∪ (A ∩ C) E

## Intervalos Reais

Veremos os subconjuntos dos números reais que são chamados de Intervalos Reais. Os intervalos reais podem ser fechados, abertos ou mistos. Nesta unidade, veremos a composição de cada um dos tipos desses intervalos e as principais operações entre intervalos.

#### Intervalo Fechado 
O intervalo fechado [a, b] com extremidades a e b é aquele que possui todos os elementos entre as extremidades e inclusive elas. 
É indicado pelos colchetes: [ para iniciar e ] para fechar. [a, b] = {x ∈ R| a ≤ x ≤ b} 
Exemplo: A = [2, 5]

#### Intervalo Aberto 
O intervalo aberto (a, b) com extremidades a e b e aquele que possui todos os elementos entre as extremidades, exceto elas próprias. 
E indicado pelos parênteses: (para iniciar e) para fechar. Ou ainda os colchetes em ordem inversa. (a, b) = {x ∈ |R| a < x < b}
Exemplo: B = ( 2, 5 ) também pode ser descrito como B = ] 2, 5 [

#### Intervalo Misto 
São intervalos que possuem uma das extremidades aberta e a outra fechada. 
Lembrando que quando está aberta a extremidade não pertence ao intervalo, somente delimita o intervalo, e quando está fechada pertence. 
Exemplos: C = (2, 5] ou ainda C = ] 2, 5]

As desigualdades < e ≤ estão diretamente ligadas ao fato de o intervalo ser aberto ou fechado, pois ≤ inclui a extremidade, já < não inclui a extremidade.

Temos também intervalos nos quais definimos apenas uma das extremidades: (a,+ ∞) = {x ∈ R | x > a} Neste caso, o intervalo é aberto em a, ou seja, não inclui o número a.

#### Operações entre Intervalos Reais

**União entre intervalos**

União de Intervalos Exemplo: [4, 9] ∪ [6, 12] = [ 4, 12]
O intervalo A = [ 4,9] em união com o intervalo B = [ 6, 12] resulta em um outro intervalo que agrupa elementos de ambos, portanto: A U B= [ 4, 12] ou ainda: A U B = { x ∈ R | 4 ≤ x ≤ 12}

**Intersecção entre Intervalos **

Exemplo: [4, 9] ∩ [6, 12] = [6, 9]
A – B = [6 , 9] ou ainda { x ∈ R | 6 ≤ x ≤ 9


**Diferença entre Intervalos**

Exemplo: [4, 9] − [6, 12] = [4, 6) 
Do intervalo A [ 4, 9] deveremos retirar o que também é comum ao intervalo B. Ou seja: de A retiramos o intervalo B.
Como resultado, temos [ 4, 6) ou ainda { x ∈ R | 4 ≤ x < 6} , ou seja, do intervalo A [ 4, 9 ] foi removida a parte que era comum de A com o intervalo B [ 6, 12].
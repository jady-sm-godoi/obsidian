
# Relações e Funções



Em qualquer área da Matemática, as relações e, principalmente, as funções desempenham papel muito importante. Intuitivamente, uma função é uma máquina que transforma um objeto de entrada num novo objeto de saída, sendo que a maneira como ocorre essa transformação é a sua finalidade, isto é, finalidade e função estão intimamente associadas.

Uma função transforma um objeto de entrada em outro objeto, que é chamado de saída.
Descrever a função é descrever a transformação ou a regra de transformação.

toda função é feita a partir de uma relação, mas nem toda relação estabelece uma função.

### Relação

Dados dois conjuntos quaisquer A e B, uma relação de A em B é qualquer subconjunto do produto cartesiano A x B

Sejam os conjuntos A = {1, 2, 3, 4} e B = {1 , 2} Faremos uma relação de A para B de forma que cada elemento de A irá se relacionar com todos os elementos de B, formando todos os pares ordenados possíveis (a, b), ou seja: de A para B. 
Logo, o produto cartesiano será dado por: 
A x B = {(1,1) (1,2) (2,1), (2,2), (3,1), (3,2), (4,1), (4,2)}
![[Pasted image 20240809142620.png]]

![[Pasted image 20240809142724.png]]

Na representação A x B por gráfico, utilizamos o eixo das abscissas (eixo x) para representar os elementos do conjunto de partida e o eixo das ordenadas (eixo y) para representar os elementos do conjunto de chegada.

a relação do produto cartesiano não é comutativa
A x B ≠ B x A

## Tipos de Relações

#### Relação Reflexiva

Uma relação R em A é reflexiva se todos os elementos de A estão relacionados consigo mesmos.
Seja A = {10, 12, 14, 16, 18}
R1 = {**(10, 10),** (10, 18), **(12, 12)**, (12, 14), **(14, 14),** (14, 16), **(16, 16)**, (16, 18), **(18, 18)**}.

#### Relação Simétrica

Uma relação R em A é simétrica se cada elemento x de A que está relacionado com y também ocorre que y está relacionado com x.
Seja A = {10, 12, 14, 16, 18}
A Relação R2 A x A = {(10, 10), **(10, 18)**, _(12, 14)_, _(14, 12)_, (14, 14), (14, 16), (16, 14), (16, 16), (16, 18), **(18, 10)**, (18, 16), (18, 18)} é, portanto, simétrica.

#### Relação Transitiva

Uma relação R em A é transitiva se cada elemento x de A que está relacionado com y e y está relacionado com z; então, ocorre que x está relacionado com z.

A relação x < y é transitiva, pois se x < y, então, pela definição de ser menor, existe um número k tal que x + k = y. Analogamente, se y < z, então, existe um número m tal que y + m = z. 5 < 6 pois 5 + 1 = 6 e 6 < 10 pois 6 + 4 = 10, como 5 + (1 + 4) = 10; então, 5 < 10.

#### Relação Antissimétrica

Uma **relação antissimétrica** é uma relação binária \( R \) em um conjunto \( A \) onde, para quaisquer elementos \( a \) e \( b \) em \( A \), se \( a \) está relacionado a \( b \) e \( b \) está relacionado a \( a \) (ou seja, \( aRb \) e \( bRa \)), então \( a \) deve ser igual a \( b \). Em outras palavras, não pode haver dois elementos distintos \( a \) e \( b \) tais que \( aRb \) e \( bRa \) simultaneamente, a menos que \( a = b \).

##### Exemplo 1: Relação "Menor ou Igual"
Considere o conjunto \( A = \{1, 2, 3\} \) e a relação \( R \) definida por \( aRb \) se \( a \leq b \). Vamos ver se \( R \) é antissimétrica:

- Para \( a = 1 \) e \( b = 2 \), temos \( 1 \leq 2 \) (então \( 1R2 \)), mas \( 2 \not\leq 1 \) (então \( 2 \not R 1 \)).
- Para \( a = 2 \) e \( b = 2 \), temos \( 2 \leq 2 \) (então \( 2R2 \)) e \( 2 \leq 2 \) (então \( 2R2 \)), mas \( a = b \) aqui.

Essa relação é antissimétrica porque não existe \( a \) e \( b \) distintos em \( A \) tais que \( aRb \) e \( bRa \) ao mesmo tempo.

##### Exemplo 2: Relação "Divisibilidade"
Considere o conjunto \( A = \{1, 2, 4, 8\} \) e a relação \( R \) definida por \( aRb \) se \( a \) divide \( b \). Vamos verificar:

- \( 2 \) divide \( 4 \) (então \( 2R4 \)), mas \( 4 \) não divide \( 2 \) (então \( 4 \not R 2 \)).
- \( 4 \) divide \( 8 \) (então \( 4R8 \)), mas \( 8 \) não divide \( 4 \) (então \( 8 \not R 4 \)).
- Para \( a = 2 \) e \( b = 2 \), \( 2 \) divide \( 2 \) (então \( 2R2 \)) e \( 2 = 2 \).

Aqui, novamente, \( R \) é antissimétrica porque não existe \( a \) e \( b \) distintos em \( A \) para os quais \( aRb \) e \( bRa \) sejam verdadeiros ao mesmo tempo.

##### Exemplo 3: Relação "Igualdade"
A relação de igualdade é antissimétrica por definição. Se \( a = b \) e \( b = a \), então \( a = b \).

##### Resumindo:
- A relação \( R \) é antissimétrica se, sempre que \( aRb \) e \( bRa \), então \( a \) deve ser igual a \( b \).
- Se existir \( a \neq b \) tal que \( aRb \) e \( bRa \), então \( R \) **não** é antissimétrica.

Antissimetria é uma propriedade importante em relações, especialmente em conjuntos ordenados, como números com a relação de "menor ou igual", ou em estruturas matemáticas como ordens parciais.

### Função

Todos os elementos de A possuem algum valor e para cada elemento do Conjunto de Partida A existe apenas um elemento correspondente no Conjunto de Chegada B. 
O conjunto de partida A passa a ser chamado de Domínio, e o conjunto de chegada B chamado de Contradomínio de f. 
A notação de função é: f: A → B x → y = f(x)

- Dom (f) = A (o que não ocorre necessariamente nas relações, já que nas relações nem todos os elementos precisam se relacionar, mas na função sim, cada um dos elementos do Domínio necessariamente deve se relacionar, e apenas com um único elemento no contradomínio);
- Os elementos do contradomínio que são resultados da função para algum elemento do Domínio constituem a IMAGEM da função, denotada por Im(f). 
  Im(f) = { f(x)|x ∈ A }
  ![[Pasted image 20240811113430.png]]
  Contradomínio é todo o conjunto B, mesmo que um ou outro elemento não se relacione; já a imagem é um subconjunto do contradomínio formado pelos elementos que são relacionados com os elementos do domínio.
- todos os elementos do domínio precisam se relacionar com um único elemento do contradomínio.

![[Pasted image 20240811113704.png]]

![[Pasted image 20240811113721.png]]

![[Pasted image 20240811113740.png]]

![[Pasted image 20240811113758.png]]

#### Representação por coordenadas:
No eixo das abscissas, temos a representação do domínio, e no eixo das ordenadas, a representação do contradomínio.
![[Pasted image 20240811114021.png]]

![[Pasted image 20240811114035.png]]

![[Pasted image 20240811114057.png]]

![[Pasted image 20240811114117.png]]

#### Igualdade entre Funções 

Sejam duas funções f: A → B e g: A → B, então f será igual a g somente se para todo elemento do domínio A as imagens de cada termo, em B, forem iguais tanto pela função f como pela função g.

### Tipos de funções

#### Funções injetoras:
qualquer que seja x do elemento do domínio, ele se relacionará apenas com um elemento do contradomínio (condição necessária para ser função) e se o contradomínio de cada elemento também só se relacionou (isto é: é imagem) de um único elemento do domínio, então chamamos a função de INJETORA.
![[Pasted image 20240811114751.png]]

#### Funções sobrejetoras:
Chamamos de sobrejetora a função na qual todo o contradomínio é imagem da função, isto é, todo elemento que pertence ao contradomínio é resultado da função.
![[Pasted image 20240811114913.png]]

#### Funções Bijetoras:
Há alguns casos em que além de ser injetora (cada um dos elementos do contradomínio é imagem de apenas um elemento do domínio) a função é também sobrejetora (todos os elementos do contradomínio são imagens de algum elemento do domínio). Quando isso ocorre, chamamos a função de BIJETORA.
![[Pasted image 20240811115129.png]]

#### Função Inversa:
Na função inversa, temos a troca dos papéis entre domínio e imagem, mas na qual a relação se mantém. Por exemplo: temos uma função f de A em B, na qual é A o domínio (conjunto de partida) e B o contradomínio (conjunto de chegada).
Quando fazemos a inversão da função f, isto é, temos f–1, B passa a ser o domínio (conjunto de partida) e A passa a ser a imagem (conjunto de chegada), a relação entre os dois conjuntos se mantém, porém no sentido inverso.
![[Pasted image 20240811115351.png]]
Para que uma função possua sua inversa, ela deve ser necessariamente bijetora; somente assim a inversão ocorrerá para todos os elementos em ambos os conjuntos

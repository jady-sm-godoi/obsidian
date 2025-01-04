
# Conjuntos Numéricos e Operações

A Aritmética trata do estudo dos Conjuntos Numéricos e das operações entre os diferentes tipos de números e suas propriedades. Esse estudo abrange desde a Aritmética Elementar até a Teoria dos Números, que propicia um bom ferramental para outras áreas, como, por exemplo, a Criptografia.

Giuseppe Peano (1858-1932):

três conceitos primitivos: zero, número (natural no caso), e a função “é sucessor de”. A partir desses três conceitos, satisfez cinco postulados ou axiomas.


**Número** é a propriedade de certos conjuntos, os chamados “Conjuntos Padrão”. Assim, associamos o zero ao conjunto vazio: ∅ ≡ 0. A noção de sucessor de x, indicado por S(x) é definida pela união:

![[Pasted image 20240806182752.png]]

O Zero está associado ao conjunto vazio; já o conjunto com o conjunto vazio é associado ao número Um e ele é o sucessor de Zero. Analogamente, temos os demais números.

Assim, temos: 
0 = ∅ ≡0 
1 = s(0) ou 1 ≡ {∅} 
2 = s(1) ou 2 ≡ {0, 1} 
3 = s(2) ou 3 ≡ {0, 1, 2} 
4 = s(3) ou 4 ≡ {0, 1, 2, 3} 

A partir dos três conceitos primitivos, Peano, então, satisfez cinco **axiomas**:

1. Zero é um número natural; 
2. Se a é um número natural, o sucessor de a também é um número natural. Se n ∈ N, então s(n) ∈ N; 
3. Zero não é o sucessor de nenhum número natural; 
4. Dois números cujos sucessores são iguais são eles próprios iguais. Ou seja, se s(n) = s(m), então n = m; 5. Se um conjunto S de números contém o zero e também o sucessor de todo número de S, então todo número está em S.

A partir desses axiomas, é criado o Conjunto dos Números Naturais

## Operações em N

#### Adição:
A soma x + y, resultado da operação da adição: + em N é dada por: 

![[Pasted image 20240806201706.png]]

#### Subtração:
A diferença x - y, resultado da operação de subtração – é definida quando o conjunto B é subconjunto de A:

![[Pasted image 20240806201739.png]]

#### Multiplicação:
O produto x . y, resultado da operação de multiplicação em N, é dado por:

![[Pasted image 20240806201951.png]]


**Em N estão definidas e fechadas duas operações: Adição e Multiplicação.** Dizemos fechadas pois valem para qualquer que seja o número natural, o que já não ocorre com a subtração, já que vimos que não é válida para qualquer par de números naturais.

1. Fechamento da Adição Para todos os números, se dois deles quaisquer, x e y são números naturais, então a sua soma x + y resultará também em um número natural.
2. Associativa da Adição e Multiplicação Na adição de três números naturais quaisquer x, y, z, tanto faz somarmos o primeiro ao resultado da adição dos dois últimos, como o resultado da soma dos dois primeiros ao terceiro; o resultado será o mesmo. Mas é importante destacar que isso ocorre quando temos somente uma das operações: ou a soma ou a multiplicação. Não é válido quanto temos mais de uma operação distinta.
3. Comutatividade da Adição e Multiplicação. Na adição, a ordem das parcelas não altera o resultado da soma. Quaisquer que sejam dois números naturais x e y, temos que a ordem dos fatores na multiplicação entre ambos não altera o resultado.
4. Distributividade da Multiplicação para Adição: Quaisquer que sejam os naturais x, y e z , temos que, se x multiplica a soma dos naturais y e z , ou seja, x * (y + z), então, o resultado será o mesmo se x multiplicar cada um dos naturais e, por fim, somarmos o resultado das multiplicações.
5. Elemento Neutro da Adição Existe um único número n que é o Zero, n = 0, chamado de neutro aditivo. A partir dessa definição, para todos os demais naturais a ele somado, o resultado será sempre o mesmo número.
6. Elemento Neutro da Adição: Existe um único número n que é o Zero, n = 0, chamado de neutro aditivo. A partir dessa definição, para todos os demais naturais a ele somado, o resultado será sempre o mesmo número.


### Conjunto dos Números Inteiros Z

No conjunto dos Inteiros, para quaisquer números x e y ∈ Z, temos que x – y = w , e w ∈ Z. Ou seja, a subtração é uma operação definida e fechada para quaisquer inteiros, o que não ocorre com o conjunto dos Naturais. 
Portanto, estão definidas e fechadas em Z: 
» Adição; 
» Multiplicação; 
» Subtração.


As seis propriedades apresentadas em N também são válidas em Z, e inclui-se agora uma sétima propriedade:

7. Elemento Oposto ou Inverso Aditivo: Para todo e qualquer número inteiro x, existe outro número inteiro chamado oposto de x, representado por op(x) = - x, e a soma entre um número e seu oposto será igual ao elemento neutro 0 “zero”.

Nas operações entre inteiros, valem as regras : 
1. A soma inteira positiva é positiva; 
2. A soma de inteiros negativos é negativa; 
3. Se o número tem sinais diferentes, subtraímos o menor do maior, em valor absoluto, e mantemos o sinal do maior, também em valor absoluto; 
4. O produto de números inteiros de mesmo sinal é positivo; 
5. O produto de números inteiros de sinais diferentes é negativo.


### Conjunto dos Números Racionais Q

![[Pasted image 20240806203758.png]]

conjunto Q dos números racionais é o conjunto formado por todos os números que podem ser escritos como uma razão (divisão) entre dois números inteiros quaisquer a e b; porém, com b sendo diferente de 0 “zero”.


##### Decimal Dízima Periódica Simples
Uma decimal dízima periódica simples é um número decimal que possui um bloco de dígitos que se repete infinitamente logo após a vírgula. Esse bloco de dígitos repetidos é chamado de período.

**Exemplo**: O número 0,333...0,333...0,333... é uma decimal dízima periódica simples, onde o dígito "3" se repete infinitamente.

##### Decimal Dízima Periódica Composta
representação decimal que possui uma parte não periódica seguida de uma parte periódica. A parte não periódica é o conjunto de dígitos iniciais que não se repetem, enquanto a parte periódica é o conjunto de dígitos que se repetem indefinidamente.

**Exemplo:**
Considerando o número 0.1234567676767....:

- Parte não periódica: `12345`
- Parte periódica: `67`

Porém, há números decimais infinitos e não periódicos que não podem ser escritos na forma fracionária; são os chamados Números Irracionais. Entre eles, destacamos: 
π= 3,14159265358979… (que é obtido a partir da razão entre o comprimento de qualquer circunferência pelo seu diâmetro); 
e = 2,718281828.. (número de Neper, utilizado como base de logaritmos); 
raiz de 2 = 1,4142135...; 
raiz de 3 = 1,7320508... .

##### Propriedades das Operações da Adição e Multiplicação em Q
As propriedades de fechamento da divisão, associatividade da adição e multiplicação, e também a comutatividade, são análogas ao Conjunto dos Inteiros.
1. Fechamento da Divisão
2. Associativa da Adição e Multiplicação
3. Comutatividade da Adição e Multiplicação
4. Distributividade da Multiplicação para Adição
5. Elemento Neutro da Adição: 0
6. Elemento Neutro da Multiplicação: 1
7. Elemento Oposto ou Inverso Aditivo
8. Elemento Inverso Multiplicativo: Ao realizarmos a multiplicação entre um número racional e seu inverso, o resultado será igual ao elemento neutro da multiplicação.
   Exemplo: 1/2 seu inverso é 2/1, então, temos que 1/2 * 2/1 = 1. 
   2/3 seu inverso é 3/2, então, temos que 2/3 * 3/2 = 1. 
   -4/5 seu inverso é -5/4, então, temos que -4/5 * (-5/4) = 1.

Unindo o conjunto dos racionais com os números irracionais, formamos o Conjunto dos Reais R.

![[Pasted image 20240807165347.png]]

### Potência

O valor de a é chamado de base e o valor de n é chamado de expoente. O resultado, chamamos de potência.

![[Pasted image 20240806210254.png]]

Qualquer que seja a base a, temos que a0 = 1.

![[Pasted image 20240806210352.png]]

![[Pasted image 20240806210418.png]]

![[Pasted image 20240806210443.png]]

![[Pasted image 20240806210509.png]]

![[Pasted image 20240806210700.png]]

##### Potência com expoente racional

![[Pasted image 20240806210825.png]]

![[Pasted image 20240806210843.png]]


### Radiciação

![[Pasted image 20240806211012.png]]
![[Pasted image 20240806211025.png]]

Não existe nenhum número real x que, elevado ao quadrado, resulte em um valor negativo.

Essa possibilidade existe no Conjunto dos Números Complexos, no qual uma unidade imaginária i tem por definição o resultado de i² = -1 e, por consequência   1 i . Essa definição, assim como o conjunto dos numéricos complexos, possui aplicações bem interessantes no cálculo de circuitos elétricos.

##### Propriedades da Radiciação

![[Pasted image 20240806211411.png]]

![[Pasted image 20240806211424.png]]

![[Pasted image 20240806211455.png]]

![[Pasted image 20240806211513.png]]

]]
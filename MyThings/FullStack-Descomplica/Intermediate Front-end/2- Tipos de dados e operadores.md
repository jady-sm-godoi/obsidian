````markdown
# Aula de JavaScript: Operadores e Variáveis

**JavaScript** é uma das linguagens mais importantes hoje. Está disponível em quase todos os dispositivos, sejam smartphones, televisores ou, graças ao **NodeJS**, agora também na área de servidores.

JavaScript é uma plataforma criada pela **Netscape** que permite a programação orientada a objetos. Ele possibilita a criação de aplicativos e documentos que podem ser executados na Internet, além de oferecer opções para interação em páginas web e manipulação de seus elementos. A linguagem possui operadores poderosos que aumentam o dinamismo do código.

---

## **Objetivos da Aula**
- Definir os tipos de dados e de variáveis em JavaScript.
- Demonstrar os principais operadores da linguagem.
- Explicar como trabalhar com variáveis e operadores em uma rotina JavaScript.

---

## **Resumo**

### Operadores
Operadores são caracteres ou cadeias de caracteres que conectam dois objetos e processam um resultado. Eles são divididos em vários grupos:

---

### **Operadores Aritméticos**

Exemplo:
```javascript
a = 5 + 4; // a é 9
b = a - 3; // b é 9 - 3, então 6
c = a * b; // c é 9 vezes 6, então 54
d = c / 4.5; // d é 54 dividido por 4.5, então 12
e = d % 5; // e é o resto de 12 dividido por 5, então 2 (5 + 5 + 2)
````

---

### **Operadores de String**

Os operadores de string funcionam apenas com textos.

|Operador|Descrição|
|---|---|
|`+`|Une duas strings|
|`+=`|Acrescenta uma string a outra|

Exemplo:

```javascript
a = 'ABC';
b = 'DEF';
c = 'GHI';

d = a + b; // d é 'ABC' mais 'DEF', então 'ABCDEF'
e = 'ABC' + b; // e é 'ABCDEF'

f = e;
f += c; // c ('GHI') é anexado a f, então f é 'ABCDEFGHI'
```

---

### **Operadores Lógicos**

São usados para formular condições, que sempre resultam em `true` ou `false`.

Exemplo:

```javascript
a = 3; b = 5;

if (a == b) { /*...*/ } 
// se a é igual a b, a condição é verdadeira

if (a != b) { /*...*/ } 
// se a não é igual a b, a condição é verdadeira

if (a == 3 && b != 4) { /*...*/ } 
// se a é 3 E b não é 4, a condição é verdadeira

if (a == 4 || b == 5) { /*...*/ } 
// se a é 4 OU b é 5, a condição é verdadeira

if (a < 5) { /*...*/ } 
// se a é menor que 5, a condição é verdadeira
```

---

### **Operadores de Atribuição**

Usados para definir valores em variáveis.

Exemplo:

```javascript
a = 3;
a += 4; // a é 7
a -= 3; // a é 4
a *= 5; // a é 20
a /= 4; // a é 5
```

---

## **Dicas**

- Aprenda mais sobre [operadores de atribuição](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Operators/Assignment_Operators).
- Explore [operadores lógicos](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Operators/Logical_Operators).

---

## **Referência Bibliográfica**

- Duckett, J. _JavaScript de alto impacto_. Alta Books, 2015.
- Castro, R. _JavaScript: guia prático_. Alta Books, 2019.
- Freeman, E. _Use a cabeça! JavaScript_. Alta Books, 2015.
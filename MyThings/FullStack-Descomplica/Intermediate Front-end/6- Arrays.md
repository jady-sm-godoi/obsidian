
![[Pasted image 20250102124545.png]]
![[Pasted image 20250102125227.png]]



---

# Arrays em JavaScript

O array é uma única variável usada para armazenar diferentes elementos. Ele é frequentemente utilizado para armazenar uma lista de elementos, acessando-os por uma única variável. Ao contrário da maioria das linguagens, onde o array é uma referência a várias variáveis, em JavaScript, o array é uma única variável que armazena vários elementos.

---

## Objetivos da Aula

- Definir os conceitos de Arrays.
- Reconhecer Arrays e seus principais métodos na linguagem JavaScript.
- Demonstrar a implementação de Arrays na linguagem JavaScript.

---

## Resumo

O objeto `Array` permite armazenar vários valores em uma única variável. Ele armazena uma coleção sequencial de tamanho fixo de elementos do mesmo tipo. É usado para armazenar uma coleção de dados e pode ser pensado como uma coleção de variáveis do mesmo tipo.

---

### Sintaxe

Use a seguinte sintaxe para criar um objeto `Array`:

```javascript
let array = new Array(); // Cria um array vazio
let array = [1, 2, 3]; // Cria um array com elementos
```

Ao especificar um único parâmetro numérico no construtor `Array`, você define o comprimento inicial da matriz:

```javascript
let array = new Array(10); // Cria um array com comprimento 10
```

O comprimento máximo permitido para uma matriz é **4.294.967.295**. Você também pode criar uma matriz atribuindo diretamente os valores:

```javascript
let array = [10, 20, 30];
```

Você usará números ordinais para acessar e definir valores dentro de uma matriz:

```javascript
array[0] = 50; // Define o valor do primeiro elemento
console.log(array[0]); // Acessa o valor do primeiro elemento
```

---

### Propriedades do Array

#### `length`: Propriedade de Comprimento do Array

A propriedade `length` retorna um inteiro sem sinal de 32 bits que especifica o número de elementos em um array.

**Sintaxe:**

```javascript
let tamanho = array.length;
```

#### `constructor`: Propriedade do Construtor do Array

A propriedade `constructor` retorna uma referência à função que criou o protótipo da instância do objeto.

**Sintaxe:**

```javascript
let construtor = array.constructor;
```

---

### Operações Básicas em Arrays

#### Adicionar um elemento ao final de um array

Use o método `push()`:

```javascript
array.push(40);
```

#### Adicionar um elemento ao início de um array

Use o método `unshift()`:

```javascript
array.unshift(0);
```

#### Remover um elemento do final de um array

Use o método `pop()`:

```javascript
array.pop();
```

#### Remover um elemento do início de um array

Use o método `shift()`:

```javascript
array.shift();
```

---

### Dicas

- Saiba mais sobre a aplicação de vetores: [Trabalhando com Vetores](https://siteantigo.portaleducacao.com.br/conteudo/artigos/informatica/trabalhando-com-vetores/31845)
- Como ordenar um array de objetos em JavaScript: [Assista ao vídeo](https://www.youtube.com/watch?v=yc0TYlnZIp4)

---

## Referência Bibliográfica

- FLANAGAN, David. _JavaScript: O Guia Definitivo_. 6ª Ed. Porto Alegre: Bookman, 2013.
- FREEMAN, Eric. _Use a cabeça!: programação JavaScript_. 1ª Ed. São Paulo: Alta Books, 2016.

---
# Arrays no JavaScript

Arrays são uma ferramenta poderosa e abrangente no JavaScript. São muito intuitivos de usar e permitem realizar diversas operações. No entanto, existem diferenças importantes entre arrays no JavaScript e em outras linguagens convencionais. Conhecê-las ajudará você a explorar todo o seu potencial.

---

## **Objetivos da Aula**
- Demonstrar o emprego, na prática, dos arrays no JavaScript para solução de problemas.

---

## **Resumo**

Quando desenvolvemos uma aplicação, frequentemente manipulamos arrays para, por exemplo, filtrar seus dados. O JavaScript possui métodos importantes que facilitam essa manipulação. Este material aborda como trabalhar com arrays de forma eficiente e eficaz.

---

### **Reduce**
O método `reduce()` aplica uma função em um acumulador e em cada valor do array (da esquerda para a direita), reduzindo-o a um único valor. Esse método é útil para condensar os valores de um array em um único resultado.

**Exemplo:**

```javascript
const array = [1, 2, 3, 4];
const soma = array.reduce((acumulador, valorAtual) => acumulador + valorAtual, 0);
console.log(soma); // Saída: 10
````

---

### **Map**

O método `map()` é usado para gerar um novo array baseado nos valores de um array existente.

**Exemplo:**

```javascript
const strings = ["JavaScript", "HTML", "CSS"];
const comprimentos = strings.map(string => string.length);
console.log(comprimentos); // Saída: [10, 4, 3]
```

**Parâmetros da função no `map()`:**

1. O elemento atual.
2. O índice do elemento.
3. O array completo.

---

### **Filter**

O método `filter()` aceita uma função de teste e retorna um novo array contendo apenas os elementos que passam no teste.

**Exemplo:**

```javascript
const numeros = [2, 5, 8, 43];
const impares = numeros.filter(numero => numero % 2 !== 0);
console.log(impares); // Saída: [5, 43]
```

---

### **For...in**

O loop `for...in` pode ser usado para iterar sobre os índices de um array.

**Exemplo:**

```javascript
const array = ["a", "b", "c"];
for (const indice in array) {
  console.log(`Índice: ${indice}, Valor: ${array[indice]}`);
}
```

---

### **For...of**

O loop `for...of` é recomendado para iterar diretamente sobre os valores de um array.

**Exemplo:**

```javascript
const array = ["a", "b", "c"];
for (const valor of array) {
  console.log(`Valor: ${valor}`);
}
```

**Diferença entre `for...in` e `for...of`:**

- **`for...in`**: Itera sobre os índices do array.
- **`for...of`**: Itera sobre os valores do array.

---

## **Referência Bibliográfica**

- FLANAGAN, David. _JavaScript: O Guia Definitivo_. 6ª Ed. Porto Alegre: Bookman, 2013.
- FREEMAN, Eric. _Use a cabeça!: programação JavaScript_. 1ª Ed. São Paulo: Alta Books, 2016.

# Entrada, Processamento e Saída de Dados em JavaScript com Manipulação do DOM

## Objetivos da Aula

- Definir os conceitos de DOM (Document Object Model).
- Reconhecer elementos DOM com JavaScript.
- Demonstrar a implementação do conceito DOM na linguagem JavaScript, com exemplos práticos.

## Resumo

### Entrada, Processamento e Saída de Dados em JavaScript

O objetivo de um programa é escrever um código no computador para resolver problemas. Para isso, é necessário que o programa tenha uma entrada de dados, para que esses dados sejam processados e, então, os resultados sejam apresentados ao usuário. A estrutura básica de um programa em JavaScript é simples, com a utilização de comentários (// para uma linha e /* ... */ para várias linhas).

#### Exemplo de Declaração e Comentários em JavaScript:

```javascript
// Este é um comentário de uma linha
/* Este é um comentário
   de várias linhas */
```

Para exemplificar a entrada de dados e a saída de informações em JavaScript, podemos criar um programa que recebe dois inteiros e mostra ambos os números utilizando o DOM para interação com o usuário na página web.

### Exemplo de Entrada e Saída com o DOM

#### HTML:

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <title>Entrada e Saída</title>
</head>
<body>
    <h1>Entrada e Saída com JavaScript</h1>
    <label for="num1">Digite o primeiro número:</label>
    <input type="number" id="num1">
    <br><br>
    <label for="num2">Digite o segundo número:</label>
    <input type="number" id="num2">
    <br><br>
    <button onclick="mostrarNumeros()">Mostrar Números</button>
    <p id="resultado"></p>

    <script src="script.js"></script>
</body>
</html>
```

#### JavaScript (script.js):

```javascript
function mostrarNumeros() {
    let num1 = document.getElementById('num1').value;
    let num2 = document.getElementById('num2').value;
    
    let resultado = `Os números digitados foram: ${num1} e ${num2}`;
    document.getElementById('resultado').innerText = resultado;
}
```

Este exemplo usa o DOM para coletar os valores dos campos de entrada e exibe os números digitados no parágrafo `#resultado` quando o botão é clicado.

### Estrutura Sequencial em JavaScript

Na estrutura sequencial, os dados são recebidos, processados e os resultados são mostrados ao usuário. Vamos criar um programa simples para calcular a soma de dois números inteiros.

#### Exemplo de Estrutura Sequencial para Soma:

#### HTML:

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <title>Soma de Números</title>
</head>
<body>
    <h1>Calculando a Soma de Dois Números</h1>
    <label for="num1">Digite o primeiro número:</label>
    <input type="number" id="num1">
    <br><br>
    <label for="num2">Digite o segundo número:</label>
    <input type="number" id="num2">
    <br><br>
    <button onclick="calcularSoma()">Calcular Soma</button>
    <p id="resultado"></p>

    <script src="script.js"></script>
</body>
</html>
```

#### JavaScript (script.js):

```javascript
function calcularSoma() {
    let num1 = parseInt(document.getElementById('num1').value);
    let num2 = parseInt(document.getElementById('num2').value);
    
    let soma = num1 + num2;
    document.getElementById('resultado').innerText = `A soma dos números é: ${soma}`;
}
```

### Estrutura de Seleção em JavaScript

A estrutura de seleção permite que o programa tome decisões com base em condições específicas. Em JavaScript, podemos usar estruturas como `if`, `else` e `else if` para realizar essas verificações.

#### Seleção Simples

Na **seleção simples**, verificamos uma única condição e tomamos uma decisão com base nela.

##### Exemplo de Seleção Simples: Verificando se um número é negativo

#### HTML:

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <title>Verificando Número Negativo</title>
</head>
<body>
    <h1>Verificando se o número é negativo</h1>
    <label for="numero">Digite um número:</label>
    <input type="number" id="numero">
    <br><br>
    <button onclick="verificarNegativo()">Verificar</button>
    <p id="resultado"></p>

    <script src="script.js"></script>
</body>
</html>
```

#### JavaScript (script.js):

```javascript
function verificarNegativo() {
    let numero = parseFloat(document.getElementById('numero').value);
    
    if (numero < 0) {
        document.getElementById('resultado').innerText = 'O número é negativo.';
    }
}
```

#### Seleção Composta

A **seleção composta** envolve duas ou mais condições. Vamos verificar se um número é positivo ou negativo.

##### Exemplo de Seleção Composta: Verificando se um número é positivo ou negativo

#### HTML:

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <title>Verificando Número</title>
</head>
<body>
    <h1>Verificando se o número é positivo ou negativo</h1>
    <label for="numero">Digite um número:</label>
    <input type="number" id="numero">
    <br><br>
    <button onclick="verificarPositivoOuNegativo()">Verificar</button>
    <p id="resultado"></p>

    <script src="script.js"></script>
</body>
</html>
```

#### JavaScript (script.js):

```javascript
function verificarPositivoOuNegativo() {
    let numero = parseFloat(document.getElementById('numero').value);
    
    if (numero > 0) {
        document.getElementById('resultado').innerText = 'O número é positivo.';
    } else if (numero < 0) {
        document.getElementById('resultado').innerText = 'O número é negativo.';
    } else {
        document.getElementById('resultado').innerText = 'O número é zero.';
    }
}
```

### Estrutura Encadeada

A **estrutura encadeada** combina várias condições e blocos de código. Por exemplo, podemos verificar se um número é par ou ímpar e, dependendo do valor, fazer outra verificação.

##### Exemplo de Seleção Encadeada: Verificando se um número é par ou ímpar

#### HTML:

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <title>Verificando Par ou Ímpar</title>
</head>
<body>
    <h1>Verificando se o número é par ou ímpar</h1>
    <label for="numero">Digite um número inteiro:</label>
    <input type="number" id="numero">
    <br><br>
    <button onclick="verificarParOuImpar()">Verificar</button>
    <p id="resultado"></p>

    <script src="script.js"></script>
</body>
</html>
```

#### JavaScript (script.js):

```javascript
function verificarParOuImpar() {
    let numero = parseInt(document.getElementById('numero').value);
    
    if (numero % 2 === 0) {
        document.getElementById('resultado').innerText = 'O número é par.';
    } else {
        document.getElementById('resultado').innerText = 'O número é ímpar.';
    }
}
```

## Conclusão

A estrutura sequencial e de seleção em JavaScript permite criar programas interativos e dinâmicos para o usuário. O uso do **DOM** permite interagir diretamente com os elementos HTML da página, tornando a experiência mais rica. Com o conhecimento dessas estruturas e do DOM, podemos criar interfaces que recebem dados do usuário, processam esses dados e retornam os resultados de forma interativa e dinâmica.

---

Referências:

- **Deitel, Paul J. & Deitel, Harvey M.** Ajax, Rich Internet Applications e Desenvolvimento Web para programadores. São Paulo: Pearson Prentice Hall, 2008.
- **Freeman, Eric.** Use a cabeça!: Programação JavaScript. 1ª Ed. São Paulo: Alta Books, 2016.
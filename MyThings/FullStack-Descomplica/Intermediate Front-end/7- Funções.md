# Funções em JavaScript

Uma **função** é uma unidade de código que realiza uma tarefa ou calcula um valor. É definida por seu papel dentro de uma estrutura maior e funciona com entradas (variáveis) para produzir resultados concretos.  

## Objetivos da Aula

- Definir os conceitos de Funções.
- Demonstrar a implementação de Funções na linguagem JavaScript.

---

## Resumo

As funções em JavaScript são blocos que realizam a mesma tarefa repetidamente, sempre que chamadas. Elas ajudam a evitar a repetição de código, tornando-o mais eficiente e fácil de entender.  

### Definição de uma Função

Para definir uma função, utiliza-se a palavra-chave `function`, seguida de:

1. **Nome da Função**: Identifica a função.
2. **Lista de Argumentos**: Dentro de parênteses `()`, separados por vírgulas.
3. **Corpo da Função**: Instruções que definem a função, dentro de chaves `{}`.

### Exemplo de Função

```javascript
function tellTime() {
  const now = new Date();
  alert(`Hora atual: ${now.toLocaleTimeString()}`);
}
````

Para chamar a função, basta usar seu nome:

```javascript
tellTime();
```

---

## Trabalhando com Parâmetros e Argumentos

Uma das vantagens das funções é a possibilidade de passar dados para elas.

### Exemplo:

```javascript
function greetUser(greeting) {
  alert(greeting);
}

// Chamando a função com um argumento
greetUser("Olá, pessoal!");
```

- **Parâmetro**: É uma variável definida na função, como `greeting`.
- **Argumento**: É o valor passado para a função ao chamá-la, como `"Olá, pessoal!"`.

---

## Criando Funções com o Construtor `Function`

Além da declaração tradicional, você pode criar funções dinamicamente com o construtor `Function()`:

### Sintaxe:

```javascript
const func = new Function('param1', 'param2', 'return param1 + param2;');

// Chamando a função
console.log(func(2, 3)); // Saída: 5
```

### Funções Anônimas

As funções criadas com o construtor `Function()` são anônimas, ou seja, não possuem um nome associado.

---

## Referências Bibliográficas

- **FLANAGAN, David.** JavaScript: O Guia Definitivo. 6ª Ed. Porto Alegre: Bookman, 2013.
- **FREEMAN, Eric.** Use a cabeça!: Programação JavaScript. 1ª Ed. São Paulo: Alta Books, 2016.
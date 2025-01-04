
# Classes no JavaScript

As classes foram introduzidas no ECMAScript 2015 e representam uma simplificação da linguagem para heranças baseadas em protótipos. Elas não utilizam um novo modelo de herança de orientação a objetos em JavaScript, mas oferecem uma maneira mais legível e estruturada de criar objetos e lidar com herança.

## Objetivos da Aula

- Definir os conceitos de classes e objetos.
- Reconhecer classes e objetos na linguagem JavaScript.
- Demonstrar a implementação de classes e objetos na linguagem JavaScript.

---

## Declaração de Classe

A declaração de classe cria uma classe com um determinado nome usando herança baseada em protótipos. A sintaxe é simples e clara:

```javascript
class Pessoa {
  constructor(nome, idade) {
    this.nome = nome;
    this.idade = idade;
  }

  saudacao() {
    return `Olá, meu nome é ${this.nome} e tenho ${this.idade} anos.`;
  }
}

// Exemplo de uso
const pessoa1 = new Pessoa("Maria", 30);
console.log(pessoa1.saudacao());
// Saída: Olá, meu nome é Maria e tenho 30 anos.
```

---

## Class Expression

Uma **class expression** é uma maneira alternativa de definir classes. Semelhante às expressões de função, elas podem ser nomeadas ou anônimas.

### Sintaxe de uma Expressão de Classe

```javascript
const Pessoa = class {
  constructor(nome, idade) {
    this.nome = nome;
    this.idade = idade;
  }

  saudacao() {
    return `Olá, meu nome é ${this.nome} e tenho ${this.idade} anos.`;
  }
};

// Exemplo de uso
const pessoa2 = new Pessoa("João", 25);
console.log(pessoa2.saudacao());
// Saída: Olá, meu nome é João e tenho 25 anos.
```

### Expressão de Classe Nomeada

As expressões de classe podem incluir um nome, que será visível apenas dentro do escopo da própria classe:

```javascript
const Animal = class Cachorro {
  constructor(raca) {
    this.raca = raca;
  }

  latir() {
    return `O ${this.raca} está latindo!`;
  }
};

// Exemplo de uso
const dog = new Animal("Labrador");
console.log(dog.latir());
// Saída: O Labrador está latindo!
```

---

## Herança com Classes

As classes em JavaScript também permitem a herança, onde uma classe pode estender outra, herdando suas propriedades e métodos.

```javascript
class Veiculo {
  constructor(tipo) {
    this.tipo = tipo;
  }

  mover() {
    return `O ${this.tipo} está se movendo.`;
  }
}

class Carro extends Veiculo {
  constructor(marca, modelo) {
    super("carro");
    this.marca = marca;
    this.modelo = modelo;
  }

  detalhes() {
    return `Este é um ${this.marca} ${this.modelo}.`;
  }
}

// Exemplo de uso
const meuCarro = new Carro("Toyota", "Corolla");
console.log(meuCarro.mover());
// Saída: O carro está se movendo.
console.log(meuCarro.detalhes());
// Saída: Este é um Toyota Corolla.
```

---

## Diferenças entre Declaração e Expressão de Classe

|Característica|Declaração de Classe|Expressão de Classe|
|---|---|---|
|Nome|Necessário|Opcional|
|Escopo|Global/Bloco|Local ao Corpo|
|Redefinição (redeclaração)|Não permitido|Permitido|

---

## Referências Bibliográficas

- FLANAGAN, David. _JavaScript: O Guia Definitivo_. 6ª Ed. Porto Alegre: Bookman, 2013.
- FREEMAN, Eric. _Use a Cabeça!: Programação JavaScript_. 1ª Ed. São Paulo: Alta Books, 2016.
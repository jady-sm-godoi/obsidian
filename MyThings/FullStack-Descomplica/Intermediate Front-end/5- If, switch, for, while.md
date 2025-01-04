````markdown
# Javascript: Instruções de Controle e Looping

A linguagem Javascript possui uma série de instruções que possibilitam os programas implementarem tomada de decisão, bem como repetição de um trecho de código ou até mesmo todo. Estas são conhecidas respectivamente por **desvios condicionais** e **laços**, chamados comumente por Looping.

---

## Objetivos da aula

- Definir os conceitos de desvio condicional e de laços.
- Demonstrar as principais instruções de desvio condicional e de laços da linguagem Javascript.
- Explicar como trabalhar desvios condicionais de loopings em uma rotina Javascript.

---

## Resumo

Ao escrever um programa, pode haver uma situação em que você precise adotar um de um determinado conjunto de caminhos. Nesses casos, você precisa usar **instruções condicionais** que permitam que seu programa tome decisões corretas e execute as ações corretas.

JavaScript oferece suporte a declarações condicionais que são usadas para executar ações diferentes com base em condições diferentes.

JavaScript suporta as seguintes formas de instrução `if..else`:

- Declaração `if`
- Declaração `if ... else`
- Declaração `if ... else if`

---

### Declaração `if`

A instrução `if` é a instrução de controle fundamental que permite ao JavaScript tomar decisões e executar instruções condicionalmente.

#### Sintaxe

```javascript
if (condicao) {
    // instruções a serem executadas se a condição for verdadeira
}
````

Aqui, uma expressão JavaScript é avaliada. Se o valor resultante for **verdadeiro**, a(s) instrução(ões) fornecida(s) são executadas. Se a expressão for **falsa**, nenhuma instrução será executada. Na maioria das vezes, você usará **operadores de comparação** ao tomar decisões.

---

### Declaração `if ... else`

A instrução `if ... else` permite ao JavaScript executar instruções de uma forma mais controlada.

#### Sintaxe

```javascript
if (condicao) {
    // instruções se a condição for verdadeira
} else {
    // instruções se a condição for falsa
}
```

Aqui, a expressão JavaScript é avaliada. Se o valor resultante for **verdadeiro**, as instruções no bloco `if` são executadas. Caso contrário, as instruções no bloco `else` são executadas.

---

### Declaração `if ... else if`

A instrução `if ... else if` é uma forma avançada de controle que permite ao JavaScript tomar uma decisão correta a partir de várias condições. Também é conhecida como “if aninhado”.

#### Sintaxe

```javascript
if (condicao1) {
    // instruções para condicao1
} else if (condicao2) {
    // instruções para condicao2
} else {
    // instruções se nenhuma condição for verdadeira
}
```

Trata-se de uma série de instruções `if`, onde cada `if` é parte da cláusula `else` da instrução anterior.

---

### Switch Case

Você pode usar várias instruções `if ... else if` para realizar uma ramificação multiway. No entanto, essa nem sempre é a melhor solução, especialmente quando todos os ramos dependem do valor de uma única variável.

A instrução `switch` foi introduzida para lidar com essas situações de forma mais eficiente.

#### Sintaxe

```javascript
switch (expressao) {
    case valor1:
        // instruções para valor1
        break;
    case valor2:
        // instruções para valor2
        break;
    default:
        // instruções padrão
}
```

O interpretador verifica cada caso em relação ao valor da expressão até encontrar uma correspondência. Se nada corresponder, o bloco `default` será executado.

---

## O laço `while`

O loop mais básico em JavaScript é o loop `while`, cujo objetivo é executar uma instrução ou bloco de código repetidamente, desde que uma expressão seja verdadeira.

#### Sintaxe

```javascript
while (condicao) {
    // instruções enquanto a condição for verdadeira
}
```

Quando a expressão se torna falsa, o loop termina.

---

## O loop `do ... while`

O loop `do ... while` é semelhante ao loop `while`, exceto que a **verificação da condição ocorre no final do loop**. Isso significa que o loop sempre será executado pelo menos uma vez, mesmo se a condição for falsa.

#### Sintaxe

```javascript
do {
    // instruções
} while (condicao);
```

---

## Referência Bibliográfica

- FLANAGAN, David. _JavaScript: O Guia Definitivo_. 6ª Ed. Porto Alegre: Bookman, 2013.
- FREEMAN, Eric. _Use a cabeça!: programação JavaScript_. 1ª Ed. São Paulo: Alta Books, 2016.
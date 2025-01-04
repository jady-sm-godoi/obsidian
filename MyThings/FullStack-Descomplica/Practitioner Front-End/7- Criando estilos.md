
![[Pasted image 20241228174637.png]]

![[Pasted image 20241228190837.png]]

# O Cascading Style Sheets (CSS)

O CSS é uma "folha de estilo" que define como serão exibidos os elementos contidos no código de uma página da internet e sua maior vantagem é efetuar a separação entre o formato e o conteúdo de um documento. Isto torna o HTML mais legível e mantém o documento independente do formato.

Uma folha de estilo contém a definição de estilo para um ou mais documentos. Como o HTML é considerado documento, o CSS pode ser utilizado para formatar a página HTML.

## Objetivos da aula

- Descrever as principais propriedades CSS referentes a texto
- Discutir a formatação de listas para menu em CSS
- Explicar o conceito de classe em CSS

## Resumo

### Propriedades para texto

Com CSS podemos definir propriedades do texto como: tamanho da fonte, cor da fonte, peso da fonte, tipo da fonte, espaçamento entre linhas e espaçamento entre letras.

```css
p {
    text-align: center;
    font-family: Arial, Helvetica, sans-serif;
    font-style: italic;
    font-size: 14px;
    text-shadow: 3px 3px 3px #ababab;
    color: white;
    text-decoration-line: underline;
    font-weight: bold;
    line-height: 90%;
    background-color: green;
}
```

No exemplo acima, o seletor `p` vai atribuir aos parágrafos da página: alinhamento do texto ao centro, fonte Arial, tipo de fonte itálica, tamanho da fonte de 14 pixels, sombreamento ao texto, cor cinza, decoração sublinhada, negrito para peso da fonte e altura da linha de 80% do tamanho da fonte e cor de fundo verde.

A propriedade `font-family` permite que se faça uma lista de prioridades de famílias de fontes e/ou nomes genéricos de famílias a serem utilizadas. O navegador irá utilizar a primeira fonte da lista que for encontrada no computador ou poderá fazer o download utilizando a informação contida na regra `@font-face`.

A propriedade `margin` do CSS define a área de margem nos quatro lados do elemento.

### Formatando listas para menu

Um menu pode ser criado aplicando CSS aos elementos de uma lista não ordenada como a que se segue.

```html
<ul>
    <li><a>Item 1</a></li>
    <li><a>Item 2</a></li>
    <li><a>Item 3</a></li>
</ul>
```

Para transformar a lista acima em menu, removemos os marcadores utilizando a propriedade `list-style: none;` no seletor `ul`, fazemos os itens `li` “flutuarem” para a esquerda utilizando a propriedade `float: left;` e, por fim, adicionamos um espaçamento entre os itens com `padding: 10px;` e removemos o sobrescrito do link com `text-decoration: none;`.

```css
ul {
    list-style: none;
}

ul li {
    float: left;
}

ul li a {
    padding: 10px;
    text-decoration: none;
}
```

### Estilizando tabelas com pseudo-classes

Com CSS podemos estilizar elementos fazendo uso de pseudo-classes. Pseudo-classes são palavras-chave adicionadas a seletores que especificam um estado especial do elemento selecionado. A lista de pseudo-classes pode ser encontrada na [documentação para desenvolvedores da Mozilla](https://developer.mozilla.org/pt-BR/docs/Web/CSS).

No exemplo abaixo, utiliza-se uma tabela, atribuindo a cor de fundo `#e9e9e9` para as linhas pares e a cor de fundo `#bdbdbd` para as linhas ímpares.

```css
tr:nth-child(even) {
    background: #e9e9e9;
}

tr:nth-child(odd) {
    background: #bdbdbd;
}
```

### Usando caixas e atribuindo classes e IDs

`<div>` é um elemento de divisão de conteúdo. É um contêiner genérico utilizado para agrupar elementos para fins de estilos (usando classes ou IDs). Deve ser utilizada somente quando não houver outro elemento semântico (como `<section>`, `<article>`, `<header>`, `<footer>`, etc.).

Classes e IDs permitem ao CSS e ao JavaScript selecionarem e acessarem elementos da página HTML. Classes podem ser atribuídas a vários elementos, enquanto IDs só podem ser atribuídos a um elemento, pois ele é o identificador único.

No exemplo a seguir, todas as divs de classe `subtitulo` receberão cor de fundo vermelho e cor de texto branca. O elemento com ID `titulo` receberá cor de fundo azul claro, cor de texto preta e texto alinhado ao centro.

```html
<style>
#titulo {
    background-color: lightblue;
    color: black;
    text-align: center;
}

.subtitulo {
    background-color: red;
    color: white;
}
</style>

<h1 id="titulo">Cidades</h1>

<h2 class="subtitulo">Londres</h2>
<h2 class="subtitulo">Paris</h2>
<h2 class="subtitulo">Tokyo</h2>
```

## Como aplicar na prática o que aprendeu

### Estilizando título

Vamos adicionar à folha de estilo `style.css` algum código para estilizar o título da página de modo a alinhá-lo ao centro, atribuir o estilo itálico, tamanho de fonte 44px, sombreado, cor branca e negrito utilizando o código a seguir:

```css
p {
    text-align: center;
    font-style: italic;
    font-size: 44px;
    text-shadow: 3px 3px 3px #0f0f0f;
    color: white;
    font-weight: bold;
}
```

Após inserir este código no arquivo `style.css`, salve, volte ao navegador, atualize a página e veja se mudou e está conforme o esperado.

### Estilizando lista como menu

Vamos adicionar estilo à lista que havíamos inserido na página. Vamos remover os marcadores, adicionar um espaçamento entre os itens, deixá-la na horizontal (como um menu), aplicar cor de fundo cinza e cor de texto branco:

```css
ul {
    list-style: none;
    padding: 25px 50px 70px 0px;
    background: gray;
}

ul li {
    float: left;
    padding: 10px;
    color: white;
}
```

Salve, volte ao navegador, atualize a página e veja se mudou e está conforme o esperado.

### Estilizando tabela com pseudo-classes

Vamos agora estilizar a tabela utilizando pseudo-classes, atribuindo cor de fundo cinza para o cabeçalho, cor de fundo `#e9e9e9` para as linhas pares e cor de fundo `#bdbdbd` para as linhas ímpares:

```css
thead th {
    background: gray;
    color: white;
}

tr:nth-child(even) {
    background: #e9e9e9;
}

tr:nth-child(odd) {
    background: #bdbdbd;
}
```

Mais uma vez, salve, volte ao navegador, atualize a página e veja se mudou e está conforme o esperado.

## Dicas quentes

- Existe uma lista de fontes "seguras para a web" (fontes tão comuns que são consideradas universalmente disponíveis nos computadores). Você pode encontrá-la no site da [W3Schools](https://www.w3schools.com/cssref/css_websafe_fonts.asp).
- Para a nomenclatura de classes e IDs, é considerada boa prática usar nomes que descrevam o propósito semântico do elemento.

## Referências

- MDN Web Docs. [S. l.], 

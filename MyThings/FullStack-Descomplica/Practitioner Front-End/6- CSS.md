
![[Pasted image 20241228171633.png]]

![[Pasted image 20241228171819.png]]

![[Pasted image 20241228172219.png]]

![[Pasted image 20241228172431.png]]



# CSS: Folhas de Estilo em Cascata

CSS, o acrônimo de _Cascading Style Sheets_, cuja tradução para português significa Folhas de estilo em cascata, é uma linguagem usada para formatar a apresentação de uma página em HTML no navegador. Os padrões desta linguagem são definidos pelo W3C, mesmo consórcio que define os padrões para a linguagem HTML.

## Objetivos da aula

- Definir o conceito de CSS;
- Discutir a estrutura básica do CSS;
- Identificar formas de implementar CSS.

## Resumo

### O que é o CSS e como é sua sintaxe

CSS foi criado em 1996 para remover da página HTML o estilo, que antes era atribuído por tags como `<font>`, um pesadelo para desenvolvedores, pois se aplicavam a cada elemento HTML. Para resolver esse problema, o _World Wide Web Consortium_ (W3C) criou o CSS, que economiza muito trabalho controlando o layout de várias páginas da web de uma só vez. Atualmente, o CSS está em sua terceira versão.

CSS é utilizado para:

- Definir cores, fontes, tamanhos de texto;
- Espaçamento entre elementos;
- Posicionamento dos elementos;
- Imagens de fundo ou cores de fundo;
- Variações de exibição para diferentes dispositivos e tamanhos de tela.

A palavra _cascata_ significa que um estilo aplicado a um elemento pai também se aplicá a todos os elementos filhos dentro do pai.

#### Estrutura da Sintaxe CSS

A sintaxe do CSS compõe-se de:

- Um **seletor**;
- Abertura de **chaves**;
- Declaração de **propriedade** e **valor**.

Exemplo:

```css
p {
  font-family: Verdana;
  font-size: 20px;
}
```

- **Seletor**: aponta para o elemento HTML que se deseja estilizar;
- **Bloco de declaração**: contém uma ou mais declarações separadas por ponto e vírgula;
- **Declaração**: inclui um nome de propriedade CSS e um valor, separados por dois pontos;
- Os blocos de declaração são cercados por chaves.

---

## Formas de adicionar CSS ao documento HTML

Existem três formas de adicionar CSS a uma página HTML:

### 1. Inline (em linha)

Um estilo embutido usado para aplicar um estilo único para um único elemento. Deve-se adicionar o atributo `style` ao elemento que se quer alterar e, dentro dele, definir as propriedades.

Exemplo:

```html
<p style="color: red; font-size: 20px;">Texto em vermelho com tamanho 20px</p>
```

### 2. Internal (interno)

O código CSS é definido na própria página HTML, dentro do elemento `<style>` dentro da seção `<head>`.

Exemplo:

```html
<head>
  <style>
    body {
      background-color: lightblue;
    }
  </style>
</head>
```

### 3. External (externo)

Um arquivo externo à página HTML que deve ser incluído via elemento `<link>` no cabeçalho da página. Com uma folha de estilo externa, você pode alterar a aparência de um site inteiro alterando apenas um arquivo.

Exemplo:

```html
<head>
  <link rel="stylesheet" href="style.css">
</head>
```

## Como aplicar na prática o que aprendeu

1. Vamos incluir em nosso projeto um arquivo externo de CSS.
2. Para isso, crie uma nova pasta dentro de seu projeto chamada `css`:
    - Clique com o botão direito na pasta do projeto no _VS Code_ e selecione _New folder_;
    - Nomeie a pasta como `css`.
3. Crie um arquivo `.css` dentro da pasta:
    - Clique com o botão direito sobre a pasta `css` criada e selecione _New file_;
    - Nomeie o arquivo como `style.css`.
4. Abra o arquivo `index.html` e adicione dentro da `<head>` a inclusão do arquivo CSS com o seguinte código:

```html
<head>
  <link rel="stylesheet" href="css/style.css">
</head>
```

5. No arquivo `style.css`, adicione o código para colorir o fundo da página de cinza:

```css
body {
  background-color: gray;
}
```

6. Adicione espaçamento entre as seções com o seguinte código:

```css
section {
  margin: 20px;
}
```

---

## Dica quente para você não esquecer

Você pode usar o [**W3C CSS Validation Service**](https://jigsaw.w3.org/css-validator/) para verificar se o seu CSS é válido. Essa é uma ferramenta indispensável para depuração:

[https://jigsaw.w3.org/css-validator/](https://jigsaw.w3.org/css-validator/)

---

## Referência Bibliográfica

- DEVELOPER. **CSS**. Disponível em: [https://developer.mozilla.org/pt-BR/docs/Web/CSS](https://developer.mozilla.org/pt-BR/docs/Web/CSS). Acesso em: 20 set. 2022.
- W3Schools is Powered by W3. **CSS Tutorial**. Disponível em: [https://www.w3schools.com/css/default.asp](https://www.w3schools.com/css/default.asp). Acesso em: 20 set. 2022.

Caro estudante, você consegue acessar os códigos utilizados na disciplina no link a seguir: [https://github.com/FaculdadeDescomplica/Practitioner_FrontEnd.git](https://github.com/FaculdadeDescomplica/Practitioner_FrontEnd.git)
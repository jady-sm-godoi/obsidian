### [[Algoritmos de Busca]]:

Os algoritmos de busca são usados para encontrar um elemento específico em uma coleção de dados. Existem várias técnicas de busca, incluindo busca linear, busca binária, busca em árvore, entre outras.

#### 1. Busca Linear:

A busca linear percorre todos os elementos na coleção de dados sequencialmente até encontrar o elemento desejado ou chegar ao final da coleção.

Exemplo em JavaScript:
``` 
function buscaLinear(arr, valor) {
    for (let i = 0; i < arr.length; i++) {
        if (arr[i] === valor) {
            return i; // Retorna o índice do valor encontrado
        }
    }
    return -1; // Retorna -1 se o valor não for encontrado
}

const lista = [3, 7, 1, 9, 4];
console.log(buscaLinear(lista, 9)); // Saída: 3
```

#### 2. Busca Binária:

A busca binária é uma técnica eficiente para encontrar um elemento em uma lista ordenada. Ela divide repetidamente a lista ao meio e compara o elemento do meio com o valor desejado.

Exemplo em JavaScript:
```
function buscaBinaria(arr, valor) {
    let inicio = 0;
    let fim = arr.length - 1;
    
    while (inicio <= fim) {
        let meio = Math.floor((inicio + fim) / 2);
        if (arr[meio] === valor) {
            return meio; // Retorna o índice do valor encontrado
        } else if (arr[meio] < valor) {
            inicio = meio + 1;
        } else {
            fim = meio - 1;
        }
    }
    return -1; // Retorna -1 se o valor não for encontrado
}

const listaOrdenada = [1, 3, 4, 7, 9];
console.log(buscaBinaria(listaOrdenada, 7)); // Saída: 3
```

### [[Algoritmos de Ordenação]]:

Os algoritmos de ordenação são usados para reorganizar os elementos em uma determinada ordem, como crescente ou decrescente.

#### 1. Ordenação por Bolha (Bubble Sort):

O algoritmo percorre a lista várias vezes, compara elementos adjacentes e os troca se estiverem na ordem errada.

Exemplo em JavaScript:
```
function bubbleSort(arr) {
    const n = arr.length;
    for (let i = 0; i < n - 1; i++) {
        for (let j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]]; // Troca os elementos
            }
        }
    }
    return arr;
}

const lista = [3, 1, 7, 4, 2];
console.log(bubbleSort(lista)); // Saída: [1, 2, 3, 4, 7]
```

#### 2. Ordenação por Inserção (Insertion Sort):

O algoritmo constrói uma lista ordenada um elemento de cada vez, inserindo cada novo elemento na posição correta.

Exemplo em JavaScript:
```
function insertionSort(arr) {
    const n = arr.length;
    for (let i = 1; i < n; i++) {
        let chave = arr[i];
        let j = i - 1;
        while (j >= 0 && arr[j] > chave) {
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = chave;
    }
    return arr;
}

const lista = [3, 1, 7, 4, 2];
console.log(insertionSort(lista)); // Saída: [1, 2, 3, 4, 7]
```
Esses são apenas alguns exemplos de algoritmos de busca e ordenação. Existem muitos outros algoritmos com diferentes eficiências e características. É importante escolher o algoritmo certo com base nos requisitos específicos do problema e nas propriedades dos dados a serem manipulados.
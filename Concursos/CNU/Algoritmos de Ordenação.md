### 1. Ordenação por Bolha (Bubble Sort):

- **Descrição**: Este algoritmo percorre repetidamente a lista, compara elementos adjacentes e os troca se estiverem na ordem errada.
- **Complexidade**: O(n^2) no pior caso.
- **Exemplo**:
```
def bubble_sort(lista):
    n = len(lista)
    for i in range(n):
        for j in range(0, n-i-1):
            if lista[j] > lista[j+1]:
                lista[j], lista[j+1] = lista[j+1], lista[j]  # Troca os elementos
    return lista

lista = [64, 34, 25, 12, 22, 11, 90]
print("Lista original:", lista)
print("Lista ordenada:", bubble_sort(lista))
```

### 2. Ordenação por Inserção (Insertion Sort):

- **Descrição**: Este algoritmo constrói uma lista ordenada um elemento de cada vez, inserindo cada novo elemento na posição correta.
- **Complexidade**: O(n^2) no pior caso.
- **Exemplo**:
```
def insertion_sort(lista):
    for i in range(1, len(lista)):
        chave = lista[i]
        j = i - 1
        while j >= 0 and chave < lista[j]:
            lista[j + 1] = lista[j]
            j -= 1
        lista[j + 1] = chave
    return lista

lista = [64, 34, 25, 12, 22, 11, 90]
print("Lista original:", lista)
print("Lista ordenada:", insertion_sort(lista))
```

### 3. Ordenação por Seleção (Selection Sort):

- **Descrição**: Este algoritmo divide a lista em duas partes: uma parte ordenada e uma parte não ordenada. Ele encontra o menor elemento da parte não ordenada e o move para a parte ordenada.
- **Complexidade**: O(n^2) no pior caso.
- **Exemplo**:
```
def selection_sort(lista):
    n = len(lista)
    for i in range(n):
        menor_indice = i
        for j in range(i+1, n):
            if lista[j] < lista[menor_indice]:
                menor_indice = j
        lista[i], lista[menor_indice] = lista[menor_indice], lista[i]  # Troca os elementos
    return lista

lista = [64, 34, 25, 12, 22, 11, 90]
print("Lista original:", lista)
print("Lista ordenada:", selection_sort(lista))
```
Esses são apenas alguns exemplos de algoritmos de ordenação. Existem muitos outros, cada um com suas próprias vantagens, desvantagens e complexidades. A escolha do algoritmo certo depende do tamanho dos dados, da eficiência desejada e de outras considerações específicas do problema.
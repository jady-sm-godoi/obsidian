### Lista Encadeada:

Uma lista encadeada é uma coleção de elementos onde cada elemento é um nó que contém um valor e uma referência (ou ponteiro) para o próximo nó na sequência. O último nó geralmente aponta para `null`, indicando o fim da lista. As operações básicas em uma lista encadeada incluem inserção, remoção e pesquisa.

```
Lista Encadeada: 3 -> 7 -> 12 -> 5 -> null
```

Nesta lista, cada nó possui um valor (como 3, 7, etc.) e uma referência para o próximo nó na sequência.

### Pilha:

Uma pilha é uma estrutura de dados na qual os elementos são adicionados e removidos de apenas uma extremidade, chamada de topo. Esta estrutura segue o princípio "último a entrar, primeiro a sair" (LIFO - Last In, First Out). As operações básicas em uma pilha incluem empurrar (push) um elemento para o topo e retirar (pop) um elemento do topo.

#### Exemplo:
```
Pilha: | 5 |
       | 3 |
       | 7 |
       -----
```
Nesta pilha, o elemento mais recentemente adicionado é 5, portanto é o topo. Quando um elemento é retirado, o próximo é 3.

### Fila:

Uma fila é uma estrutura de dados na qual os elementos são adicionados em uma extremidade (final) e removidos da outra extremidade (frente), seguindo o princípio "primeiro a entrar, primeiro a sair" (FIFO - First In, First Out). As operações básicas em uma fila incluem enfileirar (enqueue) um elemento no final e desenfileirar (dequeue) um elemento da frente.

#### Exemplo:
```
Fila:  | 3 | 7 | 12 | 5 |
        ----------------
```
Nesta fila, o elemento 3 está na frente (o primeiro a ser removido) e o elemento 5 está no final (o último a ser removido).

### Comparação:

- **Lista Encadeada**: Flexível, permite inserções e remoções em qualquer posição. O acesso a um elemento específico requer uma travessia a partir do início.
- **Pilha**: Ideal para aplicações como a implementação de chamadas de função, processamento de expressões matemáticas reversas (notação polonesa reversa).
- **Fila**: Útil em situações onde o acesso aos elementos segue uma ordem específica, como algoritmos de busca em largura (BFS - Breadth-First Search).
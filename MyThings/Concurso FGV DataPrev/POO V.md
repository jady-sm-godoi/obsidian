
## Pode um objeto ser uma subclasse de outro objeto?

A resposta correta é: **"Não, herança ocorre apenas entre as classes."**

### Explicação:

- **Herança** é um conceito fundamental da programação orientada a objetos (POO) e acontece **entre classes**, não entre objetos. Ou seja, uma classe pode ser uma subclasse de outra classe e herdar seus métodos e atributos.
    
- **Objetos** são instâncias de uma classe e, portanto, não podem ser subclasse de outro objeto diretamente. No entanto, é possível que um objeto utilize outro como parte de sua composição, mas isso não configura herança.
    

Se precisar de mais alguma explicação ou um exemplo prático, é só avisar!


## Qual o tipo de herança do Java?

A resposta correta é: **herança única**.

### Explicação:

- No **Java**, cada classe pode herdar de **apenas uma classe** (herança única), ou seja, não existe suporte para **herança múltipla de classes**.
- No entanto, Java permite que uma classe implemente múltiplas **interfaces**, o que simula a herança múltipla em certos cenários.

Essa abordagem evita problemas como o **diamante da herança**, comum em linguagens que permitem herança múltipla, como C++.
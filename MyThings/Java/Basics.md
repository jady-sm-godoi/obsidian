

---

**Java** é uma linguagem de programação de **tipagem estática**, o que significa que o tipo de uma variável é conhecido e verificado em tempo de compilação. Isso evita erros relacionados a tipos durante a execução.

Para definir uma variável, é necessário especificar explicitamente seu tipo:

```java
int explicitVar = 10;
```

Após declarar uma variável com um tipo, este tipo **não pode ser alterado**.

Além disso, Java é uma linguagem **orientada a objetos**. Isso implica que todo o código deve estar encapsulado em classes, e as funções definidas dentro dessas classes são chamadas de **métodos**.

- Um método pode receber **zero ou mais parâmetros**, e todos os parâmetros devem ter seus tipos especificados.
- O método também deve declarar o **tipo de dado que ele retorna**. Caso o método não retorne nenhum valor, utiliza-se o tipo `void`.

Por padrão, um método só pode ser acessado por outras classes se for declarado como **`public`**:

```java
class Calculator {
    public int add(int x, int y) {
        return x + y;
    }
}
```

Para chamar um método, é necessário instanciar a classe (caso o método não seja estático) e passar os argumentos esperados:

```java
Calculator calculator = new Calculator(); // Instanciação da classe
int sum = calculator.add(1, 2);           // Chamada do método com argumentos
```

---
# Strings

Em **Java**, uma `String` é um objeto que representa uma **sequência de caracteres** e é **imutável**. Isso significa que, uma vez criada, o conteúdo de uma string **não pode ser alterado**. Sempre que parece que uma `String` está sendo modificada, na realidade, uma nova instância de `String` é criada para representar o resultado.

---

### **Por que Strings são imutáveis?**

- Imutabilidade melhora a **segurança** e a **performance** em operações que envolvem múltiplas threads.
- Strings são amplamente utilizadas como chaves em estruturas como `HashMap`, e a imutabilidade ajuda a garantir que o valor da chave não seja alterado.

---

### **Manipulação de Strings**

A manipulação de `Strings` é feita utilizando métodos disponíveis na classe `String`. Como Strings são imutáveis, esses métodos sempre retornam uma nova instância da `String`.

#### **Principais Métodos da Classe `String` com Exemplos**

1. **`length()`**  
    Retorna o comprimento da string:
    
    ```java
    String text = "Java";
    int size = text.length(); // Resultado: 4
    ```
    
2. **`charAt(int index)`**  
    Retorna o caractere no índice especificado:
    
    ```java
    char first = text.charAt(0); // Resultado: 'J'
    ```
    
3. **`toUpperCase()` e `toLowerCase()`**  
    Converte a string para maiúsculas ou minúsculas:
    
    ```java
    String upper = text.toUpperCase(); // Resultado: "JAVA"
    String lower = text.toLowerCase(); // Resultado: "java"
    ```
    
4. **`substring(int beginIndex, int endIndex)`**  
    Retorna uma substring (parte da string):
    
    ```java
    String part = text.substring(1, 3); // Resultado: "av"
    ```
    
5. **`concat(String str)`**  
    Concatena (une) duas strings:
    
    ```java
    String full = text.concat(" Programming"); // Resultado: "Java Programming"
    ```
    
6. **`trim()`**  
    Remove espaços em branco no início e no fim da string:
    
    ```java
    String withSpaces = "   Java   ";
    String trimmed = withSpaces.trim(); // Resultado: "Java"
    ```
    
7. **`replace(char oldChar, char newChar)`**  
    Substitui todos os caracteres especificados por outro:
    
    ```java
    String replaced = text.replace('a', 'o'); // Resultado: "Jovo"
    ```
    
8. **`split(String regex)`**  
    Divide a string em um array com base em um delimitador:
    
    ```java
    String sentence = "Java is great";
    String[] words = sentence.split(" "); // Resultado: ["Java", "is", "great"]
    ```
    
9. **`contains(CharSequence s)`**  
    Verifica se a string contém a sequência especificada:
    
    ```java
    boolean hasJava = text.contains("va"); // Resultado: true
    ```
    
10. **`startsWith(String prefix)` e `endsWith(String suffix)`**  
    Verifica se a string começa ou termina com o valor especificado:
    
    ```java
    boolean starts = text.startsWith("Ja"); // Resultado: true
    boolean ends = text.endsWith("va");    // Resultado: true
    ```
    

---

### **Imutabilidade em Ação**

```java
public class Main {
    public static void main(String[] args) {
        String original = "Hello";
        String modified = original.concat(" World");

        System.out.println(original); // Resultado: "Hello"
        System.out.println(modified); // Resultado: "Hello World"
    }
}
```

Neste exemplo, a string original não é alterada. Uma nova string é criada ao usar o método `concat()`.

---

### **Quando usar Strings ou `StringBuilder`**

- Use `String` para **textos pequenos e imutáveis**.
- Use `StringBuilder` ou `StringBuffer` para **operações intensivas de manipulação de texto**, pois eles são mutáveis e oferecem melhor performance.

Exemplo com `StringBuilder`:

```java
StringBuilder sb = new StringBuilder("Java");
sb.append(" Programming");
System.out.println(sb.toString()); // Resultado: "Java Programming"
```

Com esses métodos e conceitos, você pode trabalhar eficientemente com strings em Java!
Em Java, as **coleções** são estruturas que permitem armazenar e manipular conjuntos de dados de forma eficiente. As principais interfaces de coleções são **List**, **Set** e **Map**, e elas têm implementações populares como `ArrayList`, `HashSet` e `HashMap`. Vamos explicar cada uma com exemplos.

---

### **1. List**
- **Características:**
  - Uma **List** é uma coleção ordenada de elementos que permite duplicatas.
  - Acesso por índice.
  - Principal implementação: `ArrayList`.

#### **Exemplo: Uso de `ArrayList`**
```java
import java.util.ArrayList;

public class ListExample {
    public static void main(String[] args) {
        ArrayList<String> fruits = new ArrayList<>();
        
        // Adicionando elementos
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Apple"); // Duplicata permitida
        
        // Iterando
        for (String fruit : fruits) {
            System.out.println(fruit);
        }
        
        // Acesso por índice
        System.out.println("Primeira fruta: " + fruits.get(0)); // Apple
        
        // Remoção
        fruits.remove("Banana");
        System.out.println("Após remoção: " + fruits);
    }
}
```
**Saída:**
```
Apple
Banana
Apple
Primeira fruta: Apple
Após remoção: [Apple, Apple]
```

---

### **2. Set**
- **Características:**
  - Um **Set** é uma coleção que **não permite elementos duplicados**.
  - Não garante ordem (a depender da implementação).
  - Principal implementação: `HashSet`.

#### **Exemplo: Uso de `HashSet`**
```java
import java.util.HashSet;

public class SetExample {
    public static void main(String[] args) {
        HashSet<String> cities = new HashSet<>();
        
        // Adicionando elementos
        cities.add("New York");
        cities.add("London");
        cities.add("New York"); // Ignorado, pois é duplicado
        
        // Iterando
        for (String city : cities) {
            System.out.println(city);
        }
        
        // Verificando existência
        System.out.println("Contém London? " + cities.contains("London")); // true
        
        // Remoção
        cities.remove("London");
        System.out.println("Após remoção: " + cities);
    }
}
```
**Saída:**
```
New York
London
Contém London? true
Após remoção: [New York]
```

---

### **3. Map**
- **Características:**
  - Um **Map** é uma estrutura que armazena pares de chave-valor.
  - As chaves devem ser únicas, mas os valores podem se repetir.
  - Principal implementação: `HashMap`.

#### **Exemplo: Uso de `HashMap`**
```java
import java.util.HashMap;

public class MapExample {
    public static void main(String[] args) {
        HashMap<String, Integer> ages = new HashMap<>();
        
        // Adicionando pares chave-valor
        ages.put("Alice", 25);
        ages.put("Bob", 30);
        ages.put("Alice", 26); // Substitui o valor anterior
        
        // Iterando
        for (String name : ages.keySet()) {
            System.out.println(name + " tem " + ages.get(name) + " anos.");
        }
        
        // Acesso por chave
        System.out.println("Idade de Bob: " + ages.get("Bob")); // 30
        
        // Remoção
        ages.remove("Alice");
        System.out.println("Após remoção: " + ages);
    }
}
```
**Saída:**
```
Alice tem 26 anos.
Bob tem 30 anos.
Idade de Bob: 30
Após remoção: {Bob=30}
```

---

### **Diferenças Resumidas**
| Característica         | List (`ArrayList`)         | Set (`HashSet`)         | Map (`HashMap`)             |
|------------------------|---------------------------|-------------------------|-----------------------------|
| Permite duplicatas     | Sim                       | Não                     | Chaves: Não, Valores: Sim  |
| Ordem garantida        | Sim                       | Não                     | Não                        |
| Acesso por índice      | Sim                       | Não                     | Não                        |
| Par chave-valor        | Não                       | Não                     | Sim                        |

---

### **Casos de Uso**
- **List**: Quando você precisa de uma coleção ordenada e permite duplicatas (ex.: lista de tarefas).
- **Set**: Quando você quer evitar duplicatas (ex.: lista de usuários únicos).
- **Map**: Quando precisa associar chaves a valores (ex.: dicionário de configurações).

Esses exemplos cobrem os conceitos básicos e mostram como usar cada tipo de coleção.
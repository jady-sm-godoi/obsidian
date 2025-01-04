Aqui está um guia detalhado para você implementar uma solução em Java para os itens mencionados:

---

### **Passo 1: Criação da classe `Funcionario`**
1. **Definição da classe:**
   - Uma classe é um molde para criar objetos. Aqui, criamos uma classe chamada `Funcionario` com os atributos `nome`, `salario` e `cargo`.

2. **Definição dos atributos:**
   - Use o modificador `private` para encapsular os dados, ou seja, proteger os atributos de acessos externos diretos.
   - Os atributos serão:
     - `nome` (tipo `String`): para armazenar o nome do funcionário.
     - `salario` (tipo `double`): para armazenar o salário do funcionário.
     - `cargo` (tipo `String`): para indicar o cargo do funcionário.

3. **Criar um construtor:**
   - Um construtor facilita a criação de objetos, inicializando os atributos com valores.

4. **Criar métodos `get` e `set`:**
   - Permitem acessar e modificar os atributos de forma controlada.

#### Código:
```java
public class Funcionario {
    private String nome;
    private double salario;
    private String cargo;

    // Construtor
    public Funcionario(String nome, double salario, String cargo) {
        this.nome = nome;
        this.salario = salario;
        this.cargo = cargo;
    }

    // Getters e Setters
    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }

    public double getSalario() {
        return salario;
    }

    public void setSalario(double salario) {
        this.salario = salario;
    }

    public String getCargo() {
        return cargo;
    }

    public void setCargo(String cargo) {
        this.cargo = cargo;
    }
}
```

---

### **Passo 2: Implementar um método para calcular o bônus salarial**
1. **Criar o método `calcularBonus`:**
   - O bônus será um percentual do salário. Por exemplo, 10%.
   - Retorne o valor do bônus sem alterar o salário original.

#### Código:
```java
public double calcularBonus(double percentual) {
    return salario * percentual / 100;
}
```

2. **Atualizar a classe `Funcionario` com o método:**
   - Adicione o método dentro da classe, junto com os outros métodos.

---

### **Passo 3: Utilizar coleções para armazenar funcionários e buscar por cargo**
1. **Criação de uma lista de funcionários:**
   - Use a classe `ArrayList`, que é uma implementação da interface `List` em Java. Ela permite armazenar e manipular objetos do tipo `Funcionario`.

2. **Adição de objetos `Funcionario`:**
   - Utilize o método `add` para adicionar funcionários à lista.

3. **Buscar funcionários por cargo:**
   - Crie um método que itera pela lista e verifica o cargo de cada funcionário.
   - Retorne uma nova lista contendo todos os funcionários com o cargo desejado.

#### Código:
```java
import java.util.ArrayList;
import java.util.List;

public class Empresa {
    public static void main(String[] args) {
        // Criação da lista de funcionários
        List<Funcionario> funcionarios = new ArrayList<>();

        // Adicionando funcionários à lista
        funcionarios.add(new Funcionario("Alice", 5000.0, "Desenvolvedor"));
        funcionarios.add(new Funcionario("Bob", 7000.0, "Gerente"));
        funcionarios.add(new Funcionario("Carol", 4500.0, "Desenvolvedor"));

        // Buscar funcionários por cargo
        String cargoBuscado = "Desenvolvedor";
        List<Funcionario> desenvolvedores = buscarPorCargo(funcionarios, cargoBuscado);

        // Exibir funcionários encontrados
        System.out.println("Funcionários com cargo " + cargoBuscado + ":");
        for (Funcionario f : desenvolvedores) {
            System.out.println(f.getNome() + " - Salário: " + f.getSalario());
        }
    }

    public static List<Funcionario> buscarPorCargo(List<Funcionario> funcionarios, String cargo) {
        List<Funcionario> resultado = new ArrayList<>();
        for (Funcionario f : funcionarios) {
            if (f.getCargo().equalsIgnoreCase(cargo)) {
                resultado.add(f);
            }
        }
        return resultado;
    }
}
```

---

### **Execução do programa**
1. **Explicação do que acontece:**
   - A lista `funcionarios` é criada e preenchida com objetos da classe `Funcionario`.
   - O método `buscarPorCargo` percorre a lista, verifica o atributo `cargo` de cada funcionário e retorna aqueles que correspondem ao cargo desejado.
   - O resultado é impresso no console.

2. **Exemplo de saída:**
```
Funcionários com cargo Desenvolvedor:
Alice - Salário: 5000.0
Carol - Salário: 4500.0
```

---

### **Pontos importantes para estudar:**
- **Estruturas de classes e métodos.**
- **Encapsulamento e uso de `getters` e `setters`.**
- **Uso da classe `ArrayList` para coleções.**
- **Iteração em listas com `for-each`.**
- **Comparação de `String` com `equalsIgnoreCase` para evitar problemas de sensibilidade ao caso.**

Se precisar de mais explicações ou ajustes, é só pedir! 😊
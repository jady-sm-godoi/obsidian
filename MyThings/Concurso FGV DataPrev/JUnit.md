
No JUnit, **teste unitário** é um tipo de teste que se concentra em testar uma única unidade de código, geralmente um método ou uma função, de forma isolada. O objetivo é verificar se a unidade de código se comporta como esperado.

### **Conceitos Essenciais de JUnit**

#### 1. **Estrutura de um Teste Unitário**

Um teste unitário no JUnit é composto por três partes principais, que são:

1. **Preparação (Setup):** Nesta etapa, você prepara o ambiente do teste, criando objetos e configurando dados necessários para o teste.
   
2. **Execução (Action):** Executa o código que está sendo testado. Isso pode ser a chamada de um método de uma classe.

3. **Verificação (Assertion):** Verifica se o resultado obtido após a execução do código é o esperado.

#### 2. **Exemplo de Teste Unitário com JUnit**

Abaixo, segue um exemplo simples de teste unitário utilizando o **JUnit 5** (versão mais recente).

Suponha que você tenha uma classe `Calculadora` com um método para somar dois números:

```java
public class Calculadora {
    public int somar(int a, int b) {
        return a + b;
    }
}
```

Agora, você quer criar um teste unitário para garantir que o método `somar` funciona corretamente.

##### **Estrutura do Teste**
- **@Test**: Essa anotação diz ao JUnit que o método é um teste.
- **assertEquals(expected, actual)**: Verifica se o valor esperado (expected) é igual ao valor real (actual) retornado pela execução do código.

```java
import static org.junit.jupiter.api.Assertions.assertEquals;
import org.junit.jupiter.api.Test;

public class CalculadoraTest {

    @Test
    public void testSomar() {
        // Preparação
        Calculadora calculadora = new Calculadora();
        
        // Execução
        int resultado = calculadora.somar(2, 3);
        
        // Verificação
        assertEquals(5, resultado, "A soma de 2 e 3 deve ser 5");
    }
}
```

#### **Explicação do Exemplo**
1. **Preparação:** Criamos uma instância da classe `Calculadora`.
2. **Execução:** Chamamos o método `somar(2, 3)` e armazenamos o resultado na variável `resultado`.
3. **Verificação:** Usamos o método `assertEquals(5, resultado)` para garantir que o valor retornado pelo método `somar` seja igual a 5.

#### 3. **Estrutura do Teste**
No JUnit, a estrutura básica de um teste unitário segue o padrão:

```java
@Test
public void nomeDoTeste() {
    // Preparação: configurar o que é necessário para o teste
    // Execução: chamar o método que está sendo testado
    // Verificação: usar assertivas (asserts) para validar o resultado
}
```

#### 4. **Assertivas Comuns**
As **assertivas** são usadas para verificar se o comportamento do código está correto. Algumas das mais comuns incluem:

- **assertEquals(expected, actual):** Verifica se o valor esperado é igual ao valor obtido.
- **assertNotEquals(expected, actual):** Verifica se o valor esperado não é igual ao valor obtido.
- **assertTrue(condition):** Verifica se a condição é verdadeira.
- **assertFalse(condition):** Verifica se a condição é falsa.
- **assertNull(value):** Verifica se o valor é `null`.
- **assertNotNull(value):** Verifica se o valor não é `null`.

#### 5. **Execução dos Testes**

Você pode executar os testes de diferentes maneiras, dependendo da sua IDE ou da ferramenta de linha de comando que estiver usando. Em uma IDE como IntelliJ IDEA ou Eclipse, você pode simplesmente clicar com o botão direito no arquivo de teste e selecionar a opção para rodar os testes. Caso use Maven ou Gradle, você pode rodar os testes com comandos como `mvn test` ou `gradle test`.

#### 6. **Boas Práticas**
- **Isolamento:** Cada teste deve ser independente dos outros. Ou seja, o sucesso ou falha de um teste não deve afetar os outros.
- **Legibilidade:** O nome do método de teste deve ser claro e descritivo, indicando qual é o comportamento que está sendo testado.
- **Simulação (Mocking):** Para testar unidades de código isoladas, você pode usar mocks (simulações de dependências) quando o método que está sendo testado depende de outros objetos.

### **Conclusão**

Um teste unitário no JUnit é uma maneira de garantir que o código que você escreve funciona como esperado. A estrutura básica inclui preparação, execução e verificação dos resultados, com o uso de assertivas para validar os resultados. JUnit é uma das ferramentas mais poderosas para realizar testes automatizados e garantir a qualidade do software.
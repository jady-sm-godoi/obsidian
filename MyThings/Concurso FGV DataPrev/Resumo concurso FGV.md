Aqui está um **material de estudo estratégico** que você pode usar para revisar os principais temas do edital com foco na regra **80/20**. Este material inclui explicações, exemplos e exercícios práticos para consolidar o aprendizado.

---

## **1. Desenvolvimento de Sistemas**

### **Java (versão 6+)**
#### **Conceitos essenciais:**
- **[[POO (Programação Orientada a Objetos)]]:**
  - Classes, objetos, herança, polimorfismo, abstração e encapsulamento.
- **[[Coleções]]:**
  - List, Set e Map (`ArrayList`, `HashSet`, `HashMap`).
- **[[Tratamento de Exceções]]:**
  ```java
  try {
      // Código que pode gerar exceção
  } catch (Exception e) {
      // Tratamento da exceção
  }
  ```

#### **[[Exercício prático Java]] :**
1. Crie uma classe `Funcionario` com atributos como `nome`, `salario` e `cargo`.
2. Implemente um método para calcular um bônus salarial.
3. Utilize coleções para armazenar funcionários e buscar por cargo.

---

### **Spring e Spring Boot**
#### **Conceitos essenciais:**
- **[[Injeção de Dependência (IoC)]]:**
  ```java
  @Service
  public class MyService {
      // Lógica do serviço
  }
  ```
- **[[Criação de APIs REST]]:**
  ```java
  @RestController
  @RequestMapping("/api")
  public class MyController {
      @GetMapping("/hello")
      public String sayHello() {
          return "Hello World!";
      }
  }
  ```

#### **[[Exercício prático Spring Boot]]:**
1. Configure um projeto Spring Boot com Maven.
2. Crie uma API REST simples que retorna uma lista de produtos.

---

### **APIs e [[Swagger]]**
#### **Conceitos essenciais:**
- **APIs RESTful:** Métodos HTTP (GET, POST, PUT, DELETE).
- **Documentação com Swagger:**
  Adicione a dependência:
  ```xml
  <dependency>
      <groupId>io.springfox</groupId>
      <artifactId>springfox-boot-starter</artifactId>
      <version>3.0.0</version>
  </dependency>
  ```

#### **Exercício prático:**
1. Adicione Swagger ao seu projeto Spring Boot.
2. Documente os endpoints de uma API.

---

## **2. Testes**

### **[[JUnit]]**
#### **Conceitos essenciais:**
- Estrutura de um teste unitário:
  ```java
  @Test
  public void testMethod() {
      assertEquals(4, 2 + 2);
  }
  ```

#### **Exercício prático:**
1. Implemente testes para métodos em uma classe `Calculadora` que somam e subtraem números.

---

### **TDD (Test-Driven Development)**
- **Passos:**
  1. Escreva um teste que falha.
  2. Implemente o código mínimo para passar no teste.
  3. Refatore.

---

## **3. Metodologias Ágeis**

### **Scrum**
#### **Conceitos essenciais:**
- Papéis: Scrum Master, Product Owner, Time de Desenvolvimento.
- Artefatos: Backlog do Produto, Backlog da Sprint.
- Eventos: Reunião diária, Sprint Review.

#### **Exercício prático:**
1. Crie um quadro fictício de Scrum com tarefas de um projeto simples.

---

## **4. Segurança da Informação**

### **[[OWASP Top 10]]**
#### **Principais vulnerabilidades:**
- **Injeção SQL:** Evite concatenar strings no SQL; use parâmetros preparados:
  ```java
  String query = "SELECT * FROM users WHERE username = ?";
  PreparedStatement stmt = connection.prepareStatement(query);
  stmt.setString(1, "user");
  ```

#### **Exercício prático:**
1. Identifique vulnerabilidades no código SQL de um exemplo fictício e corrija.

---

### **[[OAuth2]]**
- **Conceito:** Um protocolo para autorização segura de APIs.
- **Exemplo:** Implementação de autenticação com tokens de acesso.

---

## **5. Banco de Dados**

### **[[SQL Básico]]**
#### **Comandos essenciais:**
- **SELECT com JOIN:**
  ```sql
  SELECT employees.name, departments.name 
  FROM employees 
  JOIN departments ON employees.department_id = departments.id;
  ```

#### **Exercício prático:**
1. Crie duas tabelas relacionadas (ex.: funcionários e departamentos).
2. Realize consultas utilizando `JOIN`.

---

### **ETL (Extract, Transform, Load)**
- Extraia dados de um arquivo CSV, transforme-os e insira-os em uma tabela.

---

## **6. Tecnologias Front-end**

### **HTML e CSS**
#### **Conceitos essenciais:**
- Estrutura básica de uma página:
  ```html
  <html>
      <head>
          <title>Exemplo</title>
      </head>
      <body>
          <h1>Olá, Mundo!</h1>
      </body>
  </html>
  ```

#### **Exercício prático:**
1. Crie uma página HTML simples com estilos em CSS para exibir um portfólio.

---

## **7. Arquitetura e DevOps**

### **[[Arquitetura Hexagonal]]**
- **Conceito:** Separação de lógica de domínio, infraestrutura e interfaces.
- **Exemplo:** Divida um projeto em módulos com responsabilidades claras.

### **GIT**
#### **Comandos básicos:**
```bash
git init
git add .
git commit -m "Início do projeto"
git push origin main
```

#### **Exercício prático:**
1. Crie um repositório GIT local e faça commits de um projeto simples.

---

## **Resumo Prioritário**
1. **Desenvolvimento com Java e Spring Boot.**
2. **Conceitos de APIs REST e Swagger.**
3. **Testes com JUnit e práticas de TDD.**
4. **Scrum e gerenciamento ágil.**
5. **Segurança (OWASP) e GIT.**
6. **SQL (joins e consultas básicas).**

Prepare-se revisando os exemplos e fazendo pequenos projetos para reforçar a prática! 🚀
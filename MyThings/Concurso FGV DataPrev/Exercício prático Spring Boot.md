
Vamos abordar em detalhes cada passo para configurar um **projeto Spring Boot com Maven** e criar uma **API REST simples que retorna uma lista de produtos**.

### **Passo 1: Configurar um Projeto Spring Boot com Maven**

#### 1.1. **Criando o Projeto**
O primeiro passo é criar o projeto Spring Boot. Uma maneira fácil de fazer isso é usando o **Spring Initializr** (https://start.spring.io/), que gera o esqueleto do projeto.

1. Acesse [Spring Initializr](https://start.spring.io/).
2. Preencha as informações do projeto:
   - **Project:** Maven Project
   - **Language:** Java
   - **Spring Boot:** Escolha a versão estável mais recente (ex.: 2.x.x)
   - **Group:** com.exemplo (pode usar o nome do seu domínio ou algo único)
   - **Artifact:** produto-api
   - **Name:** ProdutoApi (nome do seu projeto)
   - **Packaging:** Jar
   - **Java:** 17 (ou a versão que você estiver utilizando)
   
3. Selecione as dependências necessárias:
   - **Spring Web** (para criar a API REST)
   - **Spring Boot DevTools** (opcional, mas útil para reinicialização rápida no desenvolvimento)
   - **Spring Data JPA** (caso queira salvar dados em um banco de dados, mas não será necessário neste exemplo simples)
   
4. Clique em **Generate** para baixar o projeto gerado.

#### 1.2. **Abrindo o Projeto**
Depois de fazer o download, descompacte o arquivo e abra a pasta do projeto em uma IDE como **IntelliJ IDEA** ou **Eclipse**. Você verá a estrutura do projeto Maven com um arquivo `pom.xml` que gerencia as dependências.

#### 1.3. **Verificando o arquivo `pom.xml`**
Abra o arquivo `pom.xml` e verifique se as dependências estão corretas. Ele deve se parecer com isto:

```xml
<dependencies>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-web</artifactId>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-devtools</artifactId>
        <scope>runtime</scope>
    </dependency>
</dependencies>
```

### **Passo 2: Criar a API REST Simples**

Agora que o projeto está configurado, vamos criar a API REST.

#### 2.1. **Criando a Classe `Produto`**
Vamos começar criando a classe `Produto`, que será um modelo de dados simples.

1. Crie um novo arquivo Java dentro do pacote principal `com.exemplo.produtoapi` (ou o nome que você escolheu).
2. Defina a classe `Produto`:

```java
package com.exemplo.produtoapi.model;

public class Produto {
    private String nome;
    private double preco;

    // Construtor
    public Produto(String nome, double preco) {
        this.nome = nome;
        this.preco = preco;
    }

    // Getters e Setters
    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }

    public double getPreco() {
        return preco;
    }

    public void setPreco(double preco) {
        this.preco = preco;
    }
}
```

#### 2.2. **Criando o Controlador (Controller)**
Agora, vamos criar a parte da **API REST** que irá expor os produtos.

1. Crie uma classe chamada `ProdutoController` no mesmo pacote `com.exemplo.produtoapi`:

```java
package com.exemplo.produtoapi.controller;

import com.exemplo.produtoapi.model.Produto;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

import java.util.ArrayList;
import java.util.List;

@RestController
@RequestMapping("/api/produtos")
public class ProdutoController {

    @GetMapping
    public List<Produto> getProdutos() {
        // Cria uma lista simples de produtos
        List<Produto> produtos = new ArrayList<>();
        produtos.add(new Produto("Produto 1", 100.0));
        produtos.add(new Produto("Produto 2", 150.0));
        produtos.add(new Produto("Produto 3", 200.0));

        return produtos;
    }
}
```

#### Explicação do Código:
- **@RestController:** Indica que esta classe é um controlador que irá lidar com requisições HTTP e retornar os resultados diretamente como resposta JSON.
- **@RequestMapping("/api/produtos"):** Mapeia o endpoint base `/api/produtos` para essa classe.
- **@GetMapping:** Define que o método `getProdutos()` será chamado quando uma requisição HTTP GET for feita no endpoint `/api/produtos`.
- **List<Produto> getProdutos():** Retorna uma lista de produtos (simulada no código) como resposta da API.

#### 2.3. **Executando o Projeto**

Agora que tudo está configurado, você pode rodar o projeto.

1. Vá para o arquivo principal do projeto `ProdutoApiApplication.java`. Ele deve estar localizado no pacote `com.exemplo.produtoapi`.
2. O código do arquivo `ProdutoApiApplication.java` deve ser o seguinte:

```java
package com.exemplo.produtoapi;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class ProdutoApiApplication {

    public static void main(String[] args) {
        SpringApplication.run(ProdutoApiApplication.class, args);
    }
}
```

3. Clique com o botão direito no arquivo `ProdutoApiApplication.java` e execute a classe como uma aplicação Java.

#### 2.4. **Testando a API**

Agora que o projeto está em execução, você pode testar a API.

1. Abra o navegador ou uma ferramenta como **Postman**.
2. Faça uma requisição GET para a URL:
   ```
   http://localhost:8080/api/produtos
   ```
3. Você deverá ver a resposta em formato JSON, algo como:

```json
[
  {
    "nome": "Produto 1",
    "preco": 100.0
  },
  {
    "nome": "Produto 2",
    "preco": 150.0
  },
  {
    "nome": "Produto 3",
    "preco": 200.0
  }
]
```

### **Conclusão**

Com esses passos, você configurou um **projeto Spring Boot** simples com Maven e criou uma **API REST** que retorna uma lista de produtos. Você pode expandir essa API adicionando funcionalidades como persistência em banco de dados, validação, e outros endpoints.
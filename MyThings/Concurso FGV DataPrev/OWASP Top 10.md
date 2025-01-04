
A **Injeção SQL** (SQL Injection) é uma das vulnerabilidades mais comuns e críticas no desenvolvimento de aplicações. Ela ocorre quando um atacante consegue inserir ou manipular consultas SQL (Structured Query Language) de forma maliciosa, aproveitando-se da falta de validação ou filtragem correta de dados fornecidos pelo usuário.

### **Conceito de Injeção SQL**
Quando você constrói uma consulta SQL a partir de dados fornecidos pelo usuário (como valores de formulários ou parâmetros de URL), se esses dados não forem corretamente tratados, um atacante pode "injectar" comandos SQL maliciosos. Isso pode permitir que o atacante:
- **Exporte dados** sensíveis (como informações de usuários ou credenciais).
- **Modifique dados** no banco de dados (como alterar ou excluir informações).
- **Execute comandos maliciosos**, prejudicando o funcionamento da aplicação.

### **Exemplo de Injeção SQL**
Imagine o seguinte código em uma aplicação Java que consulta um banco de dados:

```java
String sql = "SELECT * FROM usuarios WHERE username = '" + username + "' AND password = '" + password + "'";
```

Aqui, se um usuário fornecer um valor como `username = "admin"` e `password = "' OR '1'='1"`, o SQL gerado será:

```sql
SELECT * FROM usuarios WHERE username = 'admin' AND password = '' OR '1'='1';
```

Esse SQL retorna todos os registros, permitindo que o atacante faça login como qualquer usuário, sem conhecer a senha.

### **Como Evitar a Injeção SQL**
A principal estratégia para prevenir injeções SQL é **não concatenar valores diretamente nas consultas SQL**. Em vez disso, você deve usar **parâmetros preparados** ou **prepared statements**, que garantem que os dados fornecidos pelo usuário sejam tratados como valores, e não como parte do código SQL.

#### **Exemplo Usando Parâmetros Preparados (Prepared Statements)**

Aqui está o código corrigido usando parâmetros preparados:

```java
String sql = "SELECT * FROM usuarios WHERE username = ? AND password = ?";
PreparedStatement statement = connection.prepareStatement(sql);
statement.setString(1, username);
statement.setString(2, password);
ResultSet resultSet = statement.executeQuery();
```

### **Como Funciona?**
1. **Prepared Statements**: Em vez de concatenar valores diretamente na consulta SQL, usamos **`?`** como placeholders. Esses placeholders serão substituídos com os valores fornecidos pelo usuário de forma segura.
2. **Escapando os dados**: O framework ou a API utilizada escapa automaticamente os dados do usuário, prevenindo que o código malicioso seja interpretado como parte da consulta SQL.

### **Boas Práticas Adicionais**
- **Validação e Filtragem de Entrada**: Sempre valide e filtre os dados de entrada do usuário para garantir que eles estão no formato esperado (ex.: números, e-mails, etc.).
- **Privilégios Mínimos**: Configure o banco de dados de forma que as contas de usuário não tenham permissões desnecessárias (ex.: eliminar ou modificar dados que não são necessários para a aplicação).
- **Uso de ORM (Object-Relational Mapping)**: Frameworks ORM (como Hibernate ou JPA) ajudam a construir consultas de forma mais segura, evitando a necessidade de escrever SQL manualmente.

### **Conclusão**
A Injeção SQL é uma vulnerabilidade grave, mas pode ser evitada com práticas simples como o uso de **parâmetros preparados**. Sempre que possível, utilize bibliotecas ou frameworks que abstraem o acesso ao banco de dados e protejam a sua aplicação de ataques do tipo SQL Injection.
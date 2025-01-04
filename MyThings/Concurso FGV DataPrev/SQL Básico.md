Vamos explorar os **conceitos essenciais** sobre **SQL**, com foco em **comandos essenciais** e **SELECT com JOIN**, para que você tenha uma base sólida no aprendizado.

### **1. Comandos Essenciais de SQL**

#### **1.1. SELECT**
O comando `SELECT` é utilizado para consultar dados em uma tabela do banco de dados. Ele é o comando mais básico e importante em SQL.

**Sintaxe:**
```sql
SELECT coluna1, coluna2, ...
FROM tabela;
```

- **coluna1, coluna2, ...**: São os nomes das colunas que você deseja consultar.
- **tabela**: O nome da tabela da qual você deseja obter os dados.

**Exemplo:**
```sql
SELECT nome, preco FROM produtos;
```
Este comando retorna as colunas `nome` e `preco` da tabela `produtos`.

#### **1.2. WHERE**
O comando `WHERE` é usado para filtrar os dados com base em uma condição específica.

**Sintaxe:**
```sql
SELECT coluna1, coluna2, ...
FROM tabela
WHERE condicao;
```

**Exemplo:**
```sql
SELECT nome, preco FROM produtos WHERE preco > 100;
```
Isso retorna todos os produtos cujo preço seja maior que 100.

#### **1.3. INSERT**
O comando `INSERT` é utilizado para adicionar dados em uma tabela.

**Sintaxe:**
```sql
INSERT INTO tabela (coluna1, coluna2, ...)
VALUES (valor1, valor2, ...);
```

**Exemplo:**
```sql
INSERT INTO produtos (nome, preco) VALUES ('Produto X', 50.0);
```
Este comando adiciona um novo produto com nome 'Produto X' e preço 50.0 à tabela `produtos`.

#### **1.4. UPDATE**
O comando `UPDATE` é utilizado para modificar os dados existentes em uma tabela.

**Sintaxe:**
```sql
UPDATE tabela
SET coluna1 = valor1, coluna2 = valor2, ...
WHERE condicao;
```

**Exemplo:**
```sql
UPDATE produtos SET preco = 120 WHERE nome = 'Produto X';
```
Este comando atualiza o preço do 'Produto X' para 120.

#### **1.5. DELETE**
O comando `DELETE` é utilizado para excluir dados de uma tabela.

**Sintaxe:**
```sql
DELETE FROM tabela WHERE condicao;
```

**Exemplo:**
```sql
DELETE FROM produtos WHERE nome = 'Produto X';
```
Isso remove o produto chamado 'Produto X' da tabela `produtos`.

---

### **2. SELECT com JOIN**

#### **2.1. O que é JOIN?**
`JOIN` é um comando utilizado para combinar dados de duas ou mais tabelas com base em uma condição, geralmente uma chave estrangeira. Existem vários tipos de `JOIN`, mas vamos focar nos principais:

#### **2.2. INNER JOIN**
O `INNER JOIN` retorna apenas as linhas que possuem correspondência nas duas tabelas.

**Sintaxe:**
```sql
SELECT coluna1, coluna2, ...
FROM tabela1
INNER JOIN tabela2 ON tabela1.coluna = tabela2.coluna;
```

**Exemplo:**
Imagine duas tabelas: `clientes` e `pedidos`. Cada pedido tem uma referência ao cliente que fez o pedido (por meio de uma chave estrangeira).

- **Tabela clientes:**
  | id_cliente | nome_cliente |
  |------------|--------------|
  | 1          | João         |
  | 2          | Maria        |

- **Tabela pedidos:**
  | id_pedido | id_cliente | valor |
  |-----------|------------|-------|
  | 101       | 1          | 150   |
  | 102       | 2          | 200   |

**Consulta com INNER JOIN:**
```sql
SELECT clientes.nome_cliente, pedidos.valor
FROM clientes
INNER JOIN pedidos ON clientes.id_cliente = pedidos.id_cliente;
```
**Resultado:**
| nome_cliente | valor |
|--------------|-------|
| João         | 150   |
| Maria        | 200   |

Este comando retorna o nome do cliente e o valor do pedido apenas para os clientes que possuem pedidos registrados.

#### **2.3. LEFT JOIN (ou LEFT OUTER JOIN)**
O `LEFT JOIN` retorna todos os dados da tabela à esquerda, e os dados correspondentes da tabela à direita. Se não houver correspondência, os valores da tabela à direita serão `NULL`.

**Sintaxe:**
```sql
SELECT coluna1, coluna2, ...
FROM tabela1
LEFT JOIN tabela2 ON tabela1.coluna = tabela2.coluna;
```

**Exemplo:**
Se houver um cliente sem pedido, usando o mesmo exemplo de `clientes` e `pedidos`, podemos listar todos os clientes, mesmo os que não possuem pedidos.

```sql
SELECT clientes.nome_cliente, pedidos.valor
FROM clientes
LEFT JOIN pedidos ON clientes.id_cliente = pedidos.id_cliente;
```

**Resultado:**
| nome_cliente | valor |
|--------------|-------|
| João         | 150   |
| Maria        | 200   |
| Ana          | NULL  |

Neste caso, o cliente "Ana" não tem pedidos, por isso o valor é `NULL`.

#### **2.4. RIGHT JOIN (ou RIGHT OUTER JOIN)**
O `RIGHT JOIN` é semelhante ao `LEFT JOIN`, mas retorna todos os dados da tabela à direita e os dados correspondentes da tabela à esquerda. Se não houver correspondência, os valores da tabela à esquerda serão `NULL`.

**Sintaxe:**
```sql
SELECT coluna1, coluna2, ...
FROM tabela1
RIGHT JOIN tabela2 ON tabela1.coluna = tabela2.coluna;
```

#### **2.5. FULL OUTER JOIN**
O `FULL OUTER JOIN` retorna todos os dados de ambas as tabelas, com correspondência quando houver. Caso não haja correspondência, o valor da tabela que não tiver correspondência será `NULL`.

**Sintaxe:**
```sql
SELECT coluna1, coluna2, ...
FROM tabela1
FULL OUTER JOIN tabela2 ON tabela1.coluna = tabela2.coluna;
```

### **Conclusão**
Esses são os conceitos essenciais sobre **SQL**, incluindo **comandos básicos** como `SELECT`, `INSERT`, `UPDATE`, `DELETE`, e o uso de **JOINs** para combinar dados de múltiplas tabelas. Ao começar a trabalhar com SQL, esses são os comandos que você usará com mais frequência, então praticá-los é fundamental para o seu aprendizado.



Vamos criar um exercício prático com duas tabelas relacionadas: **funcionários** e **departamentos**. Vamos também realizar consultas utilizando `JOIN`.

### **Passo 1: Criar as Tabelas**

Primeiro, vamos criar as tabelas **funcionários** e **departamentos** no banco de dados. Suponha que temos um banco de dados relacional em SQL, e usaremos a seguinte estrutura:

#### **Tabela 1: departamentos**
```sql
CREATE TABLE departamentos (
    id_departamento INT PRIMARY KEY,
    nome VARCHAR(100)
);
```

#### **Tabela 2: funcionarios**
```sql
CREATE TABLE funcionarios (
    id_funcionario INT PRIMARY KEY,
    nome VARCHAR(100),
    id_departamento INT,
    salario DECIMAL(10, 2),
    FOREIGN KEY (id_departamento) REFERENCES departamentos(id_departamento)
);
```

Aqui, temos:

- **departamentos**: Tabela que contém o `id_departamento` (chave primária) e o `nome` do departamento.
- **funcionarios**: Tabela que contém o `id_funcionario` (chave primária), `nome` do funcionário, `id_departamento` (chave estrangeira referenciando o departamento) e o `salario`.

### **Passo 2: Inserir Dados nas Tabelas**

Agora, vamos adicionar alguns dados de exemplo para testar as consultas.

#### **Inserir Dados na Tabela `departamentos`:**
```sql
INSERT INTO departamentos (id_departamento, nome)
VALUES
(1, 'TI'),
(2, 'RH'),
(3, 'Financeiro');
```

#### **Inserir Dados na Tabela `funcionarios`:**
```sql
INSERT INTO funcionarios (id_funcionario, nome, id_departamento, salario)
VALUES
(1, 'João', 1, 3000.00),
(2, 'Maria', 2, 3500.00),
(3, 'Carlos', 1, 4000.00),
(4, 'Ana', 3, 5000.00),
(5, 'Lucas', 2, 4500.00);
```

Agora temos 3 departamentos e 5 funcionários, com cada funcionário pertencendo a um departamento.

### **Passo 3: Consultas utilizando `JOIN`**

Agora, vamos realizar algumas consultas utilizando `JOIN`.

#### **1. Exemplo de `INNER JOIN`**

O `INNER JOIN` retorna apenas as linhas que têm correspondência nas duas tabelas.

**Consulta**: Retorne o nome do funcionário e o nome do departamento em que ele trabalha.

```sql
SELECT funcionarios.nome AS nome_funcionario, departamentos.nome AS nome_departamento
FROM funcionarios
INNER JOIN departamentos ON funcionarios.id_departamento = departamentos.id_departamento;
```

**Resultado Esperado:**

| nome_funcionario | nome_departamento |
|------------------|-------------------|
| João             | TI                |
| Maria            | RH                |
| Carlos           | TI                |
| Ana              | Financeiro        |
| Lucas            | RH                |

#### **2. Exemplo de `LEFT JOIN`**

O `LEFT JOIN` retorna todos os registros da tabela à esquerda (funcionários) e os registros correspondentes da tabela à direita (departamentos). Se não houver correspondência, os dados da tabela à direita serão `NULL`.

**Consulta**: Retorne todos os funcionários e os departamentos onde eles trabalham, mesmo que um funcionário não esteja associado a um departamento (se existirem registros sem departamento).

```sql
SELECT funcionarios.nome AS nome_funcionario, departamentos.nome AS nome_departamento
FROM funcionarios
LEFT JOIN departamentos ON funcionarios.id_departamento = departamentos.id_departamento;
```

**Resultado Esperado:**

| nome_funcionario | nome_departamento |
|------------------|-------------------|
| João             | TI                |
| Maria            | RH                |
| Carlos           | TI                |
| Ana              | Financeiro        |
| Lucas            | RH                |

Neste caso, todos os funcionários estão associados a um departamento, então o resultado é o mesmo do `INNER JOIN`.

#### **3. Exemplo de `RIGHT JOIN`**

O `RIGHT JOIN` retorna todos os registros da tabela à direita (departamentos) e os registros correspondentes da tabela à esquerda (funcionários). Se não houver correspondência, os dados da tabela à esquerda serão `NULL`.

**Consulta**: Retorne todos os departamentos e os funcionários que pertencem a eles, incluindo departamentos que não têm funcionários.

```sql
SELECT departamentos.nome AS nome_departamento, funcionarios.nome AS nome_funcionario
FROM departamentos
RIGHT JOIN funcionarios ON funcionarios.id_departamento = departamentos.id_departamento;
```

**Resultado Esperado:**

| nome_departamento | nome_funcionario |
|-------------------|------------------|
| TI                | João             |
| RH                | Maria            |
| TI                | Carlos           |
| Financeiro        | Ana              |
| RH                | Lucas            |

#### **4. Exemplo de `FULL OUTER JOIN`**

O `FULL OUTER JOIN` retorna todos os registros de ambas as tabelas. Se não houver correspondência, o resultado terá valores `NULL`.

**Consulta**: Retorne todos os departamentos e todos os funcionários, incluindo aqueles que não têm correspondência (se existirem departamentos sem funcionários ou vice-versa).

```sql
SELECT departamentos.nome AS nome_departamento, funcionarios.nome AS nome_funcionario
FROM departamentos
FULL OUTER JOIN funcionarios ON departamentos.id_departamento = funcionarios.id_departamento;
```

**Resultado Esperado:**

| nome_departamento | nome_funcionario |
|-------------------|------------------|
| TI                | João             |
| RH                | Maria            |
| TI                | Carlos           |
| Financeiro        | Ana              |
| RH                | Lucas            |

Neste exemplo, como todos os departamentos têm funcionários, o resultado é similar ao do `INNER JOIN`.

### **Conclusão**
Com esse exercício prático, você agora tem duas tabelas relacionadas e fez consultas com diferentes tipos de `JOIN` para combinar os dados de ambas. Isso é fundamental para entender como manipular e recuperar dados de várias tabelas em SQL.
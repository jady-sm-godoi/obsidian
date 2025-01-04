# Teorema CAP

Atualmente existem mais de [300 bancos de dados no mercado](https://db-engines.com/en/ranking), e você precisa escolher aquele que melhor atende sua necessidade.

Os projetistas desses bancos de dados fizeram uma importante decisão sobre como eles devem funcionar, e por isso é importante entender o mecanismo de funcionamento deles para você não errar na escolha.

Entendendo o Teorema CAP você terá uma visão mais clara sobre os tipos de bancos de dados disponíveis, e quais estão aderentes ao seu caso de uso.

## Consistency, Availability and Partition Tolerance (CAP)

**CAP** significa Consistência [do inglês, **Consistency**], Disponibilidade [do inglês, **Availability**], e Tolerância a Partição [do inglês, **Partition Tolerance**].

**Partition Tolerance** significa que o banco de dados é distribuído em diversos servidores independentes [shared-nothing], em pares de leitura/escrita. Isso é importante, em especial, para aumentar a performance, já que quanto mais você espalha os dados em servidores diferentes, maior é o _throughput_ [megabytes por segundo] de leitura e escrita. Partition Tolerance também significa que se um servidor estiver fora, todo o sistema de banco de dados continua funcionando, com exceção desta parte específica que apresentou a falha.

Você pode perguntar por que P é chamado exatamente de “Tolerância a Partição”. O entendimento de partição aqui é “falha”, e mais especificamente falha de rede, que impede que um servidor se comunique com outro servidor. Então quando um banco de dados tolera partição, significa que se houver falha na comunicação entre um servidor que escreve e sua réplica, o banco de dados não para de funcionar, pois poderá haver outros pares de leitura e escrita no cluster que não estão no caminho da rede que falhou.

**Consistency** implica em consistência de leitura, e significa que depois que uma informação é escrita, todas as leituras subsequentes vão enxergá-la, no mesmo servidor, ou em suas réplicas. Neste caso também dizemos que há **consistência forte**, porque todos enxergam a mesma versão da informação.

**Availability** significa sempre disponível para leitura ou escrita, e todas as requisições sempre retornam alguma informação, mesmo que ela esteja inconsistente – mas nunca retorna um erro. Isto é, pode ter havido alguma falha na rede e os pares de servidores leitura/escrita não se enxergam, mas ambos permanecem abertos e recebem operações, estando em estado eventualmente consistente. Por causa disso, também dizemos que há uma **consistência eventual**, porque não é certeza que todos enxergam a mesma versão da informação.

## A Prova

O Teorema CAP foi provado, e **ele diz que das três propriedades desejadas, apenas duas podem existir ao mesmo tempo** para um par leitura/escrita.

Isso nos leva a três possibilidades que definem o mecanismo de funcionamento de um banco de dados.

**CA – Consistency e Availability**: são bancos de dados cujos dados não estão distribuídos, mas oferecem consistência, e também disponibilidade [porém, em geral através de failover, isto é, com downtime]. O Oracle RAC é o único atualmente que oferece tanto C como A “sem downtime” em um sistema de banco de dados que não tolera partição [shared-disk].

**CP – Consistency e Partition Tolerance**: são bancos de dados que oferecem consistência, isto é, os pares leitura/escrita sempre estão com os mesmo dados [consistentes], mas caso haja alguma falha na rede, ambos tornam-se indisponíveis: sacrificam a disponibilidade em favor da consistência.

**AP – Availability e Partition Tolerance**: são bancos de dados que oferecem disponibilidade, e sacrificam a consistência. Isto é, os pares leitura/escrita permanecem operantes quando há falha na rede. Notadamente, quando isto ocorre eles ficam em estado inconsistente, pois não há uma comunicação entre eles. A inconsistência pode ser resolvida quando a comunicação é reestabelecida.

## Minha Opinião… e a Sua?

Primeiramente, a letra **A** do CAP implica em uma premissa que eu particularmente não concordo.

**A** significa sempre disponível para leitura e escrita, mas sabemos que disponibilidade é medida em 9s depois da vírgula, e nada é realmente 100%. Quanto mais rotas redundantes de rede, e mais réplicas dos dados, mais 9s de disponibilidade teremos depois da vírgula, mas nunca 100% como o teorema preconiza.

Um outro ponto é que potencialmente, salvo implementação específica de cada banco de dados, os sistemas **AP** sempre apresentam um estado de consistência eventual, mesmo sem falha/partição na rede. Isso ocorre porque a propagação dos dados entre o servidor de que escreve e o servidor de réplica é assíncrona. Desta forma uma leitura pode ocorrer antes que uma informação que acabara de ser escrita fosse transmitida pela rede até o servidor em questão. Considerando que atualmente falhas de rede são raras, e as redes de comunicação locais são rápidas, sistemas **AP** oferecem uma desvantagem permanente, e na minha visão, desnecessária, tornando-os nicho para necessidades muito específicas. Há uma tendência de mercado dos bancos de dados NoSQL migrarem para o paradigma **CP**.

Então antes de usar um banco de dados, em especial nesses tempos de micro-serviços e persistência poliglota, atente-se ao mecanismo que é implementado no banco de dados.

**Requisitos de elasticidade e alto throughput para leitura e escrita exigem que o banco de dados seja tolerante a partições**. E neste caso, se houver a necessidade de consistência forte, o banco de dados deverá ser **CP**, do contrário, escolha **AP**.


Disponível em: https://universodosdados.com/2019/05/31/teorema-cap-explicado/

_____

## PostgressSQL

PostgreSQL, ou Postgres, é um sistema de gerenciamento de banco de dados relacional (RDBMS) que também suporta dados orientados a objetos. Ele é conhecido por sua conformidade com o padrão SQL e por oferecer recursos avançados, como controle de concorrência multiversion (MVCC), recuperação em caso de falha, e suporte a transações ACID (Atomicidade, Consistência, Isolamento, Durabilidade). Postgres é altamente extensível, permitindo a adição de novos tipos de dados, funções, operadores e métodos de indexação personalizados. 

Além disso, o PostgreSQL tem suporte nativo a JSON, possibilitando a integração de bancos de dados NoSQL e SQL, o que aumenta sua flexibilidade no armazenamento e gerenciamento de diferentes tipos de dados. Ele também se destaca por sua segurança, com suporte a autenticação criptografada, e escalabilidade, sendo capaz de gerenciar grandes volumes de dados com eficiência. 

Sua arquitetura permite uma fácil replicação e criação de clusters de alta disponibilidade, sendo amplamente utilizado em sistemas empresariais e plataformas que exigem alta robustez e confiabilidade.

## Microsoft SQL Server

O **Microsoft SQL Server** é um sistema de gerenciamento de banco de dados relacional (RDBMS) desenvolvido pela Microsoft. Ele é utilizado para armazenar, organizar e gerenciar grandes volumes de dados, sendo amplamente adotado em ambientes corporativos. 

Aqui estão os principais recursos do SQL Server:

### 1. **Motor de Banco de Dados Relacional**:
   - **T-SQL (Transact-SQL)**: SQL Server usa uma extensão proprietária do SQL, chamada T-SQL, que oferece funcionalidade adicional, como controle de fluxo e tratamento de erros.
   - **Suporte a Transações ACID**: Garante Atomicidade, Consistência, Isolamento e Durabilidade, assegurando integridade dos dados.

### 2. **Segurança e Compliance**:
   - **Autenticação e Autorização**: Oferece autenticação por Windows e SQL, além de permitir granularidade no controle de permissões a usuários.
   - **Criptografia**: Permite criptografia de dados em repouso e em trânsito, com suporte ao **Transparent Data Encryption (TDE)** e criptografia de colunas.

### 3. **Desempenho e Escalabilidade**:
   - **Índices Otimizados**: Suporte a índices tradicionais, full-text e colunar, otimizando consultas complexas.
   - **Particionamento de Tabelas**: Suporte a grandes conjuntos de dados, particionando tabelas para melhorar o desempenho de consulta.
   - **In-Memory OLTP**: Armazena dados críticos diretamente na memória para melhorar a performance transacional.

### 4. **Alta Disponibilidade e Recuperação**:
   - **Always On Availability Groups**: Suporta alta disponibilidade e recuperação de desastres com replicação automática entre nós.
   - **Replicação e Clustering**: Oferece replicação de dados em diferentes servidores, garantindo redundância.

### 5. **Suporte a Análise e Big Data**:
   - **Integration Services (SSIS)**: Ferramenta para ETL (extração, transformação e carga de dados) automatizando processos de integração.
   - **Analysis Services (SSAS)**: Permite a criação de cubos OLAP para análises multidimensionais.
   - **Reporting Services (SSRS)**: Gera relatórios interativos e visuais com base nos dados armazenados.

### 6. **Compatibilidade com Nuvem**:
   - O SQL Server está disponível em versões locais e na nuvem, através do **Azure SQL Database**, oferecendo escalabilidade e segurança em ambientes híbridos.

O SQL Server é projetado para suportar um grande volume de transações em ambientes empresariais, sendo altamente integrado ao ecossistema da Microsoft, como o Power BI e o Azure, tornando-o uma solução robusta e confiável para gerenciamento de dados empresariais.


## Oracle Database

O **Oracle Database** é um sistema de gerenciamento de banco de dados relacional (RDBMS) amplamente utilizado em ambientes corporativos devido à sua robustez, escalabilidade e segurança. Criado pela Oracle Corporation, ele oferece suporte completo a transações ACID, o que garante a integridade dos dados, mesmo em cenários de falha. 

Sua arquitetura é conhecida pelo uso de **Real Application Clusters (RAC)**, permitindo que várias instâncias do Oracle Database operem simultaneamente em um único banco de dados, melhorando a disponibilidade e o desempenho.

**Recursos-chave**:
- **SQL e PL/SQL**: O Oracle Database suporta SQL, a linguagem de consulta padrão para bancos de dados, e PL/SQL, uma extensão procedural que permite escrever programas mais complexos no próprio banco de dados.
- **Multitenancy**: O Oracle oferece suporte a múltiplos bancos de dados em uma única instância com o conceito de pluggable databases (PDBs) e container databases (CDBs), o que facilita a gestão e consolidação de recursos.
- **Particionamento**: Oferece técnicas de particionamento de dados que facilitam a manipulação e a consulta em grandes volumes de dados.
- **Otimização de desempenho**: Utiliza índices, planos de execução e cache de consultas para maximizar a velocidade de recuperação de dados.
- **Replicação e Recuperação de Desastres**: Através de ferramentas como Oracle Data Guard e Oracle GoldenGate, ele oferece suporte a replicação de dados e failover automático em casos de falha.
  
O Oracle Database também é conhecido por seu suporte a **data warehouses**, **big data** e **computação em nuvem**, integrando-se com soluções como **Oracle Cloud** e **Exadata** para atender grandes volumes de dados e cargas de trabalho intensivas. 

A Oracle continua a evoluir sua solução, incorporando automação e inteligência artificial com o **Oracle Autonomous Database**, uma versão que promete autogestão, autorrecuperação e autosegurança. 

Essas funcionalidades fazem do Oracle uma escolha preferencial para aplicações críticas em empresas de grande porte, onde a estabilidade, escalabilidade e segurança são fundamentais.

## MySQL

MySQL é um dos sistemas de gerenciamento de banco de dados relacional (RDBMS) mais populares do mundo. Ele foi desenvolvido inicialmente pela empresa sueca MySQL AB e posteriormente adquirido pela Oracle Corporation. MySQL é conhecido por ser rápido, escalável e fácil de usar, sendo amplamente adotado para aplicações web, como WordPress e Joomla, e integrações com outras linguagens de programação, como PHP, Python e Java.

### Características principais:
1. **Modelo Relacional**: Organiza os dados em tabelas (linhas e colunas) e utiliza SQL (Structured Query Language) como interface padrão para consultas e manipulação de dados.
2. **Código Aberto (Open Source)**: MySQL é um software gratuito e open-source, embora tenha versões comerciais com suporte adicional, como o MySQL Enterprise.
3. **Desempenho e Escalabilidade**: MySQL é otimizado para consultas rápidas e suporta grandes volumes de dados, o que o torna uma escolha ideal para grandes sistemas e aplicações de alto tráfego.
4. **Suporte a Múltiplos Modelos de Armazenamento**: Ele oferece mecanismos de armazenamento como InnoDB (com suporte a transações ACID e integridade referencial) e MyISAM (focado em desempenho de leitura).
5. **Alta Disponibilidade e Replicação**: Suporta replicação de dados em tempo real e a criação de clusters para alta disponibilidade e tolerância a falhas.
6. **Segurança**: MySQL oferece robustos controles de autenticação de usuários e permissões baseadas em funções e criptografia de dados.

### Casos de uso:
MySQL é amplamente utilizado em sistemas web, plataformas de comércio eletrônico, aplicativos SaaS e bancos de dados analíticos. Sua simplicidade, combinada com alto desempenho, faz dele uma escolha popular para desenvolvedores e empresas.

Comparado ao PostgreSQL, MySQL tem um enfoque mais direto em simplicidade e desempenho em ambientes de alta demanda, enquanto PostgreSQL se destaca em funcionalidades avançadas e extensibilidade.

## Firebird

**Firebird** é um sistema de gerenciamento de banco de dados relacional open-source, derivado do InterBase, conhecido por ser leve e eficiente, especialmente em aplicações de menor escala. Ele suporta recursos como transações ACID, triggers, procedimentos armazenados e integridade referencial. O Firebird é multiplataforma, rodando em sistemas operacionais como Windows, Linux e macOS.

### Principais características:
- **Baixo consumo de recursos:** Ideal para aplicações que precisam de um banco de dados leve.
- **Suporte a SQL padrão:** Além de extensões proprietárias para otimizar consultas e armazenamento de dados.
- **Recursos avançados:** Inclui triggers, views, eventos e procedimentos armazenados.
- **Transações ACID:** Garante a consistência e integridade dos dados.
- **Nível de isolamento e concorrência:** Implementa controle de concorrência multiversion, permitindo que múltiplas transações acessem os dados simultaneamente sem conflitos.

### Instalação do Firebird no Linux (Debian/Ubuntu):

1. **Adicione o repositório do Firebird**:
   ```
   sudo add-apt-repository ppa:mapopa/firebird3.0
   sudo apt-get update
   ```

2. **Instale o Firebird**:
   ```
   sudo apt-get install firebird3.0-server
   ```

3. **Ative o Firebird**:
   ```
   sudo systemctl enable firebird3.0
   sudo systemctl start firebird3.0
   ```

### Usando o Firebird:

1. **Cliente de administração**: Use o `isql-fb` para interagir com o banco de dados:
   ```
   isql-fb
   ```

2. **Criar um banco de dados**:
   ```sql
   CREATE DATABASE 'localhost:/path/to/database.fdb' USER 'SYSDBA' PASSWORD 'masterkey';
   ```

3. **Consultas SQL**: Execute comandos SQL como em outros RDBMS:
   ```sql
   SELECT * FROM my_table;
   ```

Firebird é uma escolha robusta e escalável para pequenas e médias aplicações, com baixo custo de manutenção e ótima performance.

_______

## Modelagem de Dados – Modelos Conceitual, Lógico e Físico

A modelagem de dados é o processo de organizar e estruturar dados para serem armazenados de forma eficiente em um banco de dados. Ela pode ser dividida em três tipos principais: **conceitual**, **lógico** e **físico**.

### 1. Modelo Conceitual:
É o nível mais abstrato, focado em representar os **requisitos** de negócio e as **entidades** envolvidas, sem considerar aspectos técnicos. O objetivo é entender o domínio do problema e como os dados estão relacionados.

Exemplo:
- Entidades: Cliente, Produto, Pedido.
- Relacionamentos: Um cliente pode fazer vários pedidos; um pedido contém vários produtos.

### 2. Modelo Lógico:
Esse modelo descreve a **estrutura dos dados** em termos de tabelas e atributos, mas ainda sem definir como será implementado fisicamente no banco de dados. No modelo lógico, se consideram chaves primárias e estrangeiras, mas não os detalhes específicos do sistema de gerenciamento de banco de dados (SGBD).

Exemplo:
- Tabelas: Cliente (ID_Cliente, Nome), Produto (ID_Produto, Nome, Preço), Pedido (ID_Pedido, Data, ID_Cliente_FK).
- Relacionamentos: Pedido contém a chave estrangeira (ID_Cliente_FK) para relacionar com Cliente.

### 3. Modelo Físico:
Aqui, o foco é a **implementação real** no banco de dados escolhido. Define como os dados serão armazenados no SGBD, incluindo detalhes como tipos de dados, índices e estrutura de armazenamento.

Exemplo:
- Tabelas com tipos de dados: 
   - Cliente (ID_Cliente INT PRIMARY KEY, Nome VARCHAR(255)).
   - Produto (ID_Produto INT PRIMARY KEY, Nome VARCHAR(255), Preço DECIMAL(10,2)).
   - Pedido (ID_Pedido INT PRIMARY KEY, Data TIMESTAMP, ID_Cliente_FK INT FOREIGN KEY REFERENCES Cliente).

### Diferenças:
- **Conceitual**: Focado nas necessidades do negócio, sem detalhes técnicos.
- **Lógico**: Estrutura das tabelas e relacionamento entre dados, mas ainda sem implementar no SGBD.
- **Físico**: Representação técnica no banco de dados, com definições detalhadas.

Essa divisão em três níveis permite uma transição suave do entendimento do problema à implementação, garantindo que todos os requisitos do negócio sejam atendidos na modelagem final.

_____

## Modelagem de Dados – Normalização – Primeira Forma Normal

A **modelagem de dados** é o processo de estruturar os dados de forma lógica para garantir consistência, organização e eficiência. Uma das técnicas fundamentais para melhorar essa estrutura é a **normalização**. Ela organiza os dados em tabelas para eliminar redundâncias e dependências indesejadas.

A **Primeira Forma Normal (1FN)** é a primeira etapa desse processo. Para uma tabela estar na 1FN, ela deve:

1. Eliminar grupos repetidos (tabelas não podem ter múltiplos valores em uma célula).
2. Garantir que cada coluna armazene apenas um tipo de dado.
3. Identificar cada linha de maneira única (com uma chave primária).

### Exemplo:

#### Tabela Não Normalizada:
| ID | Nome   | Telefone             |
|----|--------|----------------------|
| 1  | João   | 1234, 5678           |
| 2  | Maria  | 9876                 |

Aqui, a coluna **Telefone** contém múltiplos valores em uma célula, violando a 1FN.

#### Tabela Normalizada (1FN):
| ID | Nome   | Telefone |
|----|--------|----------|
| 1  | João   | 1234     |
| 1  | João   | 5678     |
| 2  | Maria  | 9876     |

Agora, cada célula contém apenas um valor, e a tabela está na **Primeira Forma Normal**.

Este processo elimina a redundância de dados e facilita a criação de consultas eficientes, uma vez que todos os dados são atômicos e facilmente manipuláveis em um formato estruturado.

## Modelagem de Dados – Normalização – Segunda Forma Normal

**Modelagem de Dados – Segunda Forma Normal (2FN)** é um passo no processo de normalização que visa eliminar redundâncias e dependências parciais em uma tabela de banco de dados.

### Requisitos:
1. **Estar na Primeira Forma Normal (1FN)**: A tabela deve ter colunas atômicas (não contendo conjuntos ou listas de valores).
2. **Eliminação de dependências parciais**: Todas as colunas não-chave devem depender da chave primária inteira, e não apenas de parte dela.

### Exemplo:

**Tabela inicial (não normalizada)**:
| Pedido_ID | Produto_ID | Quantidade | Nome_Cliente |
|-----------|------------|------------|--------------|
| 1         | 101        | 2          | João         |
| 2         | 102        | 1          | Maria        |

Aqui, `Nome_Cliente` depende apenas de `Pedido_ID`, e não de `Produto_ID`, uma dependência parcial.

**Após 2FN**:
1. Dividimos em duas tabelas:

- **Pedidos**:
  | Pedido_ID | Nome_Cliente |
  |-----------|--------------|
  | 1         | João         |
  | 2         | Maria        |

- **Itens do Pedido**:
  | Pedido_ID | Produto_ID | Quantidade |
  |-----------|------------|------------|
  | 1         | 101        | 2          |
  | 2         | 102        | 1          |

Dessa forma, eliminamos a redundância e a dependência parcial.


## Modelagem de Dados – Normalização – Terceira Forma Normal

A Terceira Forma Normal (3FN) é uma etapa de normalização de bancos de dados relacional que visa eliminar redundâncias e garantir que os dados sejam armazenados de forma eficiente e consistente. Para entender a 3FN, é útil revisar as três formas normais anteriores e depois ver a 3FN em detalhes.

### Revisão das Formas Normais

1. **Primeira Forma Normal (1FN):** 
   - **Requisitos:** Cada coluna deve conter apenas valores atômicos (não divididos) e cada linha deve ser única.
   - **Exemplo:**
     ```
     | ID | Nome  | Telefones          |
     |----|-------|---------------------|
     | 1  | João  | 1234, 5678          |
     | 2  | Maria | 9876                |
     ```
     Aqui, a coluna `Telefones` não está em 1FN porque contém múltiplos valores.

2. **Segunda Forma Normal (2FN):**
   - **Requisitos:** Estar em 1FN e, além disso, todos os atributos não-chave devem depender completamente da chave primária.
   - **Exemplo:**
     ```
     | ID | Nome  | Curso       | Professor |
     |----|-------|-------------|-----------|
     | 1  | João  | Matemática  | Prof. A   |
     | 2  | Maria | Física      | Prof. B   |
     ```
     Aqui, `Curso` e `Professor` dependem apenas do `ID`, portanto está em 2FN.

3. **Terceira Forma Normal (3FN):**
   - **Requisitos:** Estar em 2FN e, além disso, todos os atributos não-chave devem ser diretamente dependentes da chave primária e não de outros atributos não-chave.
   - **Exemplo:**
     ```
     | ID | Nome  | Curso       | NomeProfessor | Sala |
     |----|-------|-------------|---------------|------|
     | 1  | João  | Matemática  | Prof. A       | 101  |
     | 2  | Maria | Física      | Prof. B       | 102  |
     ```

### Exemplo Prático da 3FN

#### Tabela Inicial (Não Normalizada):

```
| Matricula | Nome    | Curso        | NomeProfessor | Sala |
|-----------|---------|--------------|---------------|------|
| 1         | João    | Matemática   | Prof. A       | 101  |
| 2         | Maria   | Física       | Prof. B       | 102  |
```

#### Problemas Identificados:
- **Dependência Transitiva:** `NomeProfessor` e `Sala` dependem de `Curso`, e `Curso` depende de `Matricula`. Ou seja, `NomeProfessor` e `Sala` não dependem diretamente de `Matricula`, mas sim de `Curso`.

#### Tabelas Normalizadas:

**Tabela 1: Alunos**

```
| Matricula | Nome  |
|-----------|-------|
| 1         | João  |
| 2         | Maria |
```

**Tabela 2: Cursos**

```
| Curso        | NomeProfessor | Sala |
|--------------|---------------|------|
| Matemática   | Prof. A       | 101  |
| Física       | Prof. B       | 102  |
```

**Tabela 3: Matriculas**

```
| Matricula | Curso        |
|-----------|--------------|
| 1         | Matemática   |
| 2         | Física       |
```

### Explicação da 3FN nas Tabelas:

1. **Tabela Alunos**:
   - Armazena informações sobre os alunos. Cada aluno tem uma matrícula única.

2. **Tabela Cursos**:
   - Armazena informações sobre cursos, incluindo o professor e a sala, e não depende diretamente da matrícula.

3. **Tabela Matriculas**:
   - Relaciona cada aluno a um curso específico.

Nesta estrutura, todos os atributos não-chave dependem diretamente da chave primária. As tabelas são projetadas para evitar redundâncias e inconsistências. Se quisermos adicionar um novo curso, apenas a Tabela Cursos precisa ser atualizada, e se um aluno muda de curso, isso é registrado na Tabela Matriculas.

### Resumo

A Terceira Forma Normal (3FN) assegura que:
- A tabela está em 2FN.
- Todos os atributos não-chave dependem apenas da chave primária e não de outros atributos não-chave.

Isso ajuda a garantir que os dados estejam organizados de forma a minimizar redundâncias e anomalias, tornando o banco de dados mais eficiente e fácil de manter.

___
### Resumo:

### Primeira Forma Normal (1FN)
- **Requisito:** Cada coluna deve conter apenas valores atômicos (não divididos) e cada linha deve ser única.
- **Exemplo:** Uma tabela onde cada célula tem um único valor e não há listas ou conjuntos de valores em uma única coluna.

### Segunda Forma Normal (2FN)
- **Requisito:** Estar em 1FN e garantir que todos os atributos não-chave dependem completamente da chave primária, sem dependências parciais.
- **Exemplo:** Em uma tabela onde a chave primária é composta, todos os atributos devem depender da chave primária completa e não apenas de uma parte dela.

### Terceira Forma Normal (3FN)
- **Requisito:** Estar em 2FN e garantir que todos os atributos não-chave dependem diretamente da chave primária, e não de outros atributos não-chave (eliminando dependências transitivas).
- **Exemplo:** Todos os atributos não-chave devem depender diretamente da chave primária, e não de outros atributos que não sejam a chave primária.

Essas formas normais ajudam a eliminar redundâncias e garantir a integridade dos dados em um banco de dados relacional.

_____

## Modelagem de Dados – Modelo Entidade – Relacionamento e Diagrama ER

### Modelo Entidade-Relacionamento (ER)

O Modelo Entidade-Relacionamento é uma abordagem para modelar dados em sistemas de banco de dados. Ele usa entidades, atributos e relacionamentos para descrever e visualizar como os dados se relacionam entre si.

#### 1. **Entidades**

- **Definição:** Representam objetos ou conceitos do mundo real que têm importância para o sistema. 
- **Exemplo:** Em um sistema de gerenciamento de biblioteca, as entidades podem ser `Livro`, `Autor` e `Usuário`.

**Entidade: Livro**
- Atributos: `ID_Livro`, `Título`, `Ano_Publicação`, `Gênero`

#### 2. **Atributos**

- **Definição:** Características ou propriedades das entidades.
- **Exemplo:** Para a entidade `Livro`, os atributos podem incluir `ID_Livro`, `Título`, `Ano_Publicação`, etc.

**Atributo: Título**
- Tipo: Texto

#### 3. **Relacionamentos**

- **Definição:** Associações entre entidades. Pode ter um ou mais atributos próprios.
- **Exemplo:** Um relacionamento `Escreve` pode conectar `Autor` e `Livro`, indicando que um autor escreve um livro.

**Relacionamento: Empréstimo**
- Entre entidades: `Usuário` e `Livro`
- Atributos: `Data_Empréstimo`, `Data_Devolução`

### Diagrama ER (Entidade-Relacionamento)

O Diagrama ER é uma representação visual do Modelo Entidade-Relacionamento. Ele ilustra entidades, atributos e relacionamentos, ajudando a entender a estrutura e as interações do banco de dados.

#### Componentes do Diagrama ER

1. **Entidades**
   - Representadas por retângulos.
   - Nome da entidade está dentro do retângulo.

2. **Atributos**
   - Representados por elipses conectadas às entidades.
   - Atributos chave primária são sublinhados.

3. **Relacionamentos**
   - Representados por losangos conectados a retângulos (entidades).
   - O nome do relacionamento está dentro do losango.

4. **Cardinalidade**
   - Indica o número de instâncias de uma entidade que estão associadas a uma instância de outra entidade.
   - Exemplos de cardinalidade: 1:1 (um para um), 1:N (um para muitos), M:N (muitos para muitos).

#### Exemplo Prático

Vamos criar um Diagrama ER simples para um sistema de biblioteca:

1. **Entidades:**
   - `Livro`
   - `Autor`
   - `Usuário`

2. **Atributos:**
   - `Livro`: `ID_Livro` (PK), `Título`, `Ano_Publicação`, `Gênero`
   - `Autor`: `ID_Autor` (PK), `Nome`, `Data_Nascimento`
   - `Usuário`: `ID_Usuário` (PK), `Nome`, `Data_Registro`

3. **Relacionamentos:**
   - `Escreve`: Conecta `Autor` e `Livro`
     - Cardinalidade: Muitos para Muitos (um autor pode escrever vários livros e um livro pode ter vários autores)
   - `Empréstimo`: Conecta `Usuário` e `Livro`
     - Cardinalidade: Muitos para Muitos (um usuário pode emprestar vários livros e um livro pode ser emprestado por vários usuários)

#### Diagrama ER Visual:

```
 [Livro] -----[Escreve]----- [Autor]
   |                       |
   |                       |
  [Empréstimo]             |
   |                       |
   |                       |
 [Usuário]                (Atributos, Relacionamentos, Cardinalidade)
```

### Explicação do Diagrama

- **Entidade `Livro`**:
  - Atributos: `ID_Livro`, `Título`, `Ano_Publicação`, `Gênero`
  
- **Entidade `Autor`**:
  - Atributos: `ID_Autor`, `Nome`, `Data_Nascimento`

- **Relacionamento `Escreve`**:
  - Indica que `Autores` escrevem `Livros`.
  - Cardinalidade: M:N

- **Relacionamento `Empréstimo`**:
  - Indica que `Usuários` emprestam `Livros`.
  - Cardinalidade: M:N

### Conclusão

O Modelo Entidade-Relacionamento e o Diagrama ER são ferramentas poderosas para a modelagem de dados, permitindo representar e organizar os dados e suas interações de forma clara e eficiente. Utilizando essas ferramentas, você pode garantir que seu banco de dados seja bem estruturado e atenda às necessidades do sistema.
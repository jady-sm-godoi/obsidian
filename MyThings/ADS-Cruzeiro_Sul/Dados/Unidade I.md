
# Modelagem de Dados - base teórica

## Evolução Histórica de Banco de Dados

Os seres humanos começaram a armazenar informações há muito tempo. Há décadas, elaborados sistemas de banco de dados foram desenvolvidos por escritórios governamentais, bibliotecas, hospitais e organizações empresariais, e alguns dos princípios básicos desses sistemas ainda são usados hoje.

A seguir, apresentaremos, de maneira cronológica, os principais destaques ocorridos na evolução dos bancos de dados eletrônicos.

- 1960: Foi marcada pela criação de banco de dados eletrônicos. O desenvolvimento do IMS (um banco de dados hierárquico criado pela IBM) e o aparecimento dos primeiros sistemas de banco de dados de redes.
- 1970: Surgimento do Modelo de dados relacional e a implementação de sistemas de banco de dados relacionais.
- 1980: SQL (_Structured_ _Query_ _Language_) torna-se um padrão mundial para os modelos relacionais. Sistemas de banco de dados orientados às aplicações (espacial, científico, de engenharia etc.).
- 1990: _Data mining_, _data_ _warehousing_, bancos de dados multimídia e bases de dados Web e os primeiros protótipos dos modelos orientados a objetos.
- 2000: Gerenciamento de dados de fluxo e mineração: » Mineração de dados e suas aplicações; » Tecnologia da Web; » XML; » Integração de dados; » Redes Sociais; » Computação em nuvem; » Sistemas de informação globais.

## O que é um Banco de Dados

Um banco de dados é uma coleção de dados. Essa definição pode parecer muito simples, não é mesmo? Mas, resume muito bem o que qualquer banco de dados é. Os bancos de dados suportam armazenamento e manipulação de dados, sejam eles eletrônicos ou não.

Um banco de dados pode ser tão simples quanto um arquivo de texto com uma lista de nomes. Ou podem ser tão complexos quanto um grande sistema de gerenciamento de banco de dados relacional, com ferramentas embutidas para ajudá-los a manter os dados.

Em nosso cotidiano, interagimos com bancos de dados em muitos momentos. Uma lista de telefones on-line, por exemplo, definitivamente usaria banco de dados para armazenar dados relativos a pessoas, números de telefone, outros detalhes de contato etc. Sua prestadora de serviços de eletricidade utiliza um banco de dados para gerenciar o faturamento, problemas relacionados com o cliente, para lidar com dados de panes etc.

Consideremos também o Facebook. Ele precisa armazenar, manipular e apresentar dados relacionados a usuários, seus amigos, mensagens, anúncios e muito mais.

## O que é um Sistema Gerenciador de Banco de Dados

Sistema de Gerenciamento de Banco de Dados (SGBD) é um conjunto de programas que permitem aos seus usuários controlar o acesso ao banco de dados, manipular dados, relatórios / representação de dados.

SGBD é o nome dado aos _softwares_ que gerenciam bancos de dados, e não o tipo do banco de dados.
A seguir serão apresentados os quatro principais modelos ou tipos de SGBD.

### Hierárquico

O modelo hierárquico foi desenvolvido nos anos 60 para gerenciar grandes quantidades de dados para projetos de fabricação complexos. Sua estrutura lógica básica é representada por uma árvore de cabeça para baixo. A estrutura hierárquica contém níveis ou segmentos.

Um segmento é o equivalente ao tipo de registro de um sistema de arquivos. Dentro da hierarquia, uma camada superior é percebida como o pai do segmento diretamente abaixo dele, que é chamado de filho. O modelo hierárquico descreve um conjunto de relações um-para-muitos (1: M) entre um pai e seus segmentos filhos. (Cada pai pode ter muitos filhos, mas cada filho tem apenas um pai.).

O editor de registro do Windows (figura 1) é um exemplo de um banco de dados hierárquico.

Um SGBD nesse modelo possui as seguintes vantagens:  
  
ㅤ• Simplicidade conceitual;  
  
ㅤ• Segurança de banco de dados;  
  
ㅤ• Independência dos dados;  
  
ㅤ• Integridade do banco de dados;  
  
ㅤ• Eficiência em lidar com uma grande base de dados.  
  
Quanto às desvantagens:  
  
ㅤ• Implementação complexa;  
  
ㅤ• Difícil gerenciamento;  
  
ㅤ• Falta de independência estrutural;  
  
ㅤ• Limitações de implementação;  
  
ㅤ• Falta de normas e padrões bem definidos.

Exemplos de sistemas de gerenciamento de banco de dados hierárquico incluem os bancos de dados _Information_ _Management System_ (IMS) e o _SYSTEM_ 2000.

### Rede

Consideramos o SGBD um modelo em rede, quando este organiza os dados em uma estrutura de rede. Isso geralmente resulta em complexas estruturas de banco de dados. Comparando como o modelo hierárquico, no modelo em Rede, o registro-filho pode possuir diversos pais, pois em uma rede os nós podem ter o máximo de conexões possíveis.
![[Pasted image 20240902195818.png]]
Embora o modelo de banco de dados de rede seja pouco utilizado atualmente, as definições de conceitos de banco de dados que surgiram com esse modelo ainda são utilizadas por modelos de dados mais modernos. Alguns conceitos importantes que foram definidos nesse momento são:
- Esquema: É a organização conceitual de todo o banco de dados visto pelo administrador do banco de dados.
- O subesquema: Define a parte do banco de dados “visível” pelos programas aplicativos, os quais produzem as informações desejadas a partir dos dados contidos no banco de dados.
- Data Manipulation Language (DML): É a linguagem que define o ambiente no qual os dados podem ser gerenciados e para trabalhar com os dados no banco de dados.
- Data Definition Language (DDL): Linguagem de definição de dados de esquema, a qual permite ao administrador do banco de dados definir os componentes do esquema.

Um SGDB de Rede possui as seguintes vantagens:  
  
ㅤ• Simplicidade conceitual;  
  
ㅤ• Permite gerenciar uma grande quantidade de relações;  
  
ㅤ• Possibilita a flexibilidade de acesso a dados;  
  
ㅤ• Promove a integridade do banco de dados;  
  
ㅤ• Favorece a independência dos dados;  
  
ㅤ• Possui normas e padrões bem definidos.  
  
Quanto às desvantagens:  
  
ㅤ• Complexidade do sistema;  
  
ㅤ• Falta de independência estrutural.

O _RDM Server_, _IDMS_ e _TOTAL_ são exemplos de sistemas de gerenciamento de banco de dados que implementam o modelo de rede.

### Relacional

Esse tipo de SGBD define relações de banco de dados em forma de tabelas, também conhecidas como relações. Ao contrário do SGBD de rede, o tipo relacional não suporta relacionamentos do tipo muitos para muitos.

Criado na década de 1970 por Edgar Frank Codd, pesquisador da IBM, a base do modelo relacional é um conceito matemático conhecido como relação. O modelo de dados relacional executa as mesmas funções básicas fornecidas pelos SGBDs dos tipos hierárquico e de rede, além de uma série de outras funções que tornam o modelo de dados relacional mais fácil de entender e implementar. Esse é o tipo de SGBD mais popular no mercado.

Uma das grandes vantagens desse modelo (SGBD-R) é a sua capacidade de ocultar as complexidades do modelo relacional do usuário. O SGBD-R gerencia todos os detalhes físicos, enquanto o usuário vê o banco de dados relacional como uma coleção de tabelas nas quais os dados são armazenados. O usuário pode manipular e consultar os dados de uma forma que parece intuitiva e lógica.
Uma tabela relacional armazena uma coleção de dados relacionados. A esse respeito, a tabela de banco de dados relacional se assemelha a um arquivo, disposta em linhas e colunas.
![[Pasted image 20240902201030.png]]

Outra grande vantagem é a sua linguagem de consulta poderosa e flexível, o _Structured_ _Query_ _Language_ (SQL), a qual permite ao usuário especificar o que deve ser feito sem especificar como deve ser feito. O SGBD-R usa o SQL para traduzir consultas de usuários em instruções para recuperar os dados solicitados. O SQL torna possível recuperar dados com muito menos esforço do que qualquer outro banco de dados ou ambiente de arquivos.

O SGBD-Relacional possui as seguintes vantagens:  
  
ㅤ• A independência estrutural;  
  
ㅤ• Melhor simplicidade conceitual;  
  
ㅤ• Projeto, implementação, gerenciamento e uso mais simples de banco de dados;  
  
ㅤ• Sistema de gerenciamento de banco de dados poderoso.  
  
Quanto às desvantagens, temos:  
  
ㅤ• Sobrecarga substancial de hardware e software de sistema;  
  
ㅤ• Possibilidade de má concepção e implementação.

Exemplos de sistemas de gerenciamento de banco de dados relacional incluem banco de dados _MySQL, Oracle e Microsoft SQL Server_.
#### As regras de Codd

**Regra Zero:** Todas as regras baseiam-se na noção de que para que um Banco de Dados seja considerado Relacional, ele deve utilizar os recursos relacionais exclusivamente para seu gerenciamento.

**Regra 1: _Informação_** – Todas as informações de um BDR devem ser representadas logicamente como valores de coluna em linhas dentro das tabelas.

**Regra 2:** _**Garantia de Acesso**_ – Deve-se garantir que todos os valores de uma tabela possam ser acessados por meio de uma combinação de nome de tabela, valor de chave primária e nome de coluna.

**Regra 3:** _**Tratamento Sistemático de Nulos**_ – Os nulos devem ser representados e tratados de modo sistemático, independente do tipo de dados.

**Regra 4:** _**Catálogo On-Line Dinâmico com Base no Modelo Relacional**_ – Os metadados devem ser armazenados e gerenciados como dados comuns, ou seja, em tabelas no interior do BD. Esses dados devem estar disponíveis aos usuários autorizados, utilizando a linguagem relacional padrão do BD.

**Regra 5:** _**Sublinguagem Ampla de Dados**_ – O BDR pode suportar várias linguagens. No entanto deve suportar uma linguagem declarativa bem definida com suporte para definição de dados, definição de visualização, manipulação de dados (interativa ou por programa), restrições de integridade, autorização e gerenciamento de transações (iniciar, comprometer e desfazer).

**Regra 6:** _**Atualização de Visualização**_ – Qualquer visualização que teoricamente possa ser atualizada deve ser por meio do sistema.

**Regra 7:** _**Inserção, atualização e exclusão de alto nível**_ – O BD deve dar suporte à configuração do nível de inserções, atualizações e exclusões. Ou seja, a capacidade de manipular um conjunto de dados através de um comando, deve-se estender às operações de Linguagem de Manipulação de Dados (DML) como _insert_, _update_ e _delete_.

**Regra 8:** _**Independência Física de Dados**_ – Aplicativos e recursos _ad hoc_ não são afetados logicamente quando os métodos de acesso ou as estruturas de armazenamento físico são alterados.

**Regra 9:** _**Independência Lógica de Dados**_ – Aplicativos e recursos _ad hoc_ não são afetados logicamente quando de alterações de estruturas de tabela que preservem os valores originais da tabela (alteração da ordem ou inserção de colunas). Alterações nas relações e nas views causam pouco ou nenhum impacto nas aplicações.

**Regra 10:** _**Independência de Integridade**_ – Deve ser possível que todas as restrições de integridade relacional sejam definidas na linguagem relacional e armazenadas no catálogo de sistema, não no nível da aplicação. As aplicações não devem ser afetadas quando ocorrer mudanças nas restrições de integridade.

**Regra 11:** _**Independência de Distribuição**_ – Os usuários finais e aplicativos não conhecem nem são afetados pela localização dos dados (BD Distribuídos VS. BD Locais).

**Regra 12:** _**Não transposição das Regras**_ – Se o sistema dá suporte a acesso de baixo nível aos dados, não deve haver um modo  de negligenciar as regras de integridade do BD.


### Orientado a Objetos

No SGBD orientado a objetos (SGBD-OO), tanto os dados como suas relações estão contidos em uma única estrutura conhecida como objeto. Esse modelo de dados é outro método de representar objetos do mundo real. Considera cada objeto no mundo como objetos e os isola uns dos outros.

O SGBD-OO baseia-se nos seguintes componentes:

- Um objeto é uma abstração de uma entidade do mundo real. Em termos gerais, um objeto pode ser considerado equivalente a uma tabela do SGBD Relacional. Mais precisamente, um objeto representa apenas uma ocorrência de uma entidade;
- Atributos descrevem as propriedades de um objeto. Por exemplo, um objeto PESSOA inclui os atributos Nome, Número de Segurança Social e Data de Nascimento;
- Objetos que compartilham características semelhantes são agrupados em classes. Uma classe é uma coleção de objetos semelhantes com estrutura compartilhada (atributos) e comportamento (métodos). O método de uma classe representa uma ação no mundo real, como encontrar o nome de uma pessoa selecionada, alterar o nome de uma pessoa ou imprimir o endereço de uma pessoa. Em outras palavras, os métodos são o equivalente a procedimentos em linguagens de programação tradicionais. Em termos orientados a objetos, os métodos definem o comportamento de um objeto;
- As classes são organizadas em uma hierarquia de classes. A hierarquia de classe se assemelha a uma árvore invertida na qual cada classe tem apenas um pai. Por exemplo, a classe CLIENTE e a classe EMPREGADO compartilham uma classe pai PESSOA, o que chamamos de herança;
- A herança é a capacidade de um objeto dentro da hierarquia de classe herdar os atributos e métodos das classes acima dele. Por exemplo, duas classes, CLIENTE e EMPREGADO, podem ser criadas como subclasses da classe PESSOA. Nesse caso, CLIENTE e EMPREGADO herdarão todos os atributos e métodos de PESSOA.
![[Pasted image 20240902201644.png]]
As vantagens oferecidas por esse modelo são as seguintes:  
  
ㅤ• Apresentação visual inclui conteúdo significativo;  
  
ㅤ• Alta integridade do banco de dados;  
  
ㅤ• Independência estrutural e de dados;  
  
Quanto às desvantagens:  
  
ㅤ• Falta de normas e padrões bem definidos;  
  
ㅤ• Acesso completo aos dados de navegação;  
  
ㅤ• Curva de aprendizagem íngreme.

Exemplos de sistemas de gerenciamento de banco de dados orientados a objetos incluem os bancos de dados CACHÉ, DB4Objects, VERSANT, JASMIN e MATISSE.


# A Importância dos Bancos de Dados

As informações são úteis para relatar a uma organização os resultados de suas operações atuais e colaborar com a gestão de estratégias para os negócios.

As informações organizacionais são armazenadas em um banco de dados. Aplicativos e programas, como sistemas de gerenciamento da cadeia de suprimentos e sistemas de gerenciamento de relacionamento com o cliente, acessam os dados no banco de dados para que o programa possa consultá-lo e exibir, de maneira intuitiva, o que está acontecendo com o negócio.

O valor da informação reside não apenas na própria informação, mas nas ações que surgem da informação. Por exemplo, se as informações o alertarem para a má satisfação do cliente, isso só será útil se isso criar uma mudança na forma como o negócio lida com os clientes. Assim, o processo de informação deve fazer parte de um processo de revisão mais amplo dentro do negócio para obter os melhores resultados.

Nesse contexto, um banco de dados se faz importante, pois gerencia e possibilita o acesso à informação. Elaborar como os dados serão armazenados e de qual forma, é parte extremamente relevante para o sucesso do gerenciamento e manutenção do banco de dados, tão vital e essencial para a organização.


### O que é NoSQL?

Vamos começar sobre o **NoSQL, o que vem a ser esse conceito ?**

Pesquisando pela net, encontramos muitas definições, algumas bem confusas que passam a ideia de um conceito que tenta acabar com o padrão SQL, bem como encontramos também definições mais realistas, que passam a ideia de um padrão de armazenamento de dados alternativo ao SQL, oferecendo uma robustez e escalabilidade melhores.

Para sabermos mais claramente o que é o NoSQL, e qual seu uso, é interessante saber algumas coisas antes.

O termo _NoSQL_ foi primeiramente utilizado em 1998 como o nome de um banco de dados não relacional de código aberto.

Seu autor, Carlo Strozzi, **alega que o movimento NoSQL "é completamente distinto do modelo relacional e portanto deveria ser mais apropriadamente chamado "NoREL" ou algo que produzisse o mesmo efeito"**.

Com a crescente popularização da internet, diversos novos dados foram surgindo e tratá-los foi se tornando gradualmente mais complexo e sua manutenção cada vez mais cara.

Em 2006, o artigo: BigTable: A Distributed Storage System for Structured Data, publicado pelo Google em 2006, **traz novamente à tona o conceito NoSQL**.

No inicio de 2009, o termo **NoSQL é reintroduzido por um funcionário do Rackspace**, Eric Evans, quando Johan Oskarson da Last.fm queria organizar um evento para discutir bancos de dados open source distribuídos.

O nome era uma tentativa de descrever o surgimento de um número crescente de bancos de dados não relacionais e fazia uma referência ao esquema de atribuição de nomes dos bancos de dados relacionais mais populares do mercado como [MySQL](https://www.devmedia.com.br/primeiros-passos-no-mysql/28438 "MySQL"), MS SQL, [PostgreSQL](https://www.devmedia.com.br/introducao-ao-postgresql/6390 "PostgreSQL"), etc.

A partir de então, os **bancos de dados não relacionais passaram a ser conhecidos como NoSQL**, e com crescente popularização das redes sociais, a geração de conteúdo por dispositivos móveis bem como o número cada vez maior de pessoas e dispositivos conectados, faz com que o trabalho de armazenamento de dados com o objetivo de utilizá-los em ferramentas analíticas, comece a esbarrar nas questões de escalabilidade e custos de manutenção desses dados.

Bancos de dados relacionais escalam, mas quanto maior o tamanho, mais custoso se torna essa escalabilidade, seja pelo custo de novas máquinas, seja pelo aumento de especialistas nos bancos de dados utilizados.

Já os não relacionais, permitem uma escalabilidade mais barata e menos trabalhosa, pois não exigem máquinas extremamente poderosas e sua facilidade de manutenção permite que um número menor de profissionais seja necessário.

Assim, os **bancos de dados NoSQL, vão ficando mais populares entre as grandes empresas pois reúnem as características de poder trabalhar com dados semi-estruturados** ou crus vindos de diversas origens (arquivos de log, web-sites, arquivos multimídia, etc...).

Podemos listar algumas dessas características abaixo:

**Utilização do processamento paralelo para processamento das informações:** para se atingir uma performance razoável no processamento de grandes volumes de dados, é mais eficiente dividir a tarefa em várias outras menores e que podem assim, serem executadas ao mesmo tempo, distribuindo essas tarefas pelos vários processadores disponíveis, para isso, os sistemas precisam atingir um alto grau de maturidade no processamento paralelo.

O uso de muitos processadores baratos, não só oferece melhor performance, mas se torna também uma solução economicamente interessante, pois dessa forma é possível escalar o sistema horizontalmente apenas adicionando hardware e não limita a empresa a poucos fornecedores de hardware mais poderoso.

**Distribuição em escala global:** para atender seus usuários de forma eficiente, algumas empresas utilizam vários data centers, localizados em diversas partes do pais ou do mundo.

Com isso, uma série de questões sobre disponibilidade e performance são levantadas ao construir os sistemas.

A distribuição deles combinada com o hardware barato, impõe ao sistema a necessidade de ser robusto o suficiente para tolerar falhas constantes e imprevisíveis, seja de hardware, seja da infraestrutura do lugar onde o data center se encontra.

Pensando nessas questões, bem como nas necessidades internas ou dos clientes, foi surgindo uma grande quantidade de bancos de dados não relacionais de trabalham de diferentes maneiras, e as principais estão listadas abaixo.

- **Banco de dados que trabalham no esquema chave/valor (Key/Value):** sistemas distribuídos nessa categoria, também conhecidos como tabelas de hash distribuídas, armazenam objetos indexados por chaves, e possibilitam a busca por esses objetos a partir de suas chaves.

Alguns bancos que utilizam esse padrão são: DynamoDb, Couchbase, Riak, Azure Table Storage, Redis, Tokyo Cabinet, Berkeley DB, etc...

- **Bancos de dados orientados a documentos:** os documentos dos bancos dessa categoria, são coleções de atributos e valores, onde um atributo pode ser multi-valorado. Em geral, os bancos de dados orientados a documento não possuem esquema, ou seja, os documentos armazenados não precisam possuir estrutura em comum.

Essa característica faz deles boas opções para o armazenamento de dados semi estruturados.

Alguns bancos que utilizam esse padrão são: MongoDb, CouchDB, RavenDb, etc.

- **Bancos de dados de famílias de colunas** : Bancos relacionais normalmente guardam os registros das tabelas contiguamente no disco. Por exemplo, caso se queira guardar id, nome e endereço de usuários em um sistema de cadastro, os registros seriam: Id1, Nome1, Endereço1; Id2, Nome2, Endereço2.

Essa estrutura torna a escrita muito rápida, pois todos os dados de um registro são colocados no disco com uma única escrita no banco. Essa estrutura também é eficiente caso se queira ler registros inteiros. Mas para situações onde se quer ler algumas poucas colunas de muitos registros, essa estrutura é pouco eficiente, pois muitos blocos do disco terão de ser lidos. Para esses casos onde se quer otimizar a leitura de dados estruturados, bancos de dados de famílias de colunas são mais interessantes, pois eles guardam os dados contiguamente por coluna.

O exemplo anterior em um banco de dados dessa categoria ficaria: Id1, Id2; Nome1, Nome2; Endereço1, Endereço2.

Por esse exemplo é possível perceber a desvantagem de um banco de dados de famílias de colunas: a escrita de um novo registro é bem mais custosa do que em um banco de dados tradicional. Assim, num primeiro momento, os bancos tradicionais são mais adequados aprocessamento de transações online (OLTP) enquanto os bancos de dados de famílias de
colunas são mais interessantes para processamento analítico online (OLAP). O Bigtable é uma implementação da Google dessa categoria de bancos de dados . Outros bancos de dados que são orientados a coluna: Hadoop, Cassanda, Hypertable, Amazon SimpleDB, etc. 

- **Bancos de dados de grafos:** **diferentemente de outros tipos de bancos de dados NoSQL, esse está diretamente relacionado a um modelo de dados estabelecido**, o modelo de grafos. A ideia desse modelo é representar os dados e / ou o esquema dos dados como grafos dirigidos, ou como estruturas que generalizem a noção de grafos .

O modelo de grafos é mais interessante que outros quando “informações sobre a inter-conectividade ou a topologia dos dados são mais importantes, ou tão importante quantos os dados propriamente ditos . O modelo orientado a grafos possui três componentes básicos: os nós (são os vértices do grafo), os relacionamentos (são as arestas) e as propriedades (ou atributos) dos nós e relacionamentos.

Neste caso, o banco de dados pode ser visto como um multigrafo rotulado e direcionado, onde cada par de nós pode ser conectado por mais de uma aresta. Um exemplo pode ser : “Quais cidades foram visitadas anteriormente (seja residindo ou viajando) por pessoas que viajaram para o Rio de Janeiro ?” No modelo relacional esta consulta poderia ser muito complexa devido a necessidade de múltiplas junções, o que poderia acarretar uma diminuição no desempenho da aplicação. Porém, por meio dos relacionamentos inerentes aos grafos, estas consultas tornam-se mais simples e diretas.

Alguns bancos que utilizam esse padrão são: Neo4J, Infinite Graph, InforGrid, HyperGraphDB, etc. Como podem ver, **os bancos de dados que se utilizam do conceito NoSQL**, abrangem uma ampla gama de possibilidades de armazenamento da informação.


_____________

Qual é a função do componente “mecanismo de armazenamento” em um Sistema de Gerenciamento de Banco de Dados (SGBD)?

Fornecer uma linguagem de acesso ao banco de dados.

Otimizar consultas de acesso a dados.

Registrar todas as alterações feitas nos dados.

Armazenar dados no nível do sistema operacional.

Gerenciar o acesso simultâneo a dados.

Resposta:
A função do componente "mecanismo de armazenamento" em um Sistema de Gerenciamento de Banco de Dados (SGBD) é:

**Armazenar dados no nível do sistema operacional.**

O mecanismo de armazenamento é responsável por gerenciar como os dados são armazenados fisicamente no disco e interagir com o sistema operacional para realizar operações de leitura e gravação.

_____________

Qual é a principal diferença entre os bancos de dados de valores-chave e os bancos de dados de colunas largas?

Os bancos de dados de colunas largas utilizam formato JSON para armazenar dados.

Os bancos de dados de valores-chave são usados para consultas por colunas.

Os bancos de dados de valores-chave organizam dados como nós e relacionamentos.

Os bancos de dados de colunas largas são ideais para representar relacionamentos de dados complexos.

Os bancos de dados de valores-chave armazenam colunas separadamente no disco.

Resposta:
Você está correto. A resposta correta é:

**Os bancos de dados de valores-chave armazenam dados como pares chave-valor, enquanto os bancos de dados de colunas largas armazenam colunas separadamente no disco.**

A principal diferença é que bancos de dados de valores-chave armazenam dados em pares chave-valor, onde cada chave é associada a um valor específico. Já os bancos de dados de colunas largas armazenam dados organizados por colunas, permitindo que colunas sejam armazenadas separadamente no disco, o que é útil para otimizar consultas que acessam apenas algumas colunas de um conjunto de dados grande.

A opção correta é:

**Os bancos de dados de valores-chave armazenam colunas separadamente no disco.**
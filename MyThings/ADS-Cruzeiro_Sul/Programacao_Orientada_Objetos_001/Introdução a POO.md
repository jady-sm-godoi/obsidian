
Um paradigma de programação fornece (e determina) a visão que o programador possui sobre a estruturação e execução do programa. Assim como ao resolver um problema podemos adotar uma entre variadas metodologias, ao criar um programa podemos adotar um determinado paradigma de programação para desenvolvê-lo.

A metodologia Orientação a Objetos é baseada em “objetos do mundo real”, e por este motivo é mais intuitiva ao ser humano. Em um sistema orientado a objetos, os dados e todas as operações, que manipulam esses dados, são agrupados em uma única estrutura: “as classes”. Desde o início do desenvolvimento desses sistemas e, em todas as suas fases, o analista trabalha com o mesmo elemento de abstração, os objetos.

###  Histórico

A orientação a objetos (OO) foi utilizada primeiramente na década de 70.

A Origem na linguagem SIMULA-67 (década de 60 – Noruega), que já implementava alguns conceitos da Orientação a Objetos.

SIMULA-68 foi a primeira linguagem a suportar os conceitos da Orientação a Objetos.

_Smaltalk_, criada pela _Xerox_, popularizou e incentivou a Orientação a Objetos.

Outras linguagens de Orientação a Ojbjetos: C++, Object Pascal (Delphi), C#, Java.

Java, de fato, popularizou a Orientação a Objetos.

### **Programa Estruturada _versus_ Programa Orientado a Objetos**

-   **Estruturado:** Ênfase nos procedimentos, implementados em blocos estruturados, com comunicação entre procedimentos por passagem de dados;
    
- **Orientado a objetos:** Dados e procedimentos fazem parte de um só elemento básico (objeto). Os elementos básicos comunicam-se entre si, caracterizando a execução do programa à Dados e procedimentos agrupados em um só elemento.
![[Pasted image 20240806095544.png]]


## **Por que a Tecnologia de Objetos?**

Os principais problemas do _software_ hoje são:

- Diminuir o custo e o tempo da mudança;
    
- Aumentar a capacidade e facilidade de adaptação.
    

Objetos são especialmente bons para:

- Reduzir o tempo necessário para adaptar um sistema existente (reação mais rápida à mudanças no seu ambiente de negócio);
    
- Reduzir o esforço, a complexidade e os custos associados à mudança.

### **Orientação a Objetos – Fase e Responsabilidade**

- **Análise:**
    
    - Entender o domínio do problema;
    - Definir a estrutura estática da aplicação;
    - Criar vocabulário comum de conceitos.
    
- **Projeto:**
    
    - Apresentar a melhor solução para problema;
    - Definir a estrutura dinâmica da aplicação;
    - Fazer especificação.
    
- **Implementação:**
    
    - Construir a aplicação em conformidade com a especificação;
    - Fazer testes e validações;
    - Fazer implantação.

![[Pasted image 20240806095825.png]]

## Conceito da Análise e Projeto Orientado a Objetos (OOA&D - Object-oriented Analysis and Design)

é um processo que contém suporte a notação para definição de _software_ baseado no conceito de objetos que combinam estrutura e comportamento na mesma entidade.

Este processo geralmente não é linear, mas é previsível, cíclico, e passível de teste e rastreamento.
Consiste em três partes:

- Processo (São as atividades);
    
- Notação (demonstra a interação dos objetos);
    
- Regras (descreve como o sistema deve trabalhar).
    
#### Principais conceitos:
- Classes
- Objetos

## Classes
Uma classe é uma entidade descreve um conjunto de objetos com propriedades e comportamentos semelhantes e com relacionamentos comuns com outros objetos

Usamos as classes para capturar o vocabulário do sistema que está em desenvolvimento. Essas classes podem incluir abstrações que são parte do domínio do problema, assim como as classes que fazem uma implementação. Podemos usar ainda as classes para representar itens de _software_, de _hardware_ e até itens que sejam somente conceituais.

Contexto: Venda de flores.  
Chris precisa enviar flores para o amigo Robin que mora em outra cidade.
![[Pasted image 20240828200208.png]]

- POO é estruturada como uma comunidade de agentes que interagem chamados de objetos;
- Cada objeto tem um papel a ser executado;
- Cada objeto fornece serviços ou executam ações que podem ser utilizadas por outros membros da comunidade.

### **Mensagens e Métodos**

- Uma ação é a transmissão de uma mensagem para um agente (objeto) responsável pela ação;
    
- Quando um objeto aceita a mensagem ele é responsável por tratar a ação;
    
- Em resposta a esta mensagem o receptor executará algum método para atender a solicitação.

### **Responsabilidades**

- Descreve o comportamento em termos de responsabilidades;
    
- O conjunto de responsabilidades de um objeto é descrito através e protocolos

### **Classes e Instâncias**

- O Florista é um exemplo de classe, pois representa todos os floristas. O Florista Pitoco, e o Bodjo são instâncias desta classe;
    
- Um outro exemplo de classes e instâncias é forma de gelatina e as gelatinas.

### **Notação UML para Classe e Objetos**

![[Pasted image 20240828201104.png]]
A seção superior é reservada para a identificação da classe. Essa seção é obrigatório o preenchimento. O nome da classe deve conter somente letras e palavras concatenadas e a primeira letra deve ser escrita em maiúsculo.

Na segunda seção são exibidos os atributos da classe, esses atributos são variáveis membro da classe que podem ser usadas pelos métodos tanto para acesso ou escrita.

O atributo pode ser criado com as seguintes notações:

- + Acesso público, tanto funções membros da classe e funções externas podem ter acesso ao atributo público;
    
- – Acesso privado, somente funções membros da classe tem acesso a esses atributos;
    
- "#" Acesso protegido, o atributo também é privado, mas as funções membros das classes derivadas também tem acesso aos atributos.

Na última seção são exibidos os métodos da classe, ou seja, as funções que a classe possui.

Os métodos também seguem a mesma notação que os atributos.

- + Acesso público, tanto funções membros da classe e funções externas podem ter acesso ao atributo público;
    
- – Acesso privado, somente funções membros da classe tem acesso a esses atributos;
    
- "#" Acesso protegido, o atributo também é privado mas as funções membros das classes derivadas também tem acesso aos atributos.
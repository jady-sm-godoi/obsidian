
Os padrões de criação são um conjunto de padrões de projeto que lidam com a criação de objetos de forma flexível, eficiente e reutilizável. Eles abstraem o processo de instanciação de objetos, isolando o código de criação do restante do código do sistema. Isso promove a flexibilidade, modularidade e reutilização de código.

Aqui estão alguns exemplos de padrões de criação com uma breve explicação e exemplos práticos:

1. **Singleton:**
    
    - O padrão Singleton garante que uma classe tenha apenas uma instância e fornece um ponto global de acesso a essa instância.
    - Isso é útil quando precisamos de uma única instância de uma classe para ser compartilhada por todo o sistema, como um gerenciador de logs, configurações do sistema, ou conexão com banco de dados.

```class Singleton:
    _instance = None
    
    def __new__(cls):
        if cls._instance is None:
            cls._instance = super().__new__(cls)
        return cls._instance

# Exemplo de uso
obj1 = Singleton()
obj2 = Singleton()
print(obj1 == obj2)  # Saída: True (mesma instância)
```

2. **Factory Method:**

	- O padrão Factory Method define uma interface para criar um objeto, mas permite que as subclasses escolham o tipo de objeto a ser criado.
	- Isso é útil quando temos uma hierarquia de classes e queremos que as subclasses decidam qual classe concreta instanciar.

```from abc import ABC, abstractmethod

class Creator(ABC):
    @abstractmethod
    def factory_method(self):
        pass

    def create_object(self):
        return self.factory_method()

class ConcreteCreatorA(Creator):
    def factory_method(self):
        return ConcreteProductA()

class ConcreteCreatorB(Creator):
    def factory_method(self):
        return ConcreteProductB()

class Product(ABC):
    @abstractmethod
    def operation(self):
        pass

class ConcreteProductA(Product):
    def operation(self):
        return "Product A operation"

class ConcreteProductB(Product):
    def operation(self):
        return "Product B operation"

# Exemplo de uso
creator = ConcreteCreatorA()
product = creator.create_object()
print(product.operation())  # Saída: Product A operation
```

3. **Abstract Factory:**

	- O padrão Abstract Factory fornece uma interface para criar famílias de objetos relacionados ou dependentes sem especificar suas classes concretas.
	- Isso é útil quando precisamos criar objetos que compartilham uma mesma família de classes, como widgets de interface gráfica para diferentes sistemas operacionais.
```from abc import ABC, abstractmethod

class AbstractFactory(ABC):
    @abstractmethod
    def create_product_a(self):
        pass

    @abstractmethod
    def create_product_b(self):
        pass

class ConcreteFactory1(AbstractFactory):
    def create_product_a(self):
        return ConcreteProductA1()

    def create_product_b(self):
        return ConcreteProductB1()

class ConcreteFactory2(AbstractFactory):
    def create_product_a(self):
        return ConcreteProductA2()

    def create_product_b(self):
        return ConcreteProductB2()

class AbstractProductA(ABC):
    @abstractmethod
    def operation_a(self):
        pass

class ConcreteProductA1(AbstractProductA):
    def operation_a(self):
        return "Product A1 operation"

class ConcreteProductA2(AbstractProductA):
    def operation_a(self):
        return "Product A2 operation"

class AbstractProductB(ABC):
    @abstractmethod
    def operation_b(self):
        pass

class ConcreteProductB1(AbstractProductB):
    def operation_b(self):
        return "Product B1 operation"

class ConcreteProductB2(AbstractProductB):
    def operation_b(self):
        return "Product B2 operation"

# Exemplo de uso
factory1 = ConcreteFactory1()
product_a1 = factory1.create_product_a()
product_b1 = factory1.create_product_b()
print(product_a1.operation_a())  # Saída: Product A1 operation
print(product_b1.operation_b())  # Saída: Product B1 operation
```

Esses são apenas alguns exemplos dos padrões de criação mais comuns. Cada um deles tem seus próprios casos de uso e vantagens, e a escolha do padrão correto depende das necessidades específicas do projeto em questão. Esses padrões ajudam a promover a flexibilidade, a reutilização de código e a manutenção de um design modular e escalável.
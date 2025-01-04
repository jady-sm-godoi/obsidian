**Herança** é um dos pilares da Orientação a Objetos e permite que uma classe (subclasse ou classe derivada) herde atributos e métodos de outra classe (superclasse ou classe base). A classe derivada pode estender ou especializar o comportamento da classe base, além de adicionar novos atributos e métodos próprios.

**Principais conceitos da herança:**

1. **Classe Base (Superclasse):** É a classe da qual outras classes herdam atributos e métodos. Ela serve como um modelo genérico para as classes derivadas.
    
2. **Classe Derivada (Subclasse):** É uma classe que herda atributos e métodos de uma classe base. Ela pode adicionar novos comportamentos, sobrescrever métodos existentes e, em alguns casos, ocultar atributos ou métodos da classe base.
    
3. **Hierarquia de Classes:** Classes podem formar uma hierarquia, onde uma classe base pode ter várias classes derivadas e cada classe derivada pode, por sua vez, servir como classe base para outras classes derivadas.
    

**Exemplo de Herança:**

Vamos considerar um exemplo simples com uma classe base `Animal` e duas subclasses `Cachorro` e `Gato`.

```class Animal:
    def __init__(self, nome):
        self.nome = nome

    def fazer_som(self):
        pass  # Método genérico para fazer som, será sobrescrito nas subclasses


class Cachorro(Animal):
    def fazer_som(self):
        return "Au au!"


class Gato(Animal):
    def fazer_som(self):
        return "Miau!"


# Criando objetos das subclasses
rex = Cachorro("Rex")
whiskers = Gato("Whiskers")

# Chamando o método fazer_som de cada objeto
print(rex.fazer_som())      # Saída: Au au!
print(whiskers.fazer_som()) # Saída: Miau!
```

Neste exemplo, a classe `Animal` é a classe base que contém o atributo `nome` e o método `fazer_som`. As subclasses `Cachorro` e `Gato` herdam esses atributos e métodos, e cada uma delas especializa o método `fazer_som` para retornar o som característico de cada animal.

Dessa forma, a herança permite reutilizar código, promove a organização e a hierarquia de classes, e facilita a extensão e manutenção do código. No entanto, é importante usá-la com cuidado para evitar hierarquias profundas e acoplamento excessivo entre classes.
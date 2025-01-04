**Polimorfismo** é um dos princípios fundamentais da Orientação a Objetos e refere-se à capacidade de um objeto se comportar de diferentes maneiras, dependendo do contexto em que é usado. O polimorfismo permite que objetos de diferentes classes respondam ao mesmo método de maneira diferente.

Existem dois tipos principais de polimorfismo: polimorfismo de sobrecarga (ou polimorfismo estático) e polimorfismo de sobrescrita (ou polimorfismo dinâmico).

1. **Polimorfismo de Sobrecarga (ou Polimorfismo Estático):** É quando uma classe tem vários métodos com o mesmo nome, mas com diferentes parâmetros. O método que será executado depende dos parâmetros passados no momento da chamada.
    
2. **Polimorfismo de Sobrescrita (ou Polimorfismo Dinâmico):** É quando uma classe filha (subclasse) fornece uma implementação específica para um método que já está definido em sua classe pai (superclasse). O método na classe filha substitui (sobrescreve) o método da classe pai, permitindo que o objeto da classe filha seja tratado como um objeto da classe pai, mas com comportamento específico da classe filha.
    

**Exemplo de Polimorfismo de Sobrescrita:**

Considere um exemplo com uma classe base `Animal` e duas subclasses `Cachorro` e `Gato`, onde cada uma delas implementa o método `emitir_som()` de forma diferente.
```class Animal:
    def emitir_som(self):
        pass  # Método genérico para emitir som, será sobrescrito nas subclasses


class Cachorro(Animal):
    def emitir_som(self):
        return "Au au!"


class Gato(Animal):
    def emitir_som(self):
        return "Miau!"


# Função para fazer o animal emitir som, independentemente do tipo
def fazer_barulho(animal):
    return animal.emitir_som()


# Criando objetos das subclasses
rex = Cachorro()
whiskers = Gato()

# Chamando a função fazer_barulho com diferentes tipos de animais
print(fazer_barulho(rex))      # Saída: Au au!
print(fazer_barulho(whiskers)) # Saída: Miau!
```

Neste exemplo, temos a classe base `Animal` com o método `emitir_som`, que é sobrescrito nas subclasses `Cachorro` e `Gato` para retornar os sons característicos de cada animal. A função `fazer_barulho` recebe um objeto de qualquer uma das subclasses `Animal` e chama o método `emitir_som`, permitindo que cada objeto se comporte de maneira diferente, conforme definido em sua própria classe.

Assim, o polimorfismo de sobrescrita permite tratar objetos de diferentes classes de maneira uniforme, chamando métodos com o mesmo nome, mas com comportamentos específicos de cada classe. Isso promove a flexibilidade e a reutilização de código em um sistema orientado a objetos.

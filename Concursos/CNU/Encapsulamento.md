
**Encapsulamento** é um dos princípios fundamentais da Orientação a Objetos e refere-se à ideia de esconder os detalhes de implementação de um objeto e expor apenas uma interface para interação com esse objeto. Isso significa que os dados (atributos) dentro de um objeto devem ser protegidos de acesso direto e manipulação externa, e o acesso a esses dados deve ser feito por meio de métodos específicos (métodos acessores ou getters e métodos modificadores ou setters).

O encapsulamento traz benefícios como:

1. **Controle de Acesso:** Através do encapsulamento, podemos definir quais atributos são acessíveis de fora da classe e quais são restritos, garantindo uma interação segura e controlada com os objetos.
    
2. **Modularidade:** Ao encapsular os detalhes de implementação dentro de um objeto, podemos modificar esses detalhes sem afetar outros componentes do sistema, desde que a interface pública permaneça a mesma. Isso promove a modularidade e facilita a manutenção do código.
    
3. **Reutilização de Código:** O encapsulamento permite que objetos sejam reutilizados em diferentes partes do sistema, pois o comportamento do objeto é independente de sua implementação interna.
    

**Exemplo de Encapsulamento:**

Considere uma classe `ContaBancaria` que representa uma conta em um banco. Vamos encapsular os detalhes do saldo da conta para garantir que ele só possa ser acessado e modificado de maneira controlada.

```class ContaBancaria:
    def __init__(self, numero_conta, saldo_inicial):
        self.numero_conta = numero_conta
        self.__saldo = saldo_inicial  # Atributo privado

    def depositar(self, valor):
        self.__saldo += valor

    def sacar(self, valor):
        if valor <= self.__saldo:
            self.__saldo -= valor
        else:
            print("Saldo insuficiente.")

    def get_saldo(self):  # Método acessor (getter)
        return self.__saldo

# Criando uma conta bancária
conta = ContaBancaria("123456", 1000)

# Tentando acessar o saldo diretamente (o que não é recomendado)
# print(conta.__saldo)  # Isso resultaria em um erro, pois o atributo é privado

# Acessando o saldo através do método acessor
print(conta.get_saldo())  # Saída: 1000

# Realizando um depósito
conta.depositar(500)
print(conta.get_saldo())  # Saída: 1500

# Realizando um saque
conta.sacar(200)
print(conta.get_saldo())  # Saída: 1300
```

Neste exemplo, o saldo da conta (`__saldo`) é um atributo privado, e não pode ser acessado diretamente de fora da classe `ContaBancaria`. Em vez disso, é necessário utilizar o método acessor `get_saldo()` para obter o saldo da conta. Isso garante o encapsulamento dos detalhes de implementação e o controle sobre como o saldo é acessado e modificado.
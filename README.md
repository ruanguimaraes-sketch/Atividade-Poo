# Atividade poo 

O que é Programação Orientada a Objetos (POO)?

A Programação Orientada a Objetos (POO) é um paradigma de desenvolvimento de software baseado no conceito de objetos — entidades que representam elementos do mundo real ou ideias abstratas e que possuem dados (atributos) e comportamentos (métodos). Em vez de organizar o código como uma sequência de instruções ou funções independentes, a POO foca na modelagem de objetos que interagem entre si para resolver problemas.

Por que a POO surgiu e que problema ela resolve?

A POO surgiu como uma resposta às limitações dos paradigmas anteriores, especialmente o paradigma procedural, onde o código tende a crescer de forma desorganizada à medida que a complexidade aumenta. Nesse modelo mais antigo:

dados e funções eram separados;

alterações em uma parte do sistema podiam gerar efeitos colaterais inesperados em todo o código;

programas grandes se tornavam difíceis de manter e evoluir.

A POO propõe uma solução organizando o software de maneira mais próxima do pensamento humano e do mundo real, agrupando dados e comportamentos em entidades coesas (objetos). Isso facilita:

reutilização de código,

manutenção,

escalabilidade,

redução de acoplamento entre as partes do sistema.

Os Quatro Pilares da POO

A POO se apoia em quatro conceitos fundamentais que a tornam poderosa e flexível. A seguir, cada pilar é explicado e exemplificado.

1. Abstração
   
Abstração é o processo de simplificar a complexidade, destacando apenas as características essenciais de um objeto e escondendo detalhes irrelevantes. Ao aplicar abstração, representamos um conceito complexo de forma clara e objetiva.

Exemplo (Python)
from abc import ABC, abstractmethod

class Forma(ABC):
    @abstractmethod
    def calcular_area(self):
        pass

class Circulo(Forma):
    def __init__(self, raio):
        self.raio = raio

    def calcular_area(self):
        return 3.14 * self.raio ** 2


figura = Circulo(5)
print(figura.calcular_area())


Aqui, Forma é uma abstração: sabemos que formas têm área, mas não precisamos saber como cada uma calcula.

2. Encapsulamento

Encapsulamento consiste em proteger os dados internos de um objeto, permitindo acesso apenas através de métodos controlados. Isso evita manipulação indevida e garante que o objeto mantenha sua integridade.

Exemplo (Python)
class ContaBancaria:
    def __init__(self, saldo_inicial=0):
        self.__saldo = saldo_inicial  # atributo privado

    def depositar(self, valor):
        if valor > 0:
            self.__saldo += valor

    def sacar(self, valor):
        if 0 < valor <= self.__saldo:
            self.__saldo -= valor

    def obter_saldo(self):
        return self.__saldo


conta = ContaBancaria(100)
conta.depositar(50)
conta.sacar(30)
print(conta.obter_saldo())


O atributo __saldo só pode ser alterado pelos métodos da classe.

3. Herança

Herança permite que uma classe (classe filha) reutilize e estenda características de outra classe (classe pai). Isso reduz duplicação de código e organiza melhor as relações entre objetos.

Exemplo (Python)
class Animal:
    def falar(self):
        return "Som genérico"

class Cachorro(Animal):
    def falar(self):
        return "Au au!"


a = Animal()
c = Cachorro()
print(a.falar())  # Som genérico
print(c.falar())  # Au au!


Cachorro herda de Animal e redefine o método falar.

4. Polimorfismo
Conceito

Polimorfismo significa “muitas formas”. Ele permite que métodos com o mesmo nome se comportem de maneiras diferentes dependendo do objeto que os utiliza.

Exemplo (Python)
class Gato:
    def falar(self):
        return "Miau!"

class Vaca:
    def falar(self):
        return "Muu!"

def emitir_som(animal):
    print(animal.falar())

emitir_som(Gato())
emitir_som(Vaca())

A função emitir_som funciona com qualquer objeto que implemente falar, independentemente da classe.

Conclusão

A Programação Orientada a Objetos é essencial para desenvolver sistemas mais organizados, flexíveis e fáceis de manter. Ao elaborar este relatório, aprofundei conceitos fundamentais como abstração, encapsulamento, herança e polimorfismo, entendendo como cada pilar contribui para tornar o software mais robusto e alinhado ao mundo real. A POO continua sendo um dos paradigmas mais importantes da engenharia de software, especialmente para projetos que exigem escalabilidade e clareza estrutural.

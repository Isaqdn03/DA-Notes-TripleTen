
**2025-01-15 18:45**

**Sprint:** [[Sprint5]]

**Topic:** #python-intermediario 

**Connections:** 

---
# **Programação orientada a objetos**

# Programação Orientada a Objetos em Python

## Introdução
Python é uma linguagem puramente orientada a objetos, onde tudo, incluindo números, strings, funções e até mesmo exceções, são objetos. Cada objeto pertence a uma classe específica que define suas características e comportamentos.

## Implementação Básica com Dicionários vs Classes

### Abordagem com Dicionários

```python
mage = {'health': 50, 'damage': 10, 'knowledge': 95}
knight = {'health': 100, 'damage': 25, 'knowledge': 20}

arthur = knight.copy()
arthur['name'] = 'Arthur'

richard = knight.copy()
richard['name'] = 'Richard'

def heal(character):
    character['health'] += 20

heal(richard)
```

**Explicação detalhada:**
- Criamos dicionários para representar diferentes tipos de personagens
- Cada personagem tem atributos de saúde, dano e conhecimento
- Usamos `.copy()` para criar novos personagens baseados em um template
- A função `heal()` aumenta a saúde do personagem em 20 pontos

**Saída esperada:**
```python
print(richard['health'])  # Antes do heal: 100
heal(richard)
print(richard['health'])  # Depois do heal: 120
```

### Implementação com Classes Básicas

```python
class Knight:
    def __init__(self, name):
        self.health = 100
        self.damage = 25
        self.knowledge = 20
        self.name = name

arthur = Knight('Arthur')
richard = Knight('Richard')
```

**Explicação detalhada:**
- Definimos uma classe `Knight` usando a palavra-chave `class`
- O método `__init__` é o construtor da classe
- `self` refere-se à instância atual sendo criada
- Cada atributo é definido usando `self.atributo`
- Criamos duas instâncias diferentes com nomes diferentes

**Saída esperada:**
```python
print(arthur.name)  # Arthur
print(richard.name)  # Richard
print(arthur.health)  # 100
```

## Trabalhando com Atributos

```python
class Knight:
    def __init__(self, name):
        self.health = 100
        self.damage = 25
        self.knowledge = 20
        self.name = name

arthur = Knight('Arthur')
print(arthur.health)  # Acesso direto
arthur.health = 150   # Modificação direta
print(arthur.__dict__)  # Visualização de todos os atributos
```

**Explicação detalhada:**
- Podemos acessar atributos diretamente usando a notação de ponto
- Atributos podem ser modificados após a criação do objeto
- `__dict__` mostra todos os atributos do objeto em formato de dicionário

**Saída esperada:**
```python
100  # Primeiro print
150  # Segundo print após modificação
{'health': 150, 'damage': 25, 'knowledge': 20, 'name': 'Arthur'}  # __dict__
```

## Métodos de Classe

### Métodos Regulares

```python
class Knight:
    def __init__(self, name):
        self.health = 100
        self.damage = 25
        self.knowledge = 20
        self.name = name
    
    def heal(self, amount):
        self.health += amount
    
    def learn(self, amount):
        self.knowledge += amount

arthur = Knight('Arthur')
arthur.heal(10)
arthur.learn(2)
```

**Explicação detalhada:**
- Métodos são funções definidas dentro da classe
- Todo método regular recebe `self` como primeiro parâmetro
- `heal` aumenta a saúde do personagem
- `learn` aumenta o conhecimento do personagem
- Os métodos podem receber parâmetros adicionais

**Saída esperada:**
```python
print(arthur.health)  # 110 (100 + 10)
print(arthur.knowledge)  # 22 (20 + 2)
```

### Métodos Estáticos

```python
class Stock:
    def __init__(self, ticker, amount):
        self.ticker = ticker
        self.amount = amount

    @staticmethod
    def show_current_price(ticker):
        current = None  # Simulação da busca do preço
        print(current)

Stock.show_current_price('Apple')
```

**Explicação detalhada:**
- Métodos estáticos são decorados com `@staticmethod`
- Não precisam de uma instância para serem chamados
- Não recebem `self` como parâmetro
- Podem ser chamados diretamente na classe
- Úteis para operações que não dependem do estado do objeto

**Uso exemplo:**
```python
Stock.show_current_price('Apple')  # Chamada sem instância
stock = Stock('Apple', 100)
stock.show_current_price('Apple')  # Também funciona com instância
```

### Métodos de Classe

```python
class Stock:
    def __init__(self, ticker, amount, price):
        self.ticker = ticker
        self.amount = amount
        self.price = price
        self.total = self.price * self.amount

    @classmethod
    def from_string(cls, string):
        ticker, amount, price = string.split()
        return cls(ticker, int(amount), float(price))

abc = Stock.from_string('ABC 10 1.5')
```

**Explicação detalhada:**
- Métodos de classe são decorados com `@classmethod`
- Recebem a classe (`cls`) como primeiro parâmetro
- Podem criar instâncias da classe de maneiras alternativas
- Úteis para fornecer múltiplos construtores
- Processam os dados antes de criar a instância

**Saída esperada:**
```python
print(abc.__dict__)
# {'ticker': 'ABC', 'amount': 10, 'price': 1.5, 'total': 15.0}
```

## Herança

```python
class Character:
    def __init__(self, name):
        self.name = name
        self.health = 100
    
    def heal(self, value:int=20):
        self.health += value
    
    def learn(self, value:int=20):
        self.knowledge += value
        
class Knight(Character):
    def __init__(self, name):
        Character.__init__(self, name)  # Método tradicional
        self.damage = 25
        self.knowledge = 20

class Peasant(Character):
    def __init__(self, name):
        super().__init__(name)  # Método moderno
        self.damage = 10
        self.knowledge = 36

arthur = Knight('Arthur')
arthur.heal()
arthur.learn(100)
```

**Explicação detalhada:**
- `Character` é a classe base com funcionalidades comuns
- `Knight` e `Peasant` herdam de `Character`
- Duas formas de chamar o construtor da classe pai:
  1. `Character.__init__(self, name)` - forma explícita
  2. `super().__init__(name)` - forma moderna
- Classes filhas podem adicionar novos atributos
- Métodos da classe pai são herdados automaticamente

**Saída esperada:**
```python
print(arthur.__dict__)
# Inicial:
# {'name': 'Arthur', 'health': 100, 'damage': 25, 'knowledge': 20}

# Após heal() e learn(100):
# {'name': 'Arthur', 'health': 120, 'damage': 25, 'knowledge': 120}
```

# Pontos-Chave
- Tudo em Python é objeto
- Classes são templates para criar objetos
- Atributos armazenam dados
- Métodos definem comportamentos
- Métodos estáticos não requerem instância
- Métodos de classe trabalham com a própria classe
- Herança permite reutilização de código
- `self` refere-se à instância atual
- `super()` acessa métodos da classe pai

# Resumo
A Programação Orientada a Objetos em Python oferece uma estrutura robusta para organizar código através de classes e objetos. O sistema de classes permite criar estruturas reutilizáveis e modulares, enquanto a herança facilita a extensão e especialização do código. Os diferentes tipos de métodos (regulares, estáticos e de classe) fornecem flexibilidade para implementar diversos comportamentos e funcionalidades.








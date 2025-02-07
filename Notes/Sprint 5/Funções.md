
**2025-01-09 18:48**

**Sprint:** [[Sprint5]]

**Topic:** #python-intermediario 

**Connections:** 

---
# **Funções**

# Funções em Python: Conceitos Avançados

## Escopo de Variáveis

O escopo de variáveis em Python define onde uma variável pode ser acessada no código. Existem três tipos principais:

1. **Escopo Local**: Variáveis definidas dentro de uma função
2. **Escopo Global**: Variáveis definidas fora de funções
3. **Escopo Integrado**: Variáveis built-in do Python

### Escopo Local

```python
# my_func.py
product_price = 12.0
product_qty = 5

def total_price():
    product_price = 11.0
    product_qty = 4
    print(f'Preço total: {product_price * product_qty}')

total_price()
```

**Explicação**: Este código demonstra o escopo local onde as variáveis dentro da função têm precedência sobre as variáveis globais com o mesmo nome.

**Saída esperada**:
```
Preço total: 44.0
```

### Escopo Global

```python
# my_func.py
product_price = 12.0
product_qty = 5

def total_price():
    print(f'Preço total: {product_price * product_qty}')

total_price()
```

**Explicação**: Neste exemplo, a função usa as variáveis definidas no escopo global por não encontrar definições locais.

**Saída esperada**:
```
Preço total: 60.0
```

### Escopo Integrado

```python
# my_func.py
product_price = 12.0
product_qty = 5

def total_price():
    print(f'Preço total: {price * qty}')

total_price()
```

**Explicação**: Este código resulta em erro pois as variáveis `price` e `qty` não existem em nenhum escopo.

**Saída esperada**:
```
NameError: name 'price' is not defined
```

## Tipos de Argumentos de Funções

### Argumentos Posicionais

```python
# my_func.py
def trip_price(dist_miles, mpg, price, loc_from, loc_to):
    total_price = dist_miles * price / mpg
    print(f'Uma viagem de {loc_from} a {loc_to} custa ${total_price}')

trip_price(409, 35, 5.1, 'A', 'B')
```

**Explicação**: Os argumentos são passados na ordem exata da definição da função.

**Saída esperada**:
```
Uma viagem de A a B custa $59.59714285714285
```

### Argumentos Nomeados

```python
def trip_price(dist_miles, mpg, price, loc_from, loc_to):
    total_price = dist_miles * price / mpg
    print(f'Uma viagem de {loc_from} a {loc_to} custa ${total_price}')

trip_price(dist_miles=409, loc_from='A', loc_to='B', mpg=35, price=5.1)
```

**Explicação**: Os argumentos são passados usando seus nomes, permitindo uma ordem flexível.

**Saída esperada**:
```
Uma viagem de A a B custa $59.60
```

### Argumentos Padrão

```python
def trip_price(dist_miles, mpg, price, loc_from='A', loc_to='B'):
    total_price = dist_miles * price / mpg
    print(f'Uma viagem de {loc_from} a {loc_to} custa ${total_price}')

trip_price(409, 35, price=3.8)
```

**Explicação**: Argumentos com valores padrão podem ser omitidos na chamada da função.

**Saída esperada**:
```
Uma viagem de A a B custa $44.41
```

# Pontos-Chave:
- O escopo local tem precedência sobre o escopo global
- Argumentos posicionais devem seguir a ordem exata da definição
- Argumentos nomeados oferecem maior flexibilidade na ordem
- Argumentos padrão devem ser definidos após argumentos sem valor padrão
- Argumentos nomeados devem vir após argumentos posicionais na chamada da função

# Resumo
Este conteúdo abordou conceitos fundamentais sobre funções em Python, incluindo escopo de variáveis e diferentes tipos de argumentos. A compreensão desses conceitos é crucial para escrever código Python mais eficiente e evitar erros comuns relacionados a escopo e passagem de argumentos.










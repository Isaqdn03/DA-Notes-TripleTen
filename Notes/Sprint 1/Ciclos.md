
2024-10-07 19:11

Sprint:[[Sprint1]]

Topic: #basics 


# Ciclos

## **Operadores de Atribuição Composta**

Os operadores de atribuição composta são atalhos para operações matemáticas combinadas com atribuição, tornando o código mais conciso.

- `+=` : soma e atribui (equivalente a `x = x + 5`)
- `=` : subtrai e atribui (equivalente a `x = x - 5`)
- `=` : multiplica e atribui (equivalente a `x = x * 5`)
- `/=` : divide e atribui (equivalente a `x = x / 5`)

### Exemplo:

```python
items = 10
items += 5   # agora items é 15
items -= 5   # agora items é 10
items *= 3   # agora items é 30
items /= 5   # agora items é 6.0
```

### Perguntas:

1. O que acontece com `items` após o uso de `items -= 3`?
2. Como transformar `items` em um valor que é a metade de seu valor atual com atribuição composta?

---

## **Funções Integradas**

Essas funções realizam operações comuns de maneira simplificada.

- `sum()` : retorna a soma dos elementos de uma lista.
- `max()` : retorna o valor máximo.
- `min()` : retorna o valor mínimo.

### Exemplo:

```python
durations = [142, 175, 152, 195]
total = sum(durations)     # retorna 664
longest = max(durations)   # retorna 195
shortest = min(durations)  # retorna 142
```

### Perguntas:

1. Como você calcularia a soma dos números de uma lista usando a função `sum()`?
2. Qual função integrada usaria para encontrar o menor valor de uma lista de números?

---

## **Ciclos `for`**

O ciclo `for` itera sobre elementos de uma sequência (listas, strings, etc.).

### Sintaxe:

```python
for element in lista:
    # faz algo com element
```

### Exemplo:

```python
generos = ['ação', 'drama', 'comédia']
for genero in generos:
    print(genero)
```

### Ciclo em Listas Aninhadas:

```python
movies = [
    ['The Godfather', 175],
    ['The Dark Knight', 152]
]
for movie in movies:
    print(movie[0])   # imprime o nome do filme
```

### Perguntas:

1. O que acontece se você usar um ciclo `for` para iterar sobre uma string?
2. Como acessar o segundo elemento de cada lista aninhada dentro de um ciclo `for`?

---

## **Ciclos `while`**

Um ciclo `while` continua executando enquanto a condição for `True`.

### Exemplo:

```python
peso_total = 0
capacidade = 400
while peso_total < capacidade:
    novo_peso = randint(30, 120)
    peso_total += novo_peso
    print(f'Peso total: {peso_total}')
```

### Ciclo com Contador:

```python
pessoas = 0
while pessoas < 10:
    pessoas += 1
    print(f'{pessoas} pessoas no elevador')
```

### Cuidado com Ciclos Infinitos:

Evite condições que nunca resultam em `False`:

```python
vendas = 1000
while vendas > 100:
    vendas += 1  # isso causará um ciclo infinito
```

### Perguntas:

1. Como garantir que um ciclo `while` não seja infinito?
2. Quando seria mais útil usar um ciclo `while` em vez de um `for`?











2024-10-07 22:04

Sprint: [[Sprint2]]

Topic: #basics 


# Functions
# **3.2 Sintaxe das funções**

### O QUE E UMA FUNCAO

**definicao TT:** uma abordagem modular, ou seja, eles escrevem pedaços de código que podem ser reutilizados para a mesma finalidade em diversas situações. Um elemento fundamental de código reutilizável é a função

Na programação, uma **função** funciona de maneira muito parecida a uma máquina que cozinha uma receita. A ideia básica é que escrevemos um conjunto de instruções e colocamos essas instruções em uma "caixa preta" com um nome. Quando a função é chamada, o Python vai executar as instruções e retornar o resultado.

**Minha definicao:** As funções são blocos de código nomeados, projetados para realizar uma tarefa específica. As funções permitem que você escreva o código uma vez e depois execute-o sempre que precisar realizar a mesma tarefa.

### COMO CRIAR UMA FUNCAO

1. Para criar uma função:
    - Use `def` seguido do nome da função e parênteses.
    - Coloque os parâmetros dentro dos parênteses, se houver.
    - Termine a linha com dois pontos (:).
2. Escreva o código da função com recuo de 4 espaços.
3. Use `return` para enviar o resultado da função.

![https://practicum-content.s3.amazonaws.com/resources/9.2_2PT_1702048077.png](https://practicum-content.s3.amazonaws.com/resources/9.2_2PT_1702048077.png)

### SINTAXE

**codigo TT:**

```python
def omelet(eggs_number):
    result = 'A omelete está pronta! Ovos usados: ' + str(eggs_number)
    return result

# chamada de função com 2 ovos, o resultado é atribuído à variável omelet_type
omelet_type = omelet(2)
print(omelet_type) # imprime o resultado da instrução anterior
```

Essa função em Python chamada "omelet" é definida para criar uma omelete. Vamos analisar cada parte:

1. `def omelet(eggs_number):` - Esta linha define a função chamada "omelet" que aceita um parâmetro chamado "eggs_number".
2. `result = 'A omelete está pronta! Ovos usados: ' + str(eggs_number)` - Esta linha cria uma string que inclui uma mensagem e o número de ovos usados. Note que `eggs_number` é convertido para string usando `str()`.
3. `return result` - Esta linha retorna a string criada.

Depois da definição da função, há um exemplo de como usá-la:

1. `omelet_type = omelet(2)` - Esta linha chama a função "omelet" com o argumento 2 (indicando 2 ovos) e atribui o resultado à variável "omelet_type".
2. `print(omelet_type)` - Esta linha imprime o resultado, que será a mensagem retornada pela função.

Quando executada, esta função irá imprimir: "A omelete está pronta! Ovos usados: 2".

### O QUE E PALAVRA CHAVE-RETURN

- A palavra-chave `return` é usada para fazer uma função retornar um valor específico
- Ela especifica o resultado que queremos que a função nos devolva, como o resultado de um cálculo
- Exemplo de uso: `def square(x): return x ** 2`
- `return` faz a função terminar imediatamente e retornar o valor especificado
- Qualquer código após o `return` não será executado
- É importante colocar todo o código que deve ser executado antes da instrução `return`

Este conceito é fundamental para entender como projetar e otimizar funções em Python

### QUAL E A DIFERENCA DE UMA FUNCAO COM E SEM RETURN

Função com return:

1. É como uma máquina que produz algo e entrega para você.
2. Você pode usar o resultado diretamente em outras partes do seu código.

```python
def dobrar(numero):
    return numero * 2

resultado = dobrar(5)
print(resultado)  # Vai imprimir: 10
```

### Função sem return:

1. É como uma máquina que faz uma tarefa, mas não entrega nada diretamente para você.
2. Ela pode fazer coisas (como imprimir na tela), mas não produz um valor que você possa usar depois.

```python
def cumprimentar(nome):
    print(f"Olá, {nome}!")

cumprimentar("Ana")  # Vai imprimir: Olá, Ana!
resultado = cumprimentar("Pedro")  # Vai imprimir: Olá, Pedro!
print(resultado)  # Vai imprimir: None
```

Na função com return, você pode usar o resultado em outras partes do seu código. Na função sem return, ela faz algo (como imprimir), mas não dá um valor que você possa usar depois.

# 3.3 **Uso de funções para simplificar códigos**

### Exemplo e Explicacao

## Sem função definida pelo usuário

Para cada item no carrinho:

- Calcular o total
- Com uma instrução condicional, comparar o total a 100
- Se o total for maior do que 100, subtrair 5% do total

O programa obtido será o seguinte:

```python
first_item_price = 10.0
first_item_quantity = 3

second_item_price = 51.0
second_item_quantity = 2

third_item_price = 4.0
third_item_quantity = 10

# encontre o total do primeiro item
first_item_total = first_item_quantity * first_item_price
if first_item_total > 100: # se for maior do que 100,
    first_item_total -= first_item_total * 0.05 # subtraia 5%
print(first_item_total)

# encontre o total do segundo item
second_item_total = second_item_quantity * second_item_price 
if second_item_total > 100: # se for maior do que 100,
    second_item_total -= second_item_total * 0.05 # subtraia 5%
print(second_item_total)

# encontre o total do terceiro item
third_item_total = third_item_quantity * third_item_price
if third_item_total > 100: # se for maior do que 100,
    third_item_total -= third_item_total * 0.05 # subtraia 5%
print(third_item_total)
```

```python
30.0
96.9
40.0
```

## Com uma função definida pelo usuário

Podemos dar um desconto de 10% se a quantidade for maior do que 5. Fazemos isso multiplicando o total por 0,9. Seu objetivo é escrever uma função chamada `calculate_total_price` que elimine a redundância e que possa ser usada para todos os três casos apresentados abaixo.

```python
def calculate_total_price(price, quantity):
    total = price*quantity
    if quantity > 5:
        total *= 0.9
    return total
    
# Defina os preços e as quantidades dos três itens
item_price_1 = 20.0
item_quantity_1 = 20

item_price_2 = 30.0
item_quantity_2 = 1

item_price_3 = 10.0
item_quantity_3 = 6

# Chame a função para cada item e armazene o resultado em uma variável
item_total_1 = calculate_total_price(item_price_1, item_quantity_1)# Escreva seu código aqui
item_total_2 = calculate_total_price(item_price_2, item_quantity_2)# Escreva seu código aqui
item_total_3 = calculate_total_price(item_price_3, item_quantity_3)# Escreva seu código aqui

# Imprima o preço total de cada item no carrinho
print(item_total_1)
print(item_total_2)
print(item_total_3)

```

```
360.0
30.0
54.0
```

# 3.4 **Funções de filtragem**

### Exemplo de filtragem usando funcoes

Use essas funções para filtrar filmes mais longos do que 140 minutos e imprima o resultado.

```python
def filter_by_timing(data, target_duration): 
    filtered_result = []
    for row in data:
        if row[4] > target_duration:
            filtered_result.append(row)
    return filtered_result 

def print_movie_info(data):
    for movie in data:
        print(movie)

movies_info = [
    ['The Shawshank Redemption', 'USA', 1994, 'drama', 142, 9.111],
    ['The Godfather', 'USA', 1972, 'drama, crime', 175, 8.730],
    ['The Dark Knight', 'USA', 2008, 'fantasy, action, thriller', 152, 8.499],
    ["Schindler's List", 'USA', 1993, 'drama', 195, 8.818],
    ['The Lord of the Rings: The Return of the King', 'New Zealand', 2003, 'fantasy, adventure, drama', 201, 8.625],
    ['Pulp Fiction', 'USA', 1994, 'thriller, comedy, crime', 154, 8.619],
    ['The Good, the Bad and the Ugly', 'Italy', 1966, 'western', 178, 8.521],
    ['Fight Club', 'USA', 1999, 'thriller, drama, crime', 139, 8.644],
    ['Harakiri', 'Japan', 1962, 'drama, action, history', 133, 8.106],
    ['Good Will Hunting', 'USA', 1997, 'drama, romance', 126, 8.077]
]

movies_filtered = filter_by_timing(movies_info, 140)# chame a função de filtragem aqui
print_movie_info(movies_filtered)# chame a função para imprimir os resultados aqui
```

```
['The Shawshank Redemption', 'USA', 1994, 'drama', 142, 9.111]
['The Dark Knight', 'USA', 2008, 'fantasy, action, thriller', 152, 8.499]
["Schindler's List", 'USA', 1993, 'drama', 195, 8.818]
['The Lord of the Rings: The Return of the King', 'New Zealand', 2003, 'fantasy, adventure, drama', 201, 8.625]
['Pulp Fiction', 'USA', 1994, 'thriller, comedy, crime', 154, 8.619]
['Fight Club', 'USA', 1999, 'thriller, drama, crime', 139, 8.644]
['Good Will Hunting', 'USA', 1997, 'drama, romance', 126, 8.077]
```

# 3.5 Variaveis globais e locais

### O QUE E UMA VARIAVEL LOCAL

**definicao:** Variáveis locais são definidas dentro de uma função e só podem ser acessadas dentro dessa função. Elas são criadas quando a função é chamada e destruídas quando a função termina. Variáveis locais podem ser acessadas apenas dentro do escopo da função em que elas são definidas. Isso significa que se uma variável é definida dentro de uma função, ela não pode ser acessada fora daquela função.

**minha definicao:** variaveis locais sao varias criadas dentro de uma funcao, e so pode ser acessadas dentro dessa funcao na qual foi criada.

**Exemplo:**

```python
def calcular_area_retangulo(largura, altura):
    area = largura * altura  # 'area' é uma variável local
    return area

resultado = calcular_area_retangulo(5, 3)
print(resultado)  # Isso imprimirá 15

# Tentar acessar 'area' aqui causaria um erro, pois é uma variável local
# print(area)  # Isso resultaria em um erro
```

Neste exemplo, 'area' é uma variável local dentro da função 'calcular_area_retangulo'. Ela só pode ser acessada dentro dessa função e não está disponível fora dela. As variáveis 'largura' e 'altura' também são locais para esta função.

Este conceito está alinhado com a definição de variável local que você forneceu: "variáveis locais são variáveis criadas dentro de uma função, e só podem ser acessadas dentro dessa função na qual foram criadas."

### O QUE E UMA VARIAVEL GLOBAL

**Definicao:** Variáveis globais, por outro lado, podem ser acessadas de qualquer parte do código, inclusive de dentro das funções. Elas são definidas fora de qualquer função e podem ser usadas ao longo do programa. Variáveis globais podem ser acessadas e modificadas de qualquer parte do programa. No entanto, é importante usar variáveis globais com cautela, já que elas podem dificultar o entendimento e a manutenção do código.

**Minha definicao:** Variáveis globais podem ser criadas fora de uma função e acessadas e modificadas tanto dentro como fora de uma função, em qualquer parte do programa.

**Exemplo de variável global:**

```python
milk = 50 #Declarada como uma variável global

def omelet(cheese, eggs_number):
    result = 'A omelete está pronta! Ovos usados: ' + str(eggs_number)
    if cheese == True:
        result = result + ', com queijo'
    else:
        result = result + ', sem queijo'
    result = result + ' e leite (ml): ' + str(milk) #acessamos a variável global
    print(result)

omelet(True, 3)
```

```
A omelete está pronta! Ovos usados: 3, com queijo e leite (ml): 50
```

Este código mostra o uso de uma variável global em Python:

- A variável global `milk` é declarada fora da função
- A função `omelet` usa dois parâmetros e acessa `milk` diretamente
- A função cria uma descrição da omelete e é chamada com `omelet(True, 3)`

O exemplo demonstra como variáveis globais compartilham informações no código, mas seu uso deve ser cuidadoso.

### COMBINANDO VARIAVEL LOCAL E GLOBAL

```python
result = 'A omelete está pronta!' # Declarada como uma variável global

def omelet(cheese, eggs_number):
    result = 'A omelete está pronta! Ovos usados: ' + str(eggs_number)
    if cheese == True:
        result = result + ', com queijo'
    else:
        result = result + ', sem queijo'
    print(result)

omelet(True, 3)
print(result)
```

```
A omelete está pronta! Ovos usados: 3, com queijo
A omelete está pronta!
```

Neste exemplo, a função `omelet` define uma variável local `result` que tem prioridade sobre a variável global `result`. Quando `omelet` é chamada, ela exibe o valor da variável local `result`. A instrução `print` fora da função exibe o valor da variável global `result`.

# CAPITULO 3 ATIVIDADE PRATICA

## tarefa 1

Vamos começar escrevendo uma função chamada `filter_clients` para filtrar a lista de clientes por área de trabalho. A função vai receber dois parâmetros: `clients_list` (a lista de clientes) e `field` (o campo com a área de trabalho que a função precisa encontrar). A função vai iterar sobre cada cliente na lista, e se ela encontrar o cliente com a área de trabalho especificada na lista, a informação sobre o cliente será adicionada a uma nova lista. Essa lista será retornada como resultado da execução da função quando ela finalizar sua execução.

Chame a função para a área `"Transportation"`, para fazer um teste. Em seguida, imprima a lista filtrada (já no pré-código).

```python
clients = [
    [32456, "Jack Wilson", 32, 150000, "Healthcare"],
    [34591, "Nina Brown", 45, 250000, "Telecom"],
    [37512, "Alex Smith", 39, 210000, "IT"],
    [39591, "Brian Perez", 29, 340000, "Transportation"],
    [45123, "Sarah Lee", 28, 120000, "Marketing"],
    [47635, "David Kim", 36, 180000, "Finance"],
    [49571, "Samantha Chen", 42, 220000, "Retail"],
    [50391, "Juan Rodriguez", 31, 160000, "Architecture"],
    [34556, "Lucas Hernandez", 37, 75000, "Education"],
    [64291, "Jessica Li", 25, 125000, "IT"],
    [74512, "Emma Davis", 47, 197000, "Finance"],
    [83191, "Sophia Perez", 34, 225000, "Transportation"],
    [91023, "Liam Kim", 29, 98000, "Retail"],
    [96435, "Ava Chen", 31, 175000, "Marketing"],
    [100571, "Noah Rodriguez", 28, 85000, "Architecture"],
    [101321, "Olivia Wilson", 44, 310000, "Telecom"],
    [104556, "William Brown", 38, 289000, "Finance"],
    [105491, "Emily Smith", 29, 193000, "Healthcare"],
    [107512, "Michael Perez", 53, 415000, "Transportation"]
]

# escreva a sua função filter_clients aqui
def filter_clients(clients_list, field):
    result = []
    for client in clients_list:
        if field in client[4]:
            result.append(client)
    return result

filtered_list = filter_clients(clients, "Transportation")

# imprime o resultado
print(filtered_list)
```

```
[[39591, 'Brian Perez', 29, 340000, 'Transportation'], [83191, 'Sophia Perez', 34, 225000, 'Transportation'], [107512, 'Michael Perez', 53, 415000, 'Transportation']]

```

## tarefa 2

Vamos torná-la ainda mais flexível! Escreva mais duas funções similares à anterior que chamamos:

- `filter_age()` e
- `filter_income()`

Na primeira função, usaremos a idade como o filtro, enquanto na segunda, vamos usar a renda como o filtro.

A lista `clients` deve ser usada como argumento para o parâmetro `clients_list` em ambas as funções, de forma parecida ao que você fez na tarefa anterior.

Ambas as funções devem filtrar os clientes com valores maiores do que o valor passado como um argumento na chamada da função.

Chame a função `filter_age()` e filtre a lista `clients`, extraindo os clientes que tenham mais de 40 anos. Armazene os resultados na variável `filtered_age`.

Da mesma forma, chame a função `filter_income()` e filtre a lista `clients`, extraindo apenas os clientes que tenham uma renda maior que 250.000. Salve os resultados na variável `filtered_income`.

Imprima as variáveis `filtered_age` e `filtered_income` (que já estão no pré-código).

```python
clients = [
    [32456, "Jack Wilson", 32, 150000, "Healthcare"],
    [34591, "Nina Brown", 45, 250000, "Telecom"],
    [37512, "Alex Smith", 39, 210000, "IT"],
    [39591, "Brian Perez", 29, 340000, "Transportation"],
    [45123, "Sarah Lee", 28, 120000, "Marketing"],
    [47635, "David Kim", 36, 180000, "Finance"],
    [49571, "Samantha Chen", 42, 220000, "Retail"],
    [50391, "Juan Rodriguez", 31, 160000, "Architecture"],
    [34556, "Lucas Hernandez", 37, 75000, "Education"],
    [64291, "Jessica Li", 25, 125000, "IT"],
    [74512, "Emma Davis", 47, 197000, "Finance"],
    [83191, "Sophia Perez", 34, 225000, "Transportation"],
    [91023, "Liam Kim", 29, 98000, "Retail"],
    [96435, "Ava Chen", 31, 175000, "Marketing"],
    [100571, "Noah Rodriguez", 28, 85000, "Architecture"],
    [101321, "Olivia Wilson", 44, 310000, "Telecom"],
    [104556, "William Brown", 38, 289000, "Finance"],
    [105491, "Emily Smith", 29, 193000, "Healthcare"],
    [107512, "Michael Perez", 53, 415000, "Transportation"]
]

def filter_age(age, clients_list):
    result = []
    for client in clients_list:
        if age < client[2]:
            result.append(client)
    return result

def filter_income(income, clients_list):
    result = []
    for client in clients_list:
        if income < client[3]:
            result.append(client)
    return result

# chame as funções melhoradas
filtered_age = filter_age(40, clients)
filtered_income = filter_income(250000, clients)

# imprime o resultado
print(filtered_age)
print(filtered_income)
```

```
[[34591, 'Nina Brown', 45, 250000, 'Telecom'], [49571, 'Samantha Chen', 42, 220000, 'Retail'], [74512, 'Emma Davis', 47, 197000, 'Finance'], [101321, 'Olivia Wilson', 44, 310000, 'Telecom'], [107512, 'Michael Perez', 53, 415000, 'Transportation']]
[[39591, 'Brian Perez', 29, 340000, 'Transportation'], [101321, 'Olivia Wilson', 44, 310000, 'Telecom'], [104556, 'William Brown', 38, 289000, 'Finance'], [107512, 'Michael Perez', 53, 415000, 'Transportation']]
```






# References







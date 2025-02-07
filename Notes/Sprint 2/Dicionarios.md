
2024-10-07 21:45

Sprint: [[Sprint2]]

Topic: #basics 


# Dictionaries
## **Dicionários:**

Dicionários são uma ferramenta muito útil na programação que nos permite armazenar e acessar de forma que possamos acessar facilmente quando quiser.

Um dicionário é bem semelhante a uma lista, no entanto, em um dicionário cada elemento é um par chave-valor, em que serve como um identificador único para um valor específico.

Listas são úteis para armazenar itens em uma ordem particular, enquanto dicionários são convenientes para descrever propriedades individuais de objetos.

## **Sintaxe dos dicionários:**

**Os elementos de um dicionário são indicados entre chaves. Dentro delas, você pode definir seus pares chave-valor separando cada chave de seu valor respectivo por dois pontos.**

Cada entrada de um dicionário Python consiste em duas partes: uma chave e um valor.

- **Chave** — uma string ou número que identifica o valor
- **Valor** — os dados associados à chave

Exemplo:

```python
schedule = {                    
    'SU2222': '12.06.18 12:30', # a chave fica à esquerda dos dois pontos,
    'SU1111': '12.06.18 14:05',    # o valor fica à direita
    'SU0777': '12.06.18 17:00' 
}
```

As três regras básicas da sintaxe dos dicionários são:

- Elementos de dicionários são colocados entre chaves – `{}`.
- Os itens em um dicionário (pares chave-valor) são separados por vírgulas.
- Uma chave e um valor em um par são separados por dois pontos

Exemplo:

```python
schedule = {                    
    'SU2222': '12.06.18 12:30', # a chave fica à esquerda dos dois pontos,
    'SU1111': '12.06.18 14:05',    # o valor fica à direita
    'SU0777': '12.06.18 17:00' 
}
print(schedule)
```

```
{'SU2222': '12.06.18 12:30', 'SU1111': '12.06.18 14:05', 'SU0777': '12.06.18 17:00'}
```

![Image (13).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/e4f64ce6-44f9-461d-ade7-21b3c1d64995/b5ccbf41-4f3c-4854-8cfd-58915a57775b/Image_(13).png)

Outras diferenças entre listas e dicionários:

- A obtenção de dados em um dicionário é mais rápida, mas um dicionário ocupa mais espaço na memória.
- Assim como listas, dicionários podem armazenar dados de qualquer tipo, mas as chaves só podem ser dados de tipos imutáveis, tais como strings e números (inteiros e de ponto flutuante).
## Como extrair valores de dicionários

Há duas maneiras de acessar um valor: usando a chave diretamente e usando o método `get()`

## **Uso da chave:**

Você pode especificar uma chave do dicionário entre colchetes para extrair um valor para ela.

Exemplo:

```python
financial_info = {
    'American Express': 93.23,
    'Boeing': 178.44,
    'Coca-Cola': 45.15,
    'Nike': 97.99,
    'JPMorgan':96.27,
    'Walmart': 130.68 
}

# acessando o valor da chave 'Coca-Cola' do dicionário
coca_cola_price = financial_info['Coca-Cola']
print(coca_cola_price)
```

```
45.15
```

## **Como usar `get()`:**
O método `get()` recebe a chave como argumento. Se a chave está presente no dicionário, `get()` retorna o valor correspondente. Caso contrário, ele retorna o valor padrão, que é `None`.

Exemplo:
```python
financial_info = {
    'American Express': 93.23,
    'Boeing': 178.44,
    'Coca-Cola': 45.15,
    'Nike': 97.99,
    'JPMorgan':96.27,
    'Walmart': 130.68 
}

# encontrar o valor da chave 'Pepsi':
pepsi_price = financial_info.get('Pepsi')
# encontrar o valor da chave 'Nike':
nike_price = financial_info.get('Nike')

print(pepsi_price)
print(nike_price)
```

```
None
97.99
```
O valor `none` é especial porque seu tipo é. Ele não é uma string, então é escrito sem aspas, assim como os valores e . Normalmente, indica a ausência de um valor. será útil mais tarde, quando precisarmos ver se uma chave está no dicionário. Podemos verificar se o método retorna usando a condição , da seguinte maneira: tem seu próprio tipo (), e o método retorna-o por padrão quando a chave não pode ser encontrada.

==Se você não gosta de , pode definir qualquer outro valor. O método também permite definir outro valor padrão. Basta passá-lo como o segundo argumento do método, e se a chave não for encontrada, o valor especificado será retornado.==

Exemplo:

```python
# Agora o método retorna -1 se a chave não estiver inserida no dicionário:
pepsi_price = financial_info.get('Pepsi', -1)
nike_price = financial_info.get('Nike', -1)
print(pepsi_price)
print(nike_price)
```

```
-1
97.99
```

`-1` é retornado para `'Pepsi'`, e `'Nike'` continua a retornar `97.99`, já que `'Nike'` está presente no dicionário.










**2025-02-20 15:08**

**Sprint:** [[Sprint7]]

**Topic:** #extraindo-dados-online 

**Connections:** [[Análise sintática de HTML]]

---
# **Criando DataFrame Com WebScrapping e BeautifulSoup**

 1. Faça um objeto BeautifulSoup a partir da página HTML. Salve seus resultados na variável `soup`.

```python
import requests # Importe a biblioteca de requisições enviadas ao servidor
from bs4 import BeautifulSoup # Importe a biblioteca para análise sintática da página web

URL = 'https://tripleten-com.github.io/simple-shop_pt-br/'
req = requests.get(URL)  # Requisição GET
soup = BeautifulSoup(req.text, 'lxml')
```

 2. Obtenha os nomes de produtos [Site de Produtos](https://tripleten-com.github.io/simple-shop_pt-br/) e adicione-os à lista `name_products`. Identifique os nomes das tags e seus atributos na barra de ferramentas do desenvolvedor. Obtenha as tags necessárias usando `find_all()`. imprima a lista resultante.

```python
name_products = []

# Encontra todas as divs com a classe especificada
products = soup.find_all('p', class_='t754__title t-name t-name_md js-product-name')

# Extrai o texto de cada elemento e adiciona à lista
for product in products:
    name_products.append(product.text)

print(name_products)
```

2. Obtenha os preços dos produtos de [Site de Produtos](https://tripleten-com.github.io/simple-shop_pt-br/) e adicione-os à lista `price`. Identifique os nomes das tags e seus atributos na barra de ferramentas do desenvolvedor. Obtenha as tags necessárias usando `find_all()`.Imprima a lista resultante.

```python
price = []  # A lista onde os preços dos produtos estão armazenados
for row in soup.find_all(
    'p', attrs={'class': 't754__price-value js-product-price'}
):

    price.append(row.text)
# crie um ciclo que vai percorrer todos os elementos <p> onde o valor do atributo da classe é 't754__price-value js-product-price'

print(price)
```

4. Adicione dados a um DataFrame vazio. Crie as colunas `'name'` e `'price'` e preencha-as com os dados das listas `name_products` e `price`. Imprima as primeiras 5 linhas do dataframe. As colunas devem aparecer nesta ordem: `name`, `price`.

```python
# Criar o DataFrame com as colunas na ordem especificada
products_data = pd.DataFrame({
    'name': name_products,
    'price': price
})

# Imprimir as primeiras 5 linhas
print(products_data.head())
```

### - CODIGO INTEIRO

```python
import pandas as pd
import requests # Importe a biblioteca de requisições enviadas ao servidor
from bs4 import BeautifulSoup # Importe a biblioteca para análise sintática da página web
URL = 'https://tripleten-com.github.io/simple-shop_pt-br/'
req = requests.get(URL)  # Requisição GET
soup = BeautifulSoup(req.text, 'lxml')

name_products = []  # A lista onde os nomes dos produtos estão armazenados
for row in soup.find_all(
    'p', attrs={'class': 't754__title t-name t-name_md js-product-name'}
):
    name_products.append(row.text)
price = []  # A lista onde os nomes dos produtos estão armazenados
for row in soup.find_all(
    'p', attrs={'class': 't754__price-value js-product-price'}
):
    price.append(row.text)
# Criar o DataFrame com as colunas na ordem especificada
products_data = pd.DataFrame({
    'name': name_products,
    'price': price
})

# Imprimir as primeiras 5 linhas
print(products_data.head())
```
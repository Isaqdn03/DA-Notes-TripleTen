
**2024-10-10 19:28**

**Sprint:** [[Sprint3]]

**Topic:** #tratamento-ausente-duplicados 

**Connections:** [[Processamento de valores duplicados#**Procurando por casos óbvios**]]

# **Como lidar com duplicados**
### Main Topics of this Lesson:
1. Revisão: encontrar dados duplicados
2. Como lidar com duplicados


## **1. Revisão: encontrar dados duplicados**

Usando o metodo `duplicate()` com `sum` obtemos valores duplicados em uma unica coluna ou linhas duplicadas em DF

#### **Tecnica 1:**
```python
import pandas as pd

df = pd.DataFrame({'col_1': ['A', 'B', 'A', 'A'], 'col_2': [1, 2, 2, 1]})


print('É assim que fica o conjunto de dados:')

print(df)

print('É assim que fica um objeto Séries booleano:')

print(df.duplicated())

print('É assim que fica um resultado do método duplicated() seguido por sum():')

print(df.duplicated().sum())

```

```
É assim que fica o conjunto de dados:

    col_1  col_2

0     A      1

1     B      2

2     A      2

3     A      1

É assim que fica um objeto Séries booleano:

0    False

1    False

2    False

3     True

dtype: bool

É assim que fica um resultado do método duplicated() seguido por sum(): 1
```

Entao para obter o numero de duplicadas use `duplicate()` seguida e de `sum()`

podemos tambem verificar duplicadas usando filtragem simples

```python
import pandas as pd

df = pd.DataFrame({'col_1': ['A', 'B', 'A', 'A'], 'col_2': [1, 2, 2, 1]})

print(df[df.duplicated()])

```

```
    col_1  col_2

 3     A      1
```


#### **Tecnica 2:**
metodo `value_counts()`  identifica valores univocos em uma coluna, e calcula quantas vezes cada um aparece

```python
print(df['col_1'].value_counts())
```

```
A    3
B    1
Name: col_1, dtype: int64
```

Letra `A` aparece 3
Letra `B` aparece 1


## **2. Como lidar com duplicados**

podemos usar `drop_duplicates()` para lidar com valros duplicados 

```python
import pandas as pd

df = pd.DataFrame({'col_1': ['A', 'B', 'A', 'A'], 'col_2': [1, 2, 2, 1]})

print('Conjunto de dados original:')

print(df)

print()

print('Conjunto de dados após a remoção dos duplicados:')

print(df.drop_duplicates())

```

```
Original dataset:

  col_1  col_2

0     A      1

1     B      2

2     A      2

3     A      1

Conjunto de dados após a remoção dos duplicados:

  col_1  col_2

0     A      1

1     B      2

2     A      2
```

### **`subset=`**
para considerar duplicados em uma ou algumas colunas em vez de linhas totalmentes duplicadas, use paramtetro `subset=` 

```python
print(df.drop_duplicates(subset='col_1'))
```

```python
  col_1  col_2
0     A      1
1     B      2
```

### **`.str`** 
```python
print(df['col_1'].str.lower())
```

nos permite aplicar metodos de strings diretamente a coluna, nos permitindo aplicar o metodo `lower()`, para colocar todos os valores desta coluna em minusculo 

em vez de somente imprimir, podemos mudar a coluna e atualizar ela de acordo com as necessidades, neste caso em minusculo.

```python
df['col_1'] = df['col_1'].str.lower() 
print(df)
```

```
    col_1  col_2
0     a      1
1     b      2
2     a      2
3     a      1
```

verificando o numero de duplicados verdadeiros na coluna `col_1`

```python
df['col_1'] = df['col_1'].str.lower()
print(df['col_1'].duplicated().sum())
```

```
2
```

caso queros mudar as letras para minusculo ou maiusculo em apenas uma parte da sting use `replace()` 

```python
stock['item'] = stock['item'].str.replace('GB', 'gb') 
print(stock.head())
```

```
                    id                     item  count

0  100480924     Apple iPhone Xr 64gb     10
1  100480924     Apple iPhone Xr 64gb     19
2  100480959     Xiaomi Redmi 6A 16gb     44
3  100480975          HUAWEI P30 lite     38
4  100480988  Samsung Galaxy A30 32gb     49
```


### **Modificando strings em uma coluna adicional**
se tivermos duvidas de qual abordagem usar, podemos manter a coluna original e criar coluna adicional onde strings seram modificadas


```python
stock['item_modified'] = stock['item'].str.replace('GB', 'gb')

print(stock.head())
```

```
                    id                     item  count            item_modified

0  100480924     Apple iPhone Xr 64gb     10     Apple iPhone Xr 64gb

1  100480924     Apple iPhone Xr 64gb     19     Apple iPhone Xr 64gb

2  100480959     Xiaomi Redmi 6A 16gb     44     Xiaomi Redmi 6A 16gb

3  100480975          HUAWEI P30 lite     38          HUAWEI P30 lite

4  100480988  Samsung Galaxy A30 32gb     49  Samsung Galaxy A30 32gb
```

você pode salvar o resultado da substituição feita na coluna `'item'` em uma nova coluna chamada `'item_modified'`:
### **Tarefa**
1. **Importação e leitura dos dados**:python
    
    `import pandas as pd df_stock = pd.read_csv('/datasets/phone_stock.csv')`
    O arquivo CSV 'phone_stock.csv' é lido e carregado em um DataFrame chamado `df_stock`.
2. **Criação de uma nova coluna**:python
    
    `df_stock['item_lowercase'] = df_stock['item'].str.lower()`
    Uma nova coluna 'item_lowercase' é criada, contendo os nomes dos itens em letras minúsculas.
3. **Cálculo das somas para modelos específicos**:python
    
    `apple = df_stock[df_stock['item_lowercase'] == 'apple iphone xr 64gb']['count'].sum() samsung = df_stock[df_stock['item_lowercase'] == 'samsung galaxy a30 32gb']['count'].sum()`
    O código calcula a soma dos estoques para o iPhone XR 64GB da Apple e o Galaxy A30 32GB da Samsung.
4. **Remoção de duplicatas**:python
    
    `df_stock = df_stock.drop_duplicates(subset='item_lowercase').reset_index(drop=True)`
    As duplicatas são removidas com base na coluna 'item_lowercase', e o índice é redefinido.
5. **Atualização dos valores de estoque**:python
    
    `df_stock.loc[0, 'count'] = apple df_stock.loc[3, 'count'] = samsung`
    Os valores de estoque calculados anteriormente são atualizados no DataFrame para os modelos Apple e Samsung.
6. **Exibição do resultado**:python
    
    `print(df_stock)`
    O DataFrame final é exibido, mostrando os dados de estoque atualizados com as duplicatas removidas.


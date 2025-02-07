
2024-10-07 22:37

Sprint: [[Sprint2]]

Topic: #dataframe-prepocess 


# Processamento de valores duplicados

# 5.5 **Processamento de valores duplicados**

## **Procurando por casos óbvios**

O método `duplicated()` em pandas é usado para identificar linhas duplicadas em um DataFrame. Aqui estão os principais pontos sobre este método:

- **Funcionamento básico:** Retorna uma Series booleana indicando se cada linha é uma .
- **Uso comum:** Frequentemente usado em conjunto com outros métodos, como `drop_duplicates()` para remover linhas duplicadas.
- **Exemplo de uso:**

```python
import pandas as pd
df = pd.read_csv('/datasets/music_log_raw.csv')

print(df.duplicated().sum())
```

O método `duplicated()` é uma ferramenta valiosa para identificar e lidar com dados duplicados, ajudando a manter a integridade e a qualidade dos dados em análises e processamentos subsequentes.

## Removendo duplicadas

Usando o metodo drop_duplicates() somos capaz de fazer isso com facilidade

```python
df = df.drop_duplicates()

print(df.duplicated().sum())

#0
```

podemos usar inplace=True para nao precisar reatribuir a variavel que armazena o DataFrame:

```python
df.drop_duplicates(inplace=True)

print(df.duplicated().sum())

#0
```

se checarmos o dataframe novamente vamos notar algo que pode nos atrapalhar na continucao do processamento desses dados, vale a pena notar que em DataFrames, ao contrário das listas em Python, os índices permanecem os mesmos quando as linhas são removidas:

```python
print(df.head())
```

```
        user_id          total play                                  Artist      genre              track_name
0  BF6EA5AF           92.851388                              Marina Rei        pop                  Musica
1  FB1E568E          282.981000                            Stive Morgan    ambient             Love Planet
3  EF15C7BA            8.966000                                     NaN      dance     Loving Every Minute
4  82F52E69          193.776327                                  Rixton        pop  Me And My Broken Heart
5  4166D680            3.007000  Henry Hall & His Gleneagles Hotel Band       jazz                    Home
```

as linhas duplicadas sumiram mas os indices nao mudaram

E importante atualizar os indices quando removemos linhas, para isso chamamos o metodo `reset_index()`

1. os indices antigos seram armazenados em um nova coluna chamada index
2. novos indices seram definidos em ordem para todas as linhas no DataFrame

```python
df = df.drop_duplicates().reset_index()

print(df.head())
```

```
     index   user_id  total play                                  Artist   
0      0  BF6EA5AF   92.851388                              Marina Rei  \\
1      1  FB1E568E  282.981000                            Stive Morgan   
2      3  EF15C7BA    8.966000                                 no_info   
3      4  82F52E69  193.776327                                  Rixton   
4      5  4166D680    3.007000  Henry Hall & His Gleneagles Hotel Band   

     genre                   track  
0      pop                  Musica  
1  ambient             Love Planet  
2    dance     Loving Every Minute  
3      pop  Me And My Broken Heart  
4     jazz                    Home
```

geralmente nao desejamos esta nova coluna index, para remover ela do nosso DataFrame basta definir o parametro `drop=True`

```python
df = df.drop_duplicates().reset_index(drop=True)
```

```
     user_id   total play                                  Artist    genre   
0  BF6EA5AF   92.851388                              Marina Rei      pop  \\
1  FB1E568E  282.981000                            Stive Morgan  ambient   
2  EF15C7BA    8.966000                                     NaN    dance   
3  82F52E69  193.776327                                  Rixton      pop   
4  4166D680    3.007000  Henry Hall & His Gleneagles Hotel Band     jazz   

                    track  
0                  Musica  
1             Love Planet  
2     Loving Every Minute  
3  Me And My Broken Heart  
4                    Home
```

- Chamamos o método `drop_duplicates()` e obtemos um DataFrame sem duplicados, mas com índices quebrados.
    
- Em seguida, usamos o método `reset_index()` para redefinir os índices de linha e descartar a coluna `'index'`
    
    ![https://practicum-content.s3.amazonaws.com/resources/12.5_2PT_1690266350.png](https://practicum-content.s3.amazonaws.com/resources/12.5_2PT_1690266350.png)
    

## **Procurando por valores implícitos duplicados**

### 1. Identificar Valores Únicos

Para encontrar todos os valores únicos em uma coluna, podemos usar o método `unique()`. Este método é útil para identificar variações de um valor esperado.

**Exemplo:**

```python
import pandas as pd

# Criando um DataFrame de exemplo
rating = ['date', 'name', 'points']
players = [
    ['2018.01.01', 'Rafael Nadal', 10645],
    ['2018.01.08', 'Rafael Nadal', 10600],
    ['2018.03.19', 'Roger Federerr', 9660],
    ['2018.06.18', 'Roger Fedrer', 8920],
    ['2018.11.05', 'Novak Djokovic', 8045]
]
tennis = pd.DataFrame(data=players, columns=rating)

# Visualizando os valores únicos na coluna 'name'
print(tennis['name'].unique())
```

**Resultado:**

```css
['Rafael Nadal' 'Roger Federerr' 'Roger Fedrer' 'Novak Djokovic']
```

Percebemos que o nome "Roger Federer" foi escrito de três maneiras diferentes.

Para saber quantos valores únicos existem na coluna, podemos usar `nunique()`:

```python

print(tennis['name'].nunique())
```

**Resultado:**

```
4
```

Aqui, temos quatro valores únicos, sendo que dois deles são variantes incorretas.

### 2. Corrigir Duplicados Implícitos Usando `replace()`

Para remover esses duplicados implícitos, podemos usar o método `replace()`. Isso nos permite substituir valores incorretos por um valor padrão correto.

**Exemplo:**

```python
# Substituindo valores incorretos por 'Roger Federer'
tennis['name'] = tennis['name'].replace('Roger Federerr', 'Roger Federer')
tennis['name'] = tennis['name'].replace('Roger Fedrer', 'Roger Federer')
tennis['name'] = tennis['name'].replace('Rafael Nadal', 'Rafael Nadal Parera')

print(tennis)
```

**Resultado:**

```yaml
yaml
Copy code
         date                name  points
0  2018.01.01  Rafael Nadal Parera   10645
1  2018.01.08  Rafael Nadal Parera   10600
2  2018.03.19        Roger Federer    9660
3  2018.06.18        Roger Federer    8920
4  2018.11.05       Novak Djokovic    8045

```

Nesse exemplo, corrigimos as variações dos nomes incorretos de "Roger Federer" e também padronizamos "Rafael Nadal" para "Rafael Nadal Parera".

Para tornar o código mais conciso, podemos utilizar `inplace=True`:

```python
python
Copy code
# Usando inplace para modificar o DataFrame sem precisar reatribuir
tennis['name'].replace('Roger Federerr', 'Roger Federer', inplace=True)
tennis['name'].replace('Roger Fedrer', 'Roger Federer', inplace=True)
tennis['name'].replace('Rafael Nadal', 'Rafael Nadal Parera', inplace=True)

print(tennis)

```

### 3. Automatizando com Funções

Podemos automatizar o processo de substituição criando uma função personalizada. Isso ajuda a reduzir a repetição de código quando temos muitos valores a serem substituídos.

**Exemplo:**

```python
python
Copy code
# Função para substituir valores incorretos por um valor correto
def replace_wrong_values(df, column, wrong_values, correct_value):
    for wrong_value in wrong_values:
        df[column] = df[column].replace(wrong_value, correct_value)
    return df

# Lista de nomes incorretos
duplicates = ['Roger Federerr', 'Roger Fedrer']
correct_name = 'Roger Federer'

# Chamando a função para substituir os valores incorretos
tennis = replace_wrong_values(tennis, 'name', duplicates, correct_name)
print(tennis)

```

**Resultado:**

```yaml
yaml
Copy code
         date                name  points
0  2018.01.01  Rafael Nadal Parera   10645
1  2018.01.08  Rafael Nadal Parera   10600
2  2018.03.19        Roger Federer    9660
3  2018.06.18        Roger Federer    8920
4  2018.11.05       Novak Djokovic    8045

```

Nesse exemplo, a função `replace_wrong_values` toma quatro parâmetros:

1. `df`: O DataFrame que desejamos modificar.
2. `column`: A coluna onde faremos a substituição.
3. `wrong_values`: Uma lista contendo os valores incorretos.
4. `correct_value`: O valor correto a ser utilizado.

Assim, a função percorre todos os valores incorretos da lista e os substitui pelo valor correto na coluna especificada. Isso facilita a padronização dos dados, especialmente quando temos várias variações incorretas que precisam ser corrigidas.

## Exemplo de procura de valores implicitos com variaveis

Chegou a hora de verificar o número de valores únicos na coluna `'Artist'`. Armazene os valores únicos na variável `pop_artists`. O número de artistas únicos deve ser posto na variável `n_artists`. Imprima ambas as variáveis.

```python
import pandas as pd

df = pd.read_csv('/datasets/music_log_raw.csv')

pop = df[df['genre'] == 'pop']

pop_artists = pop['Artist'].unique() # Escreva seu código aqui
n_artists = pop['Artist'].nunique()# Escreva seu código aqui

print(pop_artists)# Escreva seu código aqui)
print(n_artists)# Escreva seu código aqui)
```

```
['Marina Rei' 'Rixton' 'Andrew Paul Woodworth' ... 'Bierstrassen Cowboys'
 'Nadine Coyle' 'Less Chapell']
7533
```


# References







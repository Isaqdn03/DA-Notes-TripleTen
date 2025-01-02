
2024-10-10 11:52

Sprint:[[Sprint3]]

Topic: #tratamento-ausente-duplicados



# Contagem de valores ausente
### Main Topics of this Lesson:
1. como verificar se ha valores ausentes
2. Contagem de valores ausentes com `values_counts()`


## 1. Como verificar se ha valores ausentes

Uma otima maneira para comecar a verificacao de valores ausentes em um dataframe e usando o metodo `info()` 

o metodo `info()` imprime valores que nao estao ausentes em cada coluna
valores NULOS sao valores ausentes enquanto valores NAO NULOS sao valores nao ausentes, `info()` so considera valores nulos de verdade ou seja `None` e `NaN`

```python
import pandas as pd

df_logs = pd.read_csv('/datasets/visit_log.csv')

df_logs.info()
```

Resultado:
```python
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 200000 entries, 0 to 199999
Data columns (total 4 columns):
 #   Column    Non-Null Count   Dtype 
---  ------    --------------   ----- 
 0   user_id   200000 non-null  int64 
 1   source    198326 non-null  object
 2   email     13953 non-null   object
 3   purchase  200000 non-null  int64 
dtypes: int64(2), object(2)
memory usage: 6.1+ MB

```

podemos ver, que a valores ausentes em `source` e `email` pois tem menos 200.000 valores nao nulos

agora para descobrir a quantidade de valores nulos podemos usar `isna()` no dataframe

```python
import pandas as pd

df_logs = pd.read_csv('/datasets/visit_log.csv')

print(df_logs.isna().sum())
```

Resultado:
```python
user_id          0
source        1674
email       186047
purchase         0
dtype: int64
```

## 2. Contagem de valores ausentes com `value_counts()`

Em vez de somar os valores retornados por `isna()`, podemos contar valores ausentes e nao ausentes diretamente usando `value_counts()` que nos mostrar quantas vezes o valores unicos daquela coluna aparece nela, por padrao esse metodo exclui os valores ausentes (`None)` e `NaN`) a nao ser que configuremos `dropna=False`.

Exemplo: 
```python
import pandas as pd

df_logs = pd.read_csv('/datasets/visit_log.csv')

print(df_logs['source'].value_counts(dropna=False))
```

Resultado:
```python
other      133834
context     52032
email       12279
NaN          1674
undef         181
Name: source, dtype: int64
```

obtemos uma contagem de quantas vezes cada valor dessa coluna aparece, incluido os valores ausentes.

para contextualizar melhor, aqui esta as 20 primeiras linhas do DataFrame deste exemplo:

```python
       user_id   source       email  purchase
0   7141786820    other         NaN         0
1   5644686960    email  c129aa540a         0
2   1914055396  context         NaN         0
3   4099355752    other         NaN         0
4   6032477554  context         NaN         1
5   5872473344    other         NaN         0
6   7977025176    other         NaN         0
7   3512872755    other         NaN         0
8   1827368713  context         NaN         0
9   8688870165    other         NaN         0
10  7172802697    other         NaN         0
11  8623045648    email  d6d19c571c         0
12  2083224479  context         NaN         0
13  9819051388  context         NaN         0
14  9312844109    other         NaN         0
15  9396302801    other         NaN         0
16  6331906669    other         NaN         1
17  6840899645  context         NaN         0
18  5739438900    email  19379ee49c         0
19  7486955288    email  09c27794fa         0
```

como padrao o resultado e armazenado em ordem decrescente com base nos valores (numericos)
mas tambem podemos ordena-los em ordem alfabetica com base dos nomes dos valores usando o metodo `sort_index()`

```python
print(df_logs['source'].value_counts(dropna=False).sort_index())
```

### Recapitulação

Existem muitas formas de encontrar e contar valores ausentes na pandas. Você aprendeu três maneiras nesta lição:

- Chamando `info()` em um DataFrame
- Chamando `isna().sum()` em um DataFrame ou objeto Series
- Chamando `value_counts(dropna=False)` em um objeto Series




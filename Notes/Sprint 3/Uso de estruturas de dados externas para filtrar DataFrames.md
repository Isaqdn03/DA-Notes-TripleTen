
**2024-10-16 20:17**

**Sprint:** [[Sprint3]]

**Topic:** #Filtragem-de-Dados 

**Connections:** 

# **Uso de estruturas de dados externas para filtrar DataFrames**
### Main Topics of this Lesson:

1. Filtragem com um dicionário
2. Filtragem com um objeto Series
3. Filtragem com um DataFrame

## **1. Filtragem com um dicionário**

Para verificar a presença dos valores da coluna `'a'` entre os _valores_ do dicionário, precisamos usar o método `values()` do dicionário na consulta `"a in @our_dict.values()"`

```python
import pandas as pd

our_dict = {0: 10, 3: 11, 12: 12}
df = pd.DataFrame(
    {
        'a': [2, 3, 10, 11, 12],
        'b': [5, 4, 3, 2, 1],
        'c': ['X', 'Y', 'Y', 'Y', 'Z'],
    }
)
print(df)
print()
print(our_dict)
print()
print(df.query("a in @our_dict.values()"))
```

```
    a  b  c
0   2  5  X
1   3  4  Y
2  10  3  Y
3  11  2  Y
4  12  1  Z

{0: 10, 3: 11, 12: 12}

    a  b  c
2  10  3  Y
3  11  2  Y
4  12  1  Z
```

Cada um dos valores do dicionário (10, 11 e 12) aparece na coluna `'a'` apenas uma vez, então recebemos três linhas de `query()`.

==Agora se quisermos verificar a presencados valores de uma coluna entra as chaves de um dicionario (neste caso 0, 3 e 12) precisamos usar a consulta `"a in @our_dict.keys()"`. consulta mais curta `"a in @our_dict"` também funciona, porque verifica as chaves por padrão:==

```python
print(df.query("a in @our_dict"))
```

```
    a  b  c
1   3  4  Y
4  12  1  Z
```

## **2. Filtragem com um objeto Series**

A consulta `"a in @our_series"` verifica a presença de valores na coluna `'a'` entre os valores de `our_series` em vez de entre os índices.

```python
import pandas as pd

our_series = pd.Series([10, 11, 12])
df = pd.DataFrame(
    {
        'a': [2, 3, 10, 11, 12],
        'b': [5, 4, 3, 2, 1],
        'c': ['X', 'Y', 'Y', 'Y', 'Z'],
    }
)
print(df)
print()
print(our_series)
print()
print(df.query("a in @our_series"))

```

```
    a  b  c
0   2  5  X
1   3  4  Y
2  10  3  Y
3  11  2  Y
4  12  1  Z

0    10
1    11
2    12
dtype: int64

    a  b  c
2  10  3  Y
3  11  2  Y
4  12  1  Z
```

Se precisarmos verificar se os valores da coluna `'a'` estão presentes entre os valores de índice do Series, então teremos que usar o atributo `index`: `"a in @our_series.index"`.

## **3. Filtragem com um DataFrame**

podemos usar DataFrames externos para filtrar dados de duas maneiras
1. Filtrar usando seus valores de índice
2. Filtrar usando valores em colunas específicas

Vamos criar um DataFrame externo chamado `our_df` com valores de índice definidos pela lista `['Z', 'X', 'P']`. Podemos então verificar a inclusão dos valores da coluna `'c'` nos índices de `our_df`:

```python
import pandas as pd

df = pd.DataFrame(
    {
        'a': [2, 3, 10, 11, 12],
        'b': [5, 4, 3, 2, 1],
        'c': ['X', 'Y', 'Y', 'Y', 'Z'],
    }
)
our_df = pd.DataFrame(
    {
        'a1': [2, 4, 6],
        'b1': [3, 2, 2],
        'c1': ['A', 'B', 'C'],
    },
    index=['Z', 'X', 'P']
)

print(df)
print()
print(our_df)
print()
print(df.query("c in @our_df.index"))
```

```
    a  b  c
0   2  5  X
1   3  4  Y
2  10  3  Y
3  11  2  Y
4  12  1  Z

   a1  b1 c1
Z   2   3  A
X   4   2  B
P   6   2  C

    a  b  c
0   2  5  X
4  12  1  Z
```

Para verificar se os valores de uma coluna do DataFrame que queremos filtrar (neste caso, `df`) também estão presentes em uma coluna de um DataFrame externo (`our_df`), também precisamos especificar a coluna externa na consulta usando a **notação de ponto.**

A consulta `"a in @our_df.a1"` verifica se algum valor da coluna `'a'` de `df` está presente na coluna `'a1'` de `our_df`.
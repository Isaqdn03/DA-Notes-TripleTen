
**2024-10-14 18:26**

**Sprint:** [[Sprint3]]

**Topic:** #Filtragem-de-Dados

**Connections:** 

# **Indices em DataFrames e Series**
### Main Topics of this Lesson:

1. O Atributo `index`
2. Indexação usando `loc[]`
3. Indexacao usando `iloc[] `
4. Alteração do índice de um DataFrame usando o método `set_index()`


## **1. O Atributo `index`**

Objetos Series e Data Frames tem indices armazenados no atributo `index` , toda vez que algum deles e criado o atibuto `index` e criado automaticamente com valores padores, claro se eles nao for especificado antes da criacao

como criar um objeto Series:

```python
import pandas as pd

oceans = pd.Series(['Pacific', 'Atlantic', 'Indian', 'Southern', 'Arctic'])

print(oceans)

```

```python
0     Pacific
1    Atlantic
2      Indian
3    Southern
4      Arctic
dtype: object
```

usamos classe `Series()` da `pandas` para criar um objeto Series armazenando na variavel `oceans` 

- **Na impressao encontramos 3 componetes :**
	1. Os valores do Series à direita (nomes dos oceanos)
	2. Os valores de índice à esquerda (números inteiros de 0 a 4)
	3. O tipo de dados da pandas dos elementos do objeto Series na parte inferior (`dtype: object`)


==como um indice nao foi especificado temos um indice padrao de numeros inteiros que comeca com 0==

--- 

```python
import pandas as pd

oceans = pd.Series(['Pacific', 'Atlantic', 'Indian', 'Southern', 'Arctic'])

print(oceans.index)
print(type(oceans.index))
```

```
RangeIndex(start=0, stop=5, step=1)
<class 'pandas.core.indexes.range.RangeIndex'>
```

O indice e do tipo `RangeIndex`, Este e o indice padrao em DataFrames e Series mas nao e unico usado.

- O tipo `RangeIndex` tem três parâmetros: `start=`, `stop=` e `step=`.
	- `start=` é o primeiro índice de um objeto Series ou um DataFrame.
	- `stop=` é o último índice. Como você pode ver, ele não está incluído em um objeto Series ou DataFrame.
	- `step=` é o passo dado ao mover do primeiro índice ao último. Por padrão, é `1`

Como opcao podemos definir indices como quisermos, para isso vamos atibuir uma lista de numero(nesse caso numero) ao atributo `index` do nome do Objeto Series

```python
import pandas as pd

oceans = pd.Series(['Pacific', 'Atlantic', 'Indian', 'Southern', 'Arctic'])

oceans.index = [1, 2, 3, 4, 5]

print(oceans.index)
print(type(oceans.index))
```

```
Int64Index([1, 2, 3, 4, 5], dtype='int64')
<class 'pandas.core.indexes.numeric.Int64Index'>
```

E possivel tambem o que queremos como indices no atributo `index` direto na chamada de Series, o que epreferivel quando nao queremos o indice padrao e nao planejamos modificar os indices mais tarde

```python
import pandas as pd

oceans = pd.Series(['Pacific', 'Atlantic', 'Indian', 'Southern', 'Arctic'],
                   index=[1, 2, 3, 4, 5])

print(oceans.index)
print(type(oceans.index))
```

```
Int64Index([1, 2, 3, 4, 5], dtype='int64')
<class 'pandas.core.indexes.numeric.Int64Index'>
```

---

Se definirmos os valores de indices como strings obtemos um tipos de dados geral como `index` 

```python
index=['A', 'B', 'C', 'D', 'E']
```

```
Index(['A', 'B', 'C', 'D', 'E'], dtype='object') 
<class 'pandas.core.indexes.base.Index'>
```

---

## **2. Indexação usando `loc[]`**

- ==**Indice**: e um componente de DataFrame ou objeto Series que pode ser acessado usando o atributo `index`==
- ==**Indexacao:** e o precesso de acessar valores de um DataFrame ou objeto Series usando os respectivos indices==

**Breve revisao do atributo `loc[]` [[Filtragem com indexação lógica]]

podemos acessar elementos do DataFrame com `loc[]` passando valores de índice e nomes de colunas, como `df.loc[index_value, col_name]`.

```python
import pandas as pd

states  = ['Alabama', 'Alaska', 'Arizona', 'Arkansas']
flowers = ['Camellia', 'Forget-me-not', 'Saguaro cactus blossom', 'Apple blossom']
insects = ['Monarch butterfly', 'Four-spotted skimmer dragonfly', 'Two-tailed swallowtail', 'European honey bee']
index   = ['state 1', 'state 2', 'state 3', 'state 4']

df = pd.DataFrame({'state': states, 'flower': flowers, 'insect': insects}, index=index)

print(df.loc['state 4', 'insect'])
```

```
European honey bee
```

---

Também podemos usar `loc[]` para obter vários elementos como um objeto Series ou outro DataFrame. Basta passar para `loc[]` uma lista de indices e uma lista de coluna:

```python
df.loc[[index_value_1, index_value_1], [col_name_1, col_name_2]]
```

Exemplo em uso (com o dataframe mencionado acima):

```python
filtered_df = df.loc[['state 1', 'state 3'], ['flower', 'insect']]

print(filtered_df)
```

```
                         flower                  insect
state 1                Camellia       Monarch butterfly
state 3  Saguaro cactus blossom  Two-tailed swallowtail
```

---

**indexação** para obter um intervalo de índices para uma única coluna
- apenas especificar o primeiro e o último índice separados por um caractere `:`

```python
print(df.loc['state 1': 'state 3', 'flower'])
```

```
state 1                  Camellia
state 2             Forget-me-not
state 3    Saguaro cactus blossom
Name: flower, dtype: object
```

obtivemos os valores na coluna `'flower'` dos três primeiros estados selecionados indexando `'state 1': 'state 3'`

De forma parecida, você pode selecionar várias colunas, bem como vários índices:

```python
print(df.loc['state 1': 'state 3', 'flower': 'insect'])
```

retorna uma tabela filtrada com valores das colunas de `'flower'` até `'insect'`, para o intervalo dos índices de `'state 1'` até e incluindo `'state 3'`.

---

![[Pasted image 20241014215951.png]]

## **3. Indexacao usando `iloc[] `**

`iloc[]` usamos numeros inteiros para indexar as posicoes dos elementos que desejamos obter

```python
print(df.iloc[3, 2])
```

aqui selecionamos a linha 4 e a coluna 3 do dataframe,`iloc[]` usa a indexação normal de Python a partir de 0

podemos acessar várias linhas e/ou colunas com `iloc[]` 

```python
print(df.iloc[[0, 2], 1:])
```

```python
                         flower                  insect
state 1                Camellia       Monarch butterfly
state 3  Saguaro cactus blossom  Two-tailed swallowtail
```

o codigo seleciona a primeira linha com o indice python `0`, e a `3` linha com o indice python `2` , e as colunas seleciona todas apartir da segunda coluna com o indice python `1` 

## **4. Alteração do índice de um DataFrame usando o método `set_index()`**

Para DataFrames, existe outra forma de definir valores de índice usando o método `set_index()`

```PYTHON
df = pd.DataFrame({'state': states, 'flower': flowers, 'insect': insects}, index=index)

df = df.set_index('state') # substitui o índice

print(df)
print()
print(df.index)
```

```
state                                                           
Alabama                 Camellia               Monarch butterfly
Alaska             Forget-me-not  Four-spotted skimmer dragonfly
Arizona   Saguaro cactus blossom          Two-tailed swallowtail
Arkansas           Apple blossom              European honey bee

Index(['Alabama', 'Alaska', 'Arizona', 'Arkansas'], dtype='object', name='state')
```

indices eram os números dos estados: `'state 1'`, `'state 2'` etc. Depois, nós os substituímos pelos valores da coluna `'state'`

Agora os indices tem um novo componete de nome(os indices esta nomeado como `state` )

Se você não quiser que o índice tenha um nome, pode removê-lo definindo o atributo `index_name` de um DataFrame como `None`

```python
df = pd.DataFrame({'state': states, 'flower': flowers, 'insect': insects}, index=index)
df = df.set_index('state')

df.index.name = None
print(df)
print()
print(df.index)
```

```
                          flower                          insect
Alabama                 Camellia               Monarch butterfly
Alaska             Forget-me-not  Four-spotted skimmer dragonfly
Arizona   Saguaro cactus blossom          Two-tailed swallowtail
Arkansas           Apple blossom              European honey bee

Index(['Alabama', 'Alaska', 'Arizona', 'Arkansas'], dtype='object')
```

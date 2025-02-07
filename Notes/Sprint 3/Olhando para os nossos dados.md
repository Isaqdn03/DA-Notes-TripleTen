 
2024-10-09 11:24

Sprint: [[Sprint3]]

Topic: #leitura-e-vizualizacao 


# Olhando para os nossos dados
### Main Topics of this Lesson:
1. Revisao do metodo `info()`
2. O que e uma `tupla`, `.shape`
3.  O metodo `sample()`

## 1. Revisao do metodo `info()`

E sempre interessante usar o metodo `info()` quando recebemos um dataframe novo para trabalhar , nao e necessario usar `print()`  para o executarm pois ele automaticamente imprimi informacoes sobre o dataframe

```python
data.info()
```

```python

<class 'pandas.core.frame.DataFrame'>
RangeIndex: 34936 entries, 0 to 34935
Data columns (total 7 columns):
 #   Column        Non-Null Count  Dtype  
---  ------        --------------  -----  
 0   country       34936 non-null  object 
 1   name          34936 non-null  object 
 2   capacity_mw   34936 non-null  float64
 3   latitude      34936 non-null  float64
 4   longitude     34936 non-null  float64
 5   primary_fuel  34936 non-null  object 
 6   owner         20868 non-null  object 
dtypes: float64(3), object(4)
memory usage: 1.9+ MB
```

- Número de linhas (`RangeIndex: 34936 entries`)
- Número de colunas (`total 7 columns`)
- Nome de cada coluna (`Column`)
- Número de valores em cada coluna que _não_ estão ausentes (`Non-Null Count`)
- Tipo de dados de cada coluna (`Dtype`)

## 2. O que e uma `tupla`, `.shape`

nao e possivel acessar os dados de `info()`, ou armazenalo em uma variavel pois ele nao passa nada, apenas  imprime na tela informacoes sobre o dataframe, 

mas podemos usar  o atributo `shape` para isso, que retorna apenas o numero de linhas e de colunas do conjunto de dados 

```python
n_rows, n_cols = data.shape 

print(f"O DataFrame tem {n_rows} linhas e {n_cols} colunas")

```

resultado:
```
O DataFrame tem 34936 linhas e 7 colunas
```

Uma tupla é semelhante a uma lista do Python em termos de indexação, objetos aninhados e repetição. No entanto, a principal diferença entre os dois é que uma tupla do Python é **`imutável`** (não pode ser alterada), e uma lista do Python é mutável.

![[Image (20).png]]

##  3. O metodo `sample()`

Nao e incomum que conjuntos de dados tenham o mesmo valor emuma coluna para muitas linhas consecutivas, para obtermos uma ideia mais diversificada do conjunto de dados que estamos trabalhando podemos usar o metodo `sample()`

```python
print(data.sample(5))
```

![[Pasted image 20241009122857.png]]

sample gera linhas aleatorias do dataframe, ela por padrao seleciona uma linha apenas, toda vez que usarmos `sample()` ela ira gerar linhas aleatorias diferentes

mas se quiser obter o mesmo resultado podemos usa o parametro `random_state=`
e configuralo para um valor inteiro de preferencia propria

```python
print(data.sample(5, random_state=1369))
```














# References








**2024-10-25 12:42**

**Sprint:** [[Sprint3]]

**Topic:** #Visualização-de-dados 

**Connections:** 

# **Matrizes de dispersão**
### Main Topics of this Lesson:


## **Matrizes de Dispersão**

- Uma matriz de dispersão é uma ferramenta visual que mostra a relação entre todas as variáveis numéricas em um conjunto de dados.
- Cada célula da matriz contém um gráfico de dispersão que mostra a relação entre duas variáveis.
- As células diagonais da matriz contêm histogramas que mostram a distribuição de valores para cada variável individual.
- As células abaixo e ao lado do histograma de uma variável mostram a relação entre essa variável e outra variável.

```python
import pandas as pd 
from matplotlib import pyplot as plt 

df = pd.read_csv('/datasets/height_weight.csv') 

pd.plotting.scatter_matrix(df, figsize=(9, 9)) 
plt.show()
```

![[Pasted image 20241025130749.png]]
## **Matrizes de Correlação**

- Uma matriz de correlação é uma tabela que contém os coeficientes de correlação para cada par de colunas numéricas em um conjunto de dados.
- A matriz é simétrica, ou seja, os coeficientes de correlação acima e abaixo da diagonal principal são iguais.
- Os coeficientes de correlação na diagonal principal são sempre iguais a 1, pois qualquer variável se correlaciona perfeitamente consigo mesma.
- A matriz de correlação é uma ferramenta útil para identificar as relações entre as variáveis em um conjunto de dados.

```python
import pandas as pd 
df = pd.read_csv('/datasets/height_weight.csv')
print(df.corr())
```

```python
          height    weight       age      male
height  1.000000  0.916526  0.010042  0.760690
weight  0.916526  1.000000  0.228538  0.785218
age     0.010042  0.228538  1.000000  0.004750
male    0.760690  0.785218  0.004750  1.000000
```

![[Pasted image 20241025131105.png]]

## **Interpretação da Matriz de Correlação**

- Os coeficientes de correlação variam de -1 a 1, onde:

- 1 indica uma correlação positiva perfeita.

- 1 indica uma correlação negativa perfeita.

- 0 indica ausência de correlação.

- A matriz de correlação pode ser usada para identificar as relações entre as variáveis em um conjunto de dados e para selecionar as variáveis mais relevantes para um modelo estatístico.

## **Vantagens da Matriz de Correlação**

- A matriz de correlação é uma ferramenta rápida e eficiente para identificar as relações entre as variáveis em um conjunto de dados.
- A matriz de correlação pode ser usada para selecionar as variáveis mais relevantes para um modelo estatístico.
- A matriz de correlação pode ser usada para identificar as relações entre as variáveis em um conjunto de dados e para entender melhor a estrutura dos dados.

## **Diferenças entre Matrizes de Dispersão e Matrizes de Correlação**

- Matrizes de dispersão mostram a relação entre as variáveis em um conjunto de dados de forma visual.
- Matrizes de correlação mostram os coeficientes de correlação entre as variáveis em um conjunto de dados de forma numérica.
- Matrizes de dispersão são mais úteis para identificar padrões e relações entre as variáveis em um conjunto de dados.
- Matrizes de correlação são mais úteis para selecionar as variáveis mais relevantes para um modelo estatístico.

## **Conclusão**

- Matrizes de dispersão e matrizes de correlação são ferramentas úteis para identificar as relações entre as variáveis em um conjunto de dados.
- Matrizes de dispersão mostram a relação entre as variáveis em um conjunto de dados de forma visual.
- Matrizes de correlação mostram os coeficientes de correlação entre as variáveis em um conjunto de dados de forma numérica.
- A escolha entre matrizes de dispersão e matrizes de correlação depende do objetivo do usuário e da estrutura dos dados.


## **Atividade**

Obtenha os coeficientes de correlação da coluna `'male'` com as outras três colunas. Em vez de chamar `corr()` na coluna `male` três vezes, crie uma matriz de correlação e extraia os três coeficientes que você quer. O resultado deve ser um objeto Series com três elementos, um para cada coeficiente.

Atribua a matriz de correlação à variável `corr_mat` e atribua o Series de coeficientes à variável `male_corr`. Depois imprima `male_corr`.

Use `loc[]` com `'male'` como o primeiro argumento e uma lista dos outros dados como o segundo argumento para extrair esses valores na variável `male_corr`.

```python
import pandas as pd

df = pd.read_csv('/datasets/height_weight.csv')

corr_mat = df.corr() 

male_corr = corr_mat.loc['height':'age', 'male'] 

print(male_corr)
```

```python
height    0.760690
weight    0.785218
age       0.004750
Name: male, dtype: float64
```


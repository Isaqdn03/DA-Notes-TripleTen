
**2024-10-25 10:49**

**Sprint:** [[Sprint3]]

**Topic:** #Visualização-de-dados 

**Connections:** 

# **Gráficos de dispersão**
### Main Topics of this Lesson:


## **Gráficos de Dispersão**

Um gráfico de dispersão é uma ferramenta importante para visualizar a relação entre duas variáveis. Ele é especialmente útil quando se tem um grande conjunto de dados e se deseja entender a relação entre as variáveis.

**Características de um Gráfico de Dispersão**

- Cada ponto de dados é desenhado independentemente, sem linhas conectando-os.
- Não há necessidade de ordenar os dados para criar um gráfico de dispersão.
- É possível identificar facilmente pontos atípicos.

**Métodos para Criar Gráficos de Dispersão**

1. **Usando o parâmetro `style='o'`**

Exemplo:

```python
`df.plot(x='height', y='weight', style='o')`
```

Este método cria um gráfico de dispersão marcando explicitamente cada ponto de dados com um círculo.

2. **Usando o parâmetro `kind='scatter'`**

Exemplo:

```python
`df.plot(x='height', y='weight', kind='scatter')`
```

3. **Usando o parametro `alpha=`**

Este método cria um gráfico de dispersão usando o método padrão `plot()`.
**Parâmetro `alpha`O parâmetro `alpha` regula a transparência dos pontos no gráfico. Ele pode aceitar qualquer valor entre 0 (completamente transparente) e 1 (nada transparente).**

Exemplo:

```python
df.plot(x='height', y='weight', kind='scatter', alpha=0.5)
```

Este exemplo cria um gráfico de dispersão com pontos semi-transparentes.

**Recapitulação**

- `sort_values()`: ordena os dados pela coluna passada.
- `style='o'`: cria um gráfico de dispersão marcando explicitamente cada ponto de dados com um círculo.
- `kind='scatter'`: cria um gráfico de dispersão usando o método padrão `plot`.
- `alpha=`: define a transparência dos pontos no gráfico no valor especificado.

## **Dicas**
- Ao decidir qual tipo de gráfico usar para os dados, é importante considerar o que cada ponto dos dados representa e como se relaciona ao próximo.
- É importante considerar a transparência dos pontos no gráfico para evitar sobreposição e facilitar a visualização.
- Ler dados de um arquivo CSV: `df = pd.read_csv('/datasets/height_weight.csv')`
- Imprimir as primeiras linhas do DataFrame: `print(df.head())`
- Conferir as informações gerais sobre o DataFrame: `print(df.info())`
- Criar um gráfico de dispersão: `df.plot(x='height', y='weight', kind='scatter')`
- Definir a transparência dos pontos no gráfico: `df.plot(x='height', y='weight', kind='scatter', alpha=0.5)`

## Exemplo de codigo de grafico de dipersao (scatter)

```python
import pandas as pd
from matplotlib import pyplot as plt

df = pd.read_csv('/datasets/height_weight.csv')

df.plot(x = 'age', y= 'height',
        kind = 'scatter',
        title =  "Adult heights",
        alpha = 0.36,
        figsize = [8, 6],
        xlabel = "Age / years",
        ylabel = "Height / inches"
       )

plt.show()

```

![[Pasted image 20241025121435.png]]




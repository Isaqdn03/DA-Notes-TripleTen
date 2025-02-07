 
**2024-10-23 19:49**

**Sprint:** [[Sprint3]]

**Topic:** #Visualização-de-dados 

**Connections:** 

# **Como criar gráficos em Python com matplotlib**
### Main Topics of this Lesson:


## **Importando Bibliotecas**

- Importe a biblioteca `pandas` para trabalhar com DataFrames e Series.
- Importe a biblioteca `matplotlib.pyplot` para criar gráficos.

```python

import pandas as pd 
from matplotlib import pyplot as plt

```

## **Métodos e Funções**

- `plot()`: método da pandas que prepara uma imagem a partir dos dados.
- `show()`: função da biblioteca pyplot da Matplotlib que apresenta uma imagem ao usuário.
- `savefig()`: função da Matplotlib que salva o gráfico como um arquivo de imagem.

```python
df = pd.DataFrame({'a':[2, 3, 4, 5], 'b':[4, 9, 16, 25]}) 
df.plot() 
plt.show()
```

## **Selecionar colunas se necessario**

```python
df = pd.DataFrame({'a':[2, 3, 4, 5], 'b':[4, 9, 16, 25]}) df['b'].plot() 
plt.show()
```
## **Parâmetros de Personalização**

- `title=`: parâmetro para definir o título do gráfico.

```python
df = pd.DataFrame({'a':[2, 3, 4, 5], 'b':[4, 9, 16, 25]}) df.plot(title='Título do Gráfico') 
plt.show()
```

- `style=`: parâmetro para alterar o estilo do marcador do gráfico.
- https://matplotlib.org/stable/api/markers_api.html - site com todos os marcadores) 

```python
df = pd.DataFrame({'a':[2, 3, 4, 5], 'b':[4, 9, 16, 25]}) df.plot(style='o') 
plt.show()
```

- `x=` e `y=`: parâmetros para construir duas colunas relacionadas entre si.

```python
df = pd.DataFrame({'a':[2, 3, 4, 5], 'b':[4, 9, 16, 25]}) df.plot(x='a', y='b') 
plt.show()
```

- `xlabel=` e `ylabel=`: parâmetros para definir as legendas dos eixos.

```python
df = pd.DataFrame({'a':[2, 3, 4, 5], 'b':[4, 9, 16, 25]}) df.plot(xlabel='Eixo X', ylabel='Eixo Y') 
plt.show()
```

- `xlim=` e `ylim=`: parâmetros para definir os limites dos eixos.

```python
df = pd.DataFrame({'a':[2, 3, 4, 5], 'b':[4, 9, 16, 25]}) df.plot(xlim=[0, 10], ylim=[0, 10]) 
plt.show()
```

- `grid=`: parâmetro para adicionar linhas de grade.

```python
df = pd.DataFrame({'a':[2, 3, 4, 5], 'b':[4, 9, 16, 25]}) df.plot(grid=True) 
plt.show()
```

- `figsize=`: parâmetro para definir o tamanho do gráfico.

```python
df = pd.DataFrame({'a':[2, 3, 4, 5], 'b':[4, 9, 16, 25]}) df.plot(figsize=[10, 5]) 
plt.show()`
```

## **Dicas e Práticas**

- Sempre use `plt.show()` para exibir o gráfico.
- Use `plt.savefig()` para salvar o gráfico como um arquivo de imagem.
- Use `df.plot()` para criar gráficos simples e rápidos.
- Use `plt.xlabel()` e `plt.ylabel()` para definir as legendas dos eixos.
- Use `plt.xlim()` e `plt.ylim()` para definir os limites dos eixos.
- Use `plt.grid()` para adicionar linhas de grade.
- Use `plt.figsize()` para definir o tamanho do gráfico.


## **Exemplo de codigo de um grafico**

```python
import pandas as pd
from matplotlib import pyplot as plt

df = pd.DataFrame({'a':[2, 3, 4, 5], 'b':[4, 9, 16, 25], 'c':[1, 3, 6, 10]})

df.plot( title = 'A vs C',
         x='c', y='a',
         style = '*',
         color = 'hotpink',
         figsize = [5, 5],
         xlim = [0, 12],
         ylim = [1, 6],
         xlabel = 'C',
         ylabel = 'A',       
)

plt.show()
```

![[Pasted image 20241025104902.png]]






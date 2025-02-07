
**2024-10-25 13:22**

**Sprint:**[[Sprint3]]

**Topic:** #Visualização-de-dados 

**Connections:** 

# **Gráficos de linha**
### Main Topics of this Lesson:

## Quando Usar Gráficos de Linha

- **Gráficos de linha são ideais para dados que são conectados cronologicamente, onde cada ponto de dados tem alguma relação com o ponto anterior. Exemplos incluem dados de temperaturas, tráfego e bolsa de valores.**

## Estrutura dos Dados (DESTE EXEMPLO)

- No exemplo dado, os dados da bolsa de valores da Starbucks (SBUX) de 2015 a 2019 são usados.
- As colunas do dataframe incluem:
    
    - `date`: a data em que os dados foram registrados.
    - `open`: o preço de abertura das ações em USD.
    - `close`: o preço de fechamento das ações em USD.
    - `volume`: o número total de ações negociadas.
    

## Código Básico para Gráfico de Linha

```python
import pandas as pd 
from matplotlib import pyplot as plt 

df = pd.read_csv('/datasets/sbux.csv') 

df.plot(x='date', y='open') 
plt.show()`
```

- O método `plot()` do Pandas é usado sem especificar o parâmetro `kind`, o que resulta em um gráfico de linha por padrão.
- As colunas `x` e `y` são especificadas para definir os eixos X e Y do gráfico.

## Melhorias no Gráfico

### Adicionar Título e Legendas

- Adicionar um título ao gráfico torna-o mais bonito e fácil de entender.
- Adicionar legendas aos eixos X e Y ajuda a clarificar o que cada eixo representa.

```python
df.plot(x='date',
        y='open',
        title='Starbucks market open',
        xlabel='Date',
        ylabel='Share price / USD')
plt.show()
```
### Formatar as Legendas do Eixo X

- Para evitar que as legendas das marcas do eixo X se sobreponham, use o parâmetro `rot` para rotacionar as legendas.

```python
df.plot(x='date',
        y='open',
        title='Starbucks market open',
        xlabel='Date',
        ylabel='Share price / USD',
        rot=45)
plt.show()
```
## Outras Opções de Melhoria
### Remover Legendas Inúteis

- Se as legendas forem inúteis, elas podem ser removidas usando o parâmetro `legend=False`.

```python
df.plot(x='date',
        y='open',
        legend=False,
        title='Starbucks market open',
        xlabel='Date',
        ylabel='Share price / USD',
        rot=45)
plt.show()
```

## Exemplo Completo de Código Melhorado

```python
import pandas as pd
from matplotlib import pyplot as plt

df = pd.read_csv('/datasets/sbux.csv')

df.plot(x='date',
        y='open',
        legend=False,
        title='Starbucks market open',
        xlabel='Date',
        ylabel='Share price / USD',
        rot=45)

plt.show()
```

## Considerações Adicionais

- **Tipos de Dados**: Embora as datas sejam representadas como strings no exemplo, em aplicações mais avançadas, usar tipos de dados especiais para datas e horas pode facilitar a extração de informações e cálculos.
- **Outros Tipos de Gráficos**: Além de gráficos de linha, o Pandas também suporta outros tipos de gráficos, como gráficos de barras, histogramas, gráficos de dispersão, etc., usando o parâmetro `kind` do método `plot()`.










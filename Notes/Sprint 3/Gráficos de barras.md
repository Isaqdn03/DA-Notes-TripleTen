
**2024-10-25 14:05**

**Sprint:** [[Sprint3]]

**Topic:** #Visualização-de-dados 

**Connections:** 

# **Gráficos de barras**
### Main Topics of this Lesson:


## **Gráficos de Barras**

 Gráficos de barras são uma ferramenta útil para comparar categorias definidas por um valor numérico. Eles são especialmente úteis para visualizar dados categóricos e numéricos.
 
```python
import pandas as pd
from matplotlib import pyplot as plt

df = pd.read_csv('/datasets/west_coast_pop.csv') 

df.plot(x='year', kind='bar') 

plt.show()
```

**Informações adicionais:**

- É importante especificar a coluna correta como eixo X para que o gráfico faça sentido.
- Se você não especificar nenhuma coluna para o parâmetro y=, a pandas vai criar automaticamente uma barra para cada coluna no DataFrame que não está no eixo X.
- O gráfico de barras facilita tirar algumas conclusões sobre os dados, como a população da Califórnia é consistentemente muito maior do que a dos outros estados.

 ## **Melhorando o Gráfico**
 Explicação: Para melhorar o gráfico, podemos adicionar um título, rótulos de eixo e uma legenda. Isso torna o gráfico mais profissional e fácil de entender.**Código:**

```python
import pandas as pd
from matplotlib import pyplot as plt

df = pd.read_csv('/datasets/west_coast_pop.csv')

df.plot(x='year',
        kind='bar',
        title='West coast USA population growth',
        xlabel='Year',
        ylabel='Population (millions)')

plt.legend(['CA', 'OR', 'WA'])
plt.show()
```

**Informações adicionais:**

- A ordem da legenda na lista vai corresponder à ordem das colunas no DataFrame, então é importante ordenar as legendas corretamente.
- plt.legend() precisa vir depois de chamarmos plot() no DataFrame.
- É importante usar legendas com nomes significativos para que o público possa entender o gráfico.

## **Visualizando Dados Categóricos**

**Explicação:** Gráficos de barras são especialmente úteis para visualizar dados categóricos. Eles permitem comparar categorias definidas por um valor numérico.

```python
import pandas as pd
from matplotlib import pyplot as plt

df = pd.read_csv('/datasets/west_coast_pop.csv')

df.plot(x='year', kind='bar')
plt.show()
```

**Informações adicionais:**

- É importante escolher a coluna correta como eixo X para que o gráfico faça sentido.
- Gráficos de barras são especialmente úteis para visualizar dados categóricos e numéricos.

## **Atividade Exemplo**

```python
import pandas as pd
from matplotlib import pyplot as plt

df = pd.read_csv('/datasets/west_coast_pop.csv')

df.plot(x='year', y=['or_pop', 'wa_pop'], kind='bar', title='Pacific Northwest population growth', xlabel='Year', ylabel='Population (millions)')

plt.legend(['OR', 'WA'])
plt.show()
```

![[Pasted image 20241025152215.png]]

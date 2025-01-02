
2024-10-07 22:17

Sprint:[[Sprint2]]

Topic: #dataframe-pandas 


# Importação e uso de pacotes
# 4.3 **Importação e uso de pacotes:**

## Importanto a biblioteca

para usar pandas se precisar importa-la

```python
import pandas
```

normalmente. a pandas e importada com o alias, `pd` facilitando referencia depois no seu codigo, pode se usar qualquer alias, mas essa e a mais comum para pandas.

```python
import pandas as pd
```

## Fazendo um DataFrame

para usar Pandas, e preciso transformar meus dados em um DataFrame, e eu posso fazer isso usando a classe `DataFrame()`

a classe DataFrame() recebe dois argumentos : `data` e

![https://practicum-content.s3.amazonaws.com/resources/11.3PT_1690266007.png](https://practicum-content.s3.amazonaws.com/resources/11.3PT_1690266007.png)

Exemplo de Dataframe em Pandas:

```python
import pandas as pd

# preparando os dados e os nomes das colunas
atlas = [
      ['France', 'Paris'],  
        ['Russia', 'Moscow'],  
        ['China', 'Beijing'],  
        ['Mexico', 'Mexico City'],  
        ['Egypt', 'Cairo'],
]
geography = ['country', 'capital']

# fazendo um DataFrame
world_map = pd.DataFrame(data=atlas , columns=geography)

# imprimindo o DataFrame
print(world_map)
```

Como a `DataFrame()` é uma classe na biblioteca Pandas, ela é precedida por `pd` quando chamada.



# References







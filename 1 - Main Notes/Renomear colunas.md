
2024-10-07 22:28

Sprint: [[Sprint2]]
Topic: #dataframe-prepocess 




# Renomear colunas

# 5.3 **Renomear colunas**

## Corrigindo problemas

para primeiro verificar se existem problemas de erro com as colunas, podemos comecar usando o metodo `info()`

```python
print(df.info())
```

receberemos algo como

![https://practicum-content.s3.amazonaws.com/resources/11.2_5PT_1698311430.png](https://practicum-content.s3.amazonaws.com/resources/11.2_5PT_1698311430.png)

```python
import pandas as pd

# as distâncias são armazenadas em uma lista de listas
measurements = [['Sun', 146, 152],
                                ['Moon', 0.36, 0.41], 
                                ['Mercury', 82, 217], 
                                ['Venus', 38, 261],
                                ['Mars', 56, 401],
                                ['Jupiter', 588, 968],
                                ['Saturn', 1195, 1660],
                                ['Uranus', 2750, 3150],
                                ['Neptune', 4300, 4700],
                                ['Halley\\'s comet', 6, 5400]]

# os nomes das colunas são armazenados na variável de cabeçalho
header = ['Celestial bodies ','MIN', 'MAX'] 

# armazenando o DataFrame na variável celestial
celestial = pd.DataFrame(data=measurements, columns=header)
```

para checar os nomes das colunas usamos o atributo `.columns`

```python
print(celestial.columns)
```

```
Index(['Celestial bodies ','MIN', 'MAX'], dtype='object')
```

para fazer alteracoes que desejamos usamos um bloco de codigo como esse:

```python
# Declarando um dicionário com os nomes antigos das colunas como as chaves
# e os novos nomes de colunas como os valores
columns_new ={
    "Celestial bodies ": "celestial_bodies",
    "MIN": "min_distance",
    "MAX": "max_distance",
    }

# Chamando o método rename e passando
# o dicionário como um argumento para o parâmetro columns
celestial = celestial.rename(columns = columns_new)
print(celestial.columns)
```

Para renomear colunas, chame o método `rename()` com um dicionário como argumento `columns`. As chaves no dicionário devem ser os nomes das colunas antigas e os valores correspondentes devem ser os novos nomes.

e necessario reatribuir a variavel celestial para refletir as alteracoes.

## Renomeando colunas usando parametro `inplace`

podemos renomear colunas que nao requer reatribuicao como feito acima, basta especificar o parametro `inplace` e definilo com `True`

```python
# Declarando um dicionário com os nomes antigos das colunas como as chaves
# e os novos nomes de colunas como os valores
columns_new ={
    "Celestial bodies ": "celestial_bodies",
    "MIN": "min_distance",
    "MAX": "max_distance",
    }

# Chamando o método rename e passando
# o dicionário como um argumento para o parâmetro columns
# e True como um argumento para o parâmetro inplace
celestial.rename(columns = columns_new, inplace = True)
print(celestial.columns)
```

## **Forma automatizada de renomear colunas**

As vezes os numeros de colunas pode ser alto, tornando dificil atribuir manualmente novos valores aos nomes de coluna, tornando tambem dificil encontrar os erros em cada uma delas, nesse caso ciclos e metodos de strings podem ser bastante util

```python
new_col_names = []

for old_name in celestial.columns:
    # Primeiro, remova os espaços no início e no final
    name_stripped = old_name.strip()
    # Em seguida, coloque todas as letras em minúsculas
    name_lowered = name_stripped.lower()
    # Por fim, substitua os espaços entre as palavras por sublinhados
    name_no_spaces = name_lowered.replace(' ', '_')
    # Adicione o novo nome à lista de novos nomes das colunas
    new_col_names.append(name_no_spaces)

# Substitua os nomes antigos pelos novos
celestial.columns = new_col_names

print(df.columns)
#para conferir se esta tudo na forma desejada
```

1. Cria-se uma lista vazia chamada `new_col_names` para armazenar os novos nomes das colunas.
2. Inicia-se um loop que percorre cada nome de coluna atual do DataFrame `celestial`.
3. Para cada nome de coluna, são aplicadas as seguintes transformações:
    - a. `strip()`: Remove espaços em branco no início e no final do nome.
    - b. `lower()`: Converte todas as letras para minúsculas.
    - c. `replace(' ', '_')`: Substitui espaços entre palavras por sublinhados.
4. O novo nome de coluna transformado é adicionado à lista `new_col_names`.
5. Após processar todos os nomes, a lista `new_col_names` é atribuída diretamente ao atributo `columns` do DataFrame `celestial`, substituindo os nomes antigos pelos novos.


# References








2024-10-07 22:20

Sprint:[[Sprint2]]

Topic: #dataframe-pandas 


# Indexação do DataFrame
# 4.5 **Indexação do DataFrame**

## **Indexação por coordenadas**

usamos o atributo `loc[]` e dentro do colchete e necessesario um numero de linha e o nome da coluna que desejamos acessar,por exemplo : `df.loc[4, 'genre']`

![https://practicum-content.s3.amazonaws.com/resources/11.5PT_1690266171.png](https://practicum-content.s3.amazonaws.com/resources/11.5PT_1690266171.png)

o resultado dessa indexacao e `pop`

Exemplo em codigo:

```python
import pandas as pd

df = pd.read_csv('/datasets/music_log_chpt_11.csv')

result = df.loc[7, 'track']
print(result)
```

```python
Riviera
```

e possivel acessar celulas individuais mas tambem grupos de celulas usando indexacao, por exemplo

- Todas as células de uma determinada linha.
- Todas as células de várias linhas.
- Todas as células de um intervalo de linhas.

## Tabela com tipos de **indexação**

|Tipo|Amostra|Resultado esperado|
|---|---|---|
|Uma célula|`.loc[7, 'genre']`|Extrai o valor da célula localizada na coluna `'genre'` e na 8ª linha (que possui o índice `7`).|
|Uma coluna|`.loc[:, 'genre']`|Extrai os valores de todas as células na coluna `'genre'`.|
|Múltiplas colunas|`.loc[:, ['Artist', 'genre']]`|Extrai todos os valores de todas as células nas colunas `'Artist'` e `'genre'`.|
|Múltiplas colunas consecutivas (fatia)|`.loc[:, 'user_id': 'genre']`|Extrai todos os valores de todas as células nas colunas começando na coluna `'user_id'` e terminando com a coluna `'genre'`.|
|Uma linha|`.loc[1]`|Extrai os valores da 2ª linha (com índice `1`).|
|Todas as linhas, começando pela linha especificada|`.loc[1:]`|Extrai todos os valores da segunda linha e vai até a última linha.|
|Todas as linhas, até a linha especificada|`.loc[:3]`|Extrai todos os valores das quatro primeiras linhas (da linha com índice `0` até a linha com índice `3`).|
|Múltiplas linhas consecutivas (fatia)|`.loc[2:5]`|Extrai todos os valores de células entre a terceira linha e a linha com índice `5`.|

## **Notação abreviada para indexação**

em vez de chamar o atributo `.loc()` podemos passar entre colchetes de uma variavel na qual nosso dataframe esta armazenado os dados que desejamos fatiar (df e um exemplo de variavel que armazena um dataframe)

Tabela com abreviacoes para indexacao:

|Tipo|Amostra|Notação abreviada|
|---|---|---|
|Uma célula|`.loc[7, 'genre']`|-|
|Uma coluna|`.loc[:, 'genre']`|`df['genre']`|
|Várias colunas|`.loc[:, ['genre', 'Artist']]`|`df[['genre', 'Artist']]`|
|Várias colunas consecutivas (fatia)|`.loc[:,'total play': 'genre']`|-|
|Uma linha|`.loc[1]`|-|
|Todas as linhas, começando pela linha determinada|`.loc[1:]`|`df[1:]`|
|Todas as linhas, até a linha especificada|`.loc[:3]` incluindo 3|`df[:3]` não incluindo 3|
|Múltiplas linhas consecutivas (fatia)|`.loc[2:5]` incluindo 5|`df[2:5]` não incluindo 5|

- Fatias **excluem** o final do intervalo.
- Você não pode lidar com uma única célula ou linha, nem uma fatia de uma coluna.



# References







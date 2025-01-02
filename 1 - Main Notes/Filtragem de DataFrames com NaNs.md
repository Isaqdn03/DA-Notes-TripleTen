
2024-10-10 14:16

Sprint:[[Sprint3]]

Topic: #tratamento-ausente-duplicados 


# Filtragem de DataFrames com NaNs
### Main Topics of this Lesson:
1. Filtragem de DataFrames para lidar com valores ausentes
2. Múltiplas condições de filtragem


## 1. Filtragem de DataFrames para lidar com valores ausentes

podemos usar `isna()` juntamente com filtragem de dataframes, para criar um dataframe que possui valores somente ausentes ou somente nao ausentes para a coluna especificada:

Exemplo de filtragem de um dataframe que contera somente valores ausentes na coluna `source:

![[Pasted image 20241010145059.png]]

Resultado:

![[Pasted image 20241010145228.png]]

analise de codigo:
1. a coluna `'source'` usando `df_logs['source']`
2. em seguida aplicamos o metodo `isna()` indicando somente valores ausentes desta coluna `df_logs['source'].isna()`
3. 1. Usamos esse Séries de booleanos para filtrar o DataFrame original, extraindo apenas as linhas em que `'source'` tem valores ausentes.
4. e por fim imprimimos a nova tabela 

Como alternativa podemos tambem imprimir na tabela somente valores nao ausentes, usando a mesma aboragem acima, porem com uma pequena mudanca

![[Pasted image 20241010145648.png]]

![[Pasted image 20241010145707.png]]

aplicando o caractere `~` indicamos que queremos somente os valores nao ausentes


## 2. Múltiplas condições de filtragem

Podemos impor mais de uma condicao na filtragem de dataframes, podemos criar um dataframe sem valores ausentes na coluna `email` e que contem apenas o valor `email`
 na coluna `source`

![[Pasted image 20241010150044.png]]

![[Pasted image 20241010150109.png]]

O código verifica duas condições em uma DataFrame: a ausência de valores nulos na coluna 'email' e se a coluna 'source' tem o valor 'email'. A operação lógica `&` combina essas condições, retornando as linhas onde ambas são verdadeiras.

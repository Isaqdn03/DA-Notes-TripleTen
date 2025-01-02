
**2024-10-15 19:50**

**Sprint:**[[Sprint3]]

**Topic:** #Filtragem-de-Dados 

**Connections:** 

# **Filtragem personalizada usando query()**
### Main Topics of this Lesson:

1. Filtragem com strings de consulta e o método `query()`
2. Filtragem usando o método `isin()`

## **1. Filtragem com strings de consulta e o método `query()`**

a Filtragem usando `query` espera uma string como parametro, a string representa a consulta que queremos fazer no DataFrame

`query()` para filtragem de comparacao

```python
import pandas as pd

df = pd.read_csv('/datasets/vg_sales.csv')

print(df.query("jp_sales > 1")[['name', 'jp_sales']])
```

Para filtrar usando `query()` com base nas comparações de strings, você precisa colocar a string entre aspas.

```python
print(df.query("publisher == 'Nintendo'"[['name','publisher']].head())
```

```
                       name publisher
0                Wii Sports  Nintendo
1         Super Mario Bros.  Nintendo
2            Mario Kart Wii  Nintendo
3         Wii Sports Resort  Nintendo
4  Pokemon Red/Pokemon Blue  Nintendo
```

 Usamos aspas simples para denotar `'Nintendo'`, porque a nossa string de consulta completa já estava entre aspas duplas.

### **Mais Exemplos de query**

```python
import pandas as pd

df = pd.read_csv('/datasets/vg_sales.csv')

cols = ['name', 'publisher', 'developer']

df_filtered =df.query('publisher == developer')[cols] 

print(df_filtered.head())
```

```
                    name publisher developer
0             Wii Sports  Nintendo  Nintendo
2         Mario Kart Wii  Nintendo  Nintendo
3      Wii Sports Resort  Nintendo  Nintendo
6  New Super Mario Bros.  Nintendo  Nintendo
7               Wii Play  Nintendo  Nintendo
```

1. **Define uma lista de colunas**:
    
    `cols = ['name', 'publisher', 'developer']`
    
    A variável `cols` armazena as colunas que você deseja filtrar no `DataFrame`. Aqui, são as colunas `name` (nome do jogo), `publisher` (empresa que publicou o jogo), e `developer` (empresa que desenvolveu o jogo).
    
2. **Filtra as linhas onde o `publisher` e o `developer` são iguais**:
    
    `df_filtered = df.query('publisher == developer')[cols]`
    
    O método `query` do Pandas permite fazer consultas em `DataFrame` de forma mais legível. Aqui, ele filtra as linhas onde o valor da coluna `publisher` é igual ao da coluna `developer`, ou seja, seleciona jogos que foram desenvolvidos e publicados pela mesma empresa.
    
3. **Exibe as primeiras 5 linhas do `DataFrame` filtrado**:
    `print(df_filtered.head())`
    
    A função `head()` exibe as primeiras 5 linhas do `DataFrame` filtrado, mostrando apenas as colunas especificadas em `cols` (nome, publisher, e developer).
    

**Resumo do funcionamento**: O código carrega um dataset de vendas de videogames, filtra jogos onde a empresa que desenvolveu o jogo também foi a que publicou (ou seja, `publisher == developer`), e depois exibe as primeiras 5 linhas desses dados, mostrando apenas as colunas de interesse: nome do jogo, publisher, e developer.

## **2. Filtragem usando o método `isin()`**

`isin()` verifica se os valores em uma coluna correspondem a algum dos valores em outro vetor, como uma lista ou um dicionário.

```python
import pandas as pd

df = pd.read_csv('/datasets/vg_sales.csv')

handhelds = ['3DS', 'DS', 'GB', 'GBA', 'PSP']

print(df[df['platform'].isin(handhelds)][['name', 'platform']])

```

- `df['platform'].isin(handhelds)` verifica se os valores na coluna `'platform'` são iguais a um dos valores da lista `handhelds`
- `df[df['platform'].isin(handhelds)]` filtra o DataFrame mantendo apenas as linhas retornadas como resultado da verificação da igualdade que executamos na etapa anterior.
- Por fim, selecionamos apenas duas colunas do DataFrame filtrado: `['name', 'platform']` descartando o resto das colunas.

podemos tambem usar `~` para inverter e obter resultado no qual os valores especificados nao estarao na coluna 

```python
print(df[~df['platform'].isin(handhelds)][['name', 'platform']])
```

**Também podemos verificar a existência de algo usando o método `query()` com a palavra-chave `in` na string de consulta.**

```python
handhelds = ['3DS', 'DS', 'GB', 'GBA', 'PSP'] 

print(df.query("platform in @handhelds")[['name', 'platform']])
```

função `query` para verificar se o valor da coluna `platform` está na lista `handhelds`. O código então seleciona e exibe apenas as colunas `name` (nome do jogo) e `platform` (a plataforma portátil correspondente), mostrando o resultado na tela.

Como alternativa, você pode encontrar as linhas que não estão na lista usando a palavra-chave `not in`:

```python
handhelds = ['3DS', 'DS', 'GB', 'GBA', 'PSP'] print(df.query("platform not in @handhelds")[['name', 'platform']])
```

neste caso vai nos exibir somente as colunas `name` e `plataform` que nao contem os itens mencionados e armazenado na variavel `handhelds`  

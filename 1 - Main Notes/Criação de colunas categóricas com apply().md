
**2024-10-31 18:31**

**Sprint:** [[Sprint3]]

**Topic:** #engenharia-de-caracteristicas 

**Connections:** 

---
# **Criação de colunas categóricas com apply()**


# Anotações sobre Criação de Colunas Categóricas com `apply()`

Este documento detalha a criação de colunas categóricas em um DataFrame Pandas usando o método `apply()` e funções personalizadas.  A categorização agrupa dados em categorias significativas, facilitando a análise e interpretação.

## 1. Introdução à Categorização

A categorização simplifica a análise ao agrupar dados numéricos em categorias mais amplas.  Isso é particularmente útil quando se trabalha com dados distribuídos em muitas categorias individuais, como anos de lançamento de jogos, onde analisar cada ano separadamente pode não ser informativo.

## 2.  `value_counts()` e `sort_index()`

O método `value_counts()` conta a ocorrência de valores únicos em uma série (coluna).  Ele retorna uma nova série onde o índice representa os valores únicos e os valores representam suas contagens.

```python
import pandas as pd

df = pd.read_csv('/datasets/vg_sales.csv')
df_year_of_release = df['year_of_release'].value_counts()

print(df_year_of_release)
```

Para ordenar o resultado cronologicamente (ou em qualquer ordem de índice desejada), usamos `sort_index()`:

```python
df_year_of_release_sorted = df['year_of_release'].value_counts().sort_index()

print(df_year_of_release_sorted)
```

**Explicação:** `sort_index()` ordena a série pelo seu índice, enquanto `sort_values()` ordena pelos valores.

## 3. Criando Funções Personalizadas para Categorização

Para categorizar dados com base em regras específicas, criamos funções personalizadas.  A função recebe um valor como entrada e retorna a categoria correspondente.

**Exemplo:** Categorizando jogos por geração:

```python
def era_group(year):
    """
    Categoriza o ano de lançamento de um jogo em uma geração.
    """
    if year < 2000:
        return 'retro'
    elif year < 2010:
        return 'modern'
    elif year >= 2010:
        return 'recent'
    else:
        return 'unknown'

# Testando a função:
print(era_group(1983))  # Output: retro
print(era_group(2009))  # Output: modern
print(era_group(2021))  # Output: recent
import numpy as np
print(era_group(np.nan)) # Output: unknown
```

**Explicação:** A função `era_group()` recebe o ano como entrada e usa condicionais (`if`, `elif`, `else`) para determinar a geração.  Valores `NaN` (Not a Number), representando dados faltantes, são categorizados como 'unknown'.

## 4. Aplicando Funções com `apply()`

O método `apply()` aplica uma função a cada elemento de uma série (coluna).  Ele recebe a função como argumento.

```python
df['era_group'] = df['year_of_release'].apply(era_group)

print(df.head())
```

**Explicação:**  Esta linha aplica a função `era_group()` a cada valor na coluna `year_of_release`. O resultado de cada chamada da função é armazenado na nova coluna `era_group`.

## 5. Analisando os Dados Categorizados

Após a categorização, podemos usar `value_counts()` para analisar a distribuição das novas categorias:

```python
print(df['era_group'].value_counts())
```

**Explicação:**  `value_counts()` agora conta a frequência de cada categoria de geração, fornecendo insights sobre a distribuição dos jogos em cada grupo.


## Conclusão

A combinação de funções personalizadas com o método `apply()` oferece uma maneira flexível e poderosa de criar colunas categóricas em DataFrames Pandas.  Isso facilita a análise de dados e a extração de insights significativos.  Lembre-se de que a função aplicada deve ser projetada para lidar com valores `NaN` para evitar erros.









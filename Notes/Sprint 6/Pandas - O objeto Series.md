
**2025-02-10 19:47**

**Sprint:** [[Sprint6]]

**Topic:** #python-em-mais-detalhes 

**Connections:** 

---
# **Pandas - O objeto Series**

## Introdução ao Objeto Series
Um objeto Series é uma estrutura fundamental no pandas que representa uma coluna única de dados. (aka: objetos series e apenas uma coluna de um Dataframe)

> **Definição**: Series é uma estrutura de dados unidimensional do Pandas que pode armazenar diferentes tipos de dados (números, strings, booleanos, etc.) em uma única coluna.

[Breakdown de um Objeto Series](https://practicum-content.s3.amazonaws.com/resources/Tema_5_structure_table_v1_1549308959_1549907576_1702364399.png)

### Características Principais
- Unidimensional (uma única coluna)
- Possui índice para acesso aos dados
- Pode ser extraído de um DataFrame
- Possui atributos específicos (name, size)

## DataFrame vs Series: Diferenças Estruturais

| Característica | DataFrame | Series |
|---------------|-----------|---------|
| Dimensionalidade | Bidimensional (linhas e colunas) | Unidimensional (apenas uma coluna) |
| Acesso aos dados | Requer duas coordenadas (coluna e índice) | Requer apenas índice |
| Estrutura | Conjunto de Series | Coluna única |
| Uso típico | Dados tabulares completos | Análise de uma única variável |

### Exemplo de Código: Identificando Tipos de Estruturas
```python
import pandas as pd

# Lendo arquivo CSV
df = pd.read_csv('/datasets/music_log_chpt_11.csv')

# Extraindo múltiplas colunas (DataFrame)
part_df = df[['genre', 'Artist']]
print(type(part_df))  # pandas.core.frame.DataFrame

# Extraindo uma única coluna (Series)
artist_series = df['Artist']
print(type(artist_series))  # pandas.core.series.Series
```

## Atributos Essenciais do Series

### 1. Atributo name
```python
# Exemplo de uso do atributo name
artist_series = df['Artist']
print(artist_series.name)  # Output: Artist
```

*Importante*: O atributo name é herdado do nome da coluna original do DataFrame.

### 2. Atributo size
```python
# Verificando o tamanho do Series
print(artist_series.size)  # Output: número total de elementos
```

## Métodos de Indexação em Series

### Tipos de Indexação

7. **Indexação Simples**
```python
# Acessando um único elemento
print(artist_series[0])  # Primeiro elemento
```

8. **Indexação por Fatiamento**
```python
# Acessando múltiplos elementos consecutivos
top_20 = artist_series[0:20]  # Primeiros 20 elementos
```

9. **Indexação com loc**
```python
# Usando loc para indexação explícita
element = artist_series.loc[7]  # Elemento no índice 7
```

### Tabela de Métodos de Indexação

| Operação | Notação Completa | Notação Abreviada |
|----------|-----------------|-------------------|
| Um elemento | `series.loc[7]` | `series[7]` |
| Múltiplos elementos | `series.loc[[5,7,10]]` | `series[[5,7,10]]` |
| Fatiamento | `series.loc[5:10]` | `series[5:10]` |

## Filtragem em Series

### Filtragem Lógica
```python
# Exemplo de filtragem por condição
total_play = df['total play']
lower_20 = total_play < 20
filtered_series = total_play[lower_20]
```

### Filtragem por Igualdade
```python
# Filtrando por valor específico
genre = df['genre']
pop_genre = genre == 'pop'
pop_df = df[pop_genre]
```

## Pontos-Chave para Lembrar

10. **Estrutura Básica**
   - Series é unidimensional
   - Representa uma única coluna de dados
   - Possui índice para acesso aos elementos

11. **Manipulação**
   - Pode ser extraído de um DataFrame
   - Suporta diferentes tipos de indexação
   - Permite filtragem baseada em condições

12. **Boas Práticas**
   - Armazenar Series em variáveis para manipulação frequente
   - Usar notação apropriada para cada tipo de acesso
   - Verificar o tipo de estrutura antes das operações

# Resumo Geral

O objeto Series do Pandas é uma estrutura fundamental para análise de dados em Python, oferecendo uma maneira eficiente de trabalhar com colunas individuais de dados. Sua natureza unidimensional, combinada com recursos poderosos de indexação e filtragem, torna-o uma ferramenta essencial para manipulação e análise de dados. A compreensão clara das diferenças entre Series e DataFrame, junto com o domínio dos métodos de acesso e manipulação, permite uma análise de dados mais eficiente e precisa.










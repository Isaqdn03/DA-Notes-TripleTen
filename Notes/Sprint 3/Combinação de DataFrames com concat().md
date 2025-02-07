
**2024-11-04 18:09**

**Sprint:** [[Sprint3]]

**Topic:** #transformcao-de-dados 

**Connections:** 

---
# **Combinação de DataFrames com concat()**

# Combinação de DataFrames com Pandas concat()

## Introdução ao Dataset
O exemplo utiliza um conjunto de dados de vendas de videogames contendo informações como nome do jogo, plataforma, ano de lançamento, gênero, distribuidora e vendas por região.

### Estrutura do DataFrame Original
```python
import pandas as pd

df = pd.read_csv('/datasets/vg_sales.csv')
print(df.head())
```

Saída:
```
                       name platform  year_of_release         genre publisher  \
0                Wii Sports      Wii           2006.0        Sports  Nintendo   
1         Super Mario Bros.      NES           1985.0      Platform  Nintendo   
2            Mario Kart Wii      Wii           2008.0        Racing  Nintendo   
3         Wii Sports Resort      Wii           2009.0        Sports  Nintendo   
4  Pokemon Red/Pokemon Blue       GB           1996.0  Role-Playing  Nintendo   

  developer  na_sales  eu_sales  jp_sales  critic_score  user_score  
0  Nintendo     41.36     28.96      3.77          76.0         8.0  
1       NaN     29.08      3.58      6.81           NaN         NaN  
2  Nintendo     15.68     12.76      3.79          82.0         8.3  
3  Nintendo     15.61     10.93      3.28          80.0         8.0  
4       NaN     11.27      8.89     10.22           NaN         NaN
```

## Estatísticas por Distribuidora

### Pontuação Média dos Críticos
```python
mean_score = df.groupby('publisher')['critic_score'].mean()
print(mean_score)
```

### Total de Vendas
```python
df['total_sales'] = df['na_sales'] + df['eu_sales'] + df['jp_sales']
num_sales = df.groupby('publisher')['total_sales'].sum()
print(num_sales)
```

## Uso do concat()

### Combinando Estatísticas(Combinando Series)
```python
df_concat = pd.concat([mean_score, num_sales], axis='columns')
print(df_concat)
```

**Características importantes:**
- Usa uma lista de objetos Series/DataFrame como entrada
- Necessita do parâmetro `axis='columns'` para combinar como colunas
- Mantém os nomes originais das colunas
- Preserva o índice comum ('publisher')

## Renomeação de Colunas

```python
df_concat.columns = ['avg_critic_score', 'total_sales']
print(df_concat)
```

**Observação:** É recomendado renomear colunas após agrupamento para melhor refletir seu processamento.

## Concatenação de DataFrames

### Por Linhas (Vertical)
```python
rpgs = df[df['genre'] == 'Role-Playing']
platformers = df[df['genre'] == 'Platform']
df_concat = pd.concat([rpgs, platformers])
print(df_concat[['name', 'genre']])
```

**Características:**
- Usa `axis='index'` (padrão) ou `axis=0`
- Requer mesmo número de colunas
- Mantém todos os dados originais

# Pontos-Chave
- `concat()` é versátil para combinar Series e DataFrames
- Pode concatenar tanto por linhas quanto por colunas
- Importante especificar o eixo (`axis`) corretamente
- Preserva índices e nomes de colunas originais
- Útil para combinar resultados de diferentes operações de groupby
- Permite renomeação de colunas após a concatenação

# Resumo
O pandas `concat()` é uma ferramenta poderosa para combinar dados, seja verticalmente (por linhas) ou horizontalmente (por colunas). É especialmente útil quando trabalhamos com resultados de agrupamentos e quando precisamos juntar diferentes conjuntos de dados que compartilham estrutura similar. A função mantém a integridade dos dados e oferece flexibilidade na organização dos resultados através do parâmetro `axis`.











**2025-02-10 20:10**

**Sprint:** [[Sprint6]]

**Topic:** #python-em-mais-detalhes 

**Connections:** 

---
# **Pandas - estatística descritiva**

**A estatística descritiva é uma ferramenta fundamental para compreender as características básicas dos dados em um DataFrame. Esta lição foca em quatro métricas essenciais:**

- **Valor máximo**
- **Valor mínimo**
- **Mediana**
- **Média**
## Métricas Estatísticas Básicas

### 1. Valor Máximo (max())
**Definição:** Representa o maior valor em um conjunto de dados.

```python
import pandas as pd

df = pd.read_csv('/datasets/music_log_processed.csv')
max_value = df['total_play'].max()
```

**Exemplo Prático:**
```python
# Encontrar a música mais longa
print(df[df['total_play'] == df['total_play'].max()])
```

*Aplicação:* Identificação de valores extremos e possíveis outliers.

### 2. Valor Mínimo (min())
**Definição:** Representa o menor valor em um conjunto de dados.

```python
df_drop_skip = df[df['total_play'] > 30]
min_value = df_drop_skip['total_play'].min()
```

**Observação:** Útil para identificar limites inferiores e filtrar dados irrelevantes.

### 3. Mediana (median())
**Definição:** Valor central que divide o conjunto de dados em duas partes iguais.

**[vizualizacao de uma mediana](https://practicum-content.s3.amazonaws.com/resources/12.8_1PT_1690267836_1702364722.png)**

> A mediana é menos sensível a valores extremos que a média.

#### Como calcular a mediana:

1. Para número ímpar de valores:
   - Exemplo: [3, 5, 6, 8, 9] → Mediana = 6

2. Para número par de valores:
   - Exemplo: [3, 5, 6, 8, 9, 12] → Mediana = (6+8)/2 = 7

```python
median_value = df['total_play'].median()
```

### 4. Média (mean())
**Definição:** Soma de todos os valores dividida pelo número total de observações.

```python
mean_value = df['total_play'].mean()
```

## Análise Comparativa das Medidas

### Tabela Comparativa
| Medida | Características | Uso Principal |
|--------|----------------|---------------|
| Máximo | Identifica extremos superiores | Detecção de outliers |
| Mínimo | Identifica extremos inferiores | Filtragem de dados |
| Mediana | Resistente a outliers | Valor típico central |
| Média | Sensível a outliers | Tendência central geral |

## Interpretação e Aplicações Práticas

### Identificação de Outliers
- **Definição:** Valores atípicos muito distantes da maioria dos dados
- **Detecção:** Comparação entre média e mediana
  - Se média ≈ mediana → Poucos outliers
  - Se média ≠ mediana → Presença significativa de outliers

### Exemplo com Dados Musicais
```python
pop_tracks = df[df['genre'] == 'pop']
pop_tracks = pop_tracks[pop_tracks['total_play'] > 30]

pop_mean = pop_tracks['total_play'].mean()
pop_median = pop_tracks['total_play'].median()
```

**Resultados típicos:**
- Média ≈ 186 segundos
- Mediana ≈ 198 segundos
- Máximo = 1.158 segundos (possível outlier)

## Pontos-Chave para Lembrar
- A mediana é mais robusta para dados com outliers
- Valores muito diferentes entre média e mediana indicam assimetria nos dados
- Filtrar dados (ex: remover músicas < 30s) pode melhorar a análise
- Sempre verificar valores extremos para possíveis erros ou casos especiais

# Resumo Geral
Esta lição forneceu ferramentas essenciais para análise estatística básica usando Pandas, focando em quatro métricas fundamentais. A compreensão dessas medidas permite:
3. Identificar valores atípicos
4. Entender a distribuição dos dados
5. Tomar decisões informadas sobre filtragem e limpeza
6. Extrair insights significativos dos dados

A combinação dessas métricas oferece uma visão abrangente da estrutura dos dados, permitindo análises mais robustas e confiáveis.












**2024-10-18 20:18**

**Sprint:** [[Sprint3]]

**Topic:** #Filtragem-de-Dados 

**Connections:** 

# **Substituição de valores com where()**
### Main Topics of this Lesson:

1. Uso do `where()` para Modificar Valores

## **1. Uso do `where()` para Modificar Valores**

### **Substituir Valores Específicos**

```python
import pandas as pd

df = pd.read_csv('/datasets/vg_sales.csv')

df['platform'] = df['platform'].where(df['platform'] != 'NES', 'Nintendo Entertainment System')

print(df.iloc[:, :2].head())
```

- **Condição Lógica:** `df['platform'] != 'NES` - Verifica se o valor não é 'NES'.
- **Substituição:** Se a condição for `False`, substitui o valor por 'Nintendo Entertainment System'.
### **Modificar Valores Baseados em Condições em Múltiplas Colunas** 

```python
import pandas as pd

df = pd.read_csv('/datasets/vg_sales.csv')

df[['na_sales', 'eu_sales']] = df[['na_sales', 'eu_sales']].where((df['na_sales'] > 0) | (df['eu_sales'] > 0), None)

print(df[['name', 'na_sales', 'eu_sales']])

```

- **Condição Lógica:** `(df['na_sales'] > 0) | (df['eu_sales'] > 0)` - Verifica se pelo menos uma das vendas é maior que zero.
- **Substituição:** Se a condição for `False`, substitui os valores por `None`.

---

## Resumo dos Parâmetros do `where()`

- **Condição Lógica:** Uma expressão booleana que determina quais valores devem ser substituídos.
- **Valor de Substituição:** O valor que será usado para substituir os valores onde a condição lógica é `False`.

## Active Recall

- **Pergunta:** Como substituir todos os valores 'NES' na coluna 'platform' por 'Nintendo Entertainment System' usando `where()`?
    
    - **Resposta:** Use `df['platform'] = df['platform'].where(df['platform'] != 'NES', 'Nintendo Entertainment System')`.
    
- **Pergunta:** Como substituir os valores de 'na_sales' e 'eu_sales' por `None` quando ambos forem zero ou menos que zero?
    
    - **Resposta:** Use `df[['na_sales', 'eu_sales']] = df[['na_sales', 'eu_sales']].where((df['na_sales'] > 0) | (df['eu_sales'] > 0), None)`.
    
- **Pergunta:** Como unir os gêneros menos representados ('Puzzle' e 'Strategy') na categoria 'Misc'?
    
    - **Resposta:** Use `genres = ['Puzzle', 'Strategy']; df['genre'] = df['genre'].where(~df['genre'].isin(genres), 'Misc')`.




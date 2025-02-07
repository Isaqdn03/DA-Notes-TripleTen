
**2024-12-09 11:42**

**Sprint:** [[Sprint4]]

**Topic:** #testes-de-hipóteses 

**Connections:** 

---
# **Hipótese sobre a igualdade das médias de duas populações**

# Comparação de Médias entre Populações Estatísticas

## Fundamentação Teórica

A simples comparação numérica entre médias de duas populações não é suficiente para determinar diferenças estatisticamente significativas. É necessário considerar:

- A variância das amostras
- O tamanho das amostras
- O nível de significância estatística

**Ponto-Chave:** Uma diferença aparente entre médias pode ser resultado do acaso, não representando uma diferença real entre as populações.

## Teste t de Student (scipy.stats.ttest_ind)

### Sintaxe e Parâmetros
```python
from scipy import stats
results = stats.ttest_ind(array1, array2, equal_var)
```

Parâmetros importantes:
- **array1, array2**: Vetores contendo as amostras
- **equal_var**: Booleano que indica se as variâncias são consideradas iguais
- **Retorno**: Objeto contendo o valor-p (results.pvalue)

## Exemplo 1: Análise de Gastos por Canal

```python
from scipy import stats as st
import numpy as np

sample_1 = [3071, 3636, 3454, 3151, 2185, 3259, 1727, 2263, 2015, 
            2582, 4815, 633, 3186, 887, 2028, 3589, 2564, 1422, 1785, 
            3180, 1770, 2716, 2546, 1848, 4644, 3134, 475, 2686, 
            1838, 3352]

sample_2 = [1211, 1228, 2157, 3699, 600, 1898, 1688, 1420, 5048, 3007, 
            509, 3777, 5583, 3949, 121, 1674, 4300, 1338, 3066, 
            3562, 1010, 2311, 462, 863, 2021, 528, 1849, 255, 
            1740, 2596]

alpha = 0.05
results = st.ttest_ind(sample_1, sample_2)

print('valor-p: ', results.pvalue)
```

Saída esperada:
```
valor-p:  0.1912450522572209
Não podemos rejeitar a hipótese nula
```

### Interpretação
- Valor-p = 0.1912 (19.12%)
- Como valor-p > alpha (0.05), não há evidência estatística suficiente para concluir que existe diferença significativa entre os canais

## Exemplo 2: Análise de Tempo de Permanência por Método de Login

```python
time_on_site_logpass = [368, 113, 328, 447, 1, 156, 335, 233, 
                       308, 181, 271, 239, 411, 293, 303, 
                       206, 196, 203, 311, 205, 297, 529, 
                       373, 217, 416, 206, 1, 128, 16, 214]

time_on_site_social  = [451, 182, 469, 546, 396, 630, 206, 
                       130, 45, 569, 434, 321, 374, 149, 
                       721, 350, 347, 446, 406, 365, 203, 
                       405, 631, 545, 584, 248, 171, 309, 
                       338, 505]

results = st.ttest_ind(time_on_site_logpass, time_on_site_social)
```

Saída esperada:
```
valor-p: 0.0010501061456827461
Rejeitamos a hipótese nula
```

### Interpretação
- Valor-p = 0.00105 (0.105%)
- Como valor-p < alpha (0.05), há evidência estatística significativa de diferença entre os grupos

## Exemplo 3: Análise Sazonal de Profundidade de Visitas

```python
pages_per_session_autumn = [7.1, 7.3, 9.8, 7.3, 6.4, 10.5, 8.7, 
                          17.5, 3.3, 15.5, 16.2, 0.4, 8.3, 
                          8.1, 3.0, 6.1, 4.4, 18.8, 14.7, 16.4, 
                          13.6, 4.4, 7.4, 12.4, 3.9, 13.6, 
                          8.8, 8.1, 13.6, 12.2]

pages_per_session_summer = [12.1, 24.3, 6.4, 19.9, 19.7, 12.5, 17.6, 
                          5.0, 22.4, 13.5, 10.8, 23.4, 9.4, 3.7, 
                          2.5, 19.8, 4.8, 29.0, 1.7, 28.6, 16.7, 
                          14.2, 10.6, 18.2, 14.7, 23.8, 15.9, 16.2, 
                          12.1, 14.5]

results = st.ttest_ind(pages_per_session_autumn, 
                      pages_per_session_summer, 
                      equal_var=False)
```

Saída esperada:
```
valor-p: 0.002200163165401993
Rejeitamos a hipótese nula
```

### Interpretação
- Valor-p = 0.0022 (0.22%)
- Como valor-p < alpha (0.05), há evidência estatística de diferença sazonal no comportamento dos usuários

# Pontos-Chave Finais

1. **Interpretação do valor-p:**
   - valor-p < alpha: Rejeitamos a hipótese nula (há diferença significativa)
   - valor-p > alpha: Não rejeitamos a hipótese nula (não há evidência suficiente)

2. **Considerações práticas:**
   - Sempre definir o nível de significância (alpha) antes do teste
   - Avaliar a premissa de variâncias iguais (equal_var)
   - Interpretar os resultados no contexto do problema

3. **Importância da análise estatística:**
   - Evita conclusões baseadas apenas em diferenças numéricas
   - Fornece fundamentação científica para tomada de decisões
   - Permite identificar padrões significativos nos dados










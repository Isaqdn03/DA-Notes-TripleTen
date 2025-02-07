
**2024-12-06 18:33**

**Sprint:** [[Sprint4]]

**Topic:** #testes-de-hipóteses 

**Connections:** 

---
# **Testes de hipóteses em Python. Valores-p**

# Testes de Hipóteses em Python e Valores-p

## Conceitos Fundamentais

### Valor-p
- Representa a probabilidade de obter um resultado tão extremo quanto o observado, assumindo que a hipótese nula está correta
- Expresso como porcentagem
- Limiares convencionais:
  - > 10%: Não rejeitar a hipótese nula
  - 5%: Limiar comum para rejeição
  - 1%: Limiar mais rigoroso

### Distribuição de Student (t)
- Usada para amostras pequenas (20-30 valores)
- Semelhante à distribuição normal, mas com caudas mais pesadas
- Características:
  - Forma de sino
  - Adaptada para variâncias desconhecidas
  - Considera graus de liberdade (k)

**Ponto-Chave:** À medida que o número de graus de liberdade aumenta, a distribuição t se aproxima de uma distribuição normal.

## Implementação em Python

### Função ttest_1samp
```python
from scipy import stats as st
import numpy as np
import pandas as pd

# Sintaxe básica
st.ttest_1samp(array, popmean)
```

**Parâmetros:**
- `array`: vetor contendo a amostra
- `popmean`: média proposta para teste

### Exemplo Prático: Análise de Tempo no Site
```python
from scipy import stats as st
import numpy as np
import pandas as pd

time_on_site = pd.read_csv('user_time.csv')
interested_value = 120  # tempo em minutos
alpha = .05  # significância estatística

results = st.ttest_1samp(time_on_site, interested_value)

print('valor-p: ', results.pvalue)

if (results.pvalue < alpha):
    print("Rejeitamos a hipótese nula")
else:
    print("Não podemos rejeitar a hipótese nula")
```

Saída esperada:
```
valor-p:  [0.27702871]
Não podemos rejeitar a hipótese nula
```

### Caso de Estudo: Análise de Scooters
```python
from scipy import stats as st
import pandas as pd

scooters = pd.Series([15, 31, 10, 21, 21, 32, 30, 25, 21,
# ... outros valores ...
17, 44, 40, 33,])

optimal_value = 30
alpha = 0.05

results = st.ttest_1samp(scooters, optimal_value)

print('valor-p: ', results.pvalue)

if results.pvalue < alpha:
    print('Rejeitamos a hipótese nula')
else:
    print("Não podemos rejeitar a hipótese nula")
```

Saída esperada:
```
valor-p:  0.00033528259973700795
Rejeitamos a hipótese nula
```

## Pontos-Chave para Interpretação

1. **Interpretação dos Resultados:**
   - Nunca podemos "provar" uma hipótese
   - Podemos apenas fazer suposições com base em probabilidades
   - Um valor-p alto não prova a hipótese nula, apenas não fornece evidências para rejeitá-la

2. **Considerações Práticas:**
   - Use testes bilaterais quando a direção da diferença não importa
   - Escolha o nível de significância (α) antes de realizar o teste
   - Considere o contexto do problema ao interpretar os resultados

# Resumo
- Os testes de hipóteses em Python são realizados principalmente através da função `scipy.stats.ttest_1samp`
- O valor-p é fundamental para a tomada de decisão estatística
- A distribuição t de Student é usada para amostras pequenas
- A interpretação dos resultados deve ser feita com cautela, considerando sempre o contexto do problema
- É importante definir o nível de significância antes de realizar o teste










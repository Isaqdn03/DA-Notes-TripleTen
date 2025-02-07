
**2024-12-09 13:48**

**Sprint:** [[Sprint4]]

**Topic:** #testes-de-hipóteses 

**Connections:** 

---
# **Hipótese sobre a igualdade das médias de amostras pareadas**
# Teste de Hipótese para Amostras Pareadas

## Conceitos Fundamentais

### Amostras Pareadas
Uma amostra pareada ocorre quando medimos a mesma variável duas vezes para cada unidade de observação (por exemplo, mesmo cliente antes e depois de uma mudança). Isso permite controlar a variabilidade entre diferentes unidades de observação.

### Teste t Pareado
O teste t pareado é implementado em Python usando a função `scipy.stats.ttest_rel()`. Este teste é usado para verificar se existe diferença significativa entre as médias de duas amostras dependentes.

**Pontos-Chave:**
- Requer amostras do mesmo tamanho
- Utiliza nível de significância (α) para tomada de decisão
- Compara o valor-p com α para decidir sobre a hipótese nula

## Caso Prático: Análise de Peso de Pacotes

### Código de Implementação
```python
from scipy import stats as st
import numpy as np

before = [157, 114, 152, 355, 155, 513, 299, 268, 164, 320, 
          192, 262, 506, 240, 364, 179, 246, 427, 187, 431, 
          320, 193, 313, 347, 312, 92, 177, 225, 242, 312]

after = [282, 220, 162, 226, 296, 479, 248, 322, 298, 418, 
         552, 246, 251, 404, 368, 484, 358, 264, 359, 410, 
         382, 350, 406, 416, 438, 364, 283, 314, 420, 218]

alpha = 0.05
results = st.ttest_rel(before, after)

print('valor-p: ', results.pvalue)
```

Saída:
```
valor-p:  0.005825972457958989
Rejeitamos a hipótese nula
```

### Interpretação dos Resultados
- Valor-p (0.00583) < α (0.05)
- Conclusão: Existe evidência estatística suficiente para afirmar que houve mudança significativa nos pesos dos pacotes após a alteração do método de cálculo.

## Exemplo: Tempo de Usuários em Site

### Código e Análise
```python
time_before = [1732, 1301, 1540, 2247, 1632, 1550, 754, 1946, 1889, 
               2748, 1349, 1648, 1665, 2416, 1470, 1681, 1868, 1629, 
               1271, 1633, 2131, 942, 1599, 1127, 2200, 661, 1207, 
               1737, 2410, 1486]

time_after = [955, 2577, 360, 139, 1618, 990, 644, 1796, 1487, 949, 472, 
              1906, 1758, 1258, 2554, 612, 309, 1864, 1294, 1487, 1164, 1559, 
              491, 2286, 1270, 2069, 1553, 1629, 1704, 1623]

results = st.ttest_rel(time_before, time_after)
```

Saída:
```
valor-p: 0.0751397944405015
Não podemos rejeitar a hipótese nula
```

### Interpretação
- Valor-p (0.0751) > α (0.05)
- Conclusão: Não há evidência estatística suficiente para afirmar que o tempo gasto na área de conta pessoal mudou após o redesign.

## Exemplo: Análise de Uso de Balas em Jogo Online

### Código e Análise
```python
bullets_before = [821, 1164, 598, 854, 455, 1220, 161, 1400, 479, 215, 
                 564, 159, 920, 173, 276, 444, 273, 711, 291, 880, 
                 892, 712, 16, 476, 498, 9, 1251, 938, 389, 513]

bullets_after = [904, 220, 676, 459, 299, 659, 1698, 1120, 514, 1086, 1499, 
                1262, 829, 476, 1149, 996, 1247, 1117, 1324, 532, 1458, 898, 
                1837, 455, 1667, 898, 474, 558, 639, 1012]

print('média antes:', pd.Series(bullets_before).mean())
print('média depois:', pd.Series(bullets_after).mean())
results = st.ttest_rel(bullets_before, bullets_after)
```

Saída:
```
média antes: 591.7333333333333
média depois: 932.0666666666667
valor-p: 0.005394751910405561
Rejeitamos a hipótese nula
```

### Interpretação
- Aumento significativo na média de balas usadas
- Teste unilateral utilizado devido à hipótese específica de "mais" balas
- Valor-p/2 < α indica rejeição da hipótese nula

# Resumo

**Pontos Principais:**
1. O teste t pareado é útil para comparar médias de amostras dependentes
2. A escolha entre teste unilateral e bilateral depende da hipótese sendo testada
3. A interpretação dos resultados sempre considera o valor-p em relação ao α estabelecido
4. A rejeição da hipótese nula indica mudança estatisticamente significativa
5. A não rejeição da hipótese nula não prova que não houve mudança, apenas indica falta de evidência estatística suficiente










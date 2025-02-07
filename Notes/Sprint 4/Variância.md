
**2024-11-15 08:57**

**Sprint:** [[Sprint4]]

**Topic:** #Estatística-descritiva 

**Connections:** 

---
# **Variância**

# Análise Estatística: Variância e Covariância

## Variância (σ²)

### Conceito Fundamental
A variância é uma medida estatística que indica o grau de espalhamento dos dados em relação à média. Ela é calculada elevando ao quadrado as distâncias entre cada valor e a média do conjunto.

### Processo de Cálculo
1. Calcular a média do conjunto
2. Subtrair a média de cada valor
3. Elevar as diferenças ao quadrado
4. Calcular a média das diferenças quadradas

#### Exemplo Numérico
Para o conjunto [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10] com média = 5:

1. Diferenças em relação à média:
   - 0 - 5 = -5
   - 1 - 5 = -4
   - ...
   - 10 - 5 = 5

2. Quadrado das diferenças:
   - (-5)² = 25
   - (-4)² = 16
   - ...
   - (5)² = 25

### Fórmula Matemática
σ² = Σ(xᵢ - μ)² / n

Onde:
- σ² = variância
- xᵢ = valor individual
- μ = média
- n = número de valores

**Pontos-Chave sobre Variância:**
- Sempre é um valor positivo ou zero
- Variância zero indica que todos os valores são idênticos
- Quanto maior a variância, mais dispersos estão os dados
- É a base para o cálculo do desvio padrão

## Covariância

### Conceito Fundamental
A covariância mede como duas variáveis se relacionam, indicando se elas tendem a aumentar ou diminuir juntas.

### Fórmula Matemática
Covariância = Σ(xᵢ - x̄)(yᵢ - ȳ) / n

Onde:
- xᵢ, yᵢ = valores das variáveis
- x̄, ȳ = médias das variáveis
- n = número de pares de valores

**Interpretação da Covariância:**
- Valor positivo: variáveis tendem a aumentar juntas
- Valor negativo: quando uma aumenta, a outra tende a diminuir
- Valor zero: não há relação linear entre as variáveis

## Implementação em Python

### Cálculo da Variância
```python
import numpy as np

x = [1, 2, 3, 4, 5, 6]  # conjunto de dados
variance = np.var(x)
print(variance)
```

Saída esperada:
```
2.9166666666666665
```

### Cálculo da Covariância
```python
import numpy as np

x = [1, 2, 3, 4, 5, 6]  # conjunto de dados 1
y = [41, 62, 89, 96, 108, 115]  # conjunto de dados 2

covariance_matrix = np.cov(x,y)  # calculando a matriz de covariância
covariance = covariance_matrix[0][1]  # extraindo a covariância como um valor
print(covariance)
```

Saída esperada:
```
51.5
```

**Pontos-Chave sobre a Implementação:**
- NumPy fornece funções otimizadas para cálculos estatísticos
- `np.var()` calcula a variância diretamente
- `np.cov()` retorna uma matriz de covariância 2x2
- O valor da covariância está na posição [0][1] da matriz

# Resumo
- A variância mede a dispersão dos dados em relação à média
- A covariância indica como duas variáveis se relacionam linearmente
- Python com NumPy oferece ferramentas eficientes para cálculos estatísticos
- Valores quadrados na variância eliminam diferenças negativas
- A interpretação da covariância depende do sinal (positivo ou negativo) e da magnitude do valor calculado










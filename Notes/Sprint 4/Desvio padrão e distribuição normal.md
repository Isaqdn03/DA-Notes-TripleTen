
**2024-11-15 10:09**

**Sprint:** [[Sprint4]]

**Topic:** #Estatística-descritiva 

**Connections:** 

---
# **Desvio padrão e distribuição normal**

# Desvio Padrão e Distribuição Normal

## Introdução ao Desvio Padrão

O desvio padrão (σ) é uma medida de dispersão que nos permite entender quanto os valores de um conjunto de dados se desviam da média. Diferente da variância, o desvio padrão:
- Utiliza as mesmas unidades dos dados originais
- É obtido através da raiz quadrada da variância
- É representado pelo símbolo σ (sigma minúsculo)

A fórmula do desvio padrão é:
σ = √(Σ(xi - μ)²/n)

### Visualização com Pandas

```python
import pandas as pd

s = pd.Series([1, 2, 3, 4, 5, 6])
s.describe()
```

Saída esperada:
```
count    6.000000
mean     3.500000
std      1.870829
min      1.000000
25%      2.250000
50%      3.500000
75%      4.750000
max      6.000000
dtype: float64
```

### Cálculo com NumPy
```python
import numpy as np

x = [1, 2, 3, 4, 5, 6]
standard_deviation = np.std(x)
print(standard_deviation)
```

Saída esperada:
```
1.707825127659933
```

### Cálculo a partir da Variância
```python
import numpy as np

variance = 3.5
standard_deviation = np.sqrt(variance)
print(standard_deviation)
```

Saída esperada:
```
1.8708286933869707
```

## Distribuição Normal (Gaussiana)

A distribuição normal é caracterizada por:
- Forma simétrica de sino
- Definida por dois parâmetros: média (μ) e desvio padrão (σ)
- Maior frequência de dados próximos à média

### Características Principais
- **Simetria**: A curva é simétrica em relação à média
- **Parâmetros**:
  - Média (μ): Define o centro da distribuição
  - Desvio Padrão (σ): Define a dispersão dos dados

### Regra dos Três Sigmas
Esta regra estabelece que:
- 99,7% dos valores estão no intervalo (μ - 3σ, μ + 3σ)
- Valores fora deste intervalo são considerados **atípicos**
- É uma ferramenta importante para detecção de outliers

**Pontos-Chave:**
- O desvio padrão é mais prático que a variância por usar as mesmas unidades dos dados originais
- A distribuição normal é fundamental em estatística e análise de dados
- A regra dos três sigmas ajuda a identificar valores atípicos
- Valores atípicos podem indicar erros de medição ou informações importantes sobre os dados

## Compreensao
Para responder sobre o que representa "desvio padrão × 3 + média", vou explicar passo a passo:

Em estatística, esta é uma medida importante conhecida como "regra empírica" ou "regra dos três sigmas". Quando somamos três desvios padrão (σ) à média (μ), obtemos um limite superior que nos diz que:

1. Em uma distribuição normal:
- Aproximadamente 99.7% dos dados estão entre μ - 3σ e μ + 3σ
- O valor μ + 3σ marca o limite superior deste intervalo
- Apenas cerca de 0.15% dos valores estarão acima de μ + 3σ

Por exemplo:
Se uma série de dados tem:
- Média (μ) = 100
- Desvio padrão (σ) = 10

Então μ + 3σ = 100 + (3 × 10) = 130

Isto significa que 99.85% dos valores estarão abaixo de 130 neste caso.

Esta medida é frequentemente usada para:
- Detectar outliers (valores atípicos)
- Estabelecer limites de controle em processos
- Definir intervalos de confiança
# Resumo
O desvio padrão é uma medida fundamental de dispersão que, junto com a distribuição normal, forma a base para muitas análises estatísticas. A regra dos três sigmas nos permite identificar valores atípicos e estabelecer intervalos de confiança para nossos dados. Python oferece várias ferramentas através das bibliotecas NumPy e Pandas para calcular estas métricas importantes.










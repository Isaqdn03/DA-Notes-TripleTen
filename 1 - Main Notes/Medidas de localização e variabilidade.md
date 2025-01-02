
**2024-11-13 18:08**

**Sprint:** [[Sprint4]]

**Topic:** #Estatística-descritiva 

**Connections:** 

---
# **Medidas de localização e variabilidade**

# Medidas de Localização e Variabilidade em Estatística

## 1. Medidas de Localização

### 1.1 Conceitos Básicos
- Medidas de localização ou posição são valores que descrevem dados numéricos
- Principais medidas: média e mediana
- Cada medida tem suas próprias vantagens e casos de uso

### 1.2 Média
- Considerada uma medida algébrica de localização
- Requer todos os valores do conjunto de dados
- Cálculo: soma de todos os valores dividida pela contagem total

### 1.3 Mediana
- Medida de localização estrutural
- Representa o valor no meio de uma distribuição
- Menos sensível a mudanças nos valores extremos

### 1.4 Exemplo Prático em Python
```python
data = pd.Series([0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
print('A média é', data.mean())
print('A mediana é', data.median())
```
Saída esperada:
```
A média é 5.0
A mediana é 5.0
```

### 1.5 Exemplo de Sensibilidade a Mudanças
```python
data_new = pd.Series([0, 0.1, 0.2, 0.3, 0.4, 5, 60, 70, 80, 90, 100])
print('A nova média é', data_new.mean())
print('A nova mediana é', data_new.median())
```
Saída esperada:
```
A nova média é 36.90909090909091
A nova mediana é 5.0
```

**Pontos-Chave:**
- A média é sensível a valores extremos
- A mediana permanece estável mesmo com mudanças significativas nos dados
- A média é afetada por valores atípicos (outliers)

## 2. Medidas de Variabilidade

### 2.1 Quartis
- Primeiro Quartil (Q1): percentil 25
- Segundo Quartil (Q2): percentil 50 (mediana)
- Terceiro Quartil (Q3): percentil 75

### 2.2 Diagrama de Caixa (Boxplot)
- Representa visualmente a distribuição dos dados
- Elementos do boxplot:
  - Limite inferior (bigode): valor mínimo
  - Q1: primeiro quartil
  - Q2: mediana
  - Q3: terceiro quartil
  - Limite superior (bigode): valor máximo
  
![[Pasted image 20241113195752.png]]
### 2.3 Implementação de Boxplot em Python

![[Pasted image 20241113195839.png]]

```python
import seaborn as sns
import pandas as pd

dataset = pd.Series([1, 1, 2, 2, 2, 3, 3, 3, 3, 4, 5, 5, 6, 6])
sns.boxplot(dataset)
```

**Pontos-Chave:**
- IQR (Intervalo Interquartil): distância entre Q1 e Q3
- Representa os 50% centrais dos dados
- Útil para identificar outliers e dispersão dos dados

# Resumo
- Medidas de localização (média e mediana) fornecem valores representativos dos dados
- A média é sensível a outliers, enquanto a mediana é mais robusta
- Quartis e boxplots ajudam a visualizar a dispersão dos dados
- Python oferece ferramentas eficientes (pandas e seaborn) para análise estatística
- A escolha entre média e mediana depende do contexto e da presença de valores atípicos

# Exemplo de tarefa

1. Encontrar a média do conjunto de dados e armazená-la na variável `mean_value` usando o método apropriado.
2. Calcular a distância entre cada valor e a média e armazenar o valor resultante na variável `spacing_all`. Nesta etapa, use operações aritméticas simples com Series da Pandas. Isso vai resultar em operações elemento por elemento, o que significa que uma operação será realizada em cada elemento de um objeto Series, produzindo outro objeto Series.
3. Em seguida, calcular a distância média e armazená-la na variável `spacing_all_mean`.
4. Imprimir a variável `spacial_all_mean`.

```python
import pandas as pd

data = pd.Series([0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10])

mean_value = data.mean()  # encontre o valor médio em um conjunto
spacing_all = data - mean_value # para cada elemento no conjunto de dados, encontre sua distância da média
spacing_all_mean = spacing_all.mean()  # calcule a distância média

print(spacing_all_mean)
```
Resultado:
```
0.0
```

1. Primeiro, criamos uma Series do Pandas com valores de 0 a 10: `[0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]`
2. Calculamos a média (`mean_value`):
    - ==A média é a soma de todos os valores dividida pelo número de valores==
    - Neste caso: (0+1+2+3+4+5+6+7+8+9+10) ÷ 11 = 5
3. Calculamos `spacing_all` que é a distância de cada valor até a média:
    - Para cada número, subtraímos 5 (a média)
    - Isso resulta em: `[-5, -4, -3, -2, -1, 0, 1, 2, 3, 4, 5]`
    - Valores menores que a média têm distância negativa
    - Valores maiores que a média têm distância positiva
    - O valor igual à média (5) tem distância 0
4. Por fim, calculamos `spacing_all_mean`, que é a média das distâncias:
    - Somamos todas as distâncias: (-5 + -4 + -3 + -2 + -1 + 0 + 1 + 2 + 3 + 4 + 5) = 0
    - Dividimos pelo número de valores (11)
    - Resultado final = 0

O resultado é 0 porque:

- As distâncias negativas e positivas se cancelam
- Para qualquer conjunto de dados com distribuição simétrica em torno da média, a média das distâncias até a média sempre será zero
- Isso acontece porque há sempre valores igualmente distantes acima e abaixo da média








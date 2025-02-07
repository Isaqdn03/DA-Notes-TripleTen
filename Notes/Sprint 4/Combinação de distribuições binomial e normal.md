
**2024-11-22 12:43**

**Sprint:** [[Sprint4]]
 
**Topic:** #teoria-de-probabilidade 

**Connections:** 

---
# **Combinação de distribuições binomial e normal**

# Combinação de Distribuições Binomial e Normal

## Conceitos Fundamentais

### Valor Esperado
- Representa o valor "típico" de uma variável aleatória
- Calculado através da média ponderada de valores possíveis
- Requer múltiplas repetições do experimento para aproximação

### Experimento Binomial
- Consiste em n tentativas de um experimento simples (Bernoulli)
- Possui apenas dois resultados possíveis
- Pode ser aproximado pela distribuição normal com n ≥ 50

## Fórmulas Importantes

### Valor Esperado em Distribuição Binomial
- E(X) = n · p
  - n = número de tentativas
  - p = probabilidade de sucesso

### Variância em Distribuição Binomial
- Var(X) = n · p · (1 - p)
- Desvio padrão = √(n · p · (1 - p))

## Exemplos Práticos

### Exemplo 1: Engenheiro de Software
- n = 50 blocos de código por dia
- p = 0.2 (20% de sucesso)
- Valor esperado = 50 · 0.2 = 10 blocos perfeitos
- Variância = 50 · 0.2 · 0.8 = 8
- Desvio padrão = √8 = 2√2
- Intervalo esperado: 2 a 18 blocos perfeitos (99% dos casos)

### Exemplo 2: Análise de Cliques em Anúncios

```python
from scipy import stats as st
import math as mt

# Definindo valores dos parâmetros
binom_n = 5000
binom_p = 0.15
clicks = 715

# Calculando o valor esperado de sucessos e sigma
mu = binom_n * binom_p
sigma = mt.sqrt(binom_n * binom_p * (1 - binom_p))

# Calculando a probabilidade de conseguir 715 cliques ou menos
p_clicks = st.norm(mu, sigma).cdf(clicks)
print(p_clicks)
```

**Explicação do código:**
1. Importa as bibliotecas necessárias (scipy.stats e math)
2. Define parâmetros do experimento (n=5000, p=0.15)
3. Calcula média (mu) e desvio padrão (sigma)
4. Usa norm.cdf() para calcular probabilidade acumulada

**Saída esperada:**
```
0.08284191945650154
```
*Interpretação: Aproximadamente 8.3% de chance de obter 715 cliques ou menos*

### Exemplo 3: Análise de Newsletter

```python
from scipy import stats as st
import math as mt

binom_n = 23000
binom_p = 0.4

threshold = 9000

mu = binom_n * binom_p
sigma = mt.sqrt(binom_n * binom_p * (1 - binom_p))

p_threshold = 1 - st.norm(mu, sigma).cdf(threshold)
print(p_threshold)
```

**Explicação do código:**
1. Define parâmetros (n=23000 pessoas, p=0.4 taxa de abertura)
2. Estabelece limite desejado (threshold=9000)
3. Calcula média e desvio padrão
4. Usa 1 - norm.cdf() para calcular probabilidade de exceder o limite

**Saída esperada:**
```
0.9964477890716447
```
*Interpretação: Aproximadamente 99.64% de chance de alcançar mais de 9000 aberturas*

## Pontos-Chave
- A distribuição binomial pode ser aproximada pela normal quando n ≥ 50
- A aproximação normal facilita cálculos de probabilidade
- Valor esperado e variância são fundamentais para análise
- norm.cdf() é usado para calcular probabilidades acumuladas
- A interpretação prática dos resultados é essencial para tomada de decisões

# Resumo
A combinação das distribuições binomial e normal permite análises estatísticas mais simples em experimentos com grande número de tentativas. As ferramentas matemáticas e computacionais disponíveis (como a biblioteca scipy) facilitam esses cálculos, permitindo tomadas de decisão baseadas em dados em diversos contextos práticos, desde desenvolvimento de software até marketing digital.











**2024-11-22 10:54**

**Sprint:** [[Sprint4]]

**Topic:** #teoria-de-probabilidade 

**Connections:** 

---
# **Como trabalhar com uma distribuição normal**
# Distribuição Normal: Conceitos e Aplicações em Python

## Introdução à Distribuição Normal
A distribuição normal, também conhecida como curva em forma de sino, é uma das distribuições estatísticas mais importantes e comuns. Ela pode ser aplicada em diversos contextos, como:
- Altura de uma população
- Taxas de falha de equipamentos
- Pontuações em testes
- Medidas biológicas

## Parâmetros Fundamentais

### Notação e Parâmetros
A distribuição normal é representada como:
```
X ∼ N(μ, σ²)
```
Onde:
- μ (mi) = média da distribuição
- σ² (sigma ao quadrado) = variância
- σ = desvio padrão

### Regra dos 3 Sigmas
**Distribuição dos dados:**
- 68% dos dados estão dentro de ±1σ da média
- 95% dos dados estão dentro de ±2σ da média
- 99,7% dos dados estão dentro de ±3σ da média

## Cálculos de Probabilidade com Python

### Utilizando a Biblioteca SciPy
```python
from scipy import stats as st

# Criando distribuição normal (média=5000, desvio padrão=1500)
data = st.norm(5000, 1500)

# Calculando probabilidade para valor específico
desired_cost = 4000
probability = data.cdf(desired_cost)

print(probability)
```
**Saída esperada:**
```
0.2524925375469229
```

### Cálculo de Quantis
```python
from scipy import stats as st

data = st.norm(5000, 1500)
target_level = 0.1

# Encontrando valor para determinado percentil
cost = data.ppf(target_level)

print(cost)
```
**Saída esperada:**
```
3077.6726516830995
```

## Métodos Principais do SciPy.stats

### Tabela de Métodos
| Método | Função | Uso |
|--------|---------|-----|
| norm.cdf() | Função de distribuição acumulada | Calcula probabilidade até um valor |
| norm.ppf() | Função quantil | Encontra valor para uma probabilidade dada |

### Exemplo Prático de Uso
Para calcular a probabilidade entre dois valores (por exemplo, entre 900 e 1100 pontos em uma prova com média 1000 e desvio padrão 100):

```python
from scipy import stats as st
distribuicao = st.norm(1000, 100)
probabilidade = distribuicao.cdf(1100) - distribuicao.cdf(900)
```

## Pontos-Chave
- A distribuição normal é simétrica em torno da média
- O desvio padrão determina a dispersão dos dados
- Maior σ significa maior dispersão dos dados
- A biblioteca SciPy fornece ferramentas poderosas para cálculos estatísticos
- As funções cdf() e ppf() são complementares para análise de probabilidades

# Tarefas
# Tarefa 1: Análise de Visitantes do Site

## Contexto
- Média (μ) = 100.500 visitantes
- Desvio padrão (σ) = 3.500 visitantes
- Queremos probabilidades para:
  1. Menos de 92.000 visitantes
  2. Mais de 111.000 visitantes

## Solução Explicada
```python
from scipy import stats as st
mu = 100500
sigma = 3500
more_threshold = 111000
fewer_threshold = 92000

# Para mais de 111.000 visitantes
p_more_visitors = 1 - st.norm(mu, sigma).cdf(more_threshold)

# Para menos de 92.000 visitantes
p_fewer_visitors = st.norm(mu, sigma).cdf(fewer_threshold)
```

### Explicação dos Cálculos:
1. Para "mais de 111.000":
   - Usamos `1 - cdf(111000)` porque cdf nos dá a probabilidade até o valor
   - Resultado ≈ 0.135% (muito improvável)

2. Para "menos de 92.000":
   - Usamos diretamente `cdf(92000)`
   - Resultado ≈ 0.758% (também improvável)

# Tarefa 2: Estoque de Jogos de Xadrez

## Contexto
- Média (μ) = 420 unidades
- Desvio padrão (σ) = 65 unidades
- Objetivo: 90% de certeza de ter estoque suficiente

## Solução Explicada
```python
mu = 420
sigma = 65
prob = 0.9
n_shipment = st.norm(mu, sigma).ppf(1 - prob)
```

### Explicação do Cálculo:
- Usamos `ppf(1 - 0.9)` porque queremos o valor que deixa 90% dos casos acima
- Resultado = 336 unidades
- Interpretação: Com 336 unidades em estoque, há 90% de chance de atender toda a demanda

# Tarefa 3: Preço de Entrega Rápida

## Contexto
- Média dos pedidos (μ) = $24
- Desvio padrão (σ) = $3.20
- Objetivo: Preço de entrega menor que o pedido em 75% dos casos

## Solução Explicada
```python
mu = 24
sigma = 3.2
threshold = 0.75
max_delivery_price = st.norm(mu, sigma).ppf(1 - threshold)
```

### Explicação do Cálculo:
- Usamos `ppf(1 - 0.75)` para encontrar o valor que deixa 75% dos pedidos acima
- Resultado ≈ $21.84
- Interpretação: Se o preço da entrega for $21.84, em 75% dos casos será menor que o valor do pedido

## Pontos-Chave para Todas as Tarefas
1. **Uso do CDF (Cumulative Distribution Function)**:
   - Calcula probabilidade até um valor
   - Útil para "menos que" ou "até"

2. **Uso do PPF (Percent Point Function)**:
   - Encontra valor para uma probabilidade dada
   - Útil para encontrar limiares

3. **Interpretação Prática**:
   - Resultados em probabilidades (Tarefas 1)
   - Resultados em valores concretos (Tarefas 2 e 3)

Estas tarefas demonstram aplicações práticas da distribuição normal em cenários reais de negócios, desde previsão de tráfego até decisões de precificação.
# Resumo
A distribuição normal é uma ferramenta estatística fundamental que pode ser facilmente manipulada usando Python e a biblioteca SciPy. Através dos métodos norm.cdf() e norm.ppf(), podemos calcular probabilidades e encontrar valores específicos em uma distribuição normal. A regra dos 3 sigmas nos ajuda a entender rapidamente como os dados estão distribuídos em torno da média.











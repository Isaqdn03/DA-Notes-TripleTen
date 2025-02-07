
**2024-11-22 08:41**

**Sprint:** [[Sprint4]]

**Topic:** #teoria-de-probabilidade 

**Connections:** 

---
# **A ideia de distribuição**

# Variáveis Aleatórias e Distribuições de Probabilidade

## Variáveis Aleatórias
Uma variável aleatória é aquela que assume valores não previsíveis com 100% de certeza.

### Características Principais
- Assume valores aleatórios
- Pode ser definida numericamente
- Pode ser discreta ou contínua

**Exemplo:**
- X = altura da próxima pessoa que passar pela porta
- Y = número de compras em uma loja online

**Pontos-Chave:**
- Impossibilidade de previsão exata
- Necessidade de definição numérica
- Possibilidade de mapeamento de resultados qualitativos para quantitativos

## Tipos de Distribuições de Probabilidade

### Tabela Comparativa
| Tipo | Descrição | Exemplo |
|------|-----------|---------|
| Binomial | Distribuição discreta de sucessos em tentativas fixas | Conversão de vendas (sucesso/fracasso) |
| Uniforme | Distribuição contínua com probabilidades iguais | Lançamento de dados |
| Normal | Distribuição agrupada em torno da média | Notas de exames |

**Pontos-Chave:**
- Distribuição normal é mais comum em fenômenos naturais
- 55% dos resultados concentram-se na média em uma distribuição normal
- Valores extremos são menos frequentes

## Implementação em Python com NumPy

### Criação Básica de Arrays
```python
import numpy as np

data = np.array([1, 3, 5, 7, 11, 13, 17, 19, 23, 317])
```

**Saída esperada ao acessar elementos:**
```
O primeiro elemento: 1
O último elemento: 317
Todos os elementos, exceto o primeiro e o último: [ 3  5  7 11 13 17 19 23]
```

### Geração de Números Aleatórios com Distribuição Normal
```python
import numpy as np

mean = 15  # média
std_dev = 5  # desvio padrão
data = np.random.normal(mean, std_dev, size = 20)
```

**Saída esperada:**
```
[10.62, 7.87, 18.14, 11.91, 22.47, ...]  # valores variam por serem aleatórios
```

## Exercícios Práticos

### Análise de Resultados de Exames
```python
import numpy as np

exam_results = np.array([
    42, 56, 59, 76, 43, 34, 62, 51, 50, 65,
    66, 50, 46, 5, 79, 99, 51, 26, 35, 8,
    34, 47, 64, 58, 61, 12, 30, 63, 20, 68
])

summarized_data = {'excellent': 0, 'good': 0, 'average': 0, 'passable': 0, 'failed': 0}

for score in exam_results:
    if score >= 90:
        summarized_data['excellent'] += 1
    elif score >= 70:
        summarized_data['good'] += 1
    elif score >= 50:
        summarized_data['average'] += 1
    elif score >= 20:
        summarized_data['passable'] += 1
    else:
        summarized_data['failed'] += 1
```

**Saída esperada:**
```
excellent - 1
good - 2
average - 14
passable - 10
failed - 3
```

**Pontos-Chave do Exercício:**
- Classificação em 5 níveis de desempenho
- Uso de dicionário para contagem
- Implementação de lógica condicional

# Resumo
- Variáveis aleatórias são fundamentais para a compreensão de eventos probabilísticos
- Distribuições de probabilidade podem ser discretas ou contínuas
- NumPy oferece ferramentas poderosas para trabalhar com distribuições
- A implementação prática permite análise de dados reais
- A distribuição normal é especialmente importante em análises estatísticas











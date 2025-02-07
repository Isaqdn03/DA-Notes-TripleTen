
**2024-11-15 15:11**

**Sprint:** [[Sprint4]]

**Topic:** #teoria-de-probabilidade

**Connections:** 

---
# **Como prever o futuro**

# Teoria da Probabilidade: Fundamentos e Aplicações

## 1. Conceitos Fundamentais

### 1.1 Definições Básicas

| Termo | Definição | Exemplo |
|-------|-----------|---------|
| Experimento | Qualquer procedimento que pode ser repetido | Jogar um dado |
| Tentativa | Uma repetição de um experimento | Cada jogada do dado |
| Resultado | Um resultado de um experimento executado uma vez | Obter 1, 2, 3, 4, 5 ou 6 |
| Evento | Um resultado simples ou conjunto de resultados com probabilidade associada | Obter número ≥ 5 |

### 1.2 Notação Básica
- P(A): Probabilidade do evento A
- S: Espaço amostral (conjunto de todos os resultados possíveis)

**Pontos-Chave:**
- Cada resultado deve ter a mesma probabilidade de ocorrência
- A soma de todas as probabilidades deve ser igual a 1 (ou 100%)

## 2. Cálculo de Probabilidades

### 2.1 Fórmula Principal

```
P(A) = # de resultados que satisfazem o evento / # total de resultados
```

### 2.2 Exemplos Práticos

#### Exemplo 1: Dado
```python
# Probabilidade de obter número ≥ 5 em um dado
P(A) = 2/6 = 1/3  # (resultados favoráveis: 5,6) / (total: 1,2,3,4,5,6)
```

**Saída esperada:**
```
0.3333... (ou 33.33%)
```

#### Exemplo 2: Baralho
```python
# Probabilidade de tirar um oito de copas
P(A) = 1/52  # (1 carta específica) / (total de cartas)
```

**Saída esperada:**
```
0.0192... (ou 1.92%)
```

## 3. Espaços Amostrais Complexos

### 3.1 Exemplo com Dois Dados
- Total de resultados possíveis: 6 x 6 = 36
- Cada par ordenado representa um resultado possível
- Probabilidade de cada resultado: 1/36

**Pontos-Chave:**
- O espaço amostral cresce exponencialmente com mais variáveis
- Eventos independentes multiplicam suas possibilidades

## 4. Lei dos Grandes Números

### Princípios Fundamentais
- Quanto mais repetições, mais próximo do valor real
- Usado para estimar probabilidades em sistemas complexos
- Baseado em frequência relativa de ocorrências

## 5. Implementação em Python

### 5.1 Exemplo com DataFrame

```python
import pandas as pd

cool_rock = pd.DataFrame({
    'Artist': ['Queen', 'Queen', 'Queen', 'Pink Floyd', 'Nirvana', 
               'AC/DC', 'AC/DC', 'Scorpions', 'Scorpions', 'Scorpions'],
    'Song': ['The Show Must Go On', 'Another One Bites The Dust', 
             'We Will Rock You', 'Wish You Were Here', 'Smells Like Teen Spirit',
             'Highway To Hell', 'Back in Black', 'Wind Of Change', 
             'Still Loving You', 'Send Me An Angel']
})

# Cálculo de probabilidade
desired_artist = 'Queen'
desired_outcomes = len(cool_rock[cool_rock['Artist'] == desired_artist])
total_outcomes = len(cool_rock)
probability = desired_outcomes / total_outcomes
print(probability)
```

**Saída esperada:**
```
0.3
```

**Pontos-Chave do Código:**
- Uso de `len()` para contar ocorrências
- Operador `==` para filtrar resultados desejados
- Divisão simples para cálculo de probabilidade

# Resumo

1. A probabilidade é calculada dividindo os resultados favoráveis pelo total de resultados possíveis
2. O espaço amostral (S) contém todos os resultados possíveis
3. A soma de todas as probabilidades deve ser 1 (100%)
4. A Lei dos Grandes Números permite estimativas em sistemas complexos
5. Python oferece ferramentas eficientes para cálculos de probabilidade com DataFrames









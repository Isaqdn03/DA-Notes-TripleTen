
**2024-11-20 21:35**

**Sprint:** [[Sprint4]]

**Topic:** #teoria-de-probabilidade 

**Connections:** [[Permutacoes e formula do fatorial]]

---
# **Fundamentos da combinatória e mais problemas de probabilidades**

# Fundamentos de Combinatória e Probabilidades

## Probabilidade em Processo Seletivo
### Contexto do Problema
- Projeto de desenvolvimento de app móvel
- 5 candidatos totais
- Necessidade de selecionar 3 programadores
- Entrevistas realizadas em ordem aleatória

### Cálculo de Probabilidade Simples
**Problema:** Qual a probabilidade de um candidato específico ser entrevistado primeiro?
- Resposta: 1/5
- Justificativa: Cada candidato tem igual chance de ser o primeiro entrevistado

## Permutações e Fatorial

### Conceito de Fatorial
- Notação: n!
- Definição: Produto de todos os números naturais de 1 até n
- Fórmula: n! = 1 × 2 × 3 × ... × (n-1) × n
### Implementação em Python para Cálculo de Fatorial
```python
from math import factorial

# Defina o número necessário de cursos
courses_amount = 3

# Calcule o fatorial de 3
result = factorial(courses_amount)

# Imprima o resultado
print(result)
```
**Saída esperada:**
```
6
```

### Aplicação para 5 Candidatos
```python
from math import factorial

candidates_amount = 5
lists_amount = factorial(candidates_amount)
print(lists_amount)
```
**Saída esperada:**
```
120
```

## Combinações

### Fórmula de Combinações
- Notação: C(n,k)
- Fórmula: C(n,k) = n! / (k! × (n-k)!)
- Uso: Calcular número de grupos possíveis de k elementos a partir de n elementos

### Exemplo Prático: Sorvetes
- Cenário: 10 sabores disponíveis, escolher 3 diferentes
- Cálculo: C(10,3) = 10! / (3! × 7!) = 120 combinações possíveis

### Implementação em Python para Cálculo de Combinações
```python
from math import factorial

n = 10  # total de sabores
k = 3   # quantidade a escolher

combinations = factorial(n) / (factorial(k) * factorial(n-k))
print(combinations)
```
**Saída esperada:**
```
120.0
```

### Aplicação para Seleção de Equipe
```python
from math import factorial

n = 5  # número de candidatos
k = 3  # tamanho da equipe

combinations = factorial(n) / (factorial(k) * factorial(n-k))
print(combinations)
```
**Saída esperada:**
```
10.0
```

# Resumo
**Pontos-Chave:**
- Probabilidade simples: Chances iguais resultam em probabilidade 1/n
- Permutações: Usadas para calcular diferentes ordenações (n!)
- Combinações: Usadas para calcular diferentes grupos sem importar ordem (C(n,k))
- Python oferece a função factorial() do módulo math para cálculos
- Em um grupo de 5 candidatos:
  - Existem 120 maneiras diferentes de ordenar as entrevistas
  - Existem 10 combinações possíveis de equipes de 3 pessoas










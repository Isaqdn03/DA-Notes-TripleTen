
**2024-11-25 19:23**

**Sprint:** [[Sprint4]]

**Topic:** #testes-de-hipóteses

**Connections:** 

---
# **Amostras aleatórias e médias amostrais**

![[Pasted image 20241126201942.png]]

## Fundamentos da Amostragem
A análise estatística frequentemente trabalha com amostras ao invés de populações inteiras. Uma amostra bem selecionada pode fornecer conclusões válidas sobre toda a população estatística.

### Requisitos para Amostragem Efetiva
- Mínimo de 30 valores (preferível 50 ou mais)
- Representatividade da população
- Seleção aleatória adequada

## Tipos de Amostras

### Amostra Aleatória Simples
- Seleção usando gerador de números aleatórios
- Cada elemento tem igual chance de ser selecionado
- Adequada para populações homogêneas

### Amostra Estratificada
- Utilizada quando há subgrupos significativamente diferentes
- População dividida em estratos (grupos)
- Amostras proporcionais de cada estrato

**Exemplo Prático:**
Em uma companhia aérea:
- Passageiros classe executiva (menor quantidade, comportamento diferente)
- Passageiros classe econômica (maior quantidade)
→ Necessidade de amostragem estratificada para representar adequadamente ambos os grupos

## Teorema Central do Limite (TCL)

### Definição
O TCL estabelece que a distribuição da média amostral de qualquer população se aproxima de uma distribuição normal conforme o tamanho da amostra aumenta.

### Características Principais
1. Aplicável a qualquer distribuição populacional
2. Média amostral tende à média populacional
3. Precisão aumenta com o tamanho da amostra

## Distribuição Amostral da Média

### Componentes
1. População estatística (conjunto total)
2. Amostras (subconjuntos selecionados)
3. Médias amostrais (médias de cada amostra)

### Cálculo de Combinações Possíveis
```python
# Fórmula para calcular número de combinações possíveis
# C(n,k) = n! / (k! * (n-k)!)

# Exemplo 1:
n = 100  # tamanho população
k = 8    # tamanho amostra
# Resultado: 186.087.894.300 combinações possíveis

# Exemplo 2:
n = 500  # tamanho população
k = 20   # tamanho amostra
# Resultado: 2,6671985128374 * 10^35 combinações
```

## Erro Padrão

### Fórmula do Erro Padrão Estimado
```python
# E.S.E. = S/√n
# Onde:
# S = desvio padrão da amostra
# n = tamanho da amostra
```

**Pontos-Chave:**
- Diminui com o aumento do tamanho da amostra
- Usado para estimar a precisão da média amostral
- "Estimado" porque é baseado em dados amostrais

# Resumo
- A amostragem é fundamental para análise estatística de grandes populações
- Amostras estratificadas são necessárias para populações heterogêneas
- O Teorema Central do Limite garante que médias amostrais seguem distribuição normal
- O erro padrão diminui com o aumento do tamanho da amostra
- Uma amostra bem selecionada com 30-50 elementos pode representar adequadamente uma população









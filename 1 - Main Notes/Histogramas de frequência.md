
**2024-11-13 17:45**

**Sprint:** [[Sprint4]]

**Topic:** #Estatística-descritiva 

**Connections:** [[Histogramas]]

---
# **Histogramas de frequência**

# Histogramas: Conceitos e Implementação

## Histogramas para Variáveis Discretas

### Exemplo com Dados
No caso de dois dados sendo lançados 1.000 vezes, o histograma mostra a frequência das somas possíveis (2 a 12).

**Por que certas somas são mais frequentes?**
- Soma 2: apenas uma combinação (1+1)
- Soma 3: duas combinações (1+2, 2+1)
- Soma 4: três combinações (1+3, 2+2, 3+1)
- Soma 7: seis combinações (mais frequente)

*Pontos-Chave:*
- Média esperada = 7
- Frequência proporcional ao número de combinações possíveis
- Ideal para valores discretos predefinidos

## Histogramas para Variáveis Contínuas

### Problema com Valores Contínuos
Variáveis contínuas apresentam desafios específicos:
- Podem ter infinitos valores dentro de um intervalo
- Valores muito próximos (ex: 5 e 5,00001)
- Frequência individual = 1 para cada valor único

### Solução: Uso de Intervalos (Bins)
A melhor abordagem é dividir os valores em intervalos (bins):
1. Define-se intervalos específicos
2. Conta-se a frequência de valores em cada intervalo
3. Cria-se barras representando cada intervalo

## Implementação em Python

### Criação do Dataset
```python
import pandas as pd

data = pd.Series([11, 20, 22, 31, 32, 33, 41, 42, 43, 44, 51, 52, 53, 54, 55, 
                  61, 62, 63, 64, 65, 66, 71, 72, 73, 74, 75, 76, 77, 81, 82, 
                  83, 84, 85, 86, 87, 88, 91, 92, 93, 94, 95, 96, 97, 98, 99])
```

Saída esperada:
```
0    11
1    20
2    22
...
42    97
43    98
44    99
dtype: int64
```

### Histograma com Número Fixo de Bins
```python
data.hist(bins=4, alpha=0.5)
```

Saída esperada:
Um histograma com 4 barras distribuídas uniformemente ao longo do intervalo de dados.

### Histograma com Intervalos Customizados
```python
data.hist(bins=[11, 20, 30, 40, 50, 60, 70, 80, 90, 99], alpha=0.7)
```

Saída esperada:
Um histograma com 9 barras, cada uma representando um intervalo específico definido na lista.

![[Pasted image 20241113175041.png]]

*Pontos-Chave sobre Parâmetros:*
- `bins=`: pode receber um número inteiro ou uma lista de limites
- `alpha=`: controla a transparência (0 a 1)
- Usando lista em bins: cria n-1 barras, onde n é o número de valores na lista

# Resumo
- Histogramas são ferramentas versáteis para visualização de distribuições
- Para variáveis discretas: use frequências diretas
- Para variáveis contínuas: use intervalos (bins)
- Pandas oferece flexibilidade na criação através do método `.hist()`
- A escolha adequada dos intervalos é crucial para uma visualização significativa










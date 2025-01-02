
**2024-12-09 11:15**

**Sprint:** [[Sprint4]]

**Topic:** #testes-de-hipóteses 

**Connections:** 

---
# **Formulação de hipóteses unicaudais**

# Testes de Hipóteses Unicaudais

## Conceitos Fundamentais

Um teste unicaudal (ou unilateral) é utilizado quando estamos interessados em verificar se um parâmetro é maior (ou menor) que um determinado valor, ao invés de apenas diferente dele.

**Tipos comuns de hipóteses:**
1. Média igual a um valor específico
2. Médias iguais entre duas populações
3. Média maior (ou menor) que um valor específico
4. Média maior (ou menor) que outra população

## Diferença entre Testes Uni e Bicaudais

### Área Crítica
- **Teste Unicaudal**: 5% de significância em apenas um lado
- **Teste Bicaudal**: 5% dividido em dois lados (2.5% em cada)

**Pontos-Chave:**
- Teste unicaudal: 1,645 desvios padrão
- Teste bicaudal: 1,96 desvios padrão

# Implementação em Python

## Teste Unicaudal Básico

```python
from scipy import stats as st
import pandas as pd

# Realizar teste
results = st.ttest_1samp(data, valor_esperado)

# Ajuste para teste unicaudal
valor_p_unicaudal = results.pvalue / 2

# Verificação da hipótese
if (valor_p_unicaudal < alpha) and (data.mean() < valor_esperado):
    print("Rejeitamos H₀")
else:
    print("Não rejeitamos H₀")
```

**Saída esperada:**
```
valor-p: [número entre 0 e 1]
[Mensagem de rejeição ou não rejeição de H₀]
```

## Exemplo Prático: Watermelon Life

```python
screens = pd.Series([4, 2, 4, 5, 5, 4, 2, 3, 3, 5, ...])
prev_screens_value = 4.867
alpha = 0.05

results = st.ttest_1samp(screens, prev_screens_value)
valor_p = results.pvalue / 2

if (valor_p < alpha) and (screens.mean() < prev_screens_value):
    print("Rejeitamos a hipótese nula")
else:
    print("Não podemos rejeitar a hipótese nula")
```

**Saída obtida:**
```
valor-p: 1.3358596895543794e-06
Rejeitamos a hipótese nula
```

# Considerações Importantes

## Interpretação do Valor-p
- Notação científica: 1.336e-06 = 1,336 × 10⁻⁶
- Quanto menor o valor-p, mais forte a evidência contra H₀

## Condições para Rejeição (Teste Unicaudal)
1. valor-p < nível de significância
2. A direção da diferença deve corresponder à hipótese alternativa

# Resumo

- Testes unicaudais são mais apropriados quando o interesse está em uma única direção
- O valor-p em testes unicaudais é metade do valor bicaudal
- A implementação em Python requer ajuste manual do valor-p
- É fundamental verificar tanto a significância estatística quanto a direção da diferença
- A interpretação deve sempre considerar o contexto prático do problema

*Pontos-Chave Finais:*
- Sempre defina claramente a direção da hipótese alternativa
- Verifique se o teste unicaudal é realmente apropriado para seu caso
- Interprete os resultados considerando tanto a significância estatística quanto a relevância prática











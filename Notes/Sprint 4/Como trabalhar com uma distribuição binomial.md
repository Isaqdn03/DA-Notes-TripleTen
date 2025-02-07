
**2024-11-22 10:17**

**Sprint:** [[Sprint4]]

**Topic:** #teoria-de-probabilidade 

**Connections:** 

---
# **Como trabalhar com uma distribuição binomial**

# Distribuição Binomial

## Conceitos Fundamentais
Uma distribuição binomial é utilizada para modelar experimentos com dois resultados possíveis (sucesso ou fracasso). 

**Características principais:**
- Dois resultados possíveis por tentativa
- Probabilidade de sucesso (p)
- Probabilidade de fracasso (1-p)
- Tentativas independentes

*Pontos-Chave:*
- Se p é a probabilidade de sucesso, então (1-p) é a probabilidade de fracasso
- A soma das probabilidades deve ser sempre 1

## Experimentos Binomiais

### Definição
Um experimento binomial ocorre quando realizamos múltiplas tentativas independentes de um experimento com dois resultados possíveis.

**Exemplo prático:**
- Lançamento de moeda 100 vezes
- Cliques em banner de propaganda

### Exemplo de Cliques em Banner
Dados:
- Probabilidade de clique no banner: 88%
- Probabilidade de não clique: 12%

Para dois usuários diferentes:
```python
# Probabilidade de um clicar e outro não
p_sucesso = 0.88
p_fracasso = 0.12
probabilidade_total = (p_sucesso * p_fracasso * 2)
```

Saída esperada:
```
0.2112 ou 21.12%
```

## Cálculo de Combinações

### Fórmula de Combinação
A fórmula para calcular o número de combinações possíveis de k sucessos em n tentativas é:

C(n,k) = n! / (k! * (n-k)!)

### Implementação em Python
```python
from math import factorial

def calcular_combinacoes(n, k):
    return factorial(n) / (factorial(k) * factorial(n - k))

# Exemplo: 90 sucessos em 100 tentativas
c = factorial(100) / (factorial(90) * factorial(10))
print(c)
```

Saída esperada:
```
17310309456440.0
```

## Probabilidade de Sucessos Específicos

### Fórmula Geral
P = C(n,k) * p^k * q^(n-k)

Onde:
- p = probabilidade de sucesso
- q = probabilidade de fracasso
- k = número de sucessos
- n = número total de tentativas

## Condições para Distribuição Binomial

Para uma variável aleatória ter distribuição binomial, é necessário:
1. Número fixo de tentativas (n)
2. Cada tentativa é um experimento binomial simples
3. Tentativas independentes
4. Probabilidade de sucesso (p) constante

*Pontos-Chave:*
- As tentativas devem ser independentes
- A probabilidade deve permanecer constante
- Apenas dois resultados possíveis por tentativa
- Número fixo de tentativas

# Tarefas
## 1.   
Os notebooks da Pineapple são caros, mas bastante populares entre geeks de TI: 60% de clientes querem comprar um computador quando vêm à loja. Os produtos da Banana são mais baratos, mas não tão populares: apenas 20% dos visitantes da loja fazem uma compra. Vamos supor que a loja só tem equipamentos da Pinapple à venda. Qual é a probabilidade de que 50 do total de 80 clientes farão uma compra durante um dia? Armazene o resultado na variável `probability` e a imprima. Não se esqueça de que em Python o sinal `**` é usado para exponenciação.

```python
from math import factorial 
p = 0.6 
q = 0.4 
n = 80 
k = 50 
probability = factorial(n) / (factorial(k) * factorial(n-k)) * (p **k) * (q** (n-k)) 
print(probability)
```
## Explicacao
Vou explicar o código passo a passo. Ele calcula a probabilidade usando a distribuição binomial, que é perfeita para situações de "sucesso/fracasso" como esta.

Vamos analisar cada parte:

1. Primeiro, definimos as variáveis:
- `p = 0.6` é a probabilidade de sucesso (60% dos clientes compram)
- `q = 0.4` é a probabilidade de fracasso (40% não compram)
- `n = 80` é o número total de clientes
- `k = 50` é o número de sucessos que queremos (clientes que compram)

2. A fórmula usada é a fórmula da distribuição binomial:
```
P(X = k) = C(n,k) * p^k * q^(n-k)
```
Onde:
- C(n,k) é a combinação de n elementos tomados k a k
- p^k é a probabilidade de sucesso elevada ao número de sucessos
- q^(n-k) é a probabilidade de fracasso elevada ao número de fracassos

3. No código:
- `factorial(n) / (factorial(k) * factorial(n-k))` calcula C(n,k)
- `p ** k` calcula p elevado a k
- `q ** (n-k)` calcula q elevado a (n-k)

Por exemplo:
- Se temos 80 clientes e queremos que exatamente 50 comprem
- A combinação `C(80,50)` nos dá todas as maneiras possíveis de escolher 50 pessoas de um grupo de 80
- Multiplicamos isso pela probabilidade de exatamente 50 pessoas comprarem (0.6^50) e 30 não comprarem (0.4^30)

O resultado final nos dá a probabilidade exata de que, em um dia com 80 clientes, exatamente 50 farão uma compra.

Esta é uma aplicação prática da distribuição binomial, que é muito útil em situações onde:
1. Temos um número fixo de tentativas (80 clientes)
2. Cada tentativa tem apenas dois resultados possíveis (compra ou não compra)
3. A probabilidade de sucesso é constante (60%)
4. As tentativas são independentes (um cliente comprar não afeta a decisão de outro)
# Resumo
A distribuição binomial é uma ferramenta estatística fundamental para análise de experimentos com dois resultados possíveis. Através de fórmulas específicas e conceitos matemáticos, podemos calcular probabilidades de diferentes números de sucessos em um conjunto fixo de tentativas. A implementação em Python facilita os cálculos complexos, especialmente quando lidamos com números grandes. As condições específicas para caracterizar uma distribuição binomial devem ser sempre observadas para garantir a validade dos cálculos.










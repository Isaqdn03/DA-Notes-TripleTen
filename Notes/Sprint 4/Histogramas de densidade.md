
**2024-11-13 17:51**

**Sprint:** [[Sprint4]]

**Topic:** #Estatística-descritiva 

**Connections:** [[Histogramas]]

---
# **Histogramas de densidade**

# Histogramas de Densidade: Uma Abordagem Avançada para Visualização de Dados

## Limitações dos Histogramas Tradicionais
- Dependência dos limites dos intervalos (barras)
- Necessidade de larguras desiguais em cenários reais
- Influência do tamanho das barras na frequência

## Exemplo Prático: Histograma com Barras de Larguras Diferentes

### Características das Barras

![[Pasted image 20241113180649.png]]

1. Primeira barra:
   - Largura: 2 (intervalo 2-4)
   - Frequência: 3

2. Segunda barra:
   - Largura: 4 (intervalo 4-8)
   - Frequência: 6

3. Terceira barra:
   - Largura: 2 (intervalo 8-10)
   - Frequência: 4

### Cálculo das Áreas
```python
# Cálculo das áreas das barras
area_barra1 = largura1 * frequencia1  # 2 * 3 = 6
area_barra2 = largura2 * frequencia2  # 4 * 6 = 24
area_barra3 = largura3 * frequencia3  # 2 * 4 = 8
```

**Resultados:**
- Barra 1: 6 unidades quadradas
- Barra 2: 24 unidades quadradas
- Barra 3: 8 unidades quadradas

*Ponto-Chave:* A segunda barra tem área 4 vezes maior que a primeira, mesmo com frequência apenas 2 vezes maior.

![[Pasted image 20241113180733.png]]

## Conversão para Densidades de Frequência

### Fórmula de Densidade
```python
densidade = frequencia / largura_barra
```

### Cálculos de Densidade para Cada Barra
1. Primeira barra: 3/2 = 1,5
2. Segunda barra: 6/4 = 1,5
3. Terceira barra: 4/2 = 2

*Ponto-Chave:* A densidade permite comparação mais justa entre barras de larguras diferentes.

## Áreas no Histograma de Densidade
```python
# Cálculo das áreas após conversão para densidade
area_densidade1 = largura1 * densidade1  # 2 * 1.5 = 3
area_densidade2 = largura2 * densidade2  # 4 * 1.5 = 6
area_densidade3 = largura3 * densidade3  # 2 * 2 = 4
```

**Resultados:**
- Barra 1: 3 (representa frequência original)
- Barra 2: 6 (representa frequência original)
- Barra 3: 4 (representa frequência original)

## Exemplo Prático: Cálculo de Densidade

```python
# Dados
idade_intervalo = 40 - 20  # = 20 anos
frequencia = 44

# Cálculo da densidade
densidade = frequencia / idade_intervalo  # 44 / 20 = 2.2
```

**Resultado:** 2,2 (densidade de frequência)

## Curvas de Densidade

### Características Principais:
- Conecta os topos das barras do histograma
- Representa distribuição contínua dos dados
- Área sob a curva corresponde à frequência
- Eixo Y mostra porcentagens da área total

*Pontos-Chave:*
- 0.01 no eixo Y = 1% da área total
- 0.02 no eixo Y = 2% da área total
- Área total = número total de instâncias

# Resumo
1. Histogramas de densidade resolvem o problema de comparação entre barras de larguras diferentes
2. A densidade é calculada dividindo a frequência pela largura da barra
3. As áreas no histograma de densidade representam as frequências reais
4. Curvas de densidade são uma evolução natural dos histogramas de densidade, oferecendo uma visualização mais suave e contínua
5. A interpretação das curvas de densidade é baseada em porcentagens da área total










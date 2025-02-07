
**2024-10-25 15:25**

**Sprint:** [[Sprint3]]

**Topic:** #Visualização-de-dados 

**Connections:** 

# **Histogramas**
### Main Topics of this Lesson:

### Conceito Básico
Histograma é uma representação gráfica da distribuição de dados numéricos contínuos, mostrando frequências em intervalos.

**Diferenças do Gráfico de Barras:**
- Histograma: dados contínuos, barras juntas
- Gráfico de Barras: dados discretos, barras separadas

### Criação Básica
```python
import pandas as pd
import matplotlib.pyplot as plt

# Método 1: usando hist()
df.hist()  # todas as colunas
df.hist(column='altura')  # coluna específica

# Método 2: usando plot()
df.plot(kind='hist')  # todas as colunas
df['altura'].plot(kind='hist')  # coluna específica
```
💡 `hist()` cria gráficos separados, `plot()` sobrepõe no mesmo gráfico
💡 `hist()` nao recebe parametros de personalização como `plot()`


### Personalização com Bins
```python
# Ajustando número de barras
df.hist(column='altura', bins=30)  # mais detalhado
df.hist(column='altura', bins=10)  # menos detalhado

# Com plot e personalização
df['altura'].plot(
    kind='hist',
    bins=30,
    title='Distribuição de Alturas',
    xlabel='Altura',
    ylabel='Frequência'
)
```
💡 Mais bins = mais detalhes, menos bins = visão mais geral

### Comparando Grupos
```python
# Histogramas sobrepostos
df[df['male'] == 1]['height'].plot(kind='hist', bins=30)
df[df['male'] == 0]['height'].plot(kind='hist', bins=30, alpha=0.8)
plt.legend(['Male', 'Female'])
plt.show()
```
💡 Use `alpha` para transparência quando sobrepor histogramas

### Filtros e Índices
```python
# Ordenando e filtrando dados
df = df.sort_values('male').reset_index(drop=True)
df = df[df.index < 5000]
df.hist(column='height', bins=50)
```
💡 Útil para analisar subconjuntos específicos dos dados

### Histograma Profissional
```python
plt.figure(figsize=(10, 6))
df['altura'].plot(
    kind='hist',
    bins=30,
    color='skyblue',
    edgecolor='black',
    alpha=0.7
)
plt.title('Distribuição de Alturas')
plt.xlabel('Altura (cm)')
plt.ylabel('Frequência')
plt.grid(True, alpha=0.3)
plt.show()
```
💡 Adicione elementos visuais para melhor apresentação

### Dicas Importantes:
- Use `hist()` para análise rápida
- Use `plot()` para mais controle de formatação
- Escolha bins baseado na quantidade e distribuição dos dados
- Compare apenas variáveis similares no mesmo gráfico
- Sempre inclua títulos e legendas claros

### Quando Usar:
- Análise de distribuição
- Identificação de outliers
- Comparação entre grupos
- Verificação de normalidade
- Análise exploratória inicial

🎯 **Lembre-se:** O número ideal de bins depende dos seus dados e objetivos. Experimente diferentes valores até encontrar a visualização mais informativa.








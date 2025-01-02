
**2024-10-25 12:20**

**Sprint:** [[Sprint3]]

**Topic:** #Visualização-de-dados 

**Connections:** 

# **Correlação**
### Main Topics of this Lesson:

## O que é Correlação?

- A correlação é uma medida estatística que quantifica o grau de associação linear entre duas variáveis quantitativas. Ela indica a força e a direção da relação linear entre as variáveis.

## Tipos de Correlação

- **Correlação Positiva**: Quando uma variável aumenta, a outra também tende a aumentar. Exemplo: altura e peso de uma pessoa.
    
    - Coeficiente de correlação próximo de +1 indica uma correlação positiva forte.
    
- **Correlação Negativa**: Quando uma variável aumenta, a outra tende a diminuir. Exemplo: altura da pessoa e tom de voz.
    
    - Coeficiente de correlação próximo de -1 indica uma correlação negativa forte.
    
- **Correlação Fraca**: Existe pouca associação linear entre as variáveis, com valores de correlação próximos de zero.
    
    - Coeficiente de correlação entre 0 e ±0.3 indica uma correlação fraca.
    
- **Correlação Forte**: Existe alto grau de associação linear, com valores de correlação próximos de +1 ou -1.
    
    - Coeficiente de correlação entre ±0.7 e ±1 indica uma correlação forte.
    

## Coeficiente de Correlação de Pearson

- O coeficiente de correlação de Pearson é o mais comumente usado para medir a correlação linear entre duas variáveis. Ele varia de -1 a +1.
    
    - +1: Correlação positiva perfeita
    - -1: Correlação negativa perfeita
    - 0: Ausência de correlação linear.
    

## Cálculo do Coeficiente de Correlação

```python
import pandas as pd 
from matplotlib import pyplot as plt

df = pd.read_csv('/datasets/height_weight.csv') 

correlacao = df['height'].corr(df['weight']) 

print(correlacao)`
```

Este código calcula o coeficiente de correlação de Pearson entre as colunas `height` e `weight` de um dataframe `df` usando a biblioteca Pandas.

## Interpretação do Coeficiente de Correlação

- **Valor do Coeficiente**:
    
    - ±0.9 a ±1: Correlação muito forte
    - ±0.7 a ±0.9: Correlação forte
    - ±0.5 a ±0.7: Correlação moderada
    - ±0.3 a ±0.5: Correlação fraca
    - ±0.3 a 0: Correlação desprezível ou nula.
    

## Importância da Correlação

- **Identificar Relações**: A correlação ajuda a compreender como as variáveis interagem, facilitando a construção de modelos preditivos mais precisos.
- **Reduzir Dimensionalidade**: Variáveis altamente correlacionadas podem ser combinadas, simplificando a análise sem perder informação relevante.
- **Descobrir Padrões**: A análise de correlação pode revelar insights sobre o comportamento dos dados que não seriam evidentes de outra forma.

## Cuidados com a Interpretação

- **Correlação não Implica Causalidade**: A existência de correlação não significa que uma variável cause o efeito na outra. Experimentos controlados são necessários para determinar causalidade.

## Matrizes de Correlação

- As matrizes de correlação são ferramentas visuais úteis para resumir as correlações entre todas as variáveis de um conjunto de dados, facilitando a identificação de padrões de associação linear.
- Exemplo prático: Utilizar o método `df.corr()` do Pandas para calcular a matriz de correlação de Pearson para as variáveis numéricas de um dataframe.

## Exemplos de correlacao em graficos

### 0.6

![[Pasted image 20241025123043.png]]

### -0.6

![[Pasted image 20241025123137.png]]

### 0

![[Pasted image 20241025123207.png]]

### 0.99

![[Pasted image 20241025123254.png]]

### -0.99

![[Pasted image 20241025123326.png]]
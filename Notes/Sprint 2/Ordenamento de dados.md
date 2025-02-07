
2024-10-07 22:38

Sprint: [[Sprint2]]

Topic: #dataframe-prepocess 


# Ordenamento de dados

# 5.7 Ordenamento de dados

## Ordenando dados

![https://practicum-content.s3.amazonaws.com/resources/12.7PT_1690267678.png](https://practicum-content.s3.amazonaws.com/resources/12.7PT_1690267678.png)

### 1. Ordenação Básica com `sort_values()`

O método `sort_values()` é usado para ordenar as linhas de um DataFrame ou de uma série por valores em uma ou mais colunas. Aqui estão os principais pontos sobre como utilizá-lo.

### Parâmetros mais importantes:

- **`by=`**: Nome ou nomes das colunas cujos valores são usados para ordenar as linhas do DataFrame.
- **`ascending=`**: Ordem da ordenação. Por padrão, o valor é `True` (ordem crescente). Para ordem decrescente, definir como `False`.

### 2. Exemplo de Ordenação Crescente

Vamos supor que estamos interessados nos exoplanetas com raios semelhantes ao da Terra. Podemos usar `sort_values()` para ordenar o DataFrame pela coluna `'radius'` em ordem crescente.

```python
python
Copy code
print(exoplanet.sort_values(by='radius').head(10))

```

**Saída:**

```css
css
Copy code
             name     mass    radius  discovered
253   Kepler-37 b  0.01000  0.291431        2013
137  Kepler-102 b  0.01353  0.470774        2014
175  Kepler-138 b  0.00021  0.526818        2014
...

```

- Aqui, estamos ordenando os planetas pelos valores da coluna `'radius'` em ordem crescente.
- Os menores planetas aparecem primeiro, permitindo identificar rapidamente os que são menores que a Terra.

### 3. Ordenação em uma Única Coluna

Se aplicarmos `sort_values()` diretamente a uma coluna específica de um DataFrame, não há necessidade de usar o parâmetro `by=`.

```python

print(exoplanet['radius'].sort_values().head(10))

```

**Saída:**

```python
python
Copy code
253    0.291431
137    0.470774
175    0.526818
...

```

- Neste exemplo, ordenamos apenas a coluna `'radius'` e imprimimos os 10 menores valores. Isso é útil quando estamos interessados somente em ver a ordem dos valores de uma coluna específica.

### 4. Filtrando Dados com Indexação Lógica

Podemos combinar `sort_values()` com indexação lógica para focar em dados específicos. Vamos extrair todos os exoplanetas menores que a Terra:

```python
python
Copy code
print(exoplanet[exoplanet['radius'] < 1])

```

- **Indexação lógica**: Utilizamos a condição `exoplanet['radius'] < 1` para obter todos os planetas com raio menor que o da Terra.

**Saída:**

```python
python
Copy code
             name     mass    radius  discovered
128      KOI-55 b  0.00140  0.762205        2011
...

```

- Com isso, obtivemos um subconjunto do DataFrame contendo apenas exoplanetas com raio menor que 1 (em relação à Terra).

### 5. Ordenando e Filtrando Dados ao Mesmo Tempo

Agora vamos encontrar todos os planetas descobertos em 2014 e que possuem raio menor que o da Terra:

```python
python
Copy code
exo_small_14 = exoplanet[exoplanet['radius'] < 1]
exo_small_14 = exo_small_14[exo_small_14['discovered'] == 2014]
print(exo_small_14)

```

- Utilizamos **duas condições** para filtrar os planetas menores que a Terra e descobertos em 2014.

Agora podemos **ordenar** esses planetas por raio em ordem decrescente:

```python
python
Copy code
print(exo_small_14.sort_values(by='radius', ascending=False))

```

- **`ascending=False`**: Ordena os valores em ordem decrescente.
- Esta abordagem nos permite priorizar planetas menores ou maiores, dependendo do que for mais relevante para a análise.

**Saída:**

```python
python
Copy code
             name     mass    radius  discovered
148  Kepler-106 d  0.02549  0.952757        2014
...

```

- Assim, vemos o maior planeta entre os menores que a Terra, descobertos em 2014, no topo da tabela.

### 6. Ordenando Colunas com Strings

A ordenação pode ser feita para colunas contendo **valores alfanuméricos**. Vamos criar um exemplo simples:

```python
python
Copy code
import pandas as pd
df = pd.DataFrame(['b','a','c'], columns=['alphabet'])
df = df.sort_values(by='alphabet')
print(df)

```

**Saída:**

```css
css
Copy code
 alphabet
1       a
0       b
2       c

```

- **Ordenação alfabética**: A coluna `'alphabet'` é ordenada em ordem crescente.
- Podemos também ordenar em ordem inversa, usando `ascending=False`.

### 7. Salvando o DataFrame Ordenado

O método `sort_values()` retorna um novo objeto DataFrame, não modifica o original. Portanto, é necessário **armazenar o resultado** em uma variável para continuar trabalhando com os dados ordenados:

```python
python
Copy code
exo_small_14 = exo_small_14.sort_values(by='radius', ascending=False)

```

- Isso armazena o DataFrame ordenado em `exo_small_14`, para futuras análises.

### Resumo dos Pontos Importantes:

1. **Parâmetros do `sort_values()`**:
    - `by=`: Nome(s) das colunas para ordenar.
    - `ascending=`: Ordem da ordenação (True para crescente, False para decrescente).
2. **Ordenação por Colunas Numéricas e Alfabéticas**:
    - Podemos ordenar tanto números quanto strings em um DataFrame.
    - A ordenação alfabética é feita da mesma forma que a numérica.
3. **Filtragem e Ordenação Combinadas**:
    - É possível combinar **indexação lógica** com `sort_values()` para filtrar e ordenar os dados conforme necessário.
4. **Armazenando o Resultado Ordenado**:
    - Para salvar um DataFrame ordenado, devemos armazenar o resultado em uma variável, pois `sort_values()` não altera o DataFrame original.

Estas anotações cobrem os principais conceitos e usos do método `sort_values()`, ilustrando como podemos usá-lo para ordenar, filtrar e explorar dados em pandas de forma eficiente.


# References








**2024-10-28 20:35**

**Sprint:** [[Sprint3]]

**Topic:** #tipos-de-dados 

**Connections:** 

# **Como trabalhar com tipos de dados numéricos e de string**
### Main Topics of this Lesson:


# Trabalhando com Tipos de Dados Numéricos e de String em Pandas

Este guia aborda como trabalhar com tipos de dados numéricos (inteiros e de ponto flutuante) e de string em Pandas, incluindo a conversão entre tipos e como lidar com situações problemáticas.

## Tipos de Dados em Pandas

Quando o Pandas lê dados de um arquivo (como CSV ou Excel), ele tenta inferir o tipo de dado de cada coluna. Colunas com apenas números são tipicamente lidas como `int` ou `float`. Colunas contendo texto são lidas como `object`, que o Pandas usa para representar strings e também colunas com tipos de dados mistos.

## Conversão de Tipos de Dados com `astype()`

O método `astype()` permite converter uma série ou um DataFrame inteiro para um tipo diferente.  A sintaxe básica é `df['nome_da_coluna'] = df['nome_da_coluna'].astype('novo_tipo')`.

**Exemplo 1: Convertendo para String**

```python
import pandas as pd

d = {'col1': [1.0, 2.0], 'col2': [3, 4]}
df = pd.DataFrame(data=d)

df_str = df.astype('str')
print(df_str)
print(df_str.dtypes)
```

Este código converte todas as colunas do DataFrame `df` para o tipo string (`object`).  Observe que a aparência dos dados impressos pode não mudar, mas o tipo subjacente é alterado.

**Exemplo 2: Convertendo para Inteiro**

```python
import pandas as pd

d = {'col1': [1.0, 2.0], 'col2': [3, 4]}
df = pd.DataFrame(data=d)

df['col1'] = df['col1'].astype('int')
print(df)
print(df.dtypes)
```

Aqui, apenas a coluna `col1` é convertida para inteiro.  Os valores de ponto flutuante são truncados (a parte decimal é removida).


## Cuidados na Conversão com `astype()`

Nem todas as conversões são possíveis ou desejáveis.  Converter um float para inteiro pode resultar em perda de informação.  Tentar converter uma string que não representa um número válido para um tipo numérico resultará em um erro.

**Exemplo 3: Verificando a segurança da conversão com NumPy**

```python
import numpy as np
import pandas as pd

d = {'col1': [1.0, 2.0, 3.0, 4.0], 'col2': [5.0, 6.01, 7.0, 8.0]}
df = pd.DataFrame(data=d)

print(np.array_equal(df['col1'], df['col1'].astype('int')))  # True - Conversão segura
print(np.array_equal(df['col2'], df['col2'].astype('int')))  # False - Conversão com perda de dados
```

Usando `np.array_equal()`, podemos comparar os valores antes e depois da conversão para garantir que não haja perda de dados.

## Convertendo Strings para Números com `to_numeric()`

O método `to_numeric()` oferece mais flexibilidade na conversão de strings para números.  Ele lida com strings representando números inteiros e de ponto flutuante e possui o parâmetro `errors` para controlar o comportamento com valores inválidos.

**`errors` pode ser:**

* `'raise'` (padrão): Lança um erro se encontrar um valor inválido.
* `'coerce'`: Substitui valores inválidos por `NaN`.
* `'ignore'`: Ignora valores inválidos, deixando-os como strings.

**Exemplo 4: Usando `to_numeric()` com `errors='coerce'`**

```python
import pandas as pd

d = {'col1': ['1.0', 'B.0'], 'col2': ['3', '4']}
df = pd.DataFrame(data=d)

df['col1'] = pd.to_numeric(df['col1'], errors='coerce')
print(df)
print(df.dtypes)
```

Neste exemplo, 'B.0' não pode ser convertido para um número, então é substituído por `NaN`.


## Recapitulando

* Use `astype()` para conversões simples de tipos de dados.
* Verifique a segurança das conversões, especialmente de float para int, usando `np.array_equal()`.
* Use `to_numeric()` para converter strings








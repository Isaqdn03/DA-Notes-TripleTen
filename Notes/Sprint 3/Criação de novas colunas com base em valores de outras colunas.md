
**2024-10-30 06:48**

**Sprint:** [[Sprint3]]

**Topic:** #engenharia-de-caracteristicas

**Connections:** 

---
# **Criação de novas colunas com base em valores de outras colunas**

Uma das habilidades mais úteis na análise de dados é criar uma nova coluna para resolver problemas específicos das colunas existentes do conjunto.

### **Transformações de Coluna Usando Operadores Aritméticos**

Podemos criar uma nova coluna usando operadores aritméticos como `+`, `-`, `*`, `/`, etc.

**Exemplo: Criar uma coluna "total_sales"**

```python
import pandas as pd

df = pd.read_csv('/datasets/vg_sales.csv')

df['total_sales'] = df['na_sales'] + df['eu_sales'] + df['jp_sales']
print(df['total_sales'].head())
```

**Resultado:**

```
0    74.09
1    39.47
2    32.23
3    29.82
4    30.38
Name: total_sales, dtype: float64
```

Isso funciona porque a maioria das funções matemáticas funcionam em formato vetorial: elas são aplicadas a colunas inteiras de uma só vez e não precisam percorrer cada valor em uma coluna.

**Dica:** Ao criar uma nova coluna, é importante verificar se os tipos de dados das colunas originais são compatíveis com o operador aritmético que você está usando. Por exemplo, se você estiver somando duas colunas de tipo string, você precisará converter elas para tipo numérico antes de realizar a operação.

### **Criação de Colunas Booleanas**

Podemos criar uma coluna booleana usando os operadores de comparação `==`, `<`, `>=`, etc.

**Exemplo: Criar uma coluna "is_nintendo"**

```python
import pandas as pd

df = pd.read_csv('/datasets/vg_sales.csv')

df['is_nintendo'] = df['publisher'] == 'Nintendo'
print(df['is_nintendo'].head())
```

**Resultado:**

```
0    True
1    True
2    True
3    True
4    True
Name: is_nintendo, dtype: bool
```

Observe como isso é semelhante ao que vimos nas aulas de filtragem de dados. A maior parte da filtragem de dados vem da aplicação de colunas booleanas como uma "máscara" sobre os dados.

**Dica:** Ao criar uma coluna booleana, é importante lembrar que os valores booleanos são representados como `True` ou `False`, e não como `1` ou `0`. Isso é importante porque os operadores de comparação podem retornar valores diferentes dependendo do tipo de dado que está sendo comparado.

### **Colunas Categóricas**

Se a coluna string representar um conjunto de categorias, é muito melhor tratar esses valores diretamente como categorias.

**Exemplo: Converter a coluna "platform" para uma coluna categórica**

```python
import pandas as pd

df = pd.read_csv('/datasets/vg_sales.csv')

df['platform'] = df['platform'].astype('category')
print(df['platform'].head())
```

**Resultado:**

```
0    Wii
1    NES
2    Wii
3    Wii
4     GB
Name: platform, dtype: category
Categories (31, object): ['2600', '3DO', '3DS', 'DC', ..., 'WiiU', 'X360', 'XB', 'XOne']
```

Observe que existem apenas 31 categorias, embora existam 16.719 entradas. Quando a coluna é armazenada como strings, precisamos manter o texto completo das 16.719 entradas. Quando armazenada como uma categoria, armazenamos apenas um único número (o ID da categoria).

**Dica:** Ao trabalhar com colunas categóricas, é importante lembrar que os valores categóricos são representados como números (IDs) e não como strings. Isso é importante porque os operadores de comparação podem retornar valores diferentes dependendo do tipo de dado que está sendo comparado. Além disso, é importante verificar se a coluna categórica está sendo armazenada de forma correta para evitar problemas de memória e desempenho.








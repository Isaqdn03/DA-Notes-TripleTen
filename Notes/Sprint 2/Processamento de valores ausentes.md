
2024-10-07 22:33

Sprint: [[Sprint2]]

Topic: #dataframe-prepocess 



# 5.4 **Processamento de valores ausentes**

## **Por que é importante processar valores ausentes**

- É essencial processar valores ausentes, pois algoritmos de aprendizado de máquina e estatísticos não funcionam bem com dados incompletos.
- Valores ausentes podem aparecer como `None` ou `NaN` (formas esperadas), ou em formas inesperadas como `0`, `'?'`, `'NN'` ou `'n/a'`.
- `None` representa um valor nulo ou ausência de valor, enquanto `NaN` significa "Not A Number" e é tratado como um número do tipo `float`.
- É importante identificar e tratar valores ausentes antes de prosseguir com a análise dos dados.
- Python reconhece apenas `None` e `NaN` como valores ausentes, então formas inesperadas precisam ser identificadas manualmente.

## **Processando valores ausentes**

para encontrar todos os valores ausente em uma tabela podemos usar o metodo `isna()`

e funciona da forma que se encontrar um valor ausente na tabela ele retorna true caso contrario retorna falso

mas `isna()` nao e tao util usado sozinho, usamo `isna` normalmente com o metodo `sum()`, contando todos os valores true e retorna a soma dos mesmo.

Exemplo:

```python
print(cholera.isna().sum())
```

Resultado:

```
column	0
country	0
total_cases	1
imported_cases	6
deaths	1
case_fatality_rate	1
notes	21
dtype: int64	0
```

`isna()` e `isnull()` trabalham apenas com valores da forma comum ou seja, eles tratam apenas `NaN` e `None`.

## **Maneiras de processar valores ausente**

Existem diferentes maneiras de processar valores ausentes, dependendo dos objetivos do trabalho:

- **Remoção de linhas:** Quando os valores ausentes tornam a linha inteira sem significado.
- **Substituição de valores:** Quando os valores ausentes não são cruciais, mas a linha contém outros dados importantes.

Métodos para substituir valores ausentes:

- Usar o método `fillna()` para substituir valores `NaN` por um valor específico.
- Exemplo: `cholera['imported_cases'] = cholera['imported_cases'].fillna(0)`
- Alternativa com `inplace=True`: `cholera['imported_cases'].fillna(0, inplace=True)`

Para múltiplas colunas, pode-se usar um loop:

```python
columns_to_replace = ['imported_cases']
for col in columns_to_replace:
    cholera[col].fillna(0, inplace=True)
```

A escolha do método depende da quantidade de colunas e da especificidade da substituição necessária.

Outro Exemplo:

Escreva código para percorrer as colunas `genre`, `Artist` e `track` do DataFrame `df` e substitua todos os valores ausentes pela string `'no_info'`. A lista de colunas a serem substituídas está armazenada na variável `columns_to_replace`.

Após realizar as substituições, verifique novamente o número de valores ausentes usando `isna().sum()`

```python
import pandas as pd

df = pd.read_csv('/datasets/music_log_raw.csv')

columns_to_replace = ['genre', 'Artist', 'track']

for col in columns_to_replace:
	df[col].fillna('no_info', inplace=True)# Escreva seu código aqui

print(df.isna().sum())
```

```
  user_id       0
total play    564
Artist          0
genre           0
track           0
dtype: int64
```


# References







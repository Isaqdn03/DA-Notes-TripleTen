
**2024-11-04 18:47**

**Sprint:** [[Sprint3]]

**Topic:** #transformcao-de-dados 

**Connections:** 

---
# **Combinação de DataFrames com merge()**

# Combinação de DataFrames com Pandas merge()

## Introdução ao merge()
O método `merge()` do pandas permite combinar DataFrames de maneiras que podem afetar a quantidade total de dados, diferentemente da concatenação que preserva o número total de células.

### Exemplo Base
```python
import pandas as pd

first_pupil_df = pd.DataFrame({
    'author': ['Alcott', 'Fitzgerald', 'Steinbeck', 'Twain', 'Hemingway'],
    'title': ['Little Women',
              'The Great Gatsby',
              'Of Mice and Men',
              'The Adventures of Tom Sawyer',
              'The Old Man and the Sea']
})

second_pupil_df = pd.DataFrame({
    'author': ['Steinbeck', 'Twain', 'Hemingway', 'Salinger', 'Hawthorne'],
    'title': ['East of Eden',
              'The Adventures of Huckleberry Finn',
              'For Whom the Bell Tolls',
              'The Catcher in the Rye',
              'The Scarlett Letter']
})
```

## Tipos de Junção (Merge)

### 1. Junção Interna (Inner Merge)
```python
both_pupils = first_pupil_df.merge(second_pupil_df, on='author')
```
- Mantém apenas autores presentes em ambos DataFrames
- Colunas duplicadas recebem sufixos _x e _y
- Resultado contém 9 células (redução do total original de 20)

### 2. Junção Externa (Outer Merge)
```python
both_pupils = first_pupil_df.merge(second_pupil_df, on='author', how='outer')
```
- Mantém todos os autores de ambos DataFrames
- Preenche com NaN onde não há correspondência(aonde não tem autor em comum)
- Resultado contém 21 células(aumento do total original de 20, pois agora temos 1 autor que não tem livro em comum)

### 3. Junção à Esquerda (Left Merge)
```python
both_pupils = first_pupil_df.merge(second_pupil_df, on='author', how='left')
```
- Mantém todos os autores do DataFrame esquerdo
- Inclui dados do DataFrame direito apenas quando há correspondência
- Resultado contém 15 células

### 4. Junção à Direita (Right Merge)
- Funciona como left merge, mas mantendo todos os valores do DataFrame direito
- Pode ser obtido invertendo a ordem dos DataFrames em um left merge

## Manipulação de Nomes de Colunas

### Personalização de Sufixos
```python
both_pupils = first_pupil_df.merge(
    second_pupil_df,
    on='author',
    suffixes=['_1st_student', '_2nd_student']
)
```

### Colunas com Nomes Diferentes
```python
both_pupils = first_pupil_df.merge(
    second_pupil_df,
    left_on='authors',
    right_on='author'
)
```

## Remoção de Dados Duplicados
```python
both_pupils = both_pupils.drop('author', axis='columns')
```
- Remove colunas duplicadas após merge
- Usa axis='columns' para indicar remoção de coluna

# Pontos-Chave
1. **Tipos de Merge**:
   - Inner: mantém apenas dados comuns
   - Outer: mantém todos os dados, preenchendo com NaN
   - Left: mantém todos os dados do DataFrame esquerdo
   - Right: mantém todos os dados do DataFrame direito

2. **Parâmetros Importantes**:
   - `on=`: coluna comum para junção
   - `how=`: tipo de junção
   - `suffixes=`: personalização de sufixos
   - `left_on=` e `right_on=`: junção com colunas de nomes diferentes

3. **Considerações**:
   - Cada tipo de merge resulta em quantidade diferente de dados
   - Importante gerenciar nomes de colunas duplicadas
   - Possibilidade de remover colunas redundantes com drop()

# Resumo
O método merge() do pandas oferece diferentes maneiras de combinar DataFrames baseadas em valores comuns. A escolha do tipo de junção (inner, outer, left, right) afeta diretamente a quantidade e organização dos dados resultantes. É importante considerar a nomeação das colunas e o tratamento de dados duplicados para manter a clareza e eficiência do DataFrame final.

# Exercícios

## 1.
Temos dois conjuntos de dados, `df_orders` e `df_members`, lidos em DataFrames no pré-código.

Cada linha da tabela `df_orders` representa um pedido de serviço. A tabela inclui uma coluna `'user_id'` que registra qual cliente fez cada pedido e uma coluna `'id'` que identifica o pedido.

Cada linha na tabela `df_members` representa um cliente e inclui uma coluna `'id'` que o identifica exclusivamente.

Sua tarefa é juntar as duas tabelas de forma que você fique apenas com os clientes que realmente fizeram pedidos.

- Escolha o tipo certo de junção
- Faça a junção de `df_members` como o DataFrame à esquerda, usando a coluna de id do usuário
- Faça a junção de `df_orders` como o DataFrame à direita, usando a coluna de id do usuário, não o id do pedido
- Inclua os sufixos `'_member'` (à esquerda) e `'_order'` (à direita)
- Atribua o resultado da junção a uma variável chamada `df_merged`
- Imprima `df_merged`
- Não remova colunas com drop por enquanto

```python
import pandas as pd

df_members = pd.read_csv('/datasets/new_members.csv')
df_orders  = pd.read_csv('/datasets/recent_orders.csv')

df_merged = df_members.merge(df_orders, left_on='id', right_on='user_id', suffixes=['_member', '_order'])

print(df_merged)
```

```
   id_member      username  ...    service_id      order_timestamp
0       9836  watermelon89  ...  XMD8nVShpINn  2021-06-22Z18:32:59
1       9836  watermelon89  ...  PXAQ9MiP7BvW  2021-06-22Z18:32:59
2       9837       SUPERXD  ...  R2GA1xIVXK1o  2021-06-22Z18:39:12
3       9839    NotHotDog2  ...  NvwWjzW7FydE  2021-06-22Z18:36:21
4       9840      starrats  ...  9KyrlovWf2nH  2021-06-22Z18:34:00
5       9841     beat1box2  ...  fCobsButtJD7  2021-06-22Z18:36:55

[6 rows x 7 columns]
```

## 2.
Vamos limpar um pouco as coisas.

- Elimine a coluna duplicada (nesse caso, `'user_id'`)
- Atribua o resultado de volta ao DataFrame `df_merged`
- Imprima o DataFrame unido

```python
import pandas as pd
df_members = pd.read_csv('/datasets/new_members.csv')
df_orders = pd.read_csv('/datasets/recent_orders.csv')

# Primeiro fazemos o merge
df_merged = df_members.merge(df_orders,
                           left_on='id',
                           right_on='user_id',
                           suffixes=['_member', '_order'])

# Depois removemos a coluna user_id e atribuímos o resultado de volta ao df_merged
df_merged = df_merged.drop('user_id', axis='columns')

print(df_merged)
```

```
   id_member      username  ...    service_id      order_timestamp
0       9836  watermelon89  ...  XMD8nVShpINn  2021-06-22Z18:32:59
1       9836  watermelon89  ...  PXAQ9MiP7BvW  2021-06-22Z18:32:59
2       9837       SUPERXD  ...  R2GA1xIVXK1o  2021-06-22Z18:39:12
3       9839    NotHotDog2  ...  NvwWjzW7FydE  2021-06-22Z18:36:21
4       9840      starrats  ...  9KyrlovWf2nH  2021-06-22Z18:34:00
5       9841     beat1box2  ...  fCobsButtJD7  2021-06-22Z18:36:55

[6 rows x 6 columns]
```






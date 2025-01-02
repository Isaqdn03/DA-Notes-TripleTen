
2024-10-07 22:21

Sprint:[[Sprint2]]

Topic: #dataframe-pandas 


# Filtragem com indexação lógica
# **4.6 Filtragem com indexação lógica**

## **Indexação lógica (booleana)**

1. a indexacao de dataframes pode se torna ainda mais poderosa se incluir uma expressao logica

por exemplo para checar quais linhas da coluna genre e pop:

```python
 print(df['genre'] == 'pop')
```

podemos tambem usar metodo `.loc()`

```python
 print(df.loc[:, 'genre'] == 'pop')
```

e o resultado e:

```
 0         True
 1        False
 2        False
 3        False
 4         True
          ...
 67958     True
 67959    False
 67960    False
 67961     True
 67962    False
 Name: genre, Length: 67963, dtype: bool
```

1. agora podemos usar esta informacao que obtemos para filtrar a tabela original.

```python
 print(df.loc[df.loc[:, 'genre'] == 'pop'])
```

como alternativa tambem podemos usar:

```python
 print(df.loc[df['genre'] == 'pop'])
```

e ambas linhas de codigos nos tras ao resultado de todas as linha de df aonde ‘genre’ e ‘pop’

```
 user_id  total play                 Artist genre
 0      BF6EA5AF   92.851388             Marina Rei   pop  \\\\
 4      82F52E69  193.776327                 Rixton   pop
 8      A5E0D927    3.161000  Andrew Paul Woodworth   pop
 11     596A4517    0.000000           David Civera   pop
 13     79D2876C    2.000000        Henning Wehland   pop
 ...         ...         ...                    ...   ...
 67921  2D758485   18.554472               Yuri May   pop
 67937  8B6704A2   68.495839               Dom Blvd   pop
 67952  B0DF0750   44.200000   Bierstrassen Cowboys   pop
 67958  2E27DF51  220.551837           Nadine Coyle   pop
 67961  DB0038A8   11.529112           Less Chapell   pop
 
                                       track
 0                                    Musica
 4                    Me And My Broken Heart
 8      The Name of This Next Song Is Called
 11                                  Bye Bye
 13                       Räuber und Gendarm
 ...                                     ...
 67921                         Вера Вероника
 67937                             Dear Love
 67952  Du hast den schönsten Arsch der Welt
 67958                         Girls On Fire
 67961                                  Home
 
 [8663 rows x 5 columns]
```

como mais uma alternativa tambem podemos usar a notacao abreviada, sem o metodo `.loc()` e a saida sera a mesma.

```python
 print(df[df['genre'] == 'pop'])
```

Essa forma de indexação lógica é muito comum. Você pode usar expressões lógicas com quaisquer operações lógicas:

- Para verificar a igualdade ou desigualdade, respectivamente, use `==` e `!=`.
- Para verificar se um valor é maior ou menor, use `>` ou `<`, respectivamente.
- Use `>=` para verificar se um valor é maior ou igual a, e `<=` para verificar se um valor é menor ou igual a.

Podemos tambem armazena nossa filtragem a uma variavel:

```python
import pandas as pd

df = pd.read_csv('/datasets/music_log_chpt_11.csv')

high_total_play_df = df[df['total play'] > 90]# Escreva seu código aqui

print(high_total_play_df
```

assim nos entregando um resultado das linhas na cujo qual os total play seja maior que 90:

```
        user_id  total play        Artist       genre                   track
0      BF6EA5AF   92.851388    Marina Rei         pop                  Musica
1      FB1E568E  282.981000  Stive Morgan     ambient             Love Planet
2      FB1E568E  282.981000  Stive Morgan     ambient             Love Planet
4      82F52E69  193.776327        Rixton         pop  Me And My Broken Heart
7      386FE1ED  211.880000           NaN  electronic                 Riviera
...         ...         ...           ...         ...                     ...
67954  6E8E430E  139.627717       Alt & J      trance                 Emotion
67955  D83CBA77  185.000000           TKN        rock             Не отступай
67957  18510741  109.000000   Steel Pulse      reggae           Chant A Psalm
67958  2E27DF51  220.551837  Nadine Coyle         pop           Girls On Fire
67960  26B7058C  292.455000       Red God       metal               Действуй!

[25905 rows x 5 columns]
```

e tambem podemos stackar filtragens, para obter as linhas que bateram com as condicoes

```python
import pandas as pd

df = pd.read_csv('/datasets/music_log_chpt_11.csv')

# selecionando linhas em que o gênero é jazz e total play varia entre 80 e 130
df = df[df['total play'] >= 80]
df = df[df['total play'] <= 130]
df = df[df['genre'] == 'jazz']

print(df)
```

```
        user_id  total play  ... genre                        track
406    7F77F050  111.398000  ...  jazz                          NaN
1491   E7FD0BD8  118.992000  ...  jazz                          NaN
2107   C239B913   99.482217  ...  jazz  Mirabile Mysterium / Births
2368   7EF4E404   91.414000  ...  jazz              The 408 Special
6196   70F74E63   92.965623  ...  jazz                  Still Happy
...         ...         ...  ...   ...                          ...
60591  DE8CC264  101.545207  ...  jazz                      Caravan
61940  EDD05F4F   84.638000  ...  jazz                   Temptation
62682  AEC6E89B  107.406043  ...  jazz               Something Else
66986  A4D6D142  115.991389  ...  jazz                    The Noise
67489  5F825A4E  117.449600  ...  jazz           Sudden Inspiration

[68 rows x 5 columns]

```



# References







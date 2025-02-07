 
**2024-10-17 20:51**

**Sprint:** [[Sprint3]]

**Topic:** #Filtragem-de-Dados 

**Connections:** 

# **Filtragem com base em várias condições**
### Main Topics of this Lesson:

1. Operadores lógicos
2. Múltiplas condições com `query()`

## **1. Operadores lógicos**

Para filtra DataFrames com varias condicoes a sintaxe e diferente messe caso, não podemos usar operadores lógicos, como `and`, `or` ou `not` nas expressões de filtragem. Em vez disso, temos que usar as versões que comparam bit a bit: `&`, `|` e `~`.

Exemplo de Filtragem de DataFrame com mais de uma condicao:

```python
import pandas as pd

df = pd.read_csv('/datasets/vg_sales.csv')
df['user_score'] = pd.to_numeric(df['user_score'], errors='coerce')

print(df[(df['platform'] == 'Wii') & ~(df['genre'] == 'Sports')].head())
```

O codigo verifica todos os jogos da plataforma Wii que nao sao do genero de esportes

`(df['platform'] == 'Wii') & ~(df['genre'] == 'Sports')`:

1. Cada condição individual é separada por parênteses.
2. O operador `&` é usado em vez de `and`.
3. O operador `~` é usado em vez do `not` (e ele precede a condição que queremos negar).

---

Agora Vamos usar a condicao or obtendo todos os jogos que superam $1 Milhao em vendas em pelo menos uma das 3 regios:

```python
import pandas as pd

df = pd.read_csv('/datasets/vg_sales.csv')
df['user_score'] = pd.to_numeric(df['user_score'], errors='coerce')

print(df[(df['na_sales'] >= 1) | (df['eu_sales'] >= 1) | (df['jp_sales'] >= 1)].head())
```

Novamente, cada condição individual é separada por parênteses, e usamos o operador `|` em vez de `or`.


## **2. Múltiplas condições com `query()`**

Tambem podemos filtrar varias condicoes escrevendo strings de consulta usando o metodo `query()` 

jogos de Wii que não sejam de esportes, mas desta vez usando uma string de consulta:

```python
import pandas as pd

df = pd.read_csv('/datasets/vg_sales.csv')
df['user_score'] = pd.to_numeric(df['user_score'], errors='coerce')

print(df.query("platform == 'Wii' and genre != 'Sports'").head())
```

sem o metodo query fizemos assim: 

```python
print(df[(df['platform'] == 'Wii') & ~(df['genre'] =='Sports')].head())
```

Agora, para conectar as duas condições, basta incluir a palavra-chave `and` na string de consulta.

## **Exercicio De Filtragem Avancado**

Para completar esta tarefa, você vai precisar aplicar suas habilidades de filtragem. A variável `developers` contém uma lista de empresas. Filtre o DataFrame `df` para incluir apenas os jogos que atendam às seguintes condições:

- O jogo é vendido nas três regiões (América do Norte, Europa e Japão).
- As vendas no Japão foram maiores que as vendas combinadas na América do Norte e na Europa.
- A empresa que desenvolveu o jogo está na lista `developers`.

Recomendamos criar uma string de consulta e atribuí-la a uma variável chamada `q_string`. Depois use essa variável para fazer a filtragem.

É importante observar que não há nenhuma coluna que diz explicitamente onde os jogos foram vendidos, mas você pode deduzir que um jogo _não_ foi vendido em uma região se as vendas de lá forem iguais a 0.

Use a variável `cols` para selecionar apenas as colunas `'name'`, `'developer'`, `'na_sales'`, `'eu_sales'` e `'jp_sales'` do DataFrame filtrado e atribua o resultado à variável `df_filtered`. Imprima o DataFrame inteiro.

```python
import pandas as pd

df = pd.read_csv('/datasets/vg_sales.csv')
df['user_score'] = pd.to_numeric(df['user_score'], errors='coerce')

developers = ['SquareSoft', 'Enix Corporation', 'Square Enix']
cols = ['name', 'developer', 'na_sales', 'eu_sales', 'jp_sales']

q_string = "jp_sales > (na_sales + eu_sales) and jp_sales > 0 and na_sales > 0 and eu_sales > 0 and developer in @developers"

df_filtered = df.query(q_string)[cols]
print(df_filtered)
```

```
175                                   Final Fantasy IX  ...     2.78
633                              Final Fantasy Tactics  ...     1.34
785                                       Parasite Eve  ...     1.05
1296                                         Xenogears  ...     0.89
1780                              Brave Fencer Musashi  ...     0.65
2362              Dissidia 012: Duodecim Final Fantasy  ...     0.46
2666                                    Unlimited Saga  ...     0.56
3029   Final Fantasy Crystal Chronicles: Ring of Fates  ...     0.42
3433                                    Romancing SaGa  ...     0.47
3757               Tactics Ogre: Let Us Cling Together  ...     0.27
4195  Final Fantasy Crystal Chronicles: Echoes of Time  ...     0.27
4523                                      Dawn of Mana  ...     0.29
5587                                  Final Fantasy XI  ...     0.15
```
```
```
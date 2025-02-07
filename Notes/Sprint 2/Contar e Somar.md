
2024-10-07 22:22

Sprint:[[Sprint2]]

Topic: #dataframe-pandas 


# Contar e Somar

# 4.7 **Vamos contar e somar**

## Exemplo de metodo mean() em alta pratica:

Por exemplo, se você quiser saber quanto tempo, em média, um usuário toca uma música pop, comece obtendo uma tabela filtrada apenas para músicas `'pop'`:

```python
import pandas as pd

df = pd.read_csv('/datasets/music_log_chpt_11.csv')

pop_df = df[df['genre'] == 'pop']
```

agora precisamos extrair a coluna `'total play'`. Esta coluna contém o tempo (em segundos) que o usuário tocou a música.

```python
import pandas as pd

df = pd.read_csv('/datasets/music_log_chpt_11.csv')

pop_df = df[df['genre'] == 'pop']

pop_duration = pop_df['total play']
# extraindo a coluna de reprodução total do DataFrame filtrado
```

separamos na variavel `pop_df` apenas as linhas aonde na coluna ‘genre’ o conteudo e pop.

e em seguida armazenamos somente a coluna ‘total play’ desta nova tabela que criamos na variavel `pop_duration`

e depois desta filtragem podemos aplicar o metodo `mean():`

```python
import pandas as pd

df = pd.read_csv('/datasets/music_log_chpt_11.csv')

pop_df = df[df['genre'] == 'pop']

pop_duration = pop_df['total play']

mean_duration = pop_duration.mean()

print(mean_duration)

#resultado : 90.37219914513818
```

agora a variavel pop_duration que contem somente a coluna total play, foi inserida na variavel mean_duration, tomando o metodo mean() que calculara a media dos dados nesta coluna.

## **Filtragem com metodos em uma linha**

e possivel tambem fazer esta filtragem do exemplo acima em apenas uma linha

```python
import pandas as pd

df = pd.read_csv('/datasets/music_log_chpt_11.csv')

mean_duration = df[df['genre'] == 'pop']['total play'].mean()

print(mean_duration)

#resultado : 90.37219914513818
```

1. `df[df['genre'] == 'pop']` filtra a tabela original e extrai apenas as linhas com músicas pop.
2. Ao adicionar `['total play']`, nós extraímos a coluna `'total play'` da tabela filtrada.
3. **Aplicar o método `mean()` calcula a média para nós.**

## Metodo Count()

o metodo count() conta o numero de linhas que atendem um determinado criterio

Por exemplo, podemos usar ele para calcular o número de músicas que os usuários ouviram por mais de 3 minutos (180 segundos).

```python
import pandas as pd

df = pd.read_csv('/datasets/music_log_chpt_11.csv')

duration_threshold = 180

long_songs = df[df['total play'] > duration_threshold]['total play'].count()

print(long_songs)
```

```
19065
```

1. Definimos `duration_threshold` com o critério.
2. Filtramos o DataFrame: `df[df['total play'] > duration_threshold]`.
3. Selecionamos a coluna 'total_play': `df[df['total play'] > duration_threshold]['total play']`.
4. Aplicamos `count()` para contar as linhas: `df[df['total play'] > duration_threshold]['total play'].count()`.

Mais um Exemplo:

Escreva o código para contar o número de músicas para as quais `'Aura'` é o artista. Você vai precisar da coluna `'Artist'` para fazer isso. Armazene o resultado na variável `aura_count`. Não se esqueça de imprimir este número.

```python
import pandas as pd

df = pd.read_csv('/datasets/music_log_chpt_11.csv')

aura_count = df[df['Artist'] == 'Aura' ]['Artist'].count()

print(aura_count)

#resultado: 5
```

## Metodo Sum()

o metodo sum calcula os valores de coluna especificada.

Por exemplo, podemos usar o método `sum()` para calcular o tempo total que um usuário específico passou ouvindo música. Vamos calcular esse tempo para o usuário com o `'user_id'` `'174C0ED6'`:

```python
import pandas as pd

df = pd.read_csv('/datasets/music_log_chpt_11.csv')

user_sum_dur = df[df['user_id'] == '174C0ED6']['total play'].sum()

print(user_sum_dur)
```

- `import pandas as pd`: Importa a biblioteca Pandas e a renomeia como 'pd' para facilitar o uso.
- `df = pd.read_csv('/datasets/music_log_chpt_11.csv')`: Lê um arquivo CSV chamado 'music_log_chpt_11.csv' e armazena os dados em um DataFrame chamado 'df'.
- `user_sum_dur = df[df['user_id'] == '174C0ED6']['total play'].sum()`: Esta linha faz várias coisas:
    - Filtra o DataFrame para incluir apenas as linhas onde o 'user_id' é '174C0ED6'
    - Seleciona a coluna 'total play' desse resultado filtrado
    - Usa o método sum() para somar todos os valores dessa coluna
    - O resultado é armazenado na variável 'user_sum_dur'
- `print(user_sum_dur)`: Imprime o resultado, que é o tempo total que o usuário com ID '174C0ED6' passou ouvindo música.


# References







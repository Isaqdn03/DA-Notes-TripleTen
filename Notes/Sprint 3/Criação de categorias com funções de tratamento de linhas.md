
**2024-10-31 19:20**

**Sprint:** [[Sprint3]]

**Topic:** #engenharia-de-caracteristicas 

**Connections:** 

# Notas: Manipulação Avançada de DataFrames com Pandas

## 1. Introdução ao Tratamento de Linhas em Pandas

### 1.1 Contexto
- Análise de dados de videogames
- Necessidade de criar categorias baseadas em múltiplas colunas
- Eliminação de valores ausentes para simplificação inicial

### 1.2 Dataset Utilizado
```python
import pandas as pd
df = pd.read_csv('/datasets/vg_sales.csv')
df.dropna(inplace=True)
```

## 2. Funções de Tratamento de Linhas

### 2.1 Função era_sales_group()
- **Objetivo**: Categorizar jogos com base no ano e vendas totais
- **Parâmetros**: Recebe uma linha inteira do DataFrame
- **Retorno**: Uma string indicando a categoria do jogo

#### Regras de Categorização:
| Período | Vendas | Categoria |
|---------|---------|-----------|
| < 2000 | < $1M | retro |
| 2000-2009 | < $1M | modern |
| < 2010 | ≥ $1M | classic |
| ≥ 2010 | < $1M | recent |
| ≥ 2010 | ≥ $1M | big hit |

### 2.2 Implementação
```python
def era_sales_group(row):
    year = row['year_of_release']
    total_sales = row['na_sales'] + row['eu_sales'] + row['jp_sales']
    
    if year < 2000:
        return 'retro' if total_sales < 1 else 'classic'
    if year < 2010:
        return 'modern' if total_sales < 1 else 'classic'
    return 'recent' if total_sales < 1 else 'big hit'
```

## 3. Teste de Funções

### 3.1 Criação de Linhas de Teste
```python
column_names = ['year_of_release', 'na_sales', 'eu_sales', 'jp_sales']
row_values = [2000, 0.1, 0.25, 0]
row = pd.Series(row_values, index=column_names)
```

### 3.2 Casos de Teste
- Retro: ano < 2000, vendas < $1M
- Classic: ano < 2010, vendas ≥ $1M
- Modern: 2000-2009, vendas < $1M
- Recent: ano ≥ 2010, vendas < $1M
- Big Hit: ano ≥ 2010, vendas ≥ $1M

## 4. Criação de Novas Colunas

### 4.1 Uso do método apply()
```python
df['game_category'] = df.apply(era_sales_group, axis=1)
```

### 4.2 Parâmetros Importantes
- **axis=1**: Indica processamento por linha
- **função**: Passa a função sem parênteses

### 4.3 Análise dos Resultados
Distribuição das categorias:
```python
df['game_category'].value_counts()
# modern:  3907
# recent:  1784
# classic:  748
# big hit:  407
# retro:     43
```

## 5. Pontos-Chave de Aprendizado

1. **Flexibilidade do Pandas**:
   - Permite trabalhar com múltiplas colunas
   - Suporta funções personalizadas complexas

2. **Boas Práticas**:
   - Testar função com casos específicos
   - Documentar regras de categorização
   - Validar resultados após aplicação

3. **Considerações Técnicas**:
   - Importância do parâmetro axis
   - Tratamento de valores ausentes
   - Criação de Series para testes

## Exercicios

### 1.
Escreva uma função chamada `avg_score_group()` que tenha um parâmetro chamado `row`. O parâmetro `row` deve ser um objeto Series da pandas. A função deve calcular a pontuação média de classificação para cada jogo e, em seguida, retornar uma string que distribui cada jogo em uma das seguintes categorias:

- Um valor `'low'` para pontuações médias abaixo de 60
- Um valor `'medium'` para pontuações médias de 60 a 79, incluindo esse número
- Um valor `'high'` para pontuações médias de 80 para cima

Para calcular a pontuação média, `avg_score_group()` deve extrair valores de `row` com os nomes das colunas em `'critic_score'` e `'user_score'`. A fórmula para calculá-la é `avg_score = (critic_score + user_score * 10) / 2`.

Fizemos os testes para você, o programa deve imprimir `low`, `medium` e `high`, nessa ordem.

```python
import pandas as pd
df = pd.read_csv('/datasets/vg_sales.csv')
df.dropna(inplace=True)

def avg_score_group(row):
    """
    Classifica jogos em categorias baseado na média entre pontuações de críticos e usuários.
    
    Parâmetros:
    row (pd.Series): Series contendo 'critic_score' e 'user_score'
    
    Retorna:
    str: Categoria do jogo ('low', 'medium' ou 'high')
    """
    # Extrai as pontuações
    critic_score = row['critic_score']
    user_score = row['user_score']
    
    # Calcula a média (multiplicando user_score por 10 para normalizar)
    avg_score = (critic_score + user_score * 10) / 2
    
    # Classifica baseado nos limites estabelecidos
    if avg_score < 60:
        return 'low'
    elif avg_score < 80:  # inclui scores de 60 até 79
        return 'medium'
    else:  # scores de 80 ou mais
        return 'high'


# não modifique a parte com os testes abaixo

col_names = ['critic_score', 'user_score']
test_low  = pd.Series([10, 1.0], index=col_names)
test_med  = pd.Series([65, 6.5], index=col_names)
test_high = pd.Series([99, 9.9], index=col_names)

rows = [test_low, test_med, test_high]

for row in rows:
    print(avg_score_group(row))
```

```
low
medium
high
```


### 2.
Agora é hora de testar sua nova função. Crie três linhas personalizadas com os seguintes nomes e valores de variáveis:

- `row_1` — pontuação dos críticos de 66 e pontuação dos usuários de 3.6
- `row_2` — pontuação dos críticos de 72 e pontuação dos usuários de 8.1
- `row_3` — pontuação dos críticos de 99 e pontuação dos usuários de 9.4

Todas as variáveis `row` devem ser objetos Series com valores de índice `'critic_score'` e `'user_score'` para que `avg_score_group()` possa extrair os valores corretos.

O pré-código define a função `avg_score_group()` da última tarefa, embora ela talvez esteja um pouco diferente da sua solução. Sua tarefa é imprimir o resultado da chamada `avg_score_group()` com cada uma das três entradas acima.

```python
import pandas as pd

df = pd.read_csv('/datasets/vg_sales.csv')
df.dropna(inplace=True)

def avg_score_group(row):
    critic_score = row['critic_score']
    user_score = row['user_score']
    
    avg_score = (critic_score + user_score * 10) / 2
    
    if avg_score < 60:
        return 'low'
    if avg_score < 80:
        return 'medium'
    if avg_score >= 80:
        return 'high'


def avg_score_group(row):
    critic_score = row['critic_score']
    user_score = row['user_score']
    
    avg_score = (critic_score + user_score * 10) / 2
    
    if avg_score < 60:
        return 'low'
    if avg_score < 80:
        return 'medium'
    if avg_score >= 80:
        return 'high'


# Criando as linhas de teste como Series do pandas
row_1 = pd.Series([66, 3.6], index=['critic_score', 'user_score'])
row_2 = pd.Series([72, 8.1], index=['critic_score', 'user_score'])
row_3 = pd.Series([99, 9.4], index=['critic_score', 'user_score'])

# Imprimindo os resultados para cada linha de teste
print(avg_score_group(row_1))
print(avg_score_group(row_2))
print(avg_score_group(row_3))
```

```python
low
medium
high
```
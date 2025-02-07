
**2024-11-03 10:19**

**Sprint:** [[Sprint3]]

**Topic:** #transformcao-de-dados

**Connections:** 

---
# **Processamento de dados agrupados com agg()**


# Processamento de Dados Agrupados com Pandas

## Introdução ao groupby()
O método `groupby()` é uma ferramenta fundamental do pandas para reformatar dados agrupando linhas com base em valores em uma ou mais colunas.

### Exemplo Básico de Dados
```python
import pandas as pd

df = pd.read_csv('/datasets/vg_sales.csv')
df.dropna(inplace=True)

print(df.head())
```

Saída:
```
                    name platform  year_of_release     genre publisher  
0             Wii Sports      Wii           2006.0    Sports  Nintendo   
2         Mario Kart Wii      Wii           2008.0    Racing  Nintendo   
3      Wii Sports Resort      Wii           2009.0    Sports  Nintendo   
6  New Super Mario Bros.       DS           2006.0  Platform  Nintendo   
7               Wii Play      Wii           2006.0      Misc  Nintendo   
```

## Agrupamento Básico
### Agrupamento por Uma Coluna
```python
mean_score = df.groupby('genre')['critic_score'].mean()
print(mean_score)
```

Saída:
```
genre
Action          67.852100
Adventure       66.422053
Fighting        69.693931
Misc            67.414508
...
```

**Pontos-Chave:**
- O índice do resultado é a "chave de groupby"
- A operação altera o índice de linha para as chaves de agrupamento

## Agrupamento Múltiplo
### Agrupamento por Várias Colunas
```python
grp = df.groupby(['platform', 'genre'])
print(grp['critic_score'].mean())
```

**Características:**
- Resulta em um objeto Series multi-índice
- Dois níveis de índice: platform e genre
- Permite análise mais granular dos dados

## Framework Split-Apply-Combine
O processamento de dados segue três etapas principais:

1. **Split (Dividir)**: Separação dos dados em grupos
2. **Apply (Aplicar)**: Aplicação de função de agregação
3. **Combine (Combinar)**: Combinação dos resultados

### Implementação Completa
```python
# Método completo
grp = df.groupby(['platform', 'genre'])
mean_scores = grp['critic_score'].mean()

# Método simplificado
print(df.groupby(['platform', 'genre'])['critic_score'].mean())
```

## Método agg()
O método `agg()` permite aplicar diferentes funções de agregação a diferentes colunas simultaneamente.

### Agregações Múltiplas
```python
agg_dict = {'critic_score': 'mean', 'jp_sales': 'sum'}
grp = df.groupby(['platform', 'genre'])
print(grp.agg(agg_dict))
```

### Funções Personalizadas
```python
def double_it(sales):
    sales = sales.sum() * 2
    return sales

agg_dict = {'jp_sales': double_it}
print(grp.agg(agg_dict))
```

**Pontos-Chave sobre agg():**
- Aceita dicionário com pares coluna:função
- Suporta funções built-in e personalizadas
- Permite múltiplas agregações em uma única operação

# Resumo
- O método `groupby()` é fundamental para análise de dados agrupados
- Permite agrupamento por uma ou múltiplas colunas
- O framework split-apply-combine estrutura o processo de agregação
- O método `agg()` oferece flexibilidade para múltiplas agregações
- Suporta funções personalizadas para cálculos específicos

**Métodos Importantes:**
- `groupby()`: Agrupa dados
- `agg()`: Aplica agregações
- `mean()`: Calcula média
- `sum()`: Calcula soma
- `dropna()`: Remove valores ausentes

## Exercícios
É hora de conferir mais de perto as vendas de videogames de cada gênero.

O pré-código cria uma coluna 'total_sales' como você fez antes. Você vai usar essas colunas, então preste atenção nesses nomes.

O pré-código agrupa o DataFrame df pela coluna 'genre' e atribui o objeto agrupado resultante à variável grp.

E agora você vai:

Criar um dicionário para calcular para cada gênero:
Soma das vendas totais
Média de vendas na América do Norte (NA)
Média de vendas na Europa (EU)
Média de vendas no Japão (JP)
Atribuir o dicionário a uma variável chamada agg_dict com as tuplas descritas acima.
Atribuir o resultado de agg() a uma variável chamada genre.
Imprimir genre.

```python
import pandas as pd

df = pd.read_csv('/datasets/vg_sales.csv')
df['total_sales'] = df['na_sales'] + df['eu_sales'] + df['jp_sales']

grp = df.groupby('genre')

agg_dict = {'total_sales': 'sum', 'na_sales': 'mean', 'eu_sales': 'mean', 'jp_sales': 'mean'}

genre = grp.agg(agg_dict)# use a função agg aqui

print(genre)# imprima seus resultados aqui
```

Resultado:
```python
              total_sales  na_sales  eu_sales  jp_sales
genre
Action            1559.58  0.260834  0.154045  0.047905
Adventure          221.10  0.080783  0.048764  0.040138
Fighting           411.17  0.263086  0.118174  0.103039
Misc               728.12  0.232726  0.121566  0.061777
Platform           776.68  0.501689  0.225619  0.147331
Puzzle             230.19  0.211845  0.086224  0.098810
Racing             652.57  0.287710  0.189359  0.045404
Role-Playing       874.98  0.220540  0.125807  0.236973
Shooter            948.34  0.447649  0.239864  0.029297
Simulation         359.51  0.208455  0.129886  0.072998
Sports            1196.76  0.291495  0.160473  0.057726
Strategy           163.38  0.100366  0.066135  0.072709
```








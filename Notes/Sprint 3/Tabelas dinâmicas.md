
**2024-11-03 17:04**

**Sprint:** [[Sprint3]]

**Topic:** #transformcao-de-dados 

**Connections:** 

---
# **Tabelas dinâmicas**

# Tabelas Dinâmicas em Pandas

## Introdução
As tabelas dinâmicas são uma ferramenta poderosa do pandas para sintetizar e explorar conjuntos de dados multidimensionais. São similares às pivot tables do Excel, mas com a vantagem de serem criadas programaticamente.

## Dataset de Exemplo
O exemplo utiliza um conjunto de dados de vendas de videogames (vg_sales.csv) contendo informações sobre jogos, plataformas, vendas e avaliações.

```python
import pandas as pd

df = pd.read_csv('/datasets/vg_sales.csv')
print(df.head())
```

Saída:
```
                       name platform  year_of_release         genre publisher  
0                Wii Sports      Wii           2006.0        Sports  Nintendo   
1         Super Mario Bros.      NES           1985.0      Platform  Nintendo   
2            Mario Kart Wii      Wii           2008.0        Racing  Nintendo   
3         Wii Sports Resort      Wii           2009.0        Sports  Nintendo   
4  Pokemon Red/Pokemon Blue       GB           1996.0  Role-Playing  Nintendo   
```

## Criando Tabelas Dinâmicas com pivot_table()

### Sintaxe Básica
```python
df.dropna(inplace=True)

pivot_data = df.pivot_table(index='genre',
                           columns='platform',
                           values='eu_sales',
                           aggfunc='sum')
```

### Parâmetros Principais
- **index**: Define as linhas da tabela (no exemplo, 'genre')
- **columns**: Define as colunas da tabela (no exemplo, 'platform')
- **values**: Especifica os valores a serem agregados (no exemplo, 'eu_sales')
- **aggfunc**: Define a função de agregação (no exemplo, 'sum')

**Importante:** O resultado de pivot_table() é um DataFrame do pandas

## Comparação com groupby()

### Exemplo usando groupby()
```python
groupby_data = df.groupby(['genre', 'platform'])['eu_sales'].mean()
```

### Principais Diferenças
1. **Formato de Saída:**
   - pivot_table(): Retorna um DataFrame com formato tabular
   - groupby(): Retorna uma Series com formato hierárquico

2. **Legibilidade:**
   - pivot_table(): Mais fácil de ler e interpretar visualmente
   - groupby(): Mais compacto, mas pode ser menos intuitivo

3. **Tipo de Objeto:**
   - pivot_table(): pandas.core.frame.DataFrame
   - groupby(): pandas.core.series.Series

## Pontos-Chave
- Tabelas dinâmicas são úteis para **sintetizar dados complexos**
- pivot_table() oferece uma visualização mais **amigável e tabular**
- A escolha entre pivot_table() e groupby() depende da **preferência pessoal** e do **caso de uso específico**
- pivot_table() é especialmente útil quando se deseja **excluir colunas irrelevantes** para a análise

# Resumo
As tabelas dinâmicas no pandas oferecem uma maneira eficiente de agregar e analisar dados multidimensionais. Enquanto groupby() e pivot_table() podem realizar tarefas similares, cada método tem suas vantagens específicas. A escolha entre eles geralmente depende da necessidade de visualização e da preferência do usuário quanto ao formato da saída.










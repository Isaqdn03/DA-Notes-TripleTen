
**2024-10-10 17:18**

**Sprint:** [[Sprint3]]

**Topic:** #tratamento-ausente-duplicados 


# **Preenchimento de valores quantitativos ausentes**
### Main Topics of this Lesson:

1. Medio ou mediana
2. Quando usar a media ou a mediana
3. Verificando se ha valores atipicos
4. Preenchendo valores quantativos

---


## **1.Medio ou Mediana**

```python
import pandas as pd

analytics_data = pd.read_csv('/datasets/web_analytics_data.csv')

print(analytics_data.head(10))
```

```
      user_id device_type   age    time
0  7141786820     desktop  33.0  2127.0
1  5644686960      mobile  30.0    35.0
2  1914055396     desktop  25.0     NaN
3  4099355752     desktop  25.0  2123.0
4  6032477554     desktop  27.0    59.0
5  5872473344      mobile  27.0     NaN
6  7977025176      mobile   NaN     NaN
7  3512872755     desktop  40.0    65.0
8  1827368713     desktop  37.0     NaN
9  8688870165     desktop  36.0  2124.0
```

- `user_id`: Identifica univocamente cada visitante do site
- `device_type'`: Informa o tipo de dispositivo usado para acessar o site
- `age'`: Diz a idade do visitante, em anos
- `'time'`: Aponta o tempo gasto no site, em segundos

`'age'` e `'time'` são quantitativas, enquanto `'user_id'` e `'device_type'` são categóricas.

- **Media**

	![[Pasted image 20241010181122.png]]

- **mediana**

	![[Pasted image 20241010181148.png]]


## **2. Quando usar a media ou a mediana**

Para decidir qual é o melhor valor representativo entre a média e a mediana, podemos seguir os passos abaixo:

1. Determine se os dados têm valores atípicos significativos.
2. Se não há valores atípicos significativos, calcule a média usando o método `mean()`.
3. Se seus dados têm valores atípicos significativos, calcule a mediana usando o método `median()`.
4. Substitua valores ausentes pela média ou pela mediana usando o método `fillna()`.

	## Valores Típicos

- **O que são**: São os números que representam bem a maioria dos dados.
- **Exemplo**: Se você tem as idades de um grupo de pessoas e a maioria tem entre 20 e 30 anos, essas idades são consideradas típicas.
- **Onde estão**: Geralmente, estão perto da média (a soma de todos os valores dividida pelo número de valores).
	## Valores Atípicos

- **O que são**: São números que se afastam muito dos outros dados.
- **Exemplo**: Se a maioria das idades em um grupo é entre 20 e 30 anos, mas uma pessoa tem 90 anos, essa idade é atípica.
- **Por que importam**: Podem indicar algo interessante ou um erro. Por exemplo, se você está analisando vendas e vê um mês com vendas extremamente altas ou baixas, isso pode precisar de atenção.
	## Como Identificar

- **Valores Típicos**: Estão dentro da faixa normal dos dados.
- **Valores Atípicos**: Estão muito distantes da maioria, como se fossem "fora do padrão".

	## Resumo

- **Valores Típicos** = Normais, comuns.
- **Valores Atípicos** = Estranhos, diferentes.

## **3. Verificando se ha valores atipicos**

Nao Existem grandes valores atipicos, podemos usar a media como valor representativo tanto para `age` como para `time`

Entao neste caso podemos preencher os valores ausentes  da coluna `age` (coluna quantitativa) 
1. calculando a media desda coluna, 
2. armazenando o resultado a uma variavel, 
3. e em seguida usar para preencher os valores ausente

```python
import pandas as pd

analytics_data = pd.read_csv('/datasets/web_analytics_data.csv')

age_avg = analytics_data['age'].mean()
print("Idade média:", age_avg)

analytics_data['age'] = analytics_data['age'].fillna(age_avg)

```

```
Idade Media: 32.48966336969903
```

por padrao as linhas com valores ausentes nao sao incluidas no calculo pelo metodo `mean()` 

## **4. Preenchendo valores quantativos/TAREFA**

```python
import pandas as pd

analytics_data = pd.read_csv('/datasets/web_analytics_data.csv')

age_avg = analytics_data['age'].mean()
analytics_data['age'] = analytics_data['age'].fillna(age_avg)

desktop_data = analytics_data[analytics_data['device_type'] == 'desktop']
mobile_data =  analytics_data[analytics_data['device_type'] == 'mobile']

desktop_avg = desktop_data['time'].mean()
mobile_avg = mobile_data['time'].mean()

desktop_data['time'] = desktop_data['time'].fillna(desktop_avg)
mobile_data['time'] = mobile_data['time'].fillna(mobile_avg)

# isso vai verificar se você tem algum valor ausente
desktop_data.info()
print()
mobile_data.info()
```

1. Importação da biblioteca
    
    `import pandas as pd`
    Importa a biblioteca pandas para manipulação de dados.
2. Leitura do arquivo CSV
    
    `analytics_data = pd.read_csv('/datasets/web_analytics_data.csv')`
    Lê o arquivo CSV e armazena os dados em 'analytics_data'.
3. Tratamento de valores ausentes na coluna 'age'
    
    `age_avg = analytics_data['age'].mean() analytics_data['age'] = analytics_data['age'].fillna(age_avg)`
    Calcula a média de idade e preenche os valores ausentes com essa média.
4. Separação dos dados por tipo de dispositivo
    
    `desktop_data = analytics_data[analytics_data['device_type'] == 'desktop'] mobile_data = analytics_data[analytics_data['device_type'] == 'mobile']`
    Cria dois DataFrames separados para dados de desktop e mobile.
5. Cálculo da média de tempo para cada tipo de dispositivo
    
    `desktop_avg = desktop_data['time'].mean() mobile_avg = mobile_data['time'].mean()`
    Calcula a média da coluna 'time' para desktop e mobile separadamente.
6. Preenchimento de valores ausentes na coluna 'time'
    
    `desktop_data['time'] = desktop_data['time'].fillna(desktop_avg) mobile_data['time'] = mobile_data['time'].fillna(mobile_avg)`
    Preenche os valores ausentes na coluna 'time' com a média correspondente para cada tipo de dispositivo.
7. Verificação de valores ausentes
    
    `desktop_data.info() print() mobile_data.info()`
    Exibe informações sobre os DataFrames, incluindo contagem de valores não nulos, o que ajuda a verificar se ainda existem valores ausentes.

Em resumo, este código:

1. Carrega dados de análise web
2. Trata valores ausentes na coluna de idade para todo o conjunto de dados
3. Separa os dados por tipo de dispositivo (desktop e mobile)
4. Trata valores ausentes na coluna de tempo separadamente para cada tipo de dispositivo
5. Verifica se ainda existem valores ausentes nos conjuntos de dados resultantes
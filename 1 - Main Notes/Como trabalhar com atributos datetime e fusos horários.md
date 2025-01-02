
**2024-10-29 20:25**

**Sprint:** [[Sprint3]]

**Topic:** #tipos-de-dados 

**Connections:** 

# **Como trabalhar com atributos datetime e fusos horários**
### Main Topics of this Lesson:


# Trabalhando com Atributos datetime e Fusos Horários

## Acessando Atributos de Colunas datetime

- Os objetos datetime na pandas são representados pelo tipo de dados `Timestamp`.
- Para acessar atributos de um único valor `Timestamp`, como o ano, podemos usar a notação de ponto:

```python
import pandas as pd

df = pd.read_csv('/datasets/OnlineRetail.csv')
df['InvoiceDate'] = pd.to_datetime(df['InvoiceDate'], format='%Y-%m-%dT%H:%M:%SZ')

print(df['InvoiceDate'][0].year)  # Retorna o ano do primeiro InvoiceDate
```

```
2010
```

- Porém, não podemos acessar diretamente os atributos de uma coluna inteira de dados datetime:

```python
df['day'] = df['InvoiceDate'].day
# AttributeError: 'Series' object has no attribute 'day'
```

## Usando o Método Acessor `.dt`

- Para acessar atributos de uma coluna inteira de dados datetime, use o método acessor `.dt`:

```python
df_days = df['InvoiceDate'].dt.day
print(df_days.sample(5, random_state=42))
```

```
33553    17
9427      6
199       1
12447     6
39489    21
Name: InvoiceDate, dtype: int64
```

- O método `.dt` permite acessar vários atributos datetime, como `year`, `month`, `day`, `hour`, `minute`, `second`, etc.

## Trabalhando com Fusos Horários

- Seus dados podem vir de diferentes localizações geográficas, cada uma com seu próprio fuso horário.
- Você pode precisar converter os dados para um fuso horário específico para apresentá-los.

### Atribuindo um Fuso Horário

- Use o método `.dt.tz_localize()` para atribuir um fuso horário a uma coluna datetime:

```python
import pandas as pd

df = pd.read_csv('/datasets/OnlineRetail.csv')
df['InvoiceDate'] = pd.to_datetime(df['InvoiceDate'], format='%Y-%m-%dT%H:%M:%SZ')
df['InvoiceDate'] = df['InvoiceDate'].dt.tz_localize('UTC')

print(df['InvoiceDate'].sample(5, random_state=42))
```

```
33553   2010-12-17 12:38:00+00:00
9427    2010-12-06 09:58:00+00:00
199     2010-12-01 13:21:00+00:00
12447   2010-12-06 16:57:00+00:00
39489   2010-12-21 15:19:00+00:00
Name: InvoiceDate, dtype: datetime64[ns, UTC]
```

### Convertendo entre Fusos Horários

- Use o método `.dt.tz_convert()` para converter uma coluna datetime de um fuso horário para outro:

```python
import pandas as pd

df = pd.read_csv('/datasets/OnlineRetail.csv')
df['InvoiceDate'] = pd.to_datetime(df['InvoiceDate'], format='%Y-%m-%dT%H:%M:%SZ')
df['InvoiceDate'] = df['InvoiceDate'].dt.tz_localize('UTC')
df['InvoiceDate_NYC'] = df['InvoiceDate'].dt.tz_convert('America/New_York')

print(df['InvoiceDate_NYC'].sample(5, random_state=42))
```

```
33553   2010-12-17 07:38:00-05:00
9427    2010-12-06 04:58:00-05:00
199     2010-12-01 08:21:00-05:00
12447   2010-12-06 11:57:00-05:00
39489   2








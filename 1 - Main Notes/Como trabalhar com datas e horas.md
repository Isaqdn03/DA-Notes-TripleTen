
**2024-10-29 18:21**

**Sprint:** [[Sprint3]]

**Topic:** #tipos-de-dados 

**Connections:** 

# **Como trabalhar com datas e horas**
### Main Topics of this Lesson:


 # Trabalhando com Datas e Horas em Python

## Formatos de Datas

- Diferentes países usam diferentes formatos de data, como dia/mês/ano (08/03/2010) ou mês/dia/ano (03/08/2010).
- O Excel pode lidar com ambos os formatos, mas pode haver problemas ao carregar dados de diferentes fontes.
- Para garantir que as datas e horas sejam armazenadas corretamente e possam ser usadas em cálculos, é necessário usar o formato datetime do Python.

## Conversão para datetime

- Vamos carregar o conjunto de dados `OnlineRetail.csv` e examinar a coluna `InvoiceDate`.
- A coluna `InvoiceDate` inicialmente tem o tipo de dados `object` (string).
- Usaremos o método `pd.to_datetime()` para converter os valores de string para o tipo `datetime`.

```python
import pandas as pd

df = pd.read_csv('/datasets/OnlineRetail.csv')
df['InvoiceDate'] = pd.to_datetime(df['InvoiceDate'], format='%Y-%m-%dT%H:%M:%SZ')
```

- O parâmetro `format=` especifica o padrão de formatação da string de data e hora.
- Alguns códigos de formatação comuns:
  - `%Y`: ano de 4 dígitos
  - `%m`: mês (01-12)
  - `%d`: dia do mês (01-31)
  - `%H`: hora no formato de 24 horas
  - `%M`: minutos (00-59)
  - `%S`: segundos (00-59)

%y é para ano com 2 dígitos
%Y é para ano com 4 dígitos (que é o nosso caso)

## Prática

Vamos praticar a conversão de strings de data e hora para o formato datetime:

```python
# Exemplo 1
string_date = '20-12-2002Z04:31:00'
datetime_date = pd.to_datetime(string_date, format='%d-%m-%YZ%H:%M:%S')
print(datetime_date)
# Saída: 2002-12-20 04:31:00

# Exemplo 2
string_date = '13/05/13 12:04:00'
datetime_date = pd.to_datetime(string_date, format='%m/%d/%y %H:%M:%S')
print(datetime_date)
# Saída: 2013-05-13 12:04:00
```

Excelente! Você aprendeu a converter strings de data e hora para o formato datetime usando o método `pd.to_datetime()` e os códigos de formatação apropriados.

## Verificando objetos datetime

Vamos verificar como os dados ficaram após a conversão:

```python
import pandas as pd

df = pd.read_csv('/datasets/OnlineRetail.csv')
df['InvoiceDate'] = pd.to_datetime(df['InvoiceDate'], format='%Y-%m-%dT%H:%M:%SZ')

print(df.head())
print()
df.info()
```

Saída:
```
  InvoiceNo StockCode                          Description  Quantity  \
0    536520     21123  SET/10 IVORY POLKADOT PARTY CANDLES       1.0   
1    536520     21124   SET/10 BLUE POLKADOT PARTY CANDLES       1.0   
2    536520     21122   SET/10 PINK POLKADOT PARTY CANDLES       1.0   
3    536520     84378        SET OF 3 HEART COOKIE CUTTERS       1.0   
4    536520     21985    PACK OF 12 HEARTS DESIGN TISSUES       12.0   

          InvoiceDate UnitPrice  CustomerID         Country
0 2010-12-01 12:43:00      1.25     14729.0  United Kingdom
1 2010-12-01 12:43:00      1.25     14729.0  United Kingdom
2 2010-12-01 12:43:00      1.25     14729.0







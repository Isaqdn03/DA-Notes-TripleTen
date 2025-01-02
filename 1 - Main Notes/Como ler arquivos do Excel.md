
2024-10-09 10:43

Sprint:[[Sprint3]]

Topic: #leitura-e-vizualizacao 


# Como ler arquivos do Excel
### Main Topics of this Lesson:
1. Ler arquivos execel usando `read_excel()`
2. como acessar outras paginas de uma planilha excel usando `sheet_name=`

## Como trabalhar com arquivos Excel
a funcao `read_excel()` ler arquivos do Excel, e por padrao esta funcao carrega a primeira planilha(primeira pagina) 

![[Image (19).png]]

==usando o codigo abaixo conseguimos acessar um arquivo excel como um dataframe==

```python
import pandas as pd

df = pd.read_excel('/datasets/product_reviews.xlsx')

print(df.head())

```


## O parametro `sheet_name=`
para acessar uma diferente pagina de uma planilha podemos chamar o parametro `sheet_name=` da seguinte maneira

especificando o nome da pagina no parametro

```python
import pandas as pd

df = pd.read_excel('/datasets/product_reviews.xlsx', sheet_name='reviewers')

print(df.head())
```

mas tambem podemos usar indices da planilha em vez do nome da pagina

`sheet_name=0`
mostra a primeira pagina da planilha
`sheet_name=1`
mostra a segunda  e assim por diante 






# References







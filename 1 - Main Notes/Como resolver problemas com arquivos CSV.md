
2024-10-08 12:51

Sprint: [[Sprint3]]

Topic: #leitura-e-vizualizacao


---
# Como resolver problemas com arquivos CSV
---


### Main Topics of this Lesson:
1. Ler arquivos CSV com `read_csv()`
2. o parametro `sep=`
3. os parametros `header=` e `names=`
4. parametro `decimal=`



#### 1. `read_csv()`

para ler um um arquivo CSV use `read_csv()`

```python
import pandas as pd
data = pd.read_csv('/datasets/gpp_modified.csv') print(data.head())
```

### 2. O Parametro `sep=`
remove delimitadores que nao sao virgulas

antes de usar o parametro sep=
```python
Afghanistan|Kajaki Hydroelectric Power Plant
Afghanistan|33 0|32 322|65 119|Hydro| 0 Afghanistan|Kandahar DOG|10 0|31 67|65 795|Solar| 1
Afghanistan|Kandahar JOL|10 0|31 623|65 792|Solar| 2 
Afghanistan|Mahipar Hydroelectric Power Plant ... 0|34 
556|69 4787|Hydro| 3 Afghanistan|Naghlu Dam 
Hydroelectric Power Pla... 0|34 641|69 717|Hydro| 4 
Afghanistan|Nangarhar (Darunta) Hydroelectric ... 55|34
4847|70 3633|Hydro|
```

como usar `sep=`
```python
import pandas as pd

data = pd.read_csv('/datasets/gpp_modified.csv', sep='|')

print(data.head())
```

```python
   Afghanistan       Kajaki Hydroelectric Power Plant Afghanistan   33,0   32,322   65,119  Hydro  Unnamed: 6
0  Afghanistan                                       Kandahar DOG   10,0    31,67   65,795  Solar         NaN
1  Afghanistan                                       Kandahar JOL   10,0   31,623   65,792  Solar         NaN
2  Afghanistan      Mahipar Hydroelectric Power Plant Afghanistan   66,0   34,556  69,4787  Hydro         NaN
3  Afghanistan   Naghlu Dam Hydroelectric Power Plant Afghanistan  100,0   34,641   69,717  Hydro         NaN
4  Afghanistan  Nangarhar (Darunta) Hydroelectric Power Plant ...  11,55  34,4847  70,3633  Hydro         NaN


```


### 3. Os parametros `header=` e `names=`
neste exemplo nao possuimos um cabecalho, entao pandas como padrao passa  primeira linha como que se fosse um cabecalho, mas nesse caso sao apenas a primeira linha sao apenas dados, mas podemos passar `header=None` para corrgir isso, falando para pandas nao usar a primeira linhas como dados

```python
import pandas as pd

data = pd.read_csv('/datasets/gpp_modified.csv', sep='|', header=None)

print(data.head())
```

```python
             0                                                  1      2        3        4      5    6    
0  Afghanistan       Kajaki Hydroelectric Power Plant Afghanistan   33,0   32,322   65,119  Hydro  NaN
1  Afghanistan                                       Kandahar DOG   10,0    31,67   65,795  Solar  NaN
2  Afghanistan                                       Kandahar JOL   10,0   31,623   65,792  Solar  NaN
3  Afghanistan      Mahipar Hydroelectric Power Plant Afghanistan   66,0   34,556  69,4787  Hydro  NaN
4  Afghanistan   Naghlu Dam Hydroelectric Power Plant Afghanistan  100,0   34,641   69,717  Hydro  NaN
```

agora como a primeira linha faz parte dos conjutos de dados, pandas, automaticamente passa os nomes de cabecalhos nao existentes para numeros inteiros (1,2,3,4, etc)

Agora podemos definir os nomes das colunas usando o parametro `names=`
criamos uma lista com os nomes de coluna primeiro e depois passamos o parametro dentro `read_csv()`

```python
import pandas as pd

column_names = [
    'country',
    'name',
    'capacity_mw',
    'latitude',
    'longitude',
    'primary_fuel',
    'owner'
]
data = pd.read_csv('/datasets/gpp_modified.csv', sep='|', header=None, names=column_names)

print(data.head())
```

```
       country                                              name capacity_mw latitude longitude primary_fuel owner     
0  Afghanistan      Kajaki Hydroelectric Power Plant Afghanistan        33,0   32,322    65,119        Hydro   NaN
1  Afghanistan                                      Kandahar DOG        10,0    31,67    65,795        Solar   NaN
2  Afghanistan                                      Kandahar JOL        10,0   31,623    65,792        Solar   NaN
3  Afghanistan     Mahipar Hydroelectric Power Plant Afghanistan        66,0   34,556   69,4787        Hydro   NaN
4  Afghanistan  Naghlu Dam Hydroelectric Power Plant Afghanistan       100,0   34,641    69,717        Hydro   NaN
```

### 4. Parametro `decimal=`
neste exemplo temos como separado decimala virgula o que e incorreto, python ler separadores decimais como ponto
entao usamos o parametro `decimal=` indicando qual separado decimal esta sendo usado, para que python substitua pelo `'.'` padrao

```python
import pandas as pd

column_names = [
    'country',
    'name',
    'capacity_mw',
    'latitude',
    'longitude',
    'primary_fuel',
    'owner'
]
data = pd.read_csv(
    '/datasets/gpp_modified.csv',
    sep='|',
    header=None,
    names=column_names,
    decimal=',',
)

print(data.head())
```


```
       country                                              name capacity_mw latitude longitude primary_fuel owner      
0  Afghanistan      Kajaki Hydroelectric Power Plant Afghanistan        33.0   32.322    65.119        Hydro   NaN
1  Afghanistan                                      Kandahar DOG        10.0    31.67    65.795        Solar   NaN
2  Afghanistan                                      Kandahar JOL        10.0   31.623    65.792        Solar   NaN
3  Afghanistan     Mahipar Hydroelectric Power Plant Afghanistan        66.0   34.556   69.4787        Hydro   NaN
4  Afghanistan  Naghlu Dam Hydroelectric Power Plant Afghanistan       100.0   34.641    69.717        Hydro   NaN
```












# References







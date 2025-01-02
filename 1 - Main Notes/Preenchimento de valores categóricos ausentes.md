
2024-10-10 15:03

Sprint:[[Sprint3]]

Topic: #tratamento-ausente-duplicados 


# **Preenchimento de valores categóricos ausentes**
### Main Topics of this Lesson:
1. Variáveis quantitativas e categóricas
2. O parâmetro `keep_default_na=`


## **1. Variáveis quantitativas e categóricas**

![[Pasted image 20241010164807.png]]

As variáveis quantitativas têm valores numéricos que podemos usar para cálculos aritméticos. Coisas como altura, peso, idade e receita são exemplos de variáveis quantitativas. Numeros inteiros ou flutuantes

Já as variáveis categóricas representam um conjunto de valores possíveis que uma observação específica pode ter. Coisas como cor, marca e modelo de um carro são exemplos de variáveis categóricas.

dependendo do tipo de dados em um DataFrame Podemos substituir valores ausentes por strings vazias

Para este exemplo os valores `NaN` na coluna `'email'` são substitutos para os endereços de e-mail de usuários que não assinaram a newsletter da loja.

Entao vamos substituir valores ausentes na coluna `email` por strings vazias usando o metodo `fillna()`  
**Explicacao em ([[Processamento de valores ausentes]])**

```python
import pandas as pd

df_logs = pd.read_csv('/datasets/visit_log.csv')

df_logs['email'] = df_logs['email'].fillna('')# escreva seu código aqui

print(df_logs.head())
```

```
      user_id   source       email  purchase
0  7141786820    other                     0
1  5644686960    email  c129aa540a         0
2  1914055396  context                     0
3  4099355752    other                     0
4  6032477554  context                     1
```


## **2. O parâmetro `keep_default_na=`**

Podemos fazer de forma geral um DataFrame Ler valores ausentes como Strings vazias, basta definirmos o parametro `keep_defaul_na=` como `False` Dentro da variavel que esta lendo o DataFrame:

```python
df_logs = pd.read_csv('/datasets/visit_log.csv',keep_default_na=False)

print(df_logs.head()) 
print() 
df_logs.info()
```

**Vamos obter este Resultado:**
![[Pasted image 20241010170926.png]]
Todos os valores ausentes do DataFrame agora sao Strings vazias





































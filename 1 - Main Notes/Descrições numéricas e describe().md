
2024-10-09 16:06

Sprint:[[Sprint3]]

Topic: #leitura-e-vizualizacao 


# Descrições numéricas e describe()
### Main Topics of this Lesson:
1. O metodo `describe()`
2. O metodo `describe()` em colunas nao numericas
3. O Parametro `include=`

## 1. O metodo `describe()`

usando o metodo `describe=`
![[Pasted image 20241009164907.png]]
 resultado:
![[Pasted image 20241009164925.png]]

![[Pasted image 20241009165049.png]]

![[Pasted image 20241009165143.png]]

































## 2. O metodo `describe()` em colunas nao numericas

Alem disso tambem podemos chamar o metodo `describe()` em uma unica coluna, basta especificar o nome da colunas que desejamos vizualizar, assim:

![[Pasted image 20241009165451.png]]

Resultado:

![[Pasted image 20241009165534.png]]

e podemos tambem chamar o metodo `describe()` em colunas nao numericas(que nao contem dados de numeros)

neste exemplo a coluna country contem nome de paises:

![[Pasted image 20241009165735.png]]

![[Pasted image 20241009165802.png]]

- `'count'`: O número de valores não nulos
- `'unique'`: O número de valores unívocos
- `'top'`: O valor que ocorre com mais frequência
- `'freq'`: O número de vezes que o valor mais frequente ocorre

## 3. O Parametro `include=`

podemos usar o parametro `include=` para dizer ao metodo `describe=`quais colunas queremos incluir no resultado, mas nesse caso nao passamos um lista de nomes de colunas mais sim o seu tipo de dado das colunas que queremos

no exemplo abaixo vamos obter apenas as informacoes de colunas nao numericas do conjuto de dados :

![[Pasted image 20241009170440.png]]
resultado:
![[Pasted image 20241009170456.png]]

e podemos tambem dizer `'all'` para obter informacoes fornecidas por `describe()` nas qualquer tipo de colunas que tivermos nos nossos conjuntos de dados

==se a coluna for numerica ira aparecer `NaN` para as informacoes que so aparecem para colunas nao numericas==
==e se a coluna for nao numerica, tambem ira aparece `NaN` para as informacoes que so aparecem para colunas numericas==

syntax:
`print(data.describe(include='all))`

resultado:

![[Pasted image 20241009171118.png]]


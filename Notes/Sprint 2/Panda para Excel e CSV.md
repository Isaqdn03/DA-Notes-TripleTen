
2024-10-07 22:18

Sprint:[[Sprint2]]

Topic: #dataframe-pandas 


# Panda para Excel e CSV
# 4.4 **Pandas para Excel e arquivos CSV**

## **Leitura de arquivos CSV**

Você estará lidando principalmente com arquivos CSV (valores separados por vírgula).

Conforme discutido anteriormente, um DataFrame requer dados e nomes de colunas, ambos fornecidos em arquivos CSV:

- A primeira linha contém os nomes das colunas.
- Cada linha subsequente contém os dados correspondentes a uma linha na tabela.

**A IMAGEM DEMONSTRA COMO CSV E CONVERTIDO EM UM DATAFRAME PANDAS:**

![https://practicum-content.s3.amazonaws.com/resources/11.4_1PT_1690266076.png](https://practicum-content.s3.amazonaws.com/resources/11.4_1PT_1690266076.png)

para ler uma arquivo csv usando pandas, precisamos chamar a funcao `read_csv()` esta funcao so requer um argumento que e o caminho do arquivo

```python
import pandas as pd

df = pd.read_csv('/datasets/music_log_chpt_11.csv') 
# o argumento é o caminho do arquivo
```

O caminho difere dependendo de dois fatores:

1. O **sistema operacional** determina seu formato.
    - No Windows, o caminho é geralmente escrito com barras invertidas: `'C:\\catalog\\file.csv'`
    - Nos sistemas operacionais macOS e Linux, ele é escrito com barras: `'/catalog/files.csv'`
2. Se o caminho é **relativo** ou **absoluto**.

- Caminho absoluto: Começa no diretório raiz. Windows: `'C:\\catalog\\file.csv'`. Linux/macOS: `'/catalog/file.csv'`.
    
- Caminho relativo: Começa no diretório atual. Pode ser apenas o nome do arquivo ou incluir subdiretórios, dependendo da localização do programa.**Leitura de arquivos Excel**
    
    ![https://practicum-content.s3.amazonaws.com/resources/11.4_2PT_1690266101.png](https://practicum-content.s3.amazonaws.com/resources/11.4_2PT_1690266101.png)
    

para criar um DataFrame a partir de um arquivo excel e similiar ao processo para um arquivo CSV, o pandas fornece uma funcao interta r`ead_excel()` para ler arquivos excel.

```python
import pandas as pd

df = pd.read_excel('/datasets/music_log.xlsx') 
# o argumento é o caminho do arquivo
```

exetensoes comuns de um arquivo excel `xlsx`, `.xls`, `.xlsm`, `.xlsb` e `.xltx`.

Maneiras de criar um DataFrame

- Criar o DataFrame a partir de uma lista, como fizemos anteriormente para os países e suas capitais.
- Ler um arquivo CSV usando a função integrada da pandas.
- Ler um arquivo do Excel

## **`head()` e `tail()`**

- `head()` exibe as primeiras linhas de uma
    
- `tail()` exibe as últimas linhas.
    
    EXEMPLO `head()`
    
    ```python
    import pandas as pd
    
    df = pd.read_csv('/datasets/music_log_chpt_11.csv')
    
    print(df.head())
    ```
    
    `head()` exibe as primeiras 5 linhas por padrão passando um argumento que especifica o número desejado podemos escolher quantas linhas desejamos ver:
    
    ```python
    import pandas as pd
    
    df = pd.read_csv('/datasets/music_log_chpt_11.csv')
    
    print(df.head(3))
    
    ```
    
    O método `tail` funciona de maneira semelhante, mas exibe as últimas linhas. E dessa forma podemos verificar as últimas 3 linhas de um conjunto de dados:



# References







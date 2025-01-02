
2024-10-07 22:06

Sprint:[[Sprint2]]

Topic:  #dataframe-pandas



# 4.2 **DataFrames na Biblioteca Pandas:**

## O que e uma biblioteca

**Definicao:** Uma biblioteca em programação é um conjunto organizado de códigos pré-escritos que oferecem funcionalidades específicas, permitindo aos desenvolvedores reutilizarem soluções comuns sem precisar reescrever o código do zero. Essas bibliotecas encapsulam operações complexas em funções simples, tornando o desenvolvimento mais eficiente e reduzindo erros.

**Minha definicao: e um conjunto de codigos ja pre escritos que nos permite reutilizar funcoes comuns sem precisar escrever denovo**

## O que e pandas

**DOCUMENTACAO PANDAS:**

[pandas documentation — pandas 2.2.3 documentation](https://pandas.pydata.org/pandas-docs/stable/)

**Definição:** Pandas é uma biblioteca de software de código aberto escrita para a linguagem de programação Python. Ela fornece estruturas de dados de alto desempenho e fáceis de usar, além de ferramentas de análise de dados. Pandas é particularmente útil para manipulação e análise de dados estruturados.

**Principais características:**

- Obter dados de várias fontes e uni-los.
- Resolver problemas com dados, como remover duplicados ou preencher valores ausentes
- Adicionar, remover ou modificar dados da tabela
- Agrupamento de dados e cálculo de estatísticas para grupos

**Minha definição: Pandas e um biblioteca python, para o processamento de dados que nos permite, analisar, limpar, e editar.**

## Por que pandas e importante

pois a biblioteca pandas, simplifica e acelera o trabalho de analise de dados

O Pandas é importante porque:

- Simplifica e acelera o trabalho de análise de dados
- Oferece estruturas de dados de alto desempenho e fáceis de usar
- Permite manipulação e análise eficiente de dados estruturados
- Fornece ferramentas para lidar com problemas comuns de dados, como remoção de duplicatas e preenchimento de valores ausentes
- Facilita a obtenção e união de dados de várias fontes
- Possibilita o agrupamento de dados e cálculo de estatísticas para grupos

Essa explicação mais detalhada abrange melhor as principais razões pelas quais o Pandas é uma biblioteca tão importante e amplamente utilizada na análise de dados com Python.

## O que DataFrame

**definicao:** Um DataFrame é uma estrutura de dados bidimensional, sendo essencialmente uma tabela, na qual cada elemento possui duas coordenadas: uma linha e uma coluna. As linhas são acessadas por **índices** e as **colunas** por seus nomes. **Minha definicao:** essencicalmente e uma tabela, uma estrutura bidimencional, que pode ser acessada atraves com indices (para as linhas) e colunas (com nomes especificos, dependendo da tabela)

![https://practicum-content.s3.amazonaws.com/resources/11.2_1PT_1690265860.png](https://practicum-content.s3.amazonaws.com/resources/11.2_1PT_1690265860.png)

## Documentacao de datos

as colunas sao semelhantes a variaveis, pois dao uma pista sobre os datos contidos nelas, porem nomes sozinho nao fornecem uma compreesao completa do conjunto de dados.

geralmente um conjutos de datos contem uma documentacao que descrever cada coluna, e nos ajuda a entender mais a fundo a estrutura de dados na qual estamos trabalhando

**Exemplo:**

- `user_id` — identificação única do usuário
- `total play` — a quantidade de tempo (em segundos) que o usuário tocou a música
- `Artist` — o nome do artista
- `genre` — o gênero da música (rock, pop, eletrônico, clássico, etc.)
- `track` — o nome da música

## **Atributos da estrutura DataFrame**

Resumo da definição de atributos no contexto do Pandas:

- Atributos são propriedades de um objeto DataFrame que fornecem informações sobre os dados contidos nele(na tabela)
    
- Eles permitem acessar informações gerais sobre o conjunto de dados sem manipulá-los
    
- São acessados usando a notação de ponto e definem o estado do objeto
    
- Oferecem uma maneira conveniente de obter uma visão geral da estrutura e do conteúdo do DataFrame
    
- Facilitam o acesso a informações gerais do conjunto de dados quando este é armazenado como um objeto DataFrame
    
    Aqui estão alguns exemplos:
    
    - `dtypes` nos permite visualizar os tipos de dados dos valores em cada coluna.
    - `columns` pode ser usado para exibir os nomes das colunas.
    - `shape` é usado para entender o tamanho da tabela.

### TIPOS DE DADOS EM PANDAS:

||Python type|Pandas type|
|---|---|---|
|string|str|object|
|integer|int|int64|
|floating-point number|float|float64|
|logical data type|bool|bool|

### SHAPE

variável `df` contiver um DataFrame, podemos verificar seu tamanho usando o atributo `shape` da seguinte maneira:

![https://practicum-content.s3.amazonaws.com/resources/11.2_2PT_1690265888.png](https://practicum-content.s3.amazonaws.com/resources/11.2_2PT_1690265888.png)

### DTYPES

uma coluna pode conter valores de diferentes tipos, o atibuto `dtypes` dira exatamente qual sao eles

`print(df.dtypes)`

como saida teremos:

![https://practicum-content.s3.amazonaws.com/resources/2pt_1694774261.png](https://practicum-content.s3.amazonaws.com/resources/2pt_1694774261.png)

### COLUMNS

armazena uma lista contento todos os nomes da coluna, e ja que os nomes das colunas sao uma string, podemos ver no resultado que cada nome tem um tipo `object`

`print(df.columns)`

![https://practicum-content.s3.amazonaws.com/resources/image_1699962287.png](https://practicum-content.s3.amazonaws.com/resources/image_1699962287.png)

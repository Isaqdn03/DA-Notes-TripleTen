
**2025-03-01 16:47**

**Sprint:** [[Sprint7]]

**Topic:** #SQL-para-trabalhar-com-dados 

**Connections:** 

---
# **Convertendo Tipos de Dados em SQL**

### Exemplo Prático: Sistema de Avaliação de Livros

```sql
SELECT
    AVG(rating) AS average
FROM
    books;
```

> **Problema:** Esta consulta falha porque o campo 'rating' está armazenado como string, mesmo contendo valores numéricos (ex: "4.2", "4.16", etc.)

## Soluções para Conversão de Tipos

### 1. Usando CAST

```sql
CAST (column_name AS data_type)
```

### 2. Usando Sintaxe Alternativa (::)

```sql
column_name :: data_type
```

### Exemplo Prático de Conversão

```sql
-- Método 1: Usando CAST
SELECT
    AVG(CAST(rating AS real)) AS average
FROM
    books;

-- Método 2: Usando ::
SELECT
    AVG(rating::real) AS average
FROM
    books;
```

**Resultado:** 4.139333

## Tipos de Dados no PostgreSQL

### Tipos Numéricos

|Tipo|Descrição|Faixa/Precisão|
|---|---|---|
|integer|Números inteiros|-2147483648 a 2147483647|
|real|Números decimais|Até 6 casas decimais|

### Tipos de String

|Tipo|Descrição|Exemplo|
|---|---|---|
|varchar(n)|String de comprimento variável|varchar(50)|
|text|String sem limite de tamanho|texto longo|

### Tipos de Data e Hora

|Tipo|Uso|Exemplo|
|---|---|---|
|timestamp|Data e hora|'2024-03-01 14:30:00'|
|date|Apenas data|'2024-03-01'|

### Tipo Lógico

|Tipo|Valores Possíveis|
|---|---|
|boolean|TRUE, FALSE, NULL|

## Melhores Práticas e Considerações

### Quando Usar Conversão de Tipos

- Para operações matemáticas em campos armazenados como texto
- Para corrigir problemas de design de banco de dados
- Para garantir compatibilidade em operações específicas

### Pontos de Atenção

1. **Precisão de Dados**
    
    - Considere a precisão necessária ao converter entre tipos numéricos
    - Use 'real' para números com casas decimais
2. **Tratamento de Erros**
    
    - Sempre valide os dados antes da conversão
    - Considere o impacto da conversão em NULL values

## Resumo Geral

A conversão de tipos em SQL é uma habilidade essencial para trabalhar com bancos de dados, especialmente quando lidamos com:

- Correção de problemas de design
- Operações matemáticas em campos de texto
- Análise de dados

**Principais Aprendizados:**

- Duas sintaxes para conversão: CAST e ::
- Diferentes tipos de dados disponíveis no PostgreSQL
- Importância da validação e tratamento de erros
- Casos práticos de uso em sistemas reais

_Recursos Adicionais:_

> Para mais informações sobre tipos de dados no PostgreSQL, consulte:
> 
> - PostgreSQL Tutorial
> - Documentação oficial do PostgreSQL


# IN ACTION

1. Escreva uma consulta para calcular o peso médio (`weight`) das mercadorias da tabela `products_data_all` cujo peso está em onças (filtre a tabela para o campo `units` igual a `'oz'`). Nomeie a variável como `average`. Converta o tipo de dados na coluna `weight` para que ela contenha números de ponto flutuante.
```PYTHON
SELECT 
	AVG(weight::real ) as average
FROM
    products_data_all
WHERE 
    units = 'oz'
```

```
|average|
|23.5541|
```

2. Escreva uma consulta para achar o peso máximo do produto na categoria `'milk'`. Use o operador `CAST AS` e nomeie a variável `max_weight`.
```python
SELECT 
    MAX(CAST(weight AS real)) AS max_weight
FROM
    products_data_all
WHERE 
    CATEGORY = 'milk'
```

```
|max_weight|
|96|
```

3. Converta o campo `date` da tabela `transactions` para o tipo date. Nomeie o campo resultante como `date_no_time`.
```python
SELECT 
    CAST (date AS date) AS date_no_time
FROM
    transactions;
```

```
|date_no_time|
|2019-06-26|
|2019-06-26|
|2019-06-26|
|2019-06-12|
|2019-06-12|
...
...
```

4. Encontre as datas (`date`) das últimas e primeiras compras na tabela `transactions`. Nomeie as colunas `max_date` e `min_date`, respectivamente. Não se esqueça de converter as datas para o tipo `date`.

```python
SELECT 
    MAX(CAST(date AS date)) AS max_date,
    MIN(CAST(date AS date)) AS min_date
FROM
    transactions;
```

```
|max_date|min_date|
|2019-07-01|2019-06-01|
```
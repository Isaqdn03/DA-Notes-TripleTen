
**2025-03-01 14:46**

**Sprint:**[[Sprint7]]

**Topic:** #SQL-para-trabalhar-com-dados 

**Connections:** 

---
# **Funções de Agregação em SQL**

## Introdução

As funções de agregação em SQL são ferramentas poderosas que permitem realizar cálculos em conjuntos de dados, retornando um único valor resumido. Elas são essenciais para análise de dados e geração de relatórios estatísticos.

> **Definição**: Funções de agregação coletam todos os objetos dentro de um grupo para calcular um único valor de resumo.

## Sintaxe Básica

```sql
SELECT
    AGGREGATE_FUNCTION(field) AS alias_name
FROM
    TABLE;
```

**Componentes principais:**

- `AGGREGATE_FUNCTION`: Nome da função (COUNT, SUM, AVG, etc.)
- `field`: Campo/coluna para agregação
- `AS alias_name`: Nome personalizado para a coluna de resultado

## Tipos de Funções de Agregação

### 1. COUNT - Contagem de Registros

**Variações do COUNT:**

- `COUNT(*)`: Total de linhas
- `COUNT(column)`: Total de valores não-nulos em uma coluna
- `COUNT(DISTINCT column)`: Total de valores únicos não-nulos

```sql
-- Exemplo básico
SELECT COUNT(*) AS cnt
FROM books;
-- Resultado: 30

-- Contagem com filtro
SELECT COUNT(*) AS cnt
FROM books
WHERE author = 'Dean Koontz';
-- Resultado: 4

-- Comparação de diferentes tipos de COUNT
SELECT
    COUNT(*) AS total_rows,
    COUNT(publisher_id) AS publisher_count,
    COUNT(DISTINCT publisher_id) AS unique_publishers
FROM books;
-- Resultados:
-- total_rows: 30
-- publisher_count: 28
-- unique_publishers: 19
```

### 2. SUM - Soma de Valores

**Características:**

- Funciona apenas com valores numéricos
- Ignora valores NULL
- Retorna a soma total dos valores

```sql
SELECT SUM(pages) AS total_pages
FROM books;
-- Resultado: 16812
```

### 3. AVG - Média de Valores

**Importantes considerações:**

- Requer dados numéricos
- Ignora valores NULL no cálculo
- Retorna a média aritmética

```sql
SELECT AVG(pages) AS average_pages
FROM books;
-- Resultado: 560.4
```

### 4. MIN e MAX

- Encontram valores extremos em um conjunto de dados
- Funcionam com dados numéricos e não numéricos
- Ignoram valores NULL

## Tabela Comparativa de Funções de Agregação

|Função|Propósito|Tipo de Dados|Tratamento de NULL|
|---|---|---|---|
|COUNT(*)|Total de linhas|Qualquer|Inclui NULL|
|COUNT(column)|Total de valores|Qualquer|Ignora NULL|
|SUM|Soma total|Numérico|Ignora NULL|
|AVG|Média|Numérico|Ignora NULL|
|MIN|Menor valor|Qualquer|Ignora NULL|
|MAX|Maior valor|Qualquer|Ignora NULL|

## Práticas Recomendadas

1. **Nomenclatura clara**:
    
    - Use aliases descritivos com AS
    - Evite nomes automáticos de colunas
2. **Validação de dados**:
    
    - Verifique o tipo de dados antes de usar AVG/SUM
    - Considere o impacto dos valores NULL
3. **Otimização**:
    
    - Use COUNT(*) para contagem total de linhas
    - Use COUNT(coluna) quando precisar contar valores não-nulos

## Aplicações Práticas

1. **Análise de Biblioteca**:
    
    - Total de livros por autor
    - Média de páginas por gênero
    - Classificação média dos livros
2. **Métricas de Publicação**:
    
    - Contagem de livros por editora
    - Média de classificação por autor
    - Total de páginas publicadas

## Resumo Geral

As funções de agregação são fundamentais para análise de dados em SQL, permitindo:

- Cálculos estatísticos básicos
- Análises resumidas de grandes conjuntos de dados
- Geração de relatórios consolidados
- Métricas de desempenho e análise

**Pontos-chave para lembrar:**

- Cada função tem um propósito específico
- O tratamento de NULL varia por função
- A escolha da função impacta diretamente o resultado
- Aliases melhoram a legibilidade dos resultados











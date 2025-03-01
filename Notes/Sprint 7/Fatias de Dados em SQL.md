
**2025-02-27 18:20**

**Sprint:** [[Sprint7]]

**Topic:** #SQL-para-trabalhar-com-dados 

**Connections:** 

---
# **Fatias de Dados em SQL**

Uma fatia de dados em SQL permite filtrar informações irrelevantes, mantendo apenas os dados necessários para análise. Similar ao método `query()` em Python, o SQL oferece uma maneira poderosa de realizar essa filtragem usando o comando `WHERE`.

## Estrutura Básica da Consulta

### Sintaxe Fundamental

```sql
SELECT
    column_1,
    column_2
FROM
    table_name
WHERE
    condition;
```

### Ordem de Processamento

1. **WHERE** (primeiro a ser processado)
2. **FROM**
3. **SELECT**

> **Importante**: O bloco WHERE é mais abrangente que SELECT, pois filtra os dados da tabela inteira antes da seleção das colunas.

## Operadores de Comparação

|Operador|Significado|
|---|---|
|=|igual a|
|<>, !=|diferente de|
|>|maior que|
|<|menor que|
|>=|maior ou igual a|
|<=|menor ou igual a|

### Exemplo Prático

```sql
SELECT
    name,
    author
FROM
    books
WHERE
    author = 'Stephen King';
```

## Operadores Lógicos

### Tipos e Funcionamento

- **AND**: Seleciona linhas onde ambas as condições são verdadeiras
- **OR**: Seleciona linhas onde uma ou ambas as condições são verdadeiras
- **NOT**: Seleciona linhas onde a condição é falsa

### Exemplo com Múltiplas Condições

```sql
SELECT
    name,
    author,
    date_pub,
    pages
FROM
    books
WHERE
    date_pub > '1995-12-31'
    AND date_pub < '2001-01-01';
```

## Operador BETWEEN

### Uso e Características

- Inclui os valores limite na seleção
- Mais conciso que usar operadores de comparação
- Útil para intervalos de datas, números ou outros valores ordenados

```sql
SELECT
    name,
    author,
    date_pub,
    pages
FROM
    books
WHERE
    date_pub BETWEEN '1996-01-01' AND '2000-12-31';
```

## Operador IN

### Funcionalidade

- Permite selecionar valores de uma lista específica
- Mais eficiente que múltiplos OR
- Pode ser usado com NOT para exclusão

### Sintaxe para Diferentes Tipos de Dados

- Números: `IN (3, 7, 9)`
- Strings: `IN ('valor1', 'valor2', 'valor3')`
- Datas: `IN ('aaaa-mm-dd', 'aaaa-mm-dd')`

### Exemplo

```sql
SELECT
    name,
    genre
FROM
    books
WHERE
    genre IN ('Humor', 'Fantasy', 'Young Adult');
```

# Resumo Geral

**Pontos-Chave:**

- O SQL oferece diversos operadores para criar fatias precisas de dados
- A ordem de processamento (WHERE → FROM → SELECT) é crucial para entender como as consultas funcionam
- Operadores podem ser combinados para criar filtros complexos
- BETWEEN e IN são alternativas mais concisas para condições múltiplas
- A escolha entre diferentes operadores depende da clareza e eficiência desejadas

_Aplicações Práticas:_

- Análise de dados de vendas por período
- Filtragem de produtos por categoria
- Segmentação de clientes por características
- Análise de performance por região ou período
- Geração de relatórios customizados










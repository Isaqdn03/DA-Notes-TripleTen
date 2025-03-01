
**2025-02-26 19:20**

**Sprint:** [[Sprint7]]

**Topic:** #SQL-para-trabalhar-com-dados 

**Connections:** 

---
# Instrução SQL

<iframe src="file:///D:/Generic%20Downloads/markmap%20(1).html" width="100%" height="600"></iframe>
## Definição e Propósito

SQL é uma linguagem de computação especializada projetada para:

- Gerenciar dados em bancos de dados relacionais
- Realizar consultas estruturadas
- Manipular e recuperar dados de forma eficiente

## Características Básicas da Sintaxe SQL

### Comentários

**Comentários de linha única:**

```sql
-- Este é um comentário de linha única em SQL
```

**Comentários de múltiplas linhas:**

```sql
/* Este é um comentário
   que pode ocupar
   várias linhas */
```

### Convenções de Formatação

|Elemento|Convenção|Obrigatoriedade|
|---|---|---|
|Ponto e vírgula (;)|Ao final das instruções|Recomendado|
|Palavras-chave|MAIÚSCULAS|Opcional|
|Quebras de linha|Após palavras-chave|Opcional|
|Indentação|Após operadores principais|Recomendado|

## Instruções SQL Básicas

### Estrutura do SELECT

A instrução SELECT é fundamental para recuperar dados e segue esta estrutura básica:

```sql
SELECT
    column_1,
    column_2,
    column_3
FROM
    table_name;
```

#### Elementos principais:

- **SELECT**: Especifica as colunas desejadas
- **FROM**: Indica a tabela de origem dos dados
- **Colunas**: Lista de colunas separadas por vírgula

### Variações do SELECT

1. **Seleção de colunas específicas:**

```sql
SELECT
    name,
    author
FROM
    books;
```

1. **Seleção de todas as colunas:**

```sql
SELECT
    *
FROM
    books;
```

## Exemplo Prático: Tabela de Livros

### Estrutura da Tabela

A tabela `books` contém as seguintes colunas:

- name (título do livro)
- book_id (identificador único)
- genre (gênero)
- author (autor)
- date_pub (data de publicação)
- pages (número de páginas)
- rating (avaliação)
- publisher_id (identificador da editora)

### Exemplos de Consultas

**Consulta de autor e título:**

```sql
SELECT
    name,
    author
FROM
    books;
```

_Resultado: Retorna uma lista com nome do livro e seu respectivo autor_

**Consulta completa:**

```sql
SELECT
    *
FROM
    books;
```

_Resultado: Retorna todos os dados de todos os livros_

## Boas Práticas

1. **Formatação**
    
    - Use indentação consistente
    - Alinhe colunas verticalmente
    - Adicione quebras de linha após operadores
2. **Convenções**
    
    - Use ponto e vírgula ao final das instruções
    - Mantenha palavras-chave em maiúsculas
    - Mantenha consistência no estilo
3. **Organização**
    
    - Agrupe colunas relacionadas
    - Mantenha a legibilidade do código
    - Use comentários quando necessário

# Resumo Geral

O SQL é uma linguagem fundamental para trabalhar com bancos de dados relacionais, com uma sintaxe própria e bem estruturada. Suas principais características incluem:

- Sintaxe clara e objetiva
- Comandos estruturados e intuitivos
- Flexibilidade na formatação
- Capacidade de recuperar dados de forma precisa

A instrução SELECT é a base para consultas em SQL, permitindo recuperar dados específicos ou completos de uma tabela. O exemplo prático com a tabela de livros demonstra a aplicação real dessas consultas em um cenário de banco de dados de uma biblioteca ou livraria.

_Pontos-Chave para Lembrar:_

- Use ponto e vírgula ao final das instruções
- Mantenha boa formatação para legibilidade
- Escolha colunas específicas em vez de usar * quando possível
- Siga as convenções de formatação consistentemente











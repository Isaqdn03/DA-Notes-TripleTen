
**2025-02-26 19:05**

**Sprint:** [[Sprint7]]

**Topic:** #SQL-para-trabalhar-com-dados 

**Connections:** 

---
# **Tabelas**
## 1. Introdução às Tabelas

Uma **tabela** é uma estrutura fundamental em bancos de dados, consistindo em um conjunto organizado de linhas e colunas que armazenam dados de forma estruturada.

> **Definição**: Uma tabela é uma estrutura bidimensional que organiza dados em linhas e colunas, permitindo o armazenamento e acesso eficiente às informações.

### Exemplo Prático: Silicon Valley

Para ilustrar o conceito, utilizaremos uma tabela de funcionários da empresa fictícia Pied Piper:

|Número|Nome e Sobrenome|Posição|Pontos Fortes|Pontos Fracos|
|---|---|---|---|---|
|1|Donald Dunn|Gerente de Operações|Gerenciamento de processos|Fala alemão dormindo|
|2|Dinesh Chugtai|Desenvolvedor Java|Programação|-|

## 2. Componentes de uma Tabela

### 2.1 Campos (Colunas)

- **Definição**: Campos são as colunas da tabela que definem as características ou atributos dos objetos armazenados
- **Características**:
    - Possuem nome unívoco (único)
    - Têm tipo de dados específico
    - Representam uma categoria de informação

### 2.2 Registros (Linhas)

- **Definição**: Registros são as linhas da tabela que contêm informações sobre um objeto específico
- **Características**:
    - Cada linha representa uma entidade única
    - Contém valores para cada campo definido
    - Deve ser identificável de forma única

### 2.3 Células

- **Definição**: Célula é a interseção entre um registro e um campo
- **Características**:
    - Contém um único valor
    - Representa um dado específico do registro
    - Deve respeitar o tipo de dados do campo

## 3. Chaves Primárias

### 3.1 Chave Primária Simples

- **Definição**: Campo único que identifica inequivocamente cada registro
- **Características**:
    - Valores devem ser unívocos (únicos)
    - Não pode conter valores nulos
    - Exemplo: Campo "Número" na tabela de funcionários

### 3.2 Chave Primária Composta

- **Definição**: Combinação de múltiplos campos que juntos identificam uniquamente um registro
- **Características**:
    - Valores individuais podem se repetir
    - A combinação dos valores deve ser única
    - Exemplo: Combinação de "Nome e sobrenome" + "Posição"

## 4. Aplicação Prática

### Exemplo de Estruturação

Uma tabela bem estruturada deve:

1. Ter campos claramente definidos
2. Possuir uma chave primária adequada
3. Manter dados consistentes
4. Facilitar a busca e manipulação dos dados

### Representação Visual de uma Tabela

```
+------------------+
|     TABELA      |
+------------------+
| Campo 1 | Campo 2|  ← Campos (Colunas)
|---------|--------|
| Valor 1 | Valor 2|  ← Registro (Linha)
|---------|--------|
|   ↑               
|  Célula
```

## 5. Resumo

**Pontos-Chave:**

- Uma tabela é composta por campos (colunas) e registros (linhas)
- Células são as interseções entre campos e registros
- Toda tabela necessita de uma chave primária (simples ou composta)
- A estrutura deve garantir a unicidade e identificação dos registros

### Relações entre Conceitos

- Campos → definem a estrutura
- Registros → contêm os dados
- Células → armazenam valores específicos
- Chaves Primárias → garantem a unicidade










**2025-02-26 18:50**

**Sprint:** [[Sprint7]]

**Topic:** #SQL-para-trabalhar-com-dados

**Connections:** 

---
# **Bancos de Dados e Tabelas**

## Introdução aos Bancos de Dados

Um **banco de dados** é um sistema organizado para armazenamento estruturado de informações. Sua principal função é permitir o acesso eficiente e gerenciamento sistemático dos dados.

### Analogia do Sistema de Arquivos

> "Imagine que um escritório tenha um armário com caixas marcadas da seguinte forma: 'Funcionários', 'Relatórios' e 'Fornecedores'."

Esta analogia ilustra perfeitamente a estrutura básica de um banco de dados:

|Elemento Físico|Elemento do Banco de Dados|
|---|---|
|Armário|Banco de Dados|
|Caixas|Tabelas|
|Documentos|Registros|
|Informações no documento|Campos|

## Conceitos Fundamentais

### Entidades

- **Definição**: Grupos de objetos que compartilham características comuns
- **Exemplo**: A caixa "Funcionários" representa uma entidade
- **Características**:
    - Estrutura consistente
    - Atributos comuns
    - Identificação única

### Objetos

- **Definição**: Instâncias individuais de uma entidade
- **Exemplo**: O perfil do Senhor Peterson é um objeto da entidade "Funcionários"
- **Características**:
    - Dados específicos
    - Valores únicos
    - Pertence a uma entidade

## Bancos de Dados Relacionais

### Características Principais

1. Organização em tabelas
2. Relacionamentos entre dados
3. Estrutura consistente

### Relacionamentos

_As tabelas em um banco de dados relacional se conectam de maneira similar aos documentos físicos:_

- Funcionários ↔ Fornecedores
- Funcionários ↔ Relatórios
- Fornecedores ↔ Relatórios

## Sistema de Gerenciamento de Banco de Dados (SGBD)

### Função do SGBD

> "Para os bancos de dados, essa secretária é um SGBD"

**Responsabilidades principais:**

- Criar bancos de dados
- Gerenciar tabelas
- Editar conteúdo
- Exibir informações
- Manter integridade dos dados

### PostgreSQL

- Sistema de gerenciamento de banco de dados popular
- Código aberto
- Documentação disponível em: https://www.postgresql.org/docs/
# Resumo Geral

Os bancos de dados são sistemas fundamentais para o armazenamento organizado de informações, funcionando de maneira similar a um sistema de arquivamento físico, mas com maior eficiência e capacidade. Através de entidades e objetos, os dados são estruturados em tabelas relacionais, permitindo conexões complexas entre diferentes tipos de informação. O SGBD atua como um gerenciador central, facilitando todas as operações necessárias para manter e utilizar o banco de dados eficientemente. O PostgreSQL é uma implementação específica de SGBD que oferece todas essas funcionalidades em um pacote robusto e bem documentado.

_Pontos-Chave:_

- Organização estruturada de dados
- Relacionamentos entre diferentes tipos de informação
- Gerenciamento centralizado através do SGBD
- Importância da documentação e padronização









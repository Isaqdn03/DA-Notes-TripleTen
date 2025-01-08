
**2025-01-06 19:10**

**Sprint:** [[Sprint5]]

**Topic:** #intro-CLI 

**Connections:** 

---
# **Pipes**

# Pipes na Command Line Interface (CLI)

## Introdução aos Pipes
Os pipes são uma funcionalidade fundamental da CLI que permite a transferência de dados entre diferentes comandos. Eles funcionam como uma esteira transportadora em uma fábrica, onde:
- Dados fluem em uma direção específica
- Conectam múltiplos comandos
- Permitem processamento sequencial

## Funcionamento Básico
O operador pipe (`|`) é usado para conectar comandos, onde:
- A saída do comando à esquerda se torna a entrada do comando à direita
- Múltiplos pipes podem ser encadeados
- Cada comando processa os dados sequencialmente

## Exemplos Práticos

### Listagem Básica de Diretório
```bash
ls
```
Este comando lista todos os arquivos e diretórios no diretório atual.

Saída esperada:
```
nltk_data  work
```

### Filtragem com Grep
```bash
ls | grep "data"
```
Este comando combina:
1. `ls`: lista o conteúdo do diretório
2. `|`: passa o resultado para o próximo comando
3. `grep "data"`: filtra as linhas que contêm a palavra "data"

Saída esperada:
```
nltk_data
```

### Seleção da Última Linha
```bash
ls | tail -1
```
Este comando combina:
1. `ls`: lista o conteúdo do diretório
2. `|`: passa o resultado para o próximo comando
3. `tail -1`: seleciona apenas a última linha do resultado

Saída esperada:
```
work
```

## Pontos-Chave
- Os pipes permitem combinar múltiplos comandos de forma eficiente
- A saída de um comando se torna automaticamente a entrada do próximo
- É possível criar sequências complexas de processamento usando pipes
- A analogia com a esteira transportadora ajuda a entender o fluxo de dados

# Resumo
Os pipes são uma ferramenta poderosa na CLI que permite a conexão de múltiplos comandos, facilitando o processamento sequencial de dados. Através de exemplos práticos, vimos como combinar comandos básicos como `ls`, `grep` e `tail` para realizar tarefas mais complexas de filtragem e seleção de dados.










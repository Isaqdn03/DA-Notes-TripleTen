
**2025-02-10 19:02**

**Sprint:** [[Sprint6]]

**Topic:** #python-em-mais-detalhes 

**Connections:** 

---
# **Funções - parâmetros e valores padrão**

## Conceitos Fundamentais de Funções

### Definição e Estrutura Básica
Uma função em Python é um bloco de código reutilizável que executa uma tarefa específica. A estrutura básica inclui:
- Nome da função
- Parâmetros (opcional)
- Corpo da função
- Valor de retorno (opcional)

### Exemplo Básico de Função
```python
def filter_by_year(data, year):
    filtered_result = []
    for row in data:
        if row[2] > year:
            filtered_result.append(row)
    return filtered_result
```

*Explicação:*
- A função recebe dois parâmetros: `data` e `year`
- Cria uma lista vazia para armazenar resultados
- Filtra filmes com ano superior ao especificado
- Retorna a lista filtrada

## Valores Padrão em Parâmetros

### Conceito de Valores Padrão
> Um valor padrão é um valor predefinido que será usado caso nenhum argumento seja fornecido para o parâmetro durante a chamada da função.

### Exemplo com Omelete
```python
def omelet(eggs_number=2):
    result = 'A omelete está pronta! Ovos usados: ' + str(eggs_number)
    return result

print(omelet())  # Usando valor padrão
```

**Saída:**
```
A omelete está pronta! Ovos usados: 2
```

### **Importante!**
**Ao definir uma função, parâmetros opcionais devem ser colocados após os obrigatórios, ou seja, aqueles que não têm valores padrão atribuídos a eles. Caso contrário, você vai obter um erro quando chamar a função.**
### Múltiplos Parâmetros com Valores Padrão
```python
def omelet(cheese, eggs_number=2):
    result = 'A omelete está pronta! Ovos usados: ' + str(eggs_number)
    if cheese == True:
        result = result + ', com queijo'
    else:
        result = result + ', sem queijo'
    return result

print(omelet(False))
```

**Saída:**
```
A omelete está pronta! Ovos usados: 2, sem queijo
```

## Regras e Boas Práticas

### Ordem dos Parâmetros
| Tipo de Parâmetro | Posição | Exemplo |
|-------------------|----------|---------|
| Obrigatórios | Primeiro | `def func(obrigatorio, opcional=valor)` |
| Opcionais | Depois | `def func(param1, param2=10)` |

### Pontos Importantes:
- Parâmetros obrigatórios sempre devem vir antes dos opcionais
- Valores padrão são avaliados apenas uma vez
- É possível ter múltiplos parâmetros com valores padrão

## Exemplo Prático: Sistema de Filtragem de Filmes

### Função de Filtragem por Gênero
```python
def filter_by_genre(data, genre='drama'):
    filtered_result = []
    for row in data:
        if genre in row[3]:
            filtered_result.append(row)
    return filtered_result

# Exemplo de dados
movies_info = [
    ['The Shawshank Redemption', 'USA', 1994, 'drama', 142, 9.111],
    ['The Godfather', 'USA', 1972, 'drama, crime', 175, 8.730],
    # ... outros filmes ...
]

movies_filtered = filter_by_genre(movies_info)
```

**Saída exemplo:**
```
['The Shawshank Redemption', 'USA', 1994, 'drama', 142, 9.111]
['The Godfather', 'USA', 1972, 'drama, crime', 175, 8.73]
```

### Características da Implementação:
- Valor padrão 'drama' para o parâmetro genre
- Busca parcial no gênero (permite encontrar filmes com múltiplos gêneros)
- Retorna lista completa de informações dos filmes

# Resumo Geral

**Pontos-Chave:**
- Funções podem ter parâmetros obrigatórios e opcionais
- Valores padrão tornam parâmetros opcionais
- A ordem dos parâmetros é crucial (obrigatórios primeiro)
- Valores padrão permitem maior flexibilidade nas chamadas de função
- Exemplos práticos demonstram aplicações reais do conceito

*Aplicações Práticas:*
- Sistemas de filtragem de dados
- Processamento de informações com configurações padrão
- APIs com parâmetros opcionais
- Funções utilitárias com comportamento configurável










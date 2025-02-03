
**2025-01-09 19:09**

**Sprint:** [[Sprint5]]

**Topic:** #python-intermediario 

**Connections:** 

---
# **Verificação e dicas de tipo**

# Tipagem em Python

## Tipagem Dinâmica
Python é uma linguagem de tipagem dinâmica, o que significa que o interpretador só verifica a validade das operações quando elas precisam ser executadas. Isso contrasta com linguagens de tipagem estática como Java ou C++.

### Exemplo de Erro de Tipagem

```python
# subtract.py
def subtract(a=10, b='5'):
    return a - b
   
subtract()
print('Hello from subtract.py')
```

Explicação: Esta função tenta subtrair uma string ('5') de um número (10), o que não é uma operação válida em Python.

Saída esperada:
```
TypeError: unsupported operand type(s) for -: 'int' and 'str'
```

### Exemplo sem Erro de Execução

```python
# subtract.py
def subtract(a=10, b='5'):
    return a - b

print('Hello from subtract.py')
```

Explicação: Quando a função não é chamada, o código executa sem erros porque o interpretador Python não verifica os tipos antecipadamente.

Saída esperada:
```
Hello from subtract.py
```

# Dicas de Tipo (Type Hints)

## Sintaxe Básica

```python
def list_of_words(text: str, sep: str = " ") -> list:
    return text.split(sep)
```

Explicação:
- `text: str` - indica que o parâmetro text deve ser uma string
- `sep: str = " "` - indica que sep deve ser uma string com valor padrão de espaço
- `-> list` - indica que a função retorna uma lista

## Comportamento com Tipos Incorretos

```python
# list_of_words.py
def list_of_words(text: str, sep: str = " ") -> list:
    return text.split(sep)

print(list_of_words("Maria tinha um cordeirinho", sep=None))
```

Explicação: Mesmo com a dica de tipo indicando que `sep` deve ser uma string, o código executa normalmente com `None` porque as dicas de tipo não são verificadas pelo interpretador Python.

Saída esperada:
```
['Maria', 'tinha', 'um', 'cordeirinho']
```

# Verificação de Tipo com mypy

## Instalação do mypy
```bash
$ pip install mypy
```

## Verificação de Código com Erro

```python
# list_of_words.py
def list_of_words(text: str, sep: str = " ") -> list:
    return text.split(sep)

list_of_words("Maria tinha um cordeirinho", sep=None)
```

Saída do mypy:
```
list_of_words.py:4: error: Argument "sep" to "list_of_words" has incompatible type "None"; expected "str"
Found 1 error in 1 file (checked 1 source file)
```

## Código Corrigido

```python
# list_of_words.py
def list_of_words(text: str, sep: str = " ") -> list:
    return text.split(sep)

list_of_words("Maria tinha um cordeirinho", sep="a")
print("Hello from list_of_words.py")
```

Saída do mypy:
```
Success: no issues found in 1 source file
```

# Pontos-Chave:
- Python é uma linguagem de tipagem dinâmica, verificando tipos apenas durante a execução
- Type hints são uma forma de documentação e não afetam o comportamento em tempo de execução
- mypy é uma ferramenta externa que permite verificação estática de tipos
- Type hints seguem convenções específicas de estilo definidas no PEP 8
- A verificação de tipos com mypy ajuda a identificar possíveis erros antes da execução

# Resumo
O sistema de tipagem do Python oferece flexibilidade através da tipagem dinâmica, mas também permite adicionar dicas de tipo para melhor documentação e manutenção do código. Embora as dicas de tipo não afetem a execução do programa, ferramentas como mypy podem ser usadas para verificação estática de tipos, combinando assim os benefícios da tipagem dinâmica e estática.









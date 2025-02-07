
**2025-02-06 19:50**

**Sprint:** [[Sprint6]]

**Topic:** #uso-de-docs 

**Connections:** 

---
# **Como ler erros**

# Entendendo Erros em Python

## O que são Tracebacks?

Um traceback é o mecanismo de rastreamento de erros do Python que verifica cada passo da execução do programa. Quando algo dá errado, o Python gera uma mensagem de erro detalhada chamada traceback.

**Pontos-Chave:**
- Tracebacks são mensagens de diagnóstico úteis
- Rastreiam o programa "de baixo para cima"
- Fornecem informações detalhadas sobre o erro

## Anatomia de uma Mensagem de Erro

### Elementos principais:
4. Setas indicativas (→)
   - A última seta mostra a localização exata do erro
5. Tipo do erro
6. Descrição detalhada
7. Número da linha onde ocorreu o erro

**Dica importante:** Não se assuste com tracebacks longos - eles indicam que seu programa executou várias etapas antes de encontrar o problema.

## Tipos Comuns de Erros

### 1. SyntaxError
```python
print("Olá Mundo"
```
**Explicação:** Falta o parêntese de fechamento.

Saída esperada:
```
  File "<stdin>", line 1
    print("Olá Mundo"
                    ^
SyntaxError: invalid syntax
```

### 2. IndentationError
```python
def funcao():
print("Mal indentado")
```
**Explicação:** A linha com o print() deveria estar indentada.

Saída esperada:
```
  File "<stdin>", line 2
    print("Mal indentado")
    ^
IndentationError: unexpected indent
```

### 3. NameError
```python
print(variavel_inexistente)
```
**Explicação:** Tentativa de usar uma variável que não foi definida.

Saída esperada:
```
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'variavel_inexistente' is not defined
```

### 4. IndexError
```python
lista = [1, 2, 3]
print(lista[5])
```
**Explicação:** Tentativa de acessar um índice que não existe na lista.

Saída esperada:
```
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list index out of range
```

## Dicas para Depuração

8. Sempre leia a última seta do traceback primeiro
9. Identifique o tipo do erro
10. Consulte a documentação oficial quando necessário: [Python Exceptions](https://docs.python.org/pt-br/3/library/exceptions.html)

**Pontos-Chave:**
- A indentação é crucial em Python
- Verifique sintaxe, parênteses e vírgulas
- Certifique-se de que variáveis estão definidas antes do uso
- Confirme índices válidos ao acessar listas/dicionários

# Resumo
- Tracebacks são ferramentas úteis de diagnóstico que ajudam a identificar erros
- Os erros mais comuns são SyntaxError, IndentationError, NameError e IndexError
- Cada tipo de erro tem uma causa específica e uma solução correspondente
- Python fornece mensagens de erro claras e informativas para auxiliar na depuração
- A documentação oficial é um recurso valioso para entender melhor os erros










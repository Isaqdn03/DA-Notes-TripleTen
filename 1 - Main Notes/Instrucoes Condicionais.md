
2024-10-07 19:15

Sprint:[[Sprint1]]

Topic: #basics 


# Instrucoes Condicionais

## Expressões Lógicas e Operadores

**Operadores de Comparação:**

- Igualdade: `==`
- Diferença: `!=`
- Maior/Menor: `>`, `<`
- Maior/Menor ou igual: `>=`, `<=`

**Operadores Lógicos:**

- E lógico: `and`
- OU lógico: `or`
- NÃO lógico: `not`

**Funções Predicado:**

- `islower()`: Verifica se todos os caracteres são minúsculos
- `isdigit()`: Verifica se todos os caracteres são dígitos
- `isalpha()`: Verifica se todos os caracteres são letras

## Estruturas Condicionais

**if-elif-else:**

```python
if condição1:
# código se condição1 for verdadeira 
elif condição2:     
# código se condição2 for verdadeira 
else:     
# código se nenhuma condição for verdadeira`
```

**Operador in:**

- Verifica se um elemento está presente em uma sequência
- Exemplo: `"a" in "abc"` retorna `True`

## Pontos-Chave

1. Python avalia condições sequencialmente em estruturas if-elif-else.
2. Apenas o bloco da primeira condição verdadeira é executado.
3. A indentação é crucial para definir blocos de código em Python.
4. O operador `in` é útil para verificar substrings ou elementos em listas.
5. Estruturas condicionais podem ser combinadas com loops para processamento complexo de dados.

## Exemplo Prático


```python
for rating in ratings:     
	if 0 <= rating <= 59:        
		print(2)    
	elif 60 <= rating <= 72:        
		print(3)    
	elif 73 <= rating <= 84:        
		print(4)    
	elif 85 <= rating <= 100:        
		print(5)`
```


Este resumo cobre os conceitos essenciais de expressões lógicas e estruturas condicionais em Python, fornecendo uma base sólida para active recall studying.










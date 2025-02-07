
**2025-01-11 17:39**

**Sprint:** [[Sprint5]]

**Topic:** #python-intermediario 

**Connections:** 

---
# **Tratamentos de erros**

# Tratamento de Erros em Python

## Introdução ao Tratamento de Erros
Python oferece um sistema robusto para lidar com erros durante a execução do programa. Quando algo inesperado acontece, o programa gera uma exceção, que pode ser tratada de forma adequada para evitar que o programa seja interrompido abruptamente.

### Exemplo Prático de Erro
```python
python image_rotator.py tripleten_logo.jpe --angle 180 output.png -i
```
Saída esperada:
```
FileNotFoundError: [Errno 2] No such file or directory: 'tripleten_logo.jpe'
```

**Explicação:** Este exemplo mostra um erro comum quando um arquivo não é encontrado. O Python gera um `FileNotFoundError`, indicando que o arquivo especificado não existe no diretório.

## Try-Except Básico

### Estrutura Básica
```python
try:
    im = Image.open(args.input_file)

except FileNotFoundError:
    print('arquivo de entrada não encontrado, forneça o nome do arquivo correto:')
```

**Explicação:** 
- O bloco `try` tenta executar o código que pode gerar um erro
- O bloco `except` especifica o que fazer quando um erro específico ocorre
- Neste caso, se o arquivo não for encontrado, uma mensagem é exibida

### Try-Except com Input do Usuário
```python
try:
    im = Image.open(args.input_file)

except FileNotFoundError:
    print('arquivo de entrada não encontrado, forneça o nome do arquivo correto:')
    im = Image.open(input())
```

**Explicação:** Esta versão aprimorada permite que o usuário forneça um novo nome de arquivo quando o arquivo original não é encontrado.

## Try-Except com Múltiplas Exceções

```python
try:
    im = Image.open(args.input_file)

except FileNotFoundError:
    print('arquivo de entrada não encontrado, forneça o nome do arquivo correto:')
    im = Image.open(input())

except Exception as error_msg:
    print(error_msg)
    print('Parece ser o arquivo errado, tente outro:')
    im = Image.open(input())
```

**Explicação:** 
- Primeiro `except` trata especificamente erros de arquivo não encontrado
- Segundo `except` captura qualquer outro tipo de exceção
- `as error_msg` permite acessar a mensagem de erro original

## Try-Except-Else-Finally Completo

```python
try:
    im = Image.open(args.input_file)
    
except FileNotFoundError:
    print('arquivo de entrada não encontrado, forneça o nome do arquivo correto:')
    im = Image.open(input())

except Exception:
    print('Arquivo errado, tente outro:')
    im = Image.open(input())

else:
    print("Funcionando sem problemas")

finally:
    rotated = im.rotate(angle)
    im.close() 
    rotated.save(args.output_file)
```

**Explicação:**
- `try`: tenta abrir a imagem
- `except`: trata diferentes tipos de erros
- `else`: executa se nenhum erro ocorrer
- `finally`: executa sempre, independente de erros

Saída esperada (caso sucesso):
```
Funcionando sem problemas
```

# Pontos-Chave
- O tratamento de erros é crucial para criar programas robustos
- Sempre especifique o tipo de exceção quando possível
- Use `try-except` para código propenso a erros
- `else` e `finally` fornecem controle adicional sobre o fluxo do programa
- Comum usar tratamento de erros ao:
  - Abrir arquivos
  - Converter tipos de dados
  - Processar entrada do usuário

# Resumo
O tratamento de erros em Python permite criar programas mais resilientes e amigáveis ao usuário. Através do uso de blocos try-except, podemos capturar e tratar exceções de forma elegante, fornecendo feedback útil ao usuário e evitando que o programa seja interrompido abruptamente. A estrutura completa try-except-else-finally oferece um controle granular sobre como os erros são tratados e como o programa se recupera deles.











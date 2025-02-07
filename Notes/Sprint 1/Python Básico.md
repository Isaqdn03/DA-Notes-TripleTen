
2024-10-07 18:10

Sprint: [[Sprint1]] 

Topic: #basics



# Capitulo 1 - Python Básico

## Python Básico: Resumo para Active Recall

### **Por que Python?**

- **Sintaxe Intuitiva:** Próxima da linguagem humana.
- **Flexibilidade & Versatilidade:** Aplicável em desenvolvimento web, jogos, machine learning, análise de dados, etc.
- **Alta Demanda no Mercado:** Amplas oportunidades de emprego.

### **Variáveis**

- **Definição:** Contêineres para armazenar valores (texto, números, etc.).
    
- **Atribuição:** `nome_variavel = valor`
    
- **Sintaxe:**
    
    - Iniciam com letra ou `_`.
    - Contêm apenas letras, números e `_`.
    - **Case-Sensitive:** `my_var` ≠ `My_Var`.
- **Exemplo:**
    
    ```python
    python
    Copy code
    pi = 3.14159
    print(pi + 1)  # Output: 4.14159
    
    ```
    

### **Função `print()`**

- **Uso:** Exibe valores na tela.
    
- **Argumentos:**
    
    - **Texto:** Envolto em `' '` ou `" "`.
    - **Números:** Sem aspas.
- **Pular Linhas:** Utilize `print()` vazio ou quebre linhas no editor.
    
- **Exemplos:**
    
    ```python
   print('Hello, World!')
   print(123)
    
    ```
    

### **Operações Aritméticas**

- **Operadores Básicos:** `+`, `,` , `/`
    
- **Ordem das Operações:** PEMDAS (Parênteses, Exponenciação, Multiplicação/Divisão, Adição/Subtração)
    
- **Uso com Variáveis:**
    
    ```python
    python
    Copy code
    a = 10
    b = 5
    total = a + b
    print(total)  # Output: 15
    
    ```
    

### **Tipos de Dados**

- **Números Inteiros (`int`)**
- **Números de Ponto Flutuante (`float`)**
- **Strings (`str`)**
- **Booleanos (`bool`):** `True` ou `False`

### **Conversão de Tipos de Dados**

- **Funções de Conversão:**
    
    - `int()`: Para inteiros
    - `float()`: Para floats
    - `str()`: Para strings
- **Exemplos:**
    
    ```python
    python
    Copy code
    num_float = 5.99
    num_int = int(num_float)  # 5
    
    num_str = '123'
    num_int = int(num_str)    # 123
    
    ```
    

### **Mensagens de Erro**

1. **Erros de Sintaxe:**
    
    - **Causa:** Código mal formatado.
        
    - **Exemplo:**
        
        ```python
        python
        Copy code
        print('Oi’
        # SyntaxError: incomplete input
        
        ```
        
2. **Erros de Operação:**
    
    - **Causa:** Operações inválidas (e.g., divisão por zero).
        
    - **Exemplo:**
        
        ```python
        python
        Copy code
        print(777 / 0)
        # ZeroDivisionError: division by zero
        
        ```
        
3. **Erros de Namespace:**
    
    - **Causa:** Variáveis não definidas.
        
    - **Exemplo:**
        
        ```python
        python
        Copy code
        print(kiwi_price)
        # NameError: name 'kiwi_price' is not defined
        
        ```
        

### **Tratamento de Erros**

- **Estrutura `try-except`:**
    
    ```python
    python
    Copy code
    try:
        print(777 / 0)
    except:
        print('Não é possível dividir por zero!')
        print('Seguimos adiante!')
    # Output:
    # Não é possível dividir por zero!
    # Seguimos adiante!
    
    ```
    

### **Resumo do Capítulo 2**

- **Variáveis:** Definição e sintaxe.
- **Função `print()`:** Exibição de informações.
- **Tipos de Dados:** Inteiros, floats, strings, booleanos.
- **Operações Aritméticas:** Uso e ordem das operações.
- **Conversão de Tipos:** `int()`, `float()`, `str()`.
- **Erros Comuns:** Sintaxe, operação, namespace.
- **Tratamento de Erros:** `try-except`.

---

Use este resumo para revisar os conceitos chave, praticar exemplos e testar seu entendimento através de perguntas rápidas. Por exemplo:

- **O que define uma variável em Python?**
- **Como converter uma string para inteiro?**
- **Qual é a ordem das operações em Python?**
- **Como tratar uma divisão por zero?**

Revisar regularmente esses pontos fortalecerá seu conhecimento e preparação em Python básico.












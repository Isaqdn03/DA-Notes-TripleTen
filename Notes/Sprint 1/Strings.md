
2024-10-07 18:14

Sprint:[[Sprint1]]

Topic: #basics 


# Strings
### **Conceitos Básicos de Strings**

- **Strings**: Dados de texto, podem ser armazenados com aspas simples (`'`) ou duplas (`"`).
- Strings podem incluir **caracteres de escape** como:
    - `\\'`: Apóstrofo dentro de uma string.
    - `\\n`: Quebra de linha.
    - `\\t`: Tabulação.

### **Exemplo de Caracteres de Escape**:

```python

print("Quero um copo d'água, por favor!")
```

---

### **Strings de Múltiplas Linhas**

- Use três aspas (`"""` ou `'''`) para criar **strings de múltiplas linhas**.
    
- Exemplo:
    
    ```python
    
    shopping_list = """MInha lista de compras:
    leite, ovos, pão"""
    ```
    

---

### **Comprimento de Strings**

- A função `len()` retorna o número de caracteres de uma string.
    
- **Exemplo**:
    
    ```python
    python
    Copy code
    len("Python")  # Retorna 6
    ```
    

---

### **Índices e Slices**

- **Índices**: Começam em 0.
    - Exemplo: `string[0]` acessa o primeiro caractere.
- **Slices**: Seleciona múltiplos caracteres.
    - Sintaxe: `string[início:fim]` (o caractere no índice "fim" **não é incluído**).
        
    - Exemplo:
        
        ```python
        cidade = "São Paulo"
        cidade[0:3]  # Retorna 'São'
        ```
        

---

### **Formatação de Strings**

- **F-strings**: Coloque `f` antes das aspas e use `{}` para variáveis.
    
    - Exemplo:
        
        ```python
        nome = 'Ana'
        f"Olá, {nome}!"
        ```
        
- **Método `format()`**: Substitui variáveis em uma string.
    
    - Exemplo:
        
        ```python
        "Olá, {}!".format(nome)
        ```
        

---

### **Métodos de Strings**

1. **Manipulação de Maiúsculas/Minúsculas**:
    - `upper()`: Converte para maiúsculas.
    - `lower()`: Converte para minúsculas.
2. **Substituição e Remoção**:
    - `replace()`: Substitui partes da string.
        - Exemplo: `"banana".replace('a', 'o')` → `"bonono"`
    - `strip()`: Remove espaços no início e no fim da string.

---

### **Exercícios para Active Recall**

1. **Como você pode acessar o terceiro caractere de uma string?**
2. **Como formatar uma string com variáveis usando f-strings?**
3. **Qual método de string você usaria para converter uma string em maiúsculas?**
4. **O que acontece quando você fatia uma string além de seu comprimento?**
5. **Como remover espaços no início e no final de uma string?**

Revisando os conceitos com esses exercícios vai te ajudar a reter as informações por mais tempo!













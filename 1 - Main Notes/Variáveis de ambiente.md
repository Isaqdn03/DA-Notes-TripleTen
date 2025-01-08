
**2025-01-06 19:01**

**Sprint:** [[Sprint5]]

**Topic:** #intro-CLI 

**Connections:** 

---
# **Variáveis de ambiente**

# Variáveis de Ambiente em Python e CLI

## Introdução às Variáveis de Ambiente
Em Python e na linha de comando (CLI), as variáveis de ambiente são elementos fundamentais para armazenar informações acessíveis em todo o sistema.

### Exemplo Básico em Python
```python
name = 'brian'  # Variável Python comum
```
**Explicação**: Esta é uma atribuição básica em Python, onde o valor 'brian' é armazenado na variável `name`.

**Saída esperada**: 
```
Nenhuma saída direta, apenas armazena o valor 'brian' na memória
```

## Variáveis na CLI

### Sintaxe Básica
```bash
echo $HOME
```
**Explicação**: O comando exibe o valor da variável de ambiente HOME, que aponta para o diretório do usuário.

**Saída esperada**: 
```
/home/jovyan
```

### Listando Todas as Variáveis
```bash
env
```
**Explicação**: Lista todas as variáveis de ambiente disponíveis no sistema.

**Saída esperada**: 
```
SHELL=/bin/bash
JUPYTERHUB_ADMIN_ACCESS=1
[...]
```

## Tipos de Variáveis

### Variáveis Shell vs Ambientais

*Pontos-Chave:*
- **Variáveis Shell**: 
  - Existem apenas na instância atual do Terminal
  - Não acessíveis em outros programas
  - Não podem ser vistas com `printenv`

- **Variáveis Ambientais**:
  - Disponíveis em todo o sistema
  - Acessíveis por outros programas
  - Visíveis através de `printenv` e `env`

## Criação e Manipulação de Variáveis

### Criando Variáveis Shell
```bash
MY_V="my first variable"
echo $MY_V
```
**Explicação**: Cria uma variável shell e exibe seu valor.

**Saída esperada**: 
```
my first variable
```

### Convertendo para Variável Ambiental
```bash
export MY_V
```
**Explicação**: Transforma a variável shell em variável ambiental.

**Saída esperada**: 
```
Nenhuma saída direta, apenas exporta a variável
```

## Acesso via Python

### Usando a Biblioteca os
```python
import os
home_dir = os.environ["HOME"]
```
**Explicação**: Importa a biblioteca os e acessa o valor da variável ambiente HOME.

**Saída esperada**: 
```
Se print(home_dir): /home/jovyan
```

# Resumo
- Variáveis de ambiente são acessíveis em todo o sistema
- Sintaxe na CLI usa $ e letras maiúsculas
- Dois tipos principais: shell (locais) e ambiente (globais)
- Podem ser criadas temporária ou permanentemente
- Acessíveis via Python usando a biblioteca os
- Essenciais para configuração e gerenciamento do sistema

*Pontos-Chave Finais:*
1. Use `export` para tornar variáveis acessíveis globalmente
2. Variáveis ambientais são temporárias por padrão
3. Para permanência, edite /etc/environment
4. Sempre use letras maiúsculas para nomes de variáveis na CLI









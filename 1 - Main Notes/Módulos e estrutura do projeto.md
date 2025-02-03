
**2025-01-11 18:42**

**Sprint:** [[Sprint5]]

**Topic:** #python-intermediario 

**Connections:** 

---
# **Módulos e estrutura do projeto**

# Módulos em Python: Estrutura e Organização

## Introdução aos Módulos

Um módulo em Python é um arquivo `.py` que contém código reutilizável. O exemplo apresentado mostra um caso prático de astronomia, onde um cientista cria um módulo `astro.py` para compartilhar funções comuns entre diferentes scripts.

### Exemplo Básico de Importação

```python
# myscript.py
import astro  # importando o nosso módulo teórico
```

Saída esperada: 
Nenhuma saída direta. O módulo fica disponível para uso no script.

### Exemplo Prático com PIL

```python
from PIL import Image

im = Image.open('myimage.png')
im.rotate(90)
im.save('output.png')
```

Saída esperada:
- A imagem será aberta
- Rotacionada 90 graus
- Salva como 'output.png'

## Execução de Módulos

### Exemplo de Execução

```python
# module.py
print("Oi! Eu sou um módulo")

# myscript.py
import module
print("Executando o programa principal")
```

Saída esperada:
```
Oi! Eu sou um módulo
Executando o programa principal
```

## Instalação de Pacotes

Para instalar novos pacotes, usa-se o pip:

```bash
pip install --user package_name
pip install --user Pillow
```

Saída esperada:
```
Collecting package_name
  Downloading package_name-x.x.x.tar.gz
Successfully installed package_name-x.x.x
```

## Namespaces e Importação

### Exemplo de Verificação de Email

```python
# module.py
import re

def check_email(string: str):
    '''
    use expressões regulares para verificar a formatação do endereço de e-mail
    o padrão é "algo@algo.algo"
    '''
    if re.match('[.\w]+@\w+[.]\w+', string):
        print('correto')
    else:
        print('verifique endereço de e-mail')

# myscript.py
import module
email = input()
module.check_email(email)
```

Saída esperada:
Para input "usuario@email.com":
```
correto
```
Para input "usuarioemail.com":
```
verifique endereço de e-mail
```

## Verificação if __name__ == '__main__'

### Exemplo de Ponto de Entrada

```python
# module_1.py
def useful_function():
    print('funcionando')

if __name__ == '__main__':
    print("testando a função...")
    useful_function()
```

Saída esperada quando executado diretamente:
```
testando a função...
funcionando
```

### Exemplo de Importação em Outro Módulo

```python
# module_2.py
import module_1

def double_check():
    print('Duas vezes:')
    module_1.useful_function()
    module_1.useful_function()

if __name__ == "__main__":
    print("testando a função...")
    double_check()
```

Saída esperada quando module_2.py é executado:
```
testando a função...
Duas vezes:
funcionando
funcionando
```

## Boas Práticas de Importação

```python
# myscript.py
# Pacotes integrados
import math
import os

# Pacotes de terceiros
import pandas
import numpy

# Meu próprio módulo
import mymodule
```

**Pontos-Chave:**
- Sempre importe módulos no início do arquivo
- Organize as importações em três seções: integrados, terceiros e locais
- Evite usar `from module import *`
- Use blocos `if __name__ == '__main__'` para código que só deve ser executado quando o script é o principal

# Resumo
- Módulos são arquivos Python (.py) que contêm código reutilizável
- Pacotes são coleções de módulos, e bibliotecas são coleções de pacotes
- PyPI é o repositório oficial de pacotes Python, e pip é o gerenciador de pacotes
- Namespaces permitem organizar e acessar atributos de módulos
- A verificação `if __name__ == '__main__'` é crucial para controlar a execução de código em diferentes contextos
- Boas práticas de importação ajudam a manter o código organizado e evitar conflitos










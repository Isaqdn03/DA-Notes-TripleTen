
**2025-01-17 19:49**

**Sprint:**[[Sprint5]]

**Topic:** #python-intermediario 

**Connections:** 

---
# **Entrada e saída de arquivos File I-O**

# Entrada e Saída de Arquivos (File I/O) em Python

## Conceitos Fundamentais
Um arquivo é uma unidade de armazenamento que contém informações codificadas em bits. As extensões (como .txt, .py, .jpeg) indicam o tipo e a estrutura de codificação do arquivo.

### Pontos-Chave:
- Todos os arquivos são codificados em bits
- As extensões determinam o tipo e estrutura do arquivo
- Python oferece funções integradas para manipulação de arquivos

## Leitura de Arquivos

### Abertura Básica
```python
f = open('my_file.txt')
# ou
f = open('my_file.txt', mode='r')
```
**Explicação:** A função `open()` cria um objeto do tipo arquivo. O parâmetro `mode='r'` especifica explicitamente o modo de leitura (read).

**Saída esperada:**
```
<_io.TextIOWrapper name='my_file.txt' mode='r' encoding='cp1252'>
```

### Leitura Linha por Linha
```python
f = open('my_file.txt')
for line in f:
    print(line.rstrip())
f.close()
```
**Explicação:** Este código lê o arquivo linha por linha e usa `rstrip()` para remover espaços em branco e caracteres de nova linha extras.

**Saída esperada:**
```
"Do not go gentle into that good night"
[12, 13, 14]
100.42
Alice
```

### Usando Gerenciador de Contexto
```python
with open('my_file.txt') as f:
    for line in f.readlines():    
        print(line.rstrip())
```
**Explicação:** O gerenciador de contexto (`with`) fecha automaticamente o arquivo após seu uso, evitando vazamentos de memória.

## Gravação em Arquivos

### Modos de Gravação
- `'w'`: Cria novo arquivo vazio (sobrescreve se existente)
- `'a'`: Adiciona conteúdo ao final do arquivo

### Exemplo de Diário
```python
from datetime import datetime

now = datetime.now() 

with open('my_journal.txt', 'a') as f:
    f.write('\n')     
    f.write(str(now)) 
    f.write('\n\n')   
    f.write(' ')      
    f.write(input())  
    f.write('\n\n')   
```
**Explicação:** Este código cria ou abre um arquivo de diário, adiciona data/hora atual e permite entrada do usuário.

## Manipulação de Arquivos ZIP

```python
from zipfile import ZipFile

with open("info.txt", "w") as f:
    f.write('alguns dados')
    
with ZipFile("archive.zip", mode="w") as archive:
    archive.write("info.txt")
```
**Explicação:** Demonstra como criar um arquivo ZIP e adicionar arquivos a ele.

## Trabalho com JSON

### Leitura de JSON da Web
```python
import json
import requests

data = requests.get('https://dummyjson.com/products/1')
text = data.text
print(json.loads(text))
```
**Explicação:** Baixa dados JSON de uma URL e converte para um dicionário Python.

### Gravação em JSON
```python
import json

data = dict(user_id=12, status='active', user_name='Rachel')

with open ('output.json', 'w') as f:
    json.dump(data, f)
```
**Explicação:** Converte um dicionário Python em formato JSON e salva em arquivo.

## Trabalho com YAML

```python
import yaml

data = [{'user_id': '1', 'age': 34},
         {'user_id': '2', 'age': 37}]

print(yaml.dump(data))
```
**Explicação:** Converte estruturas de dados Python para formato YAML.

**Saída esperada:**
```yaml
- age: 34
  user_id: '1'
- age: 37
  user_id: '2'
```

# Resumo
- Python oferece diversas formas de manipular arquivos através de operações de I/O
- O gerenciador de contexto (`with`) é a forma mais segura de trabalhar com arquivos
- Diferentes formatos (TXT, JSON, YAML, ZIP) têm diferentes métodos de manipulação
- É importante sempre fechar os arquivos após o uso
- JSON e YAML são formatos populares para armazenamento de dados estruturados









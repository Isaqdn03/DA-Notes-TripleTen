
**2025-01-09 18:13**

**Sprint:** [[Sprint5]]

**Topic:** #python-intermediario 

**Connections:** 

---
# **Adição de flexibilidade a scripts Python**

# Flexibilidade em Scripts Python

## 1. Introdução a Scripts Python

Um script Python é um arquivo de texto contendo código Python que pode ser executado através da linha de comando (CLI). Scripts são fundamentais para automatização e reusabilidade de código.

### Exemplo Básico - Manipulação de Imagens

```python
from PIL import Image # importando o módulo Image da biblioteca PIL

# carregando uma imagem chamada 'tripleten_logo.jpeg'.
im = Image.open('tripleten_logo.jpeg')

# obtendo o tamanho da imagem usando o atributo .size e o imprimindo
print(im.size)

# rodando a imagem 90 graus em sentido anti-horário
rotated = im.rotate(90)

# salvando a imagem rodada
rotated.save('rotated.png')
```

Explicação:
- O código utiliza a biblioteca PIL para manipulação de imagens
- Carrega uma imagem, obtém suas dimensões, rotaciona e salva
- Operações básicas: open(), size, rotate(), save()

Saída esperada:
```
(1110, 694)
```

### Instalação da Biblioteca PIL
```bash
python3 -m pip install --upgrade pip
python3 -m pip install --upgrade Pillow
```

## 2. Argumentos de Linha de Comando

### Exemplo com Argumentos Básicos

```python
from PIL import Image
import argparse # importar o módulo argparse

# iniciar o analisador
parser = argparse.ArgumentParser()

# adicionar os argumentos com os nomes correspondentes
parser.add_argument('input_file')
parser.add_argument('output_file')
parser.add_argument('angle', type=int)

# analisar os argumentos
args = parser.parse_args()

# carregar uma imagem do argumento input_file
im = Image.open(args.input_file)

# exibir tamanho da imagem
print(im.size)

# girar a imagem em um ângulo indicado como um dos argumentos
rotated = im.rotate(args.angle)

# salvar a imagem rodada usando o caminho de saída do argumento output_file
rotated.save(args.output_file)
```

Explicação:
- Usa argparse para processar argumentos da linha de comando
- Define três argumentos posicionais: input_file, output_file e angle
- O argumento angle é convertido para inteiro com type=int

Uso na linha de comando:
```bash
python image_rotator.py tripleten_logo.jpeg output.png 180
```

Saída esperada:
```
(694, 1110)
```

## 3. Opções e Sinalizadores

### Exemplo com Opções

```python
from PIL import Image
import argparse

parser = argparse.ArgumentParser()

parser.add_argument('input_file')
parser.add_argument('output_file')
parser.add_argument('--angle', '-a', type=int, default=90)
parser.add_argument('-i', '--info', action='store_true')

args = parser.parse_args()

im = Image.open(args.input_file)

if args.info:
    print('dimensões da imagem de entrada:', im.size)

rotated = im.rotate(args.angle)
rotated.save(args.output_file)
```

Explicação:
- Adiciona opção --angle (ou -a) com valor padrão 90
- Inclui sinalizador --info (-i) para exibir informações adicionais
- Usa action='store_true' para criar um sinalizador booleano

Uso na linha de comando:
```bash
python image_rotator.py tripleten_logo.jpeg --angle 180 output.png -i
```

Saída esperada:
```
dimensões da imagem de entrada: (694, 1110)
```

## 4. Mensagens de Ajuda

### Exemplo com Documentação Completa

```python
from PIL import Image
import argparse

parser = argparse.ArgumentParser()

parser.add_argument('input_file', help='input file path')
parser.add_argument('output_file', help='output file path')
parser.add_argument('--angle', '-a', type=int, default=90, 
                   help='rotação em sentido anti-horário (graus)')
parser.add_argument('-i', '--info', action='store_true', 
                   help='exibir tamanho da imagem')

args = parser.parse_args()

im = Image.open(args.input_file)

if args.info:
    print('dimensões da imagem de entrada:', im.size)

rotated = im.rotate(args.angle)
rotated.save(args.output_file)
```

Explicação:
- Adiciona mensagens de ajuda para cada argumento
- Documenta o propósito de cada opção e argumento
- Acessível através da opção -h ou --help

Visualização da ajuda:
```bash
python image_rotator.py -h
```

Saída esperada:
```
usage: image_rotator.py [-h] [--angle ANGLE] [-i] input_file output_file

positional arguments:
  input_file   input file path
  output_file  output file path

options:
  -h, --help   show this help message and exit
  --angle ANGLE, -a ANGLE   
               counterclockwise rotation (degrees)
  -i, --info   display image size
```

# Resumo dos Principais Aprendizados

1. Scripts Python podem ser executados pela linha de comando para automatizar tarefas
2. A biblioteca PIL permite manipulação básica de imagens
3. argparse facilita a criação de interfaces de linha de comando flexíveis
4. Argumentos posicionais são obrigatórios e devem seguir uma ordem específica
5. Opções e sinalizadores oferecem flexibilidade adicional ao script
6. Mensagens de ajuda documentam o uso do script para outros usuários
7. Opções curtas podem ser combinadas para uma sintaxe mais concisa










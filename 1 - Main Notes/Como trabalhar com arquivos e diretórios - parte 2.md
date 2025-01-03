
**2025-01-02 18:18**

**Sprint:** [[Sprint5]]

**Topic:** #intro-CLI 

**Connections:** 

---
# **Como trabalhar com arquivos e diretórios - parte 2**

# Comandos de Terminal (CLI) - Parte 2

## 1. Comando Echo

### Uso Básico
O `echo` é um comando integrado usado para imprimir argumentos no Terminal como saída padrão.

```bash
echo Quero aprender sobre a CLI
```
Saída esperada:
```
Quero aprender sobre a CLI
```

### Uso Avançado com Opções

#### Opção -e (Caracteres de Escape)
```bash
echo -e 'Quero aprender sobre a CLI. \nTodo programador sabe usá-la!'
```
Saída esperada:
```
Quero aprender sobre a CLI. 
Todo programador sabe usá-la!
```

### Redirecionamento de Saída
- `>` : Substitui o conteúdo do arquivo
- `>>` : Adiciona ao final do arquivo

```bash
echo -e 'Quero aprender sobre a CLI. \nTodo programador sabe usá-la!' > my_file.txt
```

**Pontos-Chave:**
- Use aspas ao adicionar opções
- `-e` permite caracteres de escape como `\n`
- Pode criar ou sobrescrever arquivos

## 2. Comando Touch

### Criação de Arquivos Vazios
```bash
touch my_new_file
```

**Pontos-Chave:**
- Cria arquivos dummy (vazios)
- Não altera arquivos existentes
- Útil para testes e demonstrações

## 3. Comando MV (Move)

### Movendo Arquivos
```bash
mkdir sub_directory
mv my_file.txt sub_directory
```

### Movendo Múltiplos Arquivos
```bash
mv my_file1.txt my_file2.txt ~/home_sub_directory
```

### Renomeando Arquivos
```bash
mv old_file_name.txt new_file_name.txt
```

**Opções Importantes:**
- `-n`: Previne substituição
- `-i`: Solicita confirmação antes de substituir

**Pontos-Chave:**
- Pode mover ou renomear
- Funciona com arquivos e diretórios
- Cuidado com substituições

## 4. Comando CP (Copy)

### Copiando Arquivos
```bash
cp original_file.txt copy_from_original.txt
```

### Copiando Diretórios
```bash
cp -r my_files ~/home_sub_directory
```

**Pontos-Chave:**
- `-r` necessário para copiar diretórios com conteúdo
- `-n` e `-i` funcionam como no mv
- Mantém o arquivo original

## Comparação MV vs CP

| Característica | MV | CP |
|---------------|----|----|
| Arquivo Original | Remove | Mantém |
| Opção para Diretórios | Não necessária | -r necessária |
| Prevenção de Substituição | -n ou -i | -n ou -i |

# Exercícios Práticos

**Pergunta 1:** Criação de arquivo vazio
- ✅ `touch to_buy.txt`
- ❌ `cat to_buy.txt`
- ✅ `echo > to_buy.txt`

**Pergunta 2:** Prevenção de substituição
- ✅ Opção `-n`: Previne substituição
- ❌ Opção `-f`: Não previne substituição
- ✅ Opção `-i`: Solicita confirmação

# Resumo
- `echo`: Exibe texto e pode redirecionar para arquivos
- `touch`: Cria arquivos vazios
- `mv`: Move ou renomeia arquivos/diretórios
- `cp`: Copia arquivos/diretórios
- Opções `-n` e `-i` são cruciais para prevenir substituições acidentais
- A opção `-r` é necessária para copiar diretórios com conteúdo









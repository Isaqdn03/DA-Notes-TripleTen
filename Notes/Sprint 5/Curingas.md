
**2025-01-02 19:24**

**Sprint:** [[Sprint5]]

**Topic:** #intro-CLI 
 
**Connections:** 

---
# **Curingas**

# Curingas no Linux: Guia Completo

## Introdução aos Curingas
Os curingas (wildcards) são símbolos especiais utilizados para descrever padrões em strings no sistema Linux. Eles são fundamentais para operações com arquivos e diretórios.

### Tipos de Curingas
| Curinga | Símbolo | Função |
|---------|----------|---------|
| Asterisco | * | Qualquer sequência de caracteres |
| Interrogação | ? | Exatamente um caractere |
| Colchetes | [ ] | Caracteres específicos ou intervalos |
| Chaves | { } | Múltiplas correspondências |

## Curinga *: Asterisco

### Conceito
O asterisco (*) representa qualquer sequência de caracteres, incluindo sequência vazia.

### Exemplo Prático
```bash
ls file_*.txt
```
**Saída esperada:**
```
file_1.txt
file_2.txt
file_test.txt
file_data.txt
```

### Uso com rm
```bash
rm a*e.py
```
**Saída esperada:**
- Remove todos os arquivos que começam com 'a' e terminam com 'e.py'
- Exemplo: agile.py, apple.py

**Pontos-Chave:**
- Corresponde a zero ou mais caracteres
- Útil para operações em massa
- Requer cuidado ao usar com rm

## Curinga ?: Interrogação

### Conceito
Representa exatamente um caractere, nem mais nem menos.

### Exemplo Prático
```bash
ls file_?.txt
```
**Saída esperada:**
```
file_1.txt
file_a.txt
```
*Não incluirá:* file_10.txt, file_aa.txt

**Pontos-Chave:**
- Corresponde a exatamente um caractere
- Útil para padrões com comprimento fixo
- Case sensitive

## Curinga [ ]: Colchetes

### Conceito
Usado para especificar caracteres ou intervalos específicos.

### Exemplos Práticos
```bash
# Listando arquivos com 'r' ou 'y'
ls e[ry]e.txt
```
**Saída esperada:**
```
ere.txt
eye.txt
```

### Intervalos
```bash
# Usando intervalo de letras
ls [a-g]*.txt
```
**Saída esperada:**
- Arquivos começando com letras de 'a' até 'g'

**Pontos-Chave:**
- Permite especificar conjuntos de caracteres
- Suporta intervalos com hífen
- Diferencia maiúsculas/minúsculas
- Pode combinar intervalos: [a-zA-Z]

## Curinga { }: Chaves

### Conceito
Utilizado para especificar múltiplos padrões simultaneamente.

### Exemplo Prático
```bash
ls {file*.txt,e[vw]e.txt}
```
**Saída esperada:**
```
file1.txt
file2.txt
eve.txt
ewe.txt
```

### Criação de Ambiente de Teste
```bash
mkdir quiz_4_dir
cd quiz_4_dir
touch file1.txt file2.txt ere.txt eye.txt ewe.txt eve.txt
```
**Saída esperada:**
- Criação de diretório e arquivos para teste

**Pontos-Chave:**
- Permite múltiplos padrões
- Pode ser combinado com outros curingas
- Útil para operações complexas de arquivo

# Boas Práticas de Segurança

## Testes Seguros
1. Sempre teste padrões com `ls` antes de usar `rm`
2. Use ferramentas como regex101.com para validar padrões
3. Faça backup de arquivos importantes antes de operações em massa

# Resumo
- Os curingas são ferramentas poderosas para manipulação de arquivos no Linux
- Cada curinga tem um propósito específico:
  - * para qualquer sequência
  - ? para um caractere
  - [] para conjuntos específicos
  - {} para múltiplos padrões
- A segurança é crucial ao usar curingas, especialmente com comandos destrutivos
- Testes prévios com `ls` podem prevenir perda acidental de dados










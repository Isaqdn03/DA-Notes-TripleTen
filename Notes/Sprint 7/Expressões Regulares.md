
**2025-02-20 10:31**

**Sprint:** [[Sprint7]]

**Topic:** #extraindo-dados-online 

**Connections:** 

---
# **Expressões Regulares**
## Introdução
Uma expressão regular (regex) é uma ferramenta poderosa para buscar e manipular strings baseada em padrões. São especialmente úteis para analistas que trabalham com grandes conjuntos de dados textuais.

> **Definição**: Uma expressão regular é uma regra para procurar por substrings (fragmentos de texto) dentro de strings maiores.

### Exemplo Prático
Na frase "Arrived at the station in total frustration", podemos buscar o padrão "tion", que aparece duas vezes: em "sta**tion**" e "frustra**tion**".

## Funcionamento das Expressões Regulares

### Processo Básico
1. Importação do módulo `re` em Python
2. Criação do padrão de expressão regular
3. Aplicação do padrão usando métodos específicos

## Padrões Básicos de Expressões Regulares

### Tabela de Sintaxe Básica

| Padrão | Significado | Exemplo | Resultado |
|--------|-------------|---------|-----------|
| `[]` | Um caractere dos listados | `[a-]` | "a" ou "-" |
| `[^...]` | Negação | `[^a]` | Qualquer caractere exceto "a" |
| `-` | Intervalo | `[0-9]` | Qualquer dígito de 0 a 9 |
| `.` | Qualquer caractere único | `a.` | "as", "a1", "a_" |
| `\d` | Qualquer dígito | `a\d` | "a1", "a2", "a3" |
| `\w` | Letra, dígito ou _ | `a\w` | "a1", "ab" |
| `?` | 0 ou 1 ocorrência | `a?` | "" ou "a" |
| `+` | 1 ou mais ocorrências | `a+` | "a", "aa", "aaa" |
| `*` | 0 ou mais ocorrências | `a*` | "", "a", "aa" |
| `^` | Início da string | `^a` | "a..." |
| `$` | Fim da string | `a$` | "...a" |

### Escapando Caracteres Especiais
Para usar caracteres especiais literalmente, use `\` antes do caractere:
- `\+` para um sinal de mais literal
- `\.` para um ponto literal
- `\\` para uma contrabarra literal

## Expressões Regulares em Python

### Principais Métodos do Módulo `re`

#### 1. search()
```python
import re
string = '"General Slocum" 15 June 1904 East River human factor'
match = re.search('\w+', string)
print(match.group())  # Saída: 'General'
```

#### 2. split()
```python
import re
string = '"General Slocum" 15 June 1904 East River human factor'
result = re.split('\d+', string)
print(result)  # Divide a string nos números
```

#### 3. sub()
```python
import re
string = '"General Slocum" 15 June 1904 East River human factor'
result = re.sub('\d+', '', string)
print(result)  # Remove todos os números
```

#### 4. findall()
```python
import re
text = "Arrived at the station in total frustration"
matches = re.findall('[A-z]+tion', text)
print(matches)  # ['station', 'frustration']
```

## Trabalhando com Diferentes Idiomas

### Padrão Universal para Caracteres Acentuados
```python
padrao_universal = '[a-zA-ZÀ-ÿ]'  # Captura letras com acentos
```

### Padrão Específico para Francês, Espanhol e Português
```python
padrao_especifico = '[a-zA-Z àâäèéêëîïôœùûüÿçÀÂÄÈÉÊËÎÏÔŒÙÛÜŸÇ]'
```

## Recursos Adicionais para Aprendizado

*Sites Recomendados:*
- regexone.com (prática interativa)
- regexr.com (teste de expressões)
- debuggex.com (referência rápida)

# Resumo Geral

**Pontos-Chave:**
- Expressões regulares são ferramentas poderosas para busca e manipulação de texto
- O módulo `re` do Python oferece métodos completos para trabalhar com regex
- Diferentes idiomas requerem padrões específicos para caracteres especiais
- A prática é fundamental para dominar expressões regulares
- Existem várias ferramentas online para testar e aprender regex

**Aplicações Práticas:**
- Validação de dados
- Extração de informações específicas
- Processamento de texto em diferentes idiomas
- Análise de grandes conjuntos de dados textuais
- Limpeza e transformação de dados











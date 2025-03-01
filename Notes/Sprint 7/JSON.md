
**2025-02-21 09:54**

**Sprint:** [[Sprint7]]

**Topic:** #extraindo-dados-online 

**Connections:** 

---
# JSON (JavaScript Object Notation)

## Introdução ao JSON
JSON é um formato de dados leve e independente de linguagem usado para intercâmbio de dados entre sistemas.

> "JSON significa JavaScript Object Notation (Notação de Objetos JavaScript) e é um dos formatos mais comuns para transferência de dados estruturados em aplicações web."

### Características Principais
- Formato texto simples e legível
- Independente de linguagem
- Estrutura hierárquica
- Amplamente suportado

## Estrutura e Sintaxe do JSON

### Formatos Básicos
1. **Objeto**: Conjunto de pares chave-valor entre chaves `{}`
2. **Array**: Lista ordenada de valores entre colchetes `[]`

### Exemplo de Estrutura Básica
```json
{
  "name": "General Slocum",
  "date": "June 15, 1904"
}
```

### Tipos de Dados Suportados
| Tipo | Exemplo | Descrição |
|------|---------|-----------|
| String | `"texto"` | Texto entre aspas duplas |
| Número | `86.9` | Inteiros ou decimais |
| Booleano | `true/false` | Valores lógicos |
| Null | `null` | Valor nulo |
| Array | `[...]` | Lista ordenada de valores |
| Objeto | `{...}` | Conjunto de pares chave-valor |

### Estruturas Aninhadas
```json
{
  "name": "Camorta",
  "length": 86.9,
  "decks": 3,
  "details": {
	"place": "Bay of Bengal",
    "reason": "Force of nature"
  }
}
```

## Trabalhando com JSON em Python

### Módulo json
O Python fornece um módulo built-in para manipulação de JSON:

```python
import json
```

### Principais Métodos

#### 1. json.loads() - JSON para Python
```python
# Convertendo string JSON para objeto Python
x = '{"name": "General Slocum", "date": "June 15, 1904"}'
y = json.loads(x)
print('Name: {0}, date: {1}'.format(y['name'], y['date']))
```

**Saída esperada:**
```
Name: General Slocum, date: June 15, 1904
```

#### 2. json.dumps() - Python para JSON
```python
# Convertendo objeto Python para string JSON
dados_python = {"name": "Camorta", "date": "May 6, 1902"}
json_string = json.dumps(dados_python)
print(json_string)
```

### Trabalhando com Listas de Objetos
```python
x = '''[
    {"name": "General Slocum", "date": "June 15, 1904"},
    {"name": "Camorta", "date": "May 6, 1902"}
]'''
y = json.loads(x)
for item in y:
    print('Name: {0}, date: {1}'.format(item['name'], item['date']))
```

## Mapa Mental: Fluxo de Dados JSON
[Descrição do mapa mental]
- JSON String ⟷ json.loads() ⟷ Objeto Python
- Objeto Python ⟷ json.dumps() ⟷ JSON String

## Melhores Práticas

**Validação e Tratamento:**
- Sempre verifique a estrutura do JSON antes de processar
- Use try/except ao converter JSON
- Valide tipos de dados esperados

**Formatação:**
- Use aspas duplas para chaves
- Mantenha a indentação consistente
- Evite comentários no JSON

# Resumo Geral

**Pontos-Chave:**
- JSON é um formato de dados leve e independente de linguagem
- Suporta diferentes tipos de dados (strings, números, booleanos, etc.)
- Python oferece métodos nativos para manipulação de JSON (json.loads() e json.dumps())
- É ideal para transferência de dados entre sistemas

**Aplicações Práticas:**
- APIs Web
- Configurações de aplicações
- Armazenamento de dados estruturados
- Comunicação cliente-servidor











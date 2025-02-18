
**2025-02-10 19:26**

**Sprint:** [[Sprint6]]

**Topic:** #python-em-mais-detalhes 

**Connections:** 

---
# **Funções - retorno de valores**

## Fundamentos do Return
O comando `return` é uma palavra-chave fundamental em Python que permite que funções retornem valores após sua execução. 

### Características Principais
- Encerra imediatamente a execução da função
- Pode retornar qualquer tipo de valor
- Todo código após o `return` não será executado
- Uma função sempre retorna um valor (mesmo que implicitamente)

## Múltiplos Returns em uma Função

### Exemplo Prático: Função Omelete
```python
def omelet(eggs_number=2):
    if eggs_number > 0:
        return 'A omelete está pronta! Ovos usados: ' + str(eggs_number)
    else:
        return 'Como fazer uma omelete sem ovos?'
    print('Eu nunca serei impressa :(')  # Código inalcançável

print(omelet(3))
print(omelet(0))
```

**Saída esperada:**
```
A omelete está pronta! Ovos usados: 3
Como fazer uma omelete sem ovos?
```

### Pontos Importantes:
- Apenas o primeiro `return` encontrado será executado
- Útil para tratamento de diferentes condições
- Código após um `return` não será executado

## Retorno de Múltiplos Valores

### Exemplo: Cálculo de Área e Perímetro
```python
def area_and_perim(side_1, side_2):
    area = side_1 * side_2
    perimeter = 2 * (side_1 + side_2)
    return area, perimeter

print(area_and_perim(2, 3))
```

**Saída esperada:**
```
(6, 10)
```

### Características do Retorno Múltiplo:
- Valores são agrupados em uma tupla
- Separados por vírgulas após o `return`
- Podem ser de diferentes tipos
- Não há limite para quantidade de valores retornados

## Desagrupamento de Valores Retornados

### Exemplo Prático:
```python
def find_area_and_perim(side1, side2):
    area = side1 * side2
    perimeter = 2 * (side1 + side2)
    return area, perimeter

# Desagrupamento em variáveis
rec_area, rec_perimeter = find_area_and_perim(7, 3)

print(f'A área do retângulo é {rec_area}, o perímetro é {rec_perimeter}')
```

**saida de espera:**
```
A área do retângulo é 21, o perímetro é 20
```
### Boas Práticas no Desagrupamento:
| Aspecto | Recomendação | Motivo |
|---------|--------------|---------|
| Nomes de Variáveis | Usar nomes diferentes para variáveis locais e globais | Facilita leitura e depuração |
| Ordem | Manter correspondência entre ordem do return e do desagrupamento | Evita erros de atribuição |
| Quantidade | Número de variáveis deve corresponder aos valores retornados | Evita erros de desempacotamento |

## Pontos-Chave:
- O `return` encerra imediatamente a execução da função
- É possível ter múltiplos `return` em diferentes pontos da função
- Funções podem retornar múltiplos valores usando vírgulas
- Valores múltiplos são automaticamente agrupados em tuplas
- O desagrupamento permite atribuir valores retornados a variáveis individuais

# Resumo Geral
As funções em Python oferecem grande flexibilidade no retorno de valores, permitindo tanto retornos condicionais através de múltiplos `return` quanto o retorno de múltiplos valores em uma única instrução. O sistema de desagrupamento facilita o trabalho com valores múltiplos retornados, mas requer atenção à ordem e nomenclatura das variáveis. A compreensão dessas características é fundamental para escrever código Python eficiente e bem organizado.








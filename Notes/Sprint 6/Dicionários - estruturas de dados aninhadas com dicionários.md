
**2025-02-06 20:51**

**Sprint:** [[Sprint6]]

**Topic:** #python-em-mais-detalhes 

**Connections:** 

---
# **Dicionários - estruturas de dados aninhadas com dicionários**

## 1. Fundamentos de Dicionários
### 1.1 Métodos Principais
Os dicionários em Python possuem três métodos fundamentais para acessar seus elementos:

- **values()**: Extrai apenas os valores
- **keys()**: Extrai apenas as chaves
- **items()**: Extrai pares de chave-valor

### Exemplo Prático: Dados Financeiros
```python
financial_info = {
    'American Express': 93.23,
    'Boeing': 178.44,
    'Coca-Cola': 45.15,
    'Walt Disney': 119.34,
    'Nike': 97.99,
    'JPMorgan': 96.27,
    'Walmart': 130.68 
}

for value in financial_info.values():
    print(value)
```

*Saída esperada:*
```
93.23
178.44
45.15
119.34
97.99
96.27
130.68
```

## 2. Estruturas de Dados Aninhadas

### 2.1 Dicionários de Listas
Um dicionário de listas é uma estrutura onde cada chave do dicionário está associada a uma lista de valores.

#### Exemplo: Itinerário de Ônibus
```python
bus_schedule = {
    '72': ['8:00', '12:00', '17:30'],
    '26': ['9:30', '15:00'],
    '17': ['7:30', '12:30', '15:30']
}
```

**Iteração sobre dicionário de listas:**
```python
for route, times in bus_schedule.items():
    for time in times:
        print(f"Linha {route} - Partida {time}")
```

### 2.2 Listas de Dicionários
Uma estrutura que combina a flexibilidade dos dicionários com a ordenação das listas.

#### Comparação de Estruturas
| Característica | Lista de Listas | Lista de Dicionários |
|----------------|----------------|---------------------|
| Acesso aos dados | Por índices numéricos | Por chaves nomeadas |
| Legibilidade | Menor | Maior |
| Manutenção | Mais complexa | Mais simples |
| Uso de memória | Mais eficiente | Menos eficiente |

#### Exemplo: Catálogo de Filmes
```python
# Lista de dicionários
movies_table = [
    {
        'movie_name': 'The Shawshank Redemption',
        'country': 'USA',
        'genre': 'drama',
        'year': 1994,
        'duration': 142,
        'rating': 9.111
    },
    # ... outros filmes
]
```

## 3. Vantagens e Aplicações

### 3.1 Benefícios das Estruturas Aninhadas
- **Organização**: Melhor estruturação de dados complexos
- **Acessibilidade**: Acesso intuitivo através de chaves nomeadas
- **Flexibilidade**: Combinação de diferentes tipos de dados
- **Legibilidade**: Código mais compreensível e manutenível

### 3.2 Casos de Uso
7. **Sistemas de Agendamento**
   - Horários de ônibus
   - Agenda de compromissos
   - Programação de eventos

8. **Catálogos e Inventários**
   - Filmes e séries
   - Produtos em estoque
   - Bibliotecas digitais

9. **Dados Financeiros**
   - Cotações de ações
   - Histórico de transações
   - Relatórios financeiros

# Resumo Geral

As estruturas de dados aninhadas em Python oferecem uma maneira poderosa e flexível de organizar informações complexas:

10. **Dicionários de Listas**: Ideais para dados agrupados por categorias com múltiplos valores

11. **Listas de Dicionários**: Perfeitas para dados tabulares onde a nomenclatura das colunas é importante

12. **Escolha da Estrutura**: Depende da natureza dos dados e do caso de uso específico
   - Use dicionários de listas quando precisar agrupar valores relacionados
   - Use listas de dicionários quando trabalhar com dados tabulares que precisam de campos nomeados

13. **Melhores Práticas**:
   - Mantenha consistência na estrutura dos dados
   - Use nomes de chaves descritivos
   - Considere a facilidade de manutenção ao escolher a estrutura

*Pontos-Chave para Lembrar:*
- A escolha da estrutura impacta diretamente a legibilidade e manutenibilidade do código
- Estruturas aninhadas permitem representar dados complexos de forma organizada
- A combinação de listas e dicionários oferece o melhor dos dois mundos: ordenação e acesso nomeado









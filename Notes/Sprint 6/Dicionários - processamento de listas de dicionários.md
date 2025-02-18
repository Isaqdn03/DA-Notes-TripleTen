
**2025-02-10 18:29**

**Sprint:** [[Sprint6]]

**Topic:** #python-em-mais-detalhes 

**Connections:** 

---
# **Dicionários - processamento de listas de dicionários**

## 1. Tipos de Estruturas Aninhadas

### 1.1 Dicionários de Listas
Um dicionário onde cada valor é uma lista.

**Exemplo - Horários de Ônibus:**
```python
bus_schedule = {
    '72': ['8:00', '12:00', '17:30'],
    '26': ['9:30', '15:00'],
    '17': ['7:30', '12:30', '15:30']
}
```

*Aplicação Prática:* Ideal para representar dados agrupados por uma chave, como horários de ônibus por linha, produtos por categoria, ou eventos por data.

### 1.2 Listas de Dicionários
Uma lista onde cada elemento é um dicionário.

**Estrutura:**
```python
[
    {chave1: valor1, chave2: valor2, ...},
    {chave1: valor1, chave2: valor2, ...}
]
```

*Aplicação Prática:* Perfeita para representar coleções de objetos com propriedades consistentes, como pedidos, registros de usuários ou itens de inventário.

## 2. Processamento de Dados

### 2.1 Cálculo de Totais
**Exemplo - Sistema de Pedidos:**
```python
order = [
    {
        'item': 'Margherita pizza',
        'category': 'pizza',
        'quantity': 2,
        'price': 9
    },
    # ... mais itens ...
]

total_price = 0
for item in order:
    total_price += item['price'] * item['quantity']
```

*Pontos-Chave:*
- Iteração sobre cada dicionário na lista
- Acesso aos valores através das chaves
- Cálculos com múltiplos valores do dicionário

### 2.2 Filtragem de Dados
**Exemplo - Filtrar por Categoria:**
```python
filtered_order = []
for item in order:
    if item['category'] == 'pizza':
        filtered_order.append(item)
```

*Processo de Filtragem:*
1. Criar lista vazia para armazenar resultados
2. Iterar sobre a lista original
3. Verificar condição de filtro
4. Adicionar itens que atendem à condição a lista vazia criada

## 3. Comparação de Estruturas

| Característica | Dicionário de Listas | Lista de Dicionários |
|----------------|---------------------|---------------------|
| Organização    | Dados agrupados por chave | Coleção de objetos similares |
| Acesso         | dict[chave][índice] | lista[índice][chave] |
| Uso Comum      | Agrupamento de valores relacionados | Registros/objetos estruturados |
| Exemplo        | Horários de ônibus | Pedidos de restaurante |

## 4. Dicas de Processamento

### 4.1 Boas Práticas
- Sempre verifique se a chave existe antes de acessá-la
- Use variáveis descritivas para armazenar resultados intermediários
- Mantenha a consistência na estrutura dos dicionários
- Comente código complexo para maior clareza

### 4.2 Padrões Comuns
5. **Soma de Valores:**
   ```python
   total = sum(item['value'] for item in lista_dicts)
   ```

6. **Filtragem:**
   ```python
   filtrados = [item for item in lista_dicts if item['categoria'] == valor]
   ```

# Resumo Geral

As estruturas de dados aninhadas em Python oferecem grande flexibilidade para organizar e processar dados complexos:

- **Dicionários de Listas:** Ideais para agrupar dados relacionados sob uma chave comum
- **Listas de Dicionários:** Perfeitas para coleções de objetos com estrutura similar
- **Processamento:** Combine iteração, condicionais e operações matemáticas para análise de dados
- **Aplicações:** Amplamente utilizadas em sistemas reais como e-commerce, análise de dados e gerenciamento de informações

A escolha entre diferentes estruturas depende das necessidades específicas do projeto, considerando fatores como organização dos dados, facilidade de acesso e eficiência no processamento.











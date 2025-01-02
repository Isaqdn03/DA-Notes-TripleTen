
**2024-10-28 19:31**

**Sprint:** [[Sprint3]]

**Topic:** #tipos-de-dados

**Connections:** 

# **Conjunto de dados à primeira vista**
### Main Topics of this Lesson:

# ANÁLISE EXPLORATÓRIA DE DADOS COM PANDAS

## 1. INTRODUÇÃO AO CONJUNTO DE DADOS
O conjunto de dados representa transações de um varejo online do Reino Unido, contendo informações de vendas entre 01/12/2010 e 09/12/2011.

### Estrutura do Dataset
- **InvoiceNo**: Número da fatura (6 dígitos)
- **StockCode**: Código do produto (5 dígitos)
- **Description**: Nome do produto
- **Quantity**: Quantidade vendida
- **InvoiceDate**: Data e hora da transação
- **UnitPrice**: Preço unitário em libras
- **CustomerID**: ID do cliente (5 dígitos)
- **Country**: País do cliente

## 2. CARREGAMENTO INICIAL DOS DADOS

```python
import pandas as pd 

df = pd.read_csv('/datasets/OnlineRetail.csv')
print(df.head())
```

### Explicação do Código:
- Importamos a biblioteca pandas
- Carregamos o CSV usando pd.read_csv()
- Visualizamos as primeiras linhas com df.head()

## 3. ANÁLISE DOS TIPOS DE DADOS

### Verificação de Tipos Inesperados

```python
print(df['StockCode'].min(), df['StockCode'].max())
# Resultado: 10002 m
```

### Observações Importantes:
1. StockCode aparentemente numérico contém strings (ex: '82494L', '84029G')
2. Python pode comparar strings com operadores > e <
3. As regras de comparação são diferentes para strings e números

## 4. INFORMAÇÕES DETALHADAS DO DATAFRAME

```python
df.info()
```

### Resultados Relevantes:
- Total de 50000 entradas
- Tipos de dados:
  - object: InvoiceNo, StockCode, Description, InvoiceDate, UnitPrice, Country
  - float64: Quantity, CustomerID
- Valores nulos em Description e CustomerID

## 5. PONTOS DE ATENÇÃO

### Inconsistências Identificadas:
1. **Quantity**: 
   - Tipo float64 em vez de int64
   - Comum em exportações de Excel para CSV

2. **UnitPrice**:
   - Tipo object em vez de float64
   - Requer investigação adicional

## 6. BOAS PRÁTICAS APRENDIDAS

1. ==Não assumir tipos de dados sem verificação, pois pandas nem sempre carrega as informacoes corretas==
2. ==Sempre usar df.info() antes de análises profundas==
3. ==Verificar inconsistências nos tipos de dados==
4. ==Considerar a origem dos dados (ex: exportação de Excel)==

## 7. PRÓXIMOS PASSOS
- Converter Quantity para int64
- Investigar e corrigir o tipo de UnitPrice
- Tratar valores ausentes
- Padronizar formatos de dados

Esta estrutura de anotações fornece uma visão clara e organizada do conteúdo, facilitando a consulta futura e o entendimento dos conceitos apresentados.









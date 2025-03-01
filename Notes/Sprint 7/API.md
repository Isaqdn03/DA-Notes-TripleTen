
**2025-02-20 15:38**

**Sprint:** [[Sprint7]]

**Topic:** #extraindo-dados-online 

**Connections:** 

---
# **API**

## Fundamentos de API

### O que é uma API?
Uma API (Application Programming Interface) é uma interface especial de transferência de dados que permite a comunicação entre diferentes sistemas de software. Ela fornece uma maneira simplificada de interagir com sistemas complexos sem necessidade de compreender sua estrutura interna.

> "API é uma interface que permite que desenvolvedores interajam com sistemas mesmo sem compreender exatamente como eles funcionam."

### Analogias do Mundo Real
Para entender melhor o conceito de API, podemos usar duas analogias práticas:

1. **Botão de Volume do Carro**
   - *Interface*: Botão físico
   - *Sistema Complexo*: Sistema de áudio do carro
   - *Simplicidade*: Não é necessário entender o funcionamento dos alto-falantes

2. **Tomada Elétrica**
   - *Interface*: Tomada na parede
   - *Sistema Complexo*: Sistema de distribuição elétrica
   - *Método de Interação*: Plugue padronizado

## APIs no Mundo Corporativo

### Aplicações Práticas
- **Redes Sociais**: Autenticação de usuários
- **E-commerce**: Processamento de pagamentos
- **Serviços Cloud**: Armazenamento e processamento de dados

## API de Previsão do Tempo (wttr.in)

### Características Principais
- API aberta (não requer cadastro)
- Endpoint base: `http://wttr.in/`
- Suporte a múltiplas cidades
- Diferentes formatos de resposta

### Estrutura de URLs
```plaintext
Base URL: https://wttr.in/
Cidade específica: https://wttr.in/{cidade}
Com parâmetros: https://wttr.in/{cidade}?parametro1&parametro2
```

## Implementação com Python

### Requisições GET com Parâmetros
```python
import requests

city = 'Lisbon'
URL = f'https://wttr.in/{city}'
PARAM = {"format": 4, "M": ""}
req = requests.get(url=URL, params=PARAM)
```

**Explicação do código:**
- Utiliza a biblioteca `requests`
- Define cidade e URL base
- Especifica parâmetros em um dicionário
- Realiza requisição GET com parâmetros

### Exemplo Prático: Previsão para Paris
```python
import requests

city = 'Paris'
BASE_URL = f'https://wttr.in/{city}'
PARAM = {"format": 1, "m": ""}

response = requests.get(BASE_URL, params=PARAM)
print(response.text)
```

Saída esperada:
```
☁️   +10°C
```

### Exemplo Prático: Previsão para Roma Extensa
```python
import requests

city = 'Roma'# escreva sua cidade
BASE_URL = f'https://wttr.in/{city}'
# URL para o método get() 
params = { 'm': "" }

response = requests.get(BASE_URL, params=params)
print(response.text)
```

Saida esperada:
```
#jogue este codigo em uma IDE e confira o reseultado
```
## Referência de Parâmetros

### Tabela de Parâmetros Disponíveis
| Parâmetro | Descrição | Tipo | Valores Possíveis |
|-----------|-----------|------|-------------------|
| m | Sistema métrico (SI) | opcional | "" |
| format | Formato da resposta | opcional | 1-4, j1 (JSON) |
| 0 | Temperatura atual | opcional | "" |
| 1 | Temp. atual + hoje | opcional | "" |
| 2 | Atual + hoje + amanhã | opcional | "" |
| lang | Idioma da resposta | opcional | Códigos de idioma |

### Boas Práticas
1. **Uso de Parâmetros**:
   - Preferir `params` em vez de concatenação na URL
   - Manter parâmetros organizados em dicionário
   - Documentar valores utilizados

2. **Estruturação de Requisições**:
   - Separar URL base dos parâmetros
   - Validar resposta antes do uso
   - Tratar possíveis erros
# Resumo Geral

**Principais Conceitos Aprendidos:**
- APIs são interfaces que simplificam a comunicação entre sistemas
- Requisições GET podem incluir parâmetros para personalizar respostas
- A API wttr.in oferece previsões do tempo em diferentes formatos
- Python + requests facilita o consumo de APIs
- Parâmetros podem ser passados de forma organizada via dicionário

**Aplicações Práticas:**
- Consulta de previsão do tempo para diferentes cidades
- Personalização de formato de resposta
- Integração com outros sistemas via API
- Automação de consultas meteorológicas

Esta documentação fornece uma base sólida para entender e trabalhar com APIs, especialmente no contexto de serviços meteorológicos, usando Python como ferramenta principal de implementação.










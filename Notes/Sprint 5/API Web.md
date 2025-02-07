
**2025-01-21 16:06**

**Sprint:** [[Sprint5]]

**Topic:** #python-intermediario 

**Connections:** 

---
# **API Web**
# APIs Web e HTTP

## Fundamentos do HTTP
HTTP (Hypertext Transfer Protocol) é um protocolo de transferência de dados na internet que permite a comunicação entre sistemas computacionais, principalmente entre navegadores e servidores web.

**Pontos-Chave:**
- Protocolo padrão para transferência de dados na web
- Permite comunicação cliente-servidor
- Pode ser usado por navegadores ou programas

## APIs REST
REST (Representational State Transfer) é um estilo de arquitetura de software que define princípios para a criação de serviços web.

**Características principais:**
- Comunicação cliente-servidor independente
- Uso de URIs/URLs para identificação de recursos
- Solicitações HTTP autossuficientes
- Formato JSON para troca de dados
- Respostas uniformes e consistentes

# Trabalhando com APIs em Python

## Biblioteca Requests
A biblioteca requests é uma ferramenta popular para trabalhar com APIs web em Python.

Você está certo, vou refazer as partes que faltaram explicações detalhadas após os códigos. Vou mostrar especificamente para alguns exemplos importantes:

### Exemplo Básico - Frankfurter API

```python
import requests

response = requests.get("https://api.frankfurter.app/latest")
print(response)
```

**Explicação do código:**
Este código faz uma solicitação HTTP GET básica para a API Frankfurter. A função `requests.get()` envia a requisição para o endpoint "/latest" e retorna um objeto `response`. O print mostra apenas o status da resposta.

**Saída esperada:**
```
<Response [200]>
```

O código de status 200 indica que a requisição foi bem-sucedida. É o código padrão para uma resposta HTTP bem-sucedida.

### Obtendo Dados JSON

```python
import requests

response = requests.get("https://api.frankfurter.app/latest")
print(response.json())
```

**Explicação do código:**
Aqui, além de fazer a requisição, estamos usando o método `.json()` do objeto response para converter a resposta do servidor em um dicionário Python. Isso é possível porque a API retorna os dados no formato JSON. O método `.json()` automaticamente faz o parsing dessa resposta.

**Saída esperada:**
```python
{
    'amount': 1.0,
    'base': 'EUR',
    'date': '2022-04-19',
    'rates': {
        'USD': 1.0803,
        'GBP': 0.82955,
        # ... outros valores de moedas
    }
}
```

A resposta nos mostra:
- `amount`: o valor base para a conversão (1.0)
- `base`: a moeda base (EUR - Euro)
- `date`: a data das taxas de câmbio
- `rates`: um dicionário com todas as taxas de conversão disponíveis

### Usando Parâmetros de Consulta

```python
import requests

params = {"from":"USD", "to":"GBP", "amount":20}
res = requests.get("https://api.frankfurter.app/latest", params=params)
print(res.json())
```

**Explicação do código:**
Este exemplo demonstra como enviar parâmetros de consulta para a API:
1. Criamos um dicionário `params` com os parâmetros desejados
2. A biblioteca requests automaticamente converte esses parâmetros para a format URL correta
3. Os parâmetros especificam:
   - `from`: moeda de origem (USD)
   - `to`: moeda de destino (GBP)
   - `amount`: quantidade a ser convertida (20)

**Saída esperada:**
```python
{
    'amount': 20.0,
    'base': 'USD',
    'date': '2022-04-19',
    'rates': {'GBP': 15.3578}
}
```

A resposta nos mostra que 20 USD equivalem a aproximadamente 15.36 GBP na data especificada.

### Trabalhando com Headers

```python
import requests

response = requests.get("https://api.frankfurter.app/latest")

print(response.headers['Server'])
print(response.headers['Content-Type'])
print(response.headers['Content-Length'])
```

**Explicação do código:**
Este código demonstra como acessar os cabeçalhos HTTP da resposta:
1. Fazemos uma requisição GET normal
2. Acessamos diferentes campos do cabeçalho através do dicionário `headers`
3. Cada campo fornece informações específicas sobre a resposta

**Saída esperada:**
```
nginx/1.21.3
application/json; charset=utf-8
457
```

Estas informações nos dizem que:
- O servidor é nginx versão 1.21.3
- O conteúdo está em formato JSON com codificação UTF-8
- O tamanho da resposta é 457 bytes

### AccuWeather - Busca de Localização

```python
import requests

api_key = 'zC5JOYIAeAgn92Z9CJKUQE1ns3dvHeyf'  # exemplo
params = {'apikey': api_key, 'q': 'New York'}

aw_location_url = "https://dataservice.accuweather.com/locations/v1/cities/search"
aw_location_res = requests.get(aw_location_url, params=params)
```

**Explicação do código:**
Este código demonstra como fazer uma requisição autenticada:
1. Definimos a chave da API (que deve ser mantida segura)
2. Criamos um dicionário de parâmetros incluindo:
   - `apikey`: nossa chave de autenticação
   - `q`: o termo de busca (New York)
3. Fazemos a requisição GET incluindo estes parâmetros

A requisição retorna informações sobre todas as cidades chamadas "New York" encontradas no banco de dados do AccuWeather.

**Saída formatada:**
```python
for loc_info in aw_location_res.json():
    print('{:>8}   {:10}   {:16}    {:16}'.format(
        loc_info['Key'],
        loc_info['EnglishName'],
        loc_info['Country']['EnglishName'],
        loc_info['AdministrativeArea']['EnglishName']))
```

**Explicação do código de formatação:**
Este código formata a saída dos resultados:
- Usa formatação de string com alinhamento e larguras fixas
- Extrai informações específicas de cada local:
  - Key: identificador único da cidade
  - EnglishName: nome da cidade em inglês
  - Country: país onde está localizada
  - AdministrativeArea: estado ou região administrativa

**Saída esperada:**
```
  349727   New York     United States       New York        
  710949   New York     United Kingdom      Lincolnshire    
  # ... outras localizações
```

Esta saída formatada nos permite ver claramente as diferentes localizações chamadas "New York" e suas informações relevantes em um formato tabular organizado.

# Resumo

- HTTP é o protocolo fundamental para comunicação web
- APIs REST fornecem uma interface padronizada para interação com serviços web
- Python + requests é uma combinação poderosa para trabalhar com APIs
- Autenticação é comum em APIs comerciais e requer gerenciamento seguro de credenciais
- JSON é o formato padrão para troca de dados em APIs modernas

**Pontos-Chave Finais:**

- APIs permitem integração programática com serviços web
- Dados podem ser recuperados e processados automaticamente
- Segurança e autenticação são aspectos cruciais
- Documentação da API é fundamental para uso efetivo










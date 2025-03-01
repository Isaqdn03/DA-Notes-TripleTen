
**2025-02-18 09:13**

**Sprint:** [[Sprint7]]

**Topic:** #extraindo-dados-online 

**Connections:** 

---
# **Requisição GET**

## Fundamentos de Requisições GET

### O que é uma Requisição GET?
Uma requisição GET é um método HTTP utilizado para **obter dados de um servidor**. É um dos métodos mais fundamentais e comumente utilizados na comunicação cliente-servidor.

> *GET é um método de requisição HTTP que solicita a representação de um recurso específico do servidor.*

### Biblioteca Requests em Python
Para realizar requisições HTTP em Python, utilizamos a biblioteca **Requests**. 

```python
import requests  # Importação da biblioteca
```

## Implementação Prática

### 1. Configurando a URL
A URL (Uniform Resource Locator) é o endereço do recurso que queremos acessar.

```python
URL = 'https://practicum-content.s3.us-west-1.amazonaws.com/new-markets/Data_sprint_6/web-sites/most_famous_shipwrecks_ptbr_1.html?etag=9fcc222cac30e287d2b645aa88bcf13e'
```

*Componentes da URL:*
- Protocolo (https://)
- Domínio (practicum-content.s3.us-west-1.amazonaws.com)
- Caminho (/new-markets/...)
- Parâmetros (etag=...)

### 2. Fazendo a Requisição
```python
req = requests.get(URL)  # Enviando a requisição GET
```

### 3. Manipulando a Resposta
O objeto de resposta possui diversos atributos úteis:

```python
# Obtendo o conteúdo textual
print(req.text)

# Verificando o status code
print(req.status_code)
```

## Códigos de Status HTTP

### Tabela de Códigos Comuns
| Código | Nome | Significado |
|--------|------|-------------|
| 200 | OK | Requisição bem-sucedida |
| 302 | Found | Página movida |
| 400 | Bad Request | Erro na sintaxe do pedido |
| 404 | Not Found | Página não encontrada |
| 500 | Internal Server Error | Erro do servidor |
| 502 | Bad Gateway | Erro na comunicação entre servidores |
| 503 | Server Unavailable | Servidor temporariamente indisponível |

### Categorias de Status
- **2xx**: Sucesso
- **3xx**: Redirecionamento
- **4xx**: Erro do cliente
- **5xx**: Erro do servidor

## Boas Práticas

### Verificação de Status
```python
if req.status_code == 200:
    print("Requisição bem-sucedida!")
    # Processar dados
else:
    print(f"Erro na requisição: {req.status_code}")
```

### Tratamento de Erros
É importante sempre verificar o status da resposta antes de processar os dados.

*Pontos-Chave:*
- Sempre verifique o código de status antes de processar a resposta
- Mantenha as URLs em variáveis para fácil manutenção
- Use tratamento de exceções ao fazer requisições
- Documente os endpoints utilizados

# Resumo Geral
As requisições GET são fundamentais para a comunicação cliente-servidor na web. Através da biblioteca Requests do Python, podemos facilmente enviar requisições e processar respostas. É crucial entender os códigos de status HTTP para garantir o correto tratamento de sucessos e erros nas requisições. A estrutura de URLs e a manipulação adequada das respostas são habilidades essenciais para qualquer desenvolvedor trabalhando com APIs web.










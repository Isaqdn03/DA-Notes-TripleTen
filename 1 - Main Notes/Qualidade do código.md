
**2025-01-25 12:05**

**Sprint:** [[Sprint5]]

**Topic:** #python-intermediario 

**Connections:** 

---
# **Qualidade do código**

# Qualidade de Código em Python

## Fundamentos da Qualidade de Código
A qualidade do código é essencial e se baseia em quatro pilares principais:
- Estilo de código
- Confiabilidade
- Performance
- Segurança

**Pontos-Chave:**
- Facilita a comunicação entre desenvolvedores
- Melhora a manutenibilidade
- Aumenta a previsibilidade do código

## Estilo de Código e PEP 8

### Regras Básicas de Estilo
- Indentação consistente
- Convenções de nomenclatura
- Espaçamento adequado

### Exemplo de Código com Problemas de Estilo
```python
def is_prime(n):
    if n <= 1:
        return False
    for i in range(2,int(math.sqrt(n) + 1)):
        if n % i == 0:
            return False
    return True

def main():
    """contém toda a lógica principal"""
    for i in range(100):
        if is_prime(i):
            print (i, end=' ')
    print();
```

**Problemas identificados:**
- Falta de espaço após vírgula
- Espaço desnecessário antes do ponto e vírgula
- Docstring inadequada

### Código Corrigido
```python
def is_prime(n):
    """Verifica se um número é primo."""
    if n <= 1:
        return False
    for i in range(2, int(math.sqrt(n) + 1)):
        if n % i == 0:
            return False
    return True

def main():
    """Imprime todos os números primos menores que 100."""
    for i in range(100):
        if is_prime(i):
            print(i, end=' ')
    print()
```

## Testes Unitários com pytest

### Exemplo de Teste Simples
```python
def sign(x):
    """Retorna o sinal de número."""
    if x == None:
        return None
    if x < 0:
        return -1
    return 1

def test_sign():
    assert sign(-10) == -1
    assert sign(10) == 1
    assert sign(0) == 1
    assert sign(None) == None
```

**Saída esperada do teste:**
```
========================== test session starts ================================
platform linux -- Python 3.9.12, pytest-6.2.5, py-1.10.0, pluggy-1.0.0
collected 1 item

sign.py .                                                                [100%]

========================== 1 passed in 0.03s ==================================
```

### Exemplo de Teste de Grupo Etário
```python
def get_age_group(age):
    """
    Retorna a faixa etária com base na idade em anos dentro do intervalo 0..150
    caso contrário, retorna 'desconhecido'.
    """
    if age < 0 or age > 150:
        return 'desconhecido'
    if 0 <= age <= 14:
        return 'crianças'
    if 15 <= age <= 24:
        return 'jovens'
    if 25 <= age <= 64:
        return 'adultos'
    return 'idosos'
```

**Saída esperada dos testes:**
```
====================================== test session starts ======================================
platform win32 -- Python 3.12.7, pytest-7.4.4, pluggy-1.0.0
collected 1 item

age_group.py .                                                                             [100%]

================== 1 passed in 0.01s ==================
```

# O Zen do Python
Princípios fundamentais que guiam o desenvolvimento em Python:
- Simplicidade e clareza
- Explicitidade sobre implicidade
- Legibilidade como prioridade
- Praticidade sobre pureza

**Pontos-Chave:**
- São diretrizes, não regras rígidas
- Focam na qualidade e manutenibilidade do código
- Enfatizam a importância da clareza e simplicidade

# Resumo
- A qualidade do código é fundamental para projetos sustentáveis
- O estilo de código deve seguir padrões estabelecidos (PEP 8)
- Testes unitários são essenciais para garantir a confiabilidade
- Documentação clara e consistente facilita a manutenção
- O Zen do Python fornece princípios guia para boas práticas


[PEP 8 – Guia de estilo para códigos Python](https://peps.python.org/pep-0008/)

[PEP 20 – O Zen do Python](https://peps.python.org/pep-0020/)

[PEP 257 – Convenções docstring](https://peps.python.org/pep-0257/)

[Guia de estilo de Python do Google](https://google.github.io/styleguide/pyguide.html)

[O guia do mochileiro para Python: Estilo de código](https://docs.python-guide.org/writing/style/)








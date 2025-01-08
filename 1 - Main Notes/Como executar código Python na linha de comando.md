
**2025-01-07 19:13**

**Sprint:** [[Sprint5]]

**Topic:** #ambiente-de-programacao

**Connections:** 

---
# **Como executar código Python na linha de comando**

# Executando Python na Linha de Comando

## Introdução
Este guia explica como executar código Python através da linha de comando, cobrindo tanto a execução de scripts quanto o uso do interpretador interativo.
## Executando Scripts Python (.py)

### Preparação do Ambiente
- **Windows**: Usar Anaconda Navigator + Powershell Prompt
- **Mac/Linux**: Usar Terminal

### Estrutura do Comando
```bash
python nome_do_arquivo.py
```

Exemplo com cpus.py:
```bash
(base) PS D:\Documents\Python Scripts> python cpus.py
```

Saída esperada:
```
[Número de núcleos de CPU no computador]
```

### Componentes do Prompt
- **(base)**: Indica o ambiente Anaconda ativo
- **PS**: Indica PowerShell
- **Diretório atual**: Mostra o caminho onde o comando está sendo executado

## Modo Interativo (REPL)

### Iniciando o REPL
```bash
python
```

Saída esperada:
```
Python 3.8.10 (ou sua versão)
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

### Exemplos de Uso
```python
>>> print('Hello world')
```

Saída esperada:
```
Hello world
>>>
```

### Trabalhando com Variáveis
```python
>>> x = 5
>>> y = x + 3
>>> print(y)
```

Saída esperada:
```
8
```

### Saindo do REPL
```python
>>> exit()
```

*Pontos-Chave:*
- O modo interativo mantém variáveis na memória durante a sessão
- Útil para testes rápidos de código
- Todas as variáveis são perdidas ao encerrar a sessão

# Resumo
- Scripts Python (.py) podem ser executados diretamente da linha de comando
- O modo interativo (REPL) permite execução de código em tempo real
- O ambiente base do Anaconda fornece todas as ferramentas necessárias
- O REPL é ideal para testes rápidos e experimentação
- Scripts são melhores para programas maiores e permanentes

**Observações Importantes:**
- Sempre verifique se está no diretório correto antes de executar scripts
- O ambiente base do Anaconda é suficiente para a maioria das tarefas
- O modo interativo é uma ferramenta valiosa para aprendizado e debugging










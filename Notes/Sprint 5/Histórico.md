
**2025-01-06 19:16**

**Sprint:** [[Sprint5]]

**Topic:** #intro-CLI 

**Connections:** 

---
# **Histórico**

# Comando History no Terminal

## Introdução ao History
O comando `history` é uma ferramenta essencial do Terminal que permite visualizar os comandos anteriormente executados na sessão atual.

## Uso Básico
Para ver o histórico de comandos, basta digitar:

```bash
history
```

Saída esperada (exemplo de primeira execução):
```
1  history
```

**Explicação:** O comando exibe uma lista numerada, onde cada linha começa com um índice seguido do comando executado.

## Visualizando Múltiplos Comandos
Após executar vários comandos, o histórico mostra a sequência completa:

```bash
1  history
2  ls
3  pwd
4  history
```

**Explicação:** Cada comando recebe um número sequencial, permitindo fácil referência e execução posterior.

## Limitando a Saída
Para ver apenas os últimos N comandos, use `history N`:

```bash
history 3
```

Saída esperada:
```
3  pwd
4  history
5  history 3
```

**Explicação:** O argumento numérico (3) limita a saída aos três últimos comandos executados.

## Salvando o Histórico
Para salvar o histórico em um arquivo:

```bash
history > history.txt
```

**Explicação:** O operador `>` redireciona a saída do comando `history` para um arquivo chamado `history.txt` no diretório atual.

## Filtrando o Histórico
Para encontrar comandos específicos, combine `history` com `grep`:

```bash
history | grep pwd
```

Saída esperada:
```
3  pwd
7  history | grep pwd
```

**Explicação:** 
- O pipe (`|`) envia a saída do `history` para o `grep`
- O `grep` filtra apenas as linhas que contêm "pwd"

## Combinando com Outros Comandos
Exemplo usando `head` para limitar o número de linhas:

```bash
history | head -2
```

Saída esperada:
```
1  history
2  ls
```

**Explicação:** O comando mostra apenas as duas primeiras linhas do histórico.

# Pontos-Chave
- O comando `history` mostra todos os comandos executados na sessão atual
- Cada comando recebe um número sequencial único
- É possível limitar o número de comandos exibidos
- O histórico pode ser salvo em um arquivo
- Pode ser combinado com outros comandos como `grep` e `head` para filtragem
- O pipe (`|`) permite encadear comandos para manipular a saída do histórico

# Resumo
O comando `history` é uma ferramenta poderosa para gerenciar e revisar comandos executados no Terminal. Permite visualizar, filtrar, salvar e manipular o histórico de comandos, facilitando a referência a comandos anteriores e a automação de tarefas repetitivas.












**2025-01-21 19:14**

**Sprint:** [[Sprint5]]

**Topic:** #ferramentas-de-desenvolvimento 

**Connections:** 

---
# **Tabela de Comandos Git**
# Tabela de Comandos Git e Suas Explicações

| Comando | Sintaxe | Explicação | Saída Esperada/Observações |
|---------|---------|------------|---------------------------|
| git clone | `git clone https://github.com/numpy/numpy` | Cria uma cópia local completa do repositório especificado pela URL | ```Cloning into 'numpy'...remote: Counting objects: XXXXX, done.remote: Compressing objects: 100%, done.remote: Total XXXXX (delta YY), reused ZZZZ (delta WW)Receiving objects: 100%, done.``` |
| git pull | `git pull` | Atualiza o repositório local com as últimas alterações do repositório remoto | `Already up to date.` (quando já está atualizado) |
| git add | `git add .` | Prepara todas as alterações no diretório atual para confirmação. O ponto (.) significa "todos os arquivos" | Não produz saída visível |
| git commit | `git commit -m "mensagem"` | Confirma as alterações preparadas com uma mensagem descritiva | ```[main XXXXXX] add notes file 1 file changed, X insertions(+), Y deletions(-)``` |
| git commit (combinado) | `git commit -am "mensagem"` | Combina os comandos add e commit em uma única operação | Similar ao git commit normal |
| git push | `git push` | Envia as alterações confirmadas para o repositório remoto | Requer autenticação e Token de Acesso Pessoal |

## Observações Importantes:
- Os comandos devem ser executados na sequência correta do fluxo de trabalho
- É recomendado fazer commits pequenos e frequentes
- Use mensagens descritivas nos commits
- Mantenha o repositório atualizado
- Sempre verifique as alterações antes do commit
- O push requer autenticação adequada e que o repositório pertença ao usuário











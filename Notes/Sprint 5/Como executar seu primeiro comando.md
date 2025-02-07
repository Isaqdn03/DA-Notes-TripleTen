
**2024-12-17 19:49**

**Sprint:** [[Sprint5]]

**Topic:** #intro-CLI
**Connections:** 

---

# Como executar seu primeiro comando

# Estrutura e Uso de Comandos CLI (Command Line Interface)

## Sintaxe Básica de Comandos
A estrutura básica de um comando segue o padrão:
```bash
comando [opções...][argumentos...]
```

**Pontos-chave:**
- Comandos são sensíveis a maiúsculas e minúsculas
- Elementos entre colchetes são opcionais
- Podem aceitar múltiplas opções e argumentos

## Opções de Comandos

### Formato das Opções
- Hífen simples (-): `-a`, `-r`
- Hífen duplo (--): `--reverse`, `--all`

### Exemplo Básico com ls
```bash
~$ ls
```
Saída esperada:
```
Documents Downloads Pictures
Desktop   Music     Videos
```

### Exemplo com Opção Reversa
```bash
~$ ls -r
```
Saída esperada:
```
Videos     Pictures  Desktop
Music      Downloads Documents
```

### Combinando Opções
```bash
~$ ls -ra
```
ou
```bash
~$ ls -r -a
```
Saída esperada:
```
.bash_history  Documents  .local
.config        Downloads  Music
Desktop        .hidden    Videos
```

**Pontos-chave:**
- Múltiplas opções podem ser combinadas após um único hífen
- A ordem das opções não importa
- Algumas opções têm versão curta (-a) e longa (--all)

## Argumentos em Comandos

### Exemplo com Argumento
```bash
~$ ls -r sql_project
```
Saída esperada:
```
wmo_norms_db.py       README.md
wmo_norms.db         LICENSE
wmo_norms.db-journal
```

**Pontos-chave:**
- Argumentos especificam sobre qual alvo o comando deve agir
- Podem ser caminhos, arquivos ou diretórios
- São passados após as opções

## Documentação e Ajuda

### Usando --help
```bash
~$ comando --help
```
Fornece:
- Descrição do comando
- Sintaxe de uso
- Lista de opções disponíveis
- Exemplos de uso

### Usando man (manual)
```bash
~$ man comando
```
Fornece:
- Documentação completa
- Descrição detalhada
- Exemplos de uso
- Informações técnicas

# Resumo
- Comandos CLI seguem uma estrutura consistente: `comando [opções] [argumentos]`
- Opções modificam o comportamento do comando e podem ser combinadas
- Argumentos especificam o alvo da ação do comando
- Documentação está disponível através de --help e man
- Opções podem usar hífen simples (-) ou duplo (--)
- É possível combinar múltiplas opções após um único hífen










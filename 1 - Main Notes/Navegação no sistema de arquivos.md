
**2024-12-18 20:12**

**Sprint:** [[Sprint5]]

**Topic:** #intro-CLI 

**Connections:** 

---
# **Navegação no sistema de arquivos**

# Navegação no Sistema de Arquivos Linux

## Introdução
A navegação no sistema de arquivos Linux é realizada através de comandos específicos que permitem visualizar e mudar entre diretórios. Os principais comandos para esta finalidade são `pwd`, `ls` e `cd`.

## Comando pwd (Print Working Directory)
O comando `pwd` mostra o caminho completo do diretório atual em que você está.

### Exemplo de Uso:
```bash
~$ pwd
```
Saída esperada:
```
/home/anthony/edu_materials
```

**Pontos-Chave:**
- `pwd` significa "print working directory"
- Mostra o caminho absoluto do diretório atual
- Útil para confirmar sua localização no sistema de arquivos

## Comando cd (Change Directory)
O comando `cd` permite mudar de um diretório para outro. Existem várias formas de utilizá-lo.

### Navegação Direta para Subdiretório
```bash
~$ cd intro_to_ml/
```
Saída esperada (verificada com pwd):
```
/home/anthony/edu_materials/intro_to_ml/
```

### Usando Meta-localização (./)
```bash
~$ cd ./intro_to_ml/
```
Saída esperada (mesma que anterior):
```
/home/anthony/edu_materials/intro_to_ml/
```

### Usando Caminho Absoluto
```bash
~$ cd /home/anthony/edu_materials/intro_to_ml/
```
Saída esperada (mesma que anteriores):
```
/home/anthony/edu_materials/intro_to_ml/
```

## Meta-localizações
As meta-localizações são atalhos especiais para navegação:

### Diretório Atual (./)
- Representa o diretório atual
- Uso opcional ao navegar para subdiretórios

### Diretório Superior (../)
Para voltar um nível no sistema de arquivos:
```bash
~$ cd ../
```
Saída esperada (verificada com pwd):
```
/home/anthony/
```

## Atalhos de Navegação
### Diretório Home (~)
```bash
~$ cd ~
```
Saída esperada:
```
/home/anthony/
```

**Pontos-Chave:**
- `~` é um atalho para o diretório home do usuário
- Sempre leva ao `/home/<usuário>/`

# Resumo
- `pwd`: Mostra o diretório atual
- `cd`: Muda de diretório
- Formas de navegação:
  * Caminho direto
  * Meta-localizações (./ e ../)
  * Caminho absoluto
  * Atalho home (~)
- A combinação de `pwd`, `ls` e `cd` fornece todas as ferramentas necessárias para uma navegação eficiente no sistema de arquivos Linux.











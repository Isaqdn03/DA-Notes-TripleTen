
**2025-02-18 07:48**

**Sprint:** [[Sprint7]]

**Topic:** #extraindo-dados-online 

**Connections:** 

---
# **Introdução a HTML**
## Conceito Fundamental
HTML é uma linguagem de marcação de hipertexto (*Hypertext Markup Language*) utilizada para estruturar conteúdo na web. 

> "O próprio nome diz para que serve: cada objeto da página precisa ser marcado para exibir o conteúdo corretamente."

### Anatomia de um Elemento HTML
Um elemento HTML consiste em:
- Tag de abertura: `<tag>`
- Conteúdo
- Tag de fechamento: `</tag>`

*Analogia Prática:*
As tags funcionam como sinais de trânsito em uma cidade:
- Entrada da cidade: Tag de abertura `<tag>`
- Área da cidade: Conteúdo
- Saída da cidade: Tag de fechamento `</tag>`

## Estrutura Básica de um Documento HTML

### Elementos Fundamentais
7. **Documento HTML**
```html
<html>
    <!-- Conteúdo do documento -->
</html>
```

8. **Cabeçalho**
```html
<head>
    <title>Título da página</title>
    <meta> <!-- Metainformações -->
</head>
```

9. **Corpo**
```html
<body>
    <!-- Conteúdo visível da página -->
</body>
```

## Tags Comuns e Seus Usos

### Elementos de Texto
- `<p>`: Define parágrafos
- `<div>`: Cria divisões/seções
- `<!-- -->`: Comentários no código

### Tabelas HTML
Estrutura hierárquica:
10. `<table>`: Container da tabela
11. `<tr>`: Linha da tabela
12. `<th>`: Célula de cabeçalho
13. `<td>`: Célula de dados

#### Exemplo Prático de Tabela
```html
<table id="student" class='Stanford'> 
    <tr> 
        <th>Sobrenome</th>
        <th>Nome</th> 
        <th>Grupo</th>
    </tr>
    <tr>
        <td>Smith</td> 
        <td>Alex</td> 
        <td>41-A</td> 
    </tr> 
</table>
```

## Atributos HTML

### Definição e Uso
Atributos fornecem informações adicionais sobre elementos HTML.

**Formato**: `name="value"`

### Atributos Principais
14. **id**
   - Identificador único
   - Exemplo: `id="student"`
   - Apenas um elemento por página pode ter um determinado id

15. **class**
   - Identificador compartilhável
   - Exemplo: `class="Stanford"`
   - Múltiplos elementos podem compartilhar a mesma classe
   
*Analogia*: Classes são como sobrenomes de família - vários elementos podem compartilhar a mesma classe.

### Tabela Comparativa: id vs class

| Característica | id | class |
|----------------|-----|--------|
| Unicidade | Único na página | Pode ser compartilhado |
| Uso típico | Identificação específica | Agrupamento de elementos |
| Quantidade por elemento | Um único id | Múltiplas classes possíveis |

## Pontos-Chave para Análise Web
- **Estrutura Hierárquica**: Documentos HTML seguem uma estrutura clara e aninhada
- **Identificação de Elementos**: Use tags e atributos para localizar informações específicas
- **Comentários**: Úteis para entender a estrutura do código (`<!-- -->`)
- **Tabelas**: Frequentemente usadas para dados estruturados
- **Atributos**: Fundamentais para identificação e seleção de elementos

# Resumo Geral
O HTML fornece a estrutura fundamental para páginas web através de um sistema de marcação baseado em tags e atributos. A compreensão desta estrutura é crucial para mineração de dados web eficiente. As tags delimitam diferentes tipos de conteúdo, enquanto os atributos fornecem informações adicionais e identificação para os elementos. O conhecimento da hierarquia de elementos HTML, especialmente em estruturas como tabelas, é essencial para extrair dados específicos de páginas web.











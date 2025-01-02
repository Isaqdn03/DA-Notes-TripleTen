
2024-10-07 18:23

Sprint:[[Sprint1]]

Topic: #basics 

# Listas

1. **Criação de uma lista:**
    
    - Lista é uma coleção de itens mutáveis em Python. Exemplo:
        
        ```python
        python
        Copy code
        favorite_films = ['The Graduate', 'Reservoir Dogs', 'Fear and Loathing in Las Vegas']
        
        ```
        
        - Tipo: `list`
        - Tamanho: `len(favorite_films)` → 3
2. **Listas podem conter múltiplos tipos de dados:**
    
    - Exemplo de lista com diferentes tipos:
        
        ```python
        python
        Copy code
        my_list = ['<3', 77, 3.89, True, False, ['sub', 'list', 0.2]]
        
        ```
        
3. **Acesso a elementos por índice:**
    
    - Índices começam em 0. Exemplo:
        
        ```python
        python
        Copy code
        movie_info = ['Fight Club', 1999, ['thriller', 'drama', 'crime'], 139, 8.644]
        print(movie_info[0])  # 'Fight Club'
        print(movie_info[2][1])  # 'drama' (acesso a lista aninhada)
        
        ```
        
4. **Modificação de listas (mutáveis):**
    
    - **Adicionar elementos:**
        
        - `append()`: Adiciona um único elemento ao final.
            
            ```python
            python
            Copy code
            shawshank_movie.append('Frank Darabont')
            
            ```
            
        - `extend()`: Adiciona múltiplos elementos de outra lista.
            
            ```python
            python
            Copy code
            titanic_movie.extend(['drama', 194])
            
            ```
            
        - `insert()`: Insere um elemento em um índice específico.
            
            ```python
            python
            Copy code
            dark_knight_movie.insert(2, 2008)
            
            ```
            
    - **Remover elementos:**
        
        - `pop()`: Remove o último item ou o de um índice específico.
            
            ```python
            python
            Copy code
            movies.pop()  # Remove o último
            movies.pop(1)  # Remove o segundo item
            
            ```
            
5. **Ordenação de listas:**
    
    - **`sort()`:** Ordena a lista original (método in-place). Exemplo:
        
        ```python
        python
        Copy code
        years = [1994, 1972, 2008]
        years.sort()  # Crescente
        years.sort(reverse=True)  # Decrescente
        
        ```
        
    - **`sorted()`:** Retorna uma nova lista ordenada, preservando a original.
        
        ```python
        python
        Copy code
        sorted_years = sorted(years)
        
        ```
        
6. **Listas aninhadas (nested lists):**
    
    - Lista dentro de lista. Exemplo:
        
        ```python
        python
        Copy code
        movies_info = [['The Shawshank Redemption', 'USA', 1994], ['The Godfather', 'USA', 1972]]
        
        ```
        
    - Acessando elementos de listas aninhadas:
        
        ```python
        python
        Copy code
        print(movies_info[0][2])  # 1994
        
        ```
        
7. **Dividir e combinar strings:**
    
    - **`split()`:** Converte uma string em lista:
        
        ```python
        python
        Copy code
        phrase = 'vamos dividir ou não vamos dividir'
        words = phrase.split()  # ['vamos', 'dividir', 'ou', 'não', 'vamos', 'dividir']
        
        ```
        
    - **`join()`:** Combina uma lista de strings em uma única string:
        
        ```python
        python
        Copy code
        words = ['Meu', 'filme', 'favorito', 'é', 'The', 'Graduate.']
        phrase = ' '.join(words)
        
        ```
        

### Dicas de Active Recall:

- **Criação e tipos de listas:** Como você cria uma lista e como identificar seu tipo e tamanho?
- **Modificação de listas:** Qual é a diferença entre `append()` e `extend()`? Como você removeria um elemento?
- **Acesso por índice:** Como acessar um elemento específico ou aninhado dentro de uma lista?
- **Ordenação:** Qual é a diferença entre `sort()` e `sorted()`?
- **Strings e listas:** Como você divide uma string em lista e combina os elementos em uma string novamente?











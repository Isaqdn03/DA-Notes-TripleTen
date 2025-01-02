
2024-10-07 22:37

Sprint: [[Sprint2]]

Topic: #dataframe-prepocess 


# Agrupamento de dados
# 5.6 Agrupamentos de dados

### **Anotações: Agrupamento em Pandas (`groupby`)**

1. **Quando agrupar dados?**
    
    - Use o agrupamento quando houver uma lógica para dividir os dados em grupos com base em uma característica específica.
    - Exemplos:
        - Analisar picos de vendas em uma loja agrupando os dados por hora do dia.
        - Calcular o tamanho médio da compra agrupando por ID do cliente.
2. **Etapas do Agrupamento (Dividir, Aplicar, Combinar)**
    
    - **Dividir**: Divida os dados em grupos usando uma coluna específica (por exemplo, ano de descoberta, ID de loja).
    - **Aplicar**: Aplique métodos para calcular valores de interesse em cada grupo. Exemplos incluem `count()` para o número de itens ou `sum()` para a soma dos valores.
    - **Combinar**: Armazene os resultados em uma nova estrutura de dados, como um DataFrame.
3. **Método `groupby()` no Pandas**
    
    - `groupby()` é utilizado para dividir um DataFrame em grupos baseados em uma coluna especificada.
    - Ao usar o `groupby()`, você obtém um objeto `DataFrameGroupBy`, que permite aplicar métodos a cada grupo.
    
    ```python
    import pandas as pd
    exoplanet = pd.read_csv('/datasets/exoplanets.csv')
    grouped_data = exoplanet.groupby('discovered')
    ```
    
    - A linha acima cria o objeto `grouped_data` agrupado pela coluna `'discovered'`.
4. **Aplicação de Métodos em Dados Agrupados**
    
    - **Contar Elementos em Cada Grupo**: O método `count()` é usado para contar o número de elementos em cada grupo.
        
        ```python
        print(exoplanet.groupby('discovered').count())
        ```
        
        - Aqui, obtemos o número de planetas descobertos por ano.
    - **Selecionar uma Coluna Específica e Contar**: Caso precise apenas da contagem de uma coluna específica, use o nome da coluna depois de `groupby()`.
        
        ```python
        exo_number = exoplanet.groupby('discovered')['radius'].count()
        print(exo_number)
        ```
        
        - A saída mostra quantos planetas com raio conhecido foram descobertos em cada ano.
    - **Calcular Soma e Média**
        
        - Use `sum()` para obter a soma dos valores de uma coluna para cada grupo:
            
            ```python
            exo_radius_sum = exoplanet.groupby('discovered')['radius'].sum()
            print(exo_radius_sum)
            
            ```
            
        - Para obter a média dos raios dos planetas descobertos em cada ano, divida a soma pelo número de planetas:
            
            ```python
            exo_radius_mean = exo_radius_sum / exo_number
            print(exo_radius_mean)
            ```
            
            - Dessa forma, você pode verificar a média do raio dos exoplanetas descobertos ao longo dos anos.
5. **Exemplos Práticos**
    
    - **Exemplo: Análise de Descoberta de Exoplanetas**
        - Para verificar como a descoberta de novos exoplanetas evoluiu, agrupe os dados pela coluna `'discovered'` e conte o número de planetas por ano. Isso mostra a tendência de crescimento no número de descobertas.
    - **Exemplo: Analisar Raio Médio ao Longo do Tempo**
        - Primeiro, calcule a soma dos raios dos exoplanetas por ano e, em seguida, divida pelo número de planetas para encontrar a média. Essa análise ajuda a entender se planetas menores estão sendo descobertos à medida que a tecnologia melhora.

### **Pontos Importantes**

- O **método `groupby()`** é muito poderoso para agregar e analisar dados, especialmente quando se deseja observar padrões em grupos.
- Os **métodos `count()`, `sum()`, e outras funções estatísticas** (como `mean()`, `median()`) são aplicados para gerar resumos dos grupos.
- Ao aplicar métodos como `groupby('coluna')['outra_coluna']`, você restringe os cálculos a uma coluna específica, o que pode ser útil em muitas situações.



# References







O comando `LIMIT` é usado em consultas SQL para limitar o número de linhas retornadas de uma tabela. Pode ser útil para trabalhar com um subconjunto de dados ou para paginação de resultados. Em MySQL, o `LIMIT` pode ser combinado com a cláusula `ORDER BY` para controlar a ordem e o número de linhas retornadas.

Vamos explicar as consultas fornecidas com detalhes sobre o uso do `LIMIT`:

## Selecionar linhas usando `LIMIT`

1. **Selecionar uma única linha**:
   
    ```sql
    -- Selecionar a primeira linha da tabela 'customers'
    SELECT * FROM customers
    LIMIT 1;
    ```

    Esta consulta retornará apenas a primeira linha da tabela `customers`.

2. **Selecionar duas linhas**:
   
    ```sql
    -- Selecionar as primeiras duas linhas da tabela 'customers'
    SELECT * FROM customers
    LIMIT 2;
    ```

    Esta consulta retornará apenas as primeiras duas linhas da tabela `customers`.

3. **Selecionar três linhas**:
   
    ```sql
    -- Selecionar as primeiras três linhas da tabela 'customers'
    SELECT * FROM customers
    LIMIT 3;
    ```

    Esta consulta retornará apenas as primeiras três linhas da tabela `customers`.

## Usar `LIMIT` com `ORDER BY`

Você pode combinar `LIMIT` com `ORDER BY` para controlar a ordem das linhas retornadas antes de aplicar a limitação.

1. **Ordenar por `last_name` em ordem decrescente e limitar a 3 linhas**:
    
    ```sql
    -- Ordenar por 'last_name' em ordem decrescente e limitar a 3 linhas
    SELECT * FROM customers
    ORDER BY last_name DESC
    LIMIT 3;
    ```

    Esta consulta retornará as três linhas da tabela `customers` com os sobrenomes (`last_name`) em ordem decrescente.

2. **Ordenar por `last_name` em ordem crescente e limitar a 3 linhas**:
    
    ```sql
    -- Ordenar por 'last_name' em ordem crescente e limitar a 3 linhas
    SELECT * FROM customers
    ORDER BY last_name ASC
    LIMIT 3;
    ```

    Esta consulta retornará as três linhas da tabela `customers` com os sobrenomes (`last_name`) em ordem crescente.

## Usar `LIMIT` com deslocamento

Você pode usar o `LIMIT` com um deslocamento para ignorar um número específico de linhas antes de retornar o número desejado de linhas.

1. **Limitar a 3 linhas após pular a primeira**:
   
    ```sql
    -- Pular a primeira linha e selecionar as próximas 3 linhas
    SELECT * FROM customers
    LIMIT 1, 3;
    ```

    Nesta consulta, o comando `LIMIT 1, 3` indica para pular a primeira linha e retornar as próximas três linhas da tabela `customers`.

Esses exemplos ilustram como usar `LIMIT` para controlar a quantidade de linhas retornadas em consultas SQL no MySQL. Você pode ajustar o número de linhas e o deslocamento conforme necessário para trabalhar com subconjuntos específicos de dados.


As funções SQL são usadas para realizar operações em dados de uma tabela ou para manipular strings e outras formas de dados. As funções mais comuns incluem funções de agregação para cálculos em um conjunto de linhas e funções de manipulação de strings para trabalhar com strings. Vamos examinar as funções fornecidas em detalhes.

## Funções de Agregação

As funções de agregação são usadas para realizar cálculos em um conjunto de linhas e retornar um único valor. Elas são úteis para obter estatísticas sobre dados em uma tabela.

### `COUNT`

A função `COUNT` é usada para contar o número de linhas ou valores não nulos em uma coluna. Neste exemplo, a função `COUNT` conta o número de transações na tabela `transactions`:

```sql
-- Contar o número de transações
SELECT COUNT(amount) AS count
FROM transactions;
```

### `MAX`

A função `MAX` retorna o valor máximo de uma coluna. Neste exemplo, a função `MAX` retorna o valor máximo da coluna `amount` na tabela `transactions`:

```sql
-- Obter o valor máximo da coluna 'amount'
SELECT MAX(amount) AS maximum
FROM transactions;
```

### `MIN`

A função `MIN` retorna o valor mínimo de uma coluna. Neste exemplo, a função `MIN` retorna o valor mínimo da coluna `amount` na tabela `transactions`:

```sql
-- Obter o valor mínimo da coluna 'amount'
SELECT MIN(amount) AS minimum
FROM transactions;
```

### `AVG`

A função `AVG` calcula a média de uma coluna numérica. Neste exemplo, a função `AVG` retorna a média dos valores da coluna `amount` na tabela `transactions`:

```sql
-- Calcular a média dos valores da coluna 'amount'
SELECT AVG(amount) AS average
FROM transactions;
```

### `SUM`

A função `SUM` calcula a soma de uma coluna numérica. Neste exemplo, a função `SUM` retorna a soma dos valores da coluna `amount` na tabela `transactions`:

```sql
-- Calcular a soma dos valores da coluna 'amount'
SELECT SUM(amount) AS sum
FROM transactions;
```

## Função de Manipulação de Strings

As funções de manipulação de strings são usadas para modificar ou combinar strings em consultas SQL.

### `CONCAT`

A função `CONCAT` é usada para concatenar (combinar) strings. Neste exemplo, a função `CONCAT` combina as colunas `first_name` e `last_name` da tabela `employees` para criar uma nova coluna chamada `full_name`:

```sql
-- Combinar 'first_name' e 'last_name' para criar 'full_name'
SELECT CONCAT(first_name, ' ', last_name) AS full_name
FROM employees;
```

Essas funções SQL são ferramentas poderosas para trabalhar com dados em um banco de dados, permitindo que você calcule estatísticas, realize manipulações de strings e extraia informações valiosas das tabelas.

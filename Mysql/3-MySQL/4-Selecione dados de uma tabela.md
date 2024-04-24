Vamos revisar os exemplos de consultas SQL fornecidos para selecionar dados de uma tabela `employees`. Vou explicar cada exemplo de consulta.

## Selecionar todos os dados de uma tabela

A consulta abaixo seleciona todas as colunas de todas as linhas da tabela `employees`:

```sql
SELECT * FROM employees;
```

## Selecionar colunas específicas

As consultas abaixo selecionam apenas as colunas `first_name` e `last_name` da tabela `employees`:

```sql
SELECT first_name, last_name FROM employees;
```

Você também pode inverter a ordem das colunas selecionadas:

```sql
SELECT last_name, first_name FROM employees;
```

## Selecionar com critérios

As consultas a seguir selecionam dados da tabela `employees` com base em critérios específicos.

- Selecionar onde `employee_id` é igual a 1:

    ```sql
    SELECT *
    FROM employees
    WHERE employee_id = 1;
    ```

- Selecionar onde `first_name` é igual a "Spongebob":

    ```sql
    SELECT *
    FROM employees
    WHERE first_name = "Spongebob";
    ```

- Selecionar onde `hourly_pay` é maior ou igual a 15:

    ```sql
    SELECT *
    FROM employees
    WHERE hourly_pay >= 15;
    ```

- Selecionar as colunas `hire_date` e `first_name` onde `hire_date` é menor ou igual a "2023-01-03":

    ```sql
    SELECT hire_date, first_name
    FROM employees
    WHERE hire_date <= "2023-01-03";
    ```

- Selecionar onde `employee_id` é diferente de 1:

    ```sql
    SELECT *
    FROM employees
    WHERE employee_id != 1;
    ```

- Selecionar onde `hire_date` é `NULL`:

    ```sql
    SELECT *
    FROM employees
    WHERE hire_date IS NULL;
    ```

- Selecionar onde `hire_date` não é `NULL`:

    ```sql
    SELECT *
    FROM employees
    WHERE hire_date IS NOT NULL;
    ```

Desculpe pela omissão. Vou explicar o conceito de consultas SQL que retornam múltiplos resultados de uma tabela, ou seja, consultas que usam critérios para selecionar mais de uma linha da tabela `employees`.

## Selecionar múltiplos resultados com critérios

As consultas a seguir demonstram como selecionar múltiplos resultados de uma tabela com base em critérios específicos.

- **Selecionar onde `hourly_pay` é maior ou igual a 15**:

    Esta consulta seleciona todos os funcionários da tabela `employees` com uma taxa horária (`hourly_pay`) maior ou igual a 15.

    ```sql
    SELECT *
    FROM employees
    WHERE hourly_pay >= 15;
    ```

- **Selecionar onde `hire_date` é menor ou igual a "2023-01-03"**:

    Esta consulta seleciona as colunas `hire_date` e `first_name` de todos os funcionários da tabela `employees` com uma data de contratação (`hire_date`) menor ou igual a "2023-01-03".

    ```sql
    SELECT hire_date, first_name
    FROM employees
    WHERE hire_date <= "2023-01-03";
    ```

- **Selecionar onde `employee_id` é diferente de 1**:

    Esta consulta seleciona todos os funcionários da tabela `employees` com um `employee_id` diferente de 1.

    ```sql
    SELECT *
    FROM employees
    WHERE employee_id != 1;
    ```

- **Selecionar onde `hire_date` é `NULL`**:

    Esta consulta seleciona todos os funcionários da tabela `employees` com uma data de contratação (`hire_date`) igual a `NULL`.

    ```sql
    SELECT *
    FROM employees
    WHERE hire_date IS NULL;
    ```

- **Selecionar onde `hire_date` não é `NULL`**:

    Esta consulta seleciona todos os funcionários da tabela `employees` com uma data de contratação (`hire_date`) diferente de `NULL`.

    ```sql
    SELECT *
    FROM employees
    WHERE hire_date IS NOT NULL;
    ```

Essas consultas mostram como usar critérios para selecionar múltiplos resultados de uma tabela. Os critérios podem ser baseados em valores de colunas específicos, condições de comparação ou valores nulos e não nulos.


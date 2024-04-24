## Exemplo 1

No exemplo 1, uma única linha é inserida na tabela `employees`. Todos os valores de uma única linha são fornecidos na ordem em que as colunas estão definidas na tabela.

```sql
-- Inserir uma linha na tabela 'employees'
INSERT INTO employees
VALUES (1, "Eugene", "Krabs", 25.50, "2023-01-02");

-- Exibir todas as linhas da tabela 'employees'
SELECT * FROM employees;
```

Aqui, os valores representam, respectivamente: `employee_id`, `first_name`, `last_name`, `salary`, e `hire_date`.

## Exemplo 2

No exemplo 2, múltiplas linhas são inseridas em uma única instrução `INSERT INTO`. Isso permite inserir várias linhas de uma vez, separando cada linha com uma vírgula.

```sql
-- Inserir várias linhas na tabela 'employees'
INSERT INTO employees
VALUES (2, "Squidward", "Tentacles", 15.00, "2023-01-03"),
       (3, "Spongebob", "Squarepants", 12.50, "2023-01-04"),
       (4, "Patrick", "Star", 12.50, "2023-01-05"),
       (5, "Sandy", "Cheeks", 17.25, "2023-01-06");

-- Exibir todas as linhas da tabela 'employees'
SELECT * FROM employees;
```

Os valores inseridos representam, respectivamente: `employee_id`, `first_name`, `last_name`, `salary`, e `hire_date` de cada funcionário.

## Exemplo 3

No exemplo 3, uma linha é inserida na tabela `employees`, mas apenas para colunas específicas (`employee_id`, `first_name`, `last_name`). Os valores são inseridos apenas nas colunas especificadas na cláusula `INSERT INTO`.

```sql
-- Inserir uma linha nas colunas específicas 'employee_id', 'first_name', e 'last_name'
INSERT INTO employees (employee_id, first_name, last_name)
VALUES (6, "Sheldon", "Plankton");

-- Exibir todas as linhas da tabela 'employees'
SELECT * FROM employees;
```

Como algumas colunas não foram especificadas na instrução `INSERT INTO` (por exemplo, `salary` e `hire_date`), elas assumirão valores padrão definidos na tabela ou valores nulos, dependendo da configuração.

Esses exemplos demonstram como inserir dados em uma tabela MySQL usando o comando `INSERT INTO`.

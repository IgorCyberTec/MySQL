Vou explicar cada um dos comandos listados com código e uma breve descrição de suas funções no MySQL.

## UPDATE

O comando `UPDATE` é utilizado para modificar valores em linhas existentes de uma tabela no MySQL. Você pode especificar quais colunas deseja atualizar e os novos valores, além de condições para limitar quais linhas serão afetadas. Aqui está um exemplo para atualizar o salário (`salary`) de um funcionário específico (`employee_id = 1`):

```sql
-- Atualizar o salário do funcionário com employee_id = 1
UPDATE employees
SET salary = 30.00
WHERE employee_id = 1;
```

## UPDATE múltiplos campos

Você pode atualizar múltiplos campos de uma tabela ao mesmo tempo usando o comando `UPDATE`. Aqui está um exemplo para atualizar o salário (`salary`) e a data de contratação (`hire_date`) de um funcionário específico (`employee_id = 2`):

```sql
-- Atualizar o salário e a data de contratação do funcionário com employee_id = 2
UPDATE employees
SET salary = 20.00, hire_date = "2023-01-15"
WHERE employee_id = 2;
```

## UPDATE um campo para NULL

Você pode atualizar um campo para o valor `NULL` usando o comando `UPDATE`. Por exemplo, para definir a data de contratação (`hire_date`) de um funcionário específico (`employee_id = 3`) como `NULL`:

```sql
-- Definir a data de contratação de um funcionário como NULL
UPDATE employees
SET hire_date = NULL
WHERE employee_id = 3;
```

## UPDATE uma linha inteira

Você pode atualizar uma linha inteira de uma tabela especificando valores para todas as colunas que deseja alterar. Por exemplo, para atualizar os dados de um funcionário específico (`employee_id = 4`):

```sql
-- Atualizar a linha inteira de um funcionário com employee_id = 4
UPDATE employees
SET first_name = "Carlos",
    last_name = "Silva",
    salary = 18.50,
    hire_date = "2023-02-01"
WHERE employee_id = 4;
```

## DELETE uma linha

O comando `DELETE` é utilizado para remover linhas de uma tabela com base em condições especificadas. Por exemplo, para deletar uma linha específica de um funcionário (`employee_id = 5`):

```sql
-- Deletar uma linha com employee_id = 5
DELETE FROM employees
WHERE employee_id = 5;
```

A operação `DELETE` é irreversível, por isso deve ser usada com cautela para evitar a exclusão acidental de dados importantes.
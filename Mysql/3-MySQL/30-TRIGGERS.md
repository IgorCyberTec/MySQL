Os comandos fornecidos demonstram como criar *triggers* em MySQL. Uma *trigger* é um tipo especial de procedimento armazenado que é executado automaticamente em resposta a eventos específicos em uma tabela, como inserção (`INSERT`), atualização (`UPDATE`) ou exclusão (`DELETE`) de dados. Existem dois tipos de *triggers* baseados no momento em que eles são acionados: `BEFORE` (antes de um evento) e `AFTER` (após um evento).

Vou explicar cada um dos exemplos de *triggers* em detalhes:

## `BEFORE UPDATE` em `employees`

```sql
CREATE TRIGGER before_hourly_pay_update
BEFORE UPDATE ON employees 
FOR EACH ROW
SET NEW.salary = (NEW.hourly_pay * 2080);
```

### Explicação:

- **Evento**: A *trigger* é acionada `BEFORE UPDATE` em `employees`, ou seja, antes de uma operação de atualização na tabela `employees`.
- **Ação**: A *trigger* atualiza o valor de `NEW.salary` (o novo valor da coluna `salary` a ser atualizado) multiplicando `NEW.hourly_pay` por 2080.

## `BEFORE INSERT` em `employees`

```sql
CREATE TRIGGER before_hourly_pay_insert
BEFORE INSERT ON employees 
FOR EACH ROW
SET NEW.salary = (NEW.hourly_pay * 2080);
```

### Explicação:

- **Evento**: A *trigger* é acionada `BEFORE INSERT` em `employees`, ou seja, antes de uma operação de inserção na tabela `employees`.
- **Ação**: A *trigger* define o valor de `NEW.salary` (o novo valor da coluna `salary` a ser inserido) multiplicando `NEW.hourly_pay` por 2080.

## `AFTER DELETE` em `employees`

```sql
CREATE TRIGGER after_salary_delete
AFTER DELETE ON employees 
FOR EACH ROW
UPDATE expenses
SET expense_total = expense_total - OLD.salary
WHERE expense_name = "salaries";
```

### Explicação:

- **Evento**: A *trigger* é acionada `AFTER DELETE` em `employees`, ou seja, após uma operação de exclusão na tabela `employees`.
- **Ação**: A *trigger* atualiza a tabela `expenses` reduzindo `expense_total` pelo valor de `OLD.salary` (o valor da coluna `salary` antes da exclusão), onde `expense_name` é `"salaries"`.

## `AFTER INSERT` em `employees`

```sql
CREATE TRIGGER after_salary_insert
AFTER INSERT ON employees 
FOR EACH ROW
UPDATE expenses
SET expense_total = expense_total + NEW.salary
WHERE expense_name = "salaries";
```

### Explicação:

- **Evento**: A *trigger* é acionada `AFTER INSERT` em `employees`, ou seja, após uma operação de inserção na tabela `employees`.
- **Ação**: A *trigger* atualiza a tabela `expenses` aumentando `expense_total` pelo valor de `NEW.salary` (o novo valor da coluna `salary` inserido), onde `expense_name` é `"salaries"`.

## `AFTER UPDATE` em `employees`

```sql
CREATE TRIGGER after_salary_update
AFTER UPDATE ON employees 
FOR EACH ROW
UPDATE expenses
SET expense_total = expense_total + (NEW.salary - OLD.salary)
WHERE expense_name = "salaries";
```

### Explicação:

- **Evento**: A *trigger* é acionada `AFTER UPDATE` em `employees`, ou seja, após uma operação de atualização na tabela `employees`.
- **Ação**: A *trigger* atualiza a tabela `expenses` ajustando `expense_total` pela diferença entre `NEW.salary` (o novo valor de `salary`) e `OLD.salary` (o valor anterior de `salary`), onde `expense_name` é `"salaries"`.

Os exemplos mostram como as *triggers* podem ser usadas para automatizar operações adicionais em resposta a eventos específicos em uma tabela. Elas são úteis para garantir consistência de dados, manter relacionamentos entre tabelas e realizar cálculos ou ajustes automáticos nas operações de banco de dados.
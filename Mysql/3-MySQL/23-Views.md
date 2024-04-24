As instruções fornecidas criam *views* em MySQL. Uma *view* (ou *visão*) é uma consulta armazenada no banco de dados que pode ser tratada como uma tabela. Ela é criada usando a cláusula `CREATE VIEW` e representa uma consulta específica que pode ser reutilizada posteriormente. Uma *view* não armazena dados, mas fornece uma visão dos dados com base em uma consulta.

Vamos analisar cada instrução e explicar o conceito de *view*:

## `CREATE VIEW` para `employee_attendance`

```sql
-- Criar a view 'employee_attendance' com os nomes dos funcionários
CREATE VIEW employee_attendance AS 
SELECT first_name, last_name
FROM employees;
```

### Explicação:

- **Nome da view**: A view é nomeada como `employee_attendance`.
- **Consulta**: A view é criada com base na consulta que seleciona as colunas `first_name` e `last_name` da tabela `employees`.
- **Resultado**: A view `employee_attendance` fornece uma visão dos dados dos funcionários com seus primeiros e sobrenomes.

## `CREATE VIEW` para `customer_emails`

```sql
-- Criar a view 'customer_emails' com os e-mails dos clientes
CREATE VIEW customer_emails AS 
SELECT email
FROM customers;
```

### Explicação:

- **Nome da view**: A view é nomeada como `customer_emails`.
- **Consulta**: A view é criada com base na consulta que seleciona a coluna `email` da tabela `customers`.
- **Resultado**: A view `customer_emails` fornece uma visão dos dados dos clientes com seus endereços de e-mail.

## Uso de *views*

Após criar uma *view*, você pode consultá-la como se fosse uma tabela:

```sql
-- Consultar a view 'employee_attendance'
SELECT * FROM employee_attendance;

-- Consultar a view 'customer_emails'
SELECT * FROM customer_emails;
```

As *views* podem ser úteis para simplificar consultas complexas, fornecer acesso restrito a dados específicos ou criar uma camada de abstração entre os usuários e as tabelas do banco de dados. Além disso, elas podem ser usadas para consolidar consultas frequentes e melhorar a organização e a clareza do código SQL.

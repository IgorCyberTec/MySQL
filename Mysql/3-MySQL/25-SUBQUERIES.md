Os exemplos fornecidos demonstram o uso de subconsultas (também conhecidas como consultas aninhadas ou consultas embutidas) em MySQL. Uma subconsulta é uma consulta que é usada dentro de outra consulta. As subconsultas podem ser usadas para calcular valores, comparar dados ou limitar resultados em uma consulta principal.

Vamos explicar cada um dos exemplos em detalhes:

## Subconsulta para calcular a média salarial (`avg_pay`)

```sql
-- Selecionar nome, sobrenome, taxa horária e média salarial
SELECT first_name, last_name, hourly_pay,
       (SELECT AVG(hourly_pay) FROM employees) AS avg_pay
FROM employees;
```

### Explicação:

- **Consulta principal**: A consulta principal seleciona as colunas `first_name`, `last_name` e `hourly_pay` da tabela `employees`.
- **Subconsulta**: A subconsulta `(SELECT AVG(hourly_pay) FROM employees)` calcula a média salarial (`AVG`) da coluna `hourly_pay` em toda a tabela `employees`.
- **Alias `avg_pay`**: O resultado da subconsulta é rotulado como `avg_pay` e é exibido como uma coluna adicional na consulta principal.

Esta consulta retorna uma lista de funcionários com seus primeiros nomes, sobrenomes, taxas horárias (`hourly_pay`) e a média salarial (`avg_pay`) de todos os funcionários na tabela `employees`.

## Subconsulta com `IN` para encontrar clientes com transações

```sql
-- Selecionar nome e sobrenome de clientes com transações
SELECT first_name, last_name
FROM customers
WHERE customer_id IN (SELECT DISTINCT customer_id
                      FROM transactions
                      WHERE customer_id IS NOT NULL);
```

### Explicação:

- **Consulta principal**: A consulta principal seleciona as colunas `first_name` e `last_name` da tabela `customers`.
- **Condição `IN`**: A condição `IN` é usada para verificar se `customer_id` em `customers` está presente na subconsulta.
- **Subconsulta**: A subconsulta `(SELECT DISTINCT customer_id FROM transactions WHERE customer_id IS NOT NULL)` seleciona valores distintos de `customer_id` da tabela `transactions` onde `customer_id` não é nulo.
- **Resultado**: A consulta principal retorna apenas os clientes (`customers`) cujos `customer_id` estão presentes nas transações (`transactions`).

Esta consulta retorna uma lista de clientes (`customers`) com seus primeiros nomes e sobrenomes que têm transações registradas na tabela `transactions`.

As subconsultas são uma maneira eficaz de adicionar lógica adicional ou cálculos a consultas SQL, permitindo realizar operações complexas com dados de diferentes tabelas em uma única instrução.
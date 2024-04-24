A cláusula `ROLLUP` é uma extensão da cláusula `GROUP BY` em MySQL que produz linhas de totalização (chamadas de "super-aggregate") para grupos hierárquicos de dados. Ela calcula totais intermediários e um total geral (grand total) além dos totais agrupados normais, proporcionando uma visão adicional sobre os dados.

Vamos analisar cada uma das consultas e explicar como a cláusula `ROLLUP` funciona.

## Usar `ROLLUP` para calcular vendas diárias com total geral

```sql
-- Calcular vendas diárias e total geral
SELECT SUM(amount) AS "daily_sales", order_date
FROM transactions
GROUP BY order_date WITH ROLLUP;
```

### Explicação:

- **Consulta principal**: A consulta principal agrupa os dados de `transactions` por `order_date` e calcula a soma (`SUM`) da coluna `amount` para cada grupo.
- **`ROLLUP`**: A cláusula `WITH ROLLUP` produz uma linha de totalização adicional com a soma total de todas as vendas em todas as datas (`order_date`).
- **Resultado**: O resultado mostra a soma das vendas diárias para cada data (`order_date`) e uma linha adicional no final com a soma total de todas as vendas.

## Usar `ROLLUP` para contar pedidos diários com total geral

```sql
-- Contar pedidos diários e total geral
SELECT COUNT(transaction_id) AS "# of orders", order_date
FROM transactions
GROUP BY order_date WITH ROLLUP;
```

### Explicação:

- **Consulta principal**: A consulta principal agrupa os dados de `transactions` por `order_date` e conta (`COUNT`) o número de transações (`transaction_id`) para cada grupo.
- **`ROLLUP`**: A cláusula `WITH ROLLUP` produz uma linha de totalização adicional com a contagem total de pedidos em todas as datas (`order_date`).
- **Resultado**: O resultado mostra a contagem de pedidos diários para cada data (`order_date`) e uma linha adicional no final com a contagem total de todos os pedidos.

## Usar `ROLLUP` para contar pedidos por cliente com total geral

```sql
-- Contar pedidos por cliente e total geral
SELECT COUNT(transaction_id) AS "# of orders", customer_id
FROM transactions
GROUP BY customer_id WITH ROLLUP;
```

### Explicação:

- **Consulta principal**: A consulta principal agrupa os dados de `transactions` por `customer_id` e conta (`COUNT`) o número de transações (`transaction_id`) para cada grupo.
- **`ROLLUP`**: A cláusula `WITH ROLLUP` produz uma linha de totalização adicional com a contagem total de pedidos de todos os clientes (`customer_id`).
- **Resultado**: O resultado mostra a contagem de pedidos por cliente (`customer_id`) e uma linha adicional no final com a contagem total de todos os pedidos.

## Usar `ROLLUP` para calcular a soma dos salários por funcionário com total geral

```sql
-- Calcular a soma dos salários por funcionário e total geral
SELECT SUM(hourly_pay) AS "hourly_pay", employee_id
FROM employees
GROUP BY employee_id WITH ROLLUP;
```

### Explicação:

- **Consulta principal**: A consulta principal agrupa os dados de `employees` por `employee_id` e calcula a soma (`SUM`) da coluna `hourly_pay` para cada grupo.
- **`ROLLUP`**: A cláusula `WITH ROLLUP` produz uma linha de totalização adicional com a soma total de todos os salários de todos os funcionários (`employee_id`).
- **Resultado**: O resultado mostra a soma dos salários por funcionário (`employee_id`) e uma linha adicional no final com a soma total de todos os salários.

A cláusula `ROLLUP` é útil para gerar resumos hierárquicos dos dados, proporcionando uma visão de totaliar dados em vários níveis, desde os totais por grupo até o total geral. Isso facilita a análise de dados agregados em diferentes granularidades.

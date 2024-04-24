Os comandos fornecidos mostram como ordenar os resultados de consultas SQL usando a cláusula `ORDER BY` em MySQL. A cláusula `ORDER BY` é usada para ordenar os resultados de uma consulta com base em uma ou mais colunas especificadas. Você pode escolher a direção da ordenação para cada coluna, seja crescente (`ASC`) ou decrescente (`DESC`).

## Ordenar resultados por `last_name` em ordem crescente

Na primeira consulta, os resultados da tabela `employees` são ordenados pela coluna `last_name` em ordem crescente (`ASC`):

```sql
-- Selecionar todos os dados da tabela 'employees' e ordenar por 'last_name' em ordem crescente
SELECT * FROM employees
ORDER BY last_name ASC;
```

Neste exemplo, todos os dados da tabela `employees` serão retornados e ordenados alfabeticamente pela coluna `last_name` em ordem crescente.

## Ordenar resultados por `amount` em ordem decrescente e `customer_id` em ordem decrescente

Na segunda consulta, os resultados da tabela `transactions` são ordenados pela coluna `amount` em ordem decrescente (`DESC`) e pela coluna `customer_id` em ordem decrescente (`DESC`):

```sql
-- Selecionar todos os dados da tabela 'transactions' e ordenar por 'amount' em ordem decrescente e por 'customer_id' em ordem decrescente
SELECT * FROM transactions
ORDER BY amount DESC, customer_id DESC;
```

Neste exemplo, todos os dados da tabela `transactions` serão retornados e ordenados primeiro pela coluna `amount` em ordem decrescente e, em seguida, pela coluna `customer_id` em ordem decrescente para empatar valores de `amount`.

A cláusula `ORDER BY` é uma ferramenta poderosa para organizar os resultados de consultas de acordo com as necessidades específicas, permitindo ordenar dados com base em uma ou mais colunas em diferentes direções.
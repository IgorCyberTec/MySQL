Os operadores lógicos (`AND`, `OR`, `NOT`) e de comparação (`BETWEEN`, `IN`) são usados em consultas SQL para combinar condições e especificar critérios de seleção. Eles permitem refinar consultas para obter resultados mais precisos. Vamos explicar cada um desses operadores com exemplos.

## `AND`

O operador `AND` é usado para combinar duas ou mais condições. Todas as condições combinadas com `AND` devem ser verdadeiras para que a linha seja retornada na consulta.

Por exemplo, para selecionar transações em que `amount` seja maior que 50 e `transaction_date` seja em 2024:

```sql
-- Selecionar transações em que 'amount' > 50 e 'transaction_date' seja em 2024
SELECT *
FROM transactions
WHERE amount > 50 AND YEAR(transaction_date) = 2024;
```

Neste exemplo, ambas as condições devem ser verdadeiras para que uma linha seja retornada.

## `OR`

O operador `OR` é usado para combinar duas ou mais condições. Uma linha é retornada se pelo menos uma das condições combinadas com `OR` for verdadeira.

Por exemplo, para selecionar transações em que `amount` seja maior que 100 ou `customer_id` seja 2:

```sql
-- Selecionar transações em que 'amount' > 100 ou 'customer_id' seja 2
SELECT *
FROM transactions
WHERE amount > 100 OR customer_id = 2;
```

Neste exemplo, uma linha será retornada se pelo menos uma das condições for verdadeira.

## `NOT`

O operador `NOT` é usado para inverter uma condição. Ele retorna linhas em que a condição não é verdadeira.

Por exemplo, para selecionar transações em que `amount` não seja maior que 50:

```sql
-- Selecionar transações em que 'amount' não seja maior que 50
SELECT *
FROM transactions
WHERE NOT (amount > 50);
```

Neste exemplo, linhas com `amount` menor ou igual a 50 serão retornadas.

## `BETWEEN`

O operador `BETWEEN` é usado para selecionar linhas com valores dentro de um intervalo especificado. Ele é inclusivo, ou seja, inclui os valores nas extremidades do intervalo.

Por exemplo, para selecionar transações com `amount` entre 50 e 100:

```sql
-- Selecionar transações com 'amount' entre 50 e 100
SELECT *
FROM transactions
WHERE amount BETWEEN 50 AND 100;
```

Neste exemplo, transações com `amount` entre 50 e 100 (inclusive) serão retornadas.

## `IN`

O operador `IN` é usado para verificar se um valor está em uma lista de valores específicos. É útil para simplificar consultas que envolvem várias condições `OR`.

Por exemplo, para selecionar transações com `customer_id` igual a 1, 2 ou 3:

```sql
-- Selecionar transações com 'customer_id' igual a 1, 2 ou 3
SELECT *
FROM transactions
WHERE customer_id IN (1, 2, 3);
```

Neste exemplo, transações com `customer_id` igual a 1, 2 ou 3 serão retornadas.

Esses operadores ajudam a criar consultas SQL mais flexíveis e refinadas para buscar dados com base em várias condições.
As instruções fornecidas demonstram como criar procedimentos armazenados (stored procedures) em MySQL. Um procedimento armazenado é um bloco de código SQL armazenado no banco de dados que pode ser chamado para realizar operações específicas. Pode incluir consultas SQL, variáveis, fluxos de controle e argumentos de entrada.

Vou explicar cada exemplo de procedimento armazenado em detalhes:

## Exemplo 1: `get_customers()`

Este procedimento armazenado não tem argumentos de entrada e simplesmente seleciona todos os dados da tabela `customers`.

```sql
DELIMITER $$
CREATE PROCEDURE get_customers()
BEGIN
 SELECT * FROM customers;
END $$
DELIMITER ;

CALL get_customers();

DROP PROCEDURE get_customers;
```

### Explicação:

- **Criação do procedimento**: O procedimento `get_customers()` é criado com a instrução `CREATE PROCEDURE`. Dentro do procedimento, a instrução `BEGIN` marca o início do bloco de código, e `END` marca o fim.
- **Operação realizada**: O procedimento simplesmente seleciona todos os dados da tabela `customers` com uma instrução `SELECT * FROM customers;`.
- **Chamada do procedimento**: Após a criação, o procedimento é chamado com `CALL get_customers();`.
- **Exclusão do procedimento**: Por fim, o procedimento é excluído com `DROP PROCEDURE get_customers;`.

## Exemplo 2: `find_customer(IN id INT)`

Este procedimento armazenado tem um argumento de entrada `IN id INT` que representa um `customer_id` específico. Ele seleciona registros da tabela `customers` onde `customer_id` corresponde ao argumento `id`.

```sql
DELIMITER $$
CREATE PROCEDURE find_customer(IN id INT)  
BEGIN  
 SELECT *
 FROM customers
 WHERE customer_id = id;
END $$
DELIMITER ; 
```

### Explicação:

- **Argumento de entrada**: O procedimento recebe um argumento de entrada `IN id INT`, que é um inteiro representando `customer_id`.
- **Operação realizada**: O procedimento seleciona registros da tabela `customers` onde `customer_id` corresponde ao valor passado pelo argumento `id`.

## Exemplo 3: `find_customer(IN f_name VARCHAR(50), IN l_name VARCHAR(50))`

Este procedimento armazenado tem dois argumentos de entrada: `IN f_name VARCHAR(50)` para `first_name` e `IN l_name VARCHAR(50)` para `last_name`. Ele seleciona registros da tabela `customers` onde `first_name` e `last_name` correspondem aos argumentos de entrada.

```sql
DELIMITER $$
CREATE PROCEDURE find_customer(IN f_name VARCHAR(50),
                               IN l_name VARCHAR(50))  
BEGIN  
 SELECT *
 FROM customers
 WHERE first_name = f_name AND last_name = l_name;
END $$
DELIMITER ; 
```

### Explicação:

- **Argumentos de entrada**: O procedimento recebe dois argumentos de entrada, `IN f_name VARCHAR(50)` para `first_name` e `IN l_name VARCHAR(50)` para `last_name`.
- **Operação realizada**: O procedimento seleciona registros da tabela `customers` onde `first_name` corresponde a `f_name` e `last_name` corresponde a `l_name`.

Os procedimentos armazenados são úteis para encapsular consultas e operações complexas em um bloco de código reutilizável. Eles podem simplificar a execução de operações e melhorar a organização do código SQL. Além disso, eles podem aceitar argumentos de entrada para tornar os procedimentos mais flexíveis e parametrizáveis.
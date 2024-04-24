A **stored procedure** (ou procedimento armazenado) em MySQL é um bloco de código SQL armazenado no banco de dados e que pode ser reutilizado sempre que necessário. Uma stored procedure é similar a uma função em programação, podendo realizar tarefas repetitivas ou complexas, e aceitando parâmetros de entrada para personalizar sua execução.

### Vantagens de stored procedures:

- **Reutilização de código**: Uma stored procedure pode ser chamada várias vezes, eliminando a necessidade de reescrever o mesmo código SQL repetidamente.
- **Parâmetros de entrada**: Você pode passar parâmetros para uma stored procedure, permitindo que ela execute tarefas diferentes com base nos valores fornecidos.
- **Segurança**: As stored procedures podem restringir o acesso aos dados, permitindo que os usuários executem operações sem saber a estrutura do banco de dados.
- **Desempenho**: Como as stored procedures são armazenadas no banco de dados, elas podem ser otimizadas e executadas mais rapidamente do que consultas SQL ad hoc.
- **Manutenção**: Como o código está centralizado no banco de dados, é mais fácil manter e atualizar.

### Sintaxe básica para criar uma stored procedure:

```sql
DELIMITER //

CREATE PROCEDURE nome_da_procedure(param1 tipo, param2 tipo, ...)
BEGIN
    -- Bloco de código SQL
    sql_statement;
END //

DELIMITER ;
```

- **`DELIMITER`**: Define um novo delimitador para a instrução (no exemplo, `//`).
- **`CREATE PROCEDURE`**: Inicia a definição da stored procedure.
- **`nome_da_procedure`**: O nome da stored procedure.
- **`param1 tipo, param2 tipo, ...`**: Parâmetros opcionais para a procedure, com seus respectivos tipos de dados.
- **`BEGIN` e `END`**: Delimitam o bloco de código da stored procedure.
- **`sql_statement`**: O código SQL que a stored procedure executará.
- **`DELIMITER ;`**: Restaura o delimitador padrão.

### Como executar uma stored procedure:

```sql
CALL nome_da_procedure(param1, param2, ...);
```

### Exemplo prático de criação e execução de uma stored procedure:

Vamos criar uma stored procedure que seleciona clientes de uma tabela `clientes` com base em um parâmetro `cidade`:

```sql
DELIMITER //

CREATE PROCEDURE SelectClientesPorCidade(IN cidade_param VARCHAR(30))
BEGIN
    SELECT *
    FROM clientes
    WHERE cidade = cidade_param;
END //

DELIMITER ;
```

- **`IN cidade_param VARCHAR(30)`**: Define um parâmetro de entrada `cidade_param` do tipo `VARCHAR(30)`.
- **`SELECT * FROM clientes WHERE cidade = cidade_param`**: Consulta os clientes com base no valor do parâmetro `cidade_param`.

Após criar a stored procedure, podemos executá-la usando `CALL`:

```sql
CALL SelectClientesPorCidade('São Paulo');
```

- Esta chamada executará a stored procedure com o parâmetro `'São Paulo'`, retornando todos os clientes localizados nessa cidade.

Stored procedures são uma poderosa ferramenta para organizar e otimizar código SQL, fornecendo uma maneira eficiente de realizar operações complexas ou repetitivas em um banco de dados MySQL.
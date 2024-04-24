## Alguns dos Comandos SQL Mais Importantes

- `SELECT`- extrai dados de um banco de dados
- `UPDATE`atualiza dados em um banco de dados
- `DELETE`- exclui dados de um banco de dados
- `INSERT INTO`- insere novos dados em um banco de dados
- `CREATE DATABASE`- cria um novo banco de dados
- `ALTER DATABASE`- modifica um banco de dados
- `CREATE TABLE`- cria uma nova tabela
- `ALTER TABLE`- modifica uma tabela
- `DROP TABLE`- exclui uma tabela
- `CREATE INDEX`- cria um índice (chave de pesquisa)
- `DROP INDEX`- exclui um índice

Os comandos SQL são a base da interação com um banco de dados em MySQL ou em qualquer outro sistema de banco de dados relacional. Eles permitem que você crie, leia, atualize e exclua dados em bancos de dados. Vamos rever e adicionar detalhes a alguns dos comandos mais importantes e úteis.

### Comandos SQL importantes

1. **`SELECT`**:
    - Usado para selecionar e recuperar dados de um banco de dados.
    - Você pode selecionar colunas específicas ou todas (`*`) as colunas de uma tabela.
    - Exemplo:
        ```mysql
        SELECT nome, email FROM clientes;
        ```

    - `SELECT DISTINCT`: Retorna apenas valores distintos em uma coluna ou combinação de colunas.
        ```mysql
        SELECT DISTINCT pais FROM clientes;
        ```

2. **`UPDATE`**:
    - Atualiza registros em uma tabela com base em uma condição especificada.
    - Exemplo:
        ```mysql
        UPDATE clientes
        SET email = 'novo_email@example.com'
        WHERE id = 1;
        ```

3. **`DELETE`**:
    - Exclui registros de uma tabela com base em uma condição especificada.
    - Exemplo:
        ```mysql
        DELETE FROM clientes
        WHERE id = 2;
        ```

4. **`INSERT INTO`**:
    - Insere novos registros em uma tabela.
    - Exemplo:
        ```mysql
        INSERT INTO clientes (nome, email, idade)
        VALUES ('João', 'joao@example.com', 25);
        ```

5. **`CREATE DATABASE`**:
    - Cria um novo banco de dados.
    - Exemplo:
        ```mysql
        CREATE DATABASE meus_dados;
        ```

6. **`ALTER DATABASE`**:
    - Modifica um banco de dados existente (por exemplo, alterando a codificação padrão).
    - Exemplo:
        ```mysql
        ALTER DATABASE meus_dados
        CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
        ```

7. **`CREATE TABLE`**:
    - Cria uma nova tabela em um banco de dados.
    - Exemplo:
        ```mysql
        CREATE TABLE clientes (
            id INT AUTO_INCREMENT PRIMARY KEY,
            nome VARCHAR(100),
            email VARCHAR(100),
            idade INT
        );
        ```

8. **`ALTER TABLE`**:
    - Modifica uma tabela existente, adicionando ou removendo colunas, ou modificando outras propriedades da tabela.
    - Exemplo:
        ```mysql
        ALTER TABLE clientes ADD COLUMN telefone VARCHAR(20);
        ```

9. **`DROP TABLE`**:
    - Exclui uma tabela, incluindo todos os seus dados e estrutura.
    - Exemplo:
        ```mysql
        DROP TABLE clientes;
        ```

10. **`CREATE INDEX`**:
    - Cria um índice em uma ou mais colunas de uma tabela para acelerar consultas.
    - Exemplo:
        ```mysql
        CREATE INDEX idx_nome ON clientes (nome);
        ```

11. **`DROP INDEX`**:
    - Exclui um índice de uma tabela.
    - Exemplo:
        ```mysql
        DROP INDEX idx_nome ON clientes;
        ```

12. **`JOIN`**:
    - Combina linhas de duas ou mais tabelas com base em uma condição de relacionamento entre as tabelas.
    - Exemplo de `INNER JOIN`:
        ```mysql
        SELECT clientes.nome, pedidos.id
        FROM clientes
        INNER JOIN pedidos ON clientes.id = pedidos.cliente_id;
        ```

13. **`GROUP BY`**:
    - Agrupa resultados com base em uma ou mais colunas e pode ser usado com funções de agregação.
    - Exemplo:
        ```mysql
        SELECT pais, COUNT(*) AS total
        FROM clientes
        GROUP BY pais;
        ```

14. **`HAVING`**:
    - Filtra grupos de dados após o agrupamento, com base em condições específicas.
    - Exemplo:
        ```mysql
        SELECT pais, COUNT(*) AS total
        FROM clientes
        GROUP BY pais
        HAVING total > 10;
        ```

15. **`FOREIGN KEY`**:
    - Define uma chave estrangeira que estabelece um relacionamento entre duas tabelas.
    - Exemplo:
        ```mysql
        CREATE TABLE pedidos (
            id INT AUTO_INCREMENT PRIMARY KEY,
            cliente_id INT,
            data_pedido DATE,
            total DECIMAL(10,2),
            FOREIGN KEY (cliente_id) REFERENCES clientes(id)
                ON DELETE CASCADE
                ON UPDATE CASCADE
        );
        ```

Esses comandos são fundamentais para trabalhar com MySQL e bancos de dados relacionais em geral. Eles permitem criar, modificar e gerenciar dados de forma eficiente e segura.
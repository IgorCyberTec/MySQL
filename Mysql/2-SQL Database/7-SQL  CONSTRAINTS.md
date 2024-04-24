Em SQL, as restrições (ou *constraints*) são usadas para especificar regras para os dados em uma tabela. Elas ajudam a garantir a precisão, integridade e confiabilidade dos dados em uma tabela.

### Tipos de restrições em SQL:

1. **`NOT NULL`**:
    - Garante que uma coluna não pode ter valores `NULL`.
    - Exemplo: Para garantir que a coluna `nome` nunca seja `NULL`:
        ```sql
        CREATE TABLE Pessoas (
            id INT PRIMARY KEY,
            nome VARCHAR(100) NOT NULL
        );
        ```

2. **`UNIQUE`**:
    - Garante que todos os valores em uma coluna sejam únicos.
    - Exemplo: Para garantir que a coluna `email` tenha valores únicos:
        ```sql
        CREATE TABLE Clientes (
            id INT PRIMARY KEY,
            email VARCHAR(255) UNIQUE
        );
        ```

3. **`PRIMARY KEY`**:
    - Uma combinação de `NOT NULL` e `UNIQUE` que identifica de forma exclusiva cada linha em uma tabela.
    - Exemplo: Definir a coluna `id` como chave primária:
        ```sql
        CREATE TABLE Pedidos (
            id INT PRIMARY KEY,
            data DATE,
            cliente_id INT
        );
        ```

4. **`FOREIGN KEY`**:
    - Impede ações que destruam vínculos entre tabelas relacionadas.
    - Exemplo: Para definir `cliente_id` em `Pedidos` como uma chave estrangeira referenciando `Clientes`:
        ```sql
        CREATE TABLE Pedidos (
            id INT PRIMARY KEY,
            data DATE,
            cliente_id INT,
            FOREIGN KEY (cliente_id) REFERENCES Clientes(id)
        );
        ```

5. **`CHECK`**:
    - Garante que os valores em uma coluna satisfaçam uma condição específica.
    - Exemplo: Para garantir que os valores em `idade` estejam entre 18 e 65:
        ```sql
        CREATE TABLE Funcionarios (
            id INT PRIMARY KEY,
            nome VARCHAR(100),
            idade INT CHECK (idade >= 18 AND idade <= 65)
        );
        ```

6. **`DEFAULT`**:
    - Define um valor padrão para uma coluna se nenhum valor for especificado.
    - Exemplo: Definir um valor padrão de `'N/A'` para a coluna `endereco`:
        ```sql
        CREATE TABLE Clientes (
            id INT PRIMARY KEY,
            nome VARCHAR(100),
            endereco VARCHAR(255) DEFAULT 'N/A'
        );
        ```

7. **`CREATE INDEX`**:
    - Cria índices para melhorar o desempenho ao buscar dados no banco de dados.
    - Exemplo: Para criar um índice na coluna `nome` da tabela `Clientes`:
        ```sql
        CREATE INDEX idx_nome ON Clientes (nome);
        ```

### Aplicação de restrições:

- **Durante a criação da tabela**: Restrições podem ser definidas durante a criação da tabela com a instrução `CREATE TABLE`.
- **Após a criação da tabela**: Restrições podem ser adicionadas, modificadas ou removidas posteriormente com a instrução `ALTER TABLE`.

### Considerações finais:

- Restrições são fundamentais para garantir a integridade dos dados e prevenir problemas de consistência no banco de dados.
- Use restrições para estabelecer relações e vínculos entre tabelas e garantir que os dados sejam precisos e confiáveis.
- Ao planejar suas tabelas, considere as restrições necessárias para manter a integridade e consistência dos dados.
A restrição `DEFAULT` em SQL é usada para definir um valor padrão para uma coluna em uma tabela. Quando um novo registro é inserido sem especificar um valor para essa coluna, o valor padrão será usado automaticamente.

### `DEFAULT` em `CREATE TABLE`:

Você pode definir um valor padrão para uma coluna ao criar uma tabela com a instrução `CREATE TABLE`.

- **Sintaxe**:
    ```sql
    CREATE TABLE nome_da_tabela (
        coluna1 tipo_de_dado NOT NULL,
        coluna2 tipo_de_dado,
        ...
        coluna_n tipo_de_dado DEFAULT valor_padrao
    );
    ```

- **Exemplo**:
    ```sql
    CREATE TABLE Pessoas (
        ID INT NOT NULL,
        Sobrenome VARCHAR(255) NOT NULL,
        PrimeiroNome VARCHAR(255),
        Idade INT,
        Cidade VARCHAR(255) DEFAULT 'Sandnes'
    );
    ```

- Neste exemplo, a coluna `Cidade` tem um valor padrão definido como `'Sandnes'`. Se um novo registro for inserido sem especificar um valor para `Cidade`, o valor padrão `'Sandnes'` será usado.

### Uso de funções com `DEFAULT`:

Você pode usar funções para definir valores padrão dinâmicos.

- **Exemplo**:
    ```sql
    CREATE TABLE Pedidos (
        ID INT NOT NULL,
        NumeroPedido INT NOT NULL,
        DataPedido DATE DEFAULT GETDATE()
    );
    ```

- Neste exemplo, a coluna `DataPedido` tem um valor padrão definido como a função `GETDATE()`, que retorna a data atual.

### `DEFAULT` em `ALTER TABLE`:

Você pode adicionar uma restrição `DEFAULT` a uma coluna existente com a instrução `ALTER TABLE`.

- **Sintaxe**:
    ```sql
    ALTER TABLE nome_da_tabela
    ALTER COLUMN nome_da_coluna SET DEFAULT valor_padrao;
    ```

- **Exemplo para MySQL**:
    ```sql
    ALTER TABLE Pessoas
    ALTER COLUMN Cidade SET DEFAULT 'Sandnes';
    ```

- **Exemplo para SQL Server**:
    ```sql
    ALTER TABLE Pessoas
    ADD CONSTRAINT df_Cidade
    DEFAULT 'Sandnes' FOR Cidade;
    ```

### Remover uma restrição `DEFAULT`:

Você pode remover uma restrição `DEFAULT` de uma coluna existente.

- **Sintaxe**:
    ```sql
    ALTER TABLE nome_da_tabela
    ALTER COLUMN nome_da_coluna DROP DEFAULT;
    ```

- **Exemplo**:
    ```sql
    ALTER TABLE Pessoas
    ALTER COLUMN Cidade DROP DEFAULT;
    ```

- Este exemplo remove a restrição `DEFAULT` da coluna `Cidade` na tabela `Pessoas`.

### Considerações finais:

- **Facilidade**: A restrição `DEFAULT` facilita a inserção de dados, pois você não precisa especificar um valor para uma coluna com um valor padrão.
- **Cuidado ao alterar**: Ao alterar ou remover uma restrição `DEFAULT`, verifique se as alterações não impactarão o comportamento esperado dos seus dados.
- **Consistência**: Usar valores padrão ajuda a manter a consistência nos dados de uma coluna ao lidar com inserções.

A restrição `DEFAULT` é uma forma útil de automatizar a inserção de valores padrão em colunas, simplificando a manutenção dos dados e a escrita de consultas. Use-a com sabedoria para melhorar a consistência e a eficiência do seu banco de dados.
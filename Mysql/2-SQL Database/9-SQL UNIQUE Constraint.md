A restrição `UNIQUE` em SQL garante que todos os valores em uma coluna sejam diferentes entre si. Tanto a restrição `UNIQUE` quanto a restrição `PRIMARY KEY` garantem a unicidade dos valores em uma ou mais colunas. No entanto, você pode ter várias restrições `UNIQUE` em uma tabela, mas apenas uma `PRIMARY KEY`.

### `UNIQUE` em `CREATE TABLE`:

Você pode definir a restrição `UNIQUE` ao criar uma tabela com a instrução `CREATE TABLE`.

- **Sintaxe para SQL Server / Oracle / MS Access**:
    ```sql
    CREATE TABLE nome_da_tabela (
        coluna1 tipo_de_dado NOT NULL UNIQUE,
        coluna2 tipo_de_dado,
        ...
    );
    ```

- **Sintaxe para MySQL**:
    ```sql
    CREATE TABLE nome_da_tabela (
        coluna1 tipo_de_dado NOT NULL,
        coluna2 tipo_de_dado,
        ...
        UNIQUE (nome_da_coluna)
    );
    ```

- **Exemplo**:
    ```sql
    CREATE TABLE Pessoas (
        ID INT NOT NULL UNIQUE,
        Sobrenome VARCHAR(255) NOT NULL,
        PrimeiroNome VARCHAR(255),
        Idade INT
    );
    ```

- Este exemplo cria uma tabela `Pessoas` onde a coluna `ID` tem a restrição `UNIQUE`, garantindo que todos os valores em `ID` sejam únicos.

- **Definir um nome para a restrição**:
    ```sql
    CREATE TABLE Pessoas (
        ID INT NOT NULL,
        Sobrenome VARCHAR(255) NOT NULL,
        PrimeiroNome VARCHAR(255),
        Idade INT,
        CONSTRAINT UC_Pessoa UNIQUE (ID, Sobrenome)
    );
    ```

- Este exemplo define uma restrição `UNIQUE` com um nome específico (`UC_Pessoa`) nas colunas `ID` e `Sobrenome`.

### `UNIQUE` em `ALTER TABLE`:

Você pode adicionar uma restrição `UNIQUE` a uma tabela existente com a instrução `ALTER TABLE`.

- **Sintaxe**:
    ```sql
    ALTER TABLE nome_da_tabela
    ADD UNIQUE (nome_da_coluna);
    ```

- **Exemplo**:
    ```sql
    ALTER TABLE Pessoas
    ADD UNIQUE (ID);
    ```

- Este exemplo adiciona uma restrição `UNIQUE` à coluna `ID` da tabela `Pessoas`.

- **Definir um nome para a restrição**:
    ```sql
    ALTER TABLE Pessoas
    ADD CONSTRAINT UC_Pessoa UNIQUE (ID, Sobrenome);
    ```

- Este exemplo adiciona uma restrição `UNIQUE` com um nome específico (`UC_Pessoa`) às colunas `ID` e `Sobrenome`.

### Remover uma restrição `UNIQUE`:

Você pode remover uma restrição `UNIQUE` de uma tabela existente.

- **Para MySQL**:
    ```sql
    ALTER TABLE nome_da_tabela
    DROP INDEX nome_da_restricao;
    ```

- **Para SQL Server / Oracle / MS Access**:
    ```sql
    ALTER TABLE nome_da_tabela
    DROP CONSTRAINT nome_da_restricao;
    ```

- **Exemplo**:
    ```sql
    ALTER TABLE Pessoas
    DROP INDEX UC_Pessoa;
    ```

- Este exemplo remove a restrição `UNIQUE` chamada `UC_Pessoa` da tabela `Pessoas`.

### Considerações finais:

- As restrições `UNIQUE` ajudam a manter a integridade dos dados, garantindo que os valores em uma ou mais colunas sejam únicos.
- É possível adicionar restrições `UNIQUE` a várias colunas ou combinações de colunas para criar chaves compostas.
- Seja cuidadoso ao remover restrições `UNIQUE`, pois isso pode permitir a inserção de dados duplicados em uma coluna que anteriormente era única.
- 
A restrição `NOT NULL` em SQL garante que uma coluna não possa conter valores `NULL`. Ela impõe que a coluna sempre tenha um valor, o que significa que você não pode inserir um novo registro ou atualizar um registro sem fornecer um valor para essa coluna.

### `NOT NULL` em `CREATE TABLE`:

Você pode definir a restrição `NOT NULL` ao criar uma nova tabela com a instrução `CREATE TABLE`.

- **Sintaxe**:
    ```sql
    CREATE TABLE nome_da_tabela (
        coluna1 tipo_de_dado NOT NULL,
        coluna2 tipo_de_dado,
        ...
    );
    ```

- **Exemplo**:
    ```sql
    CREATE TABLE Pessoas (
        ID INT NOT NULL,
        Sobrenome VARCHAR(255) NOT NULL,
        PrimeiroNome VARCHAR(255) NOT NULL,
        Idade INT
    );
    ```

- Neste exemplo, as colunas `ID`, `Sobrenome` e `PrimeiroNome` possuem a restrição `NOT NULL`, garantindo que essas colunas não possam conter valores `NULL`.

### `NOT NULL` em `ALTER TABLE`:

Você pode adicionar a restrição `NOT NULL` a uma coluna existente com a instrução `ALTER TABLE`.

- **Sintaxe para SQL Server / MS Access**:
    ```sql
    ALTER TABLE nome_da_tabela
    ALTER COLUMN nome_da_coluna tipo_de_dado NOT NULL;
    ```

- **Sintaxe para MySQL / Oracle (versão anterior a 10G)**:
    ```sql
    ALTER TABLE nome_da_tabela
    MODIFY COLUMN nome_da_coluna tipo_de_dado NOT NULL;
    ```

- **Sintaxe para Oracle 10G ou posterior**:
    ```sql
    ALTER TABLE nome_da_tabela
    MODIFY nome_da_coluna tipo_de_dado NOT NULL;
    ```

- **Exemplo**:
    ```sql
    ALTER TABLE Pessoas
    MODIFY COLUMN Idade INT NOT NULL;
    ```

- Este exemplo adiciona a restrição `NOT NULL` à coluna `Idade` da tabela `Pessoas`.

### Considerações adicionais:

- **Enforcement**: A restrição `NOT NULL` garante que uma coluna nunca contenha valores `NULL`.
- **Erro ao inserir ou atualizar**: Se uma tentativa for feita para inserir ou atualizar um registro sem um valor para uma coluna com a restrição `NOT NULL`, ocorrerá um erro.
- **Alterações futuras**: Quando você altera uma coluna existente para `NOT NULL`, certifique-se de que não haja valores `NULL` existentes nessa coluna, ou você receberá um erro.

A restrição `NOT NULL` é uma forma eficaz de garantir que uma coluna sempre contenha um valor, ajudando a manter a integridade dos dados em seu banco de dados.
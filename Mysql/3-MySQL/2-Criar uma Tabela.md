## CREATE TABLE

O comando `CREATE TABLE` é utilizado para criar uma nova tabela em um banco de dados. Aqui está um exemplo de como criar uma tabela chamada 'clientes' com algumas colunas:

```sql
-- Criar uma tabela chamada 'clientes' com algumas colunas
CREATE TABLE clientes (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100),
    email VARCHAR(100),
    data_cadastro DATE
);
```

A tabela 'clientes' possui as colunas 'id' (chave primária com auto incremento), 'nome', 'email' e 'data_cadastro'.

## SELECT * FROM TABLE

O comando `SELECT * FROM TABLE` é utilizado para selecionar todas as colunas de uma tabela em um banco de dados. Por exemplo, para selecionar todos os dados da tabela 'clientes', você pode usar o seguinte código:

```sql
-- Selecionar todas as colunas da tabela 'clientes'
SELECT * FROM clientes;
```

## RENAME TABLE

O comando `RENAME TABLE` é utilizado para renomear uma tabela em um banco de dados. Aqui está um exemplo de como renomear a tabela 'clientes' para 'clientes_novos':

```sql
-- Renomear a tabela 'clientes' para 'clientes_novos'
RENAME TABLE clientes TO clientes_novos;
```

## DROP TABLE

O comando `DROP TABLE` é utilizado para remover uma tabela de um banco de dados. Por exemplo, para remover a tabela 'clientes', você pode usar o seguinte código:

```sql
-- Remover a tabela 'clientes' do banco de dados
DROP TABLE clientes;
```

A remoção de uma tabela é uma operação irreversível.

## Adicionar uma coluna

O comando `ALTER TABLE` com a cláusula `ADD COLUMN` é utilizado para adicionar uma nova coluna a uma tabela existente. Por exemplo, para adicionar uma nova coluna chamada 'telefone' à tabela 'clientes', você pode usar o seguinte código:

```sql
-- Adicionar uma nova coluna 'telefone' à tabela 'clientes'
ALTER TABLE clientes ADD COLUMN telefone VARCHAR(15);
```

## Renomear uma coluna

O comando `ALTER TABLE` com a cláusula `CHANGE COLUMN` pode ser utilizado para renomear uma coluna em uma tabela existente. Por exemplo, para renomear a coluna 'telefone' para 'telefone_contato' na tabela 'clientes', você pode usar o seguinte código:

```sql
-- Renomear a coluna 'telefone' para 'telefone_contato' na tabela 'clientes'
ALTER TABLE clientes CHANGE COLUMN telefone telefone_contato VARCHAR(15);
```

## Modificar uma coluna

O comando `ALTER TABLE` com a cláusula `MODIFY COLUMN` pode ser utilizado para modificar as características de uma coluna em uma tabela existente. Por exemplo, para modificar a coluna 'telefone' para ter um tamanho máximo de 20 caracteres na tabela 'clientes', você pode usar o seguinte código:

```sql
-- Modificar a coluna 'telefone' para ter um tamanho máximo de 20 caracteres
ALTER TABLE clientes MODIFY COLUMN telefone_contato VARCHAR(20);
```

## Alterar a posição de uma coluna AFTER

O comando `ALTER TABLE` com a cláusula `MODIFY COLUMN` e `AFTER` pode ser utilizado para alterar a posição de uma coluna em uma tabela, colocando-a depois de outra coluna específica. Por exemplo, para mover a coluna 'telefone' para aparecer após a coluna 'nome' na tabela 'clientes', você pode usar o seguinte código:

```sql
-- Mover a coluna 'telefone_contato' para aparecer após a coluna 'nome'
ALTER TABLE clientes MODIFY COLUMN telefone_contato VARCHAR(20) AFTER nome;
```

## Alterar a posição de uma coluna FIRST

O comando `ALTER TABLE` com a cláusula `MODIFY COLUMN` e `FIRST` pode ser utilizado para mover uma coluna para a primeira posição em uma tabela. Por exemplo, para mover a coluna 'telefone' para ser a primeira coluna na tabela 'clientes', você pode usar o seguinte código:

```sql
-- Mover a coluna 'telefone_contato' para ser a primeira coluna
ALTER TABLE clientes MODIFY COLUMN telefone_contato VARCHAR(20) FIRST;
```

## Remover uma coluna

O comando `ALTER TABLE` com a cláusula `DROP COLUMN` é utilizado para remover uma coluna de uma tabela existente. Por exemplo, para remover a coluna 'telefone' da tabela 'clientes', você pode usar o seguinte código:

```sql
-- Remover a coluna 'telefone_contato' da tabela 'clientes'
ALTER TABLE clientes DROP COLUMN telefone_contato;
```


A restrição `NOT NULL` é usada para garantir que uma coluna em uma tabela do banco de dados não aceite valores nulos (`NULL`). Isso significa que todas as linhas devem ter um valor não nulo para essa coluna específica. Você pode adicionar a restrição `NOT NULL` ao criar uma nova tabela ou alterando uma tabela existente.

## Adicionar `NOT NULL` a uma nova tabela

Ao criar uma nova tabela, você pode definir uma ou mais colunas com a restrição `NOT NULL` para garantir que esses campos não aceitem valores nulos. Aqui está um exemplo de como criar uma nova tabela `clientes` com a coluna `nome` definida como `NOT NULL`:

```sql
-- Criar uma nova tabela 'clientes' com a restrição 'NOT NULL' na coluna 'nome'
CREATE TABLE clientes (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    email VARCHAR(100),
    data_cadastro DATE
);
```

Neste exemplo, a coluna `nome` tem a restrição `NOT NULL`, o que significa que cada linha deve ter um valor não nulo nessa coluna.

## Adicionar `NOT NULL` a uma tabela existente

Para adicionar a restrição `NOT NULL` a uma coluna existente em uma tabela, você pode usar o comando `ALTER TABLE` com a cláusula `MODIFY` para modificar a coluna desejada e adicionar a restrição.

Por exemplo, para adicionar a restrição `NOT NULL` à coluna `email` em uma tabela existente `clientes`:

```sql
-- Adicionar a restrição 'NOT NULL' à coluna 'email' em uma tabela existente 'clientes'
ALTER TABLE clientes
MODIFY COLUMN email VARCHAR(100) NOT NULL;
```

Neste exemplo, a tabela `clientes` é alterada para incluir a restrição `NOT NULL` na coluna `email`. Isso garante que todas as linhas da tabela tenham um valor não nulo nessa coluna.

A restrição `NOT NULL` ajuda a manter a integridade dos dados, garantindo que campos essenciais nas tabelas tenham valores válidos em todas as linhas.
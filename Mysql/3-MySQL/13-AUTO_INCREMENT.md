A palavra-chave `AUTO_INCREMENT` é usada em MySQL para definir uma coluna como uma sequência automática de números ao inserir novos dados. Isso é útil para gerar valores únicos para uma coluna, especialmente quando ela é definida como uma chave primária.

## `AUTO_INCREMENT` ao criar uma nova tabela

Quando você cria uma nova tabela com uma coluna definida como `AUTO_INCREMENT`, cada vez que você insere um novo registro sem especificar um valor para essa coluna, o banco de dados automaticamente gera um valor único e incrementado para a coluna.

Aqui está um exemplo de como criar uma nova tabela `transactions` com uma coluna `transaction_id` definida como `AUTO_INCREMENT`:

```sql
-- Criar uma nova tabela 'transactions' com a coluna 'transaction_id' definida como 'AUTO_INCREMENT'
CREATE TABLE transactions (
    transaction_id INT PRIMARY KEY AUTO_INCREMENT,
    amount DECIMAL(5, 2)
);
```

Neste exemplo, a coluna `transaction_id` é uma chave primária e é definida como `AUTO_INCREMENT`, o que significa que, ao inserir novos registros na tabela, o banco de dados gera automaticamente um valor único e incrementado para essa coluna.

## Definir o valor inicial de `AUTO_INCREMENT`

Você pode definir o valor inicial da sequência `AUTO_INCREMENT` para uma tabela existente usando o comando `ALTER TABLE` com a cláusula `AUTO_INCREMENT`. Isso define o próximo valor a ser usado para a sequência automática.

Por exemplo, para definir o valor inicial de `AUTO_INCREMENT` como 1000 para a tabela `transactions`:

```sql
-- Definir o valor inicial de 'AUTO_INCREMENT' como 1000 para a tabela 'transactions'
ALTER TABLE transactions 
AUTO_INCREMENT = 1000;
```

Ao definir o valor inicial de `AUTO_INCREMENT` para 1000, o próximo registro inserido na tabela `transactions` terá um `transaction_id` de 1000, e a sequência continuará a partir daí.

Os valores `AUTO_INCREMENT` são úteis para gerar identificadores únicos automaticamente em uma tabela, especialmente quando se lida com registros que precisam de um identificador único para cada inserção. Isso pode simplificar o gerenciamento de dados em tabelas do banco de dados.
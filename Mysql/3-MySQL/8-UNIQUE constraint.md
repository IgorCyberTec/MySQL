O *constraint* `UNIQUE` é uma restrição em bancos de dados que garante que os valores em uma ou mais colunas de uma tabela sejam únicos para cada linha. Ele pode ser adicionado tanto ao criar uma nova tabela quanto a uma tabela existente.

## Adicionar `UNIQUE CONSTRAINT` a uma nova tabela

Ao criar uma nova tabela, você pode definir uma ou mais colunas como únicas usando a restrição `UNIQUE`. Aqui está um exemplo de como adicionar a restrição `UNIQUE` à coluna `email` durante a criação de uma nova tabela `usuarios`:

```sql
-- Criar uma nova tabela 'usuarios' com a restrição 'UNIQUE' na coluna 'email'
CREATE TABLE usuarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(50),
    email VARCHAR(100) UNIQUE,
    data_nascimento DATE
);
```

Neste exemplo, a coluna `email` tem uma restrição `UNIQUE`, o que significa que cada valor de `email` deve ser único em toda a tabela.

## Adicionar `UNIQUE CONSTRAINT` a uma tabela existente

Para adicionar uma restrição `UNIQUE` a uma tabela existente, você pode usar o comando `ALTER TABLE` com a cláusula `ADD CONSTRAINT` seguido de um nome para a restrição e a cláusula `UNIQUE` especificando as colunas a serem afetadas.

Por exemplo, para adicionar uma restrição `UNIQUE` à coluna `email` de uma tabela existente `usuarios`:

```sql
-- Adicionar a restrição 'UNIQUE' à coluna 'email' em uma tabela existente 'usuarios'
ALTER TABLE usuarios
ADD CONSTRAINT unique_email UNIQUE (email);
```

Neste exemplo, a tabela `usuarios` é alterada para incluir uma restrição `UNIQUE` na coluna `email`. Isso garante que cada valor na coluna `email` seja único em toda a tabela.

As restrições `UNIQUE` ajudam a manter a integridade dos dados, evitando duplicação em colunas ou conjuntos de colunas específicas.
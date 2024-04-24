A *chave primária* (`PRIMARY KEY`) é uma restrição em bancos de dados que identifica uma coluna ou um conjunto de colunas como único para cada linha de uma tabela. A chave primária garante que os valores em suas colunas sejam únicos e não nulos. Vou explicar como definir uma chave primária ao criar uma nova tabela ou ao alterar uma tabela existente.

## Definir `PRIMARY KEY` ao criar uma nova tabela

Ao criar uma nova tabela, você pode definir uma ou mais colunas como chave primária usando a cláusula `PRIMARY KEY`. A chave primária pode ser definida diretamente na coluna ou nas colunas que você deseja identificar como únicas e não nulas.

Aqui está um exemplo de como criar uma nova tabela `produtos` com a coluna `codigo` definida como chave primária:

```sql
-- Criar uma nova tabela 'produtos' com a coluna 'codigo' definida como chave primária
CREATE TABLE produtos (
    codigo INT PRIMARY KEY,
    nome VARCHAR(100),
    preco DECIMAL(10, 2)
);
```

Neste exemplo, a coluna `codigo` é definida como a chave primária da tabela `produtos`, garantindo que cada valor nesta coluna seja único e não nulo.

Você também pode definir uma chave primária composta por múltiplas colunas ao criar a tabela. Por exemplo:

```sql
-- Criar uma nova tabela 'pedidos' com uma chave primária composta por 'pedido_id' e 'produto_id'
CREATE TABLE pedidos (
    pedido_id INT,
    produto_id INT,
    quantidade INT,
    PRIMARY KEY (pedido_id, produto_id)
);
```

Neste exemplo, a chave primária é composta pelas colunas `pedido_id` e `produto_id`, garantindo que a combinação dessas colunas seja única em toda a tabela.

## Definir `PRIMARY KEY` para uma tabela existente

Para adicionar uma chave primária a uma tabela existente, você pode usar o comando `ALTER TABLE` com a cláusula `ADD PRIMARY KEY` seguido da(s) coluna(s) desejada(s).

Por exemplo, para adicionar a chave primária à coluna `cliente_id` de uma tabela existente `clientes`:

```sql
-- Adicionar chave primária à coluna 'cliente_id' em uma tabela existente 'clientes'
ALTER TABLE clientes
ADD PRIMARY KEY (cliente_id);
```

Você também pode adicionar uma chave primária composta por múltiplas colunas em uma tabela existente. Por exemplo, para adicionar uma chave primária composta por `pedido_id` e `produto_id` à tabela `pedidos`:

```sql
-- Adicionar chave primária composta por 'pedido_id' e 'produto_id' à tabela 'pedidos'
ALTER TABLE pedidos
ADD PRIMARY KEY (pedido_id, produto_id);
```

É importante observar que para adicionar uma chave primária a uma tabela existente, as colunas especificadas devem ser únicas e não nulas. Portanto, você pode precisar remover ou modificar dados existentes ou adicionar índices para garantir a conformidade com essas restrições antes de adicionar a chave primária.

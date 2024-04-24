A restrição `CHECK` é uma forma de garantir que os valores em uma ou mais colunas de uma tabela obedeçam a uma condição específica. Pode ser usada ao criar uma nova tabela ou para modificar uma tabela existente. Vou explicar como adicionar, usar e remover uma restrição `CHECK`.

## CHECK constraint para uma nova tabela

Ao criar uma nova tabela, você pode adicionar uma restrição `CHECK` para garantir que os valores em uma ou mais colunas obedeçam a uma condição específica. Por exemplo, para criar uma nova tabela `funcionarios` com uma restrição `CHECK` na coluna `salario` para garantir que o valor seja maior ou igual a 0:

```sql
-- Criar uma nova tabela 'funcionarios' com uma restrição 'CHECK' na coluna 'salario'
CREATE TABLE funcionarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100),
    salario DECIMAL(10, 2) CHECK (salario >= 0),
    data_contratacao DATE
);
```

Neste exemplo, a coluna `salario` tem uma restrição `CHECK` para garantir que os salários sejam maiores ou iguais a 0.

## CHECK constraint para uma tabela existente

Para adicionar uma restrição `CHECK` a uma tabela existente, você pode usar o comando `ALTER TABLE` com a cláusula `ADD CONSTRAINT` para especificar a condição `CHECK` e a coluna na qual ela deve ser aplicada.

Por exemplo, para adicionar uma restrição `CHECK` à coluna `idade` em uma tabela existente `clientes` para garantir que a idade seja entre 0 e 120:

```sql
-- Adicionar uma restrição 'CHECK' à coluna 'idade' em uma tabela existente 'clientes'
ALTER TABLE clientes
ADD CONSTRAINT check_idade CHECK (idade >= 0 AND idade <= 120);
```

## Demonstração

Para ilustrar como a restrição `CHECK` funciona, vamos inserir alguns dados em uma tabela com uma restrição `CHECK`. Suponha que você tenha uma tabela `funcionarios` com uma restrição `CHECK` que garante que o salário seja maior ou igual a 0.

Primeiro, vamos inserir uma linha com um salário válido:

```sql
-- Inserir uma linha com um salário válido
INSERT INTO funcionarios (nome, salario, data_contratacao)
VALUES ('João', 2500, '2024-04-21');
```

Este comando deve funcionar corretamente.

Agora, vamos tentar inserir uma linha com um salário inválido (negativo), que deve falhar devido à restrição `CHECK`:

```sql
-- Inserir uma linha com um salário inválido (negativo)
INSERT INTO funcionarios (nome, salario, data_contratacao)
VALUES ('Maria', -500, '2024-04-21');
```

O comando acima deve falhar porque o salário é negativo e não atende à restrição `CHECK` definida para a coluna `salario`.

## Remover uma CHECK constraint

Para remover uma restrição `CHECK` de uma tabela existente, você pode usar o comando `ALTER TABLE` com a cláusula `DROP CONSTRAINT` seguido do nome da restrição.

Por exemplo, para remover a restrição `CHECK` `check_idade` de uma tabela `clientes`:

```sql
-- Remover a restrição 'CHECK' chamada 'check_idade' da tabela 'clientes'
ALTER TABLE clientes
DROP CONSTRAINT check_idade;
```

Em alguns sistemas de banco de dados, você pode precisar especificar a palavra-chave `CHECK` ao remover a restrição.

A restrição `CHECK` é útil para garantir que os dados em uma tabela sejam consistentes e cumpram certas condições ou regras de negócio específicas.
A palavra-chave `DEFAULT` pode ser usada em MySQL para definir valores padrão para colunas em uma tabela. Um valor padrão é atribuído automaticamente a uma coluna quando uma nova linha é inserida na tabela sem especificar um valor para essa coluna.

## DEFAULT ao criar uma nova tabela

Ao criar uma nova tabela, você pode definir um valor padrão para uma ou mais colunas usando a palavra-chave `DEFAULT` seguida do valor desejado. Aqui está um exemplo de como criar uma nova tabela `clientes` com um valor padrão para a coluna `cidade`:

```sql
-- Criar uma nova tabela 'clientes' com um valor padrão para a coluna 'cidade'
CREATE TABLE clientes (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100),
    cidade VARCHAR(50) DEFAULT 'Desconhecida',
    data_cadastro DATE DEFAULT CURRENT_DATE()
);
```

Neste exemplo, a coluna `cidade` tem um valor padrão de `'Desconhecida'`, enquanto a coluna `data_cadastro` tem um valor padrão de `CURRENT_DATE()`. Isso significa que, ao inserir uma nova linha na tabela `clientes` sem especificar valores para essas colunas, o valor padrão será usado.

## DEFAULT para uma tabela existente

Para adicionar um valor padrão a uma coluna de uma tabela existente, você pode usar o comando `ALTER TABLE` com a cláusula `ALTER COLUMN` e a palavra-chave `SET DEFAULT` para definir o novo valor padrão.

Por exemplo, para adicionar um valor padrão para a coluna `estado` de uma tabela existente `clientes`:

```sql
-- Adicionar um valor padrão para a coluna 'estado' em uma tabela existente 'clientes'
ALTER TABLE clientes
ALTER COLUMN estado SET DEFAULT 'SP';
```

Neste exemplo, a coluna `estado` passa a ter um valor padrão de `'SP'`, que será utilizado para novas linhas inseridas na tabela `clientes` quando nenhum valor específico for fornecido para a coluna `estado`.

Os valores padrão são úteis para garantir consistência e preenchimento automático de colunas ao inserir novos dados em uma tabela, especialmente quando alguns valores são mais comumente utilizados ou esperados.
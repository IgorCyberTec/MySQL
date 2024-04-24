## CREATE

O comando `CREATE` é utilizado para criar novas tabelas, bancos de dados ou outros objetos no MySQL. Aqui está um exemplo de como criar um banco de dados e uma tabela:

```sql
-- Criar um banco de dados chamado 'meu_banco_de_dados'
CREATE DATABASE meu_banco_de_dados;

-- Usar o banco de dados criado
USE meu_banco_de_dados;

-- Criar uma tabela chamada 'clientes' com algumas colunas
CREATE TABLE clientes (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100),
    email VARCHAR(100),
    data_cadastro DATE
);
```

##  USE

O comando `USE` é utilizado para selecionar um banco de dados específico para ser utilizado nas operações subsequentes. 

```sql
-- Usar o banco de dados 'meu_banco_de_dados'
USE meu_banco_de_dados;
```

Depois de usar este comando, todas as operações subsequentes serão realizadas dentro do banco de dados selecionado.

##  DROP

O comando `DROP` é utilizado para remover bancos de dados, tabelas ou outros objetos do MySQL. Ele deve ser usado com cautela, pois a operação é irreversível.

```sql
-- Remover a tabela 'clientes' do banco de dados
DROP TABLE clientes;

-- Remover o banco de dados 'meu_banco_de_dados'
DROP DATABASE meu_banco_de_dados;
```

##  READ ONLY

No MySQL, o modo de banco de dados somente leitura (`READ ONLY`) pode ser configurado para impedir qualquer operação de escrita em um banco de dados específico ou em todo o servidor. Isso pode ser útil para proteger os dados contra alterações não autorizadas ou para fins de backup.

Para configurar um banco de dados ou o servidor como somente leitura, você pode usar variáveis de sistema, como mostrado nos exemplos abaixo:

```sql
-- Configurar o servidor MySQL como somente leitura
SET GLOBAL read_only = 1;

-- Configurar um banco de dados específico como somente leitura
ALTER DATABASE meu_banco_de_dados READ ONLY = TRUE;
```

### Criando uma Tabela

Para criar uma tabela em MySQL, você usa a instrução SQL "CREATE TABLE". Certifique-se de definir o nome do banco de dados ao criar a conexão.

Exemplo para criar uma tabela chamada "clientes":

```python
import mysql.connector

# Conectando ao banco de dados MySQL
mydb = mysql.connector.connect(
    host="localhost",
    user="seu_usuario",
    password="sua_senha",
    database="meubancodedados"
)

# Criando um cursor para executar instruções SQL
mycursor = mydb.cursor()

# Criando uma tabela chamada "clientes" com as colunas "nome" e "endereco"
mycursor.execute("CREATE TABLE clientes (nome VARCHAR(255), endereco VARCHAR(255))")

# Se não ocorreram erros, a tabela foi criada com sucesso.
```

### Verificando se a Tabela Existe

Você pode verificar se uma tabela existe listando todas as tabelas em seu banco de dados com a instrução "SHOW TABLES":

Exemplo para retornar uma lista das tabelas em seu banco de dados:

```python
import mysql.connector

# Conectando ao banco de dados MySQL
mydb = mysql.connector.connect(
    host="localhost",
    user="seu_usuario",
    password="sua_senha",
    database="meubancodedados"
)

# Criando um cursor para executar instruções SQL
mycursor = mydb.cursor()

# Executando a instrução para listar todas as tabelas no banco de dados
mycursor.execute("SHOW TABLES")

# Imprimindo a lista de tabelas
for x in mycursor:
    print(x)
```

### Chave Primária

Ao criar uma tabela, você também deve criar uma coluna com uma chave única para cada registro. Isso pode ser feito definindo uma **PRIMARY KEY**.

Podemos usar a declaração "INT AUTO_INCREMENT PRIMARY KEY" para inserir um número único para cada registro. O valor começa em 1 e aumenta em um para cada novo registro.

Exemplo para criar uma chave primária ao criar a tabela:

```python
import mysql.connector

# Conectando ao banco de dados MySQL
mydb = mysql.connector.connect(
    host="localhost",
    user="seu_usuario",
    password="sua_senha",
    database="meubancodedados"
)

# Criando um cursor para executar instruções SQL
mycursor = mydb.cursor()

# Criando uma tabela chamada "clientes" com uma chave primária
mycursor.execute("CREATE TABLE clientes (id INT AUTO_INCREMENT PRIMARY KEY, nome VARCHAR(255), endereco VARCHAR(255))")
```

### Adicionando Chave Primária em uma Tabela Existente

Se a tabela já existir, você pode adicionar uma chave primária com a instrução "ALTER TABLE":

Exemplo para adicionar uma chave primária em uma tabela existente chamada "clientes":

```python
import mysql.connector

# Conectando ao banco de dados MySQL
mydb = mysql.connector.connect(
    host="localhost",
    user="seu_usuario",
    password="sua_senha",
    database="meubancodedados"
)

# Criando um cursor para executar instruções SQL
mycursor = mydb.cursor()

# Adicionando uma chave primária na tabela existente "clientes"
mycursor.execute("ALTER TABLE clientes ADD COLUMN id INT AUTO_INCREMENT PRIMARY KEY")
```

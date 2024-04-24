Em MySQL, você pode combinar linhas de duas ou mais tabelas com base em uma coluna relacionada entre elas usando a instrução JOIN. Os tipos de JOIN mais comuns são INNER JOIN, LEFT JOIN e RIGHT JOIN. Em Python, você pode usar a biblioteca *MySQL Connector* para executar consultas JOIN em um banco de dados MySQL.

### Exemplo de Inner Join

Vamos usar as tabelas `users` e `products` para mostrar o nome do produto favorito de cada usuário.

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

# SQL para fazer INNER JOIN entre as tabelas "users" e "products"
sql = """
SELECT
    users.name AS user,
    products.name AS favorite
FROM
    users
INNER JOIN
    products ON users.fav = products.id
"""

# Executando a consulta
mycursor.execute(sql)

# Obtendo os resultados
myresult = mycursor.fetchall()

# Exibindo os resultados
for registro em myresult:
    print(registro)
```

### Exemplo de Left Join

O LEFT JOIN inclui todos os registros da tabela à esquerda (`users`) e os registros correspondentes da tabela à direita (`products`). Se não houver correspondência, a tabela à direita será preenchida com valores nulos.

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

# SQL para fazer LEFT JOIN entre as tabelas "users" e "products"
sql = """
SELECT
    users.name AS user,
    products.name AS favorite
FROM
    users
LEFT JOIN
    products ON users.fav = products.id
"""

# Executando a consulta
mycursor.execute(sql)

# Obtendo os resultados
myresult = mycursor.fetchall()

# Exibindo os resultados
for registro em myresult:
    print(registro)
```

### Exemplo de Right Join

O RIGHT JOIN inclui todos os registros da tabela à direita (`products`) e os registros correspondentes da tabela à esquerda (`users`). Se não houver correspondência, a tabela à esquerda será preenchida com valores nulos.

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

# SQL para fazer RIGHT JOIN entre as tabelas "users" e "products"
sql = """
SELECT
    users.name AS user,
    products.name AS favorite
FROM
    users
RIGHT JOIN
    products ON users.fav = products.id
"""

# Executando a consulta
mycursor.execute(sql)

# Obtendo os resultados
myresult = mycursor.fetchall()

# Exibindo os resultados
for registro em myresult:
    print(registro)
```

Esses são exemplos de como você pode usar JOINs em consultas SQL para combinar linhas de diferentes tabelas.
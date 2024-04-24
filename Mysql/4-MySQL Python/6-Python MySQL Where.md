Ao selecionar registros de uma tabela em MySQL, você pode usar a instrução "WHERE" para filtrar a seleção com base em uma condição específica. Em Python, você pode usar a biblioteca *MySQL Connector* para executar consultas com filtros em um banco de dados MySQL.

### Selecionando com um Filtro

Exemplo para selecionar registros onde o endereço é "Park Lane 38":

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

# SQL para selecionar registros com o endereço "Park Lane 38"
sql = "SELECT * FROM clientes WHERE endereco = 'Park Lane 38'"

# Executando a consulta
mycursor.execute(sql)

# Obtendo os resultados
myresult = mycursor.fetchall()

# Exibindo os resultados
for registro in myresult:
    print(registro)
```

### Caracteres Coringa

Você pode selecionar registros que começam, incluem ou terminam com uma determinada letra ou frase usando caracteres coringa, como `%`.

Exemplo para selecionar registros onde o endereço contém a palavra "way":

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

# SQL para selecionar registros com o endereço contendo a palavra "way"
sql = "SELECT * FROM clientes WHERE endereco LIKE '%way%'"

# Executando a consulta
mycursor.execute(sql)

# Obtendo os resultados
myresult = mycursor.fetchall()

# Exibindo os resultados
for registro in myresult:
    print(registro)
```

### Prevenção de Injeção SQL

Quando os valores da consulta são fornecidos pelo usuário, é importante escapar esses valores para prevenir injeções SQL, uma técnica comum de hacking para destruir ou usar indevidamente o banco de dados.

O módulo `mysql.connector` possui métodos para escapar os valores da consulta, como o placeholder `%s`.

Exemplo para escapar valores da consulta usando o método placeholder `%s`:

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

# SQL para selecionar registros com o endereço "Yellow Garden 2" usando placeholder
sql = "SELECT * FROM clientes WHERE endereco = %s"
adr = ("Yellow Garden 2",)

# Executando a consulta com valores escapados
mycursor.execute(sql, adr)

# Obtendo os resultados
myresult = mycursor.fetchall()

# Exibindo os resultados
for registro em myresult:
    print(registro)
```

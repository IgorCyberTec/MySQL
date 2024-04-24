Em Python, você pode criar um banco de dados MySQL usando a instrução SQL "CREATE DATABASE". Aqui está uma explicação do processo com código em português.

### Criando um Banco de Dados

Para criar um banco de dados em MySQL, use a instrução "CREATE DATABASE":

```python
import mysql.connector

# Conectando ao banco de dados MySQL
mydb = mysql.connector.connect(
    host="localhost",
    user="seu_usuario",
    password="sua_senha"
)

# Criando um cursor para executar instruções SQL
mycursor = mydb.cursor()

# Executando a instrução para criar um banco de dados chamado "meubancodedados"
mycursor.execute("CREATE DATABASE meubancodedados")

# Se não ocorreram erros, o banco de dados foi criado com sucesso.
```

### Verificando se um Banco de Dados Existe

Você pode verificar se um banco de dados existe listando todos os bancos de dados no seu sistema usando a instrução "SHOW DATABASES":

```python
import mysql.connector

# Conectando ao banco de dados MySQL
mydb = mysql.connector.connect(
    host="localhost",
    user="seu_usuario",
    password="sua_senha"
)

# Criando um cursor para executar instruções SQL
mycursor = mydb.cursor()

# Executando a instrução para listar todos os bancos de dados
mycursor.execute("SHOW DATABASES")

# Imprimindo a lista de bancos de dados
for x in mycursor:
    print(x)
```

### Tentando Acessar um Banco de Dados

Você pode tentar acessar um banco de dados ao fazer a conexão. Se o banco de dados não existir, você receberá um erro:

```python
import mysql.connector

# Tentando conectar ao banco de dados "meubancodedados"
mydb = mysql.connector.connect(
    host="localhost",
    user="seu_usuario",
    password="sua_senha",
    database="meubancodedados"
)

# Se o banco de dados não existir, um erro será gerado.
```

Substitua `"seu_usuario"` pelo seu nome de usuário, `"sua_senha"` pela sua senha e `"meubancodedados"` pelo nome do banco de dados que você deseja verificar.
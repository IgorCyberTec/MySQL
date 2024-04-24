Aqui está uma explicação sobre como inserir dados em uma tabela MySQL usando Python. O processo é explicado com exemplos de código em português.

### Inserindo Dados em uma Tabela

Para preencher uma tabela em MySQL, você pode usar a instrução "INSERT INTO". 

Exemplo para inserir um registro na tabela "clientes":

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

# SQL para inserir dados na tabela "clientes"
sql = "INSERT INTO clientes (nome, endereco) VALUES (%s, %s)"
val = ("João", "Rua Principal 21")

# Executando a instrução SQL
mycursor.execute(sql, val)

# Confirma as mudanças no banco de dados
mydb.commit()

print(mycursor.rowcount, "registro inserido.")
```

**Importante**: Note a instrução `mydb.commit()`. Ela é necessária para confirmar as mudanças, caso contrário, as mudanças não serão feitas na tabela.

### Inserindo Múltiplas Linhas

Para inserir múltiplas linhas em uma tabela, use o método `executemany()`. O segundo parâmetro do método é uma lista de tuplas, contendo os dados que você deseja inserir.

Exemplo para preencher a tabela "clientes" com dados:

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

# SQL para inserir dados na tabela "clientes"
sql = "INSERT INTO clientes (nome, endereco) VALUES (%s, %s)"
val = [
    ('Pedro', 'Rua Baixa 4'),
    ('Ana', 'Rua da Maçã 652'),
    ('Hanna', 'Montanha 21'),
    ('Miguel', 'Vale 345'),
    ('Sandra', 'Boulevard Oceano 2'),
    ('Beatriz', 'Grama Verde 1'),
    ('Ricardo', 'Rua Céu 331'),
    ('Susana', 'Rua Única 98'),
    ('Vitória', 'Jardim Amarelo 2'),
    ('Bento', 'Avenida Parque 38'),
    ('Guilherme', 'Rua Central 954'),
    ('Carlos', 'Estrada Principal 989'),
    ('Violeta', 'Caminho Lateral 1633')
]

# Executando a instrução SQL com múltiplas linhas
mycursor.executemany(sql, val)

# Confirma as mudanças no banco de dados
mydb.commit()

print(mycursor.rowcount, "registros inseridos.")
```

### Obter ID Inserido

Você pode obter o ID da linha que acabou de inserir perguntando ao objeto cursor.

Observação: Se você inserir mais de uma linha, o ID da última linha inserida será retornado.

Exemplo para inserir uma linha e retornar o ID:

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

# SQL para inserir dados na tabela "clientes"
sql = "INSERT INTO clientes (nome, endereco) VALUES (%s, %s)"
val = ("Michele", "Vila Azul")

# Executando a instrução SQL
mycursor.execute(sql, val)

# Confirma as mudanças no banco de dados
mydb.commit()

# Obtendo o ID da linha inserida
print("1 registro inserido, ID:", mycursor.lastrowid)
```
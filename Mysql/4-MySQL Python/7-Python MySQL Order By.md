A instrução "ORDER BY" em MySQL é usada para ordenar o resultado de uma consulta em ordem crescente ou decrescente. Por padrão, o resultado é ordenado em ordem crescente, mas você pode usar a palavra-chave "DESC" para ordenar em ordem decrescente.

Aqui está uma explicação de como usar o "ORDER BY" com exemplos de código em português.

### Ordenar o Resultado

Use a instrução "ORDER BY" para ordenar o resultado de uma consulta.

Exemplo para ordenar o resultado alfabeticamente pelo nome:

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

# SQL para selecionar todos os registros da tabela "clientes" e ordená-los por nome
sql = "SELECT * FROM clientes ORDER BY nome"

# Executando a consulta
mycursor.execute(sql)

# Obtendo os resultados
myresult = mycursor.fetchall()

# Exibindo os resultados
for registro em myresult:
    print(registro)
```

### Ordenar em Ordem Decrescente

Use a palavra-chave "DESC" para ordenar o resultado em ordem decrescente.

Exemplo para ordenar o resultado em ordem decrescente pelo nome:

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

# SQL para selecionar todos os registros da tabela "clientes" e ordená-los por nome em ordem decrescente
sql = "SELECT * FROM clientes ORDER BY nome DESC"

# Executando a consulta
mycursor.execute(sql)

# Obtendo os resultados
myresult = mycursor.fetchall()

# Exibindo os resultados
for registro em myresult:
    print(registro)
```
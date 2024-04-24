A instrução "UPDATE" em MySQL é usada para atualizar registros existentes em uma tabela. Em Python, você pode usar a biblioteca *MySQL Connector* para executar consultas de atualização em um banco de dados MySQL.

### Atualizando uma Tabela

Para atualizar registros existentes em uma tabela, use a instrução "UPDATE" junto com uma cláusula "WHERE" para especificar quais registros você deseja atualizar.

Exemplo para alterar a coluna de endereço de "Valley 345" para "Canyon 123":

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

# SQL para atualizar o endereço de "Valley 345" para "Canyon 123"
sql = "UPDATE clientes SET endereco = 'Canyon 123' WHERE endereco = 'Valley 345'"

# Executando a instrução
mycursor.execute(sql)

# Confirma as mudanças no banco de dados
mydb.commit()

print(mycursor.rowcount, "registro(s) afetado(s)")
```

**Importante**: Note a instrução `mydb.commit()`. Ela é necessária para confirmar as mudanças, caso contrário, nenhuma mudança será feita na tabela.

Observe a cláusula "WHERE" na sintaxe do "UPDATE": ela especifica quais registros devem ser atualizados. Se você omitir a cláusula "WHERE", todos os registros serão atualizados!

### Prevenção de Injeção SQL

É considerado uma boa prática escapar os valores de qualquer consulta, inclusive em instruções de atualização, para prevenir injeções SQL, uma técnica comum de hacking para destruir ou usar indevidamente seu banco de dados.

O módulo `mysql.connector` usa o placeholder `%s` para escapar valores na instrução de atualização.

Exemplo para escapar valores usando o placeholder `%s`:

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

# SQL para atualizar o endereço usando placeholders
sql = "UPDATE clientes SET endereco = %s WHERE endereco = %s"
val = ("Canyon 123", "Valley 345")

# Executando a consulta com valores escapados
mycursor.execute(sql, val)

# Confirma as mudanças no banco de dados
mydb.commit()

print(mycursor.rowcount, "registro(s) afetado(s)")
```
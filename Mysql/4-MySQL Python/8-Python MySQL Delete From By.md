Você pode deletar registros de uma tabela existente usando a instrução "DELETE FROM" em MySQL. Em Python, você pode usar a biblioteca *MySQL Connector* para executar consultas de exclusão em um banco de dados MySQL.

### Deletando Registros

Para deletar registros de uma tabela existente, use a instrução "DELETE FROM" seguida de uma cláusula "WHERE" para especificar quais registros você deseja excluir.

Exemplo para deletar registros em que o endereço é "Mountain 21":

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

# SQL para deletar registros com o endereço "Mountain 21"
sql = "DELETE FROM clientes WHERE endereco = 'Mountain 21'"

# Executando a consulta
mycursor.execute(sql)

# Confirma as mudanças no banco de dados
mydb.commit()

print(mycursor.rowcount, "registro(s) deletado(s)")
```

**Importante**: Note a instrução `mydb.commit()`. Ela é necessária para confirmar as mudanças, caso contrário, nenhuma mudança será feita na tabela.

Observe a cláusula "WHERE" na sintaxe do "DELETE". Ela especifica quais registros devem ser deletados. Se você omitir a cláusula "WHERE", todos os registros serão deletados!

### Prevenção de Injeção SQL

É considerado uma boa prática escapar os valores de qualquer consulta, inclusive em instruções de exclusão, para prevenir injeções SQL, uma técnica comum de hacking para destruir ou usar indevidamente seu banco de dados.

O módulo `mysql.connector` usa o placeholder `%s` para escapar valores na instrução de exclusão.

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

# SQL para deletar registros com o endereço "Yellow Garden 2" usando placeholder
sql = "DELETE FROM clientes WHERE endereco = %s"
adr = ("Yellow Garden 2",)

# Executando a consulta com valores escapados
mycursor.execute(sql, adr)

# Confirma as mudanças no banco de dados
mydb.commit()

print(mycursor.rowcount, "registro(s) deletado(s)")
```

As funções `CURRENT_DATE()` e `CURRENT_TIME()` são utilizadas em MySQL para obter a data e a hora atuais, respectivamente, do sistema do banco de dados. Ambas as funções retornam valores baseados no fuso horário definido no servidor MySQL.

## CURRENT_DATE()

A função `CURRENT_DATE()` retorna a data atual no formato `YYYY-MM-DD` (ano-mês-dia). Por exemplo, se a data atual for 21 de abril de 2024, a função retornará a string `"2024-04-21"`.

Exemplo de uso:

```sql
-- Obter a data atual
SELECT CURRENT_DATE();
```

## CURRENT_TIME()

A função `CURRENT_TIME()` retorna a hora atual no formato `HH:MM:SS` (hora-minuto-segundo). Por exemplo, se a hora atual for 15:30:45, a função retornará a string `"15:30:45"`.

Exemplo de uso:

```sql
-- Obter a hora atual
SELECT CURRENT_TIME();
```

Essas funções podem ser usadas em consultas SQL para inserir ou comparar a data ou a hora atual em relação a dados de uma tabela, ou para realizar operações baseadas na data e hora atuais. Por exemplo, você pode usá-las para adicionar registros com a data ou hora atuais ou para consultar registros que foram adicionados ou atualizados em um determinado período.

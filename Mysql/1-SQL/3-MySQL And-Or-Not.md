Os operadores `AND`, `OR` e `NOT` em MySQL são usados para combinar condições na cláusula `WHERE` e filtrar registros com base em mais de uma condição. Esses operadores permitem realizar consultas mais sofisticadas e selecionar dados com maior precisão.

### `AND`:

- O operador `AND` é usado para combinar múltiplas condições. Um registro é exibido somente se todas as condições separadas por `AND` forem verdadeiras.
- Exemplo:
    ```mysql
    SELECT * FROM clientes WHERE pais = 'Alemanha' AND cidade = 'Berlim';
    ```

### `OR`:

- O operador `OR` é usado para combinar múltiplas condições. Um registro é exibido se pelo menos uma das condições separadas por `OR` for verdadeira.
- Exemplo:
    ```mysql
    SELECT * FROM clientes WHERE cidade = 'Berlim' OR cidade = 'Stuttgart';
    ```

### `NOT`:

- O operador `NOT` é usado para negar uma condição, ou seja, para exibir registros quando uma condição específica não é verdadeira.
- Exemplo:
    ```mysql
    SELECT * FROM clientes WHERE NOT pais = 'Alemanha';
    ```

### Combinando `AND`, `OR` e `NOT`:

Você pode combinar os operadores `AND`, `OR` e `NOT` para criar consultas mais complexas e específicas.

- **Usar parênteses**:
    - Ao combinar `AND`, `OR` e `NOT`, é importante usar parênteses para definir a precedência das condições.
    - Por exemplo, se você quer selecionar registros onde o país é "Alemanha" e a cidade é "Berlim" ou "Stuttgart", você pode usar:
        ```mysql
        SELECT * FROM clientes WHERE pais = 'Alemanha' AND (cidade = 'Berlim' OR cidade = 'Stuttgart');
        ```

- **Exemplo com `NOT`**:
    - Se você quer selecionar registros onde o país não é "Alemanha" e não é "EUA", você pode usar:
        ```mysql
        SELECT * FROM clientes WHERE NOT pais = 'Alemanha' AND NOT pais = 'EUA';
        ```

### Considerações finais:

- Combine `AND`, `OR` e `NOT` para criar condições mais precisas e consultas mais eficientes.
- Use parênteses para definir claramente a precedência das condições, especialmente ao combinar `AND` e `OR`.
- Pratique combinando esses operadores em consultas `WHERE` para aprender como criar consultas mais complexas e obter resultados mais específicos.
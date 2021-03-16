https://www.youtube.com/watch?v=STo98QUKDS8

```sql
WITH fruits AS (SELECT ['raspberry', 'blackberry', 'strawberry', 'cherry'] AS fruit_array)


SELECT fruit_array[OFFSET(2)]
AS zero_indexed
FROM fruits
```

|   | zero_indexed |
|---|--------------|
|1  | strawberry   |

	

```sql
WITH fruits AS (SELECT ['raspberry', 'blackberry', 'strawberry', 'cherry'] AS fruit_array)


SELECT fruit_array[ORDINAL(2)]
AS one_indexed
FROM fruits
```

|   | one_indexed |
|---|--------------|
|1  | blackberry  |

```sql
SELECT['apple', 'pear', 'peach']
AS item, 'JACOB' AS customer_name
```

|  | items | customer_name |
|--|-------|---------------|
| 1 | apple | JACOB |
|  | pear |  |
|  | peach |  |

```sql
SELECT['apple', 'pear', 'peach']
AS item, ['JACOB', 'COBRA'] AS customer_name
```

|  | items | customer_name |
|--|-------|---------------|
| 1| apple | JACOB |
|  | pear | COBRA |
|  | peach |  |

```sql
SELECT items, customer_name
FROM 
  UNNEST(['apple', 'pear', 'peach']) AS items
CROSS JOIN 
(SELECT 'JACOB' AS customer_name)
```

|  | items | customer_name |
|--|-------|---------------|
|1 | apple | JACOB |
|2 | pear | JACOB |
|3 | peach | JACOB |

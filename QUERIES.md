1. Selezionare tutti gli studenti nati nel 1990.

```sql
SELECT *
FROM students
WHERE date_of_birth LIKE "1990-%-%"
```

```sql
SELECT *
FROM students
WHERE year(date_of_birth) = 1990
```

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

2. Selezionare tutti i corsi che valgono più di 10 crediti (479)

```sql
SELECT *
FROM courses
WHERE cfu > 10
```

3.  Selezionare tutti gli studenti che hanno più di 30 anni

```sql
SELECT *
FROM students
WHERE 2023 - year(date_of_birth) > 30
```

4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea

```sql
SELECT *
FROM `courses`
WHERE period = 'I semestre' && year = 1
```

5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020

```sql
SELECT *
FROM `exams`
WHERE hour > '14:%:%' && date = '2020-06-20'
```

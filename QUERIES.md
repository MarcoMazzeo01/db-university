1. Selezionare tutti gli studenti nati nel 1990.

```sql
SELECT *
FROM students
WHERE date_of_birth LIKE "1990-%-%";
```

```sql
SELECT *
FROM students
WHERE year(date_of_birth) = 1990;
```

2. Selezionare tutti i corsi che valgono più di 10 crediti (479)

```sql
SELECT *
FROM courses
WHERE cfu > 10;
```

3.  Selezionare tutti gli studenti che hanno più di 30 anni

```sql
SELECT *
FROM students
WHERE year(CURRENT_DATE) - year(date_of_birth) > 30;
```

```sql
--Metodo alternativo di Tiziano
SELECT *
FROM students
WHERE TIMESTAMPDIFF(year, `date_of_birth`, CURDATE()) > 30;
```

4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea

```sql
SELECT *
FROM `courses`
WHERE period = 'I semestre' AND year = 1;
```

5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020

```sql
SELECT *
FROM `exams`
WHERE hour > '14:%:%' AND date = '2020-06-20';
```

6.  Selezionare tutti i corsi di laurea magistrale

```sql
SELECT *
FROM `degrees`
WHERE level = 'magistrale';
```

7. Da quanti dipartimenti è composta l'università?

```sql
SELECT COUNT(*)
FROM departments;
```

8.  Quanti sono gli insegnanti che non hanno un numero di telefono?

```sql
SELECT *
FROM `teachers`
WHERE phone is NULL;
```

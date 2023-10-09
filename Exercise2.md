## GROUP BY

1. Contare quanti iscritti ci sono stati ogni anno

```sql
SELECT COUNT(*), year(enrolment_date) AS "anno"
FROM students
GROUP BY YEAR(enrolment_date);
```

2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

```sql
SELECT COUNT(*), office_address as "Indirizzo"
FROM teachers
GROUP BY office_address;
```

3. Calcolare la media dei voti di ogni appello d'esame

```sql
SELECT AVG(vote) as "media", exam_id as "appello"
FROM exam_student
GROUP BY appello;
```

4. Contare quanti corsi di laurea ci sono per ogni dipartimento

```sql
SELECT COUNT(id) as "Corsi di Laurea", department_id as "Dipartimento"
FROM degrees
GROUP BY Dipartimento;
```

## JOIN

1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

```sql
SELECT students.name, students.surname, degrees.name
FROM students
JOIN degrees ON degrees.id = students.degree_id AND degrees.name = 'Corso di Laurea in Economia';
```

2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

```sql
SELECT degrees.name, degrees.level, departments.name
FROM departments
JOIN degrees ON degrees.department_id = departments.id
WHERE degrees.level = 'magistrale' AND departments.name = "Dipartimento di Neuroscienze";
```

3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

```sql

```

5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

```sql

```

7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18.

```sql

```

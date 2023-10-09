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

```sql
/* Non sono sicuro sia corretto?*/
SELECT courses.name
FROM courses
JOIN course_teacher ON course_teacher.course_id = id
WHERE course_teacher.teacher_id = 44
```

4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

```sql
SELECT students.surname, students.name, degrees.name, departments.name
FROM students
JOIN degrees ON students.degree_id = degrees.id
JOIN departments ON degrees.department_id = departments.id
ORDER BY students.surname, students.name ASC
```

5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

```sql

```

6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

```sql
SELECT DISTINCT teachers.name, teachers.surname
FROM teachers
JOIN course_teacher ON course_teacher.teacher_id = teachers.id
JOIN courses ON courses.id = course_teacher.course_id
JOIN degrees ON degrees.id = courses.degree_id
JOIN departments ON departments.id = degrees.department_id
WHERE departments.name = "Dipartimento di Matematica"
ORDER BY `teachers`.`surname` DESC
```

7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18.

```sql

```

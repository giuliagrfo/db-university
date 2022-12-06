# Dopo aver creato un nuovo database nel vostro phpMyAdmin e aver importato lo schema (stesso allegato di stamattina), eseguite le query qui sotto.
# Query Todo:
* Selezionare tutti gli studenti nati nel 1990 (160)
```sql
SELECT* FROM students WHERE year(date_of_birth )=1990;
```
* Selezionare tutti i corsi che valgono più di 10 crediti (479)
```sql
SELECT* FROM courses WHERE cfu >10;
```
* Selezionare tutti gli studenti che hanno più di 30 anni
```sql
SELECT* FROM students WHERE date_of_birth <= '1992-12-05';
```
* Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)
```sql
SELECT* FROM courses WHERE period='I semestre' AND year=1;
```
* Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21)
```sql
SELECT* FROM exams WHERE `date`='2020-06-20' AND hour >='14:00:00';
```
* Selezionare tutti i corsi di laurea magistrale (38)
```sql
SELECT* FROM degrees WHERE name LIKE '%Magistrale%';
```
```sql
SELECT* FROM degrees WHERE level='magistrale';
```
* Da quanti dipartimenti è composta l'università? (12)
```sql
SELECT COUNT(id) as number_of_departments FROM departments;
```
* Quanti sono gli insegnanti che non hanno un numero di telefono? (50)
```sql
SELECT COUNT(id) as teachers_without_phone_number FROM teachers WHERE phone is NUll;
```


# Second Part

# Group by:
* Contare quanti iscritti ci sono stati ogni anno
```sql
SELECT COUNT(id) as `enrolled`, year(`enrolment_date`) FROM `students` GROUP BY year(`enrolment_date`);
```
* Contare gli insegnanti che hanno l'ufficio nello stesso edificio
```sql
 SELECT COUNT(`teachers`.`id`) AS `teachers_with_same_address` FROM `teachers` GROUP BY `teachers`.`office_address`;
```
* Calcolare la media dei voti di ogni appello d'esame
```sql
SELECT AVG(`exam_student`.vote) AS `average_vote`, `exam_id` FROM exam_student GROUP BY exam_id
```
* Contare quanti corsi di laurea ci sono per ogni dipartimento
```sql
SELECT `department_id` AS `departments_number`, COUNT(id) AS 'numero corsi' FROM `degrees` GROUP BY `department_id`;
```
# Join:
* Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
```sql

```
* Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze
```sql

```
* Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
```sql

```
* Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome
```sql

```
* Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
```sql

```
* Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)
```sql

```
* BONUS: Selezionare per ogni studente quanti tentativi d’esame ha sostenuto per superare ciascuno dei suoi esami
```sql

```
Modellizzare la struttura di una tabella per memorizzare tutti i dati riguardanti una università:
- sono presenti diversi **Dipartimenti** (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
- ogni Dipartimento offre più **Corsi di Laurea** (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
- ogni Corso di Laurea prevede diversi **Corsi** (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
- ogni Corso può essere tenuto da diversi **Insegnanti**;
- ogni Corso prevede più **appelli d'Esame**;
- ogni **Studente** è iscritto ad un solo Corso di Laurea;
- ogni Studente può iscriversi a più appelli di Esame;
- per ogni appello d'Esame a cui lo Studente ha partecipato, è necessario memorizzare il **voto** ottenuto, anche se non sufficiente.

DEPARTMENTS:
- id | BIGINT | AI NOTNULL UNIQUE 
- name
- rector


DEGREE COURSES:
- id | BIGINT | AI NOTNULL UNIQUE
- departments_id
- name 
- students_number
- teachers_number
- classes
- exams_number


COURSES:
- id | BIGINT | AI NOTNULL UNIQUE
- degree_courses_id
- name
- credits
- teachers
- classes
- lesson_hours
- students_number


STUDENTS:
- id | BIGINT | AI NOTNULL UNIQUE
- degree_courses_id
- name
- lastname
- freshman_number |
- cfu_numbers


TEACHERS:
- id | BIGINT | AI NOTNULL UNIQUE
- name
- lastname
- age
- email
- courses_name
- courses_id


EXAMS:
- id | BIGINT | AI NOTNULL UNIQUE
- number_of_appeals
- teachers_id
- students_id
- courses_id
- date
- vote



RELATIONSHIP:
- oneToMany => degree_courses & departments
- oneToMany => degree_courses & courses         
- manyToMany => courses & teachers (+ pivot table)
- oneToMany => courses & exams
- oneToMany => students & exams
- oneToMany => teachers & exams
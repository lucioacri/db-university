<!--    QUERY SELECT -->

1- Studenti nati nel 1990:

SELECT \*
FROM `students`
WHERE
YEAR(`date_of_birth`) = "1990";

2- Corsi 10+ crediti:

SELECT \*
FROM `courses`
WHERE `cfu` > "10";

3- Studenti 30+ anni:

SELECT \*
FROM `students`
WHERE `date_of_birth` < "1995-06-11";

4- Corsi primo semestre primo anno:

SELECT \*
FROM `courses`
WHERE `period` = "I semestre"
AND `year` = "1";

5- Appelli esame dopo le 14 del 20/06/2020:

SELECT \*
FROM `exams`
WHERE `date` = "2020-06-20"
AND `hour` > "14:00:00";

6- Corsi di laurea magistrale:

SELECT \*
FROM `degrees`
WHERE `level` = "magistrale";

7- Numero dipartimenti università:

SELECT COUNT(\*)
FROM `departments`;

8- Insegnanti senza numero di telefono:

SELECT COUNT(\*)
FROM `teachers`
WHERE `phone` IS NULL;

<!-- GROUP BY -->

1- Numero iscritti ogni anno:

SELECT COUNT(\*), YEAR(`enrolment_date`)
FROM `students`
GROUP BY YEAR(`enrolment_date`);

2- Insegnanti con ufficio nello stesso edificio:

SELECT `office_address`, COUNT(\*)
FROM `teachers`
GROUP BY `office_address`;

3- Media voti di ogni appello d'esame:

SELECT `exam_id`, AVG (`vote`)
FROM `exam_student`
GROUP BY `exam_id`;

4- Corsi di laurea per ogni dipartimento:

SELECT `department_id`, COUNT(`name`)
FROM `degrees`
GROUP BY `department_id`;

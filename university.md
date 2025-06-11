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

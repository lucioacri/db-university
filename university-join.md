<!-- 1- Selezionare tutti gli studenti iscritti al corso di laurea in economia -->

SELECT `students`.`name`,
`students`.`id`,
`degrees`.`name`
FROM `degrees`

INNER JOIN `students`
ON `degrees`.`id` = `students`.`degree_id`

WHERE `degrees`.`name` = "Corso di Laurea in Economia";

<!-- 2- Selezionare tutti i corsi di laurea magistrale del dipartimento di neuroscienze -->

SELECT `degrees`.`id` AS `degree_id`,
`degrees`.`name` AS `degree_name`,
`departments`.`id` AS `department_id`,
`departments`.`name` AS `department_name`

FROM `degrees`

INNER JOIN `departments`
ON `departments`.`id` = `degrees`.`department_id`

WHERE `degrees`.`level` = "magistrale" AND `departments`.`name` = "dipartimento di neuroscienze";

<!-- 3- Selezionare tutti i corsi in cui insegna fulvio amato (id=44) -->

<!-- 4- Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome -->

<!-- 5- Selezionare tutti i corsi di laurea con i relativi corsi ed insegnanti -->

<!-- 6- Selezionare tutti i docenti che insegnano nel dipartimento di matematica (54) -->

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

FROM `teachers`

INNER JOIN `course_teacher`
ON `teachers`.`id` = `course_teacher`.`teacher_id`

INNER JOIN `courses`
ON `courses`.`id` = `course_teacher`.`course_id`

WHERE `teachers`.`id` = 44
;

<!-- 4- Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome -->

SELECT `students`.`id` AS `student_id`,
`students`.`surname` AS `student_surname`,
`students`.`name` AS `student_name`,
`degrees`.`name` AS `degree_name`,
`departments`.`name` AS `department_name`
FROM `students`

INNER JOIN `degrees`
ON `students`.`degree_id` = `degrees`.`id`

INNER JOIN `departments`
ON `degrees`.`department_id` = `departments`.`id`

ORDER BY `student_surname`, `student_name`
;

<!-- 5- Selezionare tutti i corsi di laurea con i relativi corsi ed insegnanti -->

SELECT `degrees`.`id` AS `degree_id`,
`degrees`.`name` AS `degree_name`,
`degrees`.`level` AS `degree_level`,
`courses`.`name` AS `course_name`,
`courses`.`cfu` AS `course_cfu`,
`teachers`.`id` AS `teacher_id`,
`teachers`.`surname` AS `teacher_surname`,
`teachers`.`name` AS `teacher_name`

FROM `degrees`

INNER JOIN `courses`
ON `degrees`.`id` = `courses`.`degree_id`

INNER JOIN `course_teacher`
ON `courses`.`id` = `course_teacher`.`course_id`

INNER JOIN `teachers`
ON `course_teacher`.`teacher_id` = `teachers`.`id`

ORDER BY `degree_name`
;

<!-- 6- Selezionare tutti i docenti che insegnano nel dipartimento di matematica (54) -->

SELECT `teachers`.`id` AS `teacher_id`,
`teachers`.`surname` AS `teacher_surname`,
`teachers`.`name` AS `teacher_name`,
`departments`.`name` AS `department_name`

FROM `teachers`

INNER JOIN `course_teacher`
ON `teachers`.`id` = `course_teacher`.`teacher_id`

INNER JOIN `courses`
ON `course_teacher`.`course_id` = `courses`.`id`

INNER JOIN `degrees`
ON `courses`.`degree_id` = `degrees`.`id`

INNER JOIN `departments`
ON `degrees`.`department_id` = `departments`.`id`

WHERE `departments`.`name` = "dipartimento di matematica"

ORDER BY `teacher_surname`,`teacher_name`
;

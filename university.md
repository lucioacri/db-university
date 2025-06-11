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
